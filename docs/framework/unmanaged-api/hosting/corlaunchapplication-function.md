---
title: CorLaunchApplication 関数
ms.date: 03/30/2017
api_name:
- CorLaunchApplication
api_location:
- mscoree.dll
- clr.dll
api_type:
- COM
f1_keywords:
- CorLaunchApplication
helpviewer_keywords:
- CorLaunchApplication function [.NET Framework hosting]
ms.assetid: 71f362a9-8fe2-47ce-9302-05a645cf3d7d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4c997ab107ba3ceb7773bc9235b9c9dcd4d97df8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61985791"
---
# <a name="corlaunchapplication-function"></a><span data-ttu-id="6c092-102">CorLaunchApplication 関数</span><span class="sxs-lookup"><span data-stu-id="6c092-102">CorLaunchApplication Function</span></span>
<span data-ttu-id="6c092-103">指定したネットワーク パスのアプリケーションを、指定したマニフェストとその他のアプリケーション データを使用して起動します。</span><span class="sxs-lookup"><span data-stu-id="6c092-103">Starts the application at the specified network path, using the specified manifests and other application data.</span></span>  
  
 <span data-ttu-id="6c092-104">この関数は、[!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)] では非推奨とされました。</span><span class="sxs-lookup"><span data-stu-id="6c092-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6c092-105">構文</span><span class="sxs-lookup"><span data-stu-id="6c092-105">Syntax</span></span>  
  
```  
HRESULT CorLaunchApplication (  
    [in]  HOST_TYPE                dwClickOnceHost,  
    [in]  LPCWSTR                  pwzAppFullName,  
    [in]  DWORD                    dwManifestPaths,  
    [in]  LPCWSTR                 *ppwzManifestPaths,  
    [in]  DWORD                    dwActivationData,  
    [in]  LPCWSTR                 *ppwzActivationData,  
    [out] LPPROCESS_INFORMATION    lpProcessInformation  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6c092-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="6c092-106">Parameters</span></span>  
 `dwClickOnceHost`  
 <span data-ttu-id="6c092-107">[in]値、 [HOST_TYPE](../../../../docs/framework/unmanaged-api/hosting/host-type-enumeration.md)が起動して、アプリケーション ホストの種類を指定する列挙体。</span><span class="sxs-lookup"><span data-stu-id="6c092-107">[in] A value of the [HOST_TYPE](../../../../docs/framework/unmanaged-api/hosting/host-type-enumeration.md) enumeration that specifies the type of host that is launching the application.</span></span>  
  
 `pwzAppFullName`  
 <span data-ttu-id="6c092-108">[in]起動しているアプリケーションの完全名。</span><span class="sxs-lookup"><span data-stu-id="6c092-108">[in] The full name of the application that is being launched.</span></span>  
  
 `dwManifestPaths`  
 <span data-ttu-id="6c092-109">[in]アプリケーションのマニフェストのパスの数。</span><span class="sxs-lookup"><span data-stu-id="6c092-109">[in] The number of manifest paths for the application.</span></span>  
  
 `ppwzManifestPaths`  
 <span data-ttu-id="6c092-110">[in]起動しているアプリケーションのマニフェストへのパスを指定の文字列の配列。</span><span class="sxs-lookup"><span data-stu-id="6c092-110">[in] An array of strings, each of which specifies a path to a manifest for the application that is being launched.</span></span>  
  
 `dwActivationData`  
 <span data-ttu-id="6c092-111">[in]起動しているアプリケーションのデータ項目をアクティブ化の数。</span><span class="sxs-lookup"><span data-stu-id="6c092-111">[in] The number of activation data items for the application that is being launched.</span></span>  
  
 `ppwzActivationData`  
 <span data-ttu-id="6c092-112">[in]起動しているアプリケーションのライセンス認証データ項目は、それぞれの文字列の配列。</span><span class="sxs-lookup"><span data-stu-id="6c092-112">[in] An array of strings, each of which is an activation data item for the application that is being launched.</span></span>  
  
 `lpProcessInformation`  
 <span data-ttu-id="6c092-113">[out]これで、アプリケーションが読み込まれたプロセスに関する情報へのポインター。</span><span class="sxs-lookup"><span data-stu-id="6c092-113">[out] A pointer to information about the process in which the application has been loaded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6c092-114">必要条件</span><span class="sxs-lookup"><span data-stu-id="6c092-114">Requirements</span></span>  
 <span data-ttu-id="6c092-115">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6c092-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6c092-116">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="6c092-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6c092-117">**ライブラリ:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="6c092-117">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6c092-118">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6c092-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6c092-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="6c092-119">See also</span></span>

- [<span data-ttu-id="6c092-120">非推奨の CLR ホスト関数</span><span class="sxs-lookup"><span data-stu-id="6c092-120">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
