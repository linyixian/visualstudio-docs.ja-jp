---
title: '方法: [ウィンドウ検索] からメッセージ ビューを開く | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- Messages View in Spy++, opening
- opening Messages View in Spy++
ms.assetid: 601a193e-432a-417b-9406-6fec9e401264
caps.latest.revision: 7
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: ee29135e659eff7e4965b6b1fb0d24de2c2e90cc
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/02/2020
ms.locfileid: "68157887"
---
# <a name="how-to-open-messages-view-from-find-window"></a>方法: [ウィンドウ検索] からメッセージ ビューを開く
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

**[ウィンドウ検索]** ダイアログ ボックスを使用してターゲット ウィンドウを選択し、そのウィンドウのメッセージ ビューを開くと便利な場合があります。  
  
### <a name="to-open-a-messages-view-window-using-the-find-window-dialog-box"></a>[ウィンドウ検索] ダイアログ ボックスを使用して [メッセージ ビュー] ウィンドウを開く  
  
1. Spy++ とターゲット ウィンドウが表示されるように、ご利用のウィンドウを配置します。  
  
2. **[Spy]** メニューから **[ウィンドウ検索]** を選択します。  
  
     [[ウィンドウ検索] ダイアログ ボックス](../debugger/find-window-dialog-box.md)が開きます。  
  
3. **[ウィンドウ]** タブで、 **[ファインダー ツール]** をターゲット ウィンドウにドラッグします。 そのツールをドラッグすると、 **[ウィンドウ検索]** ダイアログ ボックスに選択したウィンドウの詳細が表示されます。  
  
     または  
  
     確認するウィンドウのハンドル (たとえば、デバッガーからコピーしたもの) がある場合は、それを **[ハンドル]** テキスト ボックスに入力します。  
  
4. **[表示]** で、 **[メッセージ]** を選択します。  
  
5. **[OK]** をクリックします。  
  
     空白の [[メッセージ ビュー]](../debugger/messages-view.md) ウィンドウが開き、 **[メッセージ]** メニューが Spy++ ツールバーに追加されます。  
  
6. **[メッセージ]** メニューから **[ログ オプション]** を選択します。  
  
     [[メッセージ オプション] ダイアログ ボックス](../debugger/message-options-dialog-box.md)が開きます。  
  
7. 表示するメッセージのオプションを選択します。  
  
8. **[OK]** を押して、メッセージのログ記録を開始します。  
  
     選択したオプションに応じて、メッセージはアクティブな [メッセージ ビュー] ウィンドウへのストリーミングを開始します。  
  
9. 十分な数のメッセージが表示されたら、 **[メッセージ]** メニューから **[ログ記録の停止]** を選択します。
