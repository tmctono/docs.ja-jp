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
ms.openlocfilehash: 1b1d6ad5d465d746f4c1a9400c43613591373322
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/15/2020
ms.locfileid: "90546947"
---
# <a name="cor_prf_rejit_flags-enumeration"></a><span data-ttu-id="62917-102">COR_PRF_REJIT_FLAGS 列挙型</span><span class="sxs-lookup"><span data-stu-id="62917-102">COR_PRF_REJIT_FLAGS Enumeration</span></span>
<span data-ttu-id="62917-103">[ICorProfilerInfo10:: RequestReJITWithInliners](icorprofilerinfo10-requestrejitwithinliners-method.md) API の動作を示す値を格納します。</span><span class="sxs-lookup"><span data-stu-id="62917-103">Contains values that indicate how the [ICorProfilerInfo10::RequestReJITWithInliners](icorprofilerinfo10-requestrejitwithinliners-method.md) API should behave.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="62917-104">構文</span><span class="sxs-lookup"><span data-stu-id="62917-104">Syntax</span></span>  
  
```cpp  
typedef enum  
{
    COR_PRF_REJIT_BLOCK_INLINING = 0x1,
    COR_PRF_REJIT_INLINING_CALLBACKS    = 0x2
} COR_PRF_REJIT_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="62917-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="62917-105">Members</span></span>  
  
|<span data-ttu-id="62917-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="62917-106">Member</span></span>|<span data-ttu-id="62917-107">説明</span><span class="sxs-lookup"><span data-stu-id="62917-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_REJIT_BLOCK_INLINING`| <span data-ttu-id="62917-108">ReJITted メソッドは、他のメソッドでインライン化されないようにブロックされます。</span><span class="sxs-lookup"><span data-stu-id="62917-108">ReJITted methods will be blocked from being inlined in other methods.</span></span> |  
|`COR_PRF_REJIT_INLINING_CALLBACKS`| <span data-ttu-id="62917-109">メソッドをインラインで ReJITted するように `GetFunctionParameters` 要求されたメソッドに対してコールバックを受信します。</span><span class="sxs-lookup"><span data-stu-id="62917-109">Receive `GetFunctionParameters` callbacks for any methods that inline the methods requested to be ReJITted.</span></span> |  

## <a name="requirements"></a><span data-ttu-id="62917-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="62917-110">Requirements</span></span>  
 <span data-ttu-id="62917-111">**プラットフォーム:** 「 [.Net Core でサポートされるオペレーティングシステム](../../../core/install/windows.md?pivots=os-windows)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="62917-111">**Platforms:** See [.NET Core supported operating systems](../../../core/install/windows.md?pivots=os-windows).</span></span>  
  
 <span data-ttu-id="62917-112">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="62917-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="62917-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="62917-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="62917-114">**.NET Framework のバージョン:**[!INCLUDE[net_core_22](../../../../includes/net-core-22-md.md)]</span><span class="sxs-lookup"><span data-stu-id="62917-114">**.NET Framework Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-22-md.md)]</span></span>
  
## <a name="see-also"></a><span data-ttu-id="62917-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="62917-115">See also</span></span>

- [<span data-ttu-id="62917-116">列挙体のプロファイリング</span><span class="sxs-lookup"><span data-stu-id="62917-116">Profiling Enumerations</span></span>](profiling-enumerations.md)
