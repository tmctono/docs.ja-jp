---
title: COR_PRF_SNAPSHOT_INFO 列挙型
ms.date: 03/30/2017
api_name:
- COR_PRF_SNAPSHOT_INFO
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_SNAPSHOT_INFO
helpviewer_keywords:
- COR_PRF_SNAPSHOT_INFO enumeration [.NET Framework profiling]
ms.assetid: a5906b2a-ad4a-4cc6-a421-2d7d8adf7468
topic_type:
- apiref
ms.openlocfilehash: 6ade4f7877e39a8307a36f3a3268f79e8b4d44fd
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74427270"
---
# <a name="cor_prf_snapshot_info-enumeration"></a><span data-ttu-id="f72dd-102">COR_PRF_SNAPSHOT_INFO 列挙型</span><span class="sxs-lookup"><span data-stu-id="f72dd-102">COR_PRF_SNAPSHOT_INFO Enumeration</span></span>
<span data-ttu-id="f72dd-103">プロファイラーの[Stacksnapshotcallback](../../../../docs/framework/unmanaged-api/profiling/stacksnapshotcallback-function.md)関数を呼び出すたびに、スタックスナップショットで返すデータ量を指定します。</span><span class="sxs-lookup"><span data-stu-id="f72dd-103">Specifies how much data to pass back with a stack snapshot in each call to the profiler's [StackSnapshotCallback](../../../../docs/framework/unmanaged-api/profiling/stacksnapshotcallback-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f72dd-104">構文</span><span class="sxs-lookup"><span data-stu-id="f72dd-104">Syntax</span></span>  
  
```cpp  
typedef enum _COR_PRF_SNAPSHOT_INFO {  
    COR_PRF_SNAPSHOT_DEFAULT = 0x0,  
    COR_PRF_SNAPSHOT_REGISTER_CONTEXT = 0x1,  
    COR_PRF_SNAPSHOT_X86_OPTIMIZED = 0X2  
} COR_PRF_SNAPSHOT_INFO;  
```  
  
## <a name="members"></a><span data-ttu-id="f72dd-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="f72dd-105">Members</span></span>  
  
|<span data-ttu-id="f72dd-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="f72dd-106">Members</span></span>|<span data-ttu-id="f72dd-107">説明</span><span class="sxs-lookup"><span data-stu-id="f72dd-107">Description</span></span>|  
|-------------|-----------------|  
|`COR_PRF_SNAPSHOT_DEFAULT`|<span data-ttu-id="f72dd-108">`context` パラメーターを除くすべての `StackSnapshotCallback` パラメーターに対して値を渡す必要があることを示します。</span><span class="sxs-lookup"><span data-stu-id="f72dd-108">Indicates that values must be passed for all `StackSnapshotCallback` parameters, except the `context` parameter.</span></span>|  
|`COR_PRF_SNAPSHOT_REGISTER_CONTEXT`|<span data-ttu-id="f72dd-109">`context` パラメーターを含め、すべての `StackSnapshotCallback` パラメーターに対して値を渡す必要があることを示します。</span><span class="sxs-lookup"><span data-stu-id="f72dd-109">Indicates that values must be passed for all `StackSnapshotCallback` parameters, including the `context` parameter.</span></span>|  
|`COR_PRF_SNAPSHOT_X86_OPTIMIZED`|<span data-ttu-id="f72dd-110">よりシンプルで代替のスタックウォークアルゴリズムが使用されることを示します。</span><span class="sxs-lookup"><span data-stu-id="f72dd-110">Indicates that a simpler, alternative stack-walking algorithm will be used.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f72dd-111">コメント</span><span class="sxs-lookup"><span data-stu-id="f72dd-111">Remarks</span></span>  
 <span data-ttu-id="f72dd-112">`COR_PRF_SNAPSHOT_INFO` 列挙体によって指定された値は、 [DoStackSnapshot](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md)メソッドにパラメーターとして渡されます。</span><span class="sxs-lookup"><span data-stu-id="f72dd-112">Values that are provided by the `COR_PRF_SNAPSHOT_INFO` enumeration are passed as parameters to the [DoStackSnapshot](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f72dd-113">要件</span><span class="sxs-lookup"><span data-stu-id="f72dd-113">Requirements</span></span>  
 <span data-ttu-id="f72dd-114">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f72dd-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f72dd-115">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f72dd-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f72dd-116">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f72dd-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f72dd-117">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f72dd-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f72dd-118">参照</span><span class="sxs-lookup"><span data-stu-id="f72dd-118">See also</span></span>

- [<span data-ttu-id="f72dd-119">DoStackSnapshot メソッド</span><span class="sxs-lookup"><span data-stu-id="f72dd-119">DoStackSnapshot Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md)
- [<span data-ttu-id="f72dd-120">列挙型のプロファイリング</span><span class="sxs-lookup"><span data-stu-id="f72dd-120">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
