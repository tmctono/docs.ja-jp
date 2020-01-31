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
ms.openlocfilehash: a443332e4f2b0351e99754fae610af39268bb105
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76789266"
---
# <a name="cordebugsetcontextflag-enumeration"></a><span data-ttu-id="3f0f2-102">CorDebugSetContextFlag 列挙体</span><span class="sxs-lookup"><span data-stu-id="3f0f2-102">CorDebugSetContextFlag Enumeration</span></span>
<span data-ttu-id="3f0f2-103">スタック上のアクティブ (またはリーフ) フレーム上からのコンテキストなのか、別のフレームからのアンワインドにより計算されたコンテキストなのかを示します。</span><span class="sxs-lookup"><span data-stu-id="3f0f2-103">Indicates whether the context is from the active (or leaf) frame on the stack or has been computed by unwinding from another frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3f0f2-104">構文</span><span class="sxs-lookup"><span data-stu-id="3f0f2-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugSetContextFlag  
{  
   SET_CONTEXT_FLAG_ACTIVE_FRAME = 1  
   SET_CONTEXT_FLAG_UNWIND_FRAME = 2  
}  CorDebugSetContextFlag;  
```  
  
## <a name="members"></a><span data-ttu-id="3f0f2-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="3f0f2-105">Members</span></span>  
  
|<span data-ttu-id="3f0f2-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="3f0f2-106">Member</span></span>|<span data-ttu-id="3f0f2-107">説明</span><span class="sxs-lookup"><span data-stu-id="3f0f2-107">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="3f0f2-108">SET_CONTEXT_FLAG_ACTIVE_FRAME</span><span class="sxs-lookup"><span data-stu-id="3f0f2-108">SET_CONTEXT_FLAG_ACTIVE_FRAME</span></span>|<span data-ttu-id="3f0f2-109">コンテキストは、スレッドのアクティブなコンテキストです。</span><span class="sxs-lookup"><span data-stu-id="3f0f2-109">The context is the thread’s active context.</span></span>|  
|<span data-ttu-id="3f0f2-110">SET_CONTEXT_FLAG_UNWIND_FRAME</span><span class="sxs-lookup"><span data-stu-id="3f0f2-110">SET_CONTEXT_FLAG_UNWIND_FRAME</span></span>|<span data-ttu-id="3f0f2-111">コンテキストは、別のフレームからのアンワインドによって計算されています。</span><span class="sxs-lookup"><span data-stu-id="3f0f2-111">The context has been computed by unwinding from another frame.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3f0f2-112">コメント</span><span class="sxs-lookup"><span data-stu-id="3f0f2-112">Remarks</span></span>  
 <span data-ttu-id="3f0f2-113">`CorDebugSetContextFlag` は、「 [SetContext](icordebugstackwalk-setcontext-method.md)メソッド」で使用されている値を提供します。</span><span class="sxs-lookup"><span data-stu-id="3f0f2-113">`CorDebugSetContextFlag` provides values that are used by the [ICorDebugStackWalk::SetContext](icordebugstackwalk-setcontext-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3f0f2-114">要件</span><span class="sxs-lookup"><span data-stu-id="3f0f2-114">Requirements</span></span>  
 <span data-ttu-id="3f0f2-115">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3f0f2-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3f0f2-116">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3f0f2-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3f0f2-117">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3f0f2-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3f0f2-118">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3f0f2-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f0f2-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="3f0f2-119">See also</span></span>

- [<span data-ttu-id="3f0f2-120">列挙型のデバッグ</span><span class="sxs-lookup"><span data-stu-id="3f0f2-120">Debugging Enumerations</span></span>](debugging-enumerations.md)
- [<span data-ttu-id="3f0f2-121">デバッグ</span><span class="sxs-lookup"><span data-stu-id="3f0f2-121">Debugging</span></span>](index.md)
