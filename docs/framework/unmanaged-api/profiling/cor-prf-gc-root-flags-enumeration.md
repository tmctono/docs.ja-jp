---
title: COR_PRF_GC_ROOT_FLAGS 列挙型
ms.date: 03/30/2017
api_name:
- COR_PRF_GC_ROOT_FLAGS
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_GC_ROOT_FLAGS
helpviewer_keywords:
- COR_PRF_GC_ROOT_FLAGS enumeration [.NET Framework profiling]
ms.assetid: 4611ee6f-0f05-4d84-91e1-e83d5e7dd7e4
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 263c22a07f363c2752afb50779515de043976e93
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59207709"
---
# <a name="corprfgcrootflags-enumeration"></a><span data-ttu-id="fb56a-102">COR_PRF_GC_ROOT_FLAGS 列挙型</span><span class="sxs-lookup"><span data-stu-id="fb56a-102">COR_PRF_GC_ROOT_FLAGS Enumeration</span></span>
<span data-ttu-id="fb56a-103">ガベージ コレクションのルートのプロパティを示します。</span><span class="sxs-lookup"><span data-stu-id="fb56a-103">Indicates a property of a garbage collection root.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fb56a-104">構文</span><span class="sxs-lookup"><span data-stu-id="fb56a-104">Syntax</span></span>  
  
```  
typedef enum {  
    COR_PRF_GC_ROOT_PINNING = 0x1,  
    COR_PRF_GC_ROOT_WEAKREF = 0x2,  
    COR_PRF_GC_ROOT_INTERIOR = 0x4,  
    COR_PRF_GC_ROOT_REFCOUNTED = 0x8,  
} COR_PRF_GC_ROOT_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="fb56a-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="fb56a-105">Members</span></span>  
  
|<span data-ttu-id="fb56a-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="fb56a-106">Member</span></span>|<span data-ttu-id="fb56a-107">説明</span><span class="sxs-lookup"><span data-stu-id="fb56a-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_GC_ROOT_PINNING`|<span data-ttu-id="fb56a-108">ルートでは、ガベージ コレクション オブジェクトを移動できないようにします。</span><span class="sxs-lookup"><span data-stu-id="fb56a-108">The root prevents a garbage collection from moving the object.</span></span>|  
|`COR_PRF_GC_ROOT_WEAKREF`|<span data-ttu-id="fb56a-109">ルートは、ガベージ コレクションを妨げません。</span><span class="sxs-lookup"><span data-stu-id="fb56a-109">The root does not prevent garbage collection.</span></span>|  
|`COR_PRF_GC_ROOT_INTERIOR`|<span data-ttu-id="fb56a-110">ルートは、オブジェクト自体ではなく、オブジェクトのフィールドを参照します。</span><span class="sxs-lookup"><span data-stu-id="fb56a-110">The root refers to a field of the object rather than the object itself.</span></span>|  
|`COR_PRF_GC_ROOT_REFCOUNTED`|<span data-ttu-id="fb56a-111">ルートでは、オブジェクトの参照カウントが特定の値の場合、ガベージ コレクションができないようにします。</span><span class="sxs-lookup"><span data-stu-id="fb56a-111">The root prevents garbage collection if the reference count of the object is a certain value.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fb56a-112">Remarks</span><span class="sxs-lookup"><span data-stu-id="fb56a-112">Remarks</span></span>  
 `COR_PRF_GC_ROOT_FLAGS` <span data-ttu-id="fb56a-113">特殊なルートに関する追加情報を提供するビットマスク。</span><span class="sxs-lookup"><span data-stu-id="fb56a-113">is a bitmask that provides additional information about special roots.</span></span> <span data-ttu-id="fb56a-114">ただし、すべてのルートは特別です。</span><span class="sxs-lookup"><span data-stu-id="fb56a-114">However, not all roots are special.</span></span> <span data-ttu-id="fb56a-115">たとえば、一部のルートを内部ポインター、固定、または参照カウントの弱い参照にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="fb56a-115">For example, some roots are not weak references, interior pointers, pinned, or reference-counted.</span></span> <span data-ttu-id="fb56a-116">このようなルートを伝達するためのフラグはありません。</span><span class="sxs-lookup"><span data-stu-id="fb56a-116">For such roots, there are no flags to convey.</span></span> <span data-ttu-id="fb56a-117">など、この列挙体を使用するメソッド、そのため、 [icorprofilercallback 2::rootreferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md)メソッドでは、送信 0 すべてフラグを設定するかを示す、フラグ ビットがオフになっています。</span><span class="sxs-lookup"><span data-stu-id="fb56a-117">Therefore, methods that use this enumeration, such as the [ICorProfilerCallback2::RootReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md) method, send 0 for the flags bitmask, indicating that all flags are turned off.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fb56a-118">必要条件</span><span class="sxs-lookup"><span data-stu-id="fb56a-118">Requirements</span></span>  
 <span data-ttu-id="fb56a-119">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="fb56a-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fb56a-120">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="fb56a-120">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="fb56a-121">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fb56a-121">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="fb56a-122">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="fb56a-122">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="fb56a-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="fb56a-123">See also</span></span>

- [<span data-ttu-id="fb56a-124">列挙体のプロファイリング</span><span class="sxs-lookup"><span data-stu-id="fb56a-124">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
