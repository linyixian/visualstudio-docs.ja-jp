---
title: 接続済みサービス | を使用して Redis の Azure Cache を追加するMicrosoft Docs
description: Visual Studio を使用して接続済みサービスを追加することにより、Redis サポート用の Azure キャッシュをアプリに追加します。
author: AngelosP
manager: jillfra
ms.custom: vs-azure
ms.workload: azure-vs
ms.topic: conceptual
ms.date: 08/17/2020
ms.author: angelpe
monikerRange: '>= vs-2019'
ms.openlocfilehash: 7583848c4bbe38f9094c60998e16ca3e95cf399f
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/02/2020
ms.locfileid: "88643180"
---
# <a name="add-azure-cache-for-redis-by-using-visual-studio-connected-services"></a>Visual Studio を使用して Redis 用の Azure Cache を追加接続済みサービス

Visual Studio では、 **接続済みサービス** 機能を使用して、以下のいずれかを Redis の Azure cache に接続できます。

- .NET Framework コンソールアプリ
- ASP.NET MVC (.NET Framework) 
- ASP.NET Core
- .NET Core (コンソールアプリ、WPF、Windows フォーム、クラスライブラリを含む)
- .NET Core Worker ロール
- Azure Functions
- ユニバーサル Windows プラットフォームアプリ
- Xamarin
- Cordova

接続済みサービス機能により、必要なすべての参照と接続コードがプロジェクトに追加され、構成ファイルが適切に変更されます。

> [!NOTE]
> このトピックは、Windows 上の Visual Studio に適用されます。 Visual Studio for Mac については、[Visual Studio for Mac での接続済みサービス](/visualstudio/mac/connected-services)に関するページを参照してください。
## <a name="prerequisites"></a>前提条件

- Azure ワークロードがインストールされている Visual Studio。
- サポートされている種類の1つのプロジェクト

## <a name="connect-to-azure-cache-for-redis-using-connected-services"></a>接続済みサービスを使用して Azure Cache for Redis に接続する

1. Visual Studio でプロジェクトを開きます。

1. **ソリューションエクスプローラー**で、[**接続済みサービス**] ノードを右クリックし、コンテキストメニューの [**接続済みサービスの追加**] を選択します。

1. [ **接続済みサービス** ] タブで、 **サービスの依存関係**の [+] アイコンを選択します。

    ![サービスの依存関係の追加](./media/vs-azure-tools-connected-services-storage/vs-2019/connected-services-tab.png)

1. [ **依存関係の追加** ] ページで、[ **Redis 用の Azure キャッシュ**] を選択します。

    ![Azure Cache for Redis を追加する](./media/azure-redis-cache-add-connected-service/azure-redis-cache.png)

    まだサインインしていない場合は、Azure アカウントにサインインします。 Azure アカウントを持っていない場合、[無料試用版](https://azure.microsoft.com/account/free)でサインアップできます。

1. [ **Redis 用の Azure キャッシュの構成** ] 画面で、redis 用の既存の azure キャッシュを選択し、[ **次へ**] を選択します。

    新しいコンポーネントを作成する必要がある場合は、次の手順に進んでください。 それ以外の場合は、手順 7 に進みます。

    ![Redis 用の既存の Azure キャッシュに接続する](./media/azure-redis-cache-add-connected-service/created-azure-redis-cache.png)

1. Azure Redis Cache を作成するには:

   1. 画面の下部にある [ **新しい Azure Redis Cache の作成** ] を選択します。

   1. **Azure cache For Redis: [新規作成**] 画面を入力し、[**作成**] を選択します。

       ![Redis 用の新しい Azure キャッシュ](./media/azure-redis-cache-add-connected-service/create-new-azure-redis-cache.png)

   1. [ **Redis 用の Azure キャッシュの構成** ] 画面が表示されたら、新しいキャッシュが一覧に表示されます。 一覧から新しいデータベースを選択し、[ **次へ**] を選択します。

1. 接続文字列名を入力するか、既定値を選択して、接続文字列をローカルシークレットファイルに保存するか、 [Azure Key Vault](/azure/key-vault)に格納するかを選択します。

   ![接続文字列の指定](./media/azure-redis-cache-add-connected-service/connection-string.png)

1. [ **変更の概要** ] 画面には、プロセスが完了した場合にプロジェクトに対して行われるすべての変更が表示されます。 変更が OK の場合は、[ **完了**] を選択します。

   ![変更の概要](./media/azure-redis-cache-add-connected-service/summary-of-changes.png)

1. 接続は、[**接続済みサービス**] タブの [**サービスの依存関係**] セクションに表示されます。

   ![サービスの依存関係](./media/azure-redis-cache-add-connected-service/service-dependencies-after.png)

## <a name="see-also"></a>関連項目

- [Redis の Azure Cache の製品ページ](https://azure.microsoft.com/services/cache)
- [Azure Cache for Redis のドキュメント](/azure/azure-cache-for-redis/)
- [接続済みサービス (Visual Studio for Mac)](/visualstudio/mac/connected-services)