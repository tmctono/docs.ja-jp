---
title: IGCHost::GetStats メソッド
ms.date: 03/30/2017
api_name:
- IGCHost.GetStats
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- GetStats
helpviewer_keywords:
- GetStats method, IGCHost interface [.NET Framework hosting]
- IGCHost::GetStats method [.NET Framework hosting]
ms.assetid: c4ae022c-46ac-4f19-9ddd-09b955f19412
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 14751b41809eeda5e6bd990fae368879d0f30492
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61927249"
---
# <a name="igchostgetstats-method"></a><span data-ttu-id="dbe6d-102">IGCHost::GetStats メソッド</span><span class="sxs-lookup"><span data-stu-id="dbe6d-102">IGCHost::GetStats Method</span></span>
<span data-ttu-id="dbe6d-103">ガベージ コレクション システムの現在の状態の統計情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="dbe6d-103">Gets the statistics for the current state of the garbage collection system.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dbe6d-104">構文</span><span class="sxs-lookup"><span data-stu-id="dbe6d-104">Syntax</span></span>  
  
```  
HRESULT GetStats (  
    [in, out] COR_GC_STATS *pStats  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dbe6d-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="dbe6d-105">Parameters</span></span>  
 `pStats`  
 <span data-ttu-id="dbe6d-106">[入力、出力]ポインターを[COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md)ガベージ コレクション システムの現在の状態の統計情報を含む構造体。</span><span class="sxs-lookup"><span data-stu-id="dbe6d-106">[in, out] A pointer to a [COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md) structure that contains the statistics for the current state of the garbage collection system.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dbe6d-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="dbe6d-107">Remarks</span></span>  
 <span data-ttu-id="dbe6d-108">統計情報は、スマート配賦システムによってガベージ コレクション システムの動作を使用できます。</span><span class="sxs-lookup"><span data-stu-id="dbe6d-108">The statistics can be used by a smart allocation system to help the garbage collection system operate.</span></span> <span data-ttu-id="dbe6d-109">たとえば、配賦システム可能性があります決定をより多くのメモリを追加またはコレクションを強制する必要がある統計情報を確認した後します。</span><span class="sxs-lookup"><span data-stu-id="dbe6d-109">For example, the allocation system may determine, after reviewing the statistics, that it needs to add more memory or force a collection.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dbe6d-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="dbe6d-110">Requirements</span></span>  
 <span data-ttu-id="dbe6d-111">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="dbe6d-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dbe6d-112">**ヘッダー:** GCHost.idl、GCHost.h</span><span class="sxs-lookup"><span data-stu-id="dbe6d-112">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="dbe6d-113">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="dbe6d-113">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="dbe6d-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dbe6d-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dbe6d-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="dbe6d-115">See also</span></span>

- [<span data-ttu-id="dbe6d-116">IGCHost インターフェイス</span><span class="sxs-lookup"><span data-stu-id="dbe6d-116">IGCHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-interface.md)
