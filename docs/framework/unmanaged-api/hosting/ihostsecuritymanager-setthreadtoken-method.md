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
ms.openlocfilehash: 3aabc21eb15479fe81c922c3fe9625b210caa9d2
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67778003"
---
# <a name="ihostsecuritymanagersetthreadtoken-method"></a><span data-ttu-id="d05d5-102">IHostSecurityManager::SetThreadToken メソッド</span><span class="sxs-lookup"><span data-stu-id="d05d5-102">IHostSecurityManager::SetThreadToken Method</span></span>
<span data-ttu-id="d05d5-103">現在実行中のスレッドのハンドルを設定します。</span><span class="sxs-lookup"><span data-stu-id="d05d5-103">Sets a handle for the currently executing thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d05d5-104">構文</span><span class="sxs-lookup"><span data-stu-id="d05d5-104">Syntax</span></span>  
  
```cpp  
HRESULT SetThreadToken (  
    [in] HANDLE hToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d05d5-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d05d5-105">Parameters</span></span>  
 `hToken`  
 <span data-ttu-id="d05d5-106">[in]現在実行中のスレッドを設定するトークンへのハンドル。</span><span class="sxs-lookup"><span data-stu-id="d05d5-106">[in] A handle to the token to set for the currently executing thread.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d05d5-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="d05d5-107">Return Value</span></span>  
  
|<span data-ttu-id="d05d5-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d05d5-108">HRESULT</span></span>|<span data-ttu-id="d05d5-109">説明</span><span class="sxs-lookup"><span data-stu-id="d05d5-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d05d5-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="d05d5-110">S_OK</span></span>|<span data-ttu-id="d05d5-111">`SetThreadToken` 正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="d05d5-111">`SetThreadToken` returned successfully.</span></span>|  
|<span data-ttu-id="d05d5-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="d05d5-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="d05d5-113">共通言語ランタイム (CLR) は、プロセスに読み込まれていないか、CLR は状態をマネージ コードを実行または呼び出しを正常に処理ができません。</span><span class="sxs-lookup"><span data-stu-id="d05d5-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="d05d5-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="d05d5-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="d05d5-115">呼び出しがタイムアウトになりました。</span><span class="sxs-lookup"><span data-stu-id="d05d5-115">The call timed out.</span></span>|  
|<span data-ttu-id="d05d5-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="d05d5-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="d05d5-117">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="d05d5-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="d05d5-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="d05d5-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="d05d5-119">イベントがキャンセルされましたブロックされたスレッドまたはファイバーが待機しています。</span><span class="sxs-lookup"><span data-stu-id="d05d5-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="d05d5-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="d05d5-120">E_FAIL</span></span>|<span data-ttu-id="d05d5-121">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="d05d5-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="d05d5-122">メソッドには、E_FAIL が返される、ときに、CLR は、プロセス内で使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="d05d5-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="d05d5-123">メソッドをホストする後続の呼び出しには、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="d05d5-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d05d5-124">Remarks</span><span class="sxs-lookup"><span data-stu-id="d05d5-124">Remarks</span></span>  
 <span data-ttu-id="d05d5-125">`IHostSecurityManager::SetThreadToken` 動作は同様に、同じ名前の対応する Win32 関数に点を除いて、呼び出し元に渡す任意のスレッドのハンドルで Win32 関数は、中にされた`IHostSecurityManager::SetThreadToken`現在実行中のスレッドでのみ、トークンを関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="d05d5-125">`IHostSecurityManager::SetThreadToken` behaves similarly to the corresponding Win32 function of the same name, except that the Win32 function allows the caller to pass in a handle to an arbitrary thread, while `IHostSecurityManager::SetThreadToken` can associate a token only with the currently executing thread.</span></span>  
  
 <span data-ttu-id="d05d5-126">`HANDLE`型は COM に準拠していない; は、そのサイズは、オペレーティング システムに固有とカスタム マーシャ リングが必要です。</span><span class="sxs-lookup"><span data-stu-id="d05d5-126">The `HANDLE` type is not COM-compliant; that is, its size is specific to an operating system and it requires custom marshaling.</span></span> <span data-ttu-id="d05d5-127">したがって、このトークンは、CLR とホスト間、プロセス内でのみ使用します。</span><span class="sxs-lookup"><span data-stu-id="d05d5-127">Thus, this token is for use only within the process, between the CLR and the host.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d05d5-128">必要条件</span><span class="sxs-lookup"><span data-stu-id="d05d5-128">Requirements</span></span>  
 <span data-ttu-id="d05d5-129">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d05d5-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d05d5-130">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="d05d5-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d05d5-131">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="d05d5-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d05d5-132">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d05d5-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d05d5-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="d05d5-133">See also</span></span>

- [<span data-ttu-id="d05d5-134">IHostSecurityManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d05d5-134">IHostSecurityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)
- [<span data-ttu-id="d05d5-135">IHostThreadPoolManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d05d5-135">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)
