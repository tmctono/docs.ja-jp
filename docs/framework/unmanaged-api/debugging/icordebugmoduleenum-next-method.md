---
title: ICorDebugModuleEnum::Next メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugModuleEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModuleEnum::Next
helpviewer_keywords:
- ICorDebugModuleEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugModuleEnum interface [.NET Framework debugging]
ms.assetid: 9ff3fcd6-38fe-41f8-bfd3-f0ab6c7d77ca
topic_type:
- apiref
ms.openlocfilehash: 6c4262c18e4efcbbca1b3e2a327fec7d4b609a31
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73096926"
---
# <a name="icordebugmoduleenumnext-method"></a><span data-ttu-id="5f3e3-102">ICorDebugModuleEnum::Next メソッド</span><span class="sxs-lookup"><span data-stu-id="5f3e3-102">ICorDebugModuleEnum::Next Method</span></span>
<span data-ttu-id="5f3e3-103">現在の位置から開始して、`celt` によって指定された、列挙からの "" のインスタンスの数を取得します。</span><span class="sxs-lookup"><span data-stu-id="5f3e3-103">Gets the number of "ICorDebugModule" instances specified by `celt` from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5f3e3-104">構文</span><span class="sxs-lookup"><span data-stu-id="5f3e3-104">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in]  ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugModule *modules[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5f3e3-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="5f3e3-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="5f3e3-106">から取得する `ICorDebugModule` インスタンスの数。</span><span class="sxs-lookup"><span data-stu-id="5f3e3-106">[in] The number of `ICorDebugModule` instances to be retrieved.</span></span>  
  
 `modules`  
 <span data-ttu-id="5f3e3-107">入出力ポインターの配列。それぞれが `ICorDebugModule` オブジェクトを指します。</span><span class="sxs-lookup"><span data-stu-id="5f3e3-107">[out] An array of pointers, each of which points to an `ICorDebugModule` object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="5f3e3-108">入出力実際に返された `ICorDebugModule` インスタンスの数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="5f3e3-108">[out] Pointer to the number of `ICorDebugModule` instances actually returned.</span></span> <span data-ttu-id="5f3e3-109">`celt` が1の場合、この値は null になります。</span><span class="sxs-lookup"><span data-stu-id="5f3e3-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5f3e3-110">［要件］</span><span class="sxs-lookup"><span data-stu-id="5f3e3-110">Requirements</span></span>  
 <span data-ttu-id="5f3e3-111">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5f3e3-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5f3e3-112">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5f3e3-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5f3e3-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5f3e3-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5f3e3-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5f3e3-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f3e3-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="5f3e3-115">See also</span></span>
