---
title: CorDebugThreadState 列挙型
ms.date: 03/30/2017
api_name:
- CorDebugThreadState
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugThreadState
helpviewer_keywords:
- CorDebugThreadState enumeration [.NET Framework debugging]
ms.assetid: a3ccdf18-4ec6-494d-9024-48e5c8c724f5
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ce252f5a4b5fbcdbbc7b70c8b1c829490f8f63e5
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67739528"
---
# <a name="cordebugthreadstate-enumeration"></a><span data-ttu-id="be583-102">CorDebugThreadState 列挙型</span><span class="sxs-lookup"><span data-stu-id="be583-102">CorDebugThreadState Enumeration</span></span>
<span data-ttu-id="be583-103">デバッグのスレッドの状態を指定します。</span><span class="sxs-lookup"><span data-stu-id="be583-103">Specifies the state of a thread for debugging.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="be583-104">構文</span><span class="sxs-lookup"><span data-stu-id="be583-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugThreadState {  
    THREAD_RUN,  
    THREAD_SUSPEND  
} CorDebugThreadState;  
```  
  
## <a name="members"></a><span data-ttu-id="be583-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="be583-105">Members</span></span>  
  
|<span data-ttu-id="be583-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="be583-106">Member</span></span>|<span data-ttu-id="be583-107">説明</span><span class="sxs-lookup"><span data-stu-id="be583-107">Description</span></span>|  
|------------|-----------------|  
|`THREAD_RUN`|<span data-ttu-id="be583-108">デバッグ イベントが発生しない限り、スレッドは、自由に実行されます。</span><span class="sxs-lookup"><span data-stu-id="be583-108">The thread runs freely, unless a debug event occurs.</span></span>|  
|`THREAD_SUSPEND`|<span data-ttu-id="be583-109">スレッドは実行できません。</span><span class="sxs-lookup"><span data-stu-id="be583-109">The thread cannot run.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="be583-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="be583-110">Remarks</span></span>  
 <span data-ttu-id="be583-111">デバッガーを使用して、`CorDebugThreadState`スレッドの実行を制御する列挙。</span><span class="sxs-lookup"><span data-stu-id="be583-111">The debugger uses the `CorDebugThreadState` enumeration to control a thread's execution.</span></span> <span data-ttu-id="be583-112">使用してスレッドの状態を設定することができます、 [icordebugthread::setdebugstate](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-setdebugstate-method.md)または[icordebugcontroller::setallthreadsdebugstate](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-setallthreadsdebugstate-method.md)メソッド。</span><span class="sxs-lookup"><span data-stu-id="be583-112">The state of a thread can be set by using the [ICorDebugThread::SetDebugState](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-setdebugstate-method.md) or [ICorDebugController::SetAllThreadsDebugState](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-setallthreadsdebugstate-method.md) method.</span></span>  
  
 <span data-ttu-id="be583-113">提供されるコールバック、 [API をホストしている](../../../../docs/framework/unmanaged-api/hosting/index.md)メッセージ ポンプを使用するため、中断状態は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="be583-113">A callback provided to the [hosting API](../../../../docs/framework/unmanaged-api/hosting/index.md) enables message pumping, so an interrupted state is not needed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="be583-114">必要条件</span><span class="sxs-lookup"><span data-stu-id="be583-114">Requirements</span></span>  
 <span data-ttu-id="be583-115">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="be583-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="be583-116">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="be583-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="be583-117">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="be583-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="be583-118">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="be583-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be583-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="be583-119">See also</span></span>

- [<span data-ttu-id="be583-120">列挙型のデバッグ</span><span class="sxs-lookup"><span data-stu-id="be583-120">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
