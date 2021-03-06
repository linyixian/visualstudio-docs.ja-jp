---
title: '&lt;assemblyIdentity &gt; 要素 (ClickOnce アプリケーション) |Microsoft Docs'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- urn:schemas-microsoft-com:asm.v2#assemblyIdentity
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- <assemblyIdentity> element [ClickOnce application manifest]
ms.assetid: f48e9531-efac-4d11-8166-f63a5ece1ac5
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 7870fcf644103ec7f048a809e439cb962f63bd07
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/02/2020
ms.locfileid: "62900668"
---
# <a name="ltassemblyidentitygt-element-clickonce-application"></a>&lt;assemblyIdentity &gt; 要素 (ClickOnce アプリケーション)
デプロイにデプロイされたアプリケーションを識別 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] します。

## <a name="syntax"></a>Syntax

```xml

      <assemblyIdentity
   name
   version
   publicKeyToken
   processorArchitecture
   language
/>
```

## <a name="elements-and-attributes"></a>要素と属性
 `assemblyIdentity` 要素は必須です。 子要素は含まれず、次の属性があります。

|属性|説明|
|---------------|-----------------|
|`Name`|必須です。 アプリケーションの名前を識別します。<br /><br /> に `Name` 1 つまたは二重引用符などの特殊文字が含まれている場合、アプリケーションのアクティブ化に失敗する可能性があります。|
|`Version`|必須です。 アプリケーションのバージョン番号を次の形式で指定します。 `major.minor.build.revision`|
|`publicKeyToken`|省略可能。 `SHA-1`アプリケーションまたはアセンブリに署名するときに使用する公開キーのハッシュ値の最後の8バイトを表す16文字の16進数文字列を指定します。 カタログの署名に使用される公開キーは、2048ビット以上である必要があります。<br /><br /> アセンブリに署名することをお勧めしますが、省略可能ですが、この属性は必須です。 アセンブリが署名されていない場合は、自己署名アセンブリから値をコピーするか、すべてゼロの "ダミー" 値を使用する必要があります。|
|`processorArchitecture`|必須です。 プロセッサを指定します。 有効な値は、 `msil` 32 ビット windows の場合はすべてのプロセッサ、64ビット windows の場合は、 `x86` `IA64` `Itanium` Intel 64 ビット Itanium プロセッサの場合はです。|
|`language`|必須です。 アセンブリの2つの部分言語コード (たとえば、) を識別し `en-US` ます。 この要素は `asmv2` 名前空間にあります。 指定されていない場合、既定値は `neutral` です。|

## <a name="examples"></a>例

### <a name="description"></a>説明
 次のコード例は、 `assemblyIdentity` アプリケーションマニフェストの要素を示してい [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] ます。 このコード例は、 [ClickOnce アプリケーションマニフェスト](../deployment/clickonce-application-manifest.md)に用意されている大規模な例の一部です。

### <a name="code"></a>コード

```xml
<asmv1:assemblyIdentity
  name="My Application Deployment.exe"
  version="1.0.0.0"
  publicKeyToken="43cb1e8e7a352766"
  language="neutral"
  processorArchitecture="x86"
  type="win32" />
```

## <a name="see-also"></a>関連項目
- [ClickOnce アプリケーションマニフェスト](../deployment/clickonce-application-manifest.md)
- [\<assemblyIdentity> element](../deployment/assemblyidentity-element-clickonce-deployment.md)