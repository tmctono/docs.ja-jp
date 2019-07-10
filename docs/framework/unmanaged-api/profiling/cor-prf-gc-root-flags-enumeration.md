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
ms.openlocfilehash: 7f179e3b01d6c3b34dfa765565a0fc38d0ba867c
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67753699"
---
# <a name="corprfgcrootflags-enumeration"></a><span data-ttu-id="fa45c-102">COR_PRF_GC_ROOT_FLAGS 列挙型</span><span class="sxs-lookup"><span data-stu-id="fa45c-102">COR_PRF_GC_ROOT_FLAGS Enumeration</span></span>
<span data-ttu-id="fa45c-103">ガベージ コレクションのルートのプロパティを示します。</span><span class="sxs-lookup"><span data-stu-id="fa45c-103">Indicates a property of a garbage collection root.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fa45c-104">構文</span><span class="sxs-lookup"><span data-stu-id="fa45c-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_PRF_GC_ROOT_PINNING = 0x1,  
    COR_PRF_GC_ROOT_WEAKREF = 0x2,  
    COR_PRF_GC_ROOT_INTERIOR = 0x4,  
    COR_PRF_GC_ROOT_REFCOUNTED = 0x8,  
} COR_PRF_GC_ROOT_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="fa45c-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="fa45c-105">Members</span></span>  
  
|<span data-ttu-id="fa45c-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="fa45c-106">Member</span></span>|<span data-ttu-id="fa45c-107">説明</span><span class="sxs-lookup"><span data-stu-id="fa45c-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_GC_ROOT_PINNING`|<span data-ttu-id="fa45c-108">ルートでは、ガベージ コレクション オブジェクトを移動できないようにします。</span><span class="sxs-lookup"><span data-stu-id="fa45c-108">The root prevents a garbage collection from moving the object.</span></span>|  
|`COR_PRF_GC_ROOT_WEAKREF`|<span data-ttu-id="fa45c-109">ルートは、ガベージ コレクションを妨げません。</span><span class="sxs-lookup"><span data-stu-id="fa45c-109">The root does not prevent garbage collection.</span></span>|  
|`COR_PRF_GC_ROOT_INTERIOR`|<span data-ttu-id="fa45c-110">ルートは、オブジェクト自体ではなく、オブジェクトのフィールドを参照します。</span><span class="sxs-lookup"><span data-stu-id="fa45c-110">The root refers to a field of the object rather than the object itself.</span></span>|  
|`COR_PRF_GC_ROOT_REFCOUNTED`|<span data-ttu-id="fa45c-111">ルートでは、オブジェクトの参照カウントが特定の値の場合、ガベージ コレクションができないようにします。</span><span class="sxs-lookup"><span data-stu-id="fa45c-111">The root prevents garbage collection if the reference count of the object is a certain value.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fa45c-112">Remarks</span><span class="sxs-lookup"><span data-stu-id="fa45c-112">Remarks</span></span>  
 <span data-ttu-id="fa45c-113">`COR_PRF_GC_ROOT_FLAGS` 特殊なルートに関する追加情報を提供するビットマスク。</span><span class="sxs-lookup"><span data-stu-id="fa45c-113">`COR_PRF_GC_ROOT_FLAGS` is a bitmask that provides additional information about special roots.</span></span> <span data-ttu-id="fa45c-114">ただし、すべてのルートは特別です。</span><span class="sxs-lookup"><span data-stu-id="fa45c-114">However, not all roots are special.</span></span> <span data-ttu-id="fa45c-115">たとえば、一部のルートを内部ポインター、固定、または参照カウントの弱い参照にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="fa45c-115">For example, some roots are not weak references, interior pointers, pinned, or reference-counted.</span></span> <span data-ttu-id="fa45c-116">このようなルートを伝達するためのフラグはありません。</span><span class="sxs-lookup"><span data-stu-id="fa45c-116">For such roots, there are no flags to convey.</span></span> <span data-ttu-id="fa45c-117">など、この列挙体を使用するメソッド、そのため、 [icorprofilercallback 2::rootreferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md)メソッドでは、送信 0 すべてフラグを設定するかを示す、フラグ ビットがオフになっています。</span><span class="sxs-lookup"><span data-stu-id="fa45c-117">Therefore, methods that use this enumeration, such as the [ICorProfilerCallback2::RootReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md) method, send 0 for the flags bitmask, indicating that all flags are turned off.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fa45c-118">必要条件</span><span class="sxs-lookup"><span data-stu-id="fa45c-118">Requirements</span></span>  
 <span data-ttu-id="fa45c-119">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="fa45c-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fa45c-120">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="fa45c-120">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="fa45c-121">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fa45c-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fa45c-122">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fa45c-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa45c-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="fa45c-123">See also</span></span>

- [<span data-ttu-id="fa45c-124">列挙型のプロファイリング</span><span class="sxs-lookup"><span data-stu-id="fa45c-124">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
