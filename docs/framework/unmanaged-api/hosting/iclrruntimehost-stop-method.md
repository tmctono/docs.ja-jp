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
ms.openlocfilehash: 97a0e6cbbd8972f58f9eedcfeb8aff1f93694064
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67765669"
---
# <a name="iclrruntimehoststop-method"></a><span data-ttu-id="ebb96-102">ICLRRuntimeHost::Stop メソッド</span><span class="sxs-lookup"><span data-stu-id="ebb96-102">ICLRRuntimeHost::Stop Method</span></span>
<span data-ttu-id="ebb96-103">共通言語ランタイム (CLR) では、コードの実行を停止します。</span><span class="sxs-lookup"><span data-stu-id="ebb96-103">Stops the execution of code by the common language runtime (CLR).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="ebb96-104">このメソッドによって、ホストにリソースを解放されたり、アプリケーション ドメインのアンロードまたは、スレッドの破棄されたりすることはできません。</span><span class="sxs-lookup"><span data-stu-id="ebb96-104">This method does not release resources to the host, unload application domains, or destroy threads.</span></span> <span data-ttu-id="ebb96-105">これらのリソースを解放するプロセスを終了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ebb96-105">You must terminate the process to release these resources.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ebb96-106">構文</span><span class="sxs-lookup"><span data-stu-id="ebb96-106">Syntax</span></span>  
  
```cpp  
HRESULT Stop();  
```  
  
## <a name="return-value"></a><span data-ttu-id="ebb96-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="ebb96-107">Return Value</span></span>  
  
|<span data-ttu-id="ebb96-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ebb96-108">HRESULT</span></span>|<span data-ttu-id="ebb96-109">説明</span><span class="sxs-lookup"><span data-stu-id="ebb96-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ebb96-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="ebb96-110">S_OK</span></span>|<span data-ttu-id="ebb96-111">`Stop` 正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="ebb96-111">`Stop` returned successfully.</span></span>|  
|<span data-ttu-id="ebb96-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="ebb96-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="ebb96-113">プロセスに CLR が読み込まれていないか、CLR は状態をマネージ コードを実行または呼び出しを正常に処理ができません。</span><span class="sxs-lookup"><span data-stu-id="ebb96-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="ebb96-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="ebb96-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="ebb96-115">呼び出しがタイムアウトになりました。</span><span class="sxs-lookup"><span data-stu-id="ebb96-115">The call timed out.</span></span>|  
|<span data-ttu-id="ebb96-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="ebb96-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="ebb96-117">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="ebb96-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="ebb96-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="ebb96-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="ebb96-119">イベントがキャンセルされましたブロックされたスレッドまたはファイバーが待機しています。</span><span class="sxs-lookup"><span data-stu-id="ebb96-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="ebb96-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="ebb96-120">E_FAIL</span></span>|<span data-ttu-id="ebb96-121">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="ebb96-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="ebb96-122">メソッドから E_FAIL が返された場合、CLR は、プロセス内で使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="ebb96-122">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="ebb96-123">メソッドをホストする後続の呼び出しには、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="ebb96-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ebb96-124">必要条件</span><span class="sxs-lookup"><span data-stu-id="ebb96-124">Requirements</span></span>  
 <span data-ttu-id="ebb96-125">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ebb96-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ebb96-126">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="ebb96-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ebb96-127">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="ebb96-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ebb96-128">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ebb96-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ebb96-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="ebb96-129">See also</span></span>

- [<span data-ttu-id="ebb96-130">ICLRRuntimeHost インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ebb96-130">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
