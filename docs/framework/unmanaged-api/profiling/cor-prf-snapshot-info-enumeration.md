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
ms.openlocfilehash: 97bf3e69a8ea155d53479ba6f61988e56e3bd396
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2020
ms.locfileid: "76867025"
---
# <a name="cor_prf_snapshot_info-enumeration"></a><span data-ttu-id="51e01-102">COR_PRF_SNAPSHOT_INFO 列挙型</span><span class="sxs-lookup"><span data-stu-id="51e01-102">COR_PRF_SNAPSHOT_INFO Enumeration</span></span>
<span data-ttu-id="51e01-103">プロファイラーの[Stacksnapshotcallback](stacksnapshotcallback-function.md)関数を呼び出すたびに、スタックスナップショットで返すデータ量を指定します。</span><span class="sxs-lookup"><span data-stu-id="51e01-103">Specifies how much data to pass back with a stack snapshot in each call to the profiler's [StackSnapshotCallback](stacksnapshotcallback-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="51e01-104">構文</span><span class="sxs-lookup"><span data-stu-id="51e01-104">Syntax</span></span>  
  
```cpp  
typedef enum _COR_PRF_SNAPSHOT_INFO {  
    COR_PRF_SNAPSHOT_DEFAULT = 0x0,  
    COR_PRF_SNAPSHOT_REGISTER_CONTEXT = 0x1,  
    COR_PRF_SNAPSHOT_X86_OPTIMIZED = 0X2  
} COR_PRF_SNAPSHOT_INFO;  
```  
  
## <a name="members"></a><span data-ttu-id="51e01-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="51e01-105">Members</span></span>  
  
|<span data-ttu-id="51e01-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="51e01-106">Members</span></span>|<span data-ttu-id="51e01-107">説明</span><span class="sxs-lookup"><span data-stu-id="51e01-107">Description</span></span>|  
|-------------|-----------------|  
|`COR_PRF_SNAPSHOT_DEFAULT`|<span data-ttu-id="51e01-108">`context` パラメーターを除くすべての `StackSnapshotCallback` パラメーターに対して値を渡す必要があることを示します。</span><span class="sxs-lookup"><span data-stu-id="51e01-108">Indicates that values must be passed for all `StackSnapshotCallback` parameters, except the `context` parameter.</span></span>|  
|`COR_PRF_SNAPSHOT_REGISTER_CONTEXT`|<span data-ttu-id="51e01-109">`context` パラメーターを含め、すべての `StackSnapshotCallback` パラメーターに対して値を渡す必要があることを示します。</span><span class="sxs-lookup"><span data-stu-id="51e01-109">Indicates that values must be passed for all `StackSnapshotCallback` parameters, including the `context` parameter.</span></span>|  
|`COR_PRF_SNAPSHOT_X86_OPTIMIZED`|<span data-ttu-id="51e01-110">よりシンプルで代替のスタックウォークアルゴリズムが使用されることを示します。</span><span class="sxs-lookup"><span data-stu-id="51e01-110">Indicates that a simpler, alternative stack-walking algorithm will be used.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="51e01-111">コメント</span><span class="sxs-lookup"><span data-stu-id="51e01-111">Remarks</span></span>  
 <span data-ttu-id="51e01-112">`COR_PRF_SNAPSHOT_INFO` 列挙体によって指定された値は、 [DoStackSnapshot](icorprofilerinfo2-dostacksnapshot-method.md)メソッドにパラメーターとして渡されます。</span><span class="sxs-lookup"><span data-stu-id="51e01-112">Values that are provided by the `COR_PRF_SNAPSHOT_INFO` enumeration are passed as parameters to the [DoStackSnapshot](icorprofilerinfo2-dostacksnapshot-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="51e01-113">要件</span><span class="sxs-lookup"><span data-stu-id="51e01-113">Requirements</span></span>  
 <span data-ttu-id="51e01-114">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="51e01-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="51e01-115">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="51e01-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="51e01-116">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="51e01-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="51e01-117">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="51e01-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51e01-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="51e01-118">See also</span></span>

- [<span data-ttu-id="51e01-119">DoStackSnapshot メソッド</span><span class="sxs-lookup"><span data-stu-id="51e01-119">DoStackSnapshot Method</span></span>](icorprofilerinfo2-dostacksnapshot-method.md)
- [<span data-ttu-id="51e01-120">列挙型のプロファイリング</span><span class="sxs-lookup"><span data-stu-id="51e01-120">Profiling Enumerations</span></span>](profiling-enumerations.md)
