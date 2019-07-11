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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e5fb70d530af24798636972de0a4d6280dbcb8f1
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67781627"
---
# <a name="corpropertyattr-enumeration"></a><span data-ttu-id="73d32-102">CorPropertyAttr 列挙型</span><span class="sxs-lookup"><span data-stu-id="73d32-102">CorPropertyAttr Enumeration</span></span>
<span data-ttu-id="73d32-103">プロパティのメタデータを記述する値が格納されます。</span><span class="sxs-lookup"><span data-stu-id="73d32-103">Contains values that describe the metadata of a property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="73d32-104">構文</span><span class="sxs-lookup"><span data-stu-id="73d32-104">Syntax</span></span>  
  
```cpp  
typedef enum CorPropertyAttr {  
  
    prSpecialName           =   0x0200,   
    prReservedMask          =   0xf400,  
    prRTSpecialName         =   0x0400,  
    prHasDefault            =   0x1000,  
    prUnused                =   0xe9ff  
  
} CorPropertyAttr;  
```  
  
## <a name="members"></a><span data-ttu-id="73d32-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="73d32-105">Members</span></span>  
  
|<span data-ttu-id="73d32-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="73d32-106">Member</span></span>|<span data-ttu-id="73d32-107">説明</span><span class="sxs-lookup"><span data-stu-id="73d32-107">Description</span></span>|  
|------------|-----------------|  
|`prSpecialName`|<span data-ttu-id="73d32-108">プロパティが、特別なであると、その名前を記述しているを指定しますか。</span><span class="sxs-lookup"><span data-stu-id="73d32-108">Specifies that the property is special, and that its name describes how.</span></span>|  
|`prReservedMask`|<span data-ttu-id="73d32-109">共通言語ランタイムでは、内部使用のため予約されています。</span><span class="sxs-lookup"><span data-stu-id="73d32-109">Reserved for internal use by the common language runtime.</span></span>|  
|`prRTSpecialName`|<span data-ttu-id="73d32-110">共通言語ランタイム メタデータの内部 Api がプロパティ名のエンコードを確認する必要がありますを指定します。</span><span class="sxs-lookup"><span data-stu-id="73d32-110">Specifies that the common language runtime metadata internal APIs should check the encoding of the property name.</span></span>|  
|`prHasDefault`|<span data-ttu-id="73d32-111">既定値を持つプロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="73d32-111">Specifies that the property has a default value.</span></span>|  
|`prUnused`|<span data-ttu-id="73d32-112">使用されません。</span><span class="sxs-lookup"><span data-stu-id="73d32-112">Unused.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="73d32-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="73d32-113">Requirements</span></span>  
 <span data-ttu-id="73d32-114">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="73d32-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="73d32-115">**ヘッダー:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="73d32-115">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="73d32-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="73d32-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73d32-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="73d32-117">See also</span></span>

- [<span data-ttu-id="73d32-118">メタデータ列挙型</span><span class="sxs-lookup"><span data-stu-id="73d32-118">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
