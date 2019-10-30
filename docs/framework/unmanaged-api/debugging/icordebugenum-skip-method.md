---
title: ICorDebugEnum::Skip メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugEnum.Skip
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEnum::Skip
helpviewer_keywords:
- ICorDebugEnum::Skip method [.NET Framework debugging]
- Skip method, ICorDebugEnum interface [.NET Framework debugging]
ms.assetid: e925d88a-67a5-4f76-88b8-09cedeed0232
topic_type:
- apiref
ms.openlocfilehash: 2c5cd7435ec34e852b80031cfe0310ee517b7bc5
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73103471"
---
# <a name="icordebugenumskip-method"></a><span data-ttu-id="21bc1-102">ICorDebugEnum::Skip メソッド</span><span class="sxs-lookup"><span data-stu-id="21bc1-102">ICorDebugEnum::Skip Method</span></span>
<span data-ttu-id="21bc1-103">指定した数の項目だけ、列挙内でカーソルを前方に移動します。</span><span class="sxs-lookup"><span data-stu-id="21bc1-103">Moves the cursor forward in the enumeration by the specified number of items.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="21bc1-104">構文</span><span class="sxs-lookup"><span data-stu-id="21bc1-104">Syntax</span></span>  
  
```cpp  
HRESULT Skip (  
    [in] ULONG celt  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="21bc1-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="21bc1-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="21bc1-106">からカーソルを前方に移動する項目の数。</span><span class="sxs-lookup"><span data-stu-id="21bc1-106">[in] The number of items by which to move the cursor forward.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="21bc1-107">［要件］</span><span class="sxs-lookup"><span data-stu-id="21bc1-107">Requirements</span></span>  
 <span data-ttu-id="21bc1-108">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="21bc1-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="21bc1-109">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="21bc1-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="21bc1-110">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="21bc1-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="21bc1-111">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="21bc1-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21bc1-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="21bc1-112">See also</span></span>

- [<span data-ttu-id="21bc1-113">ICorDebugEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="21bc1-113">ICorDebugEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugenum-interface1.md)
