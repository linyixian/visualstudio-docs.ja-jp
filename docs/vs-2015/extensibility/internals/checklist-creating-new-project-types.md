---
title: 'チェックリスト: 新しいプロジェクトの種類を作成する |Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- projects [Visual Studio SDK], creating new types
- project types, checklist for creating
ms.assetid: 29eb9c3b-1933-4741-aa85-65a33f0825ba
caps.latest.revision: 24
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 02edc5925109a31eebfd98c90bd116fb86eef276
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/02/2020
ms.locfileid: "65697234"
---
# <a name="checklist-creating-new-project-types"></a>チェックリスト: 新しいプロジェクト タイプの作成
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

新しいプロジェクトの種類を作成するには、いくつかのタスクを完了する必要があります。 次のチェックリストでは、これらのタスクについて説明します。  
  
1. 新しいプロジェクトの種類の機能をデザインします。 詳細については、「 [プロジェクトの種類の設計](../../extensibility/internals/project-type-design-decisions.md)上の決定」を参照してください。  
  
2. コードおよびその他のプロジェクト要素に使用されるエディターを決定します。 コアエディターまたは標準エディターを使用することも、プロジェクト固有のエディターを作成して使用することもできます。 詳細については、「 [カスタムエディターとデザイナーの作成](../../extensibility/creating-custom-editors-and-designers.md) 」および「 [方法: プロジェクト固有のエディターを開く](../../extensibility/how-to-open-project-specific-editors.md)」を参照してください。  
  
3. プロジェクト項目が **クラスビュー** と **オブジェクトブラウザー**に与える参加レベルを決定します。 詳細については、「 [シンボル参照ツールのサポート](../../extensibility/internals/supporting-symbol-browsing-tools.md)」を参照してください。  
  
4. プロジェクトおよびプロジェクト項目に対して以前に行った設計上の決定に基づいて、新しいクラスを派生させます。  
  
5. 次のプロジェクトの種類のコンポーネントのコードを記述します。  
  
    - プロジェクトファクトリ。新しいプロジェクトの作成と、既存のプロジェクトのオープンを管理します。 詳細については、「 [プロジェクトファクトリを使用したプロジェクトインスタンスの作成](../../extensibility/internals/creating-project-instances-by-using-project-factories.md)」を参照してください。  
  
    - プロジェクト階層とコマンド処理。 詳細については、「 [ビルド内にありません: HierUtil7 プロジェクトクラスを使用したプロジェクトの種類の実装 (C++)](https://msdn.microsoft.com/a5c16a09-94a2-46ef-87b5-35b815e2f346)」、「プロジェクト [モデルの要素](../../extensibility/internals/elements-of-a-project-model.md)」、「プロジェクトモデルの [コアコンポーネント](../../extensibility/internals/project-model-core-components.md) 」、および「 [menucommands と OleMenuCommands](../../misc/menucommands-vs-olemenucommands.md)」を参照してください。  
  
    - プロジェクト項目の管理。 [ **新しいプロジェクト** ] ダイアログボックスへのプロジェクトの追加が含まれます。 詳細については、「 [プロジェクトおよびプロジェクト項目テンプレートの追加](../../extensibility/internals/adding-project-and-project-item-templates.md) 」および「 [プロジェクトと項目テンプレートの登録](../../extensibility/internals/registering-project-and-item-templates.md)」を参照してください。  
  
    - プロジェクトの状態と個々の項目の永続化。 詳細については、「 [プロジェクト項目を開いて保存](../../extensibility/internals/opening-and-saving-project-items.md)する」を参照してください。 ソリューション情報の永続化については、「 [ソリューション](../../extensibility/internals/solutions-overview.md)」を参照してください。  
  
    - プロパティウィンドウに表示する構成に依存しないプロパティ。 詳細については、「 [プロパティの拡張](../../extensibility/internals/extending-properties.md)」を参照してください。  
  
    - 構成に依存するプロパティを表示するためにプロパティページに実装されているプロジェクト構成プロパティ。 詳細については、「 [構成オプションの管理](../../extensibility/internals/managing-configuration-options.md)」を参照してください。  
  
    - 配置の出力を列挙しています。 詳細については、「 [出力のプロジェクト構成](../../extensibility/internals/project-configuration-for-output.md)」を参照してください。  
  
    - Project スタートアップサービス。 詳細については、「 [プロジェクトモデルの要素](../../extensibility/internals/elements-of-a-project-model.md) 」および「 [プロジェクトモデルのコアコンポーネント](../../extensibility/internals/project-model-core-components.md)」を参照してください。  
  
    - オートメーションに使用できるオブジェクト、またはから派生したクラス `IDispatch` 。  
  
    - XML コマンドテーブル (vsct) ファイル。 詳細については、「 [Visual Studio Command Table (.Vsct) Files](../../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)」を参照してください。  
  
6. プロジェクトの種類をテスト、デバッグ、および開始します。  
  
7. の値としてを設定して、[**参照の追加**] ダイアログボックスの [**プロジェクト**] タブにプロジェクトを表示し `VARIANT_TRUE` `VSHPROPID_ShowProjInSolutionPage` ます。 詳細については、次のトピックを参照してください。 <xref:Microsoft.VisualStudio.Shell.Interop.__VSHPROPID> および <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy.GetProperty%2A>  
  
8. Vspackage をインストールするための Microsoft インストーラー (.msi) ファイルを作成します。 詳細については、「 [Windows インストーラーを使用した vspackage のインストール](../../extensibility/internals/installing-vspackages-with-windows-installer.md)」、「 [プロジェクトの種類の登録](../../extensibility/internals/registering-a-project-type.md)」、および「 [vspackage](../../extensibility/internals/vspackages.md)」を参照してください。  
  
## <a name="see-also"></a>参照  
 [Visual Studio での階層](../../extensibility/internals/hierarchies-in-visual-studio.md)   
 [プロジェクトの種類を作成する場合](../../extensibility/internals/when-to-create-project-types.md)   
 [プロジェクト タイプの作成](../../extensibility/internals/creating-project-types.md)
