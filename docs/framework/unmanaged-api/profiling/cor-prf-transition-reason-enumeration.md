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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2556196b7c8f81709e6880962e8ff36e126dd8b0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61599040"
---
# <a name="corprftransitionreason-enumeration"></a><span data-ttu-id="0f972-102">COR_PRF_TRANSITION_REASON 列挙型</span><span class="sxs-lookup"><span data-stu-id="0f972-102">COR_PRF_TRANSITION_REASON Enumeration</span></span>
<span data-ttu-id="0f972-103">マネージド コードからアンマネージド コードへ、またはその逆の遷移の理由を示します。</span><span class="sxs-lookup"><span data-stu-id="0f972-103">Indicates the reason for a transition from managed to unmanaged code, or vice versa.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0f972-104">構文</span><span class="sxs-lookup"><span data-stu-id="0f972-104">Syntax</span></span>  
  
```  
typedef enum {  
    COR_PRF_TRANSITION_CALL,  
    COR_PRF_TRANSITION_RETURN  
} COR_PRF_TRANSITION_REASON;  
```  
  
## <a name="members"></a><span data-ttu-id="0f972-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="0f972-105">Members</span></span>  
  
|<span data-ttu-id="0f972-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="0f972-106">Member</span></span>|<span data-ttu-id="0f972-107">説明</span><span class="sxs-lookup"><span data-stu-id="0f972-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_TRANSITION_CALL`|<span data-ttu-id="0f972-108">移行は、関数を呼び出すのためにです。</span><span class="sxs-lookup"><span data-stu-id="0f972-108">The transition is due to a call into a function.</span></span>|  
|`COR_PRF_TRANSITION_RETURN`|<span data-ttu-id="0f972-109">移行では、関数の戻り値が原因です。</span><span class="sxs-lookup"><span data-stu-id="0f972-109">The transition is due to a return from a function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0f972-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="0f972-110">Remarks</span></span>  
 <span data-ttu-id="0f972-111">遷移が発生したときに、プロファイラーを受け取る、 [icorprofilercallback::managedtounmanagedtransition](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-managedtounmanagedtransition-method.md)または[icorprofilercallback::unmanagedtomanagedtransition](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-unmanagedtomanagedtransition-method.md)コールバック、うちのいずれか値を指定します、`COR_PRF_TRANSITION_REASON`遷移の理由を示す列挙体。</span><span class="sxs-lookup"><span data-stu-id="0f972-111">When a transition occurs, the profiler receives an [ICorProfilerCallback::ManagedToUnmanagedTransition](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-managedtounmanagedtransition-method.md) or [ICorProfilerCallback::UnmanagedToManagedTransition](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-unmanagedtomanagedtransition-method.md) callback, either of which provides a value of the `COR_PRF_TRANSITION_REASON` enumeration to indicate the reason for the transition.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0f972-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="0f972-112">Requirements</span></span>  
 <span data-ttu-id="0f972-113">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="0f972-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0f972-114">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="0f972-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="0f972-115">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0f972-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0f972-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0f972-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
