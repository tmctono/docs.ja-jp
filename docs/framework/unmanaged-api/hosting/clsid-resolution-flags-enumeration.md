---
title: CLSID_RESOLUTION_FLAGS 列挙型
ms.date: 03/30/2017
api_name:
- CLSID_RESOLUTION_FLAGS
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CLSID_RESOLUTION_FLAGS
helpviewer_keywords:
- CLSID_RESOLUTION_FLAGS enumeration [.NET Framework hosting]
ms.assetid: cd8b9879-962a-4811-aa46-2e2b6bae0d84
topic_type:
- apiref
ms.openlocfilehash: 5ac015f958d9504bbd14a66ead86548b8df32764
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616776"
---
# <a name="clsid_resolution_flags-enumeration"></a><span data-ttu-id="a4f41-102">CLSID_RESOLUTION_FLAGS 列挙型</span><span class="sxs-lookup"><span data-stu-id="a4f41-102">CLSID_RESOLUTION_FLAGS Enumeration</span></span>
<span data-ttu-id="a4f41-103">共通言語ランタイム (CLR: common language runtime) でを解決する方法を示す値を格納し `CLSID` ます。</span><span class="sxs-lookup"><span data-stu-id="a4f41-103">Contains values that indicate how the common language runtime (CLR) should resolve a `CLSID`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a4f41-104">構文</span><span class="sxs-lookup"><span data-stu-id="a4f41-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    CLSID_RESOLUTION_DEFAULT      = 0x0,  
    CLSID_RESOLUTION_REGISTERED   = 0x1  
} CLSID_RESOLUTION_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="a4f41-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="a4f41-105">Members</span></span>  
  
|<span data-ttu-id="a4f41-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="a4f41-106">Member</span></span>|<span data-ttu-id="a4f41-107">説明</span><span class="sxs-lookup"><span data-stu-id="a4f41-107">Description</span></span>|  
|------------|-----------------|  
|`CLSID_RESOLUTION_DEFAULT`|<span data-ttu-id="a4f41-108">既定の動作を示します。</span><span class="sxs-lookup"><span data-stu-id="a4f41-108">Indicates the default behavior.</span></span>|  
|`CLSID_RESOLUTION_REGISTERED`|<span data-ttu-id="a4f41-109">は、ランタイムがレジストリを検索して shim ポリシーを適用することを示します。</span><span class="sxs-lookup"><span data-stu-id="a4f41-109">Indicates that the runtime searches the registry and applies shim policy.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a4f41-110">要件</span><span class="sxs-lookup"><span data-stu-id="a4f41-110">Requirements</span></span>  
 <span data-ttu-id="a4f41-111">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a4f41-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a4f41-112">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="a4f41-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a4f41-113">**.NET Framework のバージョン:**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a4f41-113">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4f41-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="a4f41-114">See also</span></span>

- [<span data-ttu-id="a4f41-115">ホスティングの列挙体</span><span class="sxs-lookup"><span data-stu-id="a4f41-115">Hosting Enumerations</span></span>](hosting-enumerations.md)
