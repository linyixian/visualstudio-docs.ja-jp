---
title: SetCurrentThread コマンド
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- debug.setcurrentthread
helpviewer_keywords:
- Set Current Thread command
- Debug.SetCurrentThread command
ms.assetid: 9917ed1d-6c30-4d94-b2f0-69acce74f1b2
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 54c2dabeea14293fdb86120f822eb396a028757a
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/02/2020
ms.locfileid: "85768682"
---
# <a name="set-current-thread-command"></a>SetCurrentThread コマンド
指定したスレッドを現在のスレッドとして設定します。

## <a name="syntax"></a>構文

```
Debug.SetCurrentThread index
```

## <a name="arguments"></a>引数
`index`

必須。 スレッドをそのインデックスで選択します。

## <a name="example"></a>例

```
>Debug.SetCurrentThread 1
```

## <a name="see-also"></a>参照

- [Visual Studio のコマンド](../../ide/reference/visual-studio-commands.md)
- [[コマンド] ウィンドウ](../../ide/reference/command-window.md)
- [検索コマンド ボックス](../../ide/find-command-box.md)
- [Visual Studio コマンドのエイリアス](../../ide/reference/visual-studio-command-aliases.md)