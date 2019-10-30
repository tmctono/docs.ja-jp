---
title: ICorConfiguration::SetGCHostControl メソッド
ms.date: 03/30/2017
api_name:
- ICorConfiguration.SetGCHostControl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- SetGCHostControl
helpviewer_keywords:
- ICorConfiguration::SetGCHostControl method [.NET Framework hosting]
- SetGCHostControl method [.NET Framework hosting]
ms.assetid: bca6bd79-e288-475a-aa46-6bf81541d966
topic_type:
- apiref
ms.openlocfilehash: 5a32fb0480e76f47495590a29c329f54722e2dee
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127774"
---
# <a name="icorconfigurationsetgchostcontrol-method"></a><span data-ttu-id="384ff-102">ICorConfiguration::SetGCHostControl メソッド</span><span class="sxs-lookup"><span data-stu-id="384ff-102">ICorConfiguration::SetGCHostControl Method</span></span>
<span data-ttu-id="384ff-103">仮想メモリの制限を変更するようにホストに要求するために、ガベージコレクターによって使用されるコールバックインターフェイスを設定します。</span><span class="sxs-lookup"><span data-stu-id="384ff-103">Sets the callback interface to be used by the garbage collector to request the host to change the limits of virtual memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="384ff-104">構文</span><span class="sxs-lookup"><span data-stu-id="384ff-104">Syntax</span></span>  
  
```cpp  
HRESULT SetGCHostControl (  
    [in] IGCHostControl* pGCHostControl  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="384ff-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="384ff-105">Parameters</span></span>  
 `pGCHostControl`  
 <span data-ttu-id="384ff-106">からガベージコレクターが仮想メモリの制限を変更するようにホストに要求できるようにする、 [igている Stcontrol](../../../../docs/framework/unmanaged-api/hosting/igchostcontrol-interface.md)オブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="384ff-106">[in] A pointer to an [IGCHostControl](../../../../docs/framework/unmanaged-api/hosting/igchostcontrol-interface.md) object that allows the garbage collector to request the host to change the limits of virtual memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="384ff-107">［要件］</span><span class="sxs-lookup"><span data-stu-id="384ff-107">Requirements</span></span>  
 <span data-ttu-id="384ff-108">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="384ff-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="384ff-109">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="384ff-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="384ff-110">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="384ff-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="384ff-111">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="384ff-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="384ff-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="384ff-112">See also</span></span>

- [<span data-ttu-id="384ff-113">ICorConfiguration インターフェイス</span><span class="sxs-lookup"><span data-stu-id="384ff-113">ICorConfiguration Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-interface.md)
