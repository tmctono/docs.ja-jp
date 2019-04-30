---
title: IMethodMalloc::Alloc メソッド
ms.date: 03/30/2017
api_name:
- IMethodMalloc.Alloc
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- IMethodMalloc::Alloc
helpviewer_keywords:
- IMethodMalloc::Alloc method [.NET Framework profiling]
- Alloc method, IMethodMalloc interface [.NET Framework profiling]
ms.assetid: 8653bd4c-2290-43d2-a3e1-cbbd50033f4f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9a676989bdc6866f85fabe3e15b1e6b7b8b5a9a9
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62000715"
---
# <a name="imethodmallocalloc-method"></a><span data-ttu-id="68a72-102">IMethodMalloc::Alloc メソッド</span><span class="sxs-lookup"><span data-stu-id="68a72-102">IMethodMalloc::Alloc Method</span></span>

<span data-ttu-id="68a72-103">新しい Microsoft intermediate language (MSIL) 関数本体の指定された量のメモリを割り当てようとします。</span><span class="sxs-lookup"><span data-stu-id="68a72-103">Attempts to allocate a specified amount of memory for a new Microsoft intermediate language (MSIL) function body.</span></span>

## <a name="syntax"></a><span data-ttu-id="68a72-104">構文</span><span class="sxs-lookup"><span data-stu-id="68a72-104">Syntax</span></span>

```cpp
PVOID Alloc (
    [in] ULONG   cb
);
```

## <a name="parameters"></a><span data-ttu-id="68a72-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="68a72-105">Parameters</span></span>

`cb`\
<span data-ttu-id="68a72-106">[in]メソッド本体を割り当てバイト数。</span><span class="sxs-lookup"><span data-stu-id="68a72-106">[in] The number of bytes to allocate for the method body.</span></span>

## <a name="remarks"></a><span data-ttu-id="68a72-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="68a72-107">Remarks</span></span>

 <span data-ttu-id="68a72-108">割り当てられたメモリは、このアロケーターに関連付けられているモジュールのベース アドレスよりも大きいアドレスに開始されます。</span><span class="sxs-lookup"><span data-stu-id="68a72-108">The allocated memory will begin at an address greater than the base address of the module that is associated with this allocator.</span></span> <span data-ttu-id="68a72-109">つまり、各アロケーターは、特定のモジュールが作成され、そのベース アドレスから正のオフセットにメモリを割り当てることを試みます。</span><span class="sxs-lookup"><span data-stu-id="68a72-109">In other words, each allocator is created for a particular module, and will attempt to allocate memory at a positive offset from its base address.</span></span> <span data-ttu-id="68a72-110">場合`Alloc`要求されたモジュールのベース アドレスよりも大きいアドレスにあるバイト数を割り当てに失敗する実際の使用可能なメモリ領域の量に関係なく、E_OUTOFMEMORY が返されます。</span><span class="sxs-lookup"><span data-stu-id="68a72-110">If `Alloc` fails to allocate the requested number of bytes at an address greater than the base address of the module, it returns E_OUTOFMEMORY, regardless of the actual amount of memory space available.</span></span>

 <span data-ttu-id="68a72-111">`Alloc`メソッドを組み合わせて使用する必要があります、 [icorprofilerinfo::setilfunctionbody](icorprofilerinfo-setilfunctionbody-method.md)メソッド。</span><span class="sxs-lookup"><span data-stu-id="68a72-111">The `Alloc` method should be used in conjunction with the [ICorProfilerInfo::SetILFunctionBody](icorprofilerinfo-setilfunctionbody-method.md) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="68a72-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="68a72-112">Requirements</span></span>
 <span data-ttu-id="68a72-113">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="68a72-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

 <span data-ttu-id="68a72-114">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="68a72-114">**Header:** CorProf.idl, CorProf.h</span></span>

 <span data-ttu-id="68a72-115">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="68a72-115">**Library:** CorGuids.lib</span></span>

 <span data-ttu-id="68a72-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="68a72-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="68a72-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="68a72-117">See also</span></span>

- [<span data-ttu-id="68a72-118">IMethodMalloc インターフェイス</span><span class="sxs-lookup"><span data-stu-id="68a72-118">IMethodMalloc Interface</span></span>](imethodmalloc-interface.md)