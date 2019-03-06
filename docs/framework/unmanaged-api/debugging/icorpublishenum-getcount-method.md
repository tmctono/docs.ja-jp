---
title: ICorPublishEnum::GetCount メソッド
ms.date: 03/30/2017
api_name:
- ICorPublishEnum.GetCount
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishEnum::GetCount
helpviewer_keywords:
- GetCount method, ICorPublishEnum interface [.NET Framework debugging]
- ICorPublishEnum::GetCount method [.NET Framework debugging]
ms.assetid: d228f684-2be3-4029-93ae-31fe02213c1f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c353edf9db0a7bc7ec0a25f712527dc3c9d8cc28
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57484655"
---
# <a name="icorpublishenumgetcount-method"></a><span data-ttu-id="bbe60-102">ICorPublishEnum::GetCount メソッド</span><span class="sxs-lookup"><span data-stu-id="bbe60-102">ICorPublishEnum::GetCount Method</span></span>
<span data-ttu-id="bbe60-103">列挙に含まれる項目の数を取得します。</span><span class="sxs-lookup"><span data-stu-id="bbe60-103">Gets the number of items in the enumeration.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bbe60-104">構文</span><span class="sxs-lookup"><span data-stu-id="bbe60-104">Syntax</span></span>  
  
```  
HRESULT GetCount (  
    [out] ULONG   *pcelt  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bbe60-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="bbe60-105">Parameters</span></span>  
 `pcelt`  
 <span data-ttu-id="bbe60-106">[out]列挙に含まれる項目数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="bbe60-106">[out] A pointer to the number of items in the enumeration.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bbe60-107">必要条件</span><span class="sxs-lookup"><span data-stu-id="bbe60-107">Requirements</span></span>  
 <span data-ttu-id="bbe60-108">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="bbe60-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bbe60-109">**ヘッダー:** CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="bbe60-109">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="bbe60-110">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bbe60-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bbe60-111">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bbe60-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bbe60-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="bbe60-112">See also</span></span>
- [<span data-ttu-id="bbe60-113">ICorPublishEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="bbe60-113">ICorPublishEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md)
