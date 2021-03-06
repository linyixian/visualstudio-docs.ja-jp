---
title: '方法: コードを実行せずに Office ソリューションを開く'
ms.date: 02/02/2017
ms.topic: how-to
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Office solutions [Office development in Visual Studio], opening
- opening Office solutions
- bypassing assemblies
- solutions [Office development in Visual Studio], opening
- assemblies [Office development in Visual Studio], bypassing
- Office documents [Office development in Visual Studio, opening without running code
- documents [Office development in Visual Studio], opening without running code
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: d84515c2c3159b61b96f77555b23eef0df0ae961
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/02/2020
ms.locfileid: "85543482"
---
# <a name="how-to-open-office-solutions-without-running-code"></a>方法: コードを実行せずに Office ソリューションを開く
  マネージコード拡張機能を使用して作成された Microsoft Office ソリューションは、エンドユーザーの Office アプリケーションのセキュリティ設定が [高] に設定されている場合でも実行されます。 これは、.NET アセンブリコードのセキュリティは、Microsoft Office ではなく Microsoft .NET Framework によって管理されるためです。

 ただし、コードを実行せずにドキュメントを開くことが必要になる場合もあります。 たとえば、ドキュメントを開いたときに実行されるコードは、内容を変更することがありますが、コードが変更する前にドキュメントがどのように表示されるかを更新する必要があります。 または、特定の情報が含まれているドキュメントを他のユーザーに送信したり、コードを実行したり、コンテンツを変更したりする必要がない場合もあります。

 [!INCLUDE[appliesto_alldoc](../vsto/includes/appliesto-alldoc-md.md)]

 アセンブリコードを実行せずに、マネージコード拡張機能を含むドキュメントまたはブックを開くには、いくつかの方法があります。

## <a name="to-bypass-the-assembly-by-using-the-shift-key"></a>Shift キーを使用してアセンブリをバイパスするには

- Word および Excel がドキュメントを開いているときに初期化イベントが発生しないように、 **shift**キーを押しながら [**ファイル**] メニューからドキュメントとブックを開きます。

    > [!NOTE]
    > **はじめに**作業ウィンドウからドキュメントまたはブックを開いた場合、 **shift キー**を押したままにしてもコードはバイパスされません。 また、SHIFT キーを押したままにしても、ドキュメントが開いた後にイベントが発生するのを防ぐことはできません。

     このメソッドは、コードを実行せずに変更を行うドキュメントを開き、ドキュメントを最初に変更する場合に便利です。

## <a name="to-bypass-an-assembly-by-renaming-or-removing-it"></a>名前の変更または削除によってアセンブリをバイパスするには

- アセンブリが配置されているコンピューターに必要なアクセス許可がある場合は、アセンブリの名前を変更するか、アセンブリを削除して、ドキュメントまたはブックが見つからないようにすることができます。 この結果、Office ドキュメントが開かれるたびにエラーが発生します。

     ソリューションが複数のユーザーによって使用されている場合、この方法によってソリューションがすべてのユーザーに対して実行されるのを防ぐことができます。 これは、コードまたは参照先のサーバーで問題が検出され、すべてのユーザーがそれを実行できないようにする場合に役立ちます。

## <a name="see-also"></a>関連項目
- [セキュリティで保護された Office ソリューション](../vsto/securing-office-solutions.md)
- [Office ソリューションの配置](../vsto/deploying-an-office-solution.md)
- [Office ソリューションの設計と作成](../vsto/designing-and-creating-office-solutions.md)
- [Office ソリューションのアプリケーションマニフェストと配置マニフェスト](../vsto/application-and-deployment-manifests-in-office-solutions.md)
