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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1e2d7a344cabb1ab816e4fe696ebb47276397ec3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61774557"
---
# <a name="icordebugenumskip-method"></a><span data-ttu-id="96a72-102">ICorDebugEnum::Skip メソッド</span><span class="sxs-lookup"><span data-stu-id="96a72-102">ICorDebugEnum::Skip Method</span></span>
<span data-ttu-id="96a72-103">指定数の項目では、列挙体にカーソルを移動します。</span><span class="sxs-lookup"><span data-stu-id="96a72-103">Moves the cursor forward in the enumeration by the specified number of items.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="96a72-104">構文</span><span class="sxs-lookup"><span data-stu-id="96a72-104">Syntax</span></span>  
  
```  
HRESULT Skip (  
    [in] ULONG celt  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="96a72-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="96a72-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="96a72-106">[in]カーソルを前方に移動する項目の数。</span><span class="sxs-lookup"><span data-stu-id="96a72-106">[in] The number of items by which to move the cursor forward.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="96a72-107">必要条件</span><span class="sxs-lookup"><span data-stu-id="96a72-107">Requirements</span></span>  
 <span data-ttu-id="96a72-108">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="96a72-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="96a72-109">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="96a72-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="96a72-110">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="96a72-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="96a72-111">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="96a72-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96a72-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="96a72-112">See also</span></span>

- [<span data-ttu-id="96a72-113">ICorDebugEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="96a72-113">ICorDebugEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugenum-interface1.md)
