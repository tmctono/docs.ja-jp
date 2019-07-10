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
ms.openlocfilehash: a23c2793dce5be459b3aa0f183179c584592c115
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67779874"
---
# <a name="icorconfigurationsetgchostcontrol-method"></a><span data-ttu-id="9ce83-102">ICorConfiguration::SetGCHostControl メソッド</span><span class="sxs-lookup"><span data-stu-id="9ce83-102">ICorConfiguration::SetGCHostControl Method</span></span>
<span data-ttu-id="9ce83-103">仮想メモリの制限を変更するホストに要求、ガベージ コレクターで使用されるコールバック インターフェイスを設定します。</span><span class="sxs-lookup"><span data-stu-id="9ce83-103">Sets the callback interface to be used by the garbage collector to request the host to change the limits of virtual memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9ce83-104">構文</span><span class="sxs-lookup"><span data-stu-id="9ce83-104">Syntax</span></span>  
  
```cpp  
HRESULT SetGCHostControl (  
    [in] IGCHostControl* pGCHostControl  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9ce83-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="9ce83-105">Parameters</span></span>  
 `pGCHostControl`  
 <span data-ttu-id="9ce83-106">[in]ポインター、 [IGCHostControl](../../../../docs/framework/unmanaged-api/hosting/igchostcontrol-interface.md)ガベージ コレクターは、仮想メモリの制限を変更するホストを要求できるようにするオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="9ce83-106">[in] A pointer to an [IGCHostControl](../../../../docs/framework/unmanaged-api/hosting/igchostcontrol-interface.md) object that allows the garbage collector to request the host to change the limits of virtual memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9ce83-107">必要条件</span><span class="sxs-lookup"><span data-stu-id="9ce83-107">Requirements</span></span>  
 <span data-ttu-id="9ce83-108">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="9ce83-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9ce83-109">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="9ce83-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9ce83-110">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="9ce83-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9ce83-111">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9ce83-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ce83-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="9ce83-112">See also</span></span>

- [<span data-ttu-id="9ce83-113">ICorConfiguration インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9ce83-113">ICorConfiguration Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-interface.md)
