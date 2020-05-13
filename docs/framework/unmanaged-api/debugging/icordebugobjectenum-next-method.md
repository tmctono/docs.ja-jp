---
title: ICorDebugObjectEnum::Next メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugObjectEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugObjectEnum::Next
helpviewer_keywords:
- Next method, ICorDebugObjectEnum interface [.NET Framework debugging]
- ICorDebugObjectEnum::Next method [.NET Framework debugging]
ms.assetid: 10093e3d-26b6-4ad7-8ef3-bbf66243fc02
topic_type:
- apiref
ms.openlocfilehash: 70514464f27d6123a4de1d5800ed016a39541287
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/12/2020
ms.locfileid: "83207555"
---
# <a name="icordebugobjectenumnext-method"></a><span data-ttu-id="ff0c2-102">ICorDebugObjectEnum::Next メソッド</span><span class="sxs-lookup"><span data-stu-id="ff0c2-102">ICorDebugObjectEnum::Next Method</span></span>
<span data-ttu-id="ff0c2-103">列挙から、指定した数のオブジェクトの相対仮想アドレス (RVAs) を取得します。この値は、現在の位置から開始されます。</span><span class="sxs-lookup"><span data-stu-id="ff0c2-103">Gets the relative virtual addresses (RVAs) of the specified number of objects from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ff0c2-104">構文</span><span class="sxs-lookup"><span data-stu-id="ff0c2-104">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)]
        CORDB_ADDRESS objects[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ff0c2-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="ff0c2-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="ff0c2-106">[in] 取得するオブジェクトの数。</span><span class="sxs-lookup"><span data-stu-id="ff0c2-106">[in] The number of objects to be retrieved.</span></span>  
  
 `objects`  
 <span data-ttu-id="ff0c2-107">入出力ポインターの配列。それぞれが CORDB_ADDRESS オブジェクトを指します。</span><span class="sxs-lookup"><span data-stu-id="ff0c2-107">[out] An array of pointers, each of which points to a CORDB_ADDRESS object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="ff0c2-108">入出力実際に返されたオブジェクトの数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="ff0c2-108">[out] Pointer to the number of objects actually returned.</span></span> <span data-ttu-id="ff0c2-109">が1の場合、この値は null `celt` になります。</span><span class="sxs-lookup"><span data-stu-id="ff0c2-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ff0c2-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="ff0c2-110">Requirements</span></span>  
 <span data-ttu-id="ff0c2-111">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ff0c2-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ff0c2-112">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ff0c2-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ff0c2-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ff0c2-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ff0c2-114">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ff0c2-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff0c2-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="ff0c2-115">See also</span></span>
