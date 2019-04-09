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
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59089382"
---
# <a name="cordebugcreateprocessflags-enumeration"></a><span data-ttu-id="72c70-102">CorDebugCreateProcessFlags 列挙型</span><span class="sxs-lookup"><span data-stu-id="72c70-102">CorDebugCreateProcessFlags Enumeration</span></span>
<span data-ttu-id="72c70-103">呼び出しで使用できる追加のデバッグ オプションの提供、 [icordebug::createprocess](../../../../docs/framework/unmanaged-api/debugging/icordebug-createprocess-method.md)メソッド。</span><span class="sxs-lookup"><span data-stu-id="72c70-103">Provides additional debugging options that can be used in a call to the [ICorDebug::CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebug-createprocess-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="72c70-104">構文</span><span class="sxs-lookup"><span data-stu-id="72c70-104">Syntax</span></span>  
  
```  
typedef enum CorDebugCreateProcessFlags {  
    DEBUG_NO_SPECIAL_OPTIONS    = 0x0000  
} CorDebugCreateProcessFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="72c70-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="72c70-105">Members</span></span>  
  
|<span data-ttu-id="72c70-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="72c70-106">Member</span></span>|<span data-ttu-id="72c70-107">説明</span><span class="sxs-lookup"><span data-stu-id="72c70-107">Description</span></span>|  
|------------|-----------------|  
|`DEBUG_NO_SPECIAL_OPTIONS`|<span data-ttu-id="72c70-108">特殊なオプションは設定されません。</span><span class="sxs-lookup"><span data-stu-id="72c70-108">No special options are set.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="72c70-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="72c70-109">Requirements</span></span>  
 <span data-ttu-id="72c70-110">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="72c70-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="72c70-111">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="72c70-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="72c70-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="72c70-112">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="72c70-113">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="72c70-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="72c70-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="72c70-114">See also</span></span>

- [<span data-ttu-id="72c70-115">列挙体のデバッグ</span><span class="sxs-lookup"><span data-stu-id="72c70-115">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
