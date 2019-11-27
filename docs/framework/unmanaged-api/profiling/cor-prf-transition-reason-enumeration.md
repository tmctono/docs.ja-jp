---
title: COR_PRF_TRANSITION_REASON 列挙型
ms.date: 03/30/2017
api_name:
- COR_PRF_TRANSITION_REASON
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_TRANSITION_REASON
helpviewer_keywords:
- COR_PRF_TRANSITION_REASON enumeration [.NET Framework profiling]
ms.assetid: da941118-01b7-4197-ae5b-9f2f8adcd623
topic_type:
- apiref
ms.openlocfilehash: 6d8b408675127cde399a8346f2b9734a0e038cb5
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74427147"
---
# <a name="cor_prf_transition_reason-enumeration"></a><span data-ttu-id="5d418-102">COR_PRF_TRANSITION_REASON 列挙型</span><span class="sxs-lookup"><span data-stu-id="5d418-102">COR_PRF_TRANSITION_REASON Enumeration</span></span>
<span data-ttu-id="5d418-103">マネージド コードからアンマネージド コードへ、またはその逆の遷移の理由を示します。</span><span class="sxs-lookup"><span data-stu-id="5d418-103">Indicates the reason for a transition from managed to unmanaged code, or vice versa.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5d418-104">構文</span><span class="sxs-lookup"><span data-stu-id="5d418-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_PRF_TRANSITION_CALL,  
    COR_PRF_TRANSITION_RETURN  
} COR_PRF_TRANSITION_REASON;  
```  
  
## <a name="members"></a><span data-ttu-id="5d418-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="5d418-105">Members</span></span>  
  
|<span data-ttu-id="5d418-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="5d418-106">Member</span></span>|<span data-ttu-id="5d418-107">説明</span><span class="sxs-lookup"><span data-stu-id="5d418-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_TRANSITION_CALL`|<span data-ttu-id="5d418-108">遷移は、関数の呼び出しによるものです。</span><span class="sxs-lookup"><span data-stu-id="5d418-108">The transition is due to a call into a function.</span></span>|  
|`COR_PRF_TRANSITION_RETURN`|<span data-ttu-id="5d418-109">遷移は、関数からの戻り値によるものです。</span><span class="sxs-lookup"><span data-stu-id="5d418-109">The transition is due to a return from a function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5d418-110">コメント</span><span class="sxs-lookup"><span data-stu-id="5d418-110">Remarks</span></span>  
 <span data-ttu-id="5d418-111">遷移が発生すると、プロファイラーは[ICorProfilerCallback:: ManagedToUnmanagedTransition](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-managedtounmanagedtransition-method.md)または[ICorProfilerCallback:: UnmanagedToManagedTransition](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-unmanagedtomanagedtransition-method.md)コールバックを受け取ります。いずれの場合も、遷移の理由を示すために `COR_PRF_TRANSITION_REASON` 列挙値を提供します。</span><span class="sxs-lookup"><span data-stu-id="5d418-111">When a transition occurs, the profiler receives an [ICorProfilerCallback::ManagedToUnmanagedTransition](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-managedtounmanagedtransition-method.md) or [ICorProfilerCallback::UnmanagedToManagedTransition](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-unmanagedtomanagedtransition-method.md) callback, either of which provides a value of the `COR_PRF_TRANSITION_REASON` enumeration to indicate the reason for the transition.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5d418-112">要件</span><span class="sxs-lookup"><span data-stu-id="5d418-112">Requirements</span></span>  
 <span data-ttu-id="5d418-113">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5d418-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5d418-114">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="5d418-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="5d418-115">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5d418-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5d418-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5d418-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
