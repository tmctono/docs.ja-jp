---
title: ICLRRuntimeHost::Stop メソッド
ms.date: 03/30/2017
api_name:
- ICLRRuntimeHost.Stop
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeHost::Stop
helpviewer_keywords:
- ICLRRuntimeHost::Stop method [.NET Framework hosting]
- Stop method, ICLRRuntimeHost interface [.NET Framework hosting]
ms.assetid: b8fd7daf-8f8d-4ad7-92ae-019db244cec1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5fcadb708638efb0b7946426c538e01661505dfa
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69912242"
---
# <a name="iclrruntimehoststop-method"></a><span data-ttu-id="4a80d-102">ICLRRuntimeHost::Stop メソッド</span><span class="sxs-lookup"><span data-stu-id="4a80d-102">ICLRRuntimeHost::Stop Method</span></span>
<span data-ttu-id="4a80d-103">共通言語ランタイム (CLR) によるコードの実行を停止します。</span><span class="sxs-lookup"><span data-stu-id="4a80d-103">Stops the execution of code by the common language runtime (CLR).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="4a80d-104">このメソッドは、ホストへのリソースの解放、アプリケーションドメインのアンロード、またはスレッドの破棄を行いません。</span><span class="sxs-lookup"><span data-stu-id="4a80d-104">This method does not release resources to the host, unload application domains, or destroy threads.</span></span> <span data-ttu-id="4a80d-105">これらのリソースを解放するには、プロセスを終了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4a80d-105">You must terminate the process to release these resources.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4a80d-106">構文</span><span class="sxs-lookup"><span data-stu-id="4a80d-106">Syntax</span></span>  
  
```cpp  
HRESULT Stop();  
```  
  
## <a name="return-value"></a><span data-ttu-id="4a80d-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="4a80d-107">Return Value</span></span>  
  
|<span data-ttu-id="4a80d-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="4a80d-108">HRESULT</span></span>|<span data-ttu-id="4a80d-109">説明</span><span class="sxs-lookup"><span data-stu-id="4a80d-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="4a80d-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="4a80d-110">S_OK</span></span>|<span data-ttu-id="4a80d-111">`Stop`正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="4a80d-111">`Stop` returned successfully.</span></span>|  
|<span data-ttu-id="4a80d-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="4a80d-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="4a80d-113">CLR がプロセスに読み込まれていないか、CLR がマネージドコードを実行できない状態であるか、または呼び出しが正常に処理されていません。</span><span class="sxs-lookup"><span data-stu-id="4a80d-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="4a80d-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="4a80d-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="4a80d-115">呼び出しがタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="4a80d-115">The call timed out.</span></span>|  
|<span data-ttu-id="4a80d-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="4a80d-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="4a80d-117">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="4a80d-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="4a80d-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="4a80d-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="4a80d-119">ブロックされたスレッドまたはファイバーが待機しているときに、イベントが取り消されました。</span><span class="sxs-lookup"><span data-stu-id="4a80d-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="4a80d-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="4a80d-120">E_FAIL</span></span>|<span data-ttu-id="4a80d-121">原因不明の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="4a80d-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="4a80d-122">メソッドから E_FAIL が返された場合、そのプロセス内で CLR は使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="4a80d-122">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="4a80d-123">後続のホストメソッドの呼び出しでは、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="4a80d-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="4a80d-124">必要条件</span><span class="sxs-lookup"><span data-stu-id="4a80d-124">Requirements</span></span>  
 <span data-ttu-id="4a80d-125">**・** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="4a80d-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4a80d-126">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="4a80d-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4a80d-127">**ライブラリ**Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="4a80d-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4a80d-128">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4a80d-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a80d-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="4a80d-129">See also</span></span>

- [<span data-ttu-id="4a80d-130">ICLRRuntimeHost インターフェイス</span><span class="sxs-lookup"><span data-stu-id="4a80d-130">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
