---
title: ICorDebugArrayValue インターフェイス
ms.date: 03/30/2017
api_name:
- ICorDebugArrayValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugArrayValue interface
helpviewer_keywords:
- ICorDebugArrayValue interface [.NET Framework debugging]
ms.assetid: dc437751-7093-44e2-bfdc-191d9ce3c192
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 99bd3e9ae1faec1b71933681fadf4816b4789c98
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69952211"
---
# <a name="icordebugarrayvalue-interface"></a><span data-ttu-id="3878d-102">ICorDebugArrayValue インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3878d-102">ICorDebugArrayValue Interface</span></span>

<span data-ttu-id="3878d-103">1次元配列または多次元配列を表す、値のサブクラス。</span><span class="sxs-lookup"><span data-stu-id="3878d-103">A subclass of ICorDebugHeapValue that represents a single-dimensional or multi-dimensional array.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3878d-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="3878d-104">Methods</span></span>  
  
|<span data-ttu-id="3878d-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="3878d-105">Method</span></span>|<span data-ttu-id="3878d-106">説明</span><span class="sxs-lookup"><span data-stu-id="3878d-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3878d-107">GetBaseIndicies メソッド</span><span class="sxs-lookup"><span data-stu-id="3878d-107">GetBaseIndicies Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-getbaseindicies-method.md)|<span data-ttu-id="3878d-108">配列内の各次元のベースインデックスを取得します。</span><span class="sxs-lookup"><span data-stu-id="3878d-108">Gets the base index of each dimension in the array.</span></span>|  
|[<span data-ttu-id="3878d-109">GetCount メソッド</span><span class="sxs-lookup"><span data-stu-id="3878d-109">GetCount Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-getcount-method.md)|<span data-ttu-id="3878d-110">配列内の要素の合計数を取得します。</span><span class="sxs-lookup"><span data-stu-id="3878d-110">Gets the total number of elements in the array.</span></span>|  
|[<span data-ttu-id="3878d-111">GetDimensions メソッド</span><span class="sxs-lookup"><span data-stu-id="3878d-111">GetDimensions Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-getdimensions-method.md)|<span data-ttu-id="3878d-112">配列の次元を取得します。</span><span class="sxs-lookup"><span data-stu-id="3878d-112">Gets the dimensions of the array.</span></span>|  
|[<span data-ttu-id="3878d-113">GetElement メソッド</span><span class="sxs-lookup"><span data-stu-id="3878d-113">GetElement Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-getelement-method.md)|<span data-ttu-id="3878d-114">配列内の指定された要素を表す値を取得します。</span><span class="sxs-lookup"><span data-stu-id="3878d-114">Gets a value representing the given element in the array.</span></span>|  
|[<span data-ttu-id="3878d-115">GetElementAtPosition メソッド</span><span class="sxs-lookup"><span data-stu-id="3878d-115">GetElementAtPosition Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-getelementatposition-method.md)|<span data-ttu-id="3878d-116">配列を0から始まる1次元配列として扱い、指定された位置にある要素を取得します。</span><span class="sxs-lookup"><span data-stu-id="3878d-116">Gets the element at the given position, treating the array as a zero-based, single-dimensional array.</span></span>|  
|[<span data-ttu-id="3878d-117">GetElementType メソッド</span><span class="sxs-lookup"><span data-stu-id="3878d-117">GetElementType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-getelementtype-method.md)|<span data-ttu-id="3878d-118">配列内の要素の単純型を取得します。</span><span class="sxs-lookup"><span data-stu-id="3878d-118">Gets the simple type of the elements in the array.</span></span>|  
|[<span data-ttu-id="3878d-119">GetRank メソッド</span><span class="sxs-lookup"><span data-stu-id="3878d-119">GetRank Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-getrank-method.md)|<span data-ttu-id="3878d-120">配列のディメンションの数を取得します。</span><span class="sxs-lookup"><span data-stu-id="3878d-120">Gets the number of dimensions in the array.</span></span>|  
|[<span data-ttu-id="3878d-121">HasBaseIndicies メソッド</span><span class="sxs-lookup"><span data-stu-id="3878d-121">HasBaseIndicies Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-hasbaseindicies-method.md)|<span data-ttu-id="3878d-122">配列にベースインデックスがあるかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="3878d-122">Determines whether the array has base indexes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3878d-123">Remarks</span><span class="sxs-lookup"><span data-stu-id="3878d-123">Remarks</span></span>  
 <span data-ttu-id="3878d-124">`ICorDebugArrayValue`では、1次元配列と多次元配列の両方がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="3878d-124">`ICorDebugArrayValue` supports both single-dimensional and multi-dimensional arrays.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3878d-125">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="3878d-125">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3878d-126">必要条件</span><span class="sxs-lookup"><span data-stu-id="3878d-126">Requirements</span></span>  
 <span data-ttu-id="3878d-127">**・** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3878d-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3878d-128">**ヘッダー:** CorDebug .idl、CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="3878d-128">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3878d-129">**ライブラリ**CorGuids .lib</span><span class="sxs-lookup"><span data-stu-id="3878d-129">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3878d-130">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3878d-130">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3878d-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="3878d-131">See also</span></span>

- [<span data-ttu-id="3878d-132">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3878d-132">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
