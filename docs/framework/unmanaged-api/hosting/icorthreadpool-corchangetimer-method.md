---
title: ICorThreadpool::CorChangeTimer メソッド
ms.date: 03/30/2017
api_name:
- ICorThreadpool.CorChangeTimer
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorChangeTimer
helpviewer_keywords:
- CorChangeTimer method [.NET Framework hosting]
- ICorThreadpool::CorChangeTimer method [.NET Framework hosting]
ms.assetid: 82b03a59-5a87-43ed-9b75-e04b256e1a46
topic_type:
- apiref
ms.openlocfilehash: bb3778a55e7f395ad65f6a9841ca1f31f1de4ebc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178258"
---
# <a name="icorthreadpoolcorchangetimer-method"></a><span data-ttu-id="5b465-102">ICorThreadpool::CorChangeTimer メソッド</span><span class="sxs-lookup"><span data-stu-id="5b465-102">ICorThreadpool::CorChangeTimer Method</span></span>
<span data-ttu-id="5b465-103">このメソッドは、.NET Framework インフラストラクチャをサポートします。独自に作成したコードから直接使用するためのものではありません。</span><span class="sxs-lookup"><span data-stu-id="5b465-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5b465-104">構文</span><span class="sxs-lookup"><span data-stu-id="5b465-104">Syntax</span></span>  
  
```cpp  
HRESULT CorChangeTimer (  
    [in]  HANDLE Timer,
    [in]  ULONG  DueTime,
    [in]  ULONG  Period,  
    [out] BOOL*  result  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="5b465-105">必要条件</span><span class="sxs-lookup"><span data-stu-id="5b465-105">Requirements</span></span>  
 <span data-ttu-id="5b465-106">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5b465-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5b465-107">**ヘッダー:** msCorEE.h</span><span class="sxs-lookup"><span data-stu-id="5b465-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5b465-108">**ライブラリ:** MSCorEE.dll にリソースとして含まれる</span><span class="sxs-lookup"><span data-stu-id="5b465-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5b465-109">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5b465-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b465-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="5b465-110">See also</span></span>

- [<span data-ttu-id="5b465-111">ICorThreadpool インターフェイス</span><span class="sxs-lookup"><span data-stu-id="5b465-111">ICorThreadpool Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorthreadpool-interface.md)
