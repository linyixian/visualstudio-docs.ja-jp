---
title: '[ページ ファイル] タブ ([プロセス プロパティ] ダイアログ ボックス) | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- Process properties for Windows NT
ms.assetid: daf41a06-8a55-48f6-95f5-49a8416bd308
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 25dc3b0aca1b58c18ae4038540c14fc4dbfe4036
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62904108"
---
# <a name="page-file-tab-process-properties-dialog-box"></a>[ページ ファイル] タブ ([プロセス プロパティ] ダイアログ ボックス)
**[ページ ファイル]** タブを使用し、プロセスのページング ファイルを調べます。 [[プロセス プロパティ]](../debugger/process-properties-dialog-box.md) ダイアログ ボックスを表示するには、[[プロセス ビュー]](../debugger/processes-view.md) ウィンドウにフォーカスを移動します。 ツリーで任意のプロセス ノードを選択し、 **[ビュー]** メニューから **[プロパティ]** を選択します。

 **[ページ ファイル]** タブでは、次の設定を使用できます。

|入力|説明|
|-----------|-----------------|
|**ページ ファイル サイズ**|ページング ファイルでこのプロセスが使用しているページの現行数。 ページング ファイルには、プロセスによって使用されているデータのページが格納されますが、他のファイルに含まれているデータのページは格納されません。 ページング ファイルはすべてのプロセスで使用されます。ページング ファイルに領域がないと、他のプロセスの実行中、エラーが発生することがあります。|
|**ピーク ページ ファイルのサイズ**|ページング ファイルでこのプロセスが使用しているページの最大数。|
|**ページ フォールト**|このプロセスで実行されているスレッド別のページ フォールト数。 ページ フォールトは、スレッドが参照する仮想メモリのページがメイン メモリのワーキング セットにないときに発生します。 したがって、ページがスタンバイ リストにある場合、そのために、既にメイン メモリ内にある場合、またはページを共有している別のプロセスによってページが使用されている場合は、そのページがディスクから取得されません。|