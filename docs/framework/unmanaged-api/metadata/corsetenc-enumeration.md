---
title: CorSetENC 列挙型
ms.date: 03/30/2017
api_name:
- CorSetENC
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorSetENC
helpviewer_keywords:
- CorSetENC enumeration [.NET Framework metadata]
ms.assetid: fe4150e8-071d-43fb-8e06-c3c616dbeed2
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1fd903cb4a9ce664b7a1c958a3fef0c639d6845d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59122318"
---
# <a name="corsetenc-enumeration"></a><span data-ttu-id="af511-102">CorSetENC 列挙型</span><span class="sxs-lookup"><span data-stu-id="af511-102">CorSetENC Enumeration</span></span>
<span data-ttu-id="af511-103">メタデータの生成中の動作を決定する値が格納されます。</span><span class="sxs-lookup"><span data-stu-id="af511-103">Contains values used to influence behavior during the generation of metadata.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="af511-104">構文</span><span class="sxs-lookup"><span data-stu-id="af511-104">Syntax</span></span>  
  
```  
typedef enum CorSetENC {  
  
    MDSetENCOn                  = 0x00000001,  
    MDSetENCOff                 = 0x00000002,  
  
    MDUpdateENC                 = 0x00000001,  
    MDUpdateFull                = 0x00000002,  
    MDUpdateExtension           = 0x00000003,  
    MDUpdateIncremental         = 0x00000004,  
    MDUpdateDelta               = 0x00000005,  
    MDUpdateMask                = 0x00000007  
  
} CorSetENC;  
```  
  
## <a name="members"></a><span data-ttu-id="af511-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="af511-105">Members</span></span>  
  
|<span data-ttu-id="af511-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="af511-106">Member</span></span>|<span data-ttu-id="af511-107">説明</span><span class="sxs-lookup"><span data-stu-id="af511-107">Description</span></span>|  
|------------|-----------------|  
|`MDSetENCOn`|<span data-ttu-id="af511-108">互換性のために残されています。</span><span class="sxs-lookup"><span data-stu-id="af511-108">Obsolete.</span></span>|  
|`MDSetENCOff`|<span data-ttu-id="af511-109">互換性のために残されています。</span><span class="sxs-lookup"><span data-stu-id="af511-109">Obsolete.</span></span>|  
|`MDUpdateENC`|<span data-ttu-id="af511-110">一方、メタデータを更新するには、トークン移動できないことを示します。</span><span class="sxs-lookup"><span data-stu-id="af511-110">Indicates that whereas metadata can be updated, tokens cannot be moved.</span></span>|  
|`MDUpdateFull`|<span data-ttu-id="af511-111">トークンを更新中に移動できることを示します。</span><span class="sxs-lookup"><span data-stu-id="af511-111">Indicates that tokens can be moved during updates.</span></span>|  
|`MDUpdateExtension`|<span data-ttu-id="af511-112">追加機能のみを更新できますで構成されることを示します。</span><span class="sxs-lookup"><span data-stu-id="af511-112">Indicates that updates can consist only of additions.</span></span> <span data-ttu-id="af511-113">トークンを移動することはできません。</span><span class="sxs-lookup"><span data-stu-id="af511-113">Tokens cannot be moved.</span></span>|  
|`MDUpdateIncremental`|<span data-ttu-id="af511-114">コンパイルが増分であることを示します。</span><span class="sxs-lookup"><span data-stu-id="af511-114">Indicates that compilation is incremental.</span></span>|  
|`MDUpdateDelta`|<span data-ttu-id="af511-115">その唯一の変更されたメタデータを保存するかを示します。</span><span class="sxs-lookup"><span data-stu-id="af511-115">Indicates that only changed metadata should be saved.</span></span>|  
|`MDUpdateMask`|<span data-ttu-id="af511-116">含まれています`MDUpdateENC`、`MDUpdateFull`と`MDUpdateIncremental`します。</span><span class="sxs-lookup"><span data-stu-id="af511-116">Includes `MDUpdateENC`, `MDUpdateFull` and `MDUpdateIncremental`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="af511-117">必要条件</span><span class="sxs-lookup"><span data-stu-id="af511-117">Requirements</span></span>  
 <span data-ttu-id="af511-118">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="af511-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="af511-119">**ヘッダー:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="af511-119">**Header:** CorHdr.h</span></span>  
  
 **<span data-ttu-id="af511-120">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="af511-120">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="af511-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="af511-121">See also</span></span>

- [<span data-ttu-id="af511-122">メタデータ列挙体</span><span class="sxs-lookup"><span data-stu-id="af511-122">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
