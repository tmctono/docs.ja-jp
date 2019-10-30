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
ms.openlocfilehash: 1b7d321eec2bbc2beb47c5de034bb4ef5d534c9d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73120465"
---
# <a name="iclrruntimehostgetcurrentappdomainid-method"></a><span data-ttu-id="7cf18-102">ICLRRuntimeHost::GetCurrentAppDomainId メソッド</span><span class="sxs-lookup"><span data-stu-id="7cf18-102">ICLRRuntimeHost::GetCurrentAppDomainId Method</span></span>
<span data-ttu-id="7cf18-103">現在実行中の <xref:System.AppDomain> の数値識別子を取得します。</span><span class="sxs-lookup"><span data-stu-id="7cf18-103">Gets the numeric identifier of the <xref:System.AppDomain> that is currently executing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7cf18-104">構文</span><span class="sxs-lookup"><span data-stu-id="7cf18-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCurrentAppDomainId(  
    [out] DWORD* pdwAppDomainId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7cf18-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="7cf18-105">Parameters</span></span>  
 `pdwAppDomainId`  
 <span data-ttu-id="7cf18-106">入出力現在実行中の <xref:System.AppDomain> の数値識別子。</span><span class="sxs-lookup"><span data-stu-id="7cf18-106">[out] The numeric identifier of the <xref:System.AppDomain> that is currently executing.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7cf18-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="7cf18-107">Return Value</span></span>  
  
|<span data-ttu-id="7cf18-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7cf18-108">HRESULT</span></span>|<span data-ttu-id="7cf18-109">説明</span><span class="sxs-lookup"><span data-stu-id="7cf18-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="7cf18-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="7cf18-110">S_OK</span></span>|<span data-ttu-id="7cf18-111">`GetCurrentAppDomainId` が正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="7cf18-111">`GetCurrentAppDomainId` returned successfully.</span></span>|  
|<span data-ttu-id="7cf18-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="7cf18-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="7cf18-113">共通言語ランタイム (CLR) がプロセスに読み込まれていないか、CLR がマネージコードを実行できない状態であるか、または呼び出しが正常に処理されていません。</span><span class="sxs-lookup"><span data-stu-id="7cf18-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="7cf18-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="7cf18-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="7cf18-115">呼び出しがタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="7cf18-115">The call timed out.</span></span>|  
|<span data-ttu-id="7cf18-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="7cf18-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="7cf18-117">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="7cf18-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="7cf18-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="7cf18-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="7cf18-119">ブロックされたスレッドまたはファイバーが待機しているときに、イベントが取り消されました。</span><span class="sxs-lookup"><span data-stu-id="7cf18-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="7cf18-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="7cf18-120">E_FAIL</span></span>|<span data-ttu-id="7cf18-121">原因不明の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="7cf18-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="7cf18-122">メソッドから E_FAIL が返された場合、そのプロセス内で CLR は使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="7cf18-122">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="7cf18-123">後続のホストメソッドの呼び出しでは、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="7cf18-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7cf18-124">Remarks</span><span class="sxs-lookup"><span data-stu-id="7cf18-124">Remarks</span></span>  
 <span data-ttu-id="7cf18-125">`pdwAppDomainId` パラメーターは、現在のスレッドが実行されている <xref:System.AppDomain> の <xref:System.AppDomain.Id%2A> プロパティの値に設定されます。</span><span class="sxs-lookup"><span data-stu-id="7cf18-125">The `pdwAppDomainId` parameter is set to the value of the <xref:System.AppDomain.Id%2A> property of the <xref:System.AppDomain> in which the current thread is executing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7cf18-126">［要件］</span><span class="sxs-lookup"><span data-stu-id="7cf18-126">Requirements</span></span>  
 <span data-ttu-id="7cf18-127">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7cf18-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7cf18-128">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="7cf18-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7cf18-129">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="7cf18-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7cf18-130">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7cf18-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7cf18-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="7cf18-131">See also</span></span>

- <xref:System.AppDomain>
- <xref:System.AppDomainManager>
- [<span data-ttu-id="7cf18-132">ICLRRuntimeHost インターフェイス</span><span class="sxs-lookup"><span data-stu-id="7cf18-132">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
