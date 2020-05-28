---
title: CorManifestResourceFlags 列挙型
ms.date: 03/30/2017
api_name:
- CorManifestResourceFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorManifestResourceFlags
helpviewer_keywords:
- CorManifestResourceFlags enumeration [.NET Framework metadata]
ms.assetid: 1b0306b7-622b-4b57-8edc-3c713bb147ae
topic_type:
- apiref
ms.openlocfilehash: ebdff88e9fdf499b809d56c4c29a906dbef9ec40
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008977"
---
# <a name="cormanifestresourceflags-enumeration"></a><span data-ttu-id="7c8ad-102">CorManifestResourceFlags 列挙型</span><span class="sxs-lookup"><span data-stu-id="7c8ad-102">CorManifestResourceFlags Enumeration</span></span>
<span data-ttu-id="7c8ad-103">アセンブリマニフェストでエンコードされたリソースを表示するかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="7c8ad-103">Indicates the visibility of resources encoded in an assembly manifest.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7c8ad-104">構文</span><span class="sxs-lookup"><span data-stu-id="7c8ad-104">Syntax</span></span>  
  
```cpp  
typedef enum CorManifestResourceFlags {  
  
    mrVisibilityMask        =   0x0007,  
    mrPublic                =   0x0001,  
    mrPrivate               =   0x0002  
  
} CorManifestResourceFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="7c8ad-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="7c8ad-105">Members</span></span>  
  
|<span data-ttu-id="7c8ad-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="7c8ad-106">Member</span></span>|<span data-ttu-id="7c8ad-107">説明</span><span class="sxs-lookup"><span data-stu-id="7c8ad-107">Description</span></span>|  
|------------|-----------------|  
|`mrVisibilityMask`|<span data-ttu-id="7c8ad-108">予約済み。</span><span class="sxs-lookup"><span data-stu-id="7c8ad-108">Reserved.</span></span>|  
|`mrPublic`|<span data-ttu-id="7c8ad-109">リソースはパブリックです。</span><span class="sxs-lookup"><span data-stu-id="7c8ad-109">The resources are public.</span></span>|  
|`mrPrivate`|<span data-ttu-id="7c8ad-110">リソースはプライベートです。</span><span class="sxs-lookup"><span data-stu-id="7c8ad-110">The resources are private.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="7c8ad-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="7c8ad-111">Requirements</span></span>  
 <span data-ttu-id="7c8ad-112">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7c8ad-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7c8ad-113">**ヘッダー:** CorHdr. h</span><span class="sxs-lookup"><span data-stu-id="7c8ad-113">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="7c8ad-114">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7c8ad-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c8ad-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="7c8ad-115">See also</span></span>

- [<span data-ttu-id="7c8ad-116">メタデータ列挙体</span><span class="sxs-lookup"><span data-stu-id="7c8ad-116">Metadata Enumerations</span></span>](metadata-enumerations.md)
