---
title: ICorThreadpool::CorDeleteTimer メソッド
ms.date: 03/30/2017
api_name:
- ICorThreadpool.CorDeleteTimer
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorDeleteTimer
helpviewer_keywords:
- ICorThreadpool::CorDeleteTimer method [.NET Framework hosting]
- CorDeleteTimer method [.NET Framework hosting]
ms.assetid: 74847c35-7ca1-466a-b750-b25e7b03d100
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 098c23dd0ddff4342aa4cefbaa4e149ed95a1cb3
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59178348"
---
# <a name="icorthreadpoolcordeletetimer-method"></a><span data-ttu-id="11112-102">ICorThreadpool::CorDeleteTimer メソッド</span><span class="sxs-lookup"><span data-stu-id="11112-102">ICorThreadpool::CorDeleteTimer Method</span></span>
<span data-ttu-id="11112-103">このメソッドは、.NET Framework インフラストラクチャをサポートします。独自に作成したコードから直接使用するためのものではありません。</span><span class="sxs-lookup"><span data-stu-id="11112-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="11112-104">構文</span><span class="sxs-lookup"><span data-stu-id="11112-104">Syntax</span></span>  
  
```  
HRESULT CorDeleteTimer (  
    [in]  HANDLE Timer,  
    [in]  HANDLE CompletionEvent,  
    [out] BOOL*  result  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="11112-105">必要条件</span><span class="sxs-lookup"><span data-stu-id="11112-105">Requirements</span></span>  
 <span data-ttu-id="11112-106">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="11112-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="11112-107">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="11112-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="11112-108">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="11112-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="11112-109">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="11112-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11112-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="11112-110">See also</span></span>

- [<span data-ttu-id="11112-111">ICorThreadpool インターフェイス</span><span class="sxs-lookup"><span data-stu-id="11112-111">ICorThreadpool Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorthreadpool-interface.md)
