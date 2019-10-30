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
ms.openlocfilehash: 5a957a042875b546a18a17422f355b712756e91c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73098171"
---
# <a name="cordebughandletype-enumeration"></a><span data-ttu-id="23640-102">CorDebugHandleType 列挙型</span><span class="sxs-lookup"><span data-stu-id="23640-102">CorDebugHandleType Enumeration</span></span>
<span data-ttu-id="23640-103">ハンドル型を示します。</span><span class="sxs-lookup"><span data-stu-id="23640-103">Indicates the handle type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="23640-104">構文</span><span class="sxs-lookup"><span data-stu-id="23640-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugHandleType {  
    HANDLE_STRONG                  = 1,  
    HANDLE_WEAK_TRACK_RESURRECTION = 2  
} CorDebugHandleType;  
```  
  
## <a name="members"></a><span data-ttu-id="23640-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="23640-105">Members</span></span>  
  
|<span data-ttu-id="23640-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="23640-106">Member</span></span>|<span data-ttu-id="23640-107">説明</span><span class="sxs-lookup"><span data-stu-id="23640-107">Description</span></span>|  
|------------|-----------------|  
|`HANDLE_STRONG`|<span data-ttu-id="23640-108">ハンドルは strong であり、ガベージコレクションによってオブジェクトが解放されるのを防ぎます。</span><span class="sxs-lookup"><span data-stu-id="23640-108">The handle is strong, which prevents an object from being reclaimed by garbage collection.</span></span>|  
|`HANDLE_WEAK_TRACK_RESURRECTION`|<span data-ttu-id="23640-109">ハンドルは脆弱であり、ガベージコレクションによってオブジェクトが解放されるのを防ぐことはできません。</span><span class="sxs-lookup"><span data-stu-id="23640-109">The handle is weak, which does not prevent an object from being reclaimed by garbage collection.</span></span><br /><br /> <span data-ttu-id="23640-110">オブジェクトが収集されると、ハンドルは無効になります。</span><span class="sxs-lookup"><span data-stu-id="23640-110">The handle becomes invalid when the object is collected.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="23640-111">［要件］</span><span class="sxs-lookup"><span data-stu-id="23640-111">Requirements</span></span>  
 <span data-ttu-id="23640-112">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="23640-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="23640-113">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="23640-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="23640-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="23640-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="23640-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="23640-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23640-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="23640-116">See also</span></span>

- [<span data-ttu-id="23640-117">列挙型のデバッグ</span><span class="sxs-lookup"><span data-stu-id="23640-117">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
