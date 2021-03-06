---
title: 実行の制御 |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- debugging [Debugging SDK], control of execution
ms.assetid: 97071846-007e-450f-95a6-f072d0f5e61e
caps.latest.revision: 10
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: c885c0c983e6fafd69d55b3d68f8ed6e8ff2628c
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/02/2020
ms.locfileid: "86387266"
---
# <a name="control-of-execution"></a>実行の制御
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

デバッグエンジン (DE) は、通常、次のいずれかのイベントを最後のスタートアップイベントとして送信します。  
  
- エントリポイントイベント (新しく起動したプログラムにアタッチする場合)  
  
- 既に実行されているプログラムにアタッチする場合は、読み込み完了イベント  
  
  これらのイベントはいずれも、イベントを停止しています。つまり、IDE を使用してユーザーからの応答を除外することを意味します。 詳細については、「 [操作モード](../../extensibility/debugger/operational-modes.md)」を参照してください。  
  
## <a name="stopping-event"></a>イベントの停止  
 停止イベントがデバッグセッションに送信されると、次のようになります。  
  
1. 現在の命令ポインターを含むプログラムとスレッドは、イベントインターフェイスから取得できます。  
  
2. IDE では、現在のソースコードファイルと位置が決定され、エディターで強調表示されます。  
  
3. 通常、デバッグセッションでは、プログラムの **Continue** メソッドを呼び出すことによって、この最初の停止イベントに応答します。  
  
4. 次にプログラムは、ブレークポイントにヒットするなどの停止状態が発生するまで実行されます。この場合、DE はデバッグセッションにブレークポイントイベントを送信します。 ブレークポイントイベントは停止イベントで、もう一度ユーザーの応答を待機します。  
  
5. 関数のステップイン、ステップオーバー、またはその一部を実行することをユーザーが指定した場合、IDE は、デバッグセッションに対してプログラムのメソッドを呼び出し `Step` 、ステップの単位 (命令、ステートメント、または行) とステップの種類 (つまり、関数をステップイン、ステップオーバー、または除外するかどうか) を指定します。 ステップが完了すると、DE はデバッグセッションにステップ完了イベントを送信します。これは停止イベントです。  
  
    - または -  
  
    ユーザーが現在の命令ポインターからの実行を続行することにした場合、IDE はプログラムの **Execute** メソッドを呼び出すようにデバッグセッションに要求します。 プログラムは、次の停止条件に到達するまで実行を再開します。  
  
    - または -  
  
    デバッグセッションが特定の停止イベントを無視するようになっている場合、デバッグセッションはプログラムの **Continue** メソッドを呼び出します。 プログラムが停止条件を検出したときに関数のステップイン、ステップオーバー、またはログアウトを行っていた場合は、手順を続行します。  
  
   プログラムによって、DE が停止条件を検出すると、そのような停止イベントを [IDebugLoadCompleteEvent2](../../extensibility/debugger/reference/idebugloadcompleteevent2.md) または [IDebugEntryPointEvent2](../../extensibility/debugger/reference/idebugentrypointevent2.md) として、 [IDebugEventCallback2](../../extensibility/debugger/reference/idebugeventcallback2.md) インターフェイスを介してセッションデバッグマネージャー (SDM) に送信します。 DE は、プログラムと現在の命令ポインターを含むスレッドを表す [IDebugProgram2](../../extensibility/debugger/reference/idebugprogram2.md) インターフェイスと [IDebugThread2](../../extensibility/debugger/reference/idebugthread2.md) インターフェイスを渡します。 SDM は [IDebugThread2:: enumframe info](../../extensibility/debugger/reference/idebugthread2-enumframeinfo.md) を呼び出して、一番上のスタックフレームを取得し、 [IDebugStackFrame2:: getdocumentcontext](../../extensibility/debugger/reference/idebugstackframe2-getdocumentcontext.md) を呼び出して、現在の命令ポインターに関連付けられているドキュメントコンテキストを取得します。 このドキュメントコンテキストは、通常、ソースコードファイルの名前、行、および列番号です。 IDE はこれらを使用して、現在の命令ポインターを含むソースコードを強調表示します。  
  
   通常、SDM は、 [IDebugProgram2:: Continue](../../extensibility/debugger/reference/idebugprogram2-continue.md)を呼び出すことによって、この最初の停止イベントに応答します。 次にプログラムは、ブレークポイントにヒットするなどの停止状態が発生するまで実行されます。この場合、DE は [IDebugBreakpointEvent2 インターフェイス](../../extensibility/debugger/reference/idebugbreakpointevent2.md) を SDM に送信します。 ブレークポイントイベントは停止イベントで、もう一度ユーザーの応答を待機します。  
  
   関数のステップイン、ステップオーバー、またはその一部を実行することをユーザーが指定した場合、IDE は、 [IDebugProgram2:: step](../../extensibility/debugger/reference/idebugprogram2-step.md)を呼び出すように SDM に指示します。これには、 [stepunit](../../extensibility/debugger/reference/stepunit.md) (命令、ステートメント、または行) と [stepunit](../../extensibility/debugger/reference/stepkind.md)(関数のステップイン、ステップオーバー、またはアウト) を渡します。 ステップが完了すると、DE は [IDebugStepCompleteEvent2](../../extensibility/debugger/reference/idebugstepcompleteevent2.md) インターフェイスを SDM に送信します。これは停止イベントです。  
  
   ユーザーが現在の命令ポインターからの実行を続行することにした場合、IDE は [IDebugProgram2:: Execute](../../extensibility/debugger/reference/idebugprogram2-execute.md)を呼び出すように SDM に要求します。 プログラムは、次の停止条件に到達するまで実行を再開します。  
  
   デバッグパッケージが特定の停止イベントを無視する場合、デバッグパッケージは SDM を呼び出します。これは [IDebugProgram2:: Continue](../../extensibility/debugger/reference/idebugprogram2-continue.md)を呼び出します。 プログラムが停止条件を検出したときに関数のステップイン、ステップオーバー、またはログアウトを行っていた場合は、手順を続行します。 これは、プログラムがステップ実行状態を維持し、続行する方法がわかっていることを意味します。  
  
   SDM による呼び出しが非同期に行われます `Step` 。これは、sdm が呼び出しを迅速に返すことを期待することを意味します。 **Execute** **Continue** DE が、実行前、または続行する前に、同じスレッド上で SDM を停止イベントを送信すると、 `Step` sdm は応答を停止します。 **Execute** **Continue**  
  
## <a name="see-also"></a>参照  
 [タスクのデバッグ](../../extensibility/debugger/debugging-tasks.md)
