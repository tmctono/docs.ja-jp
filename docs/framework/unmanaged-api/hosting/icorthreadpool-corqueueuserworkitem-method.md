---
title: ICorThreadpool::CorQueueUserWorkItem メソッド
ms.date: 03/30/2017
api_name:
- ICorThreadpool.CorQueueUserWorkItem
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorQueueUserWorkItem
helpviewer_keywords:
- ICorThreadpool::CorQueueUserWorkItem method [.NET Framework hosting]
- CorQueueUserWorkItem method [.NET Framework hosting]
ms.assetid: 29ac7898-a7c7-433e-8f79-cd5237e0bab8
topic_type:
- apiref
ms.openlocfilehash: 5500f2b84f00e039cbc3f669b49be467789955f0
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762735"
---
# <a name="icorthreadpoolcorqueueuserworkitem-method"></a><span data-ttu-id="68a9a-102">ICorThreadpool::CorQueueUserWorkItem メソッド</span><span class="sxs-lookup"><span data-stu-id="68a9a-102">ICorThreadpool::CorQueueUserWorkItem Method</span></span>
<span data-ttu-id="68a9a-103">このメソッドは、.NET Framework インフラストラクチャをサポートします。独自に作成したコードから直接使用するためのものではありません。</span><span class="sxs-lookup"><span data-stu-id="68a9a-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="68a9a-104">構文</span><span class="sxs-lookup"><span data-stu-id="68a9a-104">Syntax</span></span>  
  
```cpp  
HRESULT CorQueueUserWorkItem (  
    [in] LPTHREAD_START_ROUTINE Function,  
    [in] PVOID                  Context,  
    [in] BOOL                   executeOnlyOnce,  
    [out] BOOL*                 result  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="68a9a-105">要件</span><span class="sxs-lookup"><span data-stu-id="68a9a-105">Requirements</span></span>  
 <span data-ttu-id="68a9a-106">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="68a9a-106">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="68a9a-107">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="68a9a-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="68a9a-108">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="68a9a-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="68a9a-109">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="68a9a-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68a9a-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="68a9a-110">See also</span></span>

- [<span data-ttu-id="68a9a-111">ICorThreadpool インターフェイス</span><span class="sxs-lookup"><span data-stu-id="68a9a-111">ICorThreadpool Interface</span></span>](icorthreadpool-interface.md)
