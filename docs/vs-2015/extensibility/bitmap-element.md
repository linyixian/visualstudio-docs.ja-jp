---
title: Bitmap 要素 |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
helpviewer_keywords:
- VSCT XML schema elements, Bitmaps
- Bitmaps element (VSCT XML schema)
ms.assetid: edcd7891-f4e7-416d-809d-5e2eed9f17e4
caps.latest.revision: 9
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: fc1fb57c7ec43421b211b29cfd6ab97b24a1864c
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/02/2020
ms.locfileid: "68184743"
---
# <a name="bitmap-element"></a>Bitmap 要素
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

ビットマップを定義します。 ビットマップは、リソースまたはファイルから読み込まれます。  
  
## <a name="syntax"></a>構文  
  
```  
<Bitmap guid="guidImages" href="images\MyImage.bmp" usedList="bmp1, bmp2, bmp3" />  
```  
  
## <a name="attributes-and-elements"></a>属性および要素  
 以降のセクションでは、属性、子要素、および親要素について説明します。  
  
### <a name="attributes"></a>属性  
  
|属性|説明|  
|---------------|-----------------|  
|guid|必須です。 GUID/ID コマンド識別子の GUID。<br /><br /> ビットマップの guid 属性は、VSPackage またはその他のコマンドグループに関連付けられていません。  これはビットマップ定義に対して一意である必要があり、他の目的には使用できません。|  
|resID|GUID/ID コマンド識別子の ID。 ResID または href 属性のいずれかが必要です。<br /><br /> ResID 属性は、コマンドテーブルのマージ中に読み込まれるビットマップストリップを決定する整数リソース ID です。  コマンドテーブルを読み込むときに、リソース ID によって指定されたビットマップが、同じモジュールのリソースから読み込まれます。|  
|未使用のリスト|ResID 属性が存在する場合は必須です。 ビットマップストリップで使用可能なイメージを選択します。|  
|href|ビットマップへのパス。 ResID または href 属性のいずれかが必要です。<br /><br /> インクルードパスは、指定されたイメージファイルを検索します。これは、結果のバイナリに埋め込まれています。  コマンドテーブルのマージ中に、イメージがコピーされ、追加のリソース参照や読み込みは必要ありません。  使用リスト属性が存在しない場合は、ストリップ内のすべてのイメージを使用できます。 **注:**  イメージは、.bmp、.png、.gif を含む複数の形式のいずれかで指定できます。  以前のバージョンのコンパイラでは、部分的な透明度のアルファ情報を持つ32ビットビットマップイメージがサポートされていませんでした。 これらのバージョンの回避策は、.png 形式を使用することです。|  
|条件|省略可能。 「 [条件付き属性](../extensibility/vsct-xml-schema-conditional-attributes.md)」を参照してください。|  
  
### <a name="child-elements"></a>子要素  
 なし。  
  
### <a name="parent-elements"></a>親要素  
  
|要素|説明|  
|-------------|-----------------|  
|[Bitmaps 要素](../extensibility/bitmaps-element.md)|ビットマップ要素をグループ化します。|  
  
## <a name="example"></a>例  
  
```  
<Bitmap guid="guidWidgetIcons" href="WidgetToolbarIcons_32.bmp" />  
<Bitmap guid="guidWidgetIcons2" resID="IDBMP_WIDGETICONS"  
  usedList="1, 2, 3, 4"/>  
```  
  
## <a name="see-also"></a>参照  
 [Visual Studio Command Table (.Vsct) ファイル](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)
