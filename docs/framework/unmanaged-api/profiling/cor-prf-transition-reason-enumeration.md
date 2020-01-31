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
ms.openlocfilehash: 1c3c311fd431b6c0b18af3d6516973b2471cfabd
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2020
ms.locfileid: "76867056"
---
# <a name="cor_prf_transition_reason-enumeration"></a><span data-ttu-id="4c626-102">COR_PRF_TRANSITION_REASON 列挙型</span><span class="sxs-lookup"><span data-stu-id="4c626-102">COR_PRF_TRANSITION_REASON Enumeration</span></span>
<span data-ttu-id="4c626-103">マネージド コードからアンマネージド コードへ、またはその逆の遷移の理由を示します。</span><span class="sxs-lookup"><span data-stu-id="4c626-103">Indicates the reason for a transition from managed to unmanaged code, or vice versa.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4c626-104">構文</span><span class="sxs-lookup"><span data-stu-id="4c626-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_PRF_TRANSITION_CALL,  
    COR_PRF_TRANSITION_RETURN  
} COR_PRF_TRANSITION_REASON;  
```  
  
## <a name="members"></a><span data-ttu-id="4c626-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="4c626-105">Members</span></span>  
  
|<span data-ttu-id="4c626-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="4c626-106">Member</span></span>|<span data-ttu-id="4c626-107">説明</span><span class="sxs-lookup"><span data-stu-id="4c626-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_TRANSITION_CALL`|<span data-ttu-id="4c626-108">遷移は、関数の呼び出しによるものです。</span><span class="sxs-lookup"><span data-stu-id="4c626-108">The transition is due to a call into a function.</span></span>|  
|`COR_PRF_TRANSITION_RETURN`|<span data-ttu-id="4c626-109">遷移は、関数からの戻り値によるものです。</span><span class="sxs-lookup"><span data-stu-id="4c626-109">The transition is due to a return from a function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4c626-110">コメント</span><span class="sxs-lookup"><span data-stu-id="4c626-110">Remarks</span></span>  
 <span data-ttu-id="4c626-111">遷移が発生すると、プロファイラーは[ICorProfilerCallback:: ManagedToUnmanagedTransition](icorprofilercallback-managedtounmanagedtransition-method.md)または[ICorProfilerCallback:: UnmanagedToManagedTransition](icorprofilercallback-unmanagedtomanagedtransition-method.md)コールバックを受け取ります。いずれの場合も、遷移の理由を示すために `COR_PRF_TRANSITION_REASON` 列挙値を提供します。</span><span class="sxs-lookup"><span data-stu-id="4c626-111">When a transition occurs, the profiler receives an [ICorProfilerCallback::ManagedToUnmanagedTransition](icorprofilercallback-managedtounmanagedtransition-method.md) or [ICorProfilerCallback::UnmanagedToManagedTransition](icorprofilercallback-unmanagedtomanagedtransition-method.md) callback, either of which provides a value of the `COR_PRF_TRANSITION_REASON` enumeration to indicate the reason for the transition.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4c626-112">要件</span><span class="sxs-lookup"><span data-stu-id="4c626-112">Requirements</span></span>  
 <span data-ttu-id="4c626-113">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4c626-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4c626-114">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="4c626-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="4c626-115">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4c626-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4c626-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4c626-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
