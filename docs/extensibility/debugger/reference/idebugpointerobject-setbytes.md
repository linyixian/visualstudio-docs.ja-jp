---
title: 'IDebugPointerObject:: SetBytes |Microsoft Docs'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugPointerObject::SetBytes
helpviewer_keywords:
- IDebugPointerObject::SetBytes method
ms.assetid: 8c578b38-38d7-46f3-bb2e-8a730fccd334
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: dede3ee5291afbfbeab4d6e60dcbd56e205e4526
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/02/2020
ms.locfileid: "80725503"
---
# <a name="idebugpointerobjectsetbytes"></a>IDebugPointerObject::SetBytes
連続する一連のバイトからポイントする値を設定します。

## <a name="syntax"></a>構文

```cpp
HRESULT SetBytes( 
   DWORD  dwStart,
   DWORD  dwCount,
   BYTE*  pBytes,
   DWORD* pdwBytes
);
```

```csharp
int SetBytes(
   uint     dwStart,
   uint     dwCount,
   byte[]   pBytes,
   out uint pdwBytes
);
```

## <a name="parameters"></a>パラメーター
`dwStart`\
からが指すオブジェクトの先頭からのオフセット (バイト単位)。

`dwCount`\
から設定するバイト数。

`pBytes`\
から新しい値を表すバイト配列。 この値は、指定されたオフセットを開始位置として、オブジェクトに格納されます。

`pdwBytes`\
入出力実際に設定されたバイト数を返します。

## <a name="return-value"></a>戻り値
 成功した場合は S_OK を返します。それ以外の場合は、エラーコードを返します。

## <a name="remarks"></a>解説
 このメソッドは、この [IDebugPointerObject](../../../extensibility/debugger/reference/idebugpointerobject.md) によって表されるポインターがプリミティブ型またはプリミティブ型の単純な配列 (つまり、単純なバイトシーケンスで表すことができる配列) を指している場合に使用されます。 この `IDebugPointerObject` オブジェクトを null 参照にすることはできません (メモリ内のアドレスを指す必要があります)。

## <a name="see-also"></a>関連項目
- [GetBytes](../../../extensibility/debugger/reference/idebugpointerobject-getbytes.md)
- [IDebugPointerObject](../../../extensibility/debugger/reference/idebugpointerobject.md)
