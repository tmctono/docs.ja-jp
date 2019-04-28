---
title: CorDebugCreateProcessFlags 列挙型
ms.date: 03/30/2017
api_name:
- CorDebugCreateProcessFlags
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugCreateProcessFlags
helpviewer_keywords:
- CorDebugCreateProcessFlags enumeration [.NET Framework debugging]
ms.assetid: e709acce-6a17-4346-b38a-467dba567358
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ae3ba480e208762f5a80f9f1b78dd008f02b6df4
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61609114"
---
# <a name="cordebugcreateprocessflags-enumeration"></a><span data-ttu-id="cf46c-102">CorDebugCreateProcessFlags 列挙型</span><span class="sxs-lookup"><span data-stu-id="cf46c-102">CorDebugCreateProcessFlags Enumeration</span></span>
<span data-ttu-id="cf46c-103">呼び出しで使用できる追加のデバッグ オプションの提供、 [icordebug::createprocess](../../../../docs/framework/unmanaged-api/debugging/icordebug-createprocess-method.md)メソッド。</span><span class="sxs-lookup"><span data-stu-id="cf46c-103">Provides additional debugging options that can be used in a call to the [ICorDebug::CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebug-createprocess-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cf46c-104">構文</span><span class="sxs-lookup"><span data-stu-id="cf46c-104">Syntax</span></span>  
  
```  
typedef enum CorDebugCreateProcessFlags {  
    DEBUG_NO_SPECIAL_OPTIONS    = 0x0000  
} CorDebugCreateProcessFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="cf46c-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="cf46c-105">Members</span></span>  
  
|<span data-ttu-id="cf46c-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="cf46c-106">Member</span></span>|<span data-ttu-id="cf46c-107">説明</span><span class="sxs-lookup"><span data-stu-id="cf46c-107">Description</span></span>|  
|------------|-----------------|  
|`DEBUG_NO_SPECIAL_OPTIONS`|<span data-ttu-id="cf46c-108">特殊なオプションは設定されません。</span><span class="sxs-lookup"><span data-stu-id="cf46c-108">No special options are set.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="cf46c-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="cf46c-109">Requirements</span></span>  
 <span data-ttu-id="cf46c-110">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="cf46c-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cf46c-111">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cf46c-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cf46c-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cf46c-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cf46c-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cf46c-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf46c-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="cf46c-114">See also</span></span>

- [<span data-ttu-id="cf46c-115">列挙型のデバッグ</span><span class="sxs-lookup"><span data-stu-id="cf46c-115">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
