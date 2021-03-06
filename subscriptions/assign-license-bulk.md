---
title: Visual Studio サブスクリプションのライセンスをユーザーのグループに割り当てる | Microsoft Docs
author: evanwindom
ms.author: lank
manager: lank
ms.assetid: c2853359-18fd-4be4-97a6-02230c862f92
ms.date: 05/10/2020
ms.topic: how-to
description: 一括追加機能または Microsoft Azure Active Directory グループのどちらかを使って、管理者が複数のサブスクライバーにライセンスを割り当てできる方法について説明します
ms.openlocfilehash: da7ce369e1d9aaa13b0c346005914b7f64ceb780
ms.sourcegitcommit: 577c905de52057a741e68c2ed168ea527813fda5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/15/2020
ms.locfileid: "88249622"
---
# <a name="assign-subscriptions-to-multiple-users"></a>複数のユーザーにサブスクリプションを割り当てる
サブスクリプション管理ポータルでは、ユーザーを一度に 1 人ずつ追加することも、大きなグループ単位で追加することもできます。  ユーザーを個別に追加するには、[1 人のユーザーの追加](assign-license.md)に関する記事を参照してください。

大規模なユーザー グループを追加するには、一括追加機能を使用できます。または、所属する組織で Microsoft Azure Active Directory (Azure AD) を使用している場合は、Azure AD グループを使用することができます。 この記事では、両方のオプションの手順について説明します。 

<br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4vxNq]

## <a name="use-bulk-add-to-assign-subscriptions"></a>一括追加を使用してサブスクリプションを割り当てる
1. Visual Studio サブスクリプション管理ポータル (<https://manage.visualstudio.com> ) にサインインします。

1. 複数のサブスクライバーを一度に追加するには、 **[サブスクライバーの管理]** タブに移動します。 **[追加]** タブを選択してから、ドロップダウンで **[一括追加]** を選択します。  

1. 一括追加では、Microsoft Excel テンプレートを使用してサブスクライバー情報をアップロードします。 [Upload Multiple Subscribers]\(複数のサブスクライバーのアップロード\) ダイアログ ボックスで、 **[ダウンロード]** を選択してテンプレートをダウンロードします。
   > [!div class="mx-imgBorder"]
   > ![複数のサブスクライバーをアップロードするための Excel テンプレートをダウンロードする](media/download-template-upload-subscribers.png "空の Excel テンプレートをダウンロードし、一括割り当てプロセスを開始します。")
   >
   > [!NOTE]
   > 常にこのテンプレートの最新バージョンをダウンロードしてください。 古いバージョンを使うと、一括アップロードが失敗する可能性があります。

1. Excel スプレッドシートのフィールドに、サブスクリプションを割り当てるユーザーの情報を入力します。 *[Reference]* は省略可能なフィールドです。完成したらローカルにファイルを保存します。

    > [!NOTE]
    > テンプレートのフィールドの 1 つで、管理者は、サブスクライバーがソフトウェアをダウンロードする機能を有効または無効にすることができます。  ダウンロードを無効にすると、プロダクト キーへのアクセスも無効になります。

   問題なくアップロードできるよう、次のベスト プラクティスに従ってください。

    - フォームのどのフィールドにもコンマが含まれていないことを確認します。
    - フォームのフィールドの前後のスペースを削除します。
    - ユーザーの名前の名または姓が 2 つの部分からなる場合、それらの間に余分なスペースがないようにします (たとえば、"Maggie May" のように 2 つの部分からなる名前は、"MaggieMay" と入力する必要があります。システムは余分なスペースを除去しません)。
    - 必須フィールドがすべて入力済みになっていることを確認します。 
    - **[エラー メッセージ]** 列を確認してください。  エラーが一覧に示された場合は、ファイルのアップロードを試行する前に解決します。 

1. Visual Studio サブスクリプション管理ポータルに戻ります。 **[Upload Multiple Subscribers]\(複数のサブスクライバーのアップロード\)** ダイアログ ボックスで、 **[参照]** を選択します。
   > [!div class="mx-imgBorder"]
   > ![複数のサブスクライバーをアップロードするために保存したテンプレートを参照する](media/bulk-add-browse-saved-template.png "ファイルの場所を参照したり、このダイアログ ボックスにドラッグ アンド ドロップしたりできます。")

1. 保存した Excel ファイルを選んで、 **[OK]** を選択します。
   > [!div class="mx-imgBorder"]
   > ![複数のサブスクライバーをアップロードするための Excel テンプレートをアップロードする](media/bulk-upload-subscribers.png "データを含むテンプレートがここに表示されます。[OK] を選択すると、アップロードが開始します。")

    アップロードの進行状況を示すダイアログが表示されます。

    テンプレートにエラーが含まれていると、アップロードは失敗してエラーが表示されるので、テンプレートを修正して一括アップロードを再試行します。
   > [!div class="mx-imgBorder"]
   > ![複数サブスクライバーのアップロードが失敗した場合のエラー メッセージ](_img/assign-license-bulk/bulk-add-upload-failure.png "このメッセージは、アップロードしたファイルにエラーがあった場合に表示されます。エラーを解決し、一括追加プロセスを再実行します。")

   エラーが発生した場合は、次の手順を行います。
   1. 作成した Excel ファイルを開き、問題を修正して、ファイルを保存します。
   0. 管理ポータルに戻り、 **[追加]** を選択します。
   0. **[一括追加]** を選択します。
   0. Excel ファイルは既に保存されているため、テンプレートをダウンロードする必要はありません。  **[参照]** を選択し、保存したばかりのファイルを検索し、 **[開く]** を選択します。
   0. **[OK]** を選択します。


    アップロードが成功すると、サブスクライバーの一覧と確認メッセージが表示されます。
   > [!div class="mx-imgBorder"]
   > ![複数サブスクライバーのアップロードが成功した場合の確認メッセージ](_img/assign-license-bulk/bulk-add-upload-success.png "アップロードが正常に完了すると、確認メッセージが表示されます。")

## <a name="use-azure-active-directory-groups-to-assign-subscriptions"></a>Azure Active Directory グループを使用してサブスクリプションを割り当てる 
この機能を使用すると、サブスクリプションの割り当てが簡単に利用できます。 サブスクリプション管理ポータル上で、Azure Active Directory セキュリティ グループを追加できます。そうすることで、グループ内のすべてのユーザーに確実にサブスクリプションが割り当てられます。 また、操作を簡単にするために、ユーザーが組織を離れ、Azure Active Directory から削除されるときに、サブスクリプションへのアクセスも削除されます。 


> [!IMPORTANT]
>
> サブスクライバーを追加する場合の Azure AD グループの使用には、次の制限事項が適用されます。
> - 管理ポータルに最初にグループを追加するときは、管理者が AAD テナントのメンバーである必要があります。  グループを追加した後、グループのメンバーシップの変更には管理者の関与は必要ありません。 
> - グループには、少なくとも 1 人のメンバーを含んでいる必要があります。  空のグループはサポートされていません。
> - グループのユーザー数は 1,000 未満にする必要があります。 
> - すべてのユーザーが、グループの最上位レベルにいる必要があります。  入れ子になったグループはサポートされていません。
> - 信頼済みの契約のみがサポートされます。
> - グループのすべてのメンバーが、Azure AD アカウントに関連付けられた電子メール アドレスを保持している必要があります。
> - Azure AD グループを使用して追加されたサブスクリプションの場合、通知用の個別の電子メール アドレスはサポートされていません。  

<br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4rvvW]

1. Visual Studio サブスクリプション管理ポータル ([https://manage.visualstudio.com](https://manage.visualstudio.com)) にサインインします。

2. 複数のサブスクライバーを一度に追加するには、 **[サブスクライバーの管理]** タブに移動します。

3. **[追加]** タブを選択し、ドロップダウンで **[Azure Active Directory グループ]** を選択します。  

   > [!div class="mx-imgBorder"]
   > ![Azure AD を使用した一括追加の選択](_img/assign-license-bulk/bulk-add-aad.png "Azure Active Directory グループからサブスクライバーをプルするには、[Bulk add using Azure AD]\(Azure AD を使用した一括追加\) 機能を選択します。")

4. フォーム フィールドに追加する Azure AD グループの名前の入力を開始します。 これにより、組織内で使用可能な Azure AD グループが検索されます。 

5. グループを選択すると、グループ名がフィールドに自動的に入力されます。 追加する前に、そのグループ内のユーザーを表示することもできます。 次に、グループのサブスクリプション レベル、ダウンロード権限、および通信設定を選択できます。 必要に応じて、[参照] フィールドに詳細を追加できます。 

   > [!div class="mx-imgBorder"]
   > ![Azure AD グループを選択する](_img/assign-license-bulk/bulk-add-aad-details.png "Azure AD グループの名前を選択し、そのグループからサブスクライバーを追加します。")

6. **[追加]** 、 **[確認]** の順に選択します。 

7. 追加したグループを表示するには、ユーザーの一覧の一番下までスクロールします。  

8. グループのメンバーを表示するには、 **[利用者の表示]** を選択します。 グループ内のサブスクライバーに関する詳細を表示することは可能ですが、サブスクライバーまたは彼らが割り当てられているサブスクリプションを編集することはできません。    

> [!NOTE]
> 後に Azure AD グループの一部として追加されたユーザーにサブスクリプションを個別に既に割り当てている場合は、グループの一部として追加され、個別に一覧表示されなくなります。 ただし、個別のサブスクリプションが異なるサブスクリプション レベル用のものである場合は、サブスクリプションを 2 つ所有することになります。  例:ユーザーが個別の Visual Studio Professional サブスクリプションを所有していて、さらに Visual Studio Enterprise サブスクリプションを割り当てるグループのメンバーである場合は、両方を所有することになります。  


## <a name="frequently-asked-questions"></a>よく寄せられる質問
### <a name="q-can-i-choose-multiple-subscription-levels-to-be-assigned-within-an-azure-ad-group"></a>Q:Azure AD グループ内で複数のサブスクリプション レベルを割り当てることはできますか? 
A: いいえ -- グループ内のすべてのユーザーが同じサブスクリプションを受け取ります。 

### <a name="q-can-i-edit-subscriber-details-of-individuals-added-in-an-azure-ad-group"></a>Q:Azure AD グループに追加されたユーザーのサブスクライバーの詳細を編集できますか?  
A: いいえ -- 個々のサブスクライバーの情報を変更するには、それらを Azure AD セキュリティ グループから削除して、サブスクリプションを個別に割り当てる必要があります。  

### <a name="q-i-added-someone-to-my-azure-ad-security-group-but-i-dont-see-them-added-in-the-subscriptions-administration-portal-and-they-dont-have-a-subscription-why-not"></a>Q:Azure AD セキュリティ グループにユーザーを追加しましたが、そのユーザーが追加されたことがサブスクリプション管理ポータル上に表示されず、サブスクリプションもありません。 なぜでしょうか。  
A: 組織で Azure AD がどのように構成されているかに応じて、ユーザーが追加されるまでに最大 24 時間の遅延が発生することがあります。 24 時間以上経過している場合は、[サポートにお問い合わせください](https://visualstudio.microsoft.com/support/support-overview-vs)。  

## <a name="see-also"></a>関連項目
- [Visual Studio ドキュメント](https://docs.microsoft.com/visualstudio/)
- [Azure DevOps ドキュメント](https://docs.microsoft.com/azure/devops/)
- [Azure ドキュメント](https://docs.microsoft.com/azure/)
- [Microsoft 365 ドキュメント](https://docs.microsoft.com/microsoft-365/)

## <a name="next-steps"></a>次の手順
- 追加するサブスクライバーは 1 人または 2 人だけですか?  [1 人のユーザーの追加](assign-license.md)に関する記事を参照してください。
- お困りの際は、 [Visual Studio の管理とサブスクリプションのサポート](https://visualstudio.microsoft.com/support/support-overview-vs)にお問い合わせください。
