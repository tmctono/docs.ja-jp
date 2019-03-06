---
title: ICorDebugFrameEnum::Next メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugFrameEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrameEnum::Next
helpviewer_keywords:
- ICorDebugFrameEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugFrameEnum interface [.NET Framework debugging]
ms.assetid: 0bc96acb-6179-4328-a447-cda562ce9e98
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 68098895b2ad7f5c08d30f222777e52d4ee3f063
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57476660"
---
# <a name="icordebugframeenumnext-method"></a><span data-ttu-id="bb3b4-102">ICorDebugFrameEnum::Next メソッド</span><span class="sxs-lookup"><span data-stu-id="bb3b4-102">ICorDebugFrameEnum::Next Method</span></span>
<span data-ttu-id="bb3b4-103">ICorDebugFrame インスタンスの現在位置から指定の数を取得します。</span><span class="sxs-lookup"><span data-stu-id="bb3b4-103">Gets the specified number of ICorDebugFrame instances, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bb3b4-104">構文</span><span class="sxs-lookup"><span data-stu-id="bb3b4-104">Syntax</span></span>  
  
```  
HRESULT Next (  
    [in] ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugFrame *frames[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bb3b4-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="bb3b4-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="bb3b4-106">[in]数`ICorDebugFrame`インスタンスを取得します。</span><span class="sxs-lookup"><span data-stu-id="bb3b4-106">[in] The number of `ICorDebugFrame` instances to be retrieved.</span></span>  
  
 `frames`  
 <span data-ttu-id="bb3b4-107">[out]それぞれが指すポインターの配列、`ICorDebugFrame`オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="bb3b4-107">[out] An array of pointers, each of which points to an `ICorDebugFrame` object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="bb3b4-108">[out]数へのポインター`ICorDebugFrame`インスタンスが実際に返されます。</span><span class="sxs-lookup"><span data-stu-id="bb3b4-108">[out] A pointer to the number of `ICorDebugFrame` instances actually returned.</span></span> <span data-ttu-id="bb3b4-109">この値は null になる場合`celt`は 1 つです。</span><span class="sxs-lookup"><span data-stu-id="bb3b4-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bb3b4-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="bb3b4-110">Requirements</span></span>  
 <span data-ttu-id="bb3b4-111">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="bb3b4-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bb3b4-112">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bb3b4-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bb3b4-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bb3b4-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bb3b4-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bb3b4-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
