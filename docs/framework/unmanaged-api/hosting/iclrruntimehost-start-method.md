---
title: ICLRRuntimeHost::Start メソッド
ms.date: 03/30/2017
api_name:
- ICLRRuntimeHost.Start
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeHost::Start
helpviewer_keywords:
- ICLRRuntimeHost::Start method [.NET Framework hosting]
- Start method, ICLRRuntimeHost interface [.NET Framework hosting]
ms.assetid: c0a6dce5-0a8d-42e8-808b-6ca14df9d289
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 608612f6a0f4395092e33ce75fdbd249f19ae4f4
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61771840"
---
# <a name="iclrruntimehoststart-method"></a><span data-ttu-id="97dee-102">ICLRRuntimeHost::Start メソッド</span><span class="sxs-lookup"><span data-stu-id="97dee-102">ICLRRuntimeHost::Start Method</span></span>
<span data-ttu-id="97dee-103">プロセスには、共通言語ランタイム (CLR) を初期化します。</span><span class="sxs-lookup"><span data-stu-id="97dee-103">Initializes the common language runtime (CLR) into a process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="97dee-104">構文</span><span class="sxs-lookup"><span data-stu-id="97dee-104">Syntax</span></span>  
  
```  
HRESULT Start();  
```  
  
## <a name="return-value"></a><span data-ttu-id="97dee-105">戻り値</span><span class="sxs-lookup"><span data-stu-id="97dee-105">Return Value</span></span>  
  
|<span data-ttu-id="97dee-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="97dee-106">HRESULT</span></span>|<span data-ttu-id="97dee-107">説明</span><span class="sxs-lookup"><span data-stu-id="97dee-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="97dee-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="97dee-108">S_OK</span></span>|<span data-ttu-id="97dee-109">`Start` 正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="97dee-109">`Start` returned successfully.</span></span>|  
|<span data-ttu-id="97dee-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="97dee-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="97dee-111">プロセスに CLR が読み込まれていないか、CLR は状態をマネージ コードを実行または呼び出しを正常に処理ができません。</span><span class="sxs-lookup"><span data-stu-id="97dee-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="97dee-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="97dee-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="97dee-113">呼び出しがタイムアウトになりました。</span><span class="sxs-lookup"><span data-stu-id="97dee-113">The call timed out.</span></span>|  
|<span data-ttu-id="97dee-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="97dee-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="97dee-115">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="97dee-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="97dee-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="97dee-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="97dee-117">イベントがキャンセルされましたブロックされたスレッドまたはファイバーが待機しています。</span><span class="sxs-lookup"><span data-stu-id="97dee-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="97dee-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="97dee-118">E_FAIL</span></span>|<span data-ttu-id="97dee-119">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="97dee-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="97dee-120">メソッドから E_FAIL が返された場合、CLR は、プロセス内で使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="97dee-120">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="97dee-121">メソッドをホストする後続の呼び出しには、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="97dee-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="97dee-122">Remarks</span><span class="sxs-lookup"><span data-stu-id="97dee-122">Remarks</span></span>  
 <span data-ttu-id="97dee-123">多くのシナリオで必要はありませんを呼び出す`Start`ランタイムは自動的に初期化をマネージ コードを実行する最初の要求に応じてためです。</span><span class="sxs-lookup"><span data-stu-id="97dee-123">In many scenarios it is not necessary to call `Start`, because the runtime will initialize itself automatically upon the first request to run managed code.</span></span> <span data-ttu-id="97dee-124">ただし、使用することができます、`Start`を正確にすると、ランタイムを初期化するように指定します。</span><span class="sxs-lookup"><span data-stu-id="97dee-124">You can, however, use `Start` to specify exactly when the runtime should be initialized.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="97dee-125">必要条件</span><span class="sxs-lookup"><span data-stu-id="97dee-125">Requirements</span></span>  
 <span data-ttu-id="97dee-126">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="97dee-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="97dee-127">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="97dee-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="97dee-128">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="97dee-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="97dee-129">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="97dee-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97dee-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="97dee-130">See also</span></span>

- <xref:System.AppDomain>
- [<span data-ttu-id="97dee-131">ICLRRuntimeHost インターフェイス</span><span class="sxs-lookup"><span data-stu-id="97dee-131">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
