---
title: 'CA1045: 型を参照渡しで渡すことはできません |Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1045
- DoNotPassTypesByReference
helpviewer_keywords:
- CA1045
- DoNotPassTypesByReference
ms.assetid: bcc3900a-e092-4bb8-896f-cb83f6289968
caps.latest.revision: 20
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: dad2f90a51a4247a4c111ef51e85a28ba1a118ce
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/02/2020
ms.locfileid: "85548474"
---
# <a name="ca1045-do-not-pass-types-by-reference"></a>CA1045:型を参照によって渡しません
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|Item|値|
|-|-|
|TypeName|DoNotPassTypesByReference|
|CheckId|CA1045|
|カテゴリ|Microsoft Design|
|互換性に影響する変更点|あり|

## <a name="cause"></a>原因
 パブリック型のパブリックメソッドまたはプロテクトメソッドには、 `ref` プリミティブ型、参照型、または組み込み型の1つではない値型を受け取るパラメーターがあります。

## <a name="rule-description"></a>ルールの説明
 型を参照渡しで渡す ( `out` またはを使用) には `ref` 、ポインターの使用経験、値型と参照型の違いの理解、および複数の戻り値を持つメソッドの処理が必要です。 また、 `out` パラメーターとパラメーターの違い `ref` は広く認識されていません。

 参照型が "参照渡し" されると、メソッドは、パラメーターを使用してオブジェクトの別のインスタンスを返すようにします。 参照型を参照渡しで渡すことは、double ポインター、ポインターへのポインター、または二重の間接参照とも呼ばれます。既定の呼び出し規約 ("値渡し") を使用すると、参照型を受け取るパラメーターは既にオブジェクトへのポインターを受け取ります。 ポインターが指すオブジェクトではなく、値によって渡されます。 値渡しでは、メソッドが参照型の新しいインスタンスを指すようにポインターを変更することはできませんが、ポイントするオブジェクトの内容を変更することができます。 ほとんどのアプリケーションでは十分であり、必要な動作が得られます。

 メソッドが別のインスタンスを返す必要がある場合は、メソッドの戻り値を使用してこれを実行します。 文字列を <xref:System.String?displayProperty=fullName> 操作し、文字列の新しいインスタンスを返すさまざまなメソッドについては、クラスを参照してください。 このモデルを使用すると、元のオブジェクトが保持されているかどうかを判断するために呼び出し元に残されます。

 戻り値は一般的であり、頻繁に使用されますが、パラメーターとパラメーターを正しく適用するには、 `out` `ref` 中間の設計とコーディングのスキルが必要です。 一般ユーザー向けに設計されたライブラリアーキテクト `out` は、ユーザーがまたはパラメーターをマスターに使用することを想定しないでください `ref` 。

> [!NOTE]
> 大規模な構造のパラメーターを使用する場合、これらの構造をコピーするために必要な追加リソースによって、値渡しによってパフォーマンスが低下する可能性があります。 このような場合 `ref` は、またはパラメーターを使用することを検討してください `out` 。

## <a name="how-to-fix-violations"></a>違反の修正方法
 値の型に起因するこの規則違反を修正するには、メソッドが戻り値としてオブジェクトを返すようにします。 メソッドが複数の値を返す必要がある場合は、値を保持するオブジェクトの1つのインスタンスを返すように再設計します。

 参照型に起因するこの規則違反を修正するには、必要な動作が参照の新しいインスタンスを返すことを確認します。 この値がの場合、メソッドは戻り値を使用してこれを実行する必要があります。

## <a name="when-to-suppress-warnings"></a>警告を抑制する状況
 このルールからの警告を抑制するのは安全です。ただし、この設計ではユーザビリティの問題が発生する可能性があります。

## <a name="example"></a>例
 次のライブラリは、ユーザーのフィードバックへの応答を生成するクラスの2つの実装を示しています。 最初の実装 () では、 `BadRefAndOut` ライブラリユーザーが3つの戻り値を管理するように強制します。 2番目の実装 () は、 `RedesignedRefAndOut` `ReplyData` データを1つの単位として管理するコンテナークラス () のインスタンスを返すことによって、ユーザーエクスペリエンスを簡略化します。

 [!code-csharp[FxCop.Design.NoRefOrOut#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Design.NoRefOrOut/cs/FxCop.Design.NoRefOrOut.cs#1)]

## <a name="example"></a>例
 次のアプリケーションは、ユーザーのエクスペリエンスを示しています。 再設計されたライブラリ ( `UseTheSimplifiedClass` メソッド) の呼び出しはより簡単で、メソッドによって返される情報は簡単に管理できます。 2つのメソッドからの出力は同じです。

 [!code-csharp[FxCop.Design.TestNoRefOrOut#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Design.TestNoRefOrOut/cs/FxCop.Design.TestNoRefOrOut.cs#1)]

## <a name="example"></a>例
 次のライブラリ例は、 `ref` 参照型のパラメーターの使用方法を示しています。また、この機能を実装するためのより良い方法を示しています。

 [!code-csharp[FxCop.Design.RefByRefNo#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Design.RefByRefNo/cs/FxCop.Design.RefByRefNo.cs#1)]

## <a name="example"></a>例
 次のアプリケーションは、ライブラリ内の各メソッドを呼び出して、動作を示します。

 [!code-csharp[FxCop.Design.TestRefByRefNo#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Design.TestRefByRefNo/cs/FxCop.Design.TestRefByRefNo.cs#1)]

 この例を実行すると、次の出力が生成されます。

 **ポインターの変更 (値渡し):** 
**12345** 
**12345** 
**ポインターの変更-参照渡し:** 
**12345** 
**12345 abcde...z** 
**戻り値で渡す:** 
**12345 abcde...z**
## <a name="related-rules"></a>関連規則
 [CA1021:out パラメーターを使用しません](../code-quality/ca1021-avoid-out-parameters.md)
