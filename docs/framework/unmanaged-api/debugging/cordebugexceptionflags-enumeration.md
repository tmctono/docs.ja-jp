---
title: CorDebugExceptionFlags 列挙型
ms.date: 03/30/2017
api_name:
- CorDebugExceptionFlags
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugExceptionFlags
helpviewer_keywords:
- CorDebugExceptionFlags enumeration [.NET Framework debugging]
ms.assetid: b22687a8-e9cf-4e65-a1b0-f92a81bc524e
topic_type:
- apiref
ms.openlocfilehash: 198de0aed4e229d7ed8bb1679afc3a0102bd5368
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73098461"
---
# <a name="cordebugexceptionflags-enumeration"></a><span data-ttu-id="c0697-102">CorDebugExceptionFlags 列挙型</span><span class="sxs-lookup"><span data-stu-id="c0697-102">CorDebugExceptionFlags Enumeration</span></span>
<span data-ttu-id="c0697-103">例外に関する追加情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="c0697-103">Provides additional information about an exception.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c0697-104">構文</span><span class="sxs-lookup"><span data-stu-id="c0697-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugExceptionFlags {  
    DEBUG_EXCEPTION_NONE = 0,  
    DEBUG_EXCEPTION_CAN_BE_INTERCEPTED = 0x0001  
} CorDebugExceptionFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="c0697-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="c0697-105">Members</span></span>  
  
|<span data-ttu-id="c0697-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="c0697-106">Member</span></span>|<span data-ttu-id="c0697-107">説明</span><span class="sxs-lookup"><span data-stu-id="c0697-107">Description</span></span>|  
|------------|-----------------|  
|`DEBUG_EXCEPTION_NONE`|<span data-ttu-id="c0697-108">例外がありません。</span><span class="sxs-lookup"><span data-stu-id="c0697-108">There is no exception.</span></span>|  
|`DEBUG_EXCEPTION_CAN_BE_INTERCEPTED`|<span data-ttu-id="c0697-109">例外をインターセプトすることが可能です。</span><span class="sxs-lookup"><span data-stu-id="c0697-109">The exception is interceptable.</span></span><br /><br /> <span data-ttu-id="c0697-110">ただし例外のタイミングによっては、デバッガーが例外をインターセプトできないことがあります。</span><span class="sxs-lookup"><span data-stu-id="c0697-110">The timing of the exception may still be such that the debugger cannot intercept it.</span></span> <span data-ttu-id="c0697-111">たとえば、現行のコールバックの下にマネージド コードがない場合、または just-in-time (JIT) アタッチメントから発生した例外イベントの場合には、例外をインターセプトできません。</span><span class="sxs-lookup"><span data-stu-id="c0697-111">For example, if there is no managed code below the current callback or the exception event resulted from a just-in-time (JIT) attachment, the exception cannot be intercepted.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c0697-112">Remarks</span><span class="sxs-lookup"><span data-stu-id="c0697-112">Remarks</span></span>  
 <span data-ttu-id="c0697-113">この列挙には今後のバージョンで新しい値が追加される可能性があるため、`CorDebugExceptionFlags` を使用するコードは予想外の値に対して準備しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="c0697-113">New values may be added to this enumeration in later versions, so you should prepare code that uses `CorDebugExceptionFlags` for unexpected values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c0697-114">［要件］</span><span class="sxs-lookup"><span data-stu-id="c0697-114">Requirements</span></span>  
 <span data-ttu-id="c0697-115">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c0697-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c0697-116">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c0697-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c0697-117">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c0697-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c0697-118">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c0697-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0697-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="c0697-119">See also</span></span>

- [<span data-ttu-id="c0697-120">列挙型のデバッグ</span><span class="sxs-lookup"><span data-stu-id="c0697-120">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
