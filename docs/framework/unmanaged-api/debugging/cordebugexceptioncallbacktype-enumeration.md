---
title: CorDebugExceptionCallbackType 列挙型
ms.date: 03/30/2017
api_name:
- CorDebugExceptionCallbackType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugExceptionCallbackType
helpviewer_keywords:
- CorDebugExceptionCallbackType enumeration [.NET Framework debugging]
ms.assetid: 4d946ad4-3c19-42cb-bec9-8633325ba769
topic_type:
- apiref
ms.openlocfilehash: 977b1608539a302c6a27a1b54cfb2ad687025fe6
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76789405"
---
# <a name="cordebugexceptioncallbacktype-enumeration"></a><span data-ttu-id="43199-102">CorDebugExceptionCallbackType 列挙型</span><span class="sxs-lookup"><span data-stu-id="43199-102">CorDebugExceptionCallbackType Enumeration</span></span>
<span data-ttu-id="43199-103">[ICorDebugManagedCallback2:: Exception](icordebugmanagedcallback2-exception-method.md)イベントから作成されたコールバックの種類を示します。</span><span class="sxs-lookup"><span data-stu-id="43199-103">Indicates the type of callback that is made from an [ICorDebugManagedCallback2::Exception](icordebugmanagedcallback2-exception-method.md) event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="43199-104">構文</span><span class="sxs-lookup"><span data-stu-id="43199-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugExceptionCallbackType {  
    DEBUG_EXCEPTION_FIRST_CHANCE         = 1,  
    DEBUG_EXCEPTION_USER_FIRST_CHANCE    = 2,  
    DEBUG_EXCEPTION_CATCH_HANDLER_FOUND  = 3,  
    DEBUG_EXCEPTION_UNHANDLED            = 4  
} CorDebugExceptionCallbackType;  
```  
  
## <a name="members"></a><span data-ttu-id="43199-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="43199-105">Members</span></span>  
  
|<span data-ttu-id="43199-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="43199-106">Member</span></span>|<span data-ttu-id="43199-107">説明</span><span class="sxs-lookup"><span data-stu-id="43199-107">Description</span></span>|  
|------------|-----------------|  
|`DEBUG_EXCEPTION_FIRST_CHANCE`|<span data-ttu-id="43199-108">例外がスローされました。</span><span class="sxs-lookup"><span data-stu-id="43199-108">An exception was thrown.</span></span>|  
|`DEBUG_EXCEPTION_USER_FIRST_CHANCE`|<span data-ttu-id="43199-109">例外 windup プロセスによってユーザーコードが入力されました。</span><span class="sxs-lookup"><span data-stu-id="43199-109">The exception windup process entered user code.</span></span>|  
|`DEBUG_EXCEPTION_CATCH_HANDLER_FOUND`|<span data-ttu-id="43199-110">例外 windup プロセスで、ユーザーコードに `catch` ブロックが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="43199-110">The exception windup process found a `catch` block in user code.</span></span>|  
|`DEBUG_EXCEPTION_UNHANDLED`|<span data-ttu-id="43199-111">例外は処理されませんでした。</span><span class="sxs-lookup"><span data-stu-id="43199-111">The exception was not handled.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="43199-112">要件</span><span class="sxs-lookup"><span data-stu-id="43199-112">Requirements</span></span>  
 <span data-ttu-id="43199-113">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="43199-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="43199-114">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="43199-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="43199-115">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="43199-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="43199-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="43199-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43199-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="43199-117">See also</span></span>

- [<span data-ttu-id="43199-118">列挙型のデバッグ</span><span class="sxs-lookup"><span data-stu-id="43199-118">Debugging Enumerations</span></span>](debugging-enumerations.md)
