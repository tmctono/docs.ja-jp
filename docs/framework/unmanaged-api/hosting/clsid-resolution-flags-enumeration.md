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
ms.openlocfilehash: 5274e70c5bead201beb158ee2895415d7ec9e53c
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67779132"
---
# <a name="clsidresolutionflags-enumeration"></a><span data-ttu-id="d728e-102">CLSID_RESOLUTION_FLAGS 列挙型</span><span class="sxs-lookup"><span data-stu-id="d728e-102">CLSID_RESOLUTION_FLAGS Enumeration</span></span>
<span data-ttu-id="d728e-103">共通言語ランタイム (CLR) を解決する方法を示す値を含む、`CLSID`します。</span><span class="sxs-lookup"><span data-stu-id="d728e-103">Contains values that indicate how the common language runtime (CLR) should resolve a `CLSID`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d728e-104">構文</span><span class="sxs-lookup"><span data-stu-id="d728e-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    CLSID_RESOLUTION_DEFAULT      = 0x0,  
    CLSID_RESOLUTION_REGISTERED   = 0x1  
} CLSID_RESOLUTION_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="d728e-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="d728e-105">Members</span></span>  
  
|<span data-ttu-id="d728e-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="d728e-106">Member</span></span>|<span data-ttu-id="d728e-107">説明</span><span class="sxs-lookup"><span data-stu-id="d728e-107">Description</span></span>|  
|------------|-----------------|  
|`CLSID_RESOLUTION_DEFAULT`|<span data-ttu-id="d728e-108">既定の動作を示します。</span><span class="sxs-lookup"><span data-stu-id="d728e-108">Indicates the default behavior.</span></span>|  
|`CLSID_RESOLUTION_REGISTERED`|<span data-ttu-id="d728e-109">ランタイムは、レジストリを検索し、shim ポリシー適用を示します。</span><span class="sxs-lookup"><span data-stu-id="d728e-109">Indicates that the runtime searches the registry and applies shim policy.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d728e-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="d728e-110">Requirements</span></span>  
 <span data-ttu-id="d728e-111">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d728e-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d728e-112">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="d728e-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d728e-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d728e-113">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d728e-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="d728e-114">See also</span></span>

- [<span data-ttu-id="d728e-115">ホスティングの列挙型</span><span class="sxs-lookup"><span data-stu-id="d728e-115">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
