---
title: 'DA0006: 値の型で Equals() をオーバーライドしてください | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
f1_keywords:
- vs.performance.rules.DAOverrideEquals
- vs.performance.6
- vs.performance.DA0006
- vs.performance.rules.DA0006
ms.assetid: 4d85bdd6-b571-47e0-afd6-ba3764e4eed5
caps.latest.revision: 17
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: eaba2f099f2a4d04574acd5bcdd2ba8f8f44b4ce
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/02/2020
ms.locfileid: "75852361"
---
# <a name="da0006-override-equals-for-value-types"></a>DA0006:値の型で Equals() をオーバーライドしてください
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

ルール Id |DA0006 |  
|Category |。NET Framework Usage |  
|プロファイルメソッド |サンプリング |  
|Message |値型で Equals および等値演算子をオーバーライドします |。  
|メッセージ type |警告 |  
  
## <a name="cause"></a>原因  
 パブリック値型の Equals メソッドまたは等値演算子の呼び出しが、プロファイリング データの大きな割合を占めています。 さらに効率的な方法を実装することを検討してください。  
  
## <a name="rule-description"></a>ルールの説明  
 値型の場合、Equals を継承した実装が <xref:System.Reflection> ライブラリを使用して、この種類のすべてのフィールドの内容を比較します。 Reflection は計算コストが高いため、場合によってはすべてのフィールドで等値性を比較する必要はありません。 ユーザーがインスタンスの比較または並べ替えを行うことや、ハッシュ テーブル キーとしてインスタンスを使用することが予想される場合には、値型に Equals を実装する必要があります。 お使いのプログラミング言語が演算子のオーバーロードに対応している場合、等値演算子と非等値演算子も実装してください。  
  
 Equals と等値演算子をオーバーライドする方法については、[Equals および等値演算子 (==) 実装のガイドライン](https://msdn.microsoft.com/library/7h9bszxx.aspx)を参照してください。  
  
## <a name="how-to-investigate-a-warning"></a>警告の調査方法  
 Equals と等値演算子の実装例については、コード分析ルールの「[CA1815:equals および operator equals を値型でオーバーライドします](../code-quality/ca1815-override-equals-and-operator-equals-on-value-types.md)」を参照してください。
