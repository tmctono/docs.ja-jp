---
title: CorDebugHandleType 列挙型
ms.date: 03/30/2017
api_name:
- CorDebugHandleType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugHandleType
helpviewer_keywords:
- CorDebugHandleType enumeration [.NET Framework debugging]
ms.assetid: 84296b55-c2c5-424c-ac9c-8e28e2895945
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 513fc93bdac71e2a3ba59ebb53fdde44f1659af5
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59220462"
---
# <a name="cordebughandletype-enumeration"></a><span data-ttu-id="3b62d-102">CorDebugHandleType 列挙型</span><span class="sxs-lookup"><span data-stu-id="3b62d-102">CorDebugHandleType Enumeration</span></span>
<span data-ttu-id="3b62d-103">ハンドル型を示します。</span><span class="sxs-lookup"><span data-stu-id="3b62d-103">Indicates the handle type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3b62d-104">構文</span><span class="sxs-lookup"><span data-stu-id="3b62d-104">Syntax</span></span>  
  
```  
typedef enum CorDebugHandleType {  
    HANDLE_STRONG                  = 1,  
    HANDLE_WEAK_TRACK_RESURRECTION = 2  
} CorDebugHandleType;  
```  
  
## <a name="members"></a><span data-ttu-id="3b62d-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="3b62d-105">Members</span></span>  
  
|<span data-ttu-id="3b62d-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="3b62d-106">Member</span></span>|<span data-ttu-id="3b62d-107">説明</span><span class="sxs-lookup"><span data-stu-id="3b62d-107">Description</span></span>|  
|------------|-----------------|  
|`HANDLE_STRONG`|<span data-ttu-id="3b62d-108">ハンドルは、ガベージ コレクションで回収されてからオブジェクトを防ぐことが、強力なです。</span><span class="sxs-lookup"><span data-stu-id="3b62d-108">The handle is strong, which prevents an object from being reclaimed by garbage collection.</span></span>|  
|`HANDLE_WEAK_TRACK_RESURRECTION`|<span data-ttu-id="3b62d-109">ハンドルは、ガベージ コレクションで回収されてからオブジェクトを回避することできませんが、脆弱です。</span><span class="sxs-lookup"><span data-stu-id="3b62d-109">The handle is weak, which does not prevent an object from being reclaimed by garbage collection.</span></span><br /><br /> <span data-ttu-id="3b62d-110">オブジェクトを収集するときに、ハンドルは無効になります。</span><span class="sxs-lookup"><span data-stu-id="3b62d-110">The handle becomes invalid when the object is collected.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="3b62d-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="3b62d-111">Requirements</span></span>  
 <span data-ttu-id="3b62d-112">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3b62d-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3b62d-113">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3b62d-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3b62d-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3b62d-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3b62d-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3b62d-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b62d-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="3b62d-116">See also</span></span>

- [<span data-ttu-id="3b62d-117">列挙型のデバッグ</span><span class="sxs-lookup"><span data-stu-id="3b62d-117">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
