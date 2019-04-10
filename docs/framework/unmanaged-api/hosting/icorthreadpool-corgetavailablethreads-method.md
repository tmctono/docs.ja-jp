---
title: ICorThreadpool::CorGetAvailableThreads メソッド
ms.date: 03/30/2017
api_name:
- ICorThreadpool.CorGetAvailableThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorGetAvailableThreads
helpviewer_keywords:
- CorGetAvailableThreads method [.NET Framework hosting]
- ICorThreadpool::CorGetAvailableThreads method [.NET Framework hosting]
ms.assetid: 0b09b750-0b86-4ba4-9621-041857cfe8ba
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0c929b9434507ea7cce936767f2ac72ff98fda7b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59215795"
---
# <a name="icorthreadpoolcorgetavailablethreads-method"></a><span data-ttu-id="df204-102">ICorThreadpool::CorGetAvailableThreads メソッド</span><span class="sxs-lookup"><span data-stu-id="df204-102">ICorThreadpool::CorGetAvailableThreads Method</span></span>
<span data-ttu-id="df204-103">このメソッドは、.NET Framework インフラストラクチャをサポートします。独自に作成したコードから直接使用するためのものではありません。</span><span class="sxs-lookup"><span data-stu-id="df204-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="df204-104">構文</span><span class="sxs-lookup"><span data-stu-id="df204-104">Syntax</span></span>  
  
```  
HRESULT CorGetAvailableThreads (  
    [out] DWORD *AvailableWorkerThreads,  
    [out] DWORD *AvailableIOCompletionThreads  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="df204-105">必要条件</span><span class="sxs-lookup"><span data-stu-id="df204-105">Requirements</span></span>  
 <span data-ttu-id="df204-106">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="df204-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="df204-107">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="df204-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="df204-108">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="df204-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="df204-109">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="df204-109">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="df204-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="df204-110">See also</span></span>

- [<span data-ttu-id="df204-111">ICorThreadpool インターフェイス</span><span class="sxs-lookup"><span data-stu-id="df204-111">ICorThreadpool Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorthreadpool-interface.md)
