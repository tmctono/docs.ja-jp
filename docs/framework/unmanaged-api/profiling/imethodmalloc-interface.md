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
ms.openlocfilehash: ee825da1f3f0fd72a3b47b48783f0f344af99b65
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61969814"
---
# <a name="imethodmalloc-interface"></a><span data-ttu-id="75745-102">IMethodMalloc インターフェイス</span><span class="sxs-lookup"><span data-stu-id="75745-102">IMethodMalloc Interface</span></span>
<span data-ttu-id="75745-103">新しい Microsoft intermediate language (MSIL) 関数本体にメモリを割り当てるメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="75745-103">Provides a method to allocate memory for a new Microsoft intermediate language (MSIL) function body.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="75745-104">`IMethodMalloc`インターフェイスは、単純なメモリ アロケーター。</span><span class="sxs-lookup"><span data-stu-id="75745-104">The `IMethodMalloc` interface is a simple memory allocator.</span></span> <span data-ttu-id="75745-105">これにより、メモリを割り当て、解放することができます。</span><span class="sxs-lookup"><span data-stu-id="75745-105">It allows you to allocate memory, but not to free it.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="75745-106">メソッド</span><span class="sxs-lookup"><span data-stu-id="75745-106">Methods</span></span>  
  
|<span data-ttu-id="75745-107">メソッド</span><span class="sxs-lookup"><span data-stu-id="75745-107">Method</span></span>|<span data-ttu-id="75745-108">説明</span><span class="sxs-lookup"><span data-stu-id="75745-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="75745-109">Alloc メソッド</span><span class="sxs-lookup"><span data-stu-id="75745-109">Alloc Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/imethodmalloc-alloc-method.md)|<span data-ttu-id="75745-110">新しい MSIL 関数本体の指定された量のメモリを割り当てようとします。</span><span class="sxs-lookup"><span data-stu-id="75745-110">Attempts to allocate a specified amount of memory for a new MSIL function body.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="75745-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="75745-111">Remarks</span></span>  
 <span data-ttu-id="75745-112">各アロケーター モジュールに固有であり、関数本体は、モジュールのベースから正の値のオフセット位置になります。</span><span class="sxs-lookup"><span data-stu-id="75745-112">Each allocator is module-specific and ensures that the function body will be at a positive offset from the base of the module.</span></span> <span data-ttu-id="75745-113">モジュールのベースを超えるメモリはアロケーター関数本体にのみメモリを割り当てに使用するため貴重なことができます。</span><span class="sxs-lookup"><span data-stu-id="75745-113">Memory above the base of a module can be precious, so the allocator should be used to allocate memory only for a function body.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="75745-114">必要条件</span><span class="sxs-lookup"><span data-stu-id="75745-114">Requirements</span></span>  
 <span data-ttu-id="75745-115">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="75745-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="75745-116">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="75745-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="75745-117">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="75745-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="75745-118">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="75745-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75745-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="75745-119">See also</span></span>

- [<span data-ttu-id="75745-120">プロファイリングのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="75745-120">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
