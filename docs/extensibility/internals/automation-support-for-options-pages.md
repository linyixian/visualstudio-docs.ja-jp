---
title: オプションページのオートメーションサポート |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- Tools Options pages [Visual Studio SDK], automation support
- automation [Visual Studio SDK], creating Tools Options pages
ms.assetid: 0b25b82c-7432-4e0a-9e84-350269ba8260
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: fe45238948d5b4cdebbf9f002f6b242515e7622e
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/02/2020
ms.locfileid: "80709932"
---
# <a name="automation-support-for-options-pages"></a>オプションページのオートメーションサポート
Vspackage では、の [**ツール**] メニュー ([**ツール**] [オプション] ページ) にカスタム**オプション**のダイアログボックスを表示し、オートメーションモデルで使用できるようにすることができ [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] ます。

## <a name="tools-options-pages"></a>[ツール] メニューの [オプション] ページ
 **ツールオプション**ページを作成するには、VSPackage が VSPackage のメソッド実装を通じて環境に返されるユーザーコントロールの実装を提供する必要があり <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackage.GetPropertyPage%2A> ます。 (または、マネージコードの場合は <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackage.GetPropertyPage%2A> メソッドです)。

 これは省略可能ですが、オートメーションモデルを通じてこの新しいページにアクセスできるようにすることを強くお勧めします。 次の手順で行うことができます。

1. <xref:EnvDTE._DTE.Properties%2A>IDispatch によって派生したオブジェクトの実装を通じて、オブジェクトを拡張します。

2. メソッドの実装 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackage.GetAutomationObject%2A> (または、メソッドのマネージコード <xref:Microsoft.VisualStudio.Shell.Package.GetAutomationObject%2A> ) を IDispatch で派生したオブジェクトに返します。

3. オートメーションコンシューマーが <xref:EnvDTE._DTE.Properties%2A> カスタム **オプション** プロパティページでメソッドを呼び出すと、環境はメソッドを使用して、 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackage.GetAutomationObject%2A> カスタム **ツールオプション** ページのオートメーション実装を取得します。

4. 次に、VSPackage のオートメーションオブジェクトを使用して、 <xref:EnvDTE.Property> によって返される各を指定し <xref:EnvDTE._DTE.Properties%2A> ます。

   カスタム **ツールオプション** ページを実装するサンプルについては、「 [vssdk のサンプル](https://github.com/Microsoft/VSSDK-Extensibility-Samples)」を参照してください。

## <a name="see-also"></a>関連項目
- [プロジェクトオブジェクトの公開](../../extensibility/internals/exposing-project-objects.md)
