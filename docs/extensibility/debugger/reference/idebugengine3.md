---
title: IDebugEngine3 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugEngine3
helpviewer_keywords:
- IDebugEngine3 interface
ms.assetid: 8bdf4bb7-3b5d-4991-8981-772d4f6bb656
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 7026156eac7f60e7435e32244c3cc03ae5f08e1e
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/02/2020
ms.locfileid: "80730655"
---
# <a name="idebugengine3"></a>IDebugEngine3
1つ以上のモジュールのデバッグを制御する1つのデバッグエンジン (DE) を表します。

## <a name="syntax"></a>構文

```
IDebugEngine3 : IDebugEngine2
```

## <a name="notes-for-implementers"></a>実装側の注意
 このインターフェイスは、カスタム DE (シンボルがサポートされている場合) によって実装され、ジャスト Mycode 状態を有効にします。 シンボルがシンボルとジャスト Mycode をサポートしている場合、このインターフェイスは DE によって実装される必要があります。

## <a name="notes-for-callers"></a>呼び出し元に関する注意事項
 このインターフェイスは、シンボルを読み込む場所のユーザーオプションを渡すために、セッションデバッグマネージャー (SDM) によって呼び出されます。 このメソッドは、インスタンス化されるときにエンジンの GUID を設定するためにも呼び出されます (この GUID は、エンジン登録時のメトリックに基づいています)。 また、SDM は、このインターフェイスを呼び出してジャスト Mycode の状態を設定し、デバッガーによって認識されるすべての例外を指定された状態に設定します。

## <a name="methods-in-vtable-order"></a>Vtable 順序のメソッド
 インターフェイスは、 [IDebugEngine2](../../../extensibility/debugger/reference/idebugengine2.md)から継承されたメソッドに加えて、 `IDebugEngine3` 次のメソッドを公開します。

|Method|説明|
|------------|-----------------|
|[SetSymbolPath](../../../extensibility/debugger/reference/idebugengine3-setsymbolpath.md)|デバッグシンボルの検索に DE が使用するパスまたはパスを設定します。|
|[LoadSymbols](../../../extensibility/debugger/reference/idebugengine3-loadsymbols.md)|シンボルが読み込まれていないすべてのモジュールのシンボルを読み込みます。|
|[SetJustMyCodeState](../../../extensibility/debugger/reference/idebugengine3-setjustmycodestate.md)|ジャストの非 Mycode 情報についての説明を解除します。|
|[SetEngineGuid](../../../extensibility/debugger/reference/idebugengine3-setengineguid.md)|メトリックから DE の GUID を設定します。|
|[SetAllExceptions](../../../extensibility/debugger/reference/idebugengine3-setallexceptions.md)|現在未解決のすべての例外を指定された状態に設定します。|

## <a name="requirements"></a>必要条件
 ヘッダー: msdbg. h

 名前空間: VisualStudio。

 アセンブリ: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>関連項目
- [IDebugEngine2](../../../extensibility/debugger/reference/idebugengine2.md)
