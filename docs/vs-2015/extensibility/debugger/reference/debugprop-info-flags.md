---
title: DEBUGPROP_INFO_FLAGS |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- DEBUGPROP_INFO_FLAGS
helpviewer_keywords:
- DBGPROP_INFO_FLAGS enumeration
ms.assetid: 1c7fe777-615e-4929-9ed4-970d9fe0eb81
caps.latest.revision: 12
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 764d28972575e8da9ef499e6d33a4a4a1deb3b07
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/02/2020
ms.locfileid: "68143005"
---
# <a name="debugprop_info_flags"></a>DEBUGPROP_INFO_FLAGS
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

デバッグプロパティオブジェクトについて取得する情報を指定します。  
  
## <a name="syntax"></a>構文  
  
```cpp#  
enum enum_DEBUGPROP_INFO_FLAGS {   
   DEBUGPROP_INFO_FULLNAME          = 0x00000001,  
   DEBUGPROP_INFO_NAME              = 0x00000002,  
   DEBUGPROP_INFO_TYPE              = 0x00000004,  
   DEBUGPROP_INFO_VALUE             = 0x00000008,  
   DEBUGPROP_INFO_ATTRIB            = 0x00000010,  
   DEBUGPROP_INFO_PROP              = 0x00000020,  
   DEBUGPROP_INFO_VALUE_AUTOEXPAND  = 0x00010000,  
   DEBUGPROP_INFO_VALUE_NOFUNCEVAL  = 0x00020000,  
   DEBUGPROP_INFO_VALUE_RAW         = 0x00040000,  
   DEBUGPROP_INFO_VALUE_NO_TOSTRING = 0x00080000  
   DEBUGPROP_INFO_NONE              = 0x00000000,  
   DEBUGPROP_INFO_STANDARD          = DEBUGPROP_INFO_ATTRIB |  
                                      DEBUGPROP_INFO_NAME |  
                                      DEBUGPROP_INFO_TYPE |  
                                      DEBUGPROP_INFO_VALUE,  
   DEBUGPROP_INFO_ALL               = 0xffffffff  
};  
typedef DWORD DEBUGPROP_INFO_FLAGS;  
```  
  
```csharp  
public enum enum_DEBUGPROP_INFO_FLAGS {   
   DEBUGPROP_INFO_FULLNAME          = 0x00000001,  
   DEBUGPROP_INFO_NAME              = 0x00000002,  
   DEBUGPROP_INFO_TYPE              = 0x00000004,  
   DEBUGPROP_INFO_VALUE             = 0x00000008,  
   DEBUGPROP_INFO_ATTRIB            = 0x00000010,  
   DEBUGPROP_INFO_PROP              = 0x00000020,  
   DEBUGPROP_INFO_VALUE_AUTOEXPAND  = 0x00010000,  
   DEBUGPROP_INFO_VALUE_NOFUNCEVAL  = 0x00020000,  
   DEBUGPROP_INFO_VALUE_RAW         = 0x00040000,  
   DEBUGPROP_INFO_VALUE_NO_TOSTRING = 0x00080000  
   DEBUGPROP_INFO_NONE              = 0x00000000,  
   DEBUGPROP_INFO_STANDARD          = DEBUGPROP_INFO_ATTRIB |  
                                      DEBUGPROP_INFO_NAME |  
                                      DEBUGPROP_INFO_TYPE |  
                                      DEBUGPROP_INFO_VALUE,  
   DEBUGPROP_INFO_ALL               = 0xffffffff  
};  
```  
  
## <a name="members"></a>メンバー  
 DEBUGPROP_INFO_FULLNAME  
 フィールドを初期化/使用 `bstrFullName` します。  
  
 DEBUGPROP_INFO_NAME  
 フィールドを初期化/使用 `bstrName` します。  
  
 DEBUGPROP_INFO_TYPE  
 フィールドを初期化/使用 `bstrType` します。  
  
 DEBUGPROP_INFO_VALUE  
 フィールドを初期化/使用 `bstrValue` します。  
  
 DEBUGPROP_INFO_ATTRIB  
 フィールドを初期化/使用 `dwAttrib` します。  
  
 DEBUGPROP_INFO_PROP、  
 IDebugProperty2 インターフェイスを含むフィールドを初期化/使用し `pProperty` ます。 [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)  
  
 DEBUGPROP_INFO_VALUE_AUTOEXPAND  
 値フィールドに、この型のオブジェクトの自動展開値 (使用可能な場合) が含まれていることを指定します。  
  
 DEBUGPROP_INFO_VALUE_NOFUNCEVAL  
 非推奨になりました。  
  
 DEBUGPROP_INFO_VALUE_RAW  
 Beautified 値またはメンバーを返さないでください (つまり、値を書式設定しません)。  
  
 DEBUGPROP_INFO_VALUE_NO_TOSTRING  
 特別に合成された値を返さないでください (たとえば、 `ToString()` 値を生成するためにオブジェクトでを呼び出さないでください)。  
  
 DEBUGPROP_INFO_NONE  
 フラグが設定されていないことを指定します。  
  
 DEBUGPROP_INFO_STANDARD  
 `dwAttrib`、、 `bstrName` `bstrType` 、およびの各フィールドを初期化/使用し `bstrValue` ます。  
  
 DEBUGPROP_INFO_All  
 すべてのフラグのマスクを示します。  
  
## <a name="remarks"></a>注釈  
 これらの値は、 [DEBUG_PROPERTY_INFO](../../../extensibility/debugger/reference/debug-property-info.md)構造体を初期化するフィールドを示すために、 [GetPropertyInfo](../../../extensibility/debugger/reference/idebugproperty2-getpropertyinfo.md)、 [Enumchildren](../../../extensibility/debugger/reference/idebugproperty2-enumchildren.md)、および[enumchildren](../../../extensibility/debugger/reference/idebugstackframe2-enumproperties.md)メソッドに渡されます。  
  
 これらの値は、構造体のメンバーにも使用され、構造体 `dwFields` `DEBUG_PROPERTY_INFO` のどのフィールドが使用され、構造体が返されたときに有効であるかを示します。  
  
 これらの値は、ビットごとのを使用して組み合わせることができ `OR` ます。  
  
## <a name="requirements"></a>要件  
 ヘッダー: msdbg. h  
  
 名前空間: VisualStudio。  
  
 アセンブリ: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>参照  
 [列挙](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)   
 [GetPropertyInfo](../../../extensibility/debugger/reference/idebugproperty2-getpropertyinfo.md)   
 [EnumChildren](../../../extensibility/debugger/reference/idebugproperty2-enumchildren.md)   
 [EnumProperties](../../../extensibility/debugger/reference/idebugstackframe2-enumproperties.md)   
 [DEBUG_PROPERTY_INFO](../../../extensibility/debugger/reference/debug-property-info.md)
