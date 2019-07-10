---
title: ICorDebugProcessEnum::Next メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugProcessEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcessEnum::Next
helpviewer_keywords:
- Next method, ICorDebugProcessEnum interface [.NET Framework debugging]
- ICorDebugProcessEnum::Next method [.NET Framework debugging]
ms.assetid: 4ac7077c-8d88-49c4-b360-b3af0c541c63
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 59efdb76c000a78007ec0321202793ed0dd50cfb
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67768279"
---
# <a name="icordebugprocessenumnext-method"></a><span data-ttu-id="ed589-102">ICorDebugProcessEnum::Next メソッド</span><span class="sxs-lookup"><span data-stu-id="ed589-102">ICorDebugProcessEnum::Next Method</span></span>
<span data-ttu-id="ed589-103">現在の位置から始まり、列挙体から ICorDebugProcess インスタンスの指定した数を取得します。</span><span class="sxs-lookup"><span data-stu-id="ed589-103">Gets the specified number of ICorDebugProcess instances from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ed589-104">構文</span><span class="sxs-lookup"><span data-stu-id="ed589-104">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in]  ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugProcess *processes[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ed589-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="ed589-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="ed589-106">[in]数`ICorDebugProcess`インスタンスを取得します。</span><span class="sxs-lookup"><span data-stu-id="ed589-106">[in] The number of `ICorDebugProcess` instances to be retrieved.</span></span>  
  
 `processes`  
 <span data-ttu-id="ed589-107">[out]それぞれが指すポインターの配列、`ICorDebugProcess`プロセスを表すオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="ed589-107">[out] An array of pointers, each of which points to an `ICorDebugProcess` object that represents a process.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="ed589-108">[out]数へのポインター`ICorDebugProcess`インスタンスが実際に返されます。</span><span class="sxs-lookup"><span data-stu-id="ed589-108">[out] Pointer to the number of `ICorDebugProcess` instances actually returned.</span></span> <span data-ttu-id="ed589-109">この値は null になる場合`celt`は 1 つです。</span><span class="sxs-lookup"><span data-stu-id="ed589-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ed589-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="ed589-110">Requirements</span></span>  
 <span data-ttu-id="ed589-111">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ed589-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ed589-112">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ed589-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ed589-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ed589-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ed589-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ed589-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
