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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5a4cd4d353c22921ed3dba1dc08fe2cee7e429f8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61996321"
---
# <a name="cordebugexceptionobjectstackframe-structure"></a><span data-ttu-id="1d0fc-102">CorDebugExceptionObjectStackFrame 構造体</span><span class="sxs-lookup"><span data-stu-id="1d0fc-102">CorDebugExceptionObjectStackFrame Structure</span></span>
<span data-ttu-id="1d0fc-103">例外オブジェクトのスタック フレームの情報を表しています。</span><span class="sxs-lookup"><span data-stu-id="1d0fc-103">Represents stack frame information from an exception object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1d0fc-104">構文</span><span class="sxs-lookup"><span data-stu-id="1d0fc-104">Syntax</span></span>  
  
```  
typedef struct CorDebugExceptionObjectStackFrame {  
    ICorDebugModule* pModule;  
    CORDB_ADDRESS ip;  
    mdMethodDef methodDef;  
    BOOL isLastForeignExceptionFrame;  
} CorDebugExceptionObjectStackFrame;  
```  
  
## <a name="members"></a><span data-ttu-id="1d0fc-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="1d0fc-105">Members</span></span>  
  
|<span data-ttu-id="1d0fc-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="1d0fc-106">Member</span></span>|<span data-ttu-id="1d0fc-107">説明</span><span class="sxs-lookup"><span data-stu-id="1d0fc-107">Description</span></span>|  
|------------|-----------------|  
|`pModule`|<span data-ttu-id="1d0fc-108">現在のフレームの ICorDebugModule オブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="1d0fc-108">A pointer to the ICorDebugModule object for the current frame.</span></span>|  
|`ip`|<span data-ttu-id="1d0fc-109">現在のフレームの命令ポインター (EIP/RIP) の値。</span><span class="sxs-lookup"><span data-stu-id="1d0fc-109">The value of the instruction pointer (EIP/RIP) for the current frame.</span></span>|  
|`methodDef`|<span data-ttu-id="1d0fc-110">現在のフレーム メソッド トークンです。</span><span class="sxs-lookup"><span data-stu-id="1d0fc-110">The method token for the current frame.</span></span>|  
|`isLastForeignExceptionFrame`|<span data-ttu-id="1d0fc-111">フレームが外部例外の最後のフレームであるかどうかを示す値。</span><span class="sxs-lookup"><span data-stu-id="1d0fc-111">A value that indicates whether the frame is the last frame in a foreign exception.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1d0fc-112">Remarks</span><span class="sxs-lookup"><span data-stu-id="1d0fc-112">Remarks</span></span>  
 <span data-ttu-id="1d0fc-113">呼び出し元は、使用が ICorDebugModule オブジェクトへのポインターを解放する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1d0fc-113">The caller must release the pointer to the ICorDebugModule object once it is no longer in use.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1d0fc-114">必要条件</span><span class="sxs-lookup"><span data-stu-id="1d0fc-114">Requirements</span></span>  
 <span data-ttu-id="1d0fc-115">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="1d0fc-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1d0fc-116">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1d0fc-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1d0fc-117">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1d0fc-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1d0fc-118">**.NET Framework のバージョン:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1d0fc-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d0fc-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="1d0fc-119">See also</span></span>

- [<span data-ttu-id="1d0fc-120">デバッグ構造体</span><span class="sxs-lookup"><span data-stu-id="1d0fc-120">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [<span data-ttu-id="1d0fc-121">デバッグ</span><span class="sxs-lookup"><span data-stu-id="1d0fc-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
