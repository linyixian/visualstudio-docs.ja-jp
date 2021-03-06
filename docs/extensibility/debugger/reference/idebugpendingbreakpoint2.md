---
title: IDebugPendingBreakpoint2 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugPendingBreakpoint2
helpviewer_keywords:
- IDebugPendingBreakpoint2 interface
ms.assetid: d416b095-917e-475e-b796-ec0a03ffb8da
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 4e6f2c1df37e953a5d8c66bad9d0a3574a463fad
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/02/2020
ms.locfileid: "80725644"
---
# <a name="idebugpendingbreakpoint2"></a>IDebugPendingBreakpoint2
このインターフェイスは、コードの場所にバインドする準備ができているブレークポイントを表します。

## <a name="syntax"></a>構文

```
IDebugPendingBreakpoint2 : IUnknown
```

## <a name="notes-for-implementers"></a>実装側の注意
 デバッグエンジン (DE) は、ブレークポイントのサポートの一部としてこのインターフェイスを実装します。

## <a name="notes-for-callers"></a>呼び出し元に関する注意事項
 [Creatependingbreakpoint ポイント](../../../extensibility/debugger/reference/idebugengine2-creatependingbreakpoint.md)を呼び出すと、 [IDebugBreakpointRequest2](../../../extensibility/debugger/reference/idebugbreakpointrequest2.md)インターフェイスから保留中のブレークポイントが作成されます。 [Bind](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-bind.md)を呼び出すと、 `IDebugBreakpoint2` プログラムのバインドされたブレークポイントを表すインターフェイスが作成されます。

## <a name="methods-in-vtable-order"></a>Vtable 順序のメソッド
 次の表に、のメソッドを示し `IDebugPendingBreakpoint2` ます。

|Method|説明|
|------------|-----------------|
|[CanBind](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-canbind.md)|この保留中のブレークポイントをコードの場所にバインドできるかどうかを判断します。|
|[Bind](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-bind.md)|この保留中のブレークポイントを1つまたは複数のコードの場所にバインドします。|
|[GetState](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-getstate.md)|この保留中のブレークポイントの状態を取得します。|
|[GetBreakpointRequest](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-getbreakpointrequest.md)|この保留中のブレークポイントを作成するために使用されたブレークポイント要求を取得します。|
|[Virtualize](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-virtualize.md)|この保留中のブレークポイントの仮想化された状態を切り替えます。|
|[有効化](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-enable.md)|この保留中のブレークポイントの有効化状態を切り替えます。|
|[SetCondition](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-setcondition.md)|この保留中のブレークポイントに関連付けられている条件を設定または変更します。|
|[SetPassCount](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-setpasscount.md)|この保留中のブレークポイントに関連付けられているパスカウントを設定または変更します。|
|[EnumBoundBreakpoints](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-enumboundbreakpoints.md)|この保留中のブレークポイントからバインドされたすべてのブレークポイントを列挙します。|
|[EnumErrorBreakpoints](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-enumerrorbreakpoints.md)|この保留中のブレークポイントが原因で発生したすべてのエラーブレークポイントを列挙します。|
|[削除](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-delete.md)|この保留中のブレークポイントと、それにバインドされているすべてのブレークポイントを削除します。|

## <a name="remarks"></a>解説
 `IDebugPendingBreakpoint2` は、ブレークポイントを1つまたは複数のプログラムに適用できるコードにバインドするために必要なすべての情報のプロバイダーと考えることができます。

 保留中のブレークポイントによって、複数のバインドされたブレークポイントが生成される可能性があります。 たとえば、C++ スタイルのテンプレート内のブレークポイントによって、そのテンプレートの一意のインスタンスごとにバインドされたブレークポイントが生成される場合があります。

## <a name="requirements"></a>必要条件
 ヘッダー: msdbg. h

 名前空間: VisualStudio。

 アセンブリ: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>関連項目
- [CreatePendingBreakpoint](../../../extensibility/debugger/reference/idebugengine2-creatependingbreakpoint.md)
- [GetPendingBreakpoint](../../../extensibility/debugger/reference/idebugbreakpointboundevent2-getpendingbreakpoint.md)
- [GetPendingBreakpoint](../../../extensibility/debugger/reference/idebugboundbreakpoint2-getpendingbreakpoint.md)
- [GetPendingBreakpoint](../../../extensibility/debugger/reference/idebugerrorbreakpoint2-getpendingbreakpoint.md)
