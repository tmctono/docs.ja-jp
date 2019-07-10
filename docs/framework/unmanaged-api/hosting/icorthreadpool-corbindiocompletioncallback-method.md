---
title: ICorThreadpool::CorBindIoCompletionCallback メソッド
ms.date: 03/30/2017
api_name:
- ICorThreadpool.CorBindIoCompletionCallback
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorBindIoCompletionCallback
helpviewer_keywords:
- CorBindIoCompletionCallback method [.NET Framework hosting]
- ICorThreadpool::CorBindIoCompletionCallback method [.NET Framework hosting]
ms.assetid: 2b159225-f09c-42f1-aa7c-44087e121249
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 893ec89be83cf68e9b87d4a57bc221feac9932cc
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67770844"
---
# <a name="icorthreadpoolcorbindiocompletioncallback-method"></a><span data-ttu-id="5ed91-102">ICorThreadpool::CorBindIoCompletionCallback メソッド</span><span class="sxs-lookup"><span data-stu-id="5ed91-102">ICorThreadpool::CorBindIoCompletionCallback Method</span></span>
<span data-ttu-id="5ed91-103">このメソッドは、.NET Framework インフラストラクチャをサポートします。独自に作成したコードから直接使用するためのものではありません。</span><span class="sxs-lookup"><span data-stu-id="5ed91-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5ed91-104">構文</span><span class="sxs-lookup"><span data-stu-id="5ed91-104">Syntax</span></span>  
  
```cpp  
HRESULT CorBindIoCompletionCallback (  
    [in] HANDLE                          fileHandle,  
    [in] LPOVERLAPPED_COMPLETION_ROUTINE callback  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="5ed91-105">必要条件</span><span class="sxs-lookup"><span data-stu-id="5ed91-105">Requirements</span></span>  
 <span data-ttu-id="5ed91-106">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5ed91-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5ed91-107">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="5ed91-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5ed91-108">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="5ed91-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5ed91-109">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5ed91-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ed91-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="5ed91-110">See also</span></span>

- [<span data-ttu-id="5ed91-111">ICorThreadpool インターフェイス</span><span class="sxs-lookup"><span data-stu-id="5ed91-111">ICorThreadpool Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorthreadpool-interface.md)
