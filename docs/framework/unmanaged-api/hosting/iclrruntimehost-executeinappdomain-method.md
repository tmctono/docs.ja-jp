---
title: ICLRRuntimeHost::ExecuteInAppDomain メソッド
ms.date: 03/30/2017
api_name:
- ICLRRuntimeHost.ExecuteInAppDomain
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeHost::ExecuteInAppDomain
helpviewer_keywords:
- ICLRRuntimeHost::ExecuteInAppDomain method [.NET Framework hosting]
- ExecuteInAppDomain method [.NET Framework hosting]
ms.assetid: e2b0e2db-3fae-4b56-844e-d30a125a660c
topic_type:
- apiref
ms.openlocfilehash: c847f177f48d72f28192d1efabe93c65a7b3f4b8
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73120488"
---
# <a name="iclrruntimehostexecuteinappdomain-method"></a><span data-ttu-id="ced84-102">ICLRRuntimeHost::ExecuteInAppDomain メソッド</span><span class="sxs-lookup"><span data-stu-id="ced84-102">ICLRRuntimeHost::ExecuteInAppDomain Method</span></span>
<span data-ttu-id="ced84-103">指定したマネージコードを実行する <xref:System.AppDomain> を指定します。</span><span class="sxs-lookup"><span data-stu-id="ced84-103">Specifies the <xref:System.AppDomain> in which to execute the specified managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ced84-104">構文</span><span class="sxs-lookup"><span data-stu-id="ced84-104">Syntax</span></span>  
  
```cpp  
HRESULT ExecuteInAppDomain(  
    [in] DWORD AppDomainId,   
    [in] FExecuteInDomainCallback pCallback,   
    [in] void* cookie  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ced84-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="ced84-105">Parameters</span></span>  
 `AppDomainId`  
 <span data-ttu-id="ced84-106">から指定したメソッドを実行する <xref:System.AppDomain> の数値 ID。</span><span class="sxs-lookup"><span data-stu-id="ced84-106">[in] The numeric ID of the <xref:System.AppDomain> in which to execute the specified method.</span></span>  
  
 `pCallback`  
 <span data-ttu-id="ced84-107">から指定した <xref:System.AppDomain>内で実行する関数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="ced84-107">[in] A pointer to the function to execute within the specified <xref:System.AppDomain>.</span></span>  
  
 `cookie`  
 <span data-ttu-id="ced84-108">から非透過的な呼び出し元に割り当てられたメモリへのポインター。</span><span class="sxs-lookup"><span data-stu-id="ced84-108">[in] A pointer to opaque caller-allocated memory.</span></span> <span data-ttu-id="ced84-109">このパラメーターは、共通言語ランタイム (CLR) によってドメインコールバックに渡されます。</span><span class="sxs-lookup"><span data-stu-id="ced84-109">This parameter is passed by the common language runtime (CLR) to the domain callback.</span></span> <span data-ttu-id="ced84-110">ランタイムによって管理されるヒープメモリではありません。このメモリの割り当てと有効期間は、どちらも呼び出し元によって制御されます。</span><span class="sxs-lookup"><span data-stu-id="ced84-110">It is not runtime-managed heap memory; both the allocation and lifetime of this memory are controlled by the caller.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ced84-111">戻り値</span><span class="sxs-lookup"><span data-stu-id="ced84-111">Return Value</span></span>  
  
|<span data-ttu-id="ced84-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ced84-112">HRESULT</span></span>|<span data-ttu-id="ced84-113">説明</span><span class="sxs-lookup"><span data-stu-id="ced84-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ced84-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="ced84-114">S_OK</span></span>|<span data-ttu-id="ced84-115">`ExecuteInAppDomain` が正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="ced84-115">`ExecuteInAppDomain` returned successfully.</span></span>|  
|<span data-ttu-id="ced84-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="ced84-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="ced84-117">CLR がプロセスに読み込まれていないか、CLR がマネージドコードを実行できない状態であるか、または呼び出しが正常に処理されていません。</span><span class="sxs-lookup"><span data-stu-id="ced84-117">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="ced84-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="ced84-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="ced84-119">呼び出しがタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="ced84-119">The call timed out.</span></span>|  
|<span data-ttu-id="ced84-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="ced84-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="ced84-121">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="ced84-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="ced84-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="ced84-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="ced84-123">ブロックされたスレッドまたはファイバーが待機しているときに、イベントが取り消されました。</span><span class="sxs-lookup"><span data-stu-id="ced84-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="ced84-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="ced84-124">E_FAIL</span></span>|<span data-ttu-id="ced84-125">原因不明の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="ced84-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="ced84-126">メソッドから E_FAIL が返された場合、そのプロセス内で CLR は使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="ced84-126">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="ced84-127">後続のホストメソッドの呼び出しでは、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="ced84-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ced84-128">Remarks</span><span class="sxs-lookup"><span data-stu-id="ced84-128">Remarks</span></span>  
 <span data-ttu-id="ced84-129">`ExecuteInAppDomain` を使用すると、指定したマネージメソッドを実行する必要があるマネージ <xref:System.AppDomain> をホストで制御できます。</span><span class="sxs-lookup"><span data-stu-id="ced84-129">`ExecuteInAppDomain` allows the host to exercise control over which managed <xref:System.AppDomain> the specified managed method should be executed in.</span></span> <span data-ttu-id="ced84-130">[GetCurrentAppDomainId メソッド](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-getcurrentappdomainid-method.md)を呼び出すことによって、<xref:System.AppDomain.Id%2A> プロパティの値に対応するアプリケーションドメインの識別子の値を取得できます。</span><span class="sxs-lookup"><span data-stu-id="ced84-130">You can get the value of an application domain's identifier, which corresponds to the value of the <xref:System.AppDomain.Id%2A> property, by calling [GetCurrentAppDomainId Method](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-getcurrentappdomainid-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ced84-131">［要件］</span><span class="sxs-lookup"><span data-stu-id="ced84-131">Requirements</span></span>  
 <span data-ttu-id="ced84-132">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ced84-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ced84-133">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="ced84-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ced84-134">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="ced84-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ced84-135">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ced84-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ced84-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="ced84-136">See also</span></span>

- [<span data-ttu-id="ced84-137">ICLRRuntimeHost インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ced84-137">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
