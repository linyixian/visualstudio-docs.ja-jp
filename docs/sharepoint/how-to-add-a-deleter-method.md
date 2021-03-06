---
title: '方法: 削除子メソッドを追加する |Microsoft Docs'
ms.date: 02/02/2017
ms.topic: how-to
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- BDC [SharePoint development in Visual Studio], deleting data
- Business Data Connectivity service [SharePoint development in Visual Studio], Deleter
- BDC [SharePoint development in Visual Studio], Deleter
- BDC [SharePoint development in Visual Studio], removing data
- BDC [SharePoint development in Visual Studio], deleting entity instances
- Business Data Connectivity service [SharePoint development in Visual Studio], deleting entity instances
- Business Data Connectivity service [SharePoint development in Visual Studio], deleting data
- Business Data Connectivity service [SharePoint development in Visual Studio], removing data
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: dd97d28936e9f0cc50e9064fdc1a6a64bb20fc77
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/02/2020
ms.locfileid: "86017042"
---
# <a name="how-to-add-a-deleter-method"></a>方法: 削除子メソッドを追加する
  エンドユーザーが、削除子メソッドをモデルに追加することによって、SharePoint サイトの外部リストからデータレコードを削除できるようにすることができます。 詳細については、「 [ビジネスデータ接続モデルの設計](../sharepoint/designing-a-business-data-connectivity-model.md)」を参照してください。

### <a name="to-create-a-deleter-method"></a>削除子メソッドを作成するには

1. **BDC デザイナー**で、エンティティを選択します。

2. メニューバーで、[ **View**  >  **その他の Windows**  >  **BDC メソッドの詳細**を表示] を選択します。

    [ **BDC メソッドの詳細** ] ウィンドウが開きます。 このウィンドウの詳細については、「 [BDC モデルデザインツールの概要](../sharepoint/bdc-model-design-tools-overview.md)」を参照してください。

3. [ **メソッドの追加** ] の一覧で、[ **削除子メソッドの作成**] を選択します。

    Visual Studio によって、モデルに次の要素が追加されます。 これらの要素は、[ **BDC メソッドの詳細** ] ウィンドウに表示されます。

   - **Delete**という名前のメソッド。

   - メソッドの入力パラメーター。

   - パラメーターの型記述子。

   - メソッドのメソッドインスタンス。

     詳細については、「 [ビジネスデータ接続モデルの設計](../sharepoint/designing-a-business-data-connectivity-model.md)」を参照してください。

4. **ソリューションエクスプローラー**で、エンティティに対して生成されたサービスコードファイルのショートカットメニューを開き、[**コードの表示**] を選択します。

    コードエディターで entity service コードファイルが開きます。 Entity service コードファイルの詳細については、「 [ビジネスデータ接続モデルを作成する](../sharepoint/creating-a-business-data-connectivity-model.md)」を参照してください。

5. レコードを削除するコードを削除子メソッドに追加します。 次の例では、SQL Server の AdventureWorks サンプルデータベースを使用して、販売注文から行項目を削除します。

   > [!NOTE]
   > この例のメソッドでは、2つの入力パラメーターを使用します。

   > [!NOTE]
   > フィールドの値を `ServerName` サーバーの名前に置き換えます。

    [!code-csharp[SP_BDC#6](../sharepoint/codesnippet/CSharp/SP_BDC/bdcmodel1/salesorderdetailservice.cs#6)]
    [!code-vb[SP_BDC#6](../sharepoint/codesnippet/VisualBasic/sp_bdc/bdcmodel1/salesorderdetailservice.vb#6)]

## <a name="see-also"></a>関連項目
- [ビジネスデータ接続モデルを設計する](../sharepoint/designing-a-business-data-connectivity-model.md)
- [方法: Finder メソッドを追加する](../sharepoint/how-to-add-a-finder-method.md)
- [方法: 特定の Finder メソッドを追加する](../sharepoint/how-to-add-a-specific-finder-method.md)
- [方法: Creator メソッドを追加する](../sharepoint/how-to-add-a-creator-method.md)
- [方法: Updater メソッドを追加する](../sharepoint/how-to-add-an-updater-method.md)
- [BDC モデルのデザインツールの概要](../sharepoint/bdc-model-design-tools-overview.md)
- [方法: メソッドにパラメーターを追加する](../sharepoint/how-to-add-a-parameter-to-a-method.md)
- [方法: メソッドインスタンスを定義する](../sharepoint/how-to-define-a-method-instance.md)
