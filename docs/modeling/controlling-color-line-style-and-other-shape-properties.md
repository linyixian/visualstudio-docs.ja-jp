---
title: 色、線のスタイル、およびその他のシェイプのプロパティの管理
ms.date: 11/04/2016
ms.topic: how-to
author: JoshuaPartlow
ms.author: joshuapa
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: eee36ad0361f40f23c29c5672b155fc5e5405dbe
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/02/2020
ms.locfileid: "85546680"
---
# <a name="controlling-color-line-style-and-other-shape-properties"></a>色、線のスタイル、およびその他のシェイプのプロパティの管理

色など、一部の図形プロパティは "公開" できます。 つまり、プロパティを図形のドメインプロパティにリンクさせることができます。 他のユーザーは直接制御する必要があります。

## <a name="exposing-a-property"></a>プロパティの公開
 Color などの一部の図形プロパティは、ドメインプロパティの値にリンクできます。

 DSL 定義で、シェイプ、コネクタ、または図クラスを選択します。 右クリックして表示されるメニューで、[ **公開の追加**] を選択し、[塗りつぶしの色] など、目的のプロパティを選択します。

 これで、図形には、プログラムコードまたはユーザーとして設定できるドメインプロパティが設定されました。

## <a name="dynamically-updating-an-exposed-property"></a>公開されたプロパティの動的な更新
 通常は、公開されているプロパティを別のプロパティに依存させます。 たとえば、特定のドメインプロパティが0未満の場合に、図形が赤になるようにすることができます。 この依存関係を作成するには、 [ルール](../modeling/rules-propagate-changes-within-the-model.md)を作成します。 次に例を示します。

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using Microsoft.VisualStudio.Modeling;
using Microsoft.VisualStudio.Modeling.Diagrams;
namespace ExampleNamespace
{
 // Attribute associates the rule with class:
 [RuleOn(typeof(CarShape), FireTime = TimeToFire.TopLevelCommit)]
 // The rule is a class derived from one of the abstract rules:
 class CarShapeAddRule : AddRule
 {
 // Override the abstract method:
 public override void ElementAdded(ElementAddedEventArgs e)
 {
 base.ElementAdded(e);
 CarShape shape = e.ModelElement as CarShape;
 Store store = shape.Store;
 // Ignore this call if we're currently loading a model:
 if (store.TransactionManager.CurrentTransaction.IsSerializing)
  return;
 Car car = shape.ModelElement as Car;
 // Code here propagates change as required - for example:
 shape.FillColor = car.Somebool ? System.Drawing.Color.Red : System.Drawing.Color.Green;
 }
}
 // The rule must be registered:
 public partial class ExampleDomainModel
 {
 protected override Type[] GetCustomDomainModelTypes()
 {
  List<Type> types = new List<Type>(base.GetCustomDomainModelTypes());
  types.Add(typeof(CarShapeAddRule));
  // If you add more rules, list them here.
  return types.ToArray();
 }
 }
}
```