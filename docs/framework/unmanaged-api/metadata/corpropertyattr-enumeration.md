---
title: CorPropertyAttr 列挙型
ms.date: 03/30/2017
api_name:
- CorPropertyAttr
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorPropertyAttr
helpviewer_keywords:
- CorPropertyAttr enumeration [.NET Framework metadata]
ms.assetid: 58ac8202-854d-4efd-acfb-d2da8b446e12
topic_type:
- apiref
ms.openlocfilehash: 95a798d662b44cf2e088af84d3b1eec97da8e7fb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177937"
---
# <a name="corpropertyattr-enumeration"></a><span data-ttu-id="38910-102">CorPropertyAttr 列挙型</span><span class="sxs-lookup"><span data-stu-id="38910-102">CorPropertyAttr Enumeration</span></span>
<span data-ttu-id="38910-103">プロパティのメタデータを記述する値が格納されます。</span><span class="sxs-lookup"><span data-stu-id="38910-103">Contains values that describe the metadata of a property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="38910-104">構文</span><span class="sxs-lookup"><span data-stu-id="38910-104">Syntax</span></span>  
  
```cpp  
typedef enum CorPropertyAttr {  
  
    prSpecialName           =   0x0200,
    prReservedMask          =   0xf400,  
    prRTSpecialName         =   0x0400,  
    prHasDefault            =   0x1000,  
    prUnused                =   0xe9ff  
  
} CorPropertyAttr;  
```  
  
## <a name="members"></a><span data-ttu-id="38910-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="38910-105">Members</span></span>  
  
|<span data-ttu-id="38910-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="38910-106">Member</span></span>|<span data-ttu-id="38910-107">説明</span><span class="sxs-lookup"><span data-stu-id="38910-107">Description</span></span>|  
|------------|-----------------|  
|`prSpecialName`|<span data-ttu-id="38910-108">プロパティが特別であり、その名前が使用方法を記述することを指定します。</span><span class="sxs-lookup"><span data-stu-id="38910-108">Specifies that the property is special, and that its name describes how.</span></span>|  
|`prReservedMask`|<span data-ttu-id="38910-109">共通言語ランタイムで内部使用のために予約されています。</span><span class="sxs-lookup"><span data-stu-id="38910-109">Reserved for internal use by the common language runtime.</span></span>|  
|`prRTSpecialName`|<span data-ttu-id="38910-110">共通言語ランタイムのメタデータ内部 API がプロパティ名のエンコーディングをチェックすることを指定します。</span><span class="sxs-lookup"><span data-stu-id="38910-110">Specifies that the common language runtime metadata internal APIs should check the encoding of the property name.</span></span>|  
|`prHasDefault`|<span data-ttu-id="38910-111">プロパティが既定値を持つことを指定します。</span><span class="sxs-lookup"><span data-stu-id="38910-111">Specifies that the property has a default value.</span></span>|  
|`prUnused`|<span data-ttu-id="38910-112">未使用。</span><span class="sxs-lookup"><span data-stu-id="38910-112">Unused.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="38910-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="38910-113">Requirements</span></span>  
 <span data-ttu-id="38910-114">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="38910-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="38910-115">**ヘッダー:** コルドル.h</span><span class="sxs-lookup"><span data-stu-id="38910-115">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="38910-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="38910-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38910-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="38910-117">See also</span></span>

- [<span data-ttu-id="38910-118">メタデータ列挙体</span><span class="sxs-lookup"><span data-stu-id="38910-118">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
