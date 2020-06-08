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
ms.openlocfilehash: 6168c5b27868a261871b292e17ca02b04ae89917
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500781"
---
# <a name="cor_prf_snapshot_info-enumeration"></a><span data-ttu-id="95462-102">COR_PRF_SNAPSHOT_INFO 列挙型</span><span class="sxs-lookup"><span data-stu-id="95462-102">COR_PRF_SNAPSHOT_INFO Enumeration</span></span>
<span data-ttu-id="95462-103">プロファイラーの[Stacksnapshotcallback](stacksnapshotcallback-function.md)関数を呼び出すたびに、スタックスナップショットで返すデータ量を指定します。</span><span class="sxs-lookup"><span data-stu-id="95462-103">Specifies how much data to pass back with a stack snapshot in each call to the profiler's [StackSnapshotCallback](stacksnapshotcallback-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="95462-104">構文</span><span class="sxs-lookup"><span data-stu-id="95462-104">Syntax</span></span>  
  
```cpp  
typedef enum _COR_PRF_SNAPSHOT_INFO {  
    COR_PRF_SNAPSHOT_DEFAULT = 0x0,  
    COR_PRF_SNAPSHOT_REGISTER_CONTEXT = 0x1,  
    COR_PRF_SNAPSHOT_X86_OPTIMIZED = 0X2  
} COR_PRF_SNAPSHOT_INFO;  
```  
  
## <a name="members"></a><span data-ttu-id="95462-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="95462-105">Members</span></span>  
  
|<span data-ttu-id="95462-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="95462-106">Members</span></span>|<span data-ttu-id="95462-107">説明</span><span class="sxs-lookup"><span data-stu-id="95462-107">Description</span></span>|  
|-------------|-----------------|  
|`COR_PRF_SNAPSHOT_DEFAULT`|<span data-ttu-id="95462-108">パラメーターを除くすべてのパラメーターに対して値を渡す必要があることを示し `StackSnapshotCallback` `context` ます。</span><span class="sxs-lookup"><span data-stu-id="95462-108">Indicates that values must be passed for all `StackSnapshotCallback` parameters, except the `context` parameter.</span></span>|  
|`COR_PRF_SNAPSHOT_REGISTER_CONTEXT`|<span data-ttu-id="95462-109">パラメーターを含むすべてのパラメーターに対して値を渡す必要があることを示し `StackSnapshotCallback` `context` ます。</span><span class="sxs-lookup"><span data-stu-id="95462-109">Indicates that values must be passed for all `StackSnapshotCallback` parameters, including the `context` parameter.</span></span>|  
|`COR_PRF_SNAPSHOT_X86_OPTIMIZED`|<span data-ttu-id="95462-110">よりシンプルで代替のスタックウォークアルゴリズムが使用されることを示します。</span><span class="sxs-lookup"><span data-stu-id="95462-110">Indicates that a simpler, alternative stack-walking algorithm will be used.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="95462-111">解説</span><span class="sxs-lookup"><span data-stu-id="95462-111">Remarks</span></span>  
 <span data-ttu-id="95462-112">列挙体によって指定された値 `COR_PRF_SNAPSHOT_INFO` は、パラメーターとして[DoStackSnapshot](icorprofilerinfo2-dostacksnapshot-method.md)メソッドに渡されます。</span><span class="sxs-lookup"><span data-stu-id="95462-112">Values that are provided by the `COR_PRF_SNAPSHOT_INFO` enumeration are passed as parameters to the [DoStackSnapshot](icorprofilerinfo2-dostacksnapshot-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="95462-113">要件</span><span class="sxs-lookup"><span data-stu-id="95462-113">Requirements</span></span>  
 <span data-ttu-id="95462-114">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="95462-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="95462-115">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="95462-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="95462-116">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="95462-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="95462-117">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="95462-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95462-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="95462-118">See also</span></span>

- [<span data-ttu-id="95462-119">DoStackSnapshot メソッド</span><span class="sxs-lookup"><span data-stu-id="95462-119">DoStackSnapshot Method</span></span>](icorprofilerinfo2-dostacksnapshot-method.md)
- [<span data-ttu-id="95462-120">列挙体のプロファイリング</span><span class="sxs-lookup"><span data-stu-id="95462-120">Profiling Enumerations</span></span>](profiling-enumerations.md)
