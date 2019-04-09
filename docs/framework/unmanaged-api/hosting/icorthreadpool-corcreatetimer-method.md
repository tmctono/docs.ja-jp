---
title: ICorThreadpool::CorCreateTimer メソッド
ms.date: 03/30/2017
api_name:
- ICorThreadpool.CorCreateTimer
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorCreateTimer
helpviewer_keywords:
- CorCreateTimer method [.NET Framework hosting]
- ICorThreadpool::CorCreateTimer method [.NET Framework hosting]
ms.assetid: 0d56ef25-30f1-4499-8a1f-76e7654ec614
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 69090618501abe7530ac7a04ae89a6bd3582e029
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59111164"
---
# <a name="icorthreadpoolcorcreatetimer-method"></a><span data-ttu-id="0ca0f-102">ICorThreadpool::CorCreateTimer メソッド</span><span class="sxs-lookup"><span data-stu-id="0ca0f-102">ICorThreadpool::CorCreateTimer Method</span></span>
<span data-ttu-id="0ca0f-103">このメソッドは、.NET Framework インフラストラクチャをサポートします。独自に作成したコードから直接使用するためのものではありません。</span><span class="sxs-lookup"><span data-stu-id="0ca0f-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0ca0f-104">構文</span><span class="sxs-lookup"><span data-stu-id="0ca0f-104">Syntax</span></span>  
  
```  
HRESULT CorCreateTimer (  
    [in]  HANDLE*             phNewTimer,  
    [in]  WAITORTIMERCALLBACK Callback,  
    [in]  PVOID               Parameter,  
    [in]  DWORD               DueTime,  
    [in]  DWORD               Period,  
    [out] BOOL*               result  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="0ca0f-105">必要条件</span><span class="sxs-lookup"><span data-stu-id="0ca0f-105">Requirements</span></span>  
 <span data-ttu-id="0ca0f-106">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="0ca0f-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0ca0f-107">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="0ca0f-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0ca0f-108">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="0ca0f-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="0ca0f-109">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="0ca0f-109">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="0ca0f-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="0ca0f-110">See also</span></span>

- [<span data-ttu-id="0ca0f-111">ICorThreadpool インターフェイス</span><span class="sxs-lookup"><span data-stu-id="0ca0f-111">ICorThreadpool Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorthreadpool-interface.md)
