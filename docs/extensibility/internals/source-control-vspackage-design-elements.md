---
title: ソース管理 VSPackage の設計要素 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- source control packages, design elements
ms.assetid: edd3f2ff-ca32-4465-8ace-4330493b67bb
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: b5e94829f781c058d9b0ea56cdec6c03c71ffe0c
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/02/2020
ms.locfileid: "80705010"
---
# <a name="source-control-vspackage-design-elements"></a>ソース管理 VSPackage のデザイン要素
このセクションのトピックでは、詳細な統合のためにソース管理 VSPackage が実装する必要がある構造の概要を示します。 また、ソース管理 VSPackage が実装できるインターフェイスとサービス、およびソース管理 VSPackage がソース管理 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] モデルと機能をサポートするために他のコンポーネントから使用できるインターフェイスとサービスについても示します。

## <a name="in-this-section"></a>このセクションの内容
- [VSPackage 構造](../../extensibility/internals/vspackage-structure-source-control-vspackage.md)

 ソース管理 VSPackage の構造を定義します。

- [関連サービスとインターフェイス](../../extensibility/internals/related-services-and-interfaces-source-control-vspackage.md)

 ソース管理パッケージに関連するインターフェイスおよびサービスを一覧表示します。

- [提供されるサービス](../../extensibility/internals/services-provided-source-control-vspackage.md)

 ソース管理 VSPackage によって提供されるソース管理サービスについて説明します。

## <a name="related-sections"></a>関連項目
- [ソース管理 VSPackage の作成](../../extensibility/internals/creating-a-source-control-vspackage.md)

 ソース管理機能を提供するだけでなく、ソース管理 UI のカスタマイズに使用できるソース管理 VSPackage を作成する方法について説明し [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] ます。
