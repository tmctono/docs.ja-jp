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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 739670fb84eb0145fd8bf8073f453518487c38b0
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67749574"
---
# <a name="ihosttaskmanagergetstackguarantee-method"></a><span data-ttu-id="c1852-102">IHostTaskManager::GetStackGuarantee メソッド</span><span class="sxs-lookup"><span data-stu-id="c1852-102">IHostTaskManager::GetStackGuarantee Method</span></span>
<span data-ttu-id="c1852-103">プロセスの終了前に、スタック操作の完了後に、使用することが保証されるスタック領域の量を取得します。</span><span class="sxs-lookup"><span data-stu-id="c1852-103">Gets the amount of stack space that is guaranteed to be available after a stack operation completes, but before the closing of a process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c1852-104">構文</span><span class="sxs-lookup"><span data-stu-id="c1852-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStackGuarantee(  
    [out] ULONG *pGuarantee  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c1852-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c1852-105">Parameters</span></span>  
 `pGuarantee`  
 <span data-ttu-id="c1852-106">[out]使用できるバイト数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="c1852-106">[out] A pointer to the number of bytes that are available.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c1852-107">必要条件</span><span class="sxs-lookup"><span data-stu-id="c1852-107">Requirements</span></span>  
 <span data-ttu-id="c1852-108">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c1852-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c1852-109">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="c1852-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c1852-110">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="c1852-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c1852-111">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c1852-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1852-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="c1852-112">See also</span></span>

- [<span data-ttu-id="c1852-113">IHostTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c1852-113">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
