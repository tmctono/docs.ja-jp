---
title: COR_DEBUG_STEP_RANGE 構造体
ms.date: 03/30/2017
api_name:
- COR_DEBUG_STEP_RANGE
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_DEBUG_STEP_RANGE
helpviewer_keywords:
- COR_DEBUG_STEP_RANGE structure [.NET Framework debugging]
ms.assetid: 8809d00e-beaa-4dcf-b4e8-e89d0a5406b7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 57d7c3256d7b52a4e55dbb5bc420b0438983d2f2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61609530"
---
# <a name="cordebugsteprange-structure"></a><span data-ttu-id="2ea70-102">COR_DEBUG_STEP_RANGE 構造体</span><span class="sxs-lookup"><span data-stu-id="2ea70-102">COR_DEBUG_STEP_RANGE Structure</span></span>
<span data-ttu-id="2ea70-103">コードの範囲に関するオフセット情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="2ea70-103">Contains the offset information for a range of code.</span></span>  
  
 <span data-ttu-id="2ea70-104">この構造が使用者、 [icordebugstepper::steprange](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-steprange-method.md)メソッド。</span><span class="sxs-lookup"><span data-stu-id="2ea70-104">This structure is used by the [ICorDebugStepper::StepRange](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-steprange-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2ea70-105">構文</span><span class="sxs-lookup"><span data-stu-id="2ea70-105">Syntax</span></span>  
  
```  
typedef struct {  
    ULONG32 startOffset;  
    ULONG32 endOffset;  
} COR_DEBUG_STEP_RANGE;  
```  
  
## <a name="members"></a><span data-ttu-id="2ea70-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="2ea70-106">Members</span></span>  
  
|<span data-ttu-id="2ea70-107">メンバー</span><span class="sxs-lookup"><span data-stu-id="2ea70-107">Member</span></span>|<span data-ttu-id="2ea70-108">説明</span><span class="sxs-lookup"><span data-stu-id="2ea70-108">Description</span></span>|  
|------------|-----------------|  
|`startOffset`|<span data-ttu-id="2ea70-109">範囲の先頭のオフセット。</span><span class="sxs-lookup"><span data-stu-id="2ea70-109">The offset of the beginning of the range.</span></span>|  
|`endOffset`|<span data-ttu-id="2ea70-110">範囲の最後のオフセット。</span><span class="sxs-lookup"><span data-stu-id="2ea70-110">The offset of the end of the range.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="2ea70-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="2ea70-111">Requirements</span></span>  
 <span data-ttu-id="2ea70-112">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="2ea70-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2ea70-113">**ヘッダー:** CorDebug.idl</span><span class="sxs-lookup"><span data-stu-id="2ea70-113">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="2ea70-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2ea70-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2ea70-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2ea70-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ea70-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="2ea70-116">See also</span></span>

- [<span data-ttu-id="2ea70-117">StepRange メソッド</span><span class="sxs-lookup"><span data-stu-id="2ea70-117">StepRange Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-steprange-method.md)
- [<span data-ttu-id="2ea70-118">デバッグ構造体</span><span class="sxs-lookup"><span data-stu-id="2ea70-118">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [<span data-ttu-id="2ea70-119">デバッグ</span><span class="sxs-lookup"><span data-stu-id="2ea70-119">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
