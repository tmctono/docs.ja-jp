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
ms.openlocfilehash: 64d9db09b3e604247ab6a26cdca9eca22adbaace
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2020
ms.locfileid: "82976305"
---
# <a name="icordebugenumskip-method"></a><span data-ttu-id="e6548-102">ICorDebugEnum::Skip メソッド</span><span class="sxs-lookup"><span data-stu-id="e6548-102">ICorDebugEnum::Skip Method</span></span>
<span data-ttu-id="e6548-103">指定した数の項目だけ、列挙内でカーソルを前方に移動します。</span><span class="sxs-lookup"><span data-stu-id="e6548-103">Moves the cursor forward in the enumeration by the specified number of items.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e6548-104">構文</span><span class="sxs-lookup"><span data-stu-id="e6548-104">Syntax</span></span>  
  
```cpp  
HRESULT Skip (  
    [in] ULONG celt  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e6548-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e6548-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="e6548-106">からカーソルを前方に移動する項目の数。</span><span class="sxs-lookup"><span data-stu-id="e6548-106">[in] The number of items by which to move the cursor forward.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e6548-107">必要条件</span><span class="sxs-lookup"><span data-stu-id="e6548-107">Requirements</span></span>  
 <span data-ttu-id="e6548-108">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e6548-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e6548-109">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e6548-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e6548-110">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e6548-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e6548-111">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e6548-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6548-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="e6548-112">See also</span></span>

- [<span data-ttu-id="e6548-113">ICorDebugEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e6548-113">ICorDebugEnum Interface</span></span>](icordebugenum-interface1.md)
