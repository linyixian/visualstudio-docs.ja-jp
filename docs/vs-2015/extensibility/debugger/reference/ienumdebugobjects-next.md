---
title: 'IEnumDebugObjects:: Next |Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- IEnumDebugObjects::Next
helpviewer_keywords:
- IEnumDebugObjects::Next method
ms.assetid: e54c3055-6030-4dc9-9f7a-5e3ce75f252f
caps.latest.revision: 7
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 51978f3e77cc2c02768860ae91e9db7d0cff2495
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/02/2020
ms.locfileid: "68160954"
---
# <a name="ienumdebugobjectsnext"></a>IEnumDebugObjects::Next
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

このメソッドは、列挙体から次の要素のセットを返します。  
  
## <a name="syntax"></a>構文  
  
```cpp#  
HRESULT Next(  
   ULONG          celt,  
   IDebugObject** rgelt,  
   ULONG*         pceltFetched  
);  
```  
  
```csharp  
int Next(  
   uint           celt,  
   IDebugObject[] rgelt,  
   ref uint       pceltFetched  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `celt`  
 から取得する要素の数。 配列の最大サイズも指定し `rgelt` ます。  
  
 `rgelt`  
 [入力、出力]入力する [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md) 要素の配列。  
  
 `pceltFetched`  
 入出力で実際に返された要素の数を返し `rgelt` ます。  
  
## <a name="return-value"></a>戻り値  
 正常に終了した場合は、`S_OK` を返します。 要求された `S_FALSE` 数の要素を返すことができなかった場合は、を返します。それ以外の場合は、エラーコードを返します。  
  
## <a name="see-also"></a>参照  
 [IEnumDebugObjects](../../../extensibility/debugger/reference/ienumdebugobjects.md)   
 [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md)
