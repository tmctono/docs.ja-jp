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
ms.openlocfilehash: 352a45a33a109570f100e91a24cd44dc4f6780e7
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67740147"
---
# <a name="cordebugexceptionflags-enumeration"></a><span data-ttu-id="4a04f-102">CorDebugExceptionFlags 列挙型</span><span class="sxs-lookup"><span data-stu-id="4a04f-102">CorDebugExceptionFlags Enumeration</span></span>
<span data-ttu-id="4a04f-103">例外に関する追加情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="4a04f-103">Provides additional information about an exception.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4a04f-104">構文</span><span class="sxs-lookup"><span data-stu-id="4a04f-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugExceptionFlags {  
    DEBUG_EXCEPTION_NONE = 0,  
    DEBUG_EXCEPTION_CAN_BE_INTERCEPTED = 0x0001  
} CorDebugExceptionFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="4a04f-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="4a04f-105">Members</span></span>  
  
|<span data-ttu-id="4a04f-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="4a04f-106">Member</span></span>|<span data-ttu-id="4a04f-107">説明</span><span class="sxs-lookup"><span data-stu-id="4a04f-107">Description</span></span>|  
|------------|-----------------|  
|`DEBUG_EXCEPTION_NONE`|<span data-ttu-id="4a04f-108">例外がありません。</span><span class="sxs-lookup"><span data-stu-id="4a04f-108">There is no exception.</span></span>|  
|`DEBUG_EXCEPTION_CAN_BE_INTERCEPTED`|<span data-ttu-id="4a04f-109">例外をインターセプトすることが可能です。</span><span class="sxs-lookup"><span data-stu-id="4a04f-109">The exception is interceptable.</span></span><br /><br /> <span data-ttu-id="4a04f-110">ただし例外のタイミングによっては、デバッガーが例外をインターセプトできないことがあります。</span><span class="sxs-lookup"><span data-stu-id="4a04f-110">The timing of the exception may still be such that the debugger cannot intercept it.</span></span> <span data-ttu-id="4a04f-111">たとえば、現行のコールバックの下にマネージド コードがない場合、または just-in-time (JIT) アタッチメントから発生した例外イベントの場合には、例外をインターセプトできません。</span><span class="sxs-lookup"><span data-stu-id="4a04f-111">For example, if there is no managed code below the current callback or the exception event resulted from a just-in-time (JIT) attachment, the exception cannot be intercepted.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4a04f-112">Remarks</span><span class="sxs-lookup"><span data-stu-id="4a04f-112">Remarks</span></span>  
 <span data-ttu-id="4a04f-113">この列挙には今後のバージョンで新しい値が追加される可能性があるため、`CorDebugExceptionFlags` を使用するコードは予想外の値に対して準備しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="4a04f-113">New values may be added to this enumeration in later versions, so you should prepare code that uses `CorDebugExceptionFlags` for unexpected values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4a04f-114">必要条件</span><span class="sxs-lookup"><span data-stu-id="4a04f-114">Requirements</span></span>  
 <span data-ttu-id="4a04f-115">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="4a04f-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4a04f-116">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4a04f-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4a04f-117">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4a04f-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4a04f-118">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4a04f-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a04f-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="4a04f-119">See also</span></span>

- [<span data-ttu-id="4a04f-120">列挙型のデバッグ</span><span class="sxs-lookup"><span data-stu-id="4a04f-120">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
