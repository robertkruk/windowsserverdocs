---
title: Fsutil transaction
ms.custom: na
ms.prod: windows-server-2012
ms.reviewer: na
ms.suite: na
ms.technology: 
  - techgroup-storage
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: ac0d3be7-3e19-4b79-8aa5-daf8d5affd28
author: JasonGerend
---
# Fsutil transaction
Manages NTFS transactions.  
  
For examples of how to use this command, see [Examples](#BKMK_examples) .  
  
## Syntax  
  
```  
fsutil transaction [commit] <GUID>  
fsutil transaction [fileinfo] <Filename>  
fsutil transaction [list]  
fsutil transaction [query] [{Files|All}] <GUID>  
fsutil transaction [rollback] <GUID>  
  
```  
  
### Parameters  
  
|Parameter|Description|  
|-------------|---------------|  
|commit|Marks the end of a successful implicit or explicit specified transaction.|  
|<GUID>|Specifies the GUID value that represents a transaction.|  
|fileinfo|Displays transaction information for the specified file.|  
|<Filename>|Specifies full path and file name.|  
|list|Displays a list of currently running transactions.|  
|query|Displays information for the specified transaction.<br /><br />-   If **fsutil transaction query Files** is specified, the file information will be displayed only for the specified transaction.<br />-   If **fsutil transaction query All** is specified, all information for the transaction will be displayed.|  
|rollback|Rolls back a specified transaction to the beginning.|  
  
### Remarks  
  
-   Transactional NTFS was introduced in [!INCLUDE[nextref_longhorn](includes/nextref_longhorn_md.md)].  
  
### <a name="BKMK_examples"></a>Examples  
To display transaction information for file c:\\test.txt, type:  
  
```  
fsutil transaction fileinfo c:\test.txt    
```  
  
### Additional references  
[Command-Line Syntax Key](Command-Line-Syntax-Key.md)  
  
[Fsutil](Fsutil.md)  
  
[Transactional NTFS](http://go.microsoft.com/fwlink/?LinkID=165402)  
  
