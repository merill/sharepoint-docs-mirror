---
layout: Conceptual
title: "Tutorial: Run 'What-If' analysis - SharePoint in Microsoft 365 | Microsoft Learn"
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/tutorial-run-what-if-analysis
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.reviewer: rekamath
ms.author: ruihu
author: maggierui
manager: jtemper
ms.date: 2024-10-03T00:00:00.0000000Z
audience: Admin
f1.keywords:
- NOCSH
ms.topic: tutorial
ms.service: sharepoint-online
ms.subservice: admin
ms.localizationpriority: medium
search.appverid:
- SPO160
- SPS150
- MET150
description: This article provides guidance on how to run 'What-If' analysis on version storage report file.
locale: en-us
document_id: 025cd4a0-7bef-75ea-56f9-02970be851f8
document_version_independent_id: dd902810-f3d8-ff41-4997-0a2094f11058
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/tutorial-run-what-if-analysis.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: tutorial-run-what-if-analysis
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/tutorial-run-what-if-analysis.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
- https://authoring-docs-microsoft.poolparty.biz/devrel/1dd701e0-441f-4b0a-9806-aa47decc4e35
- https://authoring-docs-microsoft.poolparty.biz/devrel/60932d05-feee-4685-a73b-595e25dd9318
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
- https://authoring-docs-microsoft.poolparty.biz/devrel/0a2fc935-5977-4aa6-9f55-0be03bd2acb8
- https://authoring-docs-microsoft.poolparty.biz/devrel/c43bb58b-1190-419b-8d18-e6052371b599
platformId: 473537ef-1fc2-2dcb-bdba-9f24ea2e9270
---

# Tutorial: Run 'What-If' analysis - SharePoint in Microsoft 365 | Microsoft Learn

In this tutorial, we discuss how to leverage provided scripts and excel examples to understand the impact of applying either automatic or manual limits on version storage or impacted users. You will learn how to:

- Run impact analysis of setting Automatic limits.
- Run impact analysis of expiring versions older than specified days.
- Run impact analysis of storing version within specified count limits.

## Before you begin

In the previous tutorial, you had generated a version storage usage report. This tutorial assumes that the report generation job has successfully completed and the report is fully populated. Start by downloading the report file to your local computer. Use the scripts provided below to apply the desired setting on the file and analyze the impact.

## Run impact analysis of setting automatic version history limits

Here's an example of PowerShell script you could apply to generate a What-If Report file that applies the **Automatic Expiration** policy on the report file `C:\Report.csv`. 

```PowerShell
# save this file as ScheduleUpdate_Auto.ps1 

param (
  [Parameter(Mandatory=$true)][string]$ImportPath,
  [Parameter(Mandatory=$true)][string]$ExportPath
)

$Schedule = Import-Csv -Path $ImportPath 
$Schedule | 
  ForEach-Object { 
    $_.TargetExpirationDate = $_.AutomaticPolicyExpirationDate
  } 
$Schedule | 
  Export-Csv -Path $ExportPath -UseQuotes AsNeeded -NoTypeInformation
```

Note

Use PowerShell 7 to run the commands. You can install PowerShell 7 by following these instructions: [Installing PowerShell on Windows - PowerShell | Microsoft Learn](/en-us/powershell/scripting/install/installing-powershell-on-windows).

[![Screenshot of expiration automation.](sharepointonline/media/version-history/expiration-automation.png)](sharepointonline/media/version-history/expiration-automation.png#lightbox)

## Run impact analysis of setting manual expiration limits

Here's an example of PowerShell script to generate a What-If Report file. It applies **Manual Expiration** with expire-after days set to **30** on the report file `C:\Report.csv`. 

```PowerShell
# save this file as ScheduleUpdate_ExpireAfter.ps1

param (
  [Parameter(Mandatory=$false)][string]$ImportPath,
  [Parameter(Mandatory=$false)][string]$ExportPath,
  [Parameter(Mandatory=$false)][double]$ExpireAfter
)

function StringToDateTime($Value) { return [string]::IsNullOrEmpty($Value) ? $null : [DateTime]::ParseExact($Value, "yyyy-MM-ddTHH:mm:ssK", $null) }
function DateTimeToString($Value) { return $null -eq $Value ? "" : $Value.ToString("yyyy-MM-ddTHH:mm:ssK") }  

$Schedule = Import-Csv -Path $ImportPath 
$Schedule | 
  ForEach-Object { 
    $SnapshotDate = StringToDateTime -Value $_.SnapshotDate
    $TargetExpirationDate = $SnapshotDate.AddDays($ExpireAfter)
    $_.TargetExpirationDate = DateTimeToString -Value $TargetExpirationDate
  } 
$Schedule | 
  Export-Csv -Path $ExportPath -UseQuotes AsNeeded -NoTypeInformation
```

Note

Use PowerShell 7 to run the commands. You can install PowerShell 7 by following these instructions: [Installing PowerShell on Windows - PowerShell | Microsoft Learn.](/en-us/powershell/scripting/install/installing-powershell-on-windows)

[![Screenshot of manual expiration.](sharepointonline/media/version-history/manual-expiration.png)](sharepointonline/media/version-history/manual-expiration.png#lightbox)

## Run impact analysis of setting manual count limits

Here's an example of PowerShell script to generate a What-If report file. It applies a **Manual with Count Limits** policy with major version limit set to **50** on the report file `C:\Report.csv`.

```PowerShell
# save this file as ScheduleUpdate_Count.ps1

param (
  [Parameter(Mandatory=$true)][string]$ImportPath,
  [Parameter(Mandatory=$true)][string]$ExportPath,
  [Parameter(Mandatory=$true)][int]$MajorVersionLimit
)

$Report = Import-Csv -Path $ImportPath 

$PreviousWebId = [Guid]::Empty
$PreviousDocId = [Guid]::Empty
$PreviousWebUrl = [string]::Empty
$PreviousFileUrl = [string]::Empty
$PreviousModifiedByUserId = [string]::Empty
$PreviousModifiedByDisplayName = [string]::Empty

$FileToVersions = @{}

foreach ($Version in $Report)
{  
  $WebId = [string]::IsNullOrEmpty($Version."WebId.Compact") ? $PreviousWebId : [Guid]::Parse($Version."WebId.Compact")
  $DocId = [string]::IsNullOrEmpty($Version."DocId.Compact") ? $PreviousDocId : [Guid]::Parse($Version."DocId.Compact")
  $WebUrl = [string]::IsNullOrEmpty($Version."WebUrl.Compact") ? $PreviousWebUrl : $Version."WebUrl.Compact"
  $FileUrl = [string]::IsNullOrEmpty($Version."FileUrl.Compact") ? $PreviousFileUrl : $Version."FileUrl.Compact"
  $ModifiedByUserId = [string]::IsNullOrEmpty($Version."ModifiedBy_UserId.Compact") ? $PreviousModifiedByUserId : $Version."ModifiedBy_UserId.Compact"
  $ModifiedByDisplayName = [string]::IsNullOrEmpty($Version."ModifiedBy_DisplayName.Compact") ? $PreviousModifiedByDisplayName : $Version."ModifiedBy_DisplayName.Compact"

  $PreviousWebId = $WebId
  $PreviousDocId = $DocId
  $PreviousWebUrl = $WebUrl
  $PreviousFileUrl = $FileUrl
  $PreviousModifiedByUserId = $ModifiedByUserId
  $PreviousModifiedByDisplayName = $ModifiedByDisplayName

  if (($PreviousWebId -eq [Guid]::Empty) -or ($WebId -eq [Guid]::Empty) -or 
    ($PreviousDocId -eq [Guid]::Empty) -or ($DocId -eq [Guid]::Empty))
  {
    throw "Compact column error."
  }

  $Version."WebId.Compact" = $WebId
  $Version."DocId.Compact" = $DocId
  $Version."WebUrl.Compact" = $WebUrl
  $Version."FileUrl.Compact" = $FileUrl
  $Version."ModifiedBy_UserId.Compact" = $ModifiedByUserId
  $Version."ModifiedBy_DisplayName.Compact" = $ModifiedByDisplayName
   
  if ($null -eq $FileToVersions[$DocId]) 
  {
    $FileToVersions[$DocId] = [System.Collections.Generic.PriorityQueue[Object, Int32]]::new()
  }

  $VersionsQueue = $FileToVersions[$DocId]

  $VersionNumber = [Int32]::Parse($Version.MajorVersion) * 512 + [Int32]::Parse($Version.MinorVersion)
  $VersionsQueue.Enqueue($Version, -$VersionNumber)
}

$Schedule = [System.Collections.Generic.List[Object]]::new()

foreach ($FilesAndVersions in $FileToVersions.GetEnumerator())
{
  $VersionsQueue = $FilesAndVersions.Value
  $NumMajorVersionsSeen = 0
  while ($VersionsQueue.Count -gt 0)
  {
    $Version = $VersionsQueue.Dequeue()
    if ($NumMajorVersionsSeen -ge $MajorVersionLimit) {
      $Version.TargetExpirationDate = [DateTime]::new(2000, 1, 1).ToString("yyyy-MM-ddTHH:mm:ssK")
    }
     
    if ([int]::Parse($Version.MinorVersion) -eq 0) { $NumMajorVersionsSeen++ }

    $Schedule.Add($Version)
  }
}

$Schedule | 
  Export-Csv -Path $ExportPath -UseQuotes AsNeeded -NoTypeInformation
```

Note

Use PowerShell 7 to run the commands. You can install PowerShell 7 by following these instructions: [Installing PowerShell on Windows - PowerShell | Microsoft Learn](/en-us/powershell/scripting/install/installing-powershell-on-windows).

[![Screenshot of manual with count limits-b.](sharepointonline/media/version-history/manual-with-count-limits-b.png)](sharepointonline/media/version-history/manual-with-count-limits-b.png#lightbox)