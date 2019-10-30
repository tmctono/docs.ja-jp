---
title: IHostTaskManager::GetStackGuarantee メソッド
ms.date: 03/30/2017
api_name:
- IHostTaskManager.GetStackGuarantee
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::GetStackGuarantee
helpviewer_keywords:
- GetStackGuarantee method [.NET Framework hosting]
- IHostTaskManager::GetStackGuarantee method [.NET Framework hosting]
ms.assetid: 8176d732-c25c-4520-811d-e3310f339947
topic_type:
- apiref
ms.openlocfilehash: 22ec34c82d0f8e550dfc8941f2c048ebed6cf1d7
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133034"
---
# <a name="ihosttaskmanagergetstackguarantee-method"></a><span data-ttu-id="88ad6-102">IHostTaskManager::GetStackGuarantee メソッド</span><span class="sxs-lookup"><span data-stu-id="88ad6-102">IHostTaskManager::GetStackGuarantee Method</span></span>
<span data-ttu-id="88ad6-103">スタック操作が完了した後、プロセスが終了する前に使用可能であることが保証されているスタック領域の量を取得します。</span><span class="sxs-lookup"><span data-stu-id="88ad6-103">Gets the amount of stack space that is guaranteed to be available after a stack operation completes, but before the closing of a process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="88ad6-104">構文</span><span class="sxs-lookup"><span data-stu-id="88ad6-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStackGuarantee(  
    [out] ULONG *pGuarantee  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="88ad6-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="88ad6-105">Parameters</span></span>  
 `pGuarantee`  
 <span data-ttu-id="88ad6-106">入出力使用可能なバイト数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="88ad6-106">[out] A pointer to the number of bytes that are available.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="88ad6-107">［要件］</span><span class="sxs-lookup"><span data-stu-id="88ad6-107">Requirements</span></span>  
 <span data-ttu-id="88ad6-108">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="88ad6-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="88ad6-109">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="88ad6-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="88ad6-110">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="88ad6-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="88ad6-111">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="88ad6-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="88ad6-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="88ad6-112">See also</span></span>

- [<span data-ttu-id="88ad6-113">IHostTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="88ad6-113">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
