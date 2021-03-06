---
title: 'IDebugMethodField:: EnumAllLocals |Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- IDebugMethodField::EnumAllLocals
helpviewer_keywords:
- IDebugMethodField::EnumAllLocals method
ms.assetid: 0bc7cc13-2628-4bd8-8c06-4d2aa6755ea8
caps.latest.revision: 10
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 2f0f89c3fee45d6d56b845753958d697e41ab11f
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/02/2020
ms.locfileid: "68190885"
---
# <a name="idebugmethodfieldenumalllocals"></a>IDebugMethodField::EnumAllLocals
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

コンパイラによって内部的に生成されたものも含め、メソッドのすべてのローカル変数の列挙子を作成します。  
  
## <a name="syntax"></a>構文  
  
```cpp#  
HRESULT EnumAllLocals(   
   IDebugAddress*     pAddress,  
   IEnumDebugFields** ppLocals  
);  
```  
  
```csharp  
int EnumAllLocals(  
   IDebugAddress        pAddress,   
   out IEnumDebugFields ppLocals  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pAddress`  
 から特定のスコープまたはコンテキストを指すメソッド内のデバッグアドレスを表す [IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md) オブジェクト。  
  
 `ppLocals`  
 入出力指定されたスコープ内のすべてのローカルのリストを表す [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md) オブジェクトを返します。それ以外の場合、は、ローカルがないことを示す null 値を返します。  
  
## <a name="return-value"></a>戻り値  
 成功した場合、は S_OK を返します。ローカルがない場合は S_FALSE を返します。 それ以外の場合はエラー コードを返します。  
  
## <a name="remarks"></a>注釈  
 指定されたデバッグアドレスを含むブロック内で定義されている変数のみが列挙されます。 このメソッドには、コンパイラによって生成されるローカル変数が含まれます。 必要なものがすべてソースで明示的に定義されている場合は、 [enumlocals](../../../extensibility/debugger/reference/idebugmethodfield-enumlocals.md) メソッドを呼び出します。  
  
 メソッドには、複数のスコープコンテキストまたはブロックを含めることができます。  
  
## <a name="see-also"></a>参照  
 [IDebugMethodField](../../../extensibility/debugger/reference/idebugmethodfield.md)   
 [IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md)   
 [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md)   
 [EnumLocals](../../../extensibility/debugger/reference/idebugmethodfield-enumlocals.md)
