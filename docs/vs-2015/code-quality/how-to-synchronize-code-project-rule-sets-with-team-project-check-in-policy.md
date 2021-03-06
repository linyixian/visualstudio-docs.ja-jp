---
title: '方法: チームプロジェクトのチェックインポリシーを使用してコードプロジェクト規則セットを同期する |Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- vs.codeanalysis.selecttfsruleset
ms.assetid: 9b02f934-2db6-41ec-aaff-9c31ceec2f04
caps.latest.revision: 14
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: 3c6e7550940f9d2efa5ca228123310f1b861ee76
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/02/2020
ms.locfileid: "72651600"
---
# <a name="how-to-synchronize-code-project-rule-sets-with-team-project-check-in-policy"></a>方法: コード プロジェクト規則セットをチーム プロジェクトのチェックイン ポリシーと同期させる
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

コードプロジェクトのコード分析設定をチームプロジェクトのチェックインポリシーと同期するには、少なくともチェックインポリシーの規則セットで指定されている規則を含む規則セットを指定します。 開発者は、チェックインポリシーのルールセットの名前と場所を知らせることができます。 次のいずれかのオプションを使用して、プロジェクトのコード分析で正しい規則セットが使用されるようにすることができます。

- チェックインポリシーで Microsoft の組み込み規則セットのいずれかを使用する場合は、コードプロジェクトの [プロパティ] ダイアログボックスを開き、[コード分析] ページを表示して、コードプロジェクト設定の [コード分析] ページで規則セットを選択します。 Microsoft 標準規則セットは、Visual Studio が読み取り専用に設定されており、編集できない場合に、自動的にインストールされます。 規則セットが編集されていない場合は、ポリシーおよびローカル規則セット内の規則が一致することが保証されます。

- チェックインポリシーでカスタム規則セットが使用されている場合は、バージョン管理の規則セットファイルに対して get 操作を実行し、ローカルコピーを作成します。 次に、コードプロジェクトのコード分析設定でそのローカルの場所を指定します。 チェックインポリシーの規則セットが最新である場合、規則は確実に一致します。

     コードプロジェクトと同じ関係にあるローカルフォルダーにバージョンコントロールの場所をマップした場合、規則の場所は相対パスを使用して設定されます。 相対パスを使用すると、コード分析のコードプロジェクト設定を他のコンピューターに移動できるようになります。

- コードプロジェクトのチェックインポリシーの規則セットのコピーをカスタマイズします。 新しい規則セットに、チェックインポリシーのすべての規則と、含めるすべての規則が含まれていることを確認してください。 規則セットに、チェックインポリシーの規則セット内のすべての規則が含まれていることを確認する必要があります。

### <a name="to-specify-a-microsoft-standard-rule-set"></a>Microsoft 標準規則セットを指定するには

1. **ソリューションエクスプローラー**で、コードプロジェクトを右クリックし、[**プロパティ**] をクリックします。

2. **[コード分析]** をクリックします。

3. [ **この規則セットを実行** する] の一覧で、チェックインポリシー規則セットをクリックします。

### <a name="to-specify-a-custom-check-in-policy-rule-set"></a>カスタムチェックインポリシー規則セットを指定するには

1. 必要に応じて、チェックインポリシーを指定するルールセットファイルに対して get 操作を実行します。

2. **ソリューションエクスプローラー**で、コードプロジェクトを右クリックし、[**プロパティ**] をクリックします。

3. **[コード分析]** をクリックします。

4. [ **この規則セットを実行** する] の一覧で、をクリックし **\<Browse...>** ます。

5. [ **開く** ] ダイアログボックスで、チェックインポリシー規則セットファイルを指定します。

### <a name="to-create-a-custom-rule-set-for-a-code-project"></a>コードプロジェクトのカスタム規則セットを作成するには

1. このトピックで前述したいずれかの手順に従って、[プロジェクトの設定] ダイアログボックスの [コード分析] ページでチームプロジェクトのチェックインポリシーを選択します。

2. **[開く]** をクリックします。

3. ルールセットエディターを使用してルールを追加または削除します。

     詳細については、「 [カスタム規則セットの作成](../code-quality/creating-custom-code-analysis-rule-sets.md)」を参照してください。

4. 変更した規則セットを、ローカルコンピューター上のルールセットファイルまたは UNC パスに保存します。

5. コードプロジェクトの [プロパティ] ダイアログボックスを開き、[ **コード分析** ] ページを表示します。

6. [ **この規則セットを実行** する] の一覧で、をクリックし **\<Browse...>** ます。

7. [ **開く** ] ダイアログボックスで、規則セットファイルを指定します。
