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
ms.openlocfilehash: 67fd1a9174b04e42b53f2b866a1dfdd504362aa9
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61645618"
---
# <a name="icordebugarrayvalue-interface"></a><span data-ttu-id="fa0b9-102">ICorDebugArrayValue インターフェイス</span><span class="sxs-lookup"><span data-stu-id="fa0b9-102">ICorDebugArrayValue Interface</span></span>

<span data-ttu-id="fa0b9-103">1 次元または多次元配列を表すのサブクラスです。</span><span class="sxs-lookup"><span data-stu-id="fa0b9-103">A subclass of ICorDebugHeapValue that represents a single-dimensional or multi-dimensional array.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="fa0b9-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="fa0b9-104">Methods</span></span>  
  
|<span data-ttu-id="fa0b9-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="fa0b9-105">Method</span></span>|<span data-ttu-id="fa0b9-106">説明</span><span class="sxs-lookup"><span data-stu-id="fa0b9-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="fa0b9-107">GetBaseIndicies メソッド</span><span class="sxs-lookup"><span data-stu-id="fa0b9-107">GetBaseIndicies Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-getbaseindicies-method.md)|<span data-ttu-id="fa0b9-108">配列内の各次元のベース インデックスを取得します。</span><span class="sxs-lookup"><span data-stu-id="fa0b9-108">Gets the base index of each dimension in the array.</span></span>|  
|[<span data-ttu-id="fa0b9-109">GetCount メソッド</span><span class="sxs-lookup"><span data-stu-id="fa0b9-109">GetCount Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-getcount-method.md)|<span data-ttu-id="fa0b9-110">配列の要素の合計数を取得します。</span><span class="sxs-lookup"><span data-stu-id="fa0b9-110">Gets the total number of elements in the array.</span></span>|  
|[<span data-ttu-id="fa0b9-111">GetDimensions メソッド</span><span class="sxs-lookup"><span data-stu-id="fa0b9-111">GetDimensions Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-getdimensions-method.md)|<span data-ttu-id="fa0b9-112">配列の次元を取得します。</span><span class="sxs-lookup"><span data-stu-id="fa0b9-112">Gets the dimensions of the array.</span></span>|  
|[<span data-ttu-id="fa0b9-113">GetElement メソッド</span><span class="sxs-lookup"><span data-stu-id="fa0b9-113">GetElement Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-getelement-method.md)|<span data-ttu-id="fa0b9-114">配列内の指定した要素を表す値を取得します。</span><span class="sxs-lookup"><span data-stu-id="fa0b9-114">Gets a value representing the given element in the array.</span></span>|  
|[<span data-ttu-id="fa0b9-115">GetElementAtPosition メソッド</span><span class="sxs-lookup"><span data-stu-id="fa0b9-115">GetElementAtPosition Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-getelementatposition-method.md)|<span data-ttu-id="fa0b9-116">0 から始まる 1 次元の配列として、配列を扱う方法の指定された位置に要素を取得します。</span><span class="sxs-lookup"><span data-stu-id="fa0b9-116">Gets the element at the given position, treating the array as a zero-based, single-dimensional array.</span></span>|  
|[<span data-ttu-id="fa0b9-117">GetElementType メソッド</span><span class="sxs-lookup"><span data-stu-id="fa0b9-117">GetElementType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-getelementtype-method.md)|<span data-ttu-id="fa0b9-118">配列内の要素の単純な型を取得します。</span><span class="sxs-lookup"><span data-stu-id="fa0b9-118">Gets the simple type of the elements in the array.</span></span>|  
|[<span data-ttu-id="fa0b9-119">GetRank メソッド</span><span class="sxs-lookup"><span data-stu-id="fa0b9-119">GetRank Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-getrank-method.md)|<span data-ttu-id="fa0b9-120">配列のディメンションの数を取得します。</span><span class="sxs-lookup"><span data-stu-id="fa0b9-120">Gets the number of dimensions in the array.</span></span>|  
|[<span data-ttu-id="fa0b9-121">HasBaseIndicies メソッド</span><span class="sxs-lookup"><span data-stu-id="fa0b9-121">HasBaseIndicies Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-hasbaseindicies-method.md)|<span data-ttu-id="fa0b9-122">配列のベース インデックスがあるかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="fa0b9-122">Determines whether the array has base indexes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fa0b9-123">Remarks</span><span class="sxs-lookup"><span data-stu-id="fa0b9-123">Remarks</span></span>  
 <span data-ttu-id="fa0b9-124">`ICorDebugArrayValue` 1 次元配列と多次元の両方の配列をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="fa0b9-124">`ICorDebugArrayValue` supports both single-dimensional and multi-dimensional arrays.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fa0b9-125">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="fa0b9-125">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fa0b9-126">必要条件</span><span class="sxs-lookup"><span data-stu-id="fa0b9-126">Requirements</span></span>  
 <span data-ttu-id="fa0b9-127">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="fa0b9-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fa0b9-128">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fa0b9-128">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fa0b9-129">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fa0b9-129">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fa0b9-130">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fa0b9-130">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa0b9-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="fa0b9-131">See also</span></span>

- [<span data-ttu-id="fa0b9-132">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="fa0b9-132">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
