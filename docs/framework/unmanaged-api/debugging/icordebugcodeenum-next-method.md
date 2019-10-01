---
title: ICorDebugCodeEnum::Next メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugCodeEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCodeEnum::Next
helpviewer_keywords:
- ICorDebugCodeEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugEnum interface [.NET Framework debugging]
ms.assetid: 644ece86-384d-4c63-9fba-52c789616ff7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 076b5d628dfe83decdbbe2f5e74c50e08262c580
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2019
ms.locfileid: "71700693"
---
# <a name="icordebugcodeenumnext-method"></a><span data-ttu-id="397a2-102">ICorDebugCodeEnum::Next メソッド</span><span class="sxs-lookup"><span data-stu-id="397a2-102">ICorDebugCodeEnum::Next Method</span></span>

<span data-ttu-id="397a2-103">現在の位置から開始して、指定した数の "コード" インスタンスを列挙から取得します。</span><span class="sxs-lookup"><span data-stu-id="397a2-103">Gets the specified number of "ICorDebugCode" instances from the enumeration, starting at the current position.</span></span>

## <a name="syntax"></a><span data-ttu-id="397a2-104">構文</span><span class="sxs-lookup"><span data-stu-id="397a2-104">Syntax</span></span>

```cpp
HRESULT Next (
    [in] ULONG  celt,
    [out, size_is(celt), length_is(*pceltFetched)]
        ICorDebugCode *values[],
    [out] ULONG *pceltFetched
);
```

## <a name="parameters"></a><span data-ttu-id="397a2-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="397a2-105">Parameters</span></span>

 `celt`  
 <span data-ttu-id="397a2-106">から取得する @no__t 0 のインスタンスの数。</span><span class="sxs-lookup"><span data-stu-id="397a2-106">[in] The number of `ICorDebugCode` instances to be retrieved.</span></span>

 `values`  
 <span data-ttu-id="397a2-107">入出力ポインターの配列。それぞれが @no__t 0 のオブジェクトを指します。</span><span class="sxs-lookup"><span data-stu-id="397a2-107">[out] An array of pointers, each of which points to an `ICorDebugCode` object.</span></span>

 `pceltFetched`  
 <span data-ttu-id="397a2-108">入出力実際に返された @no__t 0 のインスタンスの数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="397a2-108">[out] A pointer to the number of `ICorDebugCode` instances actually returned.</span></span> <span data-ttu-id="397a2-109">@No__t-0 が1の場合、この値は null になることがあります。</span><span class="sxs-lookup"><span data-stu-id="397a2-109">This value may be null if `celt` is one.</span></span>

## <a name="requirements"></a><span data-ttu-id="397a2-110">要件</span><span class="sxs-lookup"><span data-stu-id="397a2-110">Requirements</span></span>

 <span data-ttu-id="397a2-111">**・** [システム要件](../../get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="397a2-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

 <span data-ttu-id="397a2-112">**ヘッダー:** CorDebug .idl、CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="397a2-112">**Header:** CorDebug.idl, CorDebug.h</span></span>

 <span data-ttu-id="397a2-113">**ライブラリ**CorGuids .lib</span><span class="sxs-lookup"><span data-stu-id="397a2-113">**Library:** CorGuids.lib</span></span>

 <span data-ttu-id="397a2-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="397a2-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
 
