---
title: CorEventAttr 列挙型
ms.date: 03/30/2017
api_name:
- CorEventAttr
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorEventAttr
helpviewer_keywords:
- CorEventAttr enumeration [.NET Framework metadata]
ms.assetid: dc2b3281-3820-487e-930d-350b66dc6417
topic_type:
- apiref
ms.openlocfilehash: ec2972605c40f4ba292f5a5f58d6d3efed53f966
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74443561"
---
# <a name="coreventattr-enumeration"></a><span data-ttu-id="d6df6-102">CorEventAttr 列挙型</span><span class="sxs-lookup"><span data-stu-id="d6df6-102">CorEventAttr Enumeration</span></span>
<span data-ttu-id="d6df6-103">イベントのメタデータを記述する値が格納されます。</span><span class="sxs-lookup"><span data-stu-id="d6df6-103">Contains values that describe the metadata of an event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d6df6-104">構文</span><span class="sxs-lookup"><span data-stu-id="d6df6-104">Syntax</span></span>  
  
```cpp  
typedef enum CorEventAttr {  
  
    evSpecialName           =   0x0200,  
  
    evReservedMask          =   0x0400,  
    evRTSpecialName         =   0x0400,  
  
} CorEventAttr;  
```  
  
## <a name="members"></a><span data-ttu-id="d6df6-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="d6df6-105">Members</span></span>  
  
|<span data-ttu-id="d6df6-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="d6df6-106">Member</span></span>|<span data-ttu-id="d6df6-107">説明</span><span class="sxs-lookup"><span data-stu-id="d6df6-107">Description</span></span>|  
|------------|-----------------|  
|`evSpecialName`|<span data-ttu-id="d6df6-108">イベントが特別であり、その名前がどのように記述するかを指定します。</span><span class="sxs-lookup"><span data-stu-id="d6df6-108">Specifies that the event is special, and that its name describes how.</span></span>|  
|`evReservedMask`|<span data-ttu-id="d6df6-109">共通言語ランタイムによる内部使用のために予約されています。</span><span class="sxs-lookup"><span data-stu-id="d6df6-109">Reserved for internal use by the common language runtime.</span></span>|  
|`evRTSpecialName`|<span data-ttu-id="d6df6-110">共通言語ランタイムがイベント名のエンコーディングを確認する必要があることを指定します。</span><span class="sxs-lookup"><span data-stu-id="d6df6-110">Specifies that the common language runtime should check the encoding of the event name.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d6df6-111">要件</span><span class="sxs-lookup"><span data-stu-id="d6df6-111">Requirements</span></span>  
 <span data-ttu-id="d6df6-112">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d6df6-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d6df6-113">**ヘッダー:** CorHdr. h</span><span class="sxs-lookup"><span data-stu-id="d6df6-113">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="d6df6-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d6df6-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6df6-115">参照</span><span class="sxs-lookup"><span data-stu-id="d6df6-115">See also</span></span>

- [<span data-ttu-id="d6df6-116">メタデータ列挙型</span><span class="sxs-lookup"><span data-stu-id="d6df6-116">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
