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
ms.openlocfilehash: ef3f1d5e78efe37070bb2bdd6d2834178947af7b
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67740081"
---
# <a name="cordebugexceptionunwindcallbacktype-enumeration"></a><span data-ttu-id="96fe1-102">CorDebugExceptionUnwindCallbackType 列挙型</span><span class="sxs-lookup"><span data-stu-id="96fe1-102">CorDebugExceptionUnwindCallbackType Enumeration</span></span>
<span data-ttu-id="96fe1-103">アンワインド フェーズ中にコールバックによって通知されるイベントを示します。</span><span class="sxs-lookup"><span data-stu-id="96fe1-103">Indicates the event that is being signaled by the callback during the unwind phase.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="96fe1-104">構文</span><span class="sxs-lookup"><span data-stu-id="96fe1-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugExceptionUnwindCallbackType {  
    DEBUG_EXCEPTION_UNWIND_BEGIN = 1,  
    DEBUG_EXCEPTION_INTERCEPTED  = 2  
} CorDebugExceptionUnwindCallbackType;  
```  
  
## <a name="members"></a><span data-ttu-id="96fe1-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="96fe1-105">Members</span></span>  
  
|<span data-ttu-id="96fe1-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="96fe1-106">Member</span></span>|<span data-ttu-id="96fe1-107">説明</span><span class="sxs-lookup"><span data-stu-id="96fe1-107">Description</span></span>|  
|------------|-----------------|  
|`DEBUG_EXCEPTION_UNWIND_BEGIN`|<span data-ttu-id="96fe1-108">アンワインド プロセスの開始。</span><span class="sxs-lookup"><span data-stu-id="96fe1-108">The beginning of the unwind process.</span></span>|  
|`DEBUG_EXCEPTION_INTERCEPTED`|<span data-ttu-id="96fe1-109">例外を受け取りました。</span><span class="sxs-lookup"><span data-stu-id="96fe1-109">The exception was intercepted.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="96fe1-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="96fe1-110">Requirements</span></span>  
 <span data-ttu-id="96fe1-111">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="96fe1-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="96fe1-112">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="96fe1-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="96fe1-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="96fe1-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="96fe1-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="96fe1-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96fe1-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="96fe1-115">See also</span></span>

- [<span data-ttu-id="96fe1-116">列挙型のデバッグ</span><span class="sxs-lookup"><span data-stu-id="96fe1-116">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
