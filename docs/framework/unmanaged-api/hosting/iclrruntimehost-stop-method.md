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
ms.openlocfilehash: 85116244ad21842fab025ddd48106deef75f210b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59166973"
---
# <a name="iclrruntimehoststop-method"></a><span data-ttu-id="6eec5-102">ICLRRuntimeHost::Stop メソッド</span><span class="sxs-lookup"><span data-stu-id="6eec5-102">ICLRRuntimeHost::Stop Method</span></span>
<span data-ttu-id="6eec5-103">共通言語ランタイム (CLR) では、コードの実行を停止します。</span><span class="sxs-lookup"><span data-stu-id="6eec5-103">Stops the execution of code by the common language runtime (CLR).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="6eec5-104">このメソッドによって、ホストにリソースを解放されたり、アプリケーション ドメインのアンロードまたは、スレッドの破棄されたりすることはできません。</span><span class="sxs-lookup"><span data-stu-id="6eec5-104">This method does not release resources to the host, unload application domains, or destroy threads.</span></span> <span data-ttu-id="6eec5-105">これらのリソースを解放するプロセスを終了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6eec5-105">You must terminate the process to release these resources.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6eec5-106">構文</span><span class="sxs-lookup"><span data-stu-id="6eec5-106">Syntax</span></span>  
  
```  
HRESULT Stop();  
```  
  
## <a name="return-value"></a><span data-ttu-id="6eec5-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="6eec5-107">Return Value</span></span>  
  
|<span data-ttu-id="6eec5-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="6eec5-108">HRESULT</span></span>|<span data-ttu-id="6eec5-109">説明</span><span class="sxs-lookup"><span data-stu-id="6eec5-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="6eec5-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="6eec5-110">S_OK</span></span>|<span data-ttu-id="6eec5-111">`Stop` 正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="6eec5-111">`Stop` returned successfully.</span></span>|  
|<span data-ttu-id="6eec5-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="6eec5-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="6eec5-113">プロセスに CLR が読み込まれていないか、CLR は状態をマネージ コードを実行または呼び出しを正常に処理ができません。</span><span class="sxs-lookup"><span data-stu-id="6eec5-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="6eec5-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="6eec5-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="6eec5-115">呼び出しがタイムアウトになりました。</span><span class="sxs-lookup"><span data-stu-id="6eec5-115">The call timed out.</span></span>|  
|<span data-ttu-id="6eec5-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="6eec5-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="6eec5-117">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="6eec5-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="6eec5-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="6eec5-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="6eec5-119">イベントがキャンセルされましたブロックされたスレッドまたはファイバーが待機しています。</span><span class="sxs-lookup"><span data-stu-id="6eec5-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="6eec5-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="6eec5-120">E_FAIL</span></span>|<span data-ttu-id="6eec5-121">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="6eec5-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="6eec5-122">メソッドから E_FAIL が返された場合、CLR は、プロセス内で使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="6eec5-122">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="6eec5-123">メソッドをホストする後続の呼び出しには、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="6eec5-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="6eec5-124">必要条件</span><span class="sxs-lookup"><span data-stu-id="6eec5-124">Requirements</span></span>  
 <span data-ttu-id="6eec5-125">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6eec5-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6eec5-126">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="6eec5-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6eec5-127">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="6eec5-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6eec5-128">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6eec5-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6eec5-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="6eec5-129">See also</span></span>

- [<span data-ttu-id="6eec5-130">ICLRRuntimeHost インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6eec5-130">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
