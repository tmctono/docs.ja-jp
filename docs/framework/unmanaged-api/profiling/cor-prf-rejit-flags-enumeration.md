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
ms.openlocfilehash: c616cb45eadab3a55aa76526d530cb2841e6d5fa
ms.sourcegitcommit: a97ecb94437362b21fffc5eb3c38b6c0b4368999
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/13/2019
ms.locfileid: "68974112"
---
# <a name="cor_prf_rejit_flags-enumeration"></a><span data-ttu-id="bb4bc-102">COR_PRF_REJIT_FLAGS 列挙型</span><span class="sxs-lookup"><span data-stu-id="bb4bc-102">COR_PRF_REJIT_FLAGS Enumeration</span></span>
<span data-ttu-id="bb4bc-103">[ICorProfilerInfo10:: RequestReJITWithInliners](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo10-requestrejitwithinliners-method.md) API の動作を示す値を格納します。</span><span class="sxs-lookup"><span data-stu-id="bb4bc-103">Contains values that indicate how the [ICorProfilerInfo10::RequestReJITWithInliners](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo10-requestrejitwithinliners-method.md) API should behave.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bb4bc-104">構文</span><span class="sxs-lookup"><span data-stu-id="bb4bc-104">Syntax</span></span>  
  
```cpp  
typedef enum  
{      
    COR_PRF_REJIT_BLOCK_INLINING = 0x1,
    COR_PRF_REJIT_INLINING_CALLBACKS    = 0x2
} COR_PRF_REJIT_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="bb4bc-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="bb4bc-105">Members</span></span>  
  
|<span data-ttu-id="bb4bc-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="bb4bc-106">Member</span></span>|<span data-ttu-id="bb4bc-107">説明</span><span class="sxs-lookup"><span data-stu-id="bb4bc-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_REJIT_BLOCK_INLINING`| <span data-ttu-id="bb4bc-108">ReJITted メソッドは、他のメソッドでインライン化されないようにブロックされます。</span><span class="sxs-lookup"><span data-stu-id="bb4bc-108">ReJITted methods will be blocked from being inlined in other methods.</span></span> |  
|`COR_PRF_REJIT_INLINING_CALLBACKS`| <span data-ttu-id="bb4bc-109">メソッド`GetFunctionParameters`をインラインで ReJITted するように要求されたメソッドに対してコールバックを受信します。</span><span class="sxs-lookup"><span data-stu-id="bb4bc-109">Receive `GetFunctionParameters` callbacks for any methods that inline the methods requested to be ReJITted.</span></span> |  

## <a name="requirements"></a><span data-ttu-id="bb4bc-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="bb4bc-110">Requirements</span></span>  
 <span data-ttu-id="bb4bc-111">**・** 「 [.Net Core でサポートされるオペレーティングシステム](../../../core/windows-prerequisites.md#net-core-supported-operating-systems)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bb4bc-111">**Platforms:** See [.NET Core supported operating systems](../../../core/windows-prerequisites.md#net-core-supported-operating-systems).</span></span>  
  
 <span data-ttu-id="bb4bc-112">**ヘッダー:** Corprof.idl、Corprof.idl</span><span class="sxs-lookup"><span data-stu-id="bb4bc-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="bb4bc-113">**ライブラリ**CorGuids .lib</span><span class="sxs-lookup"><span data-stu-id="bb4bc-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bb4bc-114">**.NET Framework のバージョン:** [!INCLUDE[net_core_22](../../../../includes/net-core-22-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bb4bc-114">**.NET Framework Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-22-md.md)]</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="bb4bc-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="bb4bc-115">See also</span></span>

- [<span data-ttu-id="bb4bc-116">列挙型のプロファイリング</span><span class="sxs-lookup"><span data-stu-id="bb4bc-116">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
