---
title: CorDebugSetContextFlag 列挙体
ms.date: 03/30/2017
api_name:
- CorDebugSetContextFlag
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugSetContextFlag
helpviewer_keywords:
- CorDebugSetContextFlag enumeration [.NET Framework debugging]
ms.assetid: b30280bb-fe75-44ed-8589-bcff081fae44
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e959ce7a77ad6ceb7f2fc848193cbd9fff028279
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67739621"
---
# <a name="cordebugsetcontextflag-enumeration"></a><span data-ttu-id="c35d6-102">CorDebugSetContextFlag 列挙体</span><span class="sxs-lookup"><span data-stu-id="c35d6-102">CorDebugSetContextFlag Enumeration</span></span>
<span data-ttu-id="c35d6-103">スタック上のアクティブ (またはリーフ) フレーム上からのコンテキストなのか、別のフレームからのアンワインドにより計算されたコンテキストなのかを示します。</span><span class="sxs-lookup"><span data-stu-id="c35d6-103">Indicates whether the context is from the active (or leaf) frame on the stack or has been computed by unwinding from another frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c35d6-104">構文</span><span class="sxs-lookup"><span data-stu-id="c35d6-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugSetContextFlag  
{  
   SET_CONTEXT_FLAG_ACTIVE_FRAME = 1  
   SET_CONTEXT_FLAG_UNWIND_FRAME = 2  
}  CorDebugSetContextFlag;  
```  
  
## <a name="members"></a><span data-ttu-id="c35d6-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="c35d6-105">Members</span></span>  
  
|<span data-ttu-id="c35d6-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="c35d6-106">Member</span></span>|<span data-ttu-id="c35d6-107">説明</span><span class="sxs-lookup"><span data-stu-id="c35d6-107">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="c35d6-108">SET_CONTEXT_FLAG_ACTIVE_FRAME</span><span class="sxs-lookup"><span data-stu-id="c35d6-108">SET_CONTEXT_FLAG_ACTIVE_FRAME</span></span>|<span data-ttu-id="c35d6-109">コンテキストは、スレッドのアクティブなコンテキストです。</span><span class="sxs-lookup"><span data-stu-id="c35d6-109">The context is the thread’s active context.</span></span>|  
|<span data-ttu-id="c35d6-110">SET_CONTEXT_FLAG_UNWIND_FRAME</span><span class="sxs-lookup"><span data-stu-id="c35d6-110">SET_CONTEXT_FLAG_UNWIND_FRAME</span></span>|<span data-ttu-id="c35d6-111">コンテキストが別のフレームからのアンワインドにより計算されます。</span><span class="sxs-lookup"><span data-stu-id="c35d6-111">The context has been computed by unwinding from another frame.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c35d6-112">Remarks</span><span class="sxs-lookup"><span data-stu-id="c35d6-112">Remarks</span></span>  
 <span data-ttu-id="c35d6-113">`CorDebugSetContextFlag` 使用される値を提供します、 [icordebugstackwalk::setcontext](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-setcontext-method.md)メソッド。</span><span class="sxs-lookup"><span data-stu-id="c35d6-113">`CorDebugSetContextFlag` provides values that are used by the [ICorDebugStackWalk::SetContext](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-setcontext-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c35d6-114">必要条件</span><span class="sxs-lookup"><span data-stu-id="c35d6-114">Requirements</span></span>  
 <span data-ttu-id="c35d6-115">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c35d6-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c35d6-116">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c35d6-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c35d6-117">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c35d6-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c35d6-118">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c35d6-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c35d6-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="c35d6-119">See also</span></span>

- [<span data-ttu-id="c35d6-120">列挙型のデバッグ</span><span class="sxs-lookup"><span data-stu-id="c35d6-120">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
- [<span data-ttu-id="c35d6-121">デバッグ</span><span class="sxs-lookup"><span data-stu-id="c35d6-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
