---
title: IDE で定義されているコマンド、メニュー、およびグループ |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- commands, environment-defined
- .vsct files, environment-defined constants
- command groups, environment-defined
ms.assetid: 86b3af13-7163-48c6-986b-7beeedbc26cc
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 6557f49b019a6793698dabe852919ec2e9f28cfd
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/02/2020
ms.locfileid: "80707718"
---
# <a name="ide-defined-commands-menus-and-groups"></a>IDE 定義コマンド、メニュー、およびグループ
多くのメニュー、コマンド、およびコマンドグループは、IDE で使用するために既に定義されてい [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] ます。 これらのコマンドは、を拡張するときに使用することもでき [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] ます。

## <a name="finding-environment-defined-commands"></a>環境定義コマンドの検索
 環境コマンドは、次の4つの vsct ファイルで定義されています。

- SharedCmdDef. vsct

- SharedCmdPlace vsct

- ShellCmdDef. vsct

- ShellCmdPlace vsct

  これらのファイルは \VisualStudioIntegration\Common\Inc にあり *\<Visual Studio SDK installation path>* \\ ます。 これらのファイルには、独自のメニュー、グループ、およびコマンドのコンテナーとして、VSPackage のコマンドテーブル構成 (vsct) ファイルで使用できるメニューとグループの定義と Guid が用意されています。

## <a name="in-this-section"></a>このセクションの内容
- [Visual Studio メニューの GUID および ID](../../extensibility/internals/guids-and-ids-of-visual-studio-menus.md)

 Visual Studio のメニューバーのメニューの GUID と ID の値、およびそれらに含まれるグループの数を示します。

- [Visual Studio ツール バーの GUID および ID](../../extensibility/internals/guids-and-ids-of-visual-studio-toolbars.md)

 Visual Studio IDE のツールバーの GUID と ID の値、およびそれらに含まれるグループの数を示します。

- [Visual Studio コマンドの GUID および ID](../../extensibility/internals/guids-and-ids-of-visual-studio-commands.md)

 Visual Studio IDE で定義されているコマンドの GUID と ID の値を指定します。

## <a name="see-also"></a>関連項目
- [Visual Studio Command Table (.Vsct) ファイル](../../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)
- [プロジェクト システムを拡張するための IDE 定義コマンド](../../extensibility/internals/ide-defined-commands-for-extending-project-systems.md)
- [VSPackage でユーザー インターフェイス要素を追加する方法](../../extensibility/internals/how-vspackages-add-user-interface-elements.md)
