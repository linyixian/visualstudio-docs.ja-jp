---
title: 'IDebugStackFrame3:: InterceptCurrentException |Microsoft Docs'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugStackFrame3::InterceptCurrentException
helpviewer_keywords:
- IDebugStackFrame3::InterceptCurrentException
ms.assetid: 116c7324-7645-4c15-b484-7a5cdd065ef5
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 7debd5323e753c6c5fd1476eac3c062fb63393b9
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/02/2020
ms.locfileid: "80719481"
---
# <a name="idebugstackframe3interceptcurrentexception"></a>IDebugStackFrame3::InterceptCurrentException
現在のスタックフレームが現在の例外をインターセプトするときに、デバッガーによって呼び出されます。

## <a name="syntax"></a>構文

```cpp
HRESULT InterceptCurrentException(
   INTERCEPT_EXCEPTION_ACTION dwFlags,
   UINT64*                    pqwCookie
);
```

```csharp
int InterceptCurrentException(
   uint dwFlags,
   out  ulong pqwCookie
);
```

## <a name="parameters"></a>パラメーター
`dwFlags`\
から異なるアクションを指定します。 現時点では、 [INTERCEPT_EXCEPTION_ACTION](../../../extensibility/debugger/reference/intercept-exception-action.md) 値のみがサポートされているため、 `IEA_INTERCEPT` 指定する必要があります。

`pqwCookie`\
入出力特定の例外を識別する一意の値。

## <a name="return-value"></a>戻り値
 成功した場合は S_OK を返します。それ以外の場合は、エラーコードを返します。

 最も一般的なエラーの例を次に示します。

|エラー|説明|
|-----------|-----------------|
|`E_EXCEPTION_CANNOT_BE_INTERCEPTED`|現在の例外はインターセプトできません。|
|`E_EXCEPTION_CANNOT_UNWIND_ABOVE_CALLBACK`|現在の実行フレームはハンドラーを検索していません。|
|`E_INTERCEPT_CURRENT_EXCEPTION_NOT_SUPPORTED`|このフレームでは、このメソッドはサポートされていません。|

## <a name="remarks"></a>注釈
 例外がスローされると、デバッガーは例外処理プロセス中のキーポイントで実行時から制御を取得します。 これらのキーの間、デバッガーは、フレームが例外をインターセプトする必要がある場合に、現在のスタックフレームに要求できます。 このように、インターセプトされた例外は基本的に、スタックフレームに例外ハンドラーがない場合でも (プログラムコードの try/catch ブロックなど)、スタックフレームの実行時例外ハンドラーになります。

 デバッガーは、例外がインターセプトされる必要があるかどうかを知りたい場合、現在のスタックフレームオブジェクトに対してこのメソッドを呼び出します。 このメソッドは、例外のすべての詳細を処理します。 [IDebugStackFrame3](../../../extensibility/debugger/reference/idebugstackframe3.md)インターフェイスが実装されていない場合、または `InterceptStackException` メソッドがエラーを返した場合、デバッガーは通常どおり例外の処理を続行します。

> [!NOTE]
> 例外は、マネージコード内でのみ、つまり、デバッグ中のプログラムが .NET ランタイムで実行されている場合にのみインターセプトできます。 もちろん、サードパーティの言語実装者は、 `InterceptStackException` 独自のデバッグエンジンでを実装できます。

 インターセプトが完了すると、 [IDebugInterceptExceptionCompleteEvent2](../../../extensibility/debugger/reference/idebuginterceptexceptioncompleteevent2.md) が通知されます。

## <a name="see-also"></a>関連項目
- [IDebugStackFrame3](../../../extensibility/debugger/reference/idebugstackframe3.md)
- [INTERCEPT_EXCEPTION_ACTION](../../../extensibility/debugger/reference/intercept-exception-action.md)
- [IDebugInterceptExceptionCompleteEvent2](../../../extensibility/debugger/reference/idebuginterceptexceptioncompleteevent2.md)
