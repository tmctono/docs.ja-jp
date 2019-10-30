---
title: IHostCrst::Enter メソッド
ms.date: 03/30/2017
api_name:
- IHostCrst.Enter
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostCrst::Enter
helpviewer_keywords:
- Enter method [.NET Framework hosting]
- IHostCrst::Enter method [.NET Framework hosting]
ms.assetid: 100dd7eb-7053-4295-9bb3-32ba47f6ec79
topic_type:
- apiref
ms.openlocfilehash: 757fb996b268892818a54a3f80a54edfd89c7630
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124427"
---
# <a name="ihostcrstenter-method"></a><span data-ttu-id="d79c0-102">IHostCrst::Enter メソッド</span><span class="sxs-lookup"><span data-stu-id="d79c0-102">IHostCrst::Enter Method</span></span>
<span data-ttu-id="d79c0-103">現在の[IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md)インスタンスによって表されるクリティカルセクションを入力します。</span><span class="sxs-lookup"><span data-stu-id="d79c0-103">Enters the critical section that is represented by the current [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d79c0-104">構文</span><span class="sxs-lookup"><span data-stu-id="d79c0-104">Syntax</span></span>  
  
```cpp  
HRESULT Enter (  
    [in] DWORD option  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d79c0-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d79c0-105">Parameters</span></span>  
 `option`  
 <span data-ttu-id="d79c0-106">から[WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md)値の1つ。操作がブロックされた場合にホストが実行するアクションを示します。</span><span class="sxs-lookup"><span data-stu-id="d79c0-106">[in] One of the [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) values, indicating what action the host should take if the operation blocks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d79c0-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="d79c0-107">Return Value</span></span>  
  
|<span data-ttu-id="d79c0-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d79c0-108">HRESULT</span></span>|<span data-ttu-id="d79c0-109">説明</span><span class="sxs-lookup"><span data-stu-id="d79c0-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d79c0-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="d79c0-110">S_OK</span></span>|<span data-ttu-id="d79c0-111">`Enter` が正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="d79c0-111">`Enter` returned successfully.</span></span>|  
|<span data-ttu-id="d79c0-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="d79c0-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="d79c0-113">共通言語ランタイム (CLR) がプロセスに読み込まれていないか、CLR がマネージコードを実行できない状態であるか、または呼び出しが正常に処理されていません。</span><span class="sxs-lookup"><span data-stu-id="d79c0-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="d79c0-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="d79c0-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="d79c0-115">呼び出しがタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="d79c0-115">The call timed out.</span></span>|  
|<span data-ttu-id="d79c0-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="d79c0-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="d79c0-117">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="d79c0-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="d79c0-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="d79c0-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="d79c0-119">ブロックされたスレッドまたはファイバーが待機しているときに、イベントが取り消されました。</span><span class="sxs-lookup"><span data-stu-id="d79c0-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="d79c0-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="d79c0-120">E_FAIL</span></span>|<span data-ttu-id="d79c0-121">原因不明の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="d79c0-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="d79c0-122">メソッドから E_FAIL が返された場合、そのプロセス内で CLR は使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="d79c0-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="d79c0-123">後続のホストメソッドの呼び出しでは、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="d79c0-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d79c0-124">Remarks</span><span class="sxs-lookup"><span data-stu-id="d79c0-124">Remarks</span></span>  
 <span data-ttu-id="d79c0-125">`Enter` Win32 `EnterCriticalSection` 関数をミラー化します。</span><span class="sxs-lookup"><span data-stu-id="d79c0-125">`Enter` mirrors the Win32 `EnterCriticalSection` function.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d79c0-126">このメソッドは、クリティカルセクションが入力されるまでを返しません。</span><span class="sxs-lookup"><span data-stu-id="d79c0-126">This method does not return until the critical section is entered.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d79c0-127">［要件］</span><span class="sxs-lookup"><span data-stu-id="d79c0-127">Requirements</span></span>  
 <span data-ttu-id="d79c0-128">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d79c0-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d79c0-129">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="d79c0-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d79c0-130">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="d79c0-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d79c0-131">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d79c0-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d79c0-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="d79c0-132">See also</span></span>

- [<span data-ttu-id="d79c0-133">ICLRSyncManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d79c0-133">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="d79c0-134">IHostCrst インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d79c0-134">IHostCrst Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md)
- [<span data-ttu-id="d79c0-135">IHostSyncManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d79c0-135">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
