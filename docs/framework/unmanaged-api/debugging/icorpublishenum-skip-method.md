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
ms.openlocfilehash: bd62fb38352022f69c45d2a5921973cfbec1c6e4
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790590"
---
# <a name="icorpublishenumskip-method"></a><span data-ttu-id="20be3-102">ICorPublishEnum::Skip メソッド</span><span class="sxs-lookup"><span data-stu-id="20be3-102">ICorPublishEnum::Skip Method</span></span>
<span data-ttu-id="20be3-103">指定した数の項目だけ、列挙内でカーソルを前方に移動します。</span><span class="sxs-lookup"><span data-stu-id="20be3-103">Moves the cursor forward in the enumeration by the specified number of items.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="20be3-104">構文</span><span class="sxs-lookup"><span data-stu-id="20be3-104">Syntax</span></span>  
  
```cpp  
HRESULT Skip (  
    [in] ULONG   celt  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="20be3-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="20be3-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="20be3-106">からカーソルを前方に移動する項目の数。</span><span class="sxs-lookup"><span data-stu-id="20be3-106">[in] The number of items by which to move the cursor forward.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="20be3-107">要件</span><span class="sxs-lookup"><span data-stu-id="20be3-107">Requirements</span></span>  
 <span data-ttu-id="20be3-108">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="20be3-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="20be3-109">**ヘッダー:** CorPub .idl、CorPub .h</span><span class="sxs-lookup"><span data-stu-id="20be3-109">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="20be3-110">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="20be3-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="20be3-111">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="20be3-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20be3-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="20be3-112">See also</span></span>

- [<span data-ttu-id="20be3-113">ICorPublishEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="20be3-113">ICorPublishEnum Interface</span></span>](icorpublishenum-interface.md)
