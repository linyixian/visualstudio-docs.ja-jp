---
title: DataContext メソッドを sprocs および関数にマップする
ms.custom: SEO-VS-2020
ms.date: 11/04/2016
ms.topic: how-to
ms.assetid: e7ca32f1-50b3-48af-ad92-ceafd749296a
author: ghogen
ms.author: ghogen
manager: jillfra
ms.workload:
- data-storage
ms.openlocfilehash: e6926631cfd9d04992d92553a346348ea18af847
ms.sourcegitcommit: 4ae5e9817ad13edd05425febb322b5be6d3c3425
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/11/2020
ms.locfileid: "90038336"
---
# <a name="how-to-create-datacontext-methods-mapped-to-stored-procedures-and-functions-or-designer"></a>方法: ストアド プロシージャや関数にマップされる DataContext メソッドを作成する (O/R デザイナー)

ストアドプロシージャおよび関数をメソッドとして **O/R デザイナー** に追加でき <xref:System.Data.Linq.DataContext> ます。 メソッドを呼び出して必要なパラメーターを渡すと、データベースでストアド プロシージャまたは関数が実行され、<xref:System.Data.Linq.DataContext> メソッドの戻り値の型のデータが返されます。 メソッドの詳細について <xref:System.Data.Linq.DataContext> は、「 [DataContext メソッド (O/R デザイナー)](../data-tools/datacontext-methods-o-r-designer.md)」を参照してください。

> [!NOTE]
> また、ストアドプロシージャを使用すると、 [!INCLUDE[vbtecdlinq](../data-tools/includes/vbtecdlinq_md.md)] エンティティクラスからデータベースに変更が保存されるときに、挿入、更新、および削除を実行する既定の実行時の動作をオーバーライドすることもできます。 詳細については、「[方法:更新、挿入、および削除を実行するストアド プロシージャを割り当てる (O/R デザイナー)](../data-tools/how-to-assign-stored-procedures-to-perform-updates-inserts-and-deletes-o-r-designer.md)」を参照してください。

## <a name="create-datacontext-methods"></a>DataContext メソッドの作成

<xref:System.Data.Linq.DataContext>ストアドプロシージャまたは関数を<strong>サーバーエクスプローラーまたは * * データベースエクスプローラー</strong>から**O/R デザイナー**にドラッグすることで、メソッドを作成できます。

> [!NOTE]
> 生成されたメソッドの戻り値の型は、 <xref:System.Data.Linq.DataContext> **O/R デザイナー**でストアドプロシージャまたは関数をドロップする場所によって異なります。 既存のエンティティ クラスに項目を直接ドロップすると、そのエンティティ クラスを戻り値の型とする <xref:System.Data.Linq.DataContext> メソッドが作成されます。 **O/R デザイナー**の空の領域に項目をドロップすると、 <xref:System.Data.Linq.DataContext> 自動的に生成された型を返すメソッドが作成されます。 <xref:System.Data.Linq.DataContext> メソッドを **[メソッド]** ペインに追加した後に、その戻り値の型を変更できます。 <xref:System.Data.Linq.DataContext> メソッドの戻り値の型を確認または変更するには、**[プロパティ]** ウィンドウでメソッドを選択し、**[戻り値の型]** プロパティを調べます。 詳細については、「 [方法: DataContext メソッドの戻り値の型を変更する (O/R デザイナー)](../data-tools/how-to-change-the-return-type-of-a-datacontext-method-o-r-designer.md)」を参照してください。

[!INCLUDE[note_settings_general](../data-tools/includes/note_settings_general_md.md)]

### <a name="to-create-datacontext-methods-that-return-automatically-generated-types"></a>自動生成された型を返す DataContext メソッドを作成するには

1. **サーバーエクスプローラー**または**データベースエクスプローラー**で、作業しているデータベースの [**ストアドプロシージャ**] ノードを展開します。

2. 目的のストアドプロシージャを見つけて、 **O/R デザイナー**の空の領域にドラッグします。

     自動生成された戻り値の型を使用して <xref:System.Data.Linq.DataContext> メソッドが作成され、**[メソッド]** ペインに表示されます。

### <a name="to-create-datacontext-methods-that-have-the-return-type-of-an-entity-class"></a>エンティティ クラスを戻り値の型とする DataContext メソッドを作成するには

1. **サーバーエクスプローラー**または**データベースエクスプローラー**で、作業しているデータベースの [**ストアドプロシージャ**] ノードを展開します。

2. 目的のストアドプロシージャを見つけて、 **O/R デザイナー**の既存のエンティティクラスにドラッグします。

     選択したエンティティ クラスを戻り値の型として <xref:System.Data.Linq.DataContext> メソッドが作成され、**[メソッド]** ペインに表示されます。

> [!NOTE]
> 既存のメソッドの戻り値の型を変更する方法の詳細については <xref:System.Data.Linq.DataContext> 、「 [方法: DataContext メソッドの戻り値の型を変更する (O/R デザイナー)](../data-tools/how-to-change-the-return-type-of-a-datacontext-method-o-r-designer.md)」を参照してください。

## <a name="see-also"></a>参照

- [Visual Studio の LINQ to SQL ツール](../data-tools/linq-to-sql-tools-in-visual-studio2.md)
- [DataContext メソッド (O/R デザイナー)](../data-tools/datacontext-methods-o-r-designer.md)
- [チュートリアル: LINQ to SQL クラスの作成](how-to-create-linq-to-sql-classes-mapped-to-tables-and-views-o-r-designer.md)
- [LINQ to SQL](/dotnet/framework/data/adonet/sql/linq/index)
- [Visual Basic における LINQ の概要](/dotnet/visual-basic/programming-guide/language-features/linq/introduction-to-linq)
- [C# での LINQ](/dotnet/csharp/linq/linq-in-csharp)
