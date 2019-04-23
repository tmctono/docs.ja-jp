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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bbf5c02972a8331b3dd5e35ffcc4213e094e532d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59175735"
---
# <a name="icorthreadpoolcorgetmaxthreads-method"></a><span data-ttu-id="354ce-102">ICorThreadpool::CorGetMaxThreads メソッド</span><span class="sxs-lookup"><span data-stu-id="354ce-102">ICorThreadpool::CorGetMaxThreads Method</span></span>
<span data-ttu-id="354ce-103">このメソッドは、.NET Framework インフラストラクチャをサポートします。独自に作成したコードから直接使用するためのものではありません。</span><span class="sxs-lookup"><span data-stu-id="354ce-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="354ce-104">構文</span><span class="sxs-lookup"><span data-stu-id="354ce-104">Syntax</span></span>  
  
```  
HRESULT CorGetMaxThreads (  
    [out] DWORD *MaxWorkerThreads,  
    [out] DWORD *MaxIOCompletionThreads  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="354ce-105">必要条件</span><span class="sxs-lookup"><span data-stu-id="354ce-105">Requirements</span></span>  
 <span data-ttu-id="354ce-106">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="354ce-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="354ce-107">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="354ce-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="354ce-108">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="354ce-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="354ce-109">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="354ce-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="354ce-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="354ce-110">See also</span></span>

- [<span data-ttu-id="354ce-111">ICorThreadpool インターフェイス</span><span class="sxs-lookup"><span data-stu-id="354ce-111">ICorThreadpool Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorthreadpool-interface.md)
