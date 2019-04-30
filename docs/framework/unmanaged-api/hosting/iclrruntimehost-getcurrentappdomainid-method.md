---
title: ICLRRuntimeHost::GetCurrentAppDomainId メソッド
ms.date: 03/30/2017
api_name:
- ICLRRuntimeHost.GetCurrentAppDomainId
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeHost::GetCurrentAppDomainId
helpviewer_keywords:
- ICLRRuntimeHost::GetCurrentAppDomainId method [.NET Framework hosting]
- GetCurrentAppDomainId method [.NET Framework hosting]
ms.assetid: 33800475-7815-4976-8aca-a1038761a2ef
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 28d1655bdc3746dab87acef2e2aac6758883e74a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61971666"
---
# <a name="iclrruntimehostgetcurrentappdomainid-method"></a><span data-ttu-id="d5440-102">ICLRRuntimeHost::GetCurrentAppDomainId メソッド</span><span class="sxs-lookup"><span data-stu-id="d5440-102">ICLRRuntimeHost::GetCurrentAppDomainId Method</span></span>
<span data-ttu-id="d5440-103">数値識別子を取得、<xref:System.AppDomain>が現在実行されています。</span><span class="sxs-lookup"><span data-stu-id="d5440-103">Gets the numeric identifier of the <xref:System.AppDomain> that is currently executing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d5440-104">構文</span><span class="sxs-lookup"><span data-stu-id="d5440-104">Syntax</span></span>  
  
```  
HRESULT GetCurrentAppDomainId(  
    [out] DWORD* pdwAppDomainId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d5440-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d5440-105">Parameters</span></span>  
 `pdwAppDomainId`  
 <span data-ttu-id="d5440-106">[out]数値識別子、<xref:System.AppDomain>が現在実行されています。</span><span class="sxs-lookup"><span data-stu-id="d5440-106">[out] The numeric identifier of the <xref:System.AppDomain> that is currently executing.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d5440-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="d5440-107">Return Value</span></span>  
  
|<span data-ttu-id="d5440-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d5440-108">HRESULT</span></span>|<span data-ttu-id="d5440-109">説明</span><span class="sxs-lookup"><span data-stu-id="d5440-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d5440-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="d5440-110">S_OK</span></span>|<span data-ttu-id="d5440-111">`GetCurrentAppDomainId` 正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="d5440-111">`GetCurrentAppDomainId` returned successfully.</span></span>|  
|<span data-ttu-id="d5440-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="d5440-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="d5440-113">共通言語ランタイム (CLR) は、プロセスに読み込まれていないか、CLR は状態をマネージ コードを実行または呼び出しを正常に処理ができません。</span><span class="sxs-lookup"><span data-stu-id="d5440-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="d5440-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="d5440-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="d5440-115">呼び出しがタイムアウトになりました。</span><span class="sxs-lookup"><span data-stu-id="d5440-115">The call timed out.</span></span>|  
|<span data-ttu-id="d5440-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="d5440-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="d5440-117">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="d5440-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="d5440-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="d5440-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="d5440-119">イベントがキャンセルされましたブロックされたスレッドまたはファイバーが待機しています。</span><span class="sxs-lookup"><span data-stu-id="d5440-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="d5440-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="d5440-120">E_FAIL</span></span>|<span data-ttu-id="d5440-121">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="d5440-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="d5440-122">メソッドから E_FAIL が返された場合、CLR は、プロセス内で使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="d5440-122">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="d5440-123">メソッドをホストする後続の呼び出しには、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="d5440-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d5440-124">Remarks</span><span class="sxs-lookup"><span data-stu-id="d5440-124">Remarks</span></span>  
 <span data-ttu-id="d5440-125">`pdwAppDomainId`パラメーターがの値に設定されている、<xref:System.AppDomain.Id%2A>のプロパティ、<xref:System.AppDomain>現在のスレッドを実行します。</span><span class="sxs-lookup"><span data-stu-id="d5440-125">The `pdwAppDomainId` parameter is set to the value of the <xref:System.AppDomain.Id%2A> property of the <xref:System.AppDomain> in which the current thread is executing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d5440-126">必要条件</span><span class="sxs-lookup"><span data-stu-id="d5440-126">Requirements</span></span>  
 <span data-ttu-id="d5440-127">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d5440-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d5440-128">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="d5440-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d5440-129">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="d5440-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d5440-130">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d5440-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5440-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="d5440-131">See also</span></span>

- <xref:System.AppDomain>
- <xref:System.AppDomainManager>
- [<span data-ttu-id="d5440-132">ICLRRuntimeHost インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d5440-132">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
