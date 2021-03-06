---
title: 従来の言語サービスでのコードのコメント化 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- comments, supporting in language services [managed package framework]
- language services [managed package framework], commenting code
ms.assetid: 9600d6f0-e2b6-4fe0-b935-fb32affb97a4
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 5450199fde29f581dafdf9b2884c88ef26ea4ce7
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/02/2020
ms.locfileid: "80709436"
---
# <a name="comment-code-in-a-legacy-language-service"></a>従来の言語サービスでのコメントコード
プログラミング言語は、通常、コードに注釈を付けたり、コメントを付けたりするための手段を提供します。 コメントは、コードに関する追加情報を提供するテキストのセクションですが、コンパイル時または解釈時には無視されます。

 Managed package framework (MPF) クラスは、選択したテキストのコメント化とコメント解除のサポートを提供します。

## <a name="comment-styles"></a>コメントのスタイル
コメントには、次の2つの一般的なスタイルがあります。

1. 行コメント。コメントは1行にあります。

2. コメントをブロックします。コメントには複数の行を含めることができます。

行のコメントには、通常、開始文字 (または文字) がありますが、ブロックコメントには開始文字と終了文字の両方があります。 たとえば、C# では、行コメントはで始まり、 `//` ブロックコメントはで始まり、で `/*` 終わり `*/` ます。

ユーザーが [詳細の**編集**] メニューからコマンド**コメントを選択**すると、  >  **Advanced**コマンドはクラスのメソッドにルーティングされ <xref:Microsoft.VisualStudio.Package.Source.CommentSpan%2A> <xref:Microsoft.VisualStudio.Package.Source> ます。 ユーザーがコマンドを選択して **選択**を解除すると、コマンドはメソッドにルーティングされ <xref:Microsoft.VisualStudio.Package.Source.UncommentSpan%2A> ます。

## <a name="support-code-comments"></a>サポートコードのコメント
 の名前付きパラメーターを使用して、言語サービスでコードのコメントをサポートすることができ `EnableCommenting` <xref:Microsoft.VisualStudio.Shell.ProvideLanguageServiceAttribute> ます。 これにより <xref:Microsoft.VisualStudio.Package.LanguagePreferences.EnableCommenting%2A> 、クラスのプロパティが設定され <xref:Microsoft.VisualStudio.Package.LanguagePreferences> ます。 言語サービス機能の設定の詳細については、「 [従来の言語サービスを登録する](../../extensibility/internals/registering-a-legacy-language-service1.md)」を参照してください。

 また、メソッドをオーバーライドし <xref:Microsoft.VisualStudio.Package.Source.GetCommentFormat%2A> <xref:Microsoft.VisualStudio.Package.CommentInfo> て、言語のコメント文字を含む構造体を返す必要があります。 C# スタイルの行コメント文字が既定値です。

### <a name="example"></a>例
 メソッドの実装例を次に示し <xref:Microsoft.VisualStudio.Package.Source.GetCommentFormat%2A> ます。

```csharp
using Microsoft.VisualStudio.Package;

namespace MyLanguagePackage
{
    class MySource : Source
    {
        public override CommentInfo GetCommentFormat() {
            CommentInfo info = new CommentInfo();
            info.LineStart       = "//";
            info.BlockStart      = "/*";
            info.BlockEnd        = "*/";
            info.UseLineComments = true;
            return info;
        }
    }
}
```

## <a name="see-also"></a>関連項目
- [従来の言語サービス機能](../../extensibility/internals/legacy-language-service-features1.md)
- [従来の言語サービスを登録する](../../extensibility/internals/registering-a-legacy-language-service1.md)
