---
title: CorTokenType 列挙型
ms.date: 03/30/2017
api_name:
- CorTokenType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorTokenType
helpviewer_keywords:
- CorTokenType enumeration [.NET Framework metadata]
ms.assetid: 93c9a369-225f-4eff-9b78-3fbee4902cf1
topic_type:
- apiref
ms.openlocfilehash: 629e18b6cd2fd7910804ecc608a45d2406dddea1
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007495"
---
# <a name="cortokentype-enumeration"></a><span data-ttu-id="5b71b-102">CorTokenType 列挙型</span><span class="sxs-lookup"><span data-stu-id="5b71b-102">CorTokenType Enumeration</span></span>
<span data-ttu-id="5b71b-103">メタデータトークンの種類を示します。</span><span class="sxs-lookup"><span data-stu-id="5b71b-103">Indicates the type of a metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5b71b-104">構文</span><span class="sxs-lookup"><span data-stu-id="5b71b-104">Syntax</span></span>  
  
```cpp  
typedef enum CorTokenType {  
  
    mdtModule                       = 0x00000000,  
    mdtTypeRef                      = 0x01000000,  
    mdtTypeDef                      = 0x02000000,  
    mdtFieldDef                     = 0x04000000,  
    mdtMethodDef                    = 0x06000000,  
    mdtParamDef                     = 0x08000000,  
    mdtInterfaceImpl                = 0x09000000,  
    mdtMemberRef                    = 0x0a000000,  
    mdtCustomAttribute              = 0x0c000000,  
    mdtPermission                   = 0x0e000000,  
    mdtSignature                    = 0x11000000,  
    mdtEvent                        = 0x14000000,  
    mdtProperty                     = 0x17000000,  
    mdtModuleRef                    = 0x1a000000,  
    mdtTypeSpec                     = 0x1b000000,  
    mdtAssembly                     = 0x20000000,  
    mdtAssemblyRef                  = 0x23000000,  
    mdtFile                         = 0x26000000,  
    mdtExportedType                 = 0x27000000,  
    mdtManifestResource             = 0x28000000,  
    mdtGenericParam                 = 0x2a000000,  
    mdtMethodSpec                   = 0x2b000000,  
    mdtGenericParamConstraint       = 0x2c000000,  
    mdtString                       = 0x70000000,  
    mdtName                         = 0x71000000,  
    mdtBaseType                     = 0x72000000  
  
} CorTokenType;  
```  
  
## <a name="members"></a><span data-ttu-id="5b71b-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="5b71b-105">Members</span></span>  
  
|<span data-ttu-id="5b71b-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="5b71b-106">Member</span></span>|<span data-ttu-id="5b71b-107">説明</span><span class="sxs-lookup"><span data-stu-id="5b71b-107">Description</span></span>|  
|------------|-----------------|  
|`mdtModule`|<span data-ttu-id="5b71b-108">`mdModule`トークン。</span><span class="sxs-lookup"><span data-stu-id="5b71b-108">An `mdModule` token.</span></span>|  
|`mdtTypeRef`|<span data-ttu-id="5b71b-109">`mdTypeRef`トークン。</span><span class="sxs-lookup"><span data-stu-id="5b71b-109">An `mdTypeRef` token.</span></span>|  
|`mdtTypeDef`|<span data-ttu-id="5b71b-110">`mdTypeDef`トークン。</span><span class="sxs-lookup"><span data-stu-id="5b71b-110">An `mdTypeDef` token.</span></span>|  
|`mdtFieldDef`|<span data-ttu-id="5b71b-111">`mdFieldDef`トークン。</span><span class="sxs-lookup"><span data-stu-id="5b71b-111">An `mdFieldDef` token.</span></span>|  
|`mdtMethodDef`|<span data-ttu-id="5b71b-112">`mdMethodDef`トークン。</span><span class="sxs-lookup"><span data-stu-id="5b71b-112">An `mdMethodDef` token.</span></span>|  
|`mdtParamDef`|<span data-ttu-id="5b71b-113">`mdParamDef`トークン。</span><span class="sxs-lookup"><span data-stu-id="5b71b-113">An `mdParamDef` token.</span></span>|  
|`mdtInterfaceImpl`|<span data-ttu-id="5b71b-114">`mdInterfaceImpl`トークン。</span><span class="sxs-lookup"><span data-stu-id="5b71b-114">An `mdInterfaceImpl` token.</span></span>|  
|`mdtMemberRef`|<span data-ttu-id="5b71b-115">`mdMemberRef`トークン。</span><span class="sxs-lookup"><span data-stu-id="5b71b-115">An `mdMemberRef` token.</span></span>|  
|`mdtCustomAttribute`|<span data-ttu-id="5b71b-116">`mdCustomAttribute`トークン。</span><span class="sxs-lookup"><span data-stu-id="5b71b-116">An `mdCustomAttribute` token.</span></span>|  
|`mdtPermission`|<span data-ttu-id="5b71b-117">`mdPermission`トークン。</span><span class="sxs-lookup"><span data-stu-id="5b71b-117">An `mdPermission` token.</span></span>|  
|`mdtSignature`|<span data-ttu-id="5b71b-118">`mdSignature`トークン。</span><span class="sxs-lookup"><span data-stu-id="5b71b-118">An `mdSignature` token.</span></span>|  
|`mdtEvent`|<span data-ttu-id="5b71b-119">`mdEvent`トークン。</span><span class="sxs-lookup"><span data-stu-id="5b71b-119">An `mdEvent` token.</span></span>|  
|`mdtProperty`|<span data-ttu-id="5b71b-120">`mdProperty`トークン。</span><span class="sxs-lookup"><span data-stu-id="5b71b-120">An `mdProperty` token.</span></span>|  
|`mdtModuleRef`|<span data-ttu-id="5b71b-121">`mdModuleRef`トークン。</span><span class="sxs-lookup"><span data-stu-id="5b71b-121">An `mdModuleRef` token.</span></span>|  
|`mdtTypeSpec`|<span data-ttu-id="5b71b-122">`mdTypeSpec`トークン。</span><span class="sxs-lookup"><span data-stu-id="5b71b-122">An `mdTypeSpec` token.</span></span>|  
|`mdtAssembly`|<span data-ttu-id="5b71b-123">`mdAssembly`トークン。</span><span class="sxs-lookup"><span data-stu-id="5b71b-123">An `mdAssembly` token.</span></span>|  
|`mdtAssemblyRef`|<span data-ttu-id="5b71b-124">`mdAssemblyRef`トークン。</span><span class="sxs-lookup"><span data-stu-id="5b71b-124">An `mdAssemblyRef` token.</span></span>|  
|`mdtFile`|<span data-ttu-id="5b71b-125">`mdFile`トークン。</span><span class="sxs-lookup"><span data-stu-id="5b71b-125">An `mdFile` token.</span></span>|  
|`mdtExportedType`|<span data-ttu-id="5b71b-126">`mdExportedType`トークン。</span><span class="sxs-lookup"><span data-stu-id="5b71b-126">An `mdExportedType` token.</span></span>|  
|`mdtManifestResource`|<span data-ttu-id="5b71b-127">`mdManifestResource`トークン。</span><span class="sxs-lookup"><span data-stu-id="5b71b-127">An `mdManifestResource` token.</span></span>|  
|`mdtGenericParam`|<span data-ttu-id="5b71b-128">`mdGenericParam`トークン。</span><span class="sxs-lookup"><span data-stu-id="5b71b-128">An `mdGenericParam` token.</span></span>|  
|`mdtMethodSpec`|<span data-ttu-id="5b71b-129">`mdMethodSpec`トークン。</span><span class="sxs-lookup"><span data-stu-id="5b71b-129">An `mdMethodSpec` token.</span></span>|  
|`mdtGenericParamConstraint`|<span data-ttu-id="5b71b-130">`mdGenericParamConstraint`トークン。</span><span class="sxs-lookup"><span data-stu-id="5b71b-130">An `mdGenericParamConstraint` token.</span></span>|  
|`mdtString`|<span data-ttu-id="5b71b-131">`mdString`トークン。</span><span class="sxs-lookup"><span data-stu-id="5b71b-131">An `mdString` token.</span></span>|  
|`mdtName`|<span data-ttu-id="5b71b-132">`mdName`トークン。</span><span class="sxs-lookup"><span data-stu-id="5b71b-132">An `mdName` token.</span></span>|  
|`mdtBaseType`|<span data-ttu-id="5b71b-133">使用されていません。</span><span class="sxs-lookup"><span data-stu-id="5b71b-133">Not used.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5b71b-134">コメント</span><span class="sxs-lookup"><span data-stu-id="5b71b-134">Remarks</span></span>  
 <span data-ttu-id="5b71b-135">各値は、対応するメタデータトークンの上位バイトの値に相当します。</span><span class="sxs-lookup"><span data-stu-id="5b71b-135">Each value is equal to the value of the top byte in the corresponding metadata token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5b71b-136">必要条件</span><span class="sxs-lookup"><span data-stu-id="5b71b-136">Requirements</span></span>  
 <span data-ttu-id="5b71b-137">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5b71b-137">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5b71b-138">**ヘッダー:** CorHdr. h</span><span class="sxs-lookup"><span data-stu-id="5b71b-138">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="5b71b-139">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5b71b-139">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b71b-140">関連項目</span><span class="sxs-lookup"><span data-stu-id="5b71b-140">See also</span></span>

- [<span data-ttu-id="5b71b-141">メタデータ列挙体</span><span class="sxs-lookup"><span data-stu-id="5b71b-141">Metadata Enumerations</span></span>](metadata-enumerations.md)
