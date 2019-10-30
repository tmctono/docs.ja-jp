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
ms.openlocfilehash: a599e754202309a2b61d1761150f3f570fd0dc76
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73120420"
---
# <a name="iclrruntimehoststart-method"></a><span data-ttu-id="27a31-102">ICLRRuntimeHost::Start メソッド</span><span class="sxs-lookup"><span data-stu-id="27a31-102">ICLRRuntimeHost::Start Method</span></span>
<span data-ttu-id="27a31-103">共通言語ランタイム (CLR) をプロセスに初期化します。</span><span class="sxs-lookup"><span data-stu-id="27a31-103">Initializes the common language runtime (CLR) into a process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="27a31-104">構文</span><span class="sxs-lookup"><span data-stu-id="27a31-104">Syntax</span></span>  
  
```cpp  
HRESULT Start();  
```  
  
## <a name="return-value"></a><span data-ttu-id="27a31-105">戻り値</span><span class="sxs-lookup"><span data-stu-id="27a31-105">Return Value</span></span>  
  
|<span data-ttu-id="27a31-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="27a31-106">HRESULT</span></span>|<span data-ttu-id="27a31-107">説明</span><span class="sxs-lookup"><span data-stu-id="27a31-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="27a31-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="27a31-108">S_OK</span></span>|<span data-ttu-id="27a31-109">`Start` が正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="27a31-109">`Start` returned successfully.</span></span>|  
|<span data-ttu-id="27a31-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="27a31-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="27a31-111">CLR がプロセスに読み込まれていないか、CLR がマネージドコードを実行できない状態であるか、または呼び出しが正常に処理されていません。</span><span class="sxs-lookup"><span data-stu-id="27a31-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="27a31-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="27a31-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="27a31-113">呼び出しがタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="27a31-113">The call timed out.</span></span>|  
|<span data-ttu-id="27a31-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="27a31-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="27a31-115">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="27a31-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="27a31-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="27a31-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="27a31-117">ブロックされたスレッドまたはファイバーが待機しているときに、イベントが取り消されました。</span><span class="sxs-lookup"><span data-stu-id="27a31-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="27a31-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="27a31-118">E_FAIL</span></span>|<span data-ttu-id="27a31-119">原因不明の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="27a31-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="27a31-120">メソッドから E_FAIL が返された場合、そのプロセス内で CLR は使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="27a31-120">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="27a31-121">後続のホストメソッドの呼び出しでは、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="27a31-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="27a31-122">Remarks</span><span class="sxs-lookup"><span data-stu-id="27a31-122">Remarks</span></span>  
 <span data-ttu-id="27a31-123">多くのシナリオでは、マネージコードを実行する最初の要求に応じてランタイムが自動的に初期化するため、`Start`を呼び出す必要はありません。</span><span class="sxs-lookup"><span data-stu-id="27a31-123">In many scenarios it is not necessary to call `Start`, because the runtime will initialize itself automatically upon the first request to run managed code.</span></span> <span data-ttu-id="27a31-124">ただし、`Start` を使用して、ランタイムをいつ初期化するかを正確に指定できます。</span><span class="sxs-lookup"><span data-stu-id="27a31-124">You can, however, use `Start` to specify exactly when the runtime should be initialized.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="27a31-125">［要件］</span><span class="sxs-lookup"><span data-stu-id="27a31-125">Requirements</span></span>  
 <span data-ttu-id="27a31-126">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="27a31-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="27a31-127">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="27a31-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="27a31-128">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="27a31-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="27a31-129">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="27a31-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27a31-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="27a31-130">See also</span></span>

- <xref:System.AppDomain>
- [<span data-ttu-id="27a31-131">ICLRRuntimeHost インターフェイス</span><span class="sxs-lookup"><span data-stu-id="27a31-131">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
