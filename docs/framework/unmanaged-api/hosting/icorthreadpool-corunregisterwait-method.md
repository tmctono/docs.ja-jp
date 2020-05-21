---
title: ICorThreadpool::CorUnregisterWait メソッド
ms.date: 03/30/2017
api_name:
- ICorThreadpool.CorUnregisterWait
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorUnregisterWait
helpviewer_keywords:
- CorUnregisterWait method [.NET Framework hosting]
- ICorThreadpool::CorUnregisterWait method [.NET Framework hosting]
ms.assetid: 42c933f1-30a8-4011-bdea-e117f3c3265e
topic_type:
- apiref
ms.openlocfilehash: e3655f77a94da25f65bada2cd4067ef53550e778
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762020"
---
# <a name="icorthreadpoolcorunregisterwait-method"></a><span data-ttu-id="afffb-102">ICorThreadpool::CorUnregisterWait メソッド</span><span class="sxs-lookup"><span data-stu-id="afffb-102">ICorThreadpool::CorUnregisterWait Method</span></span>
<span data-ttu-id="afffb-103">このメソッドは、.NET Framework インフラストラクチャをサポートします。独自に作成したコードから直接使用するためのものではありません。</span><span class="sxs-lookup"><span data-stu-id="afffb-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="afffb-104">構文</span><span class="sxs-lookup"><span data-stu-id="afffb-104">Syntax</span></span>  
  
```cpp  
HRESULT CorUnregisterWait (  
    [in] HANDLE hWaitObject,  
    [in] HANDLE CompletionEvent,  
    [out] BOOL* result  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="afffb-105">要件</span><span class="sxs-lookup"><span data-stu-id="afffb-105">Requirements</span></span>  
 <span data-ttu-id="afffb-106">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="afffb-106">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="afffb-107">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="afffb-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="afffb-108">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="afffb-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="afffb-109">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="afffb-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="afffb-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="afffb-110">See also</span></span>

- [<span data-ttu-id="afffb-111">ICorThreadpool インターフェイス</span><span class="sxs-lookup"><span data-stu-id="afffb-111">ICorThreadpool Interface</span></span>](icorthreadpool-interface.md)
