---
title: "SccGetExtendedCapabilities Function | Microsoft Docs"
ms.custom: ""
ms.date: "2018-06-30"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "SccGetExtendedCapabilities"
helpviewer_keywords: 
  - "SccGetExtendedCapabilities function"
ms.assetid: 588c6a92-2147-4d8b-a357-96ca7da0a092
caps.latest.revision: 17
ms.author: "gregvanl"
manager: "ghogen"
---
# SccGetExtendedCapabilities Function
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

The latest version of this topic can be found at [SccGetExtendedCapabilities Function](https://docs.microsoft.com/visualstudio/extensibility/sccgetextendedcapabilities-function).  
  
This function returns additional capabilities supported by the source control plug-in.  
  
## Syntax  
  
```cpp  
SCCRTN SccGetExtendedCapabilities(  
   LPVOID pContext,  
   LONG lSccExCaps,  
   LPBOOL pbSupported  
);  
```  
  
#### Parameters  
 pContext  
 [in] The source control plug-in context pointer.  
  
 lSccExCaps  
 [in] A flag specifying an extended capability for which to test (see the Extended Capability Code table in [Capability Flags](../extensibility/capability-flags.md) for the possible flags).  
  
 pbSupported  
 [out] Returns non-zero (`TRUE`) if the specified capability is supported; otherwise, returns zero (`FALSE`).  
  
## Return Value  
 The source control plug-in implementation of this function is expected to return one of the following values:  
  
|Value|Description|  
|-----------|-----------------|  
|SCC_OK|The get capability operation completed successfully.|  
|SCC_E_UNKNOWNERROR<br /><br /> SCC_E_NONSPECIFICERROR|Unknown or unspecified error occurred.|  
  
## Remarks  
 This method is called on demand; that is, when a capability needs to be tested, this method is called to determine if that capability is supported. Only one flag at a time is specified.  
  
## See Also  
 [Source Control Plug-in API Functions](../extensibility/source-control-plug-in-api-functions.md)   
 [Error Codes](../extensibility/error-codes.md)   
 [Capability Flags](../extensibility/capability-flags.md)
