---
title: CorDebugStepReason 列挙型
ms.date: 03/30/2017
api_name:
- CorDebugStepReason
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugStepReason
helpviewer_keywords:
- CorDebugStepReason enumeration [.NET Framework debugging]
ms.assetid: fe248069-b33c-48e1-a777-06ac9b239c54
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3ce2b23306e7e38f3982f8d5a4b377aa2f9547c4
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59186252"
---
# <a name="cordebugstepreason-enumeration"></a><span data-ttu-id="f7cfc-102">CorDebugStepReason 列挙型</span><span class="sxs-lookup"><span data-stu-id="f7cfc-102">CorDebugStepReason Enumeration</span></span>
<span data-ttu-id="f7cfc-103">個々のステップの結果を示します。</span><span class="sxs-lookup"><span data-stu-id="f7cfc-103">Indicates the outcome of an individual step.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f7cfc-104">構文</span><span class="sxs-lookup"><span data-stu-id="f7cfc-104">Syntax</span></span>  
  
```  
typedef enum CorDebugStepReason {  
    STEP_NORMAL,  
    STEP_RETURN,  
    STEP_CALL,  
    STEP_EXCEPTION_FILTER,  
    STEP_EXCEPTION_HANDLER,  
    STEP_INTERCEPT,  
    STEP_EXIT  
} CorDebugStepReason;  
```  
  
## <a name="members"></a><span data-ttu-id="f7cfc-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="f7cfc-105">Members</span></span>  
  
|<span data-ttu-id="f7cfc-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="f7cfc-106">Member</span></span>|<span data-ttu-id="f7cfc-107">説明</span><span class="sxs-lookup"><span data-stu-id="f7cfc-107">Description</span></span>|  
|------------|-----------------|  
|`STEP_NORMAL`|<span data-ttu-id="f7cfc-108">ステップ実行は、同じ関数内で通常は、完了。</span><span class="sxs-lookup"><span data-stu-id="f7cfc-108">Stepping completed normally, within the same function.</span></span>|  
|`STEP_RETURN`|<span data-ttu-id="f7cfc-109">ステップ実行を続行通常、関数が返された後。</span><span class="sxs-lookup"><span data-stu-id="f7cfc-109">Stepping continued normally, after the function returned.</span></span>|  
|`STEP_CALL`|<span data-ttu-id="f7cfc-110">新しく呼び出された関数の先頭には通常、続きステップ実行します。</span><span class="sxs-lookup"><span data-stu-id="f7cfc-110">Stepping continued normally, at the beginning of a newly called function.</span></span>|  
|`STEP_EXCEPTION_FILTER`|<span data-ttu-id="f7cfc-111">例外が発生しました、例外フィルターに制御が渡されます。</span><span class="sxs-lookup"><span data-stu-id="f7cfc-111">An exception was generated and control was passed to an exception filter.</span></span>|  
|`STEP_EXCEPTION_HANDLER`|<span data-ttu-id="f7cfc-112">例外が発生しました、例外ハンドラーに制御が渡されます。</span><span class="sxs-lookup"><span data-stu-id="f7cfc-112">An exception was generated and control was passed to an exception handler.</span></span>|  
|`STEP_INTERCEPT`|<span data-ttu-id="f7cfc-113">コントロールは、インターセプターに渡されました。</span><span class="sxs-lookup"><span data-stu-id="f7cfc-113">Control was passed to an interceptor.</span></span>|  
|`STEP_EXIT`|<span data-ttu-id="f7cfc-114">ステップが完了する前に、スレッドが終了しました。</span><span class="sxs-lookup"><span data-stu-id="f7cfc-114">The thread exited before the step was completed.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f7cfc-115">必要条件</span><span class="sxs-lookup"><span data-stu-id="f7cfc-115">Requirements</span></span>  
 <span data-ttu-id="f7cfc-116">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f7cfc-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f7cfc-117">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f7cfc-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f7cfc-118">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f7cfc-118">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="f7cfc-119">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="f7cfc-119">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="f7cfc-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="f7cfc-120">See also</span></span>

- [<span data-ttu-id="f7cfc-121">StepComplete メソッド</span><span class="sxs-lookup"><span data-stu-id="f7cfc-121">StepComplete Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-stepcomplete-method.md)
- [<span data-ttu-id="f7cfc-122">列挙体のデバッグ</span><span class="sxs-lookup"><span data-stu-id="f7cfc-122">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
