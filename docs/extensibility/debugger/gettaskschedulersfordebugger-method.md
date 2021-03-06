---
title: GetTaskSchedulersForDebugger メソッド |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- GetTaskSchedulersForDebugger method, TaskScheduler class [.NET Framework debug engines]
ms.assetid: 58aa236a-5ab8-4695-b303-89dffdbcd946
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: a3b0c8c16b10a4cf2268161d8a2db96c10303b1c
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/02/2020
ms.locfileid: "80738648"
---
# <a name="gettaskschedulersfordebugger-method"></a>GetTaskSchedulersForDebugger メソッド
現在アクティブなすべてのオブジェクトの配列を取得 <xref:System.Threading.Tasks.TaskScheduler> します。

 **名前空間:** <xref:System.Threading.Tasks?displayProperty=fullName>

 **アセンブリ:** mscorlib ( *mscorlib.dll*)

 .NET Framework からこの内部メンバーにアクセスできないため、次の構文は、共通中間言語 (CIL) で提供されています。

## <a name="syntax"></a>構文

```csharp
.method assembly hidebysig static class System.Threading.Tasks.TaskScheduler[] GetTaskSchedulersForDebugger() cil managed
```

## <a name="return-value"></a>戻り値
 <xref:System.Threading.Tasks.TaskScheduler>こので現在アクティブなすべてのオブジェクトの配列 <xref:System.AppDomain> 。

## <a name="remarks"></a>解説
 このメソッドはスレッドセーフではなく、の他のインスタンスと同時に使用することはできません <xref:System.Threading.Tasks.TaskScheduler> 。 デバッガーが他のすべてのスレッドを中断した場合にのみ、このメソッドをデバッガーから呼び出します。

## <a name="see-also"></a>関連項目
- [TaskScheduler クラス](../../extensibility/debugger/taskscheduler-class-internal-members.md)
