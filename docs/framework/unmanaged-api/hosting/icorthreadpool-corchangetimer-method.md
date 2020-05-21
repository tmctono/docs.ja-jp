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
ms.openlocfilehash: e2174afe0ee96bd153b7b40c73c0185d9058a0dc
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/21/2020
ms.locfileid: "83760339"
---
# <a name="icorthreadpoolcorchangetimer-method"></a><span data-ttu-id="c3bc0-102">ICorThreadpool::CorChangeTimer メソッド</span><span class="sxs-lookup"><span data-stu-id="c3bc0-102">ICorThreadpool::CorChangeTimer Method</span></span>
<span data-ttu-id="c3bc0-103">このメソッドは、.NET Framework インフラストラクチャをサポートします。独自に作成したコードから直接使用するためのものではありません。</span><span class="sxs-lookup"><span data-stu-id="c3bc0-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c3bc0-104">構文</span><span class="sxs-lookup"><span data-stu-id="c3bc0-104">Syntax</span></span>  
  
```cpp  
HRESULT CorChangeTimer (  
    [in]  HANDLE Timer,
    [in]  ULONG  DueTime,
    [in]  ULONG  Period,  
    [out] BOOL*  result  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="c3bc0-105">要件</span><span class="sxs-lookup"><span data-stu-id="c3bc0-105">Requirements</span></span>  
 <span data-ttu-id="c3bc0-106">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c3bc0-106">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c3bc0-107">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="c3bc0-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c3bc0-108">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="c3bc0-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c3bc0-109">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c3bc0-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3bc0-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="c3bc0-110">See also</span></span>

- [<span data-ttu-id="c3bc0-111">ICorThreadpool インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c3bc0-111">ICorThreadpool Interface</span></span>](icorthreadpool-interface.md)
