---
title: CorDebugExceptionObjectStackFrame 構造体
ms.date: 03/30/2017
api_name:
- CorDebugExceptionObjectStackFrame
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugExceptionObjectStackFrame
helpviewer_keywords:
- CorDebugExceptionObjectStackFrame structure [.NET Framework debugging]
ms.assetid: 542cdd81-5ae7-4361-b0ef-1ae4775df258
topic_type:
- apiref
ms.openlocfilehash: faa2082d31c5fa47b87e2238017066b477fdc191
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132168"
---
# <a name="cordebugexceptionobjectstackframe-structure"></a><span data-ttu-id="d8afc-102">CorDebugExceptionObjectStackFrame 構造体</span><span class="sxs-lookup"><span data-stu-id="d8afc-102">CorDebugExceptionObjectStackFrame Structure</span></span>
<span data-ttu-id="d8afc-103">例外オブジェクトのスタック フレームの情報を表しています。</span><span class="sxs-lookup"><span data-stu-id="d8afc-103">Represents stack frame information from an exception object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d8afc-104">構文</span><span class="sxs-lookup"><span data-stu-id="d8afc-104">Syntax</span></span>  
  
```cpp  
typedef struct CorDebugExceptionObjectStackFrame {  
    ICorDebugModule* pModule;  
    CORDB_ADDRESS ip;  
    mdMethodDef methodDef;  
    BOOL isLastForeignExceptionFrame;  
} CorDebugExceptionObjectStackFrame;  
```  
  
## <a name="members"></a><span data-ttu-id="d8afc-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="d8afc-105">Members</span></span>  
  
|<span data-ttu-id="d8afc-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="d8afc-106">Member</span></span>|<span data-ttu-id="d8afc-107">説明</span><span class="sxs-lookup"><span data-stu-id="d8afc-107">Description</span></span>|  
|------------|-----------------|  
|`pModule`|<span data-ttu-id="d8afc-108">現在のフレームのモジュールオブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="d8afc-108">A pointer to the ICorDebugModule object for the current frame.</span></span>|  
|`ip`|<span data-ttu-id="d8afc-109">現在のフレームの命令ポインター (EIP/RIP) の値。</span><span class="sxs-lookup"><span data-stu-id="d8afc-109">The value of the instruction pointer (EIP/RIP) for the current frame.</span></span>|  
|`methodDef`|<span data-ttu-id="d8afc-110">現在のフレームのメソッドトークン。</span><span class="sxs-lookup"><span data-stu-id="d8afc-110">The method token for the current frame.</span></span>|  
|`isLastForeignExceptionFrame`|<span data-ttu-id="d8afc-111">フレームが外部例外の最後のフレームであるかどうかを示す値。</span><span class="sxs-lookup"><span data-stu-id="d8afc-111">A value that indicates whether the frame is the last frame in a foreign exception.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d8afc-112">Remarks</span><span class="sxs-lookup"><span data-stu-id="d8afc-112">Remarks</span></span>  
 <span data-ttu-id="d8afc-113">呼び出し元は、使用されなくなったときに、モジュールオブジェクトへのポインターを解放する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d8afc-113">The caller must release the pointer to the ICorDebugModule object once it is no longer in use.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d8afc-114">［要件］</span><span class="sxs-lookup"><span data-stu-id="d8afc-114">Requirements</span></span>  
 <span data-ttu-id="d8afc-115">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d8afc-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d8afc-116">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d8afc-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d8afc-117">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d8afc-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d8afc-118">**.NET Framework のバージョン:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d8afc-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8afc-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="d8afc-119">See also</span></span>

- [<span data-ttu-id="d8afc-120">デバッグ構造体</span><span class="sxs-lookup"><span data-stu-id="d8afc-120">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [<span data-ttu-id="d8afc-121">デバッグ</span><span class="sxs-lookup"><span data-stu-id="d8afc-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
