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
ms.openlocfilehash: f1a0fff266e964b506b2dc7c4030caa54abaa5ed
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59171822"
---
# <a name="corpropertyattr-enumeration"></a><span data-ttu-id="99e50-102">CorPropertyAttr 列挙型</span><span class="sxs-lookup"><span data-stu-id="99e50-102">CorPropertyAttr Enumeration</span></span>
<span data-ttu-id="99e50-103">プロパティのメタデータを記述する値が格納されます。</span><span class="sxs-lookup"><span data-stu-id="99e50-103">Contains values that describe the metadata of a property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="99e50-104">構文</span><span class="sxs-lookup"><span data-stu-id="99e50-104">Syntax</span></span>  
  
```  
typedef enum CorPropertyAttr {  
  
    prSpecialName           =   0x0200,   
    prReservedMask          =   0xf400,  
    prRTSpecialName         =   0x0400,  
    prHasDefault            =   0x1000,  
    prUnused                =   0xe9ff  
  
} CorPropertyAttr;  
```  
  
## <a name="members"></a><span data-ttu-id="99e50-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="99e50-105">Members</span></span>  
  
|<span data-ttu-id="99e50-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="99e50-106">Member</span></span>|<span data-ttu-id="99e50-107">説明</span><span class="sxs-lookup"><span data-stu-id="99e50-107">Description</span></span>|  
|------------|-----------------|  
|`prSpecialName`|<span data-ttu-id="99e50-108">プロパティが、特別なであると、その名前を記述しているを指定しますか。</span><span class="sxs-lookup"><span data-stu-id="99e50-108">Specifies that the property is special, and that its name describes how.</span></span>|  
|`prReservedMask`|<span data-ttu-id="99e50-109">共通言語ランタイムでは、内部使用のため予約されています。</span><span class="sxs-lookup"><span data-stu-id="99e50-109">Reserved for internal use by the common language runtime.</span></span>|  
|`prRTSpecialName`|<span data-ttu-id="99e50-110">共通言語ランタイム メタデータの内部 Api がプロパティ名のエンコードを確認する必要がありますを指定します。</span><span class="sxs-lookup"><span data-stu-id="99e50-110">Specifies that the common language runtime metadata internal APIs should check the encoding of the property name.</span></span>|  
|`prHasDefault`|<span data-ttu-id="99e50-111">既定値を持つプロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="99e50-111">Specifies that the property has a default value.</span></span>|  
|`prUnused`|<span data-ttu-id="99e50-112">使用されません。</span><span class="sxs-lookup"><span data-stu-id="99e50-112">Unused.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="99e50-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="99e50-113">Requirements</span></span>  
 <span data-ttu-id="99e50-114">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="99e50-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="99e50-115">**ヘッダー:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="99e50-115">**Header:** CorHdr.h</span></span>  
  
 **<span data-ttu-id="99e50-116">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="99e50-116">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="99e50-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="99e50-117">See also</span></span>

- [<span data-ttu-id="99e50-118">メタデータ列挙体</span><span class="sxs-lookup"><span data-stu-id="99e50-118">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
