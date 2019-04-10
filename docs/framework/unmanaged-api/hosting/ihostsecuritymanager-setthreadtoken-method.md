---
title: IHostSecurityManager::SetThreadToken メソッド
ms.date: 03/30/2017
api_name:
- IHostSecurityManager.SetThreadToken
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSecurityManager::SetThreadToken
helpviewer_keywords:
- SetThreadToken method [.NET Framework hosting]
- IHostSecurityManager::SetThreadToken method [.NET Framework hosting]
ms.assetid: e951c345-8a86-4587-911b-a1a57bc6428a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c67471c0d88ccffbfe9b7c77809124452ccc2e5b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59208073"
---
# <a name="ihostsecuritymanagersetthreadtoken-method"></a><span data-ttu-id="82087-102">IHostSecurityManager::SetThreadToken メソッド</span><span class="sxs-lookup"><span data-stu-id="82087-102">IHostSecurityManager::SetThreadToken Method</span></span>
<span data-ttu-id="82087-103">現在実行中のスレッドのハンドルを設定します。</span><span class="sxs-lookup"><span data-stu-id="82087-103">Sets a handle for the currently executing thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="82087-104">構文</span><span class="sxs-lookup"><span data-stu-id="82087-104">Syntax</span></span>  
  
```  
HRESULT SetThreadToken (  
    [in] HANDLE hToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="82087-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="82087-105">Parameters</span></span>  
 `hToken`  
 <span data-ttu-id="82087-106">[in]現在実行中のスレッドを設定するトークンへのハンドル。</span><span class="sxs-lookup"><span data-stu-id="82087-106">[in] A handle to the token to set for the currently executing thread.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="82087-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="82087-107">Return Value</span></span>  
  
|<span data-ttu-id="82087-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="82087-108">HRESULT</span></span>|<span data-ttu-id="82087-109">説明</span><span class="sxs-lookup"><span data-stu-id="82087-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="82087-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="82087-110">S_OK</span></span>|`SetThreadToken` <span data-ttu-id="82087-111">正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="82087-111">returned successfully.</span></span>|  
|<span data-ttu-id="82087-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="82087-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="82087-113">共通言語ランタイム (CLR) は、プロセスに読み込まれていないか、CLR は状態をマネージ コードを実行または呼び出しを正常に処理ができません。</span><span class="sxs-lookup"><span data-stu-id="82087-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="82087-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="82087-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="82087-115">呼び出しがタイムアウトになりました。</span><span class="sxs-lookup"><span data-stu-id="82087-115">The call timed out.</span></span>|  
|<span data-ttu-id="82087-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="82087-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="82087-117">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="82087-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="82087-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="82087-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="82087-119">イベントがキャンセルされましたブロックされたスレッドまたはファイバーが待機しています。</span><span class="sxs-lookup"><span data-stu-id="82087-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="82087-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="82087-120">E_FAIL</span></span>|<span data-ttu-id="82087-121">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="82087-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="82087-122">メソッドには、E_FAIL が返される、ときに、CLR は、プロセス内で使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="82087-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="82087-123">メソッドをホストする後続の呼び出しには、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="82087-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="82087-124">Remarks</span><span class="sxs-lookup"><span data-stu-id="82087-124">Remarks</span></span>  
 `IHostSecurityManager::SetThreadToken` <span data-ttu-id="82087-125">動作は同様に、同じ名前の対応する Win32 関数に点を除いて、呼び出し元に渡す任意のスレッドのハンドルで Win32 関数は、中にされた`IHostSecurityManager::SetThreadToken`現在実行中のスレッドでのみ、トークンを関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="82087-125">behaves similarly to the corresponding Win32 function of the same name, except that the Win32 function allows the caller to pass in a handle to an arbitrary thread, while `IHostSecurityManager::SetThreadToken` can associate a token only with the currently executing thread.</span></span>  
  
 <span data-ttu-id="82087-126">`HANDLE`型は COM に準拠していない; は、そのサイズは、オペレーティング システムに固有とカスタム マーシャ リングが必要です。</span><span class="sxs-lookup"><span data-stu-id="82087-126">The `HANDLE` type is not COM-compliant; that is, its size is specific to an operating system and it requires custom marshaling.</span></span> <span data-ttu-id="82087-127">したがって、このトークンは、CLR とホスト間、プロセス内でのみ使用します。</span><span class="sxs-lookup"><span data-stu-id="82087-127">Thus, this token is for use only within the process, between the CLR and the host.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="82087-128">必要条件</span><span class="sxs-lookup"><span data-stu-id="82087-128">Requirements</span></span>  
 <span data-ttu-id="82087-129">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="82087-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="82087-130">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="82087-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="82087-131">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="82087-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="82087-132">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="82087-132">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="82087-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="82087-133">See also</span></span>

- [<span data-ttu-id="82087-134">IHostSecurityManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="82087-134">IHostSecurityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)
- [<span data-ttu-id="82087-135">IHostThreadPoolManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="82087-135">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)
