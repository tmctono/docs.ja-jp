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
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59220462"
---
# <a name="cordebughandletype-enumeration"></a><span data-ttu-id="6249a-102">CorDebugHandleType 列挙型</span><span class="sxs-lookup"><span data-stu-id="6249a-102">CorDebugHandleType Enumeration</span></span>
<span data-ttu-id="6249a-103">ハンドル型を示します。</span><span class="sxs-lookup"><span data-stu-id="6249a-103">Indicates the handle type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6249a-104">構文</span><span class="sxs-lookup"><span data-stu-id="6249a-104">Syntax</span></span>  
  
```  
typedef enum CorDebugHandleType {  
    HANDLE_STRONG                  = 1,  
    HANDLE_WEAK_TRACK_RESURRECTION = 2  
} CorDebugHandleType;  
```  
  
## <a name="members"></a><span data-ttu-id="6249a-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="6249a-105">Members</span></span>  
  
|<span data-ttu-id="6249a-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="6249a-106">Member</span></span>|<span data-ttu-id="6249a-107">説明</span><span class="sxs-lookup"><span data-stu-id="6249a-107">Description</span></span>|  
|------------|-----------------|  
|`HANDLE_STRONG`|<span data-ttu-id="6249a-108">ハンドルは、ガベージ コレクションで回収されてからオブジェクトを防ぐことが、強力なです。</span><span class="sxs-lookup"><span data-stu-id="6249a-108">The handle is strong, which prevents an object from being reclaimed by garbage collection.</span></span>|  
|`HANDLE_WEAK_TRACK_RESURRECTION`|<span data-ttu-id="6249a-109">ハンドルは、ガベージ コレクションで回収されてからオブジェクトを回避することできませんが、脆弱です。</span><span class="sxs-lookup"><span data-stu-id="6249a-109">The handle is weak, which does not prevent an object from being reclaimed by garbage collection.</span></span><br /><br /> <span data-ttu-id="6249a-110">オブジェクトを収集するときに、ハンドルは無効になります。</span><span class="sxs-lookup"><span data-stu-id="6249a-110">The handle becomes invalid when the object is collected.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="6249a-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="6249a-111">Requirements</span></span>  
 <span data-ttu-id="6249a-112">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6249a-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6249a-113">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6249a-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6249a-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6249a-114">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="6249a-115">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="6249a-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="6249a-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="6249a-116">See also</span></span>

- [<span data-ttu-id="6249a-117">列挙体のデバッグ</span><span class="sxs-lookup"><span data-stu-id="6249a-117">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
