---
title: CorDebugExceptionUnwindCallbackType 列挙型
ms.date: 03/30/2017
api_name:
- CorDebugExceptionUnwindCallbackType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugExceptionUnwindCallbackType
helpviewer_keywords:
- CorDebugExceptionUnwindCallbackType enumeration [.NET Framework debugging]
ms.assetid: 783dce92-8a98-43db-8f78-888d943dd5b2
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 408e72eeaa1dac83c45488d186425f30c6043280
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59155624"
---
# <a name="cordebugexceptionunwindcallbacktype-enumeration"></a><span data-ttu-id="fd8c6-102">CorDebugExceptionUnwindCallbackType 列挙型</span><span class="sxs-lookup"><span data-stu-id="fd8c6-102">CorDebugExceptionUnwindCallbackType Enumeration</span></span>
<span data-ttu-id="fd8c6-103">アンワインド フェーズ中にコールバックによって通知されるイベントを示します。</span><span class="sxs-lookup"><span data-stu-id="fd8c6-103">Indicates the event that is being signaled by the callback during the unwind phase.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fd8c6-104">構文</span><span class="sxs-lookup"><span data-stu-id="fd8c6-104">Syntax</span></span>  
  
```  
typedef enum CorDebugExceptionUnwindCallbackType {  
    DEBUG_EXCEPTION_UNWIND_BEGIN = 1,  
    DEBUG_EXCEPTION_INTERCEPTED  = 2  
} CorDebugExceptionUnwindCallbackType;  
```  
  
## <a name="members"></a><span data-ttu-id="fd8c6-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="fd8c6-105">Members</span></span>  
  
|<span data-ttu-id="fd8c6-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="fd8c6-106">Member</span></span>|<span data-ttu-id="fd8c6-107">説明</span><span class="sxs-lookup"><span data-stu-id="fd8c6-107">Description</span></span>|  
|------------|-----------------|  
|`DEBUG_EXCEPTION_UNWIND_BEGIN`|<span data-ttu-id="fd8c6-108">アンワインド プロセスの開始。</span><span class="sxs-lookup"><span data-stu-id="fd8c6-108">The beginning of the unwind process.</span></span>|  
|`DEBUG_EXCEPTION_INTERCEPTED`|<span data-ttu-id="fd8c6-109">例外を受け取りました。</span><span class="sxs-lookup"><span data-stu-id="fd8c6-109">The exception was intercepted.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="fd8c6-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="fd8c6-110">Requirements</span></span>  
 <span data-ttu-id="fd8c6-111">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="fd8c6-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fd8c6-112">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fd8c6-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fd8c6-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fd8c6-113">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="fd8c6-114">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="fd8c6-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="fd8c6-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="fd8c6-115">See also</span></span>

- [<span data-ttu-id="fd8c6-116">列挙体のデバッグ</span><span class="sxs-lookup"><span data-stu-id="fd8c6-116">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
