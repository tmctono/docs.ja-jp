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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7562ec10b6822ae0ec1478cdb077578493ea0b7a
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67781879"
---
# <a name="coreventattr-enumeration"></a><span data-ttu-id="3a160-102">CorEventAttr 列挙型</span><span class="sxs-lookup"><span data-stu-id="3a160-102">CorEventAttr Enumeration</span></span>
<span data-ttu-id="3a160-103">イベントのメタデータを記述する値が格納されます。</span><span class="sxs-lookup"><span data-stu-id="3a160-103">Contains values that describe the metadata of an event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3a160-104">構文</span><span class="sxs-lookup"><span data-stu-id="3a160-104">Syntax</span></span>  
  
```cpp  
typedef enum CorEventAttr {  
  
    evSpecialName           =   0x0200,  
  
    evReservedMask          =   0x0400,  
    evRTSpecialName         =   0x0400,  
  
} CorEventAttr;  
```  
  
## <a name="members"></a><span data-ttu-id="3a160-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="3a160-105">Members</span></span>  
  
|<span data-ttu-id="3a160-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="3a160-106">Member</span></span>|<span data-ttu-id="3a160-107">説明</span><span class="sxs-lookup"><span data-stu-id="3a160-107">Description</span></span>|  
|------------|-----------------|  
|`evSpecialName`|<span data-ttu-id="3a160-108">イベントでは、特別なとその名前が説明を指定する方法。</span><span class="sxs-lookup"><span data-stu-id="3a160-108">Specifies that the event is special, and that its name describes how.</span></span>|  
|`evReservedMask`|<span data-ttu-id="3a160-109">共通言語ランタイムでは、内部使用のため予約されています。</span><span class="sxs-lookup"><span data-stu-id="3a160-109">Reserved for internal use by the common language runtime.</span></span>|  
|`evRTSpecialName`|<span data-ttu-id="3a160-110">イベント名のエンコーディングに共通言語ランタイムが確認する必要がありますを指定します。</span><span class="sxs-lookup"><span data-stu-id="3a160-110">Specifies that the common language runtime should check the encoding of the event name.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="3a160-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="3a160-111">Requirements</span></span>  
 <span data-ttu-id="3a160-112">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3a160-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3a160-113">**ヘッダー:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="3a160-113">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="3a160-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3a160-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a160-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="3a160-115">See also</span></span>

- [<span data-ttu-id="3a160-116">メタデータ列挙型</span><span class="sxs-lookup"><span data-stu-id="3a160-116">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
