---
title: 'CA2120: セキュリティで保護されたシリアル化コンストラクター |Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA2120
- SecureSerializationConstructors
helpviewer_keywords:
- SecureSerializationConstructors
- CA2120
ms.assetid: e9989da1-55a0-43f8-9aa9-da86afae3b41
caps.latest.revision: 18
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: 10cfa03adb74871fb42a6e1c2ce4ab4ba6bcae75
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/02/2020
ms.locfileid: "85544340"
---
# <a name="ca2120-secure-serialization-constructors"></a>CA2120:シリアル化コンストラクターをセキュリティで保護します
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|Item|値|
|-|-|
|TypeName|SecureSerializationConstructors|
|CheckId|CA2120|
|カテゴリ|Microsoft.Security|
|互換性に影響する変更点|あり|

## <a name="cause"></a>原因
 この型はインターフェイスを実装し <xref:System.Runtime.Serialization.ISerializable?displayProperty=fullName> 、はデリゲートまたはインターフェイスではなく、部分的に信頼された呼び出し元を許可するアセンブリで宣言されます。 型には、 <xref:System.Runtime.Serialization.SerializationInfo?displayProperty=fullName> オブジェクトと <xref:System.Runtime.Serialization.StreamingContext?displayProperty=fullName> オブジェクト (シリアル化コンストラクターのシグネチャ) を受け取るコンストラクターがあります。 このコンストラクターはセキュリティチェックによって保護されていませんが、型の1つ以上の標準コンストラクターがセキュリティで保護されています。

## <a name="rule-description"></a>ルールの説明
 このルールは、カスタムシリアル化をサポートする型に関連しています。 型は、インターフェイスを実装する場合、カスタムシリアル化をサポート <xref:System.Runtime.Serialization.ISerializable?displayProperty=fullName> します。 シリアル化コンストラクターは必須であり、メソッドを使用してシリアル化されたオブジェクトを逆シリアル化または再作成するために使用され <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A?displayProperty=fullName> ます。 シリアル化コンストラクターによってオブジェクトが割り当てられ、初期化されるため、通常のコンストラクターに存在するセキュリティチェックもシリアル化コンストラクターに存在する必要があります。 この規則に違反する場合、インスタンスを作成できなかった呼び出し元は、シリアル化コンストラクターを使用してこれを行うことができます。

## <a name="how-to-fix-violations"></a>違反の修正方法
 この規則違反を修正するには、他のコンストラクターを保護するものと同じセキュリティ要求を使用してシリアル化コンストラクターを保護します。

## <a name="when-to-suppress-warnings"></a>警告を抑制する状況
 規則違反を抑制しないでください。

## <a name="example"></a>例
 次の例は、規則に違反する型を示しています。

 [!code-csharp[FxCop.Security.SerialCtors#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Security.SerialCtors/cs/FxCop.Security.SerialCtors.cs#1)]

## <a name="related-rules"></a>関連規則
 [CA2229:シリアル化コンストラクターを実装します](../code-quality/ca2229-implement-serialization-constructors.md)

 [CA2237:ISerializable 型を SerializableAttribute に設定します](../code-quality/ca2237-mark-iserializable-types-with-serializableattribute.md)

## <a name="see-also"></a>参照
 <xref:System.Runtime.Serialization.ISerializable?displayProperty=fullName> <xref:System.Runtime.Serialization.SerializationInfo?displayProperty=fullName>
 <xref:System.Runtime.Serialization.StreamingContext?displayProperty=fullName>
