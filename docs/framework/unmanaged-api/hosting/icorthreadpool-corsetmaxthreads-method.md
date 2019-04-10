---
title: ICorThreadpool::CorSetMaxThreads メソッド
ms.date: 03/30/2017
api_name:
- ICorThreadpool.CorSetMaxThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorSetMaxThreads
helpviewer_keywords:
- ICorThreadpool::CorSetMaxThreads method [.NET Framework hosting]
- CorSetMaxThreads method [.NET Framework hosting]
ms.assetid: 4a846238-df4e-4060-ba3b-5173f6a51e85
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 48d84d5c45ea8e1af1da44480410692d46162810
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59198245"
---
# <a name="icorthreadpoolcorsetmaxthreads-method"></a><span data-ttu-id="43ff0-102">ICorThreadpool::CorSetMaxThreads メソッド</span><span class="sxs-lookup"><span data-stu-id="43ff0-102">ICorThreadpool::CorSetMaxThreads Method</span></span>
<span data-ttu-id="43ff0-103">このメソッドは、.NET Framework インフラストラクチャをサポートします。独自に作成したコードから直接使用するためのものではありません。</span><span class="sxs-lookup"><span data-stu-id="43ff0-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="43ff0-104">構文</span><span class="sxs-lookup"><span data-stu-id="43ff0-104">Syntax</span></span>  
  
```  
HRESULT CorSetMaxThreads (  
    [in] DWORD MaxWorkerThreads,  
    [in] DWORD MaxIOCompletionThreads  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="43ff0-105">必要条件</span><span class="sxs-lookup"><span data-stu-id="43ff0-105">Requirements</span></span>  
 <span data-ttu-id="43ff0-106">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="43ff0-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="43ff0-107">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="43ff0-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="43ff0-108">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="43ff0-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="43ff0-109">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="43ff0-109">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="43ff0-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="43ff0-110">See also</span></span>

- [<span data-ttu-id="43ff0-111">ICorThreadpool インターフェイス</span><span class="sxs-lookup"><span data-stu-id="43ff0-111">ICorThreadpool Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorthreadpool-interface.md)
