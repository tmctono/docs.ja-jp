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
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59168390"
---
# <a name="icordebugarrayvalue-interface"></a><span data-ttu-id="b423d-102">ICorDebugArrayValue インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b423d-102">ICorDebugArrayValue Interface</span></span>

<span data-ttu-id="b423d-103">1 次元または多次元配列を表すのサブクラスです。</span><span class="sxs-lookup"><span data-stu-id="b423d-103">A subclass of ICorDebugHeapValue that represents a single-dimensional or multi-dimensional array.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b423d-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="b423d-104">Methods</span></span>  
  
|<span data-ttu-id="b423d-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="b423d-105">Method</span></span>|<span data-ttu-id="b423d-106">説明</span><span class="sxs-lookup"><span data-stu-id="b423d-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b423d-107">GetBaseIndicies メソッド</span><span class="sxs-lookup"><span data-stu-id="b423d-107">GetBaseIndicies Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-getbaseindicies-method.md)|<span data-ttu-id="b423d-108">配列内の各次元のベース インデックスを取得します。</span><span class="sxs-lookup"><span data-stu-id="b423d-108">Gets the base index of each dimension in the array.</span></span>|  
|[<span data-ttu-id="b423d-109">GetCount メソッド</span><span class="sxs-lookup"><span data-stu-id="b423d-109">GetCount Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-getcount-method.md)|<span data-ttu-id="b423d-110">配列の要素の合計数を取得します。</span><span class="sxs-lookup"><span data-stu-id="b423d-110">Gets the total number of elements in the array.</span></span>|  
|[<span data-ttu-id="b423d-111">GetDimensions メソッド</span><span class="sxs-lookup"><span data-stu-id="b423d-111">GetDimensions Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-getdimensions-method.md)|<span data-ttu-id="b423d-112">配列の次元を取得します。</span><span class="sxs-lookup"><span data-stu-id="b423d-112">Gets the dimensions of the array.</span></span>|  
|[<span data-ttu-id="b423d-113">GetElement メソッド</span><span class="sxs-lookup"><span data-stu-id="b423d-113">GetElement Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-getelement-method.md)|<span data-ttu-id="b423d-114">配列内の指定した要素を表す値を取得します。</span><span class="sxs-lookup"><span data-stu-id="b423d-114">Gets a value representing the given element in the array.</span></span>|  
|[<span data-ttu-id="b423d-115">GetElementAtPosition メソッド</span><span class="sxs-lookup"><span data-stu-id="b423d-115">GetElementAtPosition Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-getelementatposition-method.md)|<span data-ttu-id="b423d-116">0 から始まる 1 次元の配列として、配列を扱う方法の指定された位置に要素を取得します。</span><span class="sxs-lookup"><span data-stu-id="b423d-116">Gets the element at the given position, treating the array as a zero-based, single-dimensional array.</span></span>|  
|[<span data-ttu-id="b423d-117">GetElementType メソッド</span><span class="sxs-lookup"><span data-stu-id="b423d-117">GetElementType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-getelementtype-method.md)|<span data-ttu-id="b423d-118">配列内の要素の単純な型を取得します。</span><span class="sxs-lookup"><span data-stu-id="b423d-118">Gets the simple type of the elements in the array.</span></span>|  
|[<span data-ttu-id="b423d-119">GetRank メソッド</span><span class="sxs-lookup"><span data-stu-id="b423d-119">GetRank Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-getrank-method.md)|<span data-ttu-id="b423d-120">配列のディメンションの数を取得します。</span><span class="sxs-lookup"><span data-stu-id="b423d-120">Gets the number of dimensions in the array.</span></span>|  
|[<span data-ttu-id="b423d-121">HasBaseIndicies メソッド</span><span class="sxs-lookup"><span data-stu-id="b423d-121">HasBaseIndicies Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-hasbaseindicies-method.md)|<span data-ttu-id="b423d-122">配列のベース インデックスがあるかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="b423d-122">Determines whether the array has base indexes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b423d-123">Remarks</span><span class="sxs-lookup"><span data-stu-id="b423d-123">Remarks</span></span>  
 <span data-ttu-id="b423d-124">`ICorDebugArrayValue` 1 次元配列と多次元の両方の配列をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="b423d-124">`ICorDebugArrayValue` supports both single-dimensional and multi-dimensional arrays.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b423d-125">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="b423d-125">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b423d-126">必要条件</span><span class="sxs-lookup"><span data-stu-id="b423d-126">Requirements</span></span>  
 <span data-ttu-id="b423d-127">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b423d-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b423d-128">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b423d-128">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b423d-129">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b423d-129">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b423d-130">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b423d-130">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b423d-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="b423d-131">See also</span></span>

- [<span data-ttu-id="b423d-132">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b423d-132">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
