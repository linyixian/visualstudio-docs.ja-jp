---
title: プロパティを削除できません
ms.date: 11/04/2016
ms.topic: error-reference
ms.assetid: 55873f74-7834-4ec1-8815-eeeb65618d87
author: ghogen
ms.author: ghogen
manager: jillfra
ms.workload:
- data-storage
ms.openlocfilehash: 63e99bf7b247856815fd3e8de0f4932fed4881dc
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/02/2020
ms.locfileid: "85535292"
---
# <a name="the-property-property-name-cannot-be-deleted"></a>プロパティ \<property name> を削除できません

プロパティは、 \<property name> との間の継承の**識別子プロパティ**として設定されているため、削除できません \<class name>\<class name>

選択されたプロパティは、エラー メッセージに示されているクラス間の継承に対する**識別子のプロパティ**として設定されています。 プロパティがデータ クラス間の継承構成に関与している場合、そのプロパティを削除することはできません。

**識別子のプロパティ**をデータ クラスの別のプロパティに設定して、目的のプロパティが正常に削除されるようにしてください。

## <a name="to-correct-this-error"></a>このエラーを解決するには

1. **O/R デザイナー**で、エラーメッセージに示されているデータクラスを接続する継承線を選択します。

2. **識別子** プロパティを別のプロパティに設定します。

3. プロパティの削除を再試行します。

## <a name="see-also"></a>関連項目

- [Visual Studio の LINQ to SQL ツール](../data-tools/linq-to-sql-tools-in-visual-studio2.md)