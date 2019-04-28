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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 36792d01ebdad72271a8b0597a33d83cab34780e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61789585"
---
# <a name="clsidresolutionflags-enumeration"></a><span data-ttu-id="3f768-102">CLSID_RESOLUTION_FLAGS 列挙型</span><span class="sxs-lookup"><span data-stu-id="3f768-102">CLSID_RESOLUTION_FLAGS Enumeration</span></span>
<span data-ttu-id="3f768-103">共通言語ランタイム (CLR) を解決する方法を示す値を含む、`CLSID`します。</span><span class="sxs-lookup"><span data-stu-id="3f768-103">Contains values that indicate how the common language runtime (CLR) should resolve a `CLSID`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3f768-104">構文</span><span class="sxs-lookup"><span data-stu-id="3f768-104">Syntax</span></span>  
  
```  
typedef enum {  
    CLSID_RESOLUTION_DEFAULT      = 0x0,  
    CLSID_RESOLUTION_REGISTERED   = 0x1  
} CLSID_RESOLUTION_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="3f768-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="3f768-105">Members</span></span>  
  
|<span data-ttu-id="3f768-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="3f768-106">Member</span></span>|<span data-ttu-id="3f768-107">説明</span><span class="sxs-lookup"><span data-stu-id="3f768-107">Description</span></span>|  
|------------|-----------------|  
|`CLSID_RESOLUTION_DEFAULT`|<span data-ttu-id="3f768-108">既定の動作を示します。</span><span class="sxs-lookup"><span data-stu-id="3f768-108">Indicates the default behavior.</span></span>|  
|`CLSID_RESOLUTION_REGISTERED`|<span data-ttu-id="3f768-109">ランタイムは、レジストリを検索し、shim ポリシー適用を示します。</span><span class="sxs-lookup"><span data-stu-id="3f768-109">Indicates that the runtime searches the registry and applies shim policy.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="3f768-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="3f768-110">Requirements</span></span>  
 <span data-ttu-id="3f768-111">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3f768-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3f768-112">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="3f768-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3f768-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3f768-113">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f768-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="3f768-114">See also</span></span>

- [<span data-ttu-id="3f768-115">ホスティングの列挙型</span><span class="sxs-lookup"><span data-stu-id="3f768-115">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
