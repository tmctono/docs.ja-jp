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
ms.openlocfilehash: 1c667b19ac4bfa0bea95b85cf099906e351e5b71
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703668"
---
# <a name="iclrruntimehostgetcurrentappdomainid-method"></a><span data-ttu-id="d617b-102">ICLRRuntimeHost::GetCurrentAppDomainId メソッド</span><span class="sxs-lookup"><span data-stu-id="d617b-102">ICLRRuntimeHost::GetCurrentAppDomainId Method</span></span>
<span data-ttu-id="d617b-103">現在実行中のの数値識別子を取得し <xref:System.AppDomain> ます。</span><span class="sxs-lookup"><span data-stu-id="d617b-103">Gets the numeric identifier of the <xref:System.AppDomain> that is currently executing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d617b-104">構文</span><span class="sxs-lookup"><span data-stu-id="d617b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCurrentAppDomainId(  
    [out] DWORD* pdwAppDomainId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d617b-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d617b-105">Parameters</span></span>  
 `pdwAppDomainId`  
 <span data-ttu-id="d617b-106">入出力現在実行中のの数値識別子 <xref:System.AppDomain> 。</span><span class="sxs-lookup"><span data-stu-id="d617b-106">[out] The numeric identifier of the <xref:System.AppDomain> that is currently executing.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d617b-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="d617b-107">Return Value</span></span>  
  
|<span data-ttu-id="d617b-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d617b-108">HRESULT</span></span>|<span data-ttu-id="d617b-109">説明</span><span class="sxs-lookup"><span data-stu-id="d617b-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d617b-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="d617b-110">S_OK</span></span>|<span data-ttu-id="d617b-111">`GetCurrentAppDomainId`正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="d617b-111">`GetCurrentAppDomainId` returned successfully.</span></span>|  
|<span data-ttu-id="d617b-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="d617b-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="d617b-113">共通言語ランタイム (CLR) がプロセスに読み込まれていないか、CLR がマネージコードを実行できない状態であるか、または呼び出しが正常に処理されていません。</span><span class="sxs-lookup"><span data-stu-id="d617b-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="d617b-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="d617b-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="d617b-115">呼び出しがタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="d617b-115">The call timed out.</span></span>|  
|<span data-ttu-id="d617b-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="d617b-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="d617b-117">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="d617b-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="d617b-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="d617b-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="d617b-119">ブロックされたスレッドまたはファイバーが待機しているときに、イベントが取り消されました。</span><span class="sxs-lookup"><span data-stu-id="d617b-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="d617b-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="d617b-120">E_FAIL</span></span>|<span data-ttu-id="d617b-121">原因不明の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="d617b-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="d617b-122">メソッドが E_FAIL を返す場合、そのプロセス内で CLR は使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="d617b-122">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="d617b-123">後続のホストメソッドの呼び出しでは HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="d617b-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d617b-124">解説</span><span class="sxs-lookup"><span data-stu-id="d617b-124">Remarks</span></span>  
 <span data-ttu-id="d617b-125">`pdwAppDomainId`パラメーターは <xref:System.AppDomain.Id%2A> 、 <xref:System.AppDomain> 現在のスレッドが実行されているのプロパティの値に設定されます。</span><span class="sxs-lookup"><span data-stu-id="d617b-125">The `pdwAppDomainId` parameter is set to the value of the <xref:System.AppDomain.Id%2A> property of the <xref:System.AppDomain> in which the current thread is executing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d617b-126">要件</span><span class="sxs-lookup"><span data-stu-id="d617b-126">Requirements</span></span>  
 <span data-ttu-id="d617b-127">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d617b-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d617b-128">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="d617b-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d617b-129">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="d617b-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d617b-130">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d617b-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d617b-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="d617b-131">See also</span></span>

- <xref:System.AppDomain>
- <xref:System.AppDomainManager>
- [<span data-ttu-id="d617b-132">ICLRRuntimeHost インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d617b-132">ICLRRuntimeHost Interface</span></span>](iclrruntimehost-interface.md)
