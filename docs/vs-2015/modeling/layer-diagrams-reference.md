---
title: 'レイヤー図: Reference |Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-modeling
ms.topic: reference
f1_keywords:
- vs.teamarch.layerdiagram.layerexplorer.artifactlink
- vs.teamarch.layerdiagram.layerexplorer.artifactlink.properties
- vs.teamarch.layerdiagram.diagram
- vs.teamarch.UMLModelExplorer.layerdiagram
- vs.teamarch.layerdiagram.layerexplorer
- vs.teamarch.layerdiagram.shapes.properties
- vs.teamarch.layerdiagram.toolbox
helpviewer_keywords:
- architecture, layer diagrams
- layer diagrams
- diagrams - modeling, layer
- constraints, architectural
ms.assetid: f26c986c-1e79-420e-b29a-a283e6d8a71d
caps.latest.revision: 35
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 448a74b739bbb339d5f3b3e56c0ba59072994109
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/02/2020
ms.locfileid: "75850616"
---
# <a name="layer-diagrams-reference"></a>レイヤー図: リファレンス
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Visual Studio では、 *レイヤー図* を使用して、システムの高レベルな論理アーキテクチャを視覚化できます。 レイヤー図では、システム内の物理的な成果物が、 *レイヤー*と呼ばれる論理的な抽象的なグループに編成されます。 これらのレイヤーは成果物が実行する主要タスクまたはシステムの主要コンポーネントについて説明します。 各レイヤーには、より詳細なタスクを示す入れ子になったレイヤーを含めることもできます。

 この機能をサポートする Visual Studio のバージョンを確認するには、「 [Version support for architecture and modeling tools](../modeling/what-s-new-for-design-in-visual-studio.md#VersionSupport)」を参照してください。

 レイヤー間の必要とされる依存関係、または既存の依存関係を指定できます。 矢印で表されるこれらの依存関係は、どのレイヤーが、他のレイヤーが表す機能を使用できるか、または現在使用しているかを示します。 システムを個別のロールおよび機能を記述するレイヤーに分けて整理したレイヤー図を使用すると、コードを簡単に理解、再利用、および保守できるようになります。

 レイヤー図は、次のタスクを実行するために使用します。

- システムの既存の論理アーキテクチャまたは必要とされる論理アーキテクチャを伝達する。

- 既存のコードと必要とされるアーキテクチャの間の不整合を見つける。

- システムのリファクタリング、更新、または進化によって必要とされるアーキテクチャにもたらされる変更の影響を視覚化する。

- チェックイン操作とビルド操作による検証を追加することによって、必要とされるアーキテクチャをコードの開発中および保守中に補強する。

  このトピックでは、レイヤー図で使用できる要素について説明します。 レイヤー図を作成して描画する方法の詳細については、「 [レイヤー図: ガイドライン](../modeling/layer-diagrams-guidelines.md)」を参照してください。 レイヤーパターンの詳細については、 [パターン & プラクティス](https://apparch.codeplex.com/Wiki/View.aspx?title=Application Patterns&referringTitle=Home)に関するサイトを参照してください。

## <a name="reading-layer-diagrams"></a>レイヤー図の解説
 ![レイヤー図上の要素](../modeling/media/uml-layerrefreading.png "UML_LayerRefReading")

 レイヤー図で使用できる要素を次の表に示します。

|**図形**|**Element**|**説明**|
|---------------|-----------------|---------------------|
|1|**レイヤー**|システム内の物理的な成果物の論理グループ。 このような成果物には、名前空間、プロジェクト、クラス、メソッドなどがあります。<br /><br /> レイヤーにリンクされている成果物を表示するには、レイヤーのショートカットメニューを開き、[ **リンクの表示** ] をクリックして **レイヤーエクスプローラー**を開きます。<br /><br /> 詳細については、「 [レイヤーエクスプローラー](#Explorer)」を参照してください。<br /><br /> -   禁止されている**名前空間の依存関係**-このレイヤーに関連付けられている成果物が、指定した名前空間に依存しないように指定<br />-   禁止された**名前空間**-このレイヤーに関連付けられている成果物が、指定した名前空間に属していないことを指定します。<br />-   **必須の名前空間** -このレイヤーに関連付けられた成果物が、指定した名前空間のいずれかに属している必要があることを指定します。|
|2|**依存関係**|あるレイヤーが別のレイヤーの機能を使用することはできても、その逆はできないことを示します。<br /><br /> -   **Direction** -依存関係の方向を指定します。|
|3|**双方向の依存関係**|あるレイヤーが別のレイヤーの機能を使用でき、その逆もできることを示します。<br /><br /> -   **Direction** -依存関係の方向を指定します。|
|4|**解説**|全般的なノートを図または図の要素に追加するために使用します。|
|5|**コメント リンク**|コメントを図の要素にリンクするために使用します。|

## <a name="layer-explorer"></a><a name="Explorer"></a> レイヤーエクスプローラー
 各レイヤーをソリューション内の成果物 (たとえば、プロジェクト、クラス、名前空間、プロジェクト ファイル、またはソフトウェアのその他のパート) にリンクすることができます。 レイヤーの数字は、レイヤーにリンクされている成果物の数を示します。 ただし、レイヤーの成果物の数を読み取るときには、次の点に注意してください。

- 1 つのレイヤーが他の成果物を含む 1 つの成果物にリンクされているが、他の成果物に直接リンクされていない場合、その数字にはリンクされた成果物のみが含まれます。 ただし、レイヤー検証時の分析にはそれらの他の成果物も含まれます。

   たとえば、1 つのレイヤーが 1 つの名前空間にリンクされている場合、その名前空間に複数のクラスが含まれていても、リンクされた成果物の数は 1 です。 レイヤーに名前空間の各クラスへのリンクもある場合、その数字にはリンクされたクラスが含まれます。

- 1 つのレイヤーに成果物にリンクされた他のレイヤーが含まれている場合は、そのコンテナー レイヤーの数字にそれらの成果物が含まれていなくても、コンテナー レイヤーはそれらの成果物にリンクされます。

  レイヤーと成果物のリンクの詳細については、次のドキュメントを参照してください。

- [レイヤー図: ガイドライン](../modeling/layer-diagrams-guidelines.md)

- [コードからのレイヤー図の作成](../modeling/create-layer-diagrams-from-your-code.md)

#### <a name="to-examine-the-linked-artifacts"></a>リンクされた成果物を確認するには

- レイヤー図で、1つまたは複数のレイヤーのショートカットメニューを開き、[ **リンクの表示**] を選択します。

     **レイヤーエクスプローラー** が開き、選択したレイヤーにリンクされている成果物が表示されます。 **レイヤーエクスプローラー** には、成果物のリンクの各プロパティを示す列があります。

    > [!NOTE]
    > これらのプロパティのすべてが表示されない場合は、[ **レイヤーエクスプローラー** ] ウィンドウを展開します。

    |**レイヤー エクスプローラーの列**|**説明**|
    |----------------------------------|---------------------|
    |**Categories (カテゴリ)**|クラス、名前空間、ソース ファイルなどの成果物の種類|
    |**レイヤー**|成果物にリンクしているレイヤー|
    |**検証をサポート**|**True**の場合、レイヤー検証プロセスは、プロジェクトがこの要素との依存関係に準拠しているかどうかを検証できます。<br /><br /> **False**の場合、リンクはレイヤー検証プロセスに参加しません。<br /><br /> 詳細については、「 [レイヤー図: ガイドライン](../modeling/layer-diagrams-guidelines.md)」を参照してください。|
    |**識別子**|リンクされた成果物への参照|

## <a name="see-also"></a>参照
 [アプリのモデルを生成する](../modeling/create-models-for-your-app.md)
