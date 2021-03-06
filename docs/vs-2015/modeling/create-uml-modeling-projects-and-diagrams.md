---
title: UML モデリングプロジェクトおよびダイアグラムを作成する |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-modeling
ms.topic: conceptual
f1_keywords:
- vs.teamarch.addnewdiagramdialog
- vs.teamarch.createnewmodelingprojectdialog
helpviewer_keywords:
- projects [Visual Studio ALM], modeling
- diagrams - modeling, modeling
- modeling diagrams
- projects, UML
- UML, deleting diagrams
- UML
- UML diagrams, adding
- UML, projects
- Visual Studio ALM, modeling projects
- modeling projects
- UML diagrams
- projects, modeling
ms.assetid: c178b04b-4fd2-4bed-97e3-d793dae8649c
caps.latest.revision: 50
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 52c55b2cfdf000d91a83071b53e8e9450187b720
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/02/2020
ms.locfileid: "75852026"
---
# <a name="create-uml-modeling-projects-and-diagrams"></a>UML モデリング プロジェクトおよびダイアグラムを作成する
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

UML モデルは、ソフトウェア システムを理解したり設計したりする上で、また、ソフトウェア システムについて話し合う際に役立ちます。 Visual Studio には、最もよく使用される 5 つの UML 図 (アクティビティ図、クラス図、コンポーネント図、シーケンス図、およびユース ケース図) のテンプレートが用意されています。 また、システムの構造の定義に役立つレイヤー図も作成できます。

 UML モデリング図とレイヤー図が存在することが可能なのは、モデリング プロジェクト内のみです。 各モデリング プロジェクトには、1 つの共有 UML モデルといくつかの UML 図が含まれています。 各図はモデルの部分ビューです。 UML モデルは、UML 図にあるすべての要素が含まれていて、UML モデル エクスプローラーを使用して表示することができます。 モデルと図との関係の詳細については、「 [UML モデルとダイアグラムの編集](../modeling/edit-uml-models-and-diagrams.md)」を参照してください。 バージョン管理されたプロジェクトのモデリングについては、「[バージョン管理下のモデルと図の管理](../modeling/manage-models-and-diagrams-under-version-control.md)」および「[モデリングソリューションの構造](../modeling/structure-your-modeling-solution.md)」を参照してください。

> [!NOTE]
> また、プログラム コードを視覚化するために使用される、.NET クラス図と呼ばれる別の種類の図もあります。 詳細については、「 [クラスと型の設計と表示](https://msdn.microsoft.com/library/ab7aty24.aspx)」を参照してください。

## <a name="create-a-diagram-in-a-modeling-project"></a><a name="CreatingModelingDiagrams"></a> モデリングプロジェクトでの図の作成
 この機能をサポートする Visual Studio のバージョンを確認するには、「 [Version support for architecture and modeling tools](../modeling/what-s-new-for-design-in-visual-studio.md#VersionSupport)」を参照してください。

#### <a name="to-create-a-diagram-and-add-it-to-a-project"></a>図を作成してプロジェクトに追加するには

1. [ **アーキテクチャ** ] メニューの [ **新しい UML またはレイヤー図**] をクリックします。

2. [ **新しいダイアグラムの追加** ] ダイアログボックスで、目的のモデリング図の種類をクリックします。

    ![[新しいダイアグラムの追加] ダイアログ](../modeling/media/uml-adddiagram.png "UML_AddDiagram")

3. 新しい図の名前を入力します。

4. [ **モデリングプロジェクトに追加** ] ボックスで、次のようにします。

   - ソリューション内に既に存在するモデリングプロジェクトを選択し、[ **OK]** をクリックします。

     \- または

   1. [ **新しいモデリングプロジェクトの作成**] を選択し、[ **OK**] をクリックします。

   2. [ **新しいモデリングプロジェクトの作成** ] ダイアログボックスで、新しいプロジェクトの名前と場所を入力し、[ **OK**] をクリックします。

        ![[新しいモデリング プロジェクトの作成] ダイアログ](../modeling/media/uml-createmodel.png "UML_CreateModel")

        ソリューションが開いている場合は、新しいプロジェクトがソリューションに追加されます。 開いているソリューションがない場合は、新しいソリューションの名前を入力できます。

   モデリング プロジェクトが既に存在する場合は、次の手順を使用することもできます。

#### <a name="to-add-a-diagram-to-an-existing-modeling-project"></a>既存のモデリング プロジェクトに図を追加するには

1. **ソリューションエクスプローラー**で、[モデリングプロジェクト] ノードをクリックします。

    > [!NOTE]
    > モデリングプロジェクトには、 **modeldefinition**という名前のモデル定義フォルダーが含まれています。

2. **[プロジェクト]** メニューの **[新しい項目の追加]** をクリックします。

3. [ **新しい項目の追加-** *\<project name>* ] ダイアログボックスの [ **テンプレート**] で、モデリング図の種類 ([ **UML コンポーネント図**] など) をクリックします。

4. ダイアグラムの名前を入力し、[ **追加**] をクリックします。

     モデリング図が開き、モデリング プロジェクトに表示されます。

    > [!CAUTION]
    > 他のモデリング プロジェクト、またはソリューション内の他の場所に、既存の図ファイルを追加、コピー、またはドラッグしないでください。 そのようにすると、コピーした図から要素が消えたり、図を開いた際にエラーが発生したりします。 図のファイルは、そのファイルが作成されたモデリング プロジェクトから開く必要があります。 これは、UML 図がそのモデリング プロジェクトによって所有されるモデルのビューであるためです。 図のファイルをコピーするには、新しい図を作成し、コピー元の図から新しい図に要素をコピーします。 詳細については、「 [モデリングプロジェクトと図のトラブルシューティング](#TroubleshootingModelingProjects)」を参照してください。

#### <a name="to-create-a-blank-modeling-project"></a>空のモデリング プロジェクトを作成するには

1. **[ファイル]** メニューの **[新規作成]** をポイントし、 **[プロジェクト]** をクリックします。

2. [ **新しいプロジェクト** ] ダイアログボックスの [ **インストールされているテンプレート**] で、[ **モデリングプロジェクト**] をクリックします。

3. 中央のウィンドウで、[ **モデリングプロジェクト**] をクリックします。

4. プロジェクトに名前を設定し、[ **名前** ] ボックスと [ **場所** ] ボックスに場所を指定します。

5. [ **ソリューション** ] ボックスで、[ **ソリューションに追加** ] を選択して、既に開いているソリューションに新しいプロジェクトを追加します。または、新しいソリューションを **作成** して、開いているソリューションを閉じ、新しいソリューションにプロジェクトを追加します。

## <a name="removing-modeling-diagrams-from-a-project"></a><a name="RemovingModelingDiagrams"></a> プロジェクトからのモデリング図の削除
 図を完全に削除することも、プロジェクトから図を一時的に除外し、後で元に戻すこともできます。

#### <a name="to-permanently-delete-a-diagram-from-a-project"></a>プロジェクトから図を完全に削除するには

- **ソリューションエクスプローラー**で、ダイアグラムを表すメインファイルを右クリックし、[**削除**] をクリックします。

     プロジェクトとファイル システムから図が削除されます。 図に示されている要素は、 **UML モデルエクスプローラー**からは削除されません。

    > [!NOTE]
    > 各図は 2 つのファイルを持ちます。一方のファイルは、もう一方の付属ファイルです。 たとえば、`CD1` という名前のコンポーネント図がある場合は、`CD1.componentdiagram` という名前のファイルを削除する必要があります。 `CD1.componentdiagram.layout` という名前の付属ファイルは自動的に削除されます。

#### <a name="to-temporarily-exclude-a-diagram-from-a-project"></a>プロジェクトから図を一時的に除外するには

- **ソリューションエクスプローラー**で、ダイアグラムファイルを右クリックし、[**プロジェクトから除外**] をクリックします。

     図が、プロジェクトから削除されます。 ファイル システムからは削除されません。

    > [!NOTE]
    > 図に示されている要素は、 **UML モデルエクスプローラー**からは削除されません。

#### <a name="to-restore-a-temporarily-excluded-diagram-to-a-project"></a>一時的に除外した図をプロジェクトに戻すには

1. **ソリューションエクスプローラー**で、[モデリングプロジェクト] ノードをクリックします。

    > [!NOTE]
    > モデリングプロジェクトには、 **modeldefinition**という名前のモデル定義フォルダーが含まれています。

2. **[プロジェクト]** メニューの **[既存項目の追加]** をクリックします。

3. [ **既存項目の追加** ] ダイアログボックスで、ダイアグラムファイルを見つけて、ファイルを選択し、[ **追加**] をクリックします。

     モデリング図が開き、モデリング プロジェクトに表示されます。

    > [!NOTE]
    > それぞれの図に対応するファイルは、ファイル システム内に 2 つ存在します。 `.layout` という拡張子のファイルは選択しないでください。 また、Visual Studio において、既存の UML 図を複数のモデリング プロジェクトに追加する機能はサポートされていません。 各図のファイルは、そのファイルが作成されたモデリング プロジェクトの中で開く必要があります。 これは、UML 図にそのモデリング プロジェクトが所有するモデルのビューが表示されるためです。

## <a name="diagrams-that-do-not-require-modeling-projects"></a><a name="NonModelDiagrams"></a> モデリングプロジェクトを必要としない図
 次の種類の図は、モデリング プロジェクトには含まれません。

- ソース コードのビューとして作成されるクラス図。 これらは、UML クラス図とは無関係です。 詳細については、「 [クラスと型の設計と表示](../ide/designing-and-viewing-classes-and-types.md)」を参照してください。

- コード マップ。 「 [Map dependencies across your solutions](../modeling/map-dependencies-across-your-solutions.md)」を参照してください。

- UML 図でもレイヤー図でもない図 (ドメイン固有の言語など)。

## <a name="troubleshooting-modeling-projects-and-diagrams"></a><a name="TroubleshootingModelingProjects"></a> モデリングプロジェクトと図のトラブルシューティング
 次の表で、モデリング プロジェクトまたは図で発生する可能性のある問題と、その解決方法を説明します。

|**問題点**|**原因**|**解像度**|
|---------------|----------------|--------------------|
|モデリング プロジェクトを開くことも、ソリューションに読み込むこともできません。<br /><br /> 次のメッセージが表示されます。<br /><br /> "ソリューション内の 1 つ以上のプロジェクトが正しく読み込まれていません。 詳細については、出力ウィンドウを確認してください。"<br /><br /> [出力] ウィンドウに次のメッセージが表示されます。<br /><br /> "*ModelingProjectFilenameAndPath*: Error: 認識できない Guid 形式です。"|モデリング プロジェクトに、同じソリューション内にある同じ名前のプロジェクトへの参照が含まれています。<br /><br /> たとえば、同じソリューション内にある同じ名前のプロジェクトにレイヤーがリンクされています。|テキスト エディターを使用してモデリング プロジェクト ファイルを開き、参照を削除して、モデリング プロジェクトを再度開きます。<br /><br /> この問題を回避するには、同じ名前のプロジェクトへの参照を追加しないようにします。 プロジェクト名が一意であることを確認します。|
|他のモデリング プロジェクト、またはソリューション内の他の場所に図を追加、コピー、ドラッグすると、その図の要素がなくなります。<br /><br /> - または -<br /><br /> 図を開こうとすると、次のメッセージが表示されます。<br /><br /> -"このプロジェクトには、定義が存在しないため、図の一部の図形またはコネクタがありません。 図を閉じている間に定義がモデルから削除されたか、これらの定義を含まない別のプロジェクトに図がコピーされました。"<br /><br /> - または -<br /><br /> -"このドキュメントは別のプロジェクトによって開かれています。"|モデリング プロジェクトから別のモデリング プロジェクトまたはソリューション内の別の場所に、図のファイルが追加、ドラッグ、またはコピーされました。|図のファイルをコピーするには、新しい図を作成し、コピー元の図から新しい図に要素をコピーします。|

## <a name="see-also"></a>参照
 [UML モデルとダイアグラムの編集](../modeling/edit-uml-models-and-diagrams.md)[モデリングソリューションの構成](../modeling/structure-your-modeling-solution.md)
