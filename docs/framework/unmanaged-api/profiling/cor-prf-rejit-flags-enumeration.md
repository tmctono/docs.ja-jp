---
title: COR_PRF_REJIT_FLAGS 列挙型
ms.date: 08/06/2019
api_name:
- COR_PRF_REJIT_FLAGS Enumeration
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_REJIT_FLAGS
helpviewer_keywords:
- COR_PRF_REJIT_FLAGS enumeration [.NET Framework profiling]
topic_type:
- apiref
author: davmason
ms.author: davmason
ms.openlocfilehash: 3b4f85072b9dcf87d696b979fa6cbf4e59393f82
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "77453040"
---
# <a name="cor_prf_rejit_flags-enumeration"></a><span data-ttu-id="52bbb-102">COR_PRF_REJIT_FLAGS 列挙型</span><span class="sxs-lookup"><span data-stu-id="52bbb-102">COR_PRF_REJIT_FLAGS Enumeration</span></span>
<span data-ttu-id="52bbb-103">[ICorProfilerInfo10:: RequestReJITWithInliners](icorprofilerinfo10-requestrejitwithinliners-method.md) API の動作を示す値を格納します。</span><span class="sxs-lookup"><span data-stu-id="52bbb-103">Contains values that indicate how the [ICorProfilerInfo10::RequestReJITWithInliners](icorprofilerinfo10-requestrejitwithinliners-method.md) API should behave.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="52bbb-104">構文</span><span class="sxs-lookup"><span data-stu-id="52bbb-104">Syntax</span></span>  
  
```cpp  
typedef enum  
{      
    COR_PRF_REJIT_BLOCK_INLINING = 0x1,
    COR_PRF_REJIT_INLINING_CALLBACKS    = 0x2
} COR_PRF_REJIT_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="52bbb-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="52bbb-105">Members</span></span>  
  
|<span data-ttu-id="52bbb-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="52bbb-106">Member</span></span>|<span data-ttu-id="52bbb-107">説明</span><span class="sxs-lookup"><span data-stu-id="52bbb-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_REJIT_BLOCK_INLINING`| <span data-ttu-id="52bbb-108">ReJITted メソッドは、他のメソッドでインライン化されないようにブロックされます。</span><span class="sxs-lookup"><span data-stu-id="52bbb-108">ReJITted methods will be blocked from being inlined in other methods.</span></span> |  
|`COR_PRF_REJIT_INLINING_CALLBACKS`| <span data-ttu-id="52bbb-109">メソッドをインラインで ReJITted する必要があるメソッドのコールバックを `GetFunctionParameters` 受信します。</span><span class="sxs-lookup"><span data-stu-id="52bbb-109">Receive `GetFunctionParameters` callbacks for any methods that inline the methods requested to be ReJITted.</span></span> |  

## <a name="requirements"></a><span data-ttu-id="52bbb-110">要件</span><span class="sxs-lookup"><span data-stu-id="52bbb-110">Requirements</span></span>  
 <span data-ttu-id="52bbb-111">**プラットフォーム:** 「 [.Net Core でサポートされるオペレーティングシステム](../../../core/install/dependencies.md?pivots=os-windows)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="52bbb-111">**Platforms:** See [.NET Core supported operating systems](../../../core/install/dependencies.md?pivots=os-windows).</span></span>  
  
 <span data-ttu-id="52bbb-112">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="52bbb-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="52bbb-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="52bbb-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="52bbb-114">**.NET Framework のバージョン:** [!INCLUDE[net_core_22](../../../../includes/net-core-22-md.md)]</span><span class="sxs-lookup"><span data-stu-id="52bbb-114">**.NET Framework Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-22-md.md)]</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="52bbb-115">参照</span><span class="sxs-lookup"><span data-stu-id="52bbb-115">See also</span></span>

- [<span data-ttu-id="52bbb-116">列挙型のプロファイリング</span><span class="sxs-lookup"><span data-stu-id="52bbb-116">Profiling Enumerations</span></span>](profiling-enumerations.md)
