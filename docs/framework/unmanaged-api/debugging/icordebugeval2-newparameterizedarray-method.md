---
title: ICorDebugEval2::NewParameterizedArray メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugEval2.NewParameterizedArray
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval2::NewParameterizedArray
helpviewer_keywords:
- ICorDebugEval2::NewParameterizedArray method [.NET Framework debugging]
- NewParameterizedArray method [.NET Framework debugging]
ms.assetid: 45efb8ba-c4de-4109-945f-e734d376b43c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 973f975885bbbf5cbed74adef7b9f4f423c42583
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67753657"
---
# <a name="icordebugeval2newparameterizedarray-method"></a><span data-ttu-id="b31a4-102">ICorDebugEval2::NewParameterizedArray メソッド</span><span class="sxs-lookup"><span data-stu-id="b31a4-102">ICorDebugEval2::NewParameterizedArray Method</span></span>
<span data-ttu-id="b31a4-103">指定した要素型とディメンションの新しい配列を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="b31a4-103">Allocates a new array of the specified element type and dimensions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b31a4-104">構文</span><span class="sxs-lookup"><span data-stu-id="b31a4-104">Syntax</span></span>  
  
```cpp  
HRESULT NewParameterizedArray(  
    [in] ICorDebugType          *pElementType,  
    [in] ULONG32                rank,  
    [in, size_is(rank)] ULONG32 dims[],  
    [in, size_is(rank)] ULONG32 lowBounds[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b31a4-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="b31a4-105">Parameters</span></span>  
 `pElementType`  
 <span data-ttu-id="b31a4-106">[in]配列に格納されている要素の型を表す ICorDebugType オブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="b31a4-106">[in] A pointer to an ICorDebugType object that represents the type of element stored in the array.</span></span>  
  
 `rank`  
 <span data-ttu-id="b31a4-107">[in]配列の次元の数。</span><span class="sxs-lookup"><span data-stu-id="b31a4-107">[in] The number of dimensions of the array.</span></span> <span data-ttu-id="b31a4-108">.NET framework version 2.0 では、この値は 1 にある必要があります。</span><span class="sxs-lookup"><span data-stu-id="b31a4-108">In the .NET Framework version 2.0, this value must be 1.</span></span>  
  
 `dims`  
 <span data-ttu-id="b31a4-109">[in]配列の各次元のバイト単位のサイズ。</span><span class="sxs-lookup"><span data-stu-id="b31a4-109">[in] The size, in bytes, of each dimension of the array.</span></span>  
  
 `lowBounds`  
 <span data-ttu-id="b31a4-110">[in] オプション。</span><span class="sxs-lookup"><span data-stu-id="b31a4-110">[in] Optional.</span></span> <span data-ttu-id="b31a4-111">配列の各次元の下限値です。</span><span class="sxs-lookup"><span data-stu-id="b31a4-111">The lower bound of each dimension of the array.</span></span> <span data-ttu-id="b31a4-112">この値を省略すると、各ディメンションの下限を 0 が使われます。</span><span class="sxs-lookup"><span data-stu-id="b31a4-112">If this value is omitted, a lower bound of zero is assumed for each dimension.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b31a4-113">Remarks</span><span class="sxs-lookup"><span data-stu-id="b31a4-113">Remarks</span></span>  
 <span data-ttu-id="b31a4-114">配列の要素には、ジェネリック型のインスタンスを使用できます。</span><span class="sxs-lookup"><span data-stu-id="b31a4-114">The elements of the array may be instances of a generic type.</span></span> <span data-ttu-id="b31a4-115">配列が常に、スレッドが現在実行されているアプリケーション ドメインで作成されます。</span><span class="sxs-lookup"><span data-stu-id="b31a4-115">The array is always created in the application domain in which the thread is currently running.</span></span> <span data-ttu-id="b31a4-116">.NET Framework 2.0 の値で`rank`1 である必要があります。</span><span class="sxs-lookup"><span data-stu-id="b31a4-116">In the .NET Framework 2.0, the value of `rank` must be 1.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b31a4-117">必要条件</span><span class="sxs-lookup"><span data-stu-id="b31a4-117">Requirements</span></span>  
 <span data-ttu-id="b31a4-118">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b31a4-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b31a4-119">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b31a4-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b31a4-120">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b31a4-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b31a4-121">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b31a4-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
