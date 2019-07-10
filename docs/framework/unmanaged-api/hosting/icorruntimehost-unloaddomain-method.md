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
ms.openlocfilehash: 90c845d87cc9c8bf229dd604ec2077ec28d31dcd
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67770788"
---
# <a name="icorruntimehostunloaddomain-method"></a><span data-ttu-id="42b87-102">ICorRuntimeHost::UnloadDomain メソッド</span><span class="sxs-lookup"><span data-stu-id="42b87-102">ICorRuntimeHost::UnloadDomain Method</span></span>
<span data-ttu-id="42b87-103">現在のプロセスから指定したアプリケーション ドメインをアンロードします。</span><span class="sxs-lookup"><span data-stu-id="42b87-103">Unloads the specified application domain from the current process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="42b87-104">構文</span><span class="sxs-lookup"><span data-stu-id="42b87-104">Syntax</span></span>  
  
```cpp  
HRESULT UnloadDomain (  
    [in] IUnknown* pAppDomain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="42b87-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="42b87-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="42b87-106">[in]型のポインター<xref:System._AppDomain?displayProperty=nameWithType>ロードするドメインを表します。</span><span class="sxs-lookup"><span data-stu-id="42b87-106">[in] A pointer of type <xref:System._AppDomain?displayProperty=nameWithType> that represents the domain to be unloaded.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="42b87-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="42b87-107">Return Value</span></span>  
  
|<span data-ttu-id="42b87-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="42b87-108">HRESULT</span></span>|<span data-ttu-id="42b87-109">説明</span><span class="sxs-lookup"><span data-stu-id="42b87-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="42b87-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="42b87-110">S_OK</span></span>|<span data-ttu-id="42b87-111">操作が正常に完了しました。</span><span class="sxs-lookup"><span data-stu-id="42b87-111">The operation was successful.</span></span>|  
|<span data-ttu-id="42b87-112">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="42b87-112">S_FALSE</span></span>|<span data-ttu-id="42b87-113">操作を完了できませんでした。</span><span class="sxs-lookup"><span data-stu-id="42b87-113">The operation failed to complete.</span></span>|  
|<span data-ttu-id="42b87-114">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="42b87-114">E_FAIL</span></span>|<span data-ttu-id="42b87-115">未知の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="42b87-115">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="42b87-116">場合は、メソッドは、E_FAIL を返します、共通言語ランタイム (CLR) はプロセスで使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="42b87-116">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="42b87-117">Api をホストする後続の呼び出しには、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="42b87-117">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="42b87-118">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="42b87-118">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="42b87-119">プロセスに CLR が読み込まれていないか、CLR は状態をマネージ コードを実行または呼び出しを正常に処理ができません。</span><span class="sxs-lookup"><span data-stu-id="42b87-119">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="42b87-120">必要条件</span><span class="sxs-lookup"><span data-stu-id="42b87-120">Requirements</span></span>  
 <span data-ttu-id="42b87-121">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="42b87-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="42b87-122">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="42b87-122">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="42b87-123">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="42b87-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="42b87-124">**.NET framework のバージョン:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="42b87-124">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42b87-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="42b87-125">See also</span></span>

- <xref:System._AppDomain>
- <xref:System.AppDomain>
- [<span data-ttu-id="42b87-126">ICorRuntimeHost インターフェイス</span><span class="sxs-lookup"><span data-stu-id="42b87-126">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
