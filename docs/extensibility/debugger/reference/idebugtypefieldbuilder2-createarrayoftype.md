---
title: 'IDebugTypeFieldBuilder2:: CreateArrayOfType |Microsoft Docs'
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- IDebugTypeFieldBuilder2::CreateArrayOfType
- CreateArrayOfType
ms.assetid: 85166ac9-0bff-49a0-b2fd-ca7f7a8eae4b
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 3d7a229ea92b57252a9f01976e7b5c80348bd314
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/02/2020
ms.locfileid: "80718314"
---
# <a name="idebugtypefieldbuilder2createarrayoftype"></a>IDebugTypeFieldBuilder2::CreateArrayOfType
指定した型とサイズの配列を作成します。

## <a name="syntax"></a>構文

```cpp
HRESULT CreateArrayOfType (
   IDebugField*  pTypeField,
   DWORD         rank,
   IDebugField** pArrayOfTypeField
);
```

```csharp
int CreateArrayOfType (
   IDebugField     pTypeField,
   uint            rank,
   out IDebugField pArrayOfTypeField
);
```

## <a name="parameters"></a>パラメーター
`pTypeField`\
から配列が保持する要素の型。

`rank`\
から配列内の要素の数。

`pArrayOfTypeField`\
入出力新しい配列を表す [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) オブジェクトを返します。

## <a name="return-value"></a>戻り値
 成功した場合はを返し `S_OK` ます。それ以外の場合はエラーコードを返します。

## <a name="see-also"></a>関連項目
- [IDebugTypeFieldBuilder2](../../../extensibility/debugger/reference/idebugtypefieldbuilder2.md)
