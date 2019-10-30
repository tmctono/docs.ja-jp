---
title: ICorDebugEval::NewArray メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugEval.NewArray
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval::NewArray
helpviewer_keywords:
- NewArray method [.NET Framework debugging]
- ICorDebugEval::NewArray method [.NET Framework debugging]
ms.assetid: cc79a67d-5368-434d-a943-209db90491b9
topic_type:
- apiref
ms.openlocfilehash: ca0844e4d2b1cad65266d58c6cda74de203d1758
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137656"
---
# <a name="icordebugevalnewarray-method"></a><span data-ttu-id="0c359-102">ICorDebugEval::NewArray メソッド</span><span class="sxs-lookup"><span data-stu-id="0c359-102">ICorDebugEval::NewArray Method</span></span>
<span data-ttu-id="0c359-103">指定した要素の型と次元の新しい配列を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="0c359-103">Allocates a new array of the specified element type and dimensions.</span></span>  
  
 <span data-ttu-id="0c359-104">このメソッドは .NET Framework バージョン2.0 では廃止されています。</span><span class="sxs-lookup"><span data-stu-id="0c359-104">This method is obsolete in the .NET Framework version 2.0.</span></span> <span data-ttu-id="0c359-105">代わりに[ICorDebugEval2:: NewParameterizedArray](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedarray-method.md)を使用してください。</span><span class="sxs-lookup"><span data-stu-id="0c359-105">Use [ICorDebugEval2::NewParameterizedArray](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedarray-method.md) instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0c359-106">構文</span><span class="sxs-lookup"><span data-stu-id="0c359-106">Syntax</span></span>  
  
```cpp  
HRESULT NewArray (  
    [in] CorElementType     elementType,  
    [in] ICorDebugClass     *pElementClass,  
    [in] ULONG32            rank,  
    [in, size_is(rank)] ULONG32 dims[],  
    [in, size_is(rank)] ULONG32 lowBounds[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0c359-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="0c359-107">Parameters</span></span>  
 `elementType`  
 <span data-ttu-id="0c359-108">から配列の要素の型を指定する CorElementType 列挙体の値。</span><span class="sxs-lookup"><span data-stu-id="0c359-108">[in] A value of the CorElementType enumeration that specifies the element type of the array.</span></span>  
  
 `pElementClass`  
 <span data-ttu-id="0c359-109">から要素のクラスを指定する、ツールオブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="0c359-109">[in] A pointer to a ICorDebugClass object that specifies the class of the element.</span></span> <span data-ttu-id="0c359-110">要素の型がプリミティブ型の場合、この値は null になることがあります。</span><span class="sxs-lookup"><span data-stu-id="0c359-110">This value may be null if the element type is a primitive type.</span></span>  
  
 `rank`  
 <span data-ttu-id="0c359-111">から配列の次元数。</span><span class="sxs-lookup"><span data-stu-id="0c359-111">[in] The number of dimensions of the array.</span></span> <span data-ttu-id="0c359-112">.NET Framework 2.0 では、この値は1である必要があります。</span><span class="sxs-lookup"><span data-stu-id="0c359-112">In the .NET Framework 2.0, this value must be 1.</span></span>  
  
 `dims`  
 <span data-ttu-id="0c359-113">から配列の各次元のサイズ (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="0c359-113">[in] The size, in bytes, of each dimension of the array.</span></span>  
  
 `lowBounds`  
 <span data-ttu-id="0c359-114">[in] オプション。</span><span class="sxs-lookup"><span data-stu-id="0c359-114">[in] Optional.</span></span> <span data-ttu-id="0c359-115">配列の各次元の下限。</span><span class="sxs-lookup"><span data-stu-id="0c359-115">The lower bound of each dimension of the array.</span></span> <span data-ttu-id="0c359-116">この値を省略すると、次元ごとに下限0が想定されます。</span><span class="sxs-lookup"><span data-stu-id="0c359-116">If this value is omitted, a lower bound of zero is assumed for each dimension.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0c359-117">Remarks</span><span class="sxs-lookup"><span data-stu-id="0c359-117">Remarks</span></span>  
 <span data-ttu-id="0c359-118">配列は常に、スレッドが現在実行されているアプリケーションドメインで作成されます。</span><span class="sxs-lookup"><span data-stu-id="0c359-118">The array is always created in the application domain in which the thread is currently executing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0c359-119">［要件］</span><span class="sxs-lookup"><span data-stu-id="0c359-119">Requirements</span></span>  
 <span data-ttu-id="0c359-120">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0c359-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0c359-121">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0c359-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0c359-122">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0c359-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0c359-123">**.NET Framework のバージョン:** 1.1、1.0</span><span class="sxs-lookup"><span data-stu-id="0c359-123">**.NET Framework Versions:** 1.1, 1.0</span></span>
