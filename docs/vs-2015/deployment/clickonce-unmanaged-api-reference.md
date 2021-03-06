---
title: ClickOnce アンマネージ API リファレンス |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-deployment
ms.topic: reference
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- LaunchApplication [ClickOnce unmanaged]
- ClickOnce, unmanaged APIs
- CleanOnlineAppCache [ClickOnce unmanaged]
- CleanOnlineAppCacheW interface [ClickOnce unmanaged]
- GetDeploymentDataFromManifest [ClickOnce unmanaged]
ms.assetid: ec002138-4054-456d-bcc1-79ac2f4a4fd7
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 714d7b18995bf1ad51b07e02227e440879f73c9e
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/02/2020
ms.locfileid: "68192306"
---
# <a name="clickonce-unmanaged-api-reference"></a>ClickOnce アンマネージ API リファレンス
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

[!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)] dfshim.dll からのアンマネージパブリック Api。  
  
## <a name="cleanonlineappcache"></a>Cleanオンライン Appcache  
 すべてのオンラインアプリケーションをアプリケーションキャッシュから消去またはアンインストール [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)] します。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は S_OK を返します。それ以外の場合は、エラーを表す HRESULT を返します。 マネージ例外が発生した場合、は 0x80020009 (DISP_E_EXCEPTION) を返します。  
  
### <a name="remarks"></a>注釈  
 まだ実行されていない場合は、Cleanオンライン Appcache を呼び出すとサービスが開始され [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)] ます。  
  
## <a name="getdeploymentdatafrommanifest"></a>GetDeploymentDataFromManifest  
 マニフェストおよびアクティベーション URL から配置情報を取得します。  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|Type|  
|---------------|-----------------|----------|  
|`pcwzActivationUrl`|`ActivationURL` へのポインター。|LPCWSTR|  
|`pcwzPathToDeploymentManifest`|`PathToDeploymentManifest` へのポインター。|LPCWSTR|  
|`pwzApplicationIdentity`|返される完全なアプリケーション id を指定する NULL で終わる文字列を受け取るバッファーへのポインター。|LPWSTR|  
|`pdwIdentityBufferLength`|バッファーの長さ `pwzApplicationIdentity` (WCHARs) である DWORD へのポインター。 これには、NULL 終端文字のスペースが含まれます。|LPDWORD|  
|`pwzProcessorArchitecture`|マニフェストからアプリケーション配置のプロセッサアーキテクチャを指定する NULL で終わる文字列を受け取るバッファーへのポインター。|LPWSTR|  
|`pdwArchitectureBufferLength`|バッファーの長さ `pwzProcessorArchitecture` (WCHARs) である DWORD へのポインター。|LPDWORD|  
|`pwzApplicationManifestCodebase`|マニフェストからアプリケーションマニフェストのコードベースを指定する NULL で終わる文字列を受け取るバッファーへのポインター。|LPWSTR|  
|`pdwCodebaseBufferLength`|バッファーの長さ `pwzApplicationManifestCodebase` (WCHARs) である DWORD へのポインター。|LPDWORD|  
|`pwzDeploymentProvider`|マニフェストから配置プロバイダーを指定する NULL で終わる文字列を受け取るバッファーへのポインター (存在する場合)。 それ以外の場合は、空の文字列が返されます。|LPWSTR|  
|`pdwProviderBufferLength`|の長さである DWORD へのポインター `pwzProviderBufferLength` 。|LPDWORD|  
  
### <a name="return-value"></a>戻り値  
 成功した場合は S_OK を返します。それ以外の場合は、エラーを表す HRESULT を返します。 バッファーが小さすぎる場合は、HRESULTFROMWIN32 (ERROR_INSUFFICIENT_BUFFER) を返します。  
  
### <a name="remarks"></a>注釈  
 ポインターを null にすることはできません。 `pcwzActivationUrl` およびを空にすることはでき `pcwzPathToDeploymentManifest` ません。  
  
 アクティベーション URL をクリーンアップするのは、呼び出し元の責任です。 たとえば、必要に応じてエスケープ文字を追加したり、クエリ文字列を削除したりできます。  
  
 入力の長さを制限するのは、呼び出し元の責任です。 たとえば、URL の最大長は2KB です。  
  
## <a name="launchapplication"></a>LaunchApplication  
 デプロイ URL を使用してアプリケーションを起動またはインストールします。  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|Type|  
|---------------|-----------------|----------|  
|`deploymentUrl`|配置マニフェストの URL を格納している NULL で終わる文字列へのポインター。|LPCWSTR|  
|`data`|将来使用するために予約されています。 NULL にする必要があります|LPVOID|  
|`flags`|将来使用するために予約されています。 0 を指定する必要があります。|DWORD|  
  
### <a name="return-value"></a>戻り値  
 成功した場合は S_OK を返します。それ以外の場合は、エラーを表す HRESULT を返します。 マネージ例外が発生した場合、は 0x80020009 (DISP_E_EXCEPTION) を返します。  
  
## <a name="see-also"></a>参照  
 <xref:System.Deployment.Application.DeploymentServiceCom.CleanOnlineAppCache%2A>
