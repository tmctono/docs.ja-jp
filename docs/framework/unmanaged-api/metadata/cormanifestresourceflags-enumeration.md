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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 204f04b1ed1ea293639e0b9826f7e0ce6f384763
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59198544"
---
# <a name="cormanifestresourceflags-enumeration"></a><span data-ttu-id="ef34c-102">CorManifestResourceFlags 列挙型</span><span class="sxs-lookup"><span data-stu-id="ef34c-102">CorManifestResourceFlags Enumeration</span></span>
<span data-ttu-id="ef34c-103">アセンブリ マニフェストでエンコードされているリソースの可視性を示します。</span><span class="sxs-lookup"><span data-stu-id="ef34c-103">Indicates the visibility of resources encoded in an assembly manifest.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ef34c-104">構文</span><span class="sxs-lookup"><span data-stu-id="ef34c-104">Syntax</span></span>  
  
```  
typedef enum CorManifestResourceFlags {  
  
    mrVisibilityMask        =   0x0007,  
    mrPublic                =   0x0001,  
    mrPrivate               =   0x0002  
  
} CorManifestResourceFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="ef34c-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="ef34c-105">Members</span></span>  
  
|<span data-ttu-id="ef34c-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="ef34c-106">Member</span></span>|<span data-ttu-id="ef34c-107">説明</span><span class="sxs-lookup"><span data-stu-id="ef34c-107">Description</span></span>|  
|------------|-----------------|  
|`mrVisibilityMask`|<span data-ttu-id="ef34c-108">予約済み。</span><span class="sxs-lookup"><span data-stu-id="ef34c-108">Reserved.</span></span>|  
|`mrPublic`|<span data-ttu-id="ef34c-109">リソースはパブリックです。</span><span class="sxs-lookup"><span data-stu-id="ef34c-109">The resources are public.</span></span>|  
|`mrPrivate`|<span data-ttu-id="ef34c-110">リソースはプライベートです。</span><span class="sxs-lookup"><span data-stu-id="ef34c-110">The resources are private.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ef34c-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="ef34c-111">Requirements</span></span>  
 <span data-ttu-id="ef34c-112">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ef34c-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ef34c-113">**ヘッダー:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="ef34c-113">**Header:** CorHdr.h</span></span>  
  
 **<span data-ttu-id="ef34c-114">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="ef34c-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="ef34c-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="ef34c-115">See also</span></span>

- [<span data-ttu-id="ef34c-116">メタデータ列挙体</span><span class="sxs-lookup"><span data-stu-id="ef34c-116">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
