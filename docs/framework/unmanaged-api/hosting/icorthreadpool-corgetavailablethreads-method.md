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
ms.openlocfilehash: 43d22e5b6fcbbb006d9745942ca94434ee64c08c
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67751316"
---
# <a name="icorthreadpoolcorgetavailablethreads-method"></a><span data-ttu-id="bcca8-102">ICorThreadpool::CorGetAvailableThreads メソッド</span><span class="sxs-lookup"><span data-stu-id="bcca8-102">ICorThreadpool::CorGetAvailableThreads Method</span></span>
<span data-ttu-id="bcca8-103">このメソッドは、.NET Framework インフラストラクチャをサポートします。独自に作成したコードから直接使用するためのものではありません。</span><span class="sxs-lookup"><span data-stu-id="bcca8-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bcca8-104">構文</span><span class="sxs-lookup"><span data-stu-id="bcca8-104">Syntax</span></span>  
  
```cpp  
HRESULT CorGetAvailableThreads (  
    [out] DWORD *AvailableWorkerThreads,  
    [out] DWORD *AvailableIOCompletionThreads  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="bcca8-105">必要条件</span><span class="sxs-lookup"><span data-stu-id="bcca8-105">Requirements</span></span>  
 <span data-ttu-id="bcca8-106">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="bcca8-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bcca8-107">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="bcca8-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="bcca8-108">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="bcca8-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="bcca8-109">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bcca8-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bcca8-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="bcca8-110">See also</span></span>

- [<span data-ttu-id="bcca8-111">ICorThreadpool インターフェイス</span><span class="sxs-lookup"><span data-stu-id="bcca8-111">ICorThreadpool Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorthreadpool-interface.md)
