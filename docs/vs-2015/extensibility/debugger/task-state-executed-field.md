---
title: TASK_STATE_EXECUTED Field |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- TASK_STATE_EXECUTED field, Task class [.NET Framework debug engines]
ms.assetid: 75b8f9d0-b908-40d0-b109-70feaed2ab0c
caps.latest.revision: 9
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 6dcfb6c7b4b79d1abd2b393e32b9795f613c205a
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/02/2020
ms.locfileid: "68162221"
---
# <a name="task_state_executed-field"></a>TASK_STATE_EXECUTED フィールド
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

タスクは実行中で、まだ完了していません。  
  
 **名前空間:** <xref:System.Threading.Tasks?displayProperty=fullName>  
  
 **アセンブリ:** mscorlib (mscorlib.dll)  
  
 .NET Framework からこの内部メンバーにアクセスすることはできないため、次の構文は、共通中間言語 (CIL) で提供されています。  
  
## <a name="syntax"></a>構文  
  
```  
.field static assembly literal int32 TASK_STATE_EXECUTED = int32(0x00020000)  
```  
  
## <a name="remarks"></a>解説  
 [M_stateFlags](../../extensibility/debugger/m-stateflags-field.md)フィールドにこの値が含まれている場合、 <xref:System.Threading.Tasks.Task.Status%2A> プロパティはを返し <xref:System.Threading.Tasks.TaskStatus?displayProperty=fullName> ます。  
  
## <a name="see-also"></a>参照  
 [Task クラス](../../extensibility/debugger/task-class-internal-members.md)
