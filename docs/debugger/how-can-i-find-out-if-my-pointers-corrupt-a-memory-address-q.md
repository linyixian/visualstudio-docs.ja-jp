---
title: ポインターがメモリ アドレスを破壊しているかどうか調べる | Microsoft Docs
ms.custom: seodec18
ms.date: 11/04/2016
ms.topic: how-to
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- addresses, pointers corrupting memory address
- memory, corruption
- pointers, corrupting memory addresses
- memory address corruption by pointers
- debugging [C++], memory corruption
- corrupted memory address
ms.assetid: a147c939-4fb1-415c-8410-cf303781e9e8
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 075569815d55ea30f688c5ce86c56990fca03cd1
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/02/2020
ms.locfileid: "85350356"
---
# <a name="how-can-i-find-out-if-my-pointers-corrupt-a-memory-address"></a>ポインターがメモリ アドレスを破壊しているかどうか見つけるには
## <a name="problem-description"></a>問題の説明
 ポインターの 1 つがアドレス 0x00408000 のメモリを破壊してしまったようです。 どうなっているのか調べる方法はありますか。

## <a name="solution"></a>ソリューション

#### <a name="check-for-heap-corruption"></a>ヒープ破損のチェック

- メモリの破損は、その多くがヒープの破損に起因します。 グローバル フラグ ユーティリティ (gflags.exe) または pageheap.exe を使用してください。 [/windows-hardware/drivers/debugger/gflags-and-pageheap](/windows-hardware/drivers/debugger/gflags-and-pageheap) を参照してください。

#### <a name="to-find-where-the-memory-address-is-modified"></a>メモリ アドレスの変更箇所を見つけるには

1. 0x00408000 にデータ ブレークポイントを設定します。 「[データ変更ブレークポイントを設定する (ネイティブ C++ のみ)](../debugger/using-breakpoints.md#BKMK_set_a_data_breakpoint_native_cplusplus)」を参照してください。

2. ブレークポイントにヒットしたら、 **[メモリ]** ウィンドウを使用して、0x00408000 から始まるメモリの内容を表示します。 詳細については、[メモリ ウィンドウ](../debugger/memory-windows.md)に関する記事をご覧ください。

## <a name="see-also"></a>関連項目
- [ネイティブ コードのデバッグに関する FAQ](../debugger/debugging-native-code-faqs.md)
- [ネイティブ コードのデバッグ](../debugger/debugging-native-code.md)
