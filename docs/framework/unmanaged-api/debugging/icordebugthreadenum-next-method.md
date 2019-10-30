---
title: ICorDebugThreadEnum::Next メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugThreadEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThreadEnum::Next
helpviewer_keywords:
- ICorDebugThreadEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugThreadEnum interface [.NET Framework debugging]
ms.assetid: f967c93d-9a7f-4aaf-99a1-a1317899ff3f
topic_type:
- apiref
ms.openlocfilehash: 0c455706b0d644d2444e9fbdf49c5a5d4f5295a9
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122386"
---
# <a name="icordebugthreadenumnext-method"></a><span data-ttu-id="dd7ae-102">ICorDebugThreadEnum::Next メソッド</span><span class="sxs-lookup"><span data-stu-id="dd7ae-102">ICorDebugThreadEnum::Next Method</span></span>
<span data-ttu-id="dd7ae-103">現在の位置から開始して、列挙体から指定されたスレッドインスタンスの数を取得します。</span><span class="sxs-lookup"><span data-stu-id="dd7ae-103">Gets the number of specified ICorDebugThread instances from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dd7ae-104">構文</span><span class="sxs-lookup"><span data-stu-id="dd7ae-104">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugThread *threads[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dd7ae-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="dd7ae-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="dd7ae-106">から取得する `ICorDebugThread` インスタンスの数。</span><span class="sxs-lookup"><span data-stu-id="dd7ae-106">[in] The number of `ICorDebugThread` instances to be retrieved.</span></span>  
  
 `threads`  
 <span data-ttu-id="dd7ae-107">入出力ポインターの配列。各ポインターは、スレッドを表す `ICorDebugThread` オブジェクトを指します。</span><span class="sxs-lookup"><span data-stu-id="dd7ae-107">[out] An array of pointers, each of which points to an `ICorDebugThread` object that represents a thread.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="dd7ae-108">入出力実際に返された `ICorDebugThread` インスタンスの数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="dd7ae-108">[out] Pointer to the number of `ICorDebugThread` instances actually returned.</span></span> <span data-ttu-id="dd7ae-109">`celt` が1の場合、この値は null になります。</span><span class="sxs-lookup"><span data-stu-id="dd7ae-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dd7ae-110">［要件］</span><span class="sxs-lookup"><span data-stu-id="dd7ae-110">Requirements</span></span>  
 <span data-ttu-id="dd7ae-111">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dd7ae-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dd7ae-112">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="dd7ae-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="dd7ae-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dd7ae-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dd7ae-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dd7ae-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
