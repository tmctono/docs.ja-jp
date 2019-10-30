---
title: ICLRTaskManager::GetCurrentTaskType メソッド
ms.date: 03/30/2017
api_name:
- ICLRTaskManager.GetCurrentTaskType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTaskManager::GetCurrentTaskType
helpviewer_keywords:
- GetCurrentTaskType method [.NET Framework hosting]
- ICLRTaskManager::GetCurrentTaskType method [.NET Framework hosting]
ms.assetid: 6b0d9259-dbe2-45bb-b34d-990f60c73424
topic_type:
- apiref
ms.openlocfilehash: 848255d44ce8637182f18288d30151a3f0df0912
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73092163"
---
# <a name="iclrtaskmanagergetcurrenttasktype-method"></a><span data-ttu-id="ebd32-102">ICLRTaskManager::GetCurrentTaskType メソッド</span><span class="sxs-lookup"><span data-stu-id="ebd32-102">ICLRTaskManager::GetCurrentTaskType Method</span></span>
<span data-ttu-id="ebd32-103">現在実行中のタスクの種類を取得します。</span><span class="sxs-lookup"><span data-stu-id="ebd32-103">Gets the type of the task that is currently executing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ebd32-104">構文</span><span class="sxs-lookup"><span data-stu-id="ebd32-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCurrentTaskType(  
    [out] ETaskType *pTaskType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ebd32-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="ebd32-105">Parameters</span></span>  
 `pTaskType`  
 <span data-ttu-id="ebd32-106">入出力現在実行中のタスクの種類を示す[Etasktype](../../../../docs/framework/unmanaged-api/hosting/etasktype-enumeration.md)列挙値へのポインター。</span><span class="sxs-lookup"><span data-stu-id="ebd32-106">[out] A pointer to a value of the [ETaskType](../../../../docs/framework/unmanaged-api/hosting/etasktype-enumeration.md) enumeration that indicates the type of task that is currently executing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ebd32-107">［要件］</span><span class="sxs-lookup"><span data-stu-id="ebd32-107">Requirements</span></span>  
 <span data-ttu-id="ebd32-108">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ebd32-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ebd32-109">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="ebd32-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ebd32-110">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="ebd32-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ebd32-111">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ebd32-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ebd32-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="ebd32-112">See also</span></span>

- [<span data-ttu-id="ebd32-113">ICLRTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ebd32-113">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
