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
ms.openlocfilehash: aa17f637ef71373697db5ce66e4a6540c5cc5fbd
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139497"
---
# <a name="ihostsecuritymanagersetthreadtoken-method"></a><span data-ttu-id="8f31d-102">IHostSecurityManager::SetThreadToken メソッド</span><span class="sxs-lookup"><span data-stu-id="8f31d-102">IHostSecurityManager::SetThreadToken Method</span></span>
<span data-ttu-id="8f31d-103">現在実行中のスレッドのハンドルを設定します。</span><span class="sxs-lookup"><span data-stu-id="8f31d-103">Sets a handle for the currently executing thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8f31d-104">構文</span><span class="sxs-lookup"><span data-stu-id="8f31d-104">Syntax</span></span>  
  
```cpp  
HRESULT SetThreadToken (  
    [in] HANDLE hToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8f31d-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="8f31d-105">Parameters</span></span>  
 `hToken`  
 <span data-ttu-id="8f31d-106">から現在実行中のスレッドに設定するトークンへのハンドル。</span><span class="sxs-lookup"><span data-stu-id="8f31d-106">[in] A handle to the token to set for the currently executing thread.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8f31d-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="8f31d-107">Return Value</span></span>  
  
|<span data-ttu-id="8f31d-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8f31d-108">HRESULT</span></span>|<span data-ttu-id="8f31d-109">説明</span><span class="sxs-lookup"><span data-stu-id="8f31d-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8f31d-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="8f31d-110">S_OK</span></span>|<span data-ttu-id="8f31d-111">`SetThreadToken` が正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="8f31d-111">`SetThreadToken` returned successfully.</span></span>|  
|<span data-ttu-id="8f31d-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="8f31d-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="8f31d-113">共通言語ランタイム (CLR) がプロセスに読み込まれていないか、CLR がマネージコードを実行できない状態であるか、または呼び出しが正常に処理されていません。</span><span class="sxs-lookup"><span data-stu-id="8f31d-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="8f31d-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="8f31d-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="8f31d-115">呼び出しがタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="8f31d-115">The call timed out.</span></span>|  
|<span data-ttu-id="8f31d-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="8f31d-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="8f31d-117">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="8f31d-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="8f31d-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="8f31d-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="8f31d-119">ブロックされたスレッドまたはファイバーが待機しているときに、イベントが取り消されました。</span><span class="sxs-lookup"><span data-stu-id="8f31d-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="8f31d-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="8f31d-120">E_FAIL</span></span>|<span data-ttu-id="8f31d-121">原因不明の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="8f31d-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="8f31d-122">メソッドから E_FAIL が返された場合、そのプロセス内で CLR は使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="8f31d-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="8f31d-123">後続のホストメソッドの呼び出しでは、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="8f31d-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8f31d-124">Remarks</span><span class="sxs-lookup"><span data-stu-id="8f31d-124">Remarks</span></span>  
 <span data-ttu-id="8f31d-125">`IHostSecurityManager::SetThreadToken` は、同じ名前の対応する Win32 関数と同様に動作しますが、Win32 関数を使用すると、呼び出し元は任意のスレッドへのハンドルを渡すことができ、`IHostSecurityManager::SetThreadToken` は現在実行中のスレッドにのみトークンを関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="8f31d-125">`IHostSecurityManager::SetThreadToken` behaves similarly to the corresponding Win32 function of the same name, except that the Win32 function allows the caller to pass in a handle to an arbitrary thread, while `IHostSecurityManager::SetThreadToken` can associate a token only with the currently executing thread.</span></span>  
  
 <span data-ttu-id="8f31d-126">`HANDLE` 型は COM に準拠していません。つまり、サイズはオペレーティングシステムに固有であり、カスタムマーシャリングが必要です。</span><span class="sxs-lookup"><span data-stu-id="8f31d-126">The `HANDLE` type is not COM-compliant; that is, its size is specific to an operating system and it requires custom marshaling.</span></span> <span data-ttu-id="8f31d-127">したがって、このトークンは、CLR とホストの間でプロセス内でのみ使用されます。</span><span class="sxs-lookup"><span data-stu-id="8f31d-127">Thus, this token is for use only within the process, between the CLR and the host.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8f31d-128">［要件］</span><span class="sxs-lookup"><span data-stu-id="8f31d-128">Requirements</span></span>  
 <span data-ttu-id="8f31d-129">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8f31d-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8f31d-130">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="8f31d-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8f31d-131">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="8f31d-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8f31d-132">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8f31d-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f31d-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="8f31d-133">See also</span></span>

- [<span data-ttu-id="8f31d-134">IHostSecurityManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8f31d-134">IHostSecurityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)
- [<span data-ttu-id="8f31d-135">IHostThreadPoolManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8f31d-135">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)
