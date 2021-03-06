---
title: デバッガーコンテキスト |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- debugging [Debugging SDK], contexts
ms.assetid: 79808036-b680-4e4c-9c61-4ed43aa11323
caps.latest.revision: 10
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 771a3cd8ae25173f3033b3a3229e516570f5dedc
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/02/2020
ms.locfileid: "68200629"
---
# <a name="debugger-contexts"></a>デバッガー コンテキスト
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

デバッグでは、 [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] デバッグエンジン (DE) は、次のように複数の異なるコンテキスト内で同時に動作します。  
  
- プログラムの実行ストリーム内の現在の位置を記述するコードコンテキスト。  
  
- ドキュメントコンテキストまたは位置。ソースドキュメント内の現在位置を記述します。  
  
- 式の評価コンテキスト。式の評価が行われるコンテキストを記述します。  
  
## <a name="in-this-section"></a>このセクションの内容  
 [コード コンテキスト](../../extensibility/debugger/code-context.md)  
 コードコンテキストについては、今日の実行時アーキテクチャにおけるプログラムの命令ストリームのアドレスとして、また、コードが命令によって表されない場合がありますが、他の方法では nontraditional 言語について説明します。  
  
 [ドキュメントの位置](../../extensibility/debugger/document-position.md)  
 IDE で認識されているソースファイル内の位置を抽象化することによって、Visual Studio のデバッグでのドキュメントの位置を定義します。  
  
 [ドキュメントのコンテキスト](../../extensibility/debugger/document-context.md)  
 ソースファイルに関連して Visual Studio のデバッグで表現されるドキュメントコンテキストについて説明します。 また、シンボルハンドラーがコードコンテキストをドキュメントコンテキストにマップする方法についても説明します。  
  
 [式の評価のコンテキスト](../../extensibility/debugger/expression-evaluation-context.md)  
 Visual Studio の式の評価コンテキストに関する情報を提供します。 たとえば、スタックフレームに関連付けられている式の評価コンテキストでは、ローカル変数、メソッドパラメーター、およびクラスメンバーを評価するためのコンテキストが提供されます。  
  
## <a name="related-sections"></a>関連項目  
 [デバッグの概念](../../extensibility/debugger/debugger-concepts.md)  
 デバッグアーキテクチャの主要概念について説明します。  
  
 [デバッグ (コンポーネントを)](../../extensibility/debugger/debugger-components.md)  
 デバッグエンジン (DE)、式エバリュエーター (EE)、およびシンボルハンドラー (SH) など、Visual Studio のデバッグコンポーネントの概要について説明します。  
  
 [タスクのデバッグ](../../extensibility/debugger/debugging-tasks.md)  
 プログラムの起動や式の評価など、さまざまなデバッグタスクへのリンクが含まれています。
