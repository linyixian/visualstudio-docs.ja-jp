---
title: Web サイトサポート属性 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- web site projects, registration
ms.assetid: 46d52e2c-ca2a-4bbd-8500-5b0129768aec
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: ef75f99480145475278357a552f3ac74c0289800
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/02/2020
ms.locfileid: "80703497"
---
# <a name="web-site-support-attributes"></a>Web サイト サポートの属性
[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] Web サイトプロジェクトを拡張して、Web プログラミング言語をサポートすることができます。 言語をに登録する必要があり [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] ます。これにより、言語を選択したときに [ **新しい Web サイト** ] ダイアログボックスにプロジェクトテンプレートが表示されるようになります。

IronPython Studio サンプルには、web サイトのサポートが含まれています。 このサンプルには、新しい Web プロジェクトの分離コードとして IronPython を登録するための次の属性クラスが含まれています。

## <a name="websiteprojectattribute"></a>WebSiteProjectAttribute
 この属性は言語プロジェクトに適用されます。 この言語は、[**新しい Web サイト**] ダイアログボックスの [**言語**] ボックスの一覧に表示される Web プログラミング言語の一覧に追加されます。 たとえば、次のコードでは、IronPython がリストに追加されます。

```
[WebSiteProject("IronPython", "Iron Python")]
public class PythonProjectPackage : ProjectPackage
```

 この属性は、テンプレートフォルダーを指すようにテンプレートパスを設定することもできます。 テンプレートフォルダーの場所の詳細については、「 [Web サイトサポートテンプレート](../../extensibility/internals/web-site-support-templates.md)」を参照してください。

## <a name="websiteprojectrelatedfilesattribute"></a>WebSiteProjectRelatedFilesAttribute
 この属性は言語プロジェクトに適用されます。 これにより、Web サイトプロジェクトは、 **ソリューションエクスプローラー**内の別のファイルの種類 (プライマリ) の下にあるファイルの種類 (関連) を入れ子にすることができます。

 たとえば、次のコードでは、IronPython codebehind ファイルが .aspx ファイルに関連付けられていることを指定しています。 IronPython Web サイトソリューションに新しい .aspx Web ページが作成されると、新しい .py ソースファイルが生成され、.aspx ページの子ノードとして表示されます。

```
[WebSiteProjectRelatedFiles("aspx", "py")]
public class PythonProjectPackage : ProjectPackage
```

## <a name="provideintellisenseproviderattribute"></a>ProvideIntellisenseProviderAttribute
 この属性は、言語プロジェクトパッケージに配置されます。 言語の IntelliSense プロバイダーを選択します。

 たとえば、次のコードでは、を実装する PythonIntellisenseProvider のインスタンスを <xref:Microsoft.VisualStudio.Shell.Interop.IVsIntellisenseProject> オンデマンドで作成し、言語サービスを提供するように指定しています。

```
[ProvideIntellisenseProvider(typeof(PythonIntellisenseProvider), "IronPythonCodeProvider", "Iron Python", ".py", "IronPython;Python", "IronPython")]
public class PythonPackage : Package, IOleComponent
```

 IVsIntellisenseProject 実装は、コードを含む Web ページが要求されているがキャッシュされていない場合に、参照を処理し、言語コンパイラを呼び出します。

## <a name="see-also"></a>こちらもご覧ください
- [Web サイト サポート](../../extensibility/internals/web-site-support.md)
