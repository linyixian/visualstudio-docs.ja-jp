---
title: IEnumDebugObjects |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- IEnumDebugObjects
helpviewer_keywords:
- IEnumDebugObjects interface
ms.assetid: 0950364c-6c8a-4b6c-ba37-c6aa359fa72c
caps.latest.revision: 10
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 1d01e6340be0cb710d9173850e66fc18d543347d
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "63434975"
---
# <a name="ienumdebugobjects"></a>IEnumDebugObjects
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

> [!IMPORTANT]
> Visual Studio 2015 での式エバリュエーターの実装には、この方法は非推奨とされます。 CLR 式エバリュエーターの実装方法の詳細についてを参照してください[CLR 式エバリュエーター](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators)と[マネージ式エバリュエーターのサンプル](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample)します。  
  
 このインターフェイスを実装するオブジェクトのコレクションを表します、 [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md)インターフェイス。  
  
## <a name="syntax"></a>構文  
  
```  
IEnumDebugObjects : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>実装についてのメモ  
 式エバリュエーターを実装するオブジェクトのセットを指定するには、このインターフェイスを実装する、 [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md)インターフェイス。 存在するための標準 COM 列挙型ではないことに注意してください、 [GetCount](../../../extensibility/debugger/reference/ienumdebugobjects-getcount.md)メソッド。  
  
## <a name="notes-for-callers"></a>呼び出し元のノート  
 [GetElements](../../../extensibility/debugger/reference/idebugarrayobject-getelements.md)このインターフェイスを返します。  
  
## <a name="methods-in-vtable-order"></a>Vtable 順序メソッド  
 このインターフェイスは、次のメソッドを実装します。  
  
|メソッド|説明|  
|------------|-----------------|  
|[次へ](../../../extensibility/debugger/reference/ienumdebugobjects-next.md)|次のセットを取得します。 [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md)列挙体からのオブジェクト。|  
|[Skip](../../../extensibility/debugger/reference/ienumdebugobjects-skip.md)|指定されたエントリ数をスキップします。|  
|[Reset](../../../extensibility/debugger/reference/ienumdebugobjects-reset.md)|最初のエントリを列挙型をリセットします。|  
|[Clone](../../../extensibility/debugger/reference/ienumdebugobjects-clone.md)|現在の列挙体のコピーを取得します。|  
|[GetCount](../../../extensibility/debugger/reference/ienumdebugobjects-getcount.md)|列挙内のエントリの数を取得します。|  
  
## <a name="remarks"></a>Remarks  
 このインターフェイスは、配列内のオブジェクトのセットを列挙するためにデバッグ エンジンを使用します。  
  
## <a name="requirements"></a>必要条件  
 ヘッダー: ee.h  
  
 名前空間: Microsoft.VisualStudio.Debugger.Interop  
  
 アセンブリ:Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>関連項目  
 [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md)   
 [GetElements](../../../extensibility/debugger/reference/idebugarrayobject-getelements.md)
