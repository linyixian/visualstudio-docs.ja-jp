---
title: PARSEFLAGS |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- PARSEFLAGS
helpviewer_keywords:
- PARSEFLAGS enumeration
ms.assetid: 47943f0a-54cb-4493-a62e-5dba97bd4c35
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 0cc70fdd9fe1279e4d419a422b970eb3d3b07c65
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/02/2020
ms.locfileid: "80714119"
---
# <a name="parseflags"></a>PARSEFLAGS
式を解析する方法を指定します。

## <a name="syntax"></a>構文

```cpp
enum enum_PARSEFLAGS { 
   PARSE_EXPRESSION            = 0x0001,
   PARSE_FUNCTION_AS_ADDRESS   = 0x0002,
   PARSE_DESIGN_TIME_EXPR_EVAL = 0x1000
};
typedef DWORD PARSEFLAGS;
```

```csharp
public enum enum_PARSEFLAGS { 
   PARSE_EXPRESSION            = 0x0001,
   PARSE_FUNCTION_AS_ADDRESS   = 0x0002,
   PARSE_DESIGN_TIME_EXPR_EVAL = 0x1000
};
```

## <a name="fields"></a>フィールド
 `PARSE_EXPRESSION`\
 式がステートメントではないことを示します。

 `PARSE_FUNCTION_AS_ADDRESS`\
 式がアドレスとして解析 (および後で評価) されることを示します。

 `PARSE_DESIGN_TIME_EXPR_EVAL`\
 デザイン時に式が解析されることを示します (つまり、デザイナーが開いている場合)。

## <a name="remarks"></a>注釈
 [Parsetext](../../../extensibility/debugger/reference/idebugexpressioncontext2-parsetext.md)メソッドおよび[Parse](../../../extensibility/debugger/reference/idebugexpressionevaluator-parse.md)メソッドにパラメーターとして渡されます。

## <a name="requirements"></a>必要条件
 ヘッダー: msdbg. h

 名前空間: VisualStudio。

 アセンブリ: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>関連項目
- [列挙型](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)
- [ParseText](../../../extensibility/debugger/reference/idebugexpressioncontext2-parsetext.md)
- [Parse](../../../extensibility/debugger/reference/idebugexpressionevaluator-parse.md)
