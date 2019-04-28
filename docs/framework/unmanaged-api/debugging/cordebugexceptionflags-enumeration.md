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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2c7b9b25673685dde8b75702c80f525515917ae1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61915254"
---
# <a name="cordebugexceptionflags-enumeration"></a><span data-ttu-id="6d1de-102">CorDebugExceptionFlags 列挙型</span><span class="sxs-lookup"><span data-stu-id="6d1de-102">CorDebugExceptionFlags Enumeration</span></span>
<span data-ttu-id="6d1de-103">例外に関する追加情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="6d1de-103">Provides additional information about an exception.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6d1de-104">構文</span><span class="sxs-lookup"><span data-stu-id="6d1de-104">Syntax</span></span>  
  
```  
typedef enum CorDebugExceptionFlags {  
    DEBUG_EXCEPTION_NONE = 0,  
    DEBUG_EXCEPTION_CAN_BE_INTERCEPTED = 0x0001  
} CorDebugExceptionFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="6d1de-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="6d1de-105">Members</span></span>  
  
|<span data-ttu-id="6d1de-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="6d1de-106">Member</span></span>|<span data-ttu-id="6d1de-107">説明</span><span class="sxs-lookup"><span data-stu-id="6d1de-107">Description</span></span>|  
|------------|-----------------|  
|`DEBUG_EXCEPTION_NONE`|<span data-ttu-id="6d1de-108">例外がありません。</span><span class="sxs-lookup"><span data-stu-id="6d1de-108">There is no exception.</span></span>|  
|`DEBUG_EXCEPTION_CAN_BE_INTERCEPTED`|<span data-ttu-id="6d1de-109">例外をインターセプトすることが可能です。</span><span class="sxs-lookup"><span data-stu-id="6d1de-109">The exception is interceptable.</span></span><br /><br /> <span data-ttu-id="6d1de-110">ただし例外のタイミングによっては、デバッガーが例外をインターセプトできないことがあります。</span><span class="sxs-lookup"><span data-stu-id="6d1de-110">The timing of the exception may still be such that the debugger cannot intercept it.</span></span> <span data-ttu-id="6d1de-111">たとえば、現行のコールバックの下にマネージド コードがない場合、または just-in-time (JIT) アタッチメントから発生した例外イベントの場合には、例外をインターセプトできません。</span><span class="sxs-lookup"><span data-stu-id="6d1de-111">For example, if there is no managed code below the current callback or the exception event resulted from a just-in-time (JIT) attachment, the exception cannot be intercepted.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6d1de-112">Remarks</span><span class="sxs-lookup"><span data-stu-id="6d1de-112">Remarks</span></span>  
 <span data-ttu-id="6d1de-113">この列挙には今後のバージョンで新しい値が追加される可能性があるため、`CorDebugExceptionFlags` を使用するコードは予想外の値に対して準備しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="6d1de-113">New values may be added to this enumeration in later versions, so you should prepare code that uses `CorDebugExceptionFlags` for unexpected values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6d1de-114">必要条件</span><span class="sxs-lookup"><span data-stu-id="6d1de-114">Requirements</span></span>  
 <span data-ttu-id="6d1de-115">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6d1de-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6d1de-116">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6d1de-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6d1de-117">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6d1de-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6d1de-118">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6d1de-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d1de-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="6d1de-119">See also</span></span>

- [<span data-ttu-id="6d1de-120">列挙型のデバッグ</span><span class="sxs-lookup"><span data-stu-id="6d1de-120">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
