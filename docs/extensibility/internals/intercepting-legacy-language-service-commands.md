---
title: レガシ言語サービスコマンドのインターセプト |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- commands, intercepting language service
- language services, intercepting commands
ms.assetid: eea69f03-349c-44bb-bd4f-4925c0dc3e55
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 5206bced8b4bfae32498434765e5c3f61801b386
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/02/2020
ms.locfileid: "80707452"
---
# <a name="intercepting-legacy-language-service-commands"></a>従来の言語サービスのコマンドの受信
では [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 、テキストビューで処理されるような言語サービスをインターセプトすることができます。 これは、テキストビューでは管理されない言語固有の動作に便利です。 これらのコマンドを受け取るには、言語サービスからテキストビューに1つ以上のコマンドフィルターを追加します。

## <a name="getting-and-routing-the-command"></a>コマンドの取得とルーティング
 コマンドフィルターは、 <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> 特定の文字シーケンスまたはキーコマンドを監視するオブジェクトです。 複数のコマンドフィルターを1つのテキストビューに関連付けることができます。 各テキストビューでは、コマンドフィルターのチェーンが保持されます。 新しいコマンドフィルターを作成したら、適切なテキストビューのチェーンにフィルターを追加します。

 でメソッドを呼び出して、 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView.AddCommandFilter%2A> <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView> コマンドフィルターをチェーンに追加します。 を呼び出すと <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView.AddCommandFilter%2A> 、 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] コマンドフィルターで処理されないコマンドを渡すことができる別のコマンドフィルターが返されます。

 コマンド処理には、次のオプションがあります。

- コマンドを処理し、チェーン内の次のコマンドフィルターにコマンドを渡します。

- コマンドを処理し、次のコマンドフィルターにコマンドを渡しません。

- コマンドを処理するのではなく、コマンドを次のコマンドフィルターに渡します。

- コマンドを無視します。 現在のフィルターでは処理せず、次のフィルターに渡すことはできません。

  言語サービスで処理する必要があるコマンドの詳細については、「 [言語サービスフィルターの重要なコマンド](../../extensibility/internals/important-commands-for-language-service-filters.md)」を参照してください。
