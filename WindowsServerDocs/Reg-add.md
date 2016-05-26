---
title: Reg add
ms.custom: na
ms.prod: windows-server-2012
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: d9ad143e-dc10-4e2e-a229-408393c40079
author: jaimeo
---
# Reg add
Adds a new subkey or entry to the registry.  
  
## Syntax  
  
```  
reg add <KeyName> [{/v ValueName | /ve}] [/t DataType] [/s Separator] [/d Data] [/f]  
```  
  
For examples of how to use this command, see [Examples](#BKMK_examples).  
  
## Parameters  
  
|Parameter|Description|  
|-------------|---------------|  
|<KeyName*>*|Specifies the full path of the subkey or entry to be added. To specify a remote computer, include the computer name \(in the format \\\\<ComputerName>\\\) as part of the *KeyName*. Omitting \\\\ComputerName\\ causes the operation to default to the local computer. The *KeyName* must include a valid root key. Valid root keys for the local computer are: HKLM, HKCU, HKCR, HKU, and HKCC. If a remote computer is specified, valid root keys are: HKLM and HKU.|  
|\/v <ValueName>|Specifies the name of the registry entry to be added under the specified subkey.|  
|\/ve|Specifies that the registry entry that is added to the registry has a null value.|  
|\/t <Type>|Specifies the type for the registry entry. *Type* must be one of the following:<br /><br />REG\_SZ<br /><br />REG\_MULTI\_SZ<br /><br />REG\_DWORD\_BIG\_ENDIAN<br /><br />REG\_DWORD<br /><br />REG\_BINARY<br /><br />REG\_DWORD\_LITTLE\_ENDIAN<br /><br />REG\_LINK<br /><br />REG\_FULL\_RESOURCE\_DESCRIPTOR<br /><br />REG\_EXPAND\_SZ|  
|\/s <Separator>|Specifies the character to be used to separate multiple instances of data when the REG\_MULTI\_SZ data type is specified and more than one entry needs to be listed. If not specified, the default separator is **\\0**.|  
|\/d <Data>|Specifies the data for the new registry entry.|  
|\/f|Adds the registry entry without prompting for confirmation.|  
|\/?|Displays help for **reg add** at the command prompt.|  
  
## Remarks  
  
-   Subtrees cannot be added with this operation. This version of **reg** does not ask for confirmation when adding a subkey.  
  
-   The following table lists the return values for the **reg add** operation.  
  
|Value|Description|  
|---------|---------------|  
|0|Success|  
|1|Failure|  
  
-   For the REG\_EXPAND\_SZ key type, use the caret symbol \( **^** \) with **%**" inside the \/d parameter  
  
-  
  
## <a name="BKMK_examples"></a>Examples  
To add the key HKLM\\Software\\MyCo on remote computer ABC, type:  
  
```  
REG ADD \\ABC\HKLM\Software\MyCo  
```  
  
To add a registry entry to HKLM\\Software\\MyCo with a value named **Data** of type REG\_BINARY and data of **fe340ead**, type:  
  
```  
REG ADD HKLM\Software\MyCo /v Data /t REG_BINARY /d fe340ead  
```  
  
To add a multivalued registry entry to  HKLM\\Software\\MyCo with a value name of **MRU** of type REG\_MULTI\_SZ and data of **fax\\0mail\\0\\0**, type:  
  
```  
REG ADD HKLM\Software\MyCo /v MRU /t REG_MULTI_SZ /d fax\0mail\0\0  
```  
  
To add an expanded registry entry to HKLM\\Software\\MyCo with a value name of **Path** of type REG\_EXPAND\_SZ and data of **%systemroot%**, type:  
  
```  
REG ADD HKLM\Software\MyCo /v Path /t REG_EXPAND_SZ /d ^%systemroot^%  
```  
  
#### Additional references  
[Command-Line Syntax Key](Command-Line-Syntax-Key.md)  
  
