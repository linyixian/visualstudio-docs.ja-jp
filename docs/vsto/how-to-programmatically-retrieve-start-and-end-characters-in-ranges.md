---
title: プログラムを利用して範囲内の終了文字 & 開始する
ms.date: 02/02/2017
ms.topic: how-to
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- ranges, retrieving start and end characters
- end characters
- start characters
- documents [Office development in Visual Studio], retrieving ranges
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 485945f235a9161b6dc0584f7018c6f03c6024f5
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/02/2020
ms.locfileid: "85537658"
---
# <a name="how-to-programmatically-retrieve-start-and-end-characters-in-ranges"></a>方法: プログラムによって範囲内の開始文字と終了文字を取得する
  この例では、範囲の開始位置と終了位置の文字位置を取得する方法を示します。

 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]

## <a name="to-retrieve-start-and-end-characters-of-a-range-in-a-document-level-customization"></a>ドキュメント レベルのカスタマイズ内の範囲の先頭と末尾の文字を取得するには

1. <xref:Microsoft.Office.Interop.Word.Range.Start%2A> オブジェクトの <xref:Microsoft.Office.Interop.Word.Range.End%2A> プロパティおよび <xref:Microsoft.Office.Interop.Word.Range> プロパティの値を取得します。 次のコード例では、ドキュメントの 2 番目の文の開始位置と終了位置を取得します。 このコード例を使用するには、プロジェクトの `ThisDocument` クラスからコードを実行します。

     [!code-vb[Trin_VstcoreWordAutomation#25](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#25)]
     [!code-csharp[Trin_VstcoreWordAutomation#25](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#25)]

## <a name="to-retrieve-start-and-end-characters-of-a-range-by-using-a-vsto-add-in"></a>VSTO アドインを使用して範囲の開始文字と終了文字を取得するには

1. <xref:Microsoft.Office.Interop.Word.Range.Start%2A> オブジェクトの <xref:Microsoft.Office.Interop.Word.Range.End%2A> プロパティおよび <xref:Microsoft.Office.Interop.Word.Range> プロパティの値を取得します。 次のコード例では、アクティブなドキュメントの 2 番目の文の開始位置と終了位置を取得します。 このコード例を使用するには、プロジェクトの `ThisAddIn` クラスからコードを実行します。

     [!code-vb[Trin_VstcoreWordAutomationAddIn#25](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#25)]
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#25](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#25)]

## <a name="see-also"></a>関連項目
- [方法: プログラムによって文書内の範囲を定義および選択する](../vsto/how-to-programmatically-define-and-select-ranges-in-documents.md)
- [方法: プログラムによって文書内の範囲を拡張する](../vsto/how-to-programmatically-extend-ranges-in-documents.md)
- [方法: プログラムによって Word 文書の範囲をリセットする](../vsto/how-to-programmatically-reset-ranges-in-word-documents.md)
- [方法: プログラムによって文書内の範囲または選択項目を折りたたむ](../vsto/how-to-programmatically-collapse-ranges-or-selections-in-documents.md)
- [方法: 範囲を作成するときにプログラムによって段落記号を除外する](../vsto/how-to-programmatically-exclude-paragraph-marks-when-creating-ranges.md)
- [方法: プログラムによって文書内の文字数をカウントする](../vsto/how-to-programmatically-count-characters-in-documents.md)
