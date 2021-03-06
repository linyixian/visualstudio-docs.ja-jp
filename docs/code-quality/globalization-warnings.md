---
title: グローバリゼーションの警告
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- vs.codeanalysis.globalizationrules
helpviewer_keywords:
- warnings, globalization
- globalization warnings
- globalization [Visual Studio], warnings
- managed code analysis warnings, globalization warnings
ms.assetid: a8d12d41-14bf-4b43-af24-168312d7c390
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: cd215a8b5c8dfb5905117638883d94d09268ce3d
ms.sourcegitcommit: 5caad925ca0b5d136416144a279e984836d8f28c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2020
ms.locfileid: "89509849"
---
# <a name="globalization-warnings"></a>グローバリゼーションの警告
グローバリゼーションの警告は、国際対応のライブラリとアプリケーションをサポートします。

## <a name="in-this-section"></a>このセクションの内容

|ルール|説明|
|----------|-----------------|
|[CA1303:ローカライズされるパラメーターとしてリテラルを渡さない](../code-quality/ca1303.md)|外部から参照できるメソッドは、.NET コンストラクターまたはメソッドにパラメーターとして文字列リテラルを渡し、その文字列はローカライズ可能である必要があります。|
|[CA1304:CultureInfo を指定します](../code-quality/ca1304.md)|System.Globalization.CultureInfo パラメーターを受け入れるオーバーロードを持つメンバーを呼び出しているメソッドまたはコンストラクターが、CultureInfo パラメーターを使用するオーバーロードを呼び出していません。 CultureInfo オブジェクトまたは System.IFormatProvider オブジェクトが指定されない場合、オーバーロードされたメンバーから提示された既定値は、すべてのロケールに効果が及ばない可能性があります。|
|[CA1305:IFormatProvider を指定します](../code-quality/ca1305.md)|System.IFormatProvider パラメーターを受け入れるオーバーロードを持つメンバーを 1 つ以上呼び出しているメソッドまたはコンストラクターが、IFormatProvider パラメーターを使用するオーバーロードを呼び出していません。 System.Globalization.CultureInfo オブジェクトまたは IFormatProvider オブジェクトが指定されない場合、オーバーロードされたメンバーから提示された既定値は、すべてのロケールに効果が及ばない可能性があります。|
|[CA1306:データ型のロケールを設定します](../code-quality/ca1306.md)|ロケールによって、データに関するカルチャ固有の表示要素が決まります。たとえば、数値、通貨記号、並べ替え順序に使用する形式などです。 DataTable または DataSet を作成するときは、ロケールを明示的に設定する必要があります。|
|[CA1307:意味を明確にするための StringComparison の指定](../code-quality/ca1307.md)|文字列比較演算で、StringComparison パラメーターを設定しないメソッド オーバーロードが使用されています。|
|[CA1308:文字列を大文字に標準化します](../code-quality/ca1308.md)|文字列は大文字に正規化する必要があります。 小文字への変換時に 1 つの小さい文字グループをラウンド トリップさせることができません。|
|[CA1309:順序を示す StringComparison を使用します](../code-quality/ca1309.md)|非言語的な文字列比較演算で、StringComparison パラメーターが Ordinal または OrdinalIgnoreCase に設定されていません。 パラメーターを StringComparison.Ordinal または StringComparison.OrdinalIgnoreCase に明示的に設定することによって、多くの場合、コードの速度、正確さ、および信頼性が向上します。|
|[CA1310:正確な StringComparison の指定](../code-quality/ca1310.md)|文字列比較操作では、StringComparison パラメーターを設定せず、カルチャ固有の文字列比較を既定で使用するメソッドオーバーロードを使用します。|
|[CA2101: P/Invoke 文字列引数のマーシャリングを指定します。](../code-quality/ca2101.md)|プラットフォーム呼び出しメンバーは、部分的に信頼された呼び出し元を許可し、文字列パラメーターを持ち、文字列を明示的にマーシャリングしません。 これはセキュリティ上の脆弱性となる可能性があります。|
