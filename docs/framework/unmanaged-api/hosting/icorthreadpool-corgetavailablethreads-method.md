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
ms.openlocfilehash: e5c11cfe21303aca6b867951ad610cddc58a0f03
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762761"
---
# <a name="icorthreadpoolcorgetavailablethreads-method"></a><span data-ttu-id="2e70f-102">ICorThreadpool::CorGetAvailableThreads メソッド</span><span class="sxs-lookup"><span data-stu-id="2e70f-102">ICorThreadpool::CorGetAvailableThreads Method</span></span>
<span data-ttu-id="2e70f-103">このメソッドは、.NET Framework インフラストラクチャをサポートします。独自に作成したコードから直接使用するためのものではありません。</span><span class="sxs-lookup"><span data-stu-id="2e70f-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2e70f-104">構文</span><span class="sxs-lookup"><span data-stu-id="2e70f-104">Syntax</span></span>  
  
```cpp  
HRESULT CorGetAvailableThreads (  
    [out] DWORD *AvailableWorkerThreads,  
    [out] DWORD *AvailableIOCompletionThreads  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="2e70f-105">要件</span><span class="sxs-lookup"><span data-stu-id="2e70f-105">Requirements</span></span>  
 <span data-ttu-id="2e70f-106">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2e70f-106">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2e70f-107">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="2e70f-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2e70f-108">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="2e70f-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2e70f-109">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2e70f-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e70f-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="2e70f-110">See also</span></span>

- [<span data-ttu-id="2e70f-111">ICorThreadpool インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2e70f-111">ICorThreadpool Interface</span></span>](icorthreadpool-interface.md)
