---
title: 'IDebugProperty2:: SetValueAsReference |Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- IDebugProperty2::SetValueAsReference
helpviewer_keywords:
- IDebugProperty2::SetValueAsReference method
ms.assetid: 341b1b89-4ab8-4e1c-abe2-fb955df5c6b0
caps.latest.revision: 10
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: a94e3767ee05e39e847af27dc5999fa8bbbe2d44
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/02/2020
ms.locfileid: "68193455"
---
# <a name="idebugproperty2setvalueasreference"></a>IDebugProperty2::SetValueAsReference
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

このプロパティの値を、指定された参照の値に設定します。  
  
## <a name="syntax"></a>構文  
  
```cpp#  
HRESULT SetValueAsReference(  
   IDebugReference2** rgpArgs,  
   DWORD              dwArgCount,  
   IDebugReference2*  pValue,  
   DWORD              dwTimeout  
);  
```  
  
```csharp  
int SetValueAsReference(  
   IDebugReference2[] rgpArgs,  
   uint               dwArgCount,  
   IDebugReference2   pValue,  
   uint               dwTimeout  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `rgpArgs`  
 からマネージコードプロパティ setter に渡す引数の配列。 プロパティセッターが引数を取らない場合、またはこの [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md) オブジェクトがこのようなプロパティセッターを参照しない場合、は `rgpArgs` null 値である必要があります。 通常、このパラメーターは null 値です。  
  
 `dwArgCount`  
 から配列内の引数の数 `rgpArgs` 。  
  
 `pValue`  
 から [IDebugReference2](../../../extensibility/debugger/reference/idebugreference2.md) オブジェクトの形式で、このプロパティの設定に使用する値への参照。  
  
 `dwTimeout`  
 から値を設定するためにかかる時間 (ミリ秒単位)。 一般的な値は `INFINITE` です。 これは、考えられる評価にかかる時間に影響します。  
  
## <a name="return-value"></a>戻り値  
 成功した場合は、を返し `S_OK` ます。それ以外の場合は、次のいずれかのエラーコードを返します。  
  
|エラー|説明|  
|-----------|-----------------|  
|`E_SETVALUEASREFERENCE_NOTSUPPORTED`|参照からの値の設定はサポートされていません。|  
|`E_SETVALUE_VALUE_CANNOT_BE_SET`|このプロパティがメソッドを参照しているため、値を設定できません。|  
|`E_SETVALUE_VALUE_IS_READONLY`|値は読み取り専用であるため、設定できません。|  
|`E_NOTIMPL`|このメソッドは実装されていません。|  
  
## <a name="see-also"></a>参照  
 [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)   
 [IDebugReference2](../../../extensibility/debugger/reference/idebugreference2.md)
