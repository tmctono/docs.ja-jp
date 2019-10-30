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
ms.openlocfilehash: d28f6eab5390194a4089cbbaf1f586c3f53a7db5
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132252"
---
# <a name="cordebugcreateprocessflags-enumeration"></a><span data-ttu-id="b295e-102">CorDebugCreateProcessFlags 列挙型</span><span class="sxs-lookup"><span data-stu-id="b295e-102">CorDebugCreateProcessFlags Enumeration</span></span>
<span data-ttu-id="b295e-103">[ICorDebug:: CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebug-createprocess-method.md)メソッドの呼び出しで使用できる追加のデバッグオプションを提供します。</span><span class="sxs-lookup"><span data-stu-id="b295e-103">Provides additional debugging options that can be used in a call to the [ICorDebug::CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebug-createprocess-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b295e-104">構文</span><span class="sxs-lookup"><span data-stu-id="b295e-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugCreateProcessFlags {  
    DEBUG_NO_SPECIAL_OPTIONS    = 0x0000  
} CorDebugCreateProcessFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="b295e-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="b295e-105">Members</span></span>  
  
|<span data-ttu-id="b295e-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="b295e-106">Member</span></span>|<span data-ttu-id="b295e-107">説明</span><span class="sxs-lookup"><span data-stu-id="b295e-107">Description</span></span>|  
|------------|-----------------|  
|`DEBUG_NO_SPECIAL_OPTIONS`|<span data-ttu-id="b295e-108">特別なオプションは設定されていません。</span><span class="sxs-lookup"><span data-stu-id="b295e-108">No special options are set.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b295e-109">［要件］</span><span class="sxs-lookup"><span data-stu-id="b295e-109">Requirements</span></span>  
 <span data-ttu-id="b295e-110">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b295e-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b295e-111">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b295e-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b295e-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b295e-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b295e-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b295e-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b295e-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="b295e-114">See also</span></span>

- [<span data-ttu-id="b295e-115">列挙型のデバッグ</span><span class="sxs-lookup"><span data-stu-id="b295e-115">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
