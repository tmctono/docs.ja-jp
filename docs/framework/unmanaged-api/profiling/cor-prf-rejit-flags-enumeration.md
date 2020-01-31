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
ms.openlocfilehash: fabbcd497dc2f321da90188cebbac6ed4e147492
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2020
ms.locfileid: "76867088"
---
# <a name="cor_prf_rejit_flags-enumeration"></a><span data-ttu-id="43668-102">COR_PRF_REJIT_FLAGS 列挙型</span><span class="sxs-lookup"><span data-stu-id="43668-102">COR_PRF_REJIT_FLAGS Enumeration</span></span>
<span data-ttu-id="43668-103">[ICorProfilerInfo10:: RequestReJITWithInliners](icorprofilerinfo10-requestrejitwithinliners-method.md) API の動作を示す値を格納します。</span><span class="sxs-lookup"><span data-stu-id="43668-103">Contains values that indicate how the [ICorProfilerInfo10::RequestReJITWithInliners](icorprofilerinfo10-requestrejitwithinliners-method.md) API should behave.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="43668-104">構文</span><span class="sxs-lookup"><span data-stu-id="43668-104">Syntax</span></span>  
  
```cpp  
typedef enum  
{      
    COR_PRF_REJIT_BLOCK_INLINING = 0x1,
    COR_PRF_REJIT_INLINING_CALLBACKS    = 0x2
} COR_PRF_REJIT_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="43668-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="43668-105">Members</span></span>  
  
|<span data-ttu-id="43668-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="43668-106">Member</span></span>|<span data-ttu-id="43668-107">説明</span><span class="sxs-lookup"><span data-stu-id="43668-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_REJIT_BLOCK_INLINING`| <span data-ttu-id="43668-108">ReJITted メソッドは、他のメソッドでインライン化されないようにブロックされます。</span><span class="sxs-lookup"><span data-stu-id="43668-108">ReJITted methods will be blocked from being inlined in other methods.</span></span> |  
|`COR_PRF_REJIT_INLINING_CALLBACKS`| <span data-ttu-id="43668-109">メソッドをインラインで ReJITted する必要があるメソッドのコールバックを `GetFunctionParameters` 受信します。</span><span class="sxs-lookup"><span data-stu-id="43668-109">Receive `GetFunctionParameters` callbacks for any methods that inline the methods requested to be ReJITted.</span></span> |  

## <a name="requirements"></a><span data-ttu-id="43668-110">要件</span><span class="sxs-lookup"><span data-stu-id="43668-110">Requirements</span></span>  
 <span data-ttu-id="43668-111">**プラットフォーム:** 「 [.Net Core でサポートされるオペレーティングシステム](../../../core/install/dependencies.md?tabs=netcore30&pivots=os-windows)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="43668-111">**Platforms:** See [.NET Core supported operating systems](../../../core/install/dependencies.md?tabs=netcore30&pivots=os-windows).</span></span>  
  
 <span data-ttu-id="43668-112">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="43668-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="43668-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="43668-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="43668-114">**.NET Framework のバージョン:** [!INCLUDE[net_core_22](../../../../includes/net-core-22-md.md)]</span><span class="sxs-lookup"><span data-stu-id="43668-114">**.NET Framework Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-22-md.md)]</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="43668-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="43668-115">See also</span></span>

- [<span data-ttu-id="43668-116">列挙型のプロファイリング</span><span class="sxs-lookup"><span data-stu-id="43668-116">Profiling Enumerations</span></span>](profiling-enumerations.md)
