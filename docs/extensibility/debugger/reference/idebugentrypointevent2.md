---
title: IDebugEntryPointEvent2 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugEntryPointEvent2
helpviewer_keywords:
- IDebugEntryPointEvent2 interface
ms.assetid: a15d1cc3-97b7-438c-8d24-c23149708f42
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 531ff846f2488193ed7f3d9f200a1a4ea04df6f9
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/02/2020
ms.locfileid: "80730333"
---
# <a name="idebugentrypointevent2"></a>IDebugEntryPointEvent2
デバッグエンジン (DE) は、プログラムがユーザーコードの最初の命令を実行しようとしているときに、このインターフェイスをセッションデバッグマネージャー (SDM) に送信します。

## <a name="syntax"></a>構文

```
IDebugEntryPointEvent2 : IUnknown
```

## <a name="notes-for-implementers"></a>実装側の注意
 DE は、通常の操作の一部としてこのインターフェイスを実装します。 [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md)インターフェイスは、このインターフェイスと同じオブジェクトに実装する必要があります。 SDM は、 [QueryInterface](/cpp/atl/queryinterface) を使用してインターフェイスにアクセスし `IDebugEvent2` ます。

## <a name="notes-for-callers"></a>呼び出し元に関する注意事項
 DE は、デバッグ中のプログラムが読み込まれ、ユーザーコードの最初の命令を実行する準備が整ったときに、このイベントオブジェクトを作成して送信します。 イベントは、デバッグ対象のプログラムにアタッチされたときに SDM によって提供される [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md) callback 関数を使用して送信されます。

## <a name="remarks"></a>解説
- [IDebugLoadCompleteEvent2](../../../extensibility/debugger/reference/idebugloadcompleteevent2.md) は、プログラムが最初の命令を実行しようとしているときに送信されます。 たとえば、 `IDebugEntryPoint2` は、プログラムがユーザーの関数を実行しようとしているときに送信され `main` ます。

 DE が送信されるとき `IDebugEntryPointEvent2` 、現在のコードの位置は、のようなユーザーコードの最初の命令である必要があり `main` ます。

## <a name="requirements"></a>必要条件
 ヘッダー: msdbg. h

 名前空間: VisualStudio。

 アセンブリ: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>関連項目
- [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md)
- [IDebugLoadCompleteEvent2](../../../extensibility/debugger/reference/idebugloadcompleteevent2.md)
