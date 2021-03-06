---
title: Enumerator オブジェクトが必要です。Microsoft Docs
ms.date: 01/18/2017
ms.prod: visual-studio-windows
ms.technology: vs-javascript
ms.topic: error-reference
f1_keywords:
- VS.WebClient.Help.SCRIPT5015
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: dc6e32c1-a6e6-4e12-ac99-e3f65f91c8d7
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: ff61894ce808cd33876e876c596e791a3347ab72
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/02/2020
ms.locfileid: "85817594"
---
# <a name="enumerator-object-expected"></a>列挙子オブジェクトが必要です。
以外の型のオブジェクトに対して、 **enumerator** 、enumerator、列挙子、列挙子、または **enumerator** . prototype. プロトタイプのメソッドを呼び出そうとしまし `Enumerator` た。 この種類の呼び出しのオブジェクトは、型である必要があり `Enumerator` ます。 この規則を解除するコードの例を次に示します。  
  
```JavaScript  
var o = new Object;  
o.f = Enumerator.prototype.atEnd;  
o.f();  
```  
  
### <a name="to-correct-this-error"></a>このエラーを解決するには  
  
- 型のオブジェクトに対して**のみ、****列挙子**、プロトタイプ、列挙子、列挙**子、enumerator、また**は**enumerator** . prototype. moveNext メソッドを `Enumerator` 呼び出します。 オブジェクトがオブジェクトであるかどうかを確認するには `Enumerator` 、次のように使用します。  
  
    ```js
    if(x instanceof Enumerator)  
    ```  
  
## <a name="see-also"></a>関連項目  
 [Enumerator オブジェクト](../../javascript/reference/enumerator-object-javascript.md)