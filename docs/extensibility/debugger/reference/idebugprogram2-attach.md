---
title: 'IDebugProgram2:: Attach |Microsoft Docs'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugProgram2::Attach
helpviewer_keywords:
- IDebugProgram2::Attach
ms.assetid: de069fbf-a565-4905-b102-f5658c55aacd
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 7d0b182ba7a873816e3a7aa32d39beb2c63cc5ce
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/02/2020
ms.locfileid: "80723137"
---
# <a name="idebugprogram2attach"></a>IDebugProgram2::Attach
プログラムにアタッチします。

## <a name="syntax"></a>構文

```cpp
HRESULT Attach( 
   IDebugEventCallback2* pCallback
);
```

```csharp
int Attach( 
   IDebugEventCallback2 pCallback
);
```

## <a name="parameters"></a>パラメーター
`pCallback`\
からデバッグイベント通知に使用される [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md) オブジェクト。

## <a name="return-value"></a>戻り値
 成功した場合はを返し `S_OK` ます。それ以外の場合はエラーコードを返します。 次の表に、考えられるエラーコードを示します。

|値|[説明]|
|-----------|-----------------|
|`E_ATTACH_DEBUGGER_ALREADY_ATTACHED`|指定されたプログラムは既にデバッガーにアタッチされています。|
|`E_ATTACH_DEBUGGEE_PROCESS_SECURITY_VIOLATION`|Attach プロシージャの実行中にセキュリティ違反が発生しました。|
|`E_ATTACH_CANNOT_ATTACH_TO_DESKTOP`|デスクトッププログラムをデバッガーにアタッチできません。|

## <a name="remarks"></a>解説
 デバッグエンジン (DE) は、プログラムにアタッチするためにこのメソッドを呼び出すことはありません。 DE がプログラムのアドレス空間で実行されている場合は、 [Onattach](../../../extensibility/debugger/reference/idebugprogramnodeattach2-onattach.md) メソッドが呼び出されます。 セッションデバッグマネージャーの (SDM) アドレス空間で DE を実行すると、 [Attach](../../../extensibility/debugger/reference/idebugengine2-attach.md) メソッドが呼び出されます。

## <a name="see-also"></a>関連項目
- [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)
- [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md)
- [OnAttach](../../../extensibility/debugger/reference/idebugprogramnodeattach2-onattach.md)
- [[アタッチ]](../../../extensibility/debugger/reference/idebugengine2-attach.md)
