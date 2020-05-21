---
title: ICorThreadpool::CorGetMaxThreads メソッド
ms.date: 03/30/2017
api_name:
- ICorThreadpool.CorGetMaxThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorGetMaxThreads
helpviewer_keywords:
- CorGetMaxThreads method [.NET Framework hosting]
- ICorThreadpool::CorGetMaxThreads method [.NET Framework hosting]
ms.assetid: 2861533a-cda0-47b3-b716-0d363505289b
topic_type:
- apiref
ms.openlocfilehash: 46ffdb21c1f3b501cc28afffc224349887af5644
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762751"
---
# <a name="icorthreadpoolcorgetmaxthreads-method"></a><span data-ttu-id="22baf-102">ICorThreadpool::CorGetMaxThreads メソッド</span><span class="sxs-lookup"><span data-stu-id="22baf-102">ICorThreadpool::CorGetMaxThreads Method</span></span>
<span data-ttu-id="22baf-103">このメソッドは、.NET Framework インフラストラクチャをサポートします。独自に作成したコードから直接使用するためのものではありません。</span><span class="sxs-lookup"><span data-stu-id="22baf-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="22baf-104">構文</span><span class="sxs-lookup"><span data-stu-id="22baf-104">Syntax</span></span>  
  
```cpp  
HRESULT CorGetMaxThreads (  
    [out] DWORD *MaxWorkerThreads,  
    [out] DWORD *MaxIOCompletionThreads  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="22baf-105">要件</span><span class="sxs-lookup"><span data-stu-id="22baf-105">Requirements</span></span>  
 <span data-ttu-id="22baf-106">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="22baf-106">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="22baf-107">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="22baf-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="22baf-108">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="22baf-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="22baf-109">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="22baf-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22baf-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="22baf-110">See also</span></span>

- [<span data-ttu-id="22baf-111">ICorThreadpool インターフェイス</span><span class="sxs-lookup"><span data-stu-id="22baf-111">ICorThreadpool Interface</span></span>](icorthreadpool-interface.md)
