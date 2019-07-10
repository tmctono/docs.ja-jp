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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b712ee0bb8e67f448b7ea2bee3c092367181abad
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67740217"
---
# <a name="cordebugexceptioncallbacktype-enumeration"></a><span data-ttu-id="5a60e-102">CorDebugExceptionCallbackType 列挙型</span><span class="sxs-lookup"><span data-stu-id="5a60e-102">CorDebugExceptionCallbackType Enumeration</span></span>
<span data-ttu-id="5a60e-103">行われるコールバックの型を示す、 [icordebugmanagedcallback 2::exception](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-exception-method.md)イベント。</span><span class="sxs-lookup"><span data-stu-id="5a60e-103">Indicates the type of callback that is made from an [ICorDebugManagedCallback2::Exception](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-exception-method.md) event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5a60e-104">構文</span><span class="sxs-lookup"><span data-stu-id="5a60e-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugExceptionCallbackType {  
    DEBUG_EXCEPTION_FIRST_CHANCE         = 1,  
    DEBUG_EXCEPTION_USER_FIRST_CHANCE    = 2,  
    DEBUG_EXCEPTION_CATCH_HANDLER_FOUND  = 3,  
    DEBUG_EXCEPTION_UNHANDLED            = 4  
} CorDebugExceptionCallbackType;  
```  
  
## <a name="members"></a><span data-ttu-id="5a60e-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="5a60e-105">Members</span></span>  
  
|<span data-ttu-id="5a60e-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="5a60e-106">Member</span></span>|<span data-ttu-id="5a60e-107">説明</span><span class="sxs-lookup"><span data-stu-id="5a60e-107">Description</span></span>|  
|------------|-----------------|  
|`DEBUG_EXCEPTION_FIRST_CHANCE`|<span data-ttu-id="5a60e-108">例外がスローされました。</span><span class="sxs-lookup"><span data-stu-id="5a60e-108">An exception was thrown.</span></span>|  
|`DEBUG_EXCEPTION_USER_FIRST_CHANCE`|<span data-ttu-id="5a60e-109">例外のワインド プロセスでは、ユーザー コードを入力します。</span><span class="sxs-lookup"><span data-stu-id="5a60e-109">The exception windup process entered user code.</span></span>|  
|`DEBUG_EXCEPTION_CATCH_HANDLER_FOUND`|<span data-ttu-id="5a60e-110">例外のワインド処理、`catch`ユーザー コードでブロックします。</span><span class="sxs-lookup"><span data-stu-id="5a60e-110">The exception windup process found a `catch` block in user code.</span></span>|  
|`DEBUG_EXCEPTION_UNHANDLED`|<span data-ttu-id="5a60e-111">例外は処理されませんでした。</span><span class="sxs-lookup"><span data-stu-id="5a60e-111">The exception was not handled.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5a60e-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="5a60e-112">Requirements</span></span>  
 <span data-ttu-id="5a60e-113">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5a60e-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5a60e-114">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5a60e-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5a60e-115">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5a60e-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5a60e-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5a60e-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a60e-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="5a60e-117">See also</span></span>

- [<span data-ttu-id="5a60e-118">列挙型のデバッグ</span><span class="sxs-lookup"><span data-stu-id="5a60e-118">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
