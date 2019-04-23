---
title: ICorRuntimeHost::UnloadDomain メソッド
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.UnloadDomain
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::UnloadDomain
helpviewer_keywords:
- ICorRuntimeHost::UnloadDomain method [.NET Framework hosting]
- UnloadDomain method [.NET Framework hosting]
ms.assetid: dd9e9204-a80d-44f3-8192-779224b35056
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 492a60d3c8d18bec4e99ae778686fec6e8724248
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59140570"
---
# <a name="icorruntimehostunloaddomain-method"></a><span data-ttu-id="bdbd5-102">ICorRuntimeHost::UnloadDomain メソッド</span><span class="sxs-lookup"><span data-stu-id="bdbd5-102">ICorRuntimeHost::UnloadDomain Method</span></span>
<span data-ttu-id="bdbd5-103">現在のプロセスから指定したアプリケーション ドメインをアンロードします。</span><span class="sxs-lookup"><span data-stu-id="bdbd5-103">Unloads the specified application domain from the current process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bdbd5-104">構文</span><span class="sxs-lookup"><span data-stu-id="bdbd5-104">Syntax</span></span>  
  
```  
HRESULT UnloadDomain (  
    [in] IUnknown* pAppDomain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bdbd5-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="bdbd5-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="bdbd5-106">[in]型のポインター<xref:System._AppDomain?displayProperty=nameWithType>ロードするドメインを表します。</span><span class="sxs-lookup"><span data-stu-id="bdbd5-106">[in] A pointer of type <xref:System._AppDomain?displayProperty=nameWithType> that represents the domain to be unloaded.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bdbd5-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="bdbd5-107">Return Value</span></span>  
  
|<span data-ttu-id="bdbd5-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="bdbd5-108">HRESULT</span></span>|<span data-ttu-id="bdbd5-109">説明</span><span class="sxs-lookup"><span data-stu-id="bdbd5-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="bdbd5-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="bdbd5-110">S_OK</span></span>|<span data-ttu-id="bdbd5-111">操作が正常に完了しました。</span><span class="sxs-lookup"><span data-stu-id="bdbd5-111">The operation was successful.</span></span>|  
|<span data-ttu-id="bdbd5-112">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="bdbd5-112">S_FALSE</span></span>|<span data-ttu-id="bdbd5-113">操作を完了できませんでした。</span><span class="sxs-lookup"><span data-stu-id="bdbd5-113">The operation failed to complete.</span></span>|  
|<span data-ttu-id="bdbd5-114">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="bdbd5-114">E_FAIL</span></span>|<span data-ttu-id="bdbd5-115">未知の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="bdbd5-115">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="bdbd5-116">場合は、メソッドは、E_FAIL を返します、共通言語ランタイム (CLR) はプロセスで使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="bdbd5-116">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="bdbd5-117">Api をホストする後続の呼び出しには、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="bdbd5-117">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="bdbd5-118">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="bdbd5-118">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="bdbd5-119">プロセスに CLR が読み込まれていないか、CLR は状態をマネージ コードを実行または呼び出しを正常に処理ができません。</span><span class="sxs-lookup"><span data-stu-id="bdbd5-119">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="bdbd5-120">必要条件</span><span class="sxs-lookup"><span data-stu-id="bdbd5-120">Requirements</span></span>  
 <span data-ttu-id="bdbd5-121">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="bdbd5-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bdbd5-122">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="bdbd5-122">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="bdbd5-123">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="bdbd5-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="bdbd5-124">**.NET framework のバージョン:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="bdbd5-124">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bdbd5-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="bdbd5-125">See also</span></span>

- <xref:System._AppDomain>
- <xref:System.AppDomain>
- [<span data-ttu-id="bdbd5-126">ICorRuntimeHost インターフェイス</span><span class="sxs-lookup"><span data-stu-id="bdbd5-126">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
