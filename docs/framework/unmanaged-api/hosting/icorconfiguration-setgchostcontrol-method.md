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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 50a92058e8a394b95c690d19f1bafdddbed8246a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59135994"
---
# <a name="icorconfigurationsetgchostcontrol-method"></a><span data-ttu-id="eae7b-102">ICorConfiguration::SetGCHostControl メソッド</span><span class="sxs-lookup"><span data-stu-id="eae7b-102">ICorConfiguration::SetGCHostControl Method</span></span>
<span data-ttu-id="eae7b-103">仮想メモリの制限を変更するホストに要求、ガベージ コレクターで使用されるコールバック インターフェイスを設定します。</span><span class="sxs-lookup"><span data-stu-id="eae7b-103">Sets the callback interface to be used by the garbage collector to request the host to change the limits of virtual memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eae7b-104">構文</span><span class="sxs-lookup"><span data-stu-id="eae7b-104">Syntax</span></span>  
  
```  
HRESULT SetGCHostControl (  
    [in] IGCHostControl* pGCHostControl  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="eae7b-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="eae7b-105">Parameters</span></span>  
 `pGCHostControl`  
 <span data-ttu-id="eae7b-106">[in]ポインター、 [IGCHostControl](../../../../docs/framework/unmanaged-api/hosting/igchostcontrol-interface.md)ガベージ コレクターは、仮想メモリの制限を変更するホストを要求できるようにするオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="eae7b-106">[in] A pointer to an [IGCHostControl](../../../../docs/framework/unmanaged-api/hosting/igchostcontrol-interface.md) object that allows the garbage collector to request the host to change the limits of virtual memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eae7b-107">必要条件</span><span class="sxs-lookup"><span data-stu-id="eae7b-107">Requirements</span></span>  
 <span data-ttu-id="eae7b-108">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="eae7b-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eae7b-109">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="eae7b-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="eae7b-110">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="eae7b-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="eae7b-111">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="eae7b-111">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="eae7b-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="eae7b-112">See also</span></span>

- [<span data-ttu-id="eae7b-113">ICorConfiguration インターフェイス</span><span class="sxs-lookup"><span data-stu-id="eae7b-113">ICorConfiguration Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-interface.md)
