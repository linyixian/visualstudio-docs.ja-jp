---
title: ワークフローデザイナー-ForEach &lt; T &gt; アクティビティデザイナー
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- System.Activities.Statements.ForEach`1.UI
ms.assetid: 67097b3a-fcf5-4a72-beb1-2c7784151a86
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 30d43351211a6ff857630b47f05be77e27bd7951
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/02/2020
ms.locfileid: "75593916"
---
# <a name="foreachlttgt-activity-designer"></a>ForEach &lt; T &gt; アクティビティデザイナー

<xref:System.Activities.Statements.ForEach%601> アクティビティは、指定した <xref:System.Activities.Statements.ForEach%601.Body%2A> コレクション内の各項目に対して、<xref:System.Activities.Statements.ForEach%601.Values%2A> に含まれるアクティビティを実行します。

## <a name="foreacht-properties-in-the-workflow-designer"></a>\>ワークフローデザイナー内の ForEach<T プロパティ

次の表に、最も役に立つ <xref:System.Activities.Statements.ForEach%601> アクティビティのプロパティと、デザイナーでのその使用方法を示します。

|プロパティ名|必須|使用|
|-|--------------|-|
|<xref:System.Activities.Activity.DisplayName%2A>|×|<xref:System.Activities.Statements.ForEach%601> アクティビティの表示名。 既定値は ForEach<Int32 \> です。 <xref:System.Activities.Activity.DisplayName%2A> 値は必須ではありませんが、使用することをお勧めします。|
|<xref:System.Activities.Statements.ForEach%601.Values%2A>|○|反復処理を行う項目のコレクション。 を設定するには、 <xref:System.Activities.Statements.ForEach%601.Values%2A> **ForEach<T \> **アクティビティデザイナーまたはプロパティグリッドの [**値**] ボックスに Visual Basic 式を入力します。|
|*TypeArgument*|○|<xref:System.Activities.Statements.ForEach%601.Values%2A>ジェネリックパラメーター *T*によって指定されたコレクション内の項目の型。既定では、 *Typeargument*は**Int32**に設定されています。 型を変更するには、プロパティグリッドの *Typeargument* コンボボックスの値を変更します。|

既定では、ループ反復子には **item**という名前が付けられます。 反復子変数の名前は、<xref:System.Activities.Statements.ForEach%601> アクティビティ デザイナーで変更できます。 ループ反復子は、<xref:System.Activities.Statements.ForEach%601> アクティビティの子の式で使用できます。

## <a name="see-also"></a>こちらもご覧ください

- [ParallelForEach\<T>](../workflow-designer/parallelforeach-t-activity-designer.md)
- [制御フロー](../workflow-designer/control-flow-activity-designers.md)
