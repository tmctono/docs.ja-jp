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
ms.openlocfilehash: c22e3c7c04a2b85723f1c0dba4543465faccab58
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67745486"
---
# <a name="corprftransitionreason-enumeration"></a><span data-ttu-id="0257a-102">COR_PRF_TRANSITION_REASON 列挙型</span><span class="sxs-lookup"><span data-stu-id="0257a-102">COR_PRF_TRANSITION_REASON Enumeration</span></span>
<span data-ttu-id="0257a-103">マネージド コードからアンマネージド コードへ、またはその逆の遷移の理由を示します。</span><span class="sxs-lookup"><span data-stu-id="0257a-103">Indicates the reason for a transition from managed to unmanaged code, or vice versa.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0257a-104">構文</span><span class="sxs-lookup"><span data-stu-id="0257a-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_PRF_TRANSITION_CALL,  
    COR_PRF_TRANSITION_RETURN  
} COR_PRF_TRANSITION_REASON;  
```  
  
## <a name="members"></a><span data-ttu-id="0257a-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="0257a-105">Members</span></span>  
  
|<span data-ttu-id="0257a-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="0257a-106">Member</span></span>|<span data-ttu-id="0257a-107">説明</span><span class="sxs-lookup"><span data-stu-id="0257a-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_TRANSITION_CALL`|<span data-ttu-id="0257a-108">移行は、関数を呼び出すのためにです。</span><span class="sxs-lookup"><span data-stu-id="0257a-108">The transition is due to a call into a function.</span></span>|  
|`COR_PRF_TRANSITION_RETURN`|<span data-ttu-id="0257a-109">移行では、関数の戻り値が原因です。</span><span class="sxs-lookup"><span data-stu-id="0257a-109">The transition is due to a return from a function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0257a-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="0257a-110">Remarks</span></span>  
 <span data-ttu-id="0257a-111">遷移が発生したときに、プロファイラーを受け取る、 [icorprofilercallback::managedtounmanagedtransition](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-managedtounmanagedtransition-method.md)または[icorprofilercallback::unmanagedtomanagedtransition](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-unmanagedtomanagedtransition-method.md)コールバック、うちのいずれか値を指定します、`COR_PRF_TRANSITION_REASON`遷移の理由を示す列挙体。</span><span class="sxs-lookup"><span data-stu-id="0257a-111">When a transition occurs, the profiler receives an [ICorProfilerCallback::ManagedToUnmanagedTransition](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-managedtounmanagedtransition-method.md) or [ICorProfilerCallback::UnmanagedToManagedTransition](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-unmanagedtomanagedtransition-method.md) callback, either of which provides a value of the `COR_PRF_TRANSITION_REASON` enumeration to indicate the reason for the transition.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0257a-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="0257a-112">Requirements</span></span>  
 <span data-ttu-id="0257a-113">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="0257a-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0257a-114">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="0257a-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="0257a-115">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0257a-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0257a-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0257a-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
