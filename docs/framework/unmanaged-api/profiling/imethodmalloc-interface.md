---
title: IMethodMalloc インターフェイス
ms.date: 03/30/2017
api_name:
- IMethodMalloc
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- IMethodMalloc
helpviewer_keywords:
- IMethodMalloc interface [.NET Framework profiling]
ms.assetid: 8c8ab5dc-557c-473a-82f2-6e403eca7dac
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c67ce15175f8667139f99cec1ed17531eab473e1
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69935648"
---
# <a name="imethodmalloc-interface"></a><span data-ttu-id="9ca2f-102">IMethodMalloc インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9ca2f-102">IMethodMalloc Interface</span></span>
<span data-ttu-id="9ca2f-103">新しい Microsoft 中間言語 (MSIL) 関数の本体にメモリを割り当てる方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="9ca2f-103">Provides a method to allocate memory for a new Microsoft intermediate language (MSIL) function body.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9ca2f-104">`IMethodMalloc`インターフェイスは、単純なメモリアロケーターです。</span><span class="sxs-lookup"><span data-stu-id="9ca2f-104">The `IMethodMalloc` interface is a simple memory allocator.</span></span> <span data-ttu-id="9ca2f-105">メモリを割り当てることはできますが、解放することはできません。</span><span class="sxs-lookup"><span data-stu-id="9ca2f-105">It allows you to allocate memory, but not to free it.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="9ca2f-106">メソッド</span><span class="sxs-lookup"><span data-stu-id="9ca2f-106">Methods</span></span>  
  
|<span data-ttu-id="9ca2f-107">メソッド</span><span class="sxs-lookup"><span data-stu-id="9ca2f-107">Method</span></span>|<span data-ttu-id="9ca2f-108">説明</span><span class="sxs-lookup"><span data-stu-id="9ca2f-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="9ca2f-109">Alloc メソッド</span><span class="sxs-lookup"><span data-stu-id="9ca2f-109">Alloc Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/imethodmalloc-alloc-method.md)|<span data-ttu-id="9ca2f-110">新しい MSIL 関数本体に指定された量のメモリを割り当てようとします。</span><span class="sxs-lookup"><span data-stu-id="9ca2f-110">Attempts to allocate a specified amount of memory for a new MSIL function body.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9ca2f-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="9ca2f-111">Remarks</span></span>  
 <span data-ttu-id="9ca2f-112">各アロケーターはモジュール固有であり、関数本体がモジュールのベースから正のオフセットになるようにします。</span><span class="sxs-lookup"><span data-stu-id="9ca2f-112">Each allocator is module-specific and ensures that the function body will be at a positive offset from the base of the module.</span></span> <span data-ttu-id="9ca2f-113">モジュールのベースを超えるメモリは貴重な場合があるため、アロケーターを使用して、関数本体にのみメモリを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="9ca2f-113">Memory above the base of a module can be precious, so the allocator should be used to allocate memory only for a function body.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9ca2f-114">必要条件</span><span class="sxs-lookup"><span data-stu-id="9ca2f-114">Requirements</span></span>  
 <span data-ttu-id="9ca2f-115">**・** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="9ca2f-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9ca2f-116">**ヘッダー:** Corprof.idl、Corprof.idl</span><span class="sxs-lookup"><span data-stu-id="9ca2f-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="9ca2f-117">**ライブラリ**CorGuids .lib</span><span class="sxs-lookup"><span data-stu-id="9ca2f-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9ca2f-118">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9ca2f-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ca2f-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="9ca2f-119">See also</span></span>

- [<span data-ttu-id="9ca2f-120">プロファイリングのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="9ca2f-120">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
