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
ms.openlocfilehash: 79afaac4dce1c4baa9802d81af90c425f5de7a08
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804918"
---
# <a name="ihostcrstenter-method"></a><span data-ttu-id="e00e8-102">IHostCrst::Enter メソッド</span><span class="sxs-lookup"><span data-stu-id="e00e8-102">IHostCrst::Enter Method</span></span>
<span data-ttu-id="e00e8-103">現在の[IHostCrst](ihostcrst-interface.md)インスタンスによって表されるクリティカルセクションを入力します。</span><span class="sxs-lookup"><span data-stu-id="e00e8-103">Enters the critical section that is represented by the current [IHostCrst](ihostcrst-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e00e8-104">構文</span><span class="sxs-lookup"><span data-stu-id="e00e8-104">Syntax</span></span>  
  
```cpp  
HRESULT Enter (  
    [in] DWORD option  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e00e8-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e00e8-105">Parameters</span></span>  
 `option`  
 <span data-ttu-id="e00e8-106">から[WAIT_OPTION](wait-option-enumeration.md)値の1つ。操作がブロックされた場合にホストが実行するアクションを示します。</span><span class="sxs-lookup"><span data-stu-id="e00e8-106">[in] One of the [WAIT_OPTION](wait-option-enumeration.md) values, indicating what action the host should take if the operation blocks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e00e8-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="e00e8-107">Return Value</span></span>  
  
|<span data-ttu-id="e00e8-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e00e8-108">HRESULT</span></span>|<span data-ttu-id="e00e8-109">説明</span><span class="sxs-lookup"><span data-stu-id="e00e8-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e00e8-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="e00e8-110">S_OK</span></span>|<span data-ttu-id="e00e8-111">`Enter`正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="e00e8-111">`Enter` returned successfully.</span></span>|  
|<span data-ttu-id="e00e8-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="e00e8-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="e00e8-113">共通言語ランタイム (CLR) がプロセスに読み込まれていないか、CLR がマネージコードを実行できない状態であるか、または呼び出しが正常に処理されていません。</span><span class="sxs-lookup"><span data-stu-id="e00e8-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="e00e8-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="e00e8-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="e00e8-115">呼び出しがタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="e00e8-115">The call timed out.</span></span>|  
|<span data-ttu-id="e00e8-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="e00e8-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="e00e8-117">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="e00e8-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="e00e8-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="e00e8-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="e00e8-119">ブロックされたスレッドまたはファイバーが待機しているときに、イベントが取り消されました。</span><span class="sxs-lookup"><span data-stu-id="e00e8-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="e00e8-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="e00e8-120">E_FAIL</span></span>|<span data-ttu-id="e00e8-121">原因不明の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="e00e8-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="e00e8-122">メソッドが E_FAIL を返すと、そのプロセス内で CLR が使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="e00e8-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="e00e8-123">後続のホストメソッドの呼び出しでは HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="e00e8-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e00e8-124">解説</span><span class="sxs-lookup"><span data-stu-id="e00e8-124">Remarks</span></span>  
 <span data-ttu-id="e00e8-125">`Enter`Win32 関数をミラー化 `EnterCriticalSection` します。</span><span class="sxs-lookup"><span data-stu-id="e00e8-125">`Enter` mirrors the Win32 `EnterCriticalSection` function.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e00e8-126">このメソッドは、クリティカルセクションが入力されるまでを返しません。</span><span class="sxs-lookup"><span data-stu-id="e00e8-126">This method does not return until the critical section is entered.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e00e8-127">要件</span><span class="sxs-lookup"><span data-stu-id="e00e8-127">Requirements</span></span>  
 <span data-ttu-id="e00e8-128">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e00e8-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e00e8-129">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="e00e8-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e00e8-130">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="e00e8-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e00e8-131">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e00e8-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e00e8-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="e00e8-132">See also</span></span>

- [<span data-ttu-id="e00e8-133">ICLRSyncManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e00e8-133">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="e00e8-134">IHostCrst インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e00e8-134">IHostCrst Interface</span></span>](ihostcrst-interface.md)
- [<span data-ttu-id="e00e8-135">IHostSyncManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e00e8-135">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
