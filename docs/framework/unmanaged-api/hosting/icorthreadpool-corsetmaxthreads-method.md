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
ms.openlocfilehash: 7f972bcfedd028d85debbbd60968a57c4d64ee0c
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/21/2020
ms.locfileid: "83760341"
---
# <a name="icorthreadpoolcorsetmaxthreads-method"></a><span data-ttu-id="539f1-102">ICorThreadpool::CorSetMaxThreads メソッド</span><span class="sxs-lookup"><span data-stu-id="539f1-102">ICorThreadpool::CorSetMaxThreads Method</span></span>
<span data-ttu-id="539f1-103">このメソッドは、.NET Framework インフラストラクチャをサポートします。独自に作成したコードから直接使用するためのものではありません。</span><span class="sxs-lookup"><span data-stu-id="539f1-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="539f1-104">構文</span><span class="sxs-lookup"><span data-stu-id="539f1-104">Syntax</span></span>  
  
```cpp  
HRESULT CorSetMaxThreads (  
    [in] DWORD MaxWorkerThreads,  
    [in] DWORD MaxIOCompletionThreads  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="539f1-105">要件</span><span class="sxs-lookup"><span data-stu-id="539f1-105">Requirements</span></span>  
 <span data-ttu-id="539f1-106">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="539f1-106">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="539f1-107">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="539f1-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="539f1-108">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="539f1-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="539f1-109">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="539f1-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="539f1-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="539f1-110">See also</span></span>

- [<span data-ttu-id="539f1-111">ICorThreadpool インターフェイス</span><span class="sxs-lookup"><span data-stu-id="539f1-111">ICorThreadpool Interface</span></span>](icorthreadpool-interface.md)
