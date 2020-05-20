---
title: ICorPublishEnum::Skip メソッド
ms.date: 03/30/2017
api_name:
- ICorPublishEnum.Skip
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishEnum::Skip
helpviewer_keywords:
- ICorPublishEnum::Skip method [.NET Framework debugging]
- Skip method, ICorDebugEnum interface [.NET Framework debugging]
ms.assetid: 1680ec06-4ab0-447e-93ad-cdb8693fde5c
topic_type:
- apiref
ms.openlocfilehash: b68a9ec1e8fee4fdecd2114af28c75c4a236cb3a
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2020
ms.locfileid: "83421148"
---
# <a name="icorpublishenumskip-method"></a><span data-ttu-id="3e8a6-102">ICorPublishEnum::Skip メソッド</span><span class="sxs-lookup"><span data-stu-id="3e8a6-102">ICorPublishEnum::Skip Method</span></span>
<span data-ttu-id="3e8a6-103">指定した数の項目だけ、列挙内でカーソルを前方に移動します。</span><span class="sxs-lookup"><span data-stu-id="3e8a6-103">Moves the cursor forward in the enumeration by the specified number of items.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3e8a6-104">構文</span><span class="sxs-lookup"><span data-stu-id="3e8a6-104">Syntax</span></span>  
  
```cpp  
HRESULT Skip (  
    [in] ULONG   celt  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3e8a6-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="3e8a6-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="3e8a6-106">からカーソルを前方に移動する項目の数。</span><span class="sxs-lookup"><span data-stu-id="3e8a6-106">[in] The number of items by which to move the cursor forward.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3e8a6-107">要件</span><span class="sxs-lookup"><span data-stu-id="3e8a6-107">Requirements</span></span>  
 <span data-ttu-id="3e8a6-108">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3e8a6-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3e8a6-109">**ヘッダー:** CorPub .idl、CorPub .h</span><span class="sxs-lookup"><span data-stu-id="3e8a6-109">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="3e8a6-110">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3e8a6-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3e8a6-111">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3e8a6-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e8a6-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="3e8a6-112">See also</span></span>

- [<span data-ttu-id="3e8a6-113">ICorPublishEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3e8a6-113">ICorPublishEnum Interface</span></span>](icorpublishenum-interface.md)
