---
title: GETNAME_TYPE |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- GETNAME_TYPE
helpviewer_keywords:
- GETNAME_TYPE enumeration
ms.assetid: 2f9f1679-e9e8-4c9c-ac90-aa07bfe69914
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 1d0d146ec4ed7340bde36b298df9d455257b35fe
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/02/2020
ms.locfileid: "80736674"
---
# <a name="getname_type"></a>GETNAME_TYPE
取得するファイルの名前の種類を指定します。

## <a name="syntax"></a>構文

```cpp
enum enum_GETNAME_TYPE {
    GN_NAME         = 0,
    GN_FILENAME     = 1,
    GN_BASENAME     = 2,
    GN_MONIKERNAME  = 3,
    GN_URL          = 4,
    GN_TITLE        = 5,
    GN_STARTPAGEURL = 6
};
typedef DWORD GETNAME_TYPE;
```

```csharp
public enum enum_GETNAME_TYPE {
    GN_NAME         = 0,
    GN_FILENAME     = 1,
    GN_BASENAME     = 2,
    GN_MONIKERNAME  = 3,
    GN_URL          = 4,
    GN_TITLE        = 5,
    GN_STARTPAGEURL = 6
};
```

## <a name="fields"></a>フィールド
`GN_NAME`\
ドキュメントまたはコンテキストのフレンドリ名を指定します。

`GN_FILENAME`\
ドキュメントまたはコンテキストの完全パスを指定します。

`GN_BASENAME`\
ドキュメントまたはコンテキストの完全パスではなく、基本ファイル名を指定します。

`GN_MONIKERNAME`\
モニカーの形式で、ドキュメントまたはコンテキストの一意な名前を指定します。

`GN_URL`\
ドキュメントまたはコンテキストの URL 名を指定します。

`GN_TITLE`\
ドキュメントのタイトルを指定します (存在する場合)。

`GN_STARTPAGEURL`\
プロセスの開始ページの URL を取得します。

## <a name="remarks"></a>解説
これらの値は、返される名前の種類を指定するために、 [getname](../../../extensibility/debugger/reference/idebugdocument2-getname.md)、 [Getname](../../../extensibility/debugger/reference/idebugdocumentcontext2-getname.md)、および [getname](../../../extensibility/debugger/reference/idebugprocess2-getname.md) メソッドにパラメーターとして渡されます。

## <a name="requirements"></a>必要条件
ヘッダー: msdbg. h

名前空間: VisualStudio。

アセンブリ: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>関連項目
- [列挙型](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)
- [GetName](../../../extensibility/debugger/reference/idebugdocument2-getname.md)
- [GetName](../../../extensibility/debugger/reference/idebugdocumentcontext2-getname.md)
- [GetName](../../../extensibility/debugger/reference/idebugprocess2-getname.md)
