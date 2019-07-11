---
title: ICorThreadpool::CorCallOrQueueUserWorkItem メソッド
ms.date: 03/30/2017
api_name:
- ICorThreadpool.CorCallOrQueueUserWorkItem
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorCallOrQueueUserWorkItem
helpviewer_keywords:
- ICorThreadpool::CorCallOrQueueUserWorkItem method [.NET Framework hosting]
- CorCallOrQueueUserWorkItem method [.NET Framework hosting]
ms.assetid: a2081223-84ca-4331-a8d3-9352f422f3e7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 62c81741b1260c20b25a0f49a33d3a20ebde24a5
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67780410"
---
# <a name="icorthreadpoolcorcallorqueueuserworkitem-method"></a><span data-ttu-id="78048-102">ICorThreadpool::CorCallOrQueueUserWorkItem メソッド</span><span class="sxs-lookup"><span data-stu-id="78048-102">ICorThreadpool::CorCallOrQueueUserWorkItem Method</span></span>
<span data-ttu-id="78048-103">このメソッドは、.NET Framework インフラストラクチャをサポートします。独自に作成したコードから直接使用するためのものではありません。</span><span class="sxs-lookup"><span data-stu-id="78048-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="78048-104">構文</span><span class="sxs-lookup"><span data-stu-id="78048-104">Syntax</span></span>  
  
```cpp  
HRESULT CorCallOrQueueUserWorkItem (  
    [in] LPTHREAD_START_ROUTINE Function,  
    [in] PVOID                  Context,  
    [out] BOOL*                 result  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="78048-105">必要条件</span><span class="sxs-lookup"><span data-stu-id="78048-105">Requirements</span></span>  
 <span data-ttu-id="78048-106">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="78048-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="78048-107">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="78048-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="78048-108">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="78048-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="78048-109">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="78048-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78048-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="78048-110">See also</span></span>

- [<span data-ttu-id="78048-111">ICorThreadpool インターフェイス</span><span class="sxs-lookup"><span data-stu-id="78048-111">ICorThreadpool Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorthreadpool-interface.md)
