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
ms.openlocfilehash: 206e4fb232f4786a76525d24aa379b25d6d2f71d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73099347"
---
# <a name="cor_debug_step_range-structure"></a><span data-ttu-id="0aafc-102">COR_DEBUG_STEP_RANGE 構造体</span><span class="sxs-lookup"><span data-stu-id="0aafc-102">COR_DEBUG_STEP_RANGE Structure</span></span>
<span data-ttu-id="0aafc-103">コードの範囲に関するオフセット情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="0aafc-103">Contains the offset information for a range of code.</span></span>  
  
 <span data-ttu-id="0aafc-104">この構造体は、 [ICorDebugStepper:: StepRange](icordebugstepper-steprange-method.md)メソッドによって使用されます。</span><span class="sxs-lookup"><span data-stu-id="0aafc-104">This structure is used by the [ICorDebugStepper::StepRange](icordebugstepper-steprange-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0aafc-105">構文</span><span class="sxs-lookup"><span data-stu-id="0aafc-105">Syntax</span></span>  
  
```cpp  
typedef struct {  
    ULONG32 startOffset;  
    ULONG32 endOffset;  
} COR_DEBUG_STEP_RANGE;  
```  
  
## <a name="members"></a><span data-ttu-id="0aafc-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="0aafc-106">Members</span></span>  
  
|<span data-ttu-id="0aafc-107">メンバー</span><span class="sxs-lookup"><span data-stu-id="0aafc-107">Member</span></span>|<span data-ttu-id="0aafc-108">説明</span><span class="sxs-lookup"><span data-stu-id="0aafc-108">Description</span></span>|  
|------------|-----------------|  
|`startOffset`|<span data-ttu-id="0aafc-109">範囲の先頭のオフセット。</span><span class="sxs-lookup"><span data-stu-id="0aafc-109">The offset of the beginning of the range.</span></span>|  
|`endOffset`|<span data-ttu-id="0aafc-110">範囲の末尾のオフセット。</span><span class="sxs-lookup"><span data-stu-id="0aafc-110">The offset of the end of the range.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0aafc-111">［要件］</span><span class="sxs-lookup"><span data-stu-id="0aafc-111">Requirements</span></span>  
 <span data-ttu-id="0aafc-112">**:** 「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0aafc-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0aafc-113">**ヘッダー:** CorDebug .idl</span><span class="sxs-lookup"><span data-stu-id="0aafc-113">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="0aafc-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0aafc-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0aafc-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0aafc-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0aafc-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="0aafc-116">See also</span></span>

- [<span data-ttu-id="0aafc-117">StepRange メソッド</span><span class="sxs-lookup"><span data-stu-id="0aafc-117">StepRange Method</span></span>](icordebugstepper-steprange-method.md)
- [<span data-ttu-id="0aafc-118">デバッグ構造体</span><span class="sxs-lookup"><span data-stu-id="0aafc-118">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="0aafc-119">デバッグ</span><span class="sxs-lookup"><span data-stu-id="0aafc-119">Debugging</span></span>](index.md)
