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
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59227835"
---
# <a name="igchostgetstats-method"></a><span data-ttu-id="d1eba-102">IGCHost::GetStats メソッド</span><span class="sxs-lookup"><span data-stu-id="d1eba-102">IGCHost::GetStats Method</span></span>
<span data-ttu-id="d1eba-103">ガベージ コレクション システムの現在の状態の統計情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="d1eba-103">Gets the statistics for the current state of the garbage collection system.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d1eba-104">構文</span><span class="sxs-lookup"><span data-stu-id="d1eba-104">Syntax</span></span>  
  
```  
HRESULT GetStats (  
    [in, out] COR_GC_STATS *pStats  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d1eba-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d1eba-105">Parameters</span></span>  
 `pStats`  
 <span data-ttu-id="d1eba-106">[入力、出力]ポインターを[COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md)ガベージ コレクション システムの現在の状態の統計情報を含む構造体。</span><span class="sxs-lookup"><span data-stu-id="d1eba-106">[in, out] A pointer to a [COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md) structure that contains the statistics for the current state of the garbage collection system.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d1eba-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="d1eba-107">Remarks</span></span>  
 <span data-ttu-id="d1eba-108">統計情報は、スマート配賦システムによってガベージ コレクション システムの動作を使用できます。</span><span class="sxs-lookup"><span data-stu-id="d1eba-108">The statistics can be used by a smart allocation system to help the garbage collection system operate.</span></span> <span data-ttu-id="d1eba-109">たとえば、配賦システム可能性があります決定をより多くのメモリを追加またはコレクションを強制する必要がある統計情報を確認した後します。</span><span class="sxs-lookup"><span data-stu-id="d1eba-109">For example, the allocation system may determine, after reviewing the statistics, that it needs to add more memory or force a collection.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d1eba-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="d1eba-110">Requirements</span></span>  
 <span data-ttu-id="d1eba-111">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d1eba-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d1eba-112">**ヘッダー:** GCHost.idl、GCHost.h</span><span class="sxs-lookup"><span data-stu-id="d1eba-112">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="d1eba-113">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="d1eba-113">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="d1eba-114">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="d1eba-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="d1eba-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="d1eba-115">See also</span></span>

- [<span data-ttu-id="d1eba-116">IGCHost インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d1eba-116">IGCHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-interface.md)
