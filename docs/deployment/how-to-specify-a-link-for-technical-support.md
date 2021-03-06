---
title: テクニカルサポートへのリンクを指定する方法 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: how-to
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- Support URL property
- product support, specifying URL for ClickOnce applications
- Web pages, ClickOnce
- Web sites, creating for ClickOnce support
- ClickOnce deployment, specifying support Web page address
- customer support, ClickOnce applications
- URLs, ClickOnce applications
ms.assetid: 500aebee-545e-4831-a78b-b8671a008015
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: e64ef97b8b51f8a943e216bad67ec300026d5654
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/02/2020
ms.locfileid: "85382056"
---
# <a name="how-to-specify-a-link-for-technical-support"></a>方法: テクニカル サポートのリンクを指定する
アプリケーションを公開するとき [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 、 **サポート URL** プロパティは、ユーザーがアプリケーションに関する情報を取得するために使用できる Web ページまたはファイル共有を識別します。 このプロパティは省略可能です。指定されている場合、URL はアプリケーションの [ **プログラムの追加と削除** ] ダイアログボックスに表示されます。

 "**サポート URL** " プロパティは、**プロジェクトデザイナー**の [**発行**] ページで設定できます。

### <a name="to-specify-a-support-url"></a>サポート URL を指定するには

1. **ソリューション エクスプローラー**でプロジェクトを選択し、 **[プロジェクト]** メニューの **[プロパティ]** をクリックします。

2. **[公開]** タブをクリックします。

3. [ **オプション** ] ボタンをクリックして、[ **発行オプション** ] ダイアログボックスを開きます。

4. [ **説明**] をクリックします。

5. [ **サポート URL** ] フィールドに、web サイト、web ページ、または UNC 共有への完全修飾パスを入力します。

## <a name="see-also"></a>関連項目
- [ClickOnce アプリケーションの発行](../deployment/publishing-clickonce-applications.md)
- [方法: 発行ウィザードを使用して ClickOnce アプリケーションを発行する](../deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard.md)