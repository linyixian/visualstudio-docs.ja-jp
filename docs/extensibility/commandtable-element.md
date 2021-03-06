---
title: CommandTable 要素 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- CommandTable
helpviewer_keywords:
- CommandTable element (VSCT XML schema)
- VSCT XML schema elements, CommandTable
ms.assetid: 15c38159-660a-4ef4-9643-aa6fcfca82a9
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: a362763d34335b9a18c4114a7c35b23f0efee020
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/02/2020
ms.locfileid: "80739646"
---
# <a name="commandtable-element"></a>CommandTable 要素
CommandTable は、 *. vsct* ファイルのルート要素です。 これは、VSPackage が IDE に提供するコマンドの実際のレイアウトと種類を定義するファイルです。 コマンドには、メニュー項目、メニュー、ツールバー、およびコンボボックスを含めることができます。 詳細については、「 [Visual Studio コマンドテーブル (vsct) ファイル](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)」を参照してください。

## <a name="syntax"></a>構文

```xml
<CommandTable xmlns="http://schemas.microsoft.com/VisualStudio/2005-10-18/CommandTable" xmlns:xs="http://www.w3.org/2001/XMLSchema" >
  <Extern>... </Extern>
  <Include>... </Include>
  <Define>... </Define>
  <Commands>... </Commands>
  <CommandPlacements>... </CommandPlacements>
  <VisibilityConstraints>... </VisibilityConstraints>
  <KeyBindings>... </KeyBindings>
  <UsedCommands... </UsedCommands>
  <Symbols>... </Symbols>
</CommandTable>
```

## <a name="attributes-and-elements"></a>属性と要素
 以降のセクションでは、属性、子要素、および親要素について説明します。

### <a name="attributes"></a>属性

| 属性 | 説明 |
|-----------| - |
| xmlns | 必須。 XML 名前空間:<br /><br /> `xmlns=http://schemas.microsoft.com/VisualStudio/2005-10-18/CommandTable`<br /><br /> xmlns: xs = " <http://www.w3.org/2001/XMLSchema> " |
| language | 省略可能。 Language 属性は、コマンドテーブル内のすべての要素の既定の言語を指定するために使用でき \<Strings> ます。  言語が指定されていない場合は、現在のプロセスの言語が使用されます。<br /><br /> language = "en-us" |

### <a name="child-elements"></a>子要素

|要素|説明|
|-------------|-----------------|
|[Extern 要素](../extensibility/extern-element.md)|省略可能。 コンパイラのプリプロセッサディレクティブを格納します。|
|[Include 要素](../extensibility/include-element.md)|省略可能。 コンパイルに含めるすべてのファイルへのパスを格納します。|
|[Define 要素](../extensibility/define-element.md)|省略可能。 名前と値を指定してシンボルを定義します。|
|[Commands 要素](../extensibility/commands-element.md)|省略可能。 他のすべての要素を含む VSPackage のすべてのコマンドを定義する親要素。|
|[CommandPlacements 要素](../extensibility/commandplacements-element.md)|省略可能。 コマンドバーのどこにコマンドを配置するかを定義します。|
|[VisibilityConstraints 要素](../extensibility/visibilityconstraints-element.md)|省略可能。 コマンドおよびツールバーを静的に表示するかどうかを決定します。|
|[キーバインド要素](../extensibility/keybindings-element.md)|省略可能。 コマンドのショートカットキーの組み合わせ (存在する場合) を指定します。|
|[Used Commands 要素](../extensibility/usedcommands-element.md)|省略可能。 VSPackage は、必要に応じて、他の Vspackage でサポートされていた独自のバージョンの機能を実装できます。|
|[Symbols 要素](https://www.microsoft.com/download/details.aspx?id=55984)|省略可能。 コンパイラのシンボルデータ (Guid、Id など) が含まれています。|

### <a name="parent-elements"></a>親要素

|要素|説明|
|-------------|-----------------|
|なし||

## <a name="see-also"></a>関連項目
- [Visual Studio コマンドテーブル (vsct) ファイル](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)
