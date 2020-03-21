---
title: CorCheckDuplicatesFor 列挙型
ms.date: 03/30/2017
api_name:
- CorCheckDuplicatesFor
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorCheckDuplicatesFor
helpviewer_keywords:
- CorCheckDuplicatesFor enumeration [.NET Framework metadata]
ms.assetid: d8ec8d3c-70f7-4cc6-9957-68068fd8f49c
topic_type:
- apiref
ms.openlocfilehash: 04dc12ab4d7d178ebf1575a3260f9f4981972782
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176189"
---
# <a name="corcheckduplicatesfor-enumeration"></a><span data-ttu-id="13e16-102">CorCheckDuplicatesFor 列挙型</span><span class="sxs-lookup"><span data-stu-id="13e16-102">CorCheckDuplicatesFor Enumeration</span></span>
<span data-ttu-id="13e16-103">重複をチェックするメタデータ トークンを指定します。</span><span class="sxs-lookup"><span data-stu-id="13e16-103">Specifies the metadata tokens that will be checked for duplicates.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="13e16-104">構文</span><span class="sxs-lookup"><span data-stu-id="13e16-104">Syntax</span></span>  
  
```cpp  
typedef enum CorCheckDuplicatesFor {  
  
    MDDupAll                    = 0xffffffff,  
    MDDupENC                    = MDDupAll,  
    MDNoDupChecks               = 0x00000000,  
    MDDupTypeDef                = 0x00000001,  
    MDDupInterfaceImpl          = 0x00000002,  
    MDDupMethodDef              = 0x00000004,  
    MDDupTypeRef                = 0x00000008,  
    MDDupMemberRef              = 0x00000010,  
    MDDupCustomAttribute        = 0x00000020,  
    MDDupParamDef               = 0x00000040,  
    MDDupPermission             = 0x00000080,  
    MDDupProperty               = 0x00000100,  
    MDDupEvent                  = 0x00000200,  
    MDDupFieldDef               = 0x00000400,  
    MDDupSignature              = 0x00000800,  
    MDDupModuleRef              = 0x00001000,  
    MDDupTypeSpec               = 0x00002000,  
    MDDupImplMap                = 0x00004000,  
    MDDupAssemblyRef            = 0x00008000,  
    MDDupFile                   = 0x00010000,  
    MDDupExportedType           = 0x00020000,  
    MDDupManifestResource       = 0x00040000,  
    MDDupGenericParam           = 0x00080000,  
    MDDupMethodSpec             = 0x00100000,  
    MDDupGenericParamConstraint = 0x00200000,  
  
    MDDupAssembly               = 0x10000000,  
  
    MDDupDefault =
        MDNoDupChecks | MDDupTypeRef | MDDupMemberRef |
        MDDupSignature | MDDupTypeSpec | MDDupMethodSpec  
  
} CorCheckDuplicatesFor;  
```  
  
## <a name="members"></a><span data-ttu-id="13e16-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="13e16-105">Members</span></span>  
  
|<span data-ttu-id="13e16-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="13e16-106">Member</span></span>|<span data-ttu-id="13e16-107">説明</span><span class="sxs-lookup"><span data-stu-id="13e16-107">Description</span></span>|  
|------------|-----------------|  
|`MDDupAll`|<span data-ttu-id="13e16-108">すべてのメタデータ トークンに重複がないか確認します。</span><span class="sxs-lookup"><span data-stu-id="13e16-108">Check all metadata tokens for duplicates.</span></span>|  
|`MDDupENC`|<span data-ttu-id="13e16-109">使用されていません。</span><span class="sxs-lookup"><span data-stu-id="13e16-109">Not used.</span></span>|  
|`MDNoDupChecks`|<span data-ttu-id="13e16-110">メタデータ トークンの重複をチェックしないでください。</span><span class="sxs-lookup"><span data-stu-id="13e16-110">Do not check metadata tokens for duplicates.</span></span>|  
|`MDDupTypeDef`|<span data-ttu-id="13e16-111">`mdTypeDef`トークンの重複を確認します。</span><span class="sxs-lookup"><span data-stu-id="13e16-111">Check for duplicates of `mdTypeDef` tokens.</span></span>|  
|`MDDupInterfaceImpl`|<span data-ttu-id="13e16-112">`mdInterfaceImpl`トークンの重複を確認します。</span><span class="sxs-lookup"><span data-stu-id="13e16-112">Check for duplicates of `mdInterfaceImpl` tokens.</span></span>|  
|`MDDupMethodDef`|<span data-ttu-id="13e16-113">`mdMethodDef`トークンの重複を確認します。</span><span class="sxs-lookup"><span data-stu-id="13e16-113">Check for duplicates of `mdMethodDef` tokens.</span></span>|  
|`MDDupTypeRef`|<span data-ttu-id="13e16-114">`mdTypeRef`トークンの重複を確認します。</span><span class="sxs-lookup"><span data-stu-id="13e16-114">Check for duplicates of `mdTypeRef` tokens.</span></span>|  
|`MDDupMemberRef`|<span data-ttu-id="13e16-115">`mdMemberRef`トークンの重複を確認します。</span><span class="sxs-lookup"><span data-stu-id="13e16-115">Check for duplicates of `mdMemberRef` tokens.</span></span>|  
|`MDDupCustomAttribute`|<span data-ttu-id="13e16-116">`mdCustomAttribute`トークンの重複を確認します。</span><span class="sxs-lookup"><span data-stu-id="13e16-116">Check for duplicates of `mdCustomAttribute` tokens.</span></span>|  
|`MDDupParamDef`|<span data-ttu-id="13e16-117">`mdParamDef`トークンの重複を確認します。</span><span class="sxs-lookup"><span data-stu-id="13e16-117">Check for duplicates of `mdParamDef` tokens.</span></span>|  
|`MDDupPermission`|<span data-ttu-id="13e16-118">`mdPermission`トークンの重複を確認します。</span><span class="sxs-lookup"><span data-stu-id="13e16-118">Check for duplicates of `mdPermission` tokens.</span></span>|  
|`MDDupProperty`|<span data-ttu-id="13e16-119">`mdProperty`トークンの重複を確認します。</span><span class="sxs-lookup"><span data-stu-id="13e16-119">Check for duplicates of `mdProperty` tokens.</span></span>|  
|`MDDupEvent`|<span data-ttu-id="13e16-120">`mdEvent`トークンの重複を確認します。</span><span class="sxs-lookup"><span data-stu-id="13e16-120">Check for duplicates of `mdEvent` tokens.</span></span>|  
|`MDDupFieldDef`|<span data-ttu-id="13e16-121">`mdFieldDef`トークンの重複を確認します。</span><span class="sxs-lookup"><span data-stu-id="13e16-121">Check for duplicates of `mdFieldDef` tokens.</span></span>|  
|`MDDupSignature`|<span data-ttu-id="13e16-122">`mdSignature`トークンの重複を確認します。</span><span class="sxs-lookup"><span data-stu-id="13e16-122">Check for duplicates of `mdSignature` tokens.</span></span>|  
|`MDDupModuleRef`|<span data-ttu-id="13e16-123">`mdModuleRef`トークンの重複を確認します。</span><span class="sxs-lookup"><span data-stu-id="13e16-123">Check for duplicates of `mdModuleRef` tokens.</span></span>|  
|`MDDupTypeSpec`|<span data-ttu-id="13e16-124">`mdTypeSpec`トークンの重複を確認します。</span><span class="sxs-lookup"><span data-stu-id="13e16-124">Check for duplicates of `mdTypeSpec` tokens.</span></span>|  
|`MDDupImplMap`|<span data-ttu-id="13e16-125">`mdImplMap`トークンの重複を確認します。</span><span class="sxs-lookup"><span data-stu-id="13e16-125">Check for duplicates of `mdImplMap` tokens.</span></span>|  
|`MDDupAssemblyRef`|<span data-ttu-id="13e16-126">`mdAssemblyRef`トークンの重複を確認します。</span><span class="sxs-lookup"><span data-stu-id="13e16-126">Check for duplicates of `mdAssemblyRef` tokens.</span></span>|  
|`MDDupFile`|<span data-ttu-id="13e16-127">`mdFile`トークンの重複を確認します。</span><span class="sxs-lookup"><span data-stu-id="13e16-127">Check for duplicates of `mdFile` tokens.</span></span>|  
|`MDDupExportedType`|<span data-ttu-id="13e16-128">`mdExportedType`トークンの重複を確認します。</span><span class="sxs-lookup"><span data-stu-id="13e16-128">Check for duplicates of `mdExportedType` tokens.</span></span>|  
|`MDDupManifestResource`|<span data-ttu-id="13e16-129">`mdManifestResource`トークンの重複を確認します。</span><span class="sxs-lookup"><span data-stu-id="13e16-129">Check for duplicates of `mdManifestResource` tokens.</span></span>|  
|`MDDupGenericParam`|<span data-ttu-id="13e16-130">`mdGenericParam`トークンの重複を確認します。</span><span class="sxs-lookup"><span data-stu-id="13e16-130">Check for duplicates of `mdGenericParam` tokens.</span></span>|  
|`MDDupMethodSpec`|<span data-ttu-id="13e16-131">`mdMethodSpec`トークンの重複を確認します。</span><span class="sxs-lookup"><span data-stu-id="13e16-131">Check for duplicates of `mdMethodSpec` tokens.</span></span>|  
|`MDDupGenericParamConstraint`|<span data-ttu-id="13e16-132">`mdGenericParamConstraint`トークンの重複を確認します。</span><span class="sxs-lookup"><span data-stu-id="13e16-132">Check for duplicates of `mdGenericParamConstraint` tokens.</span></span>|  
|`MDDupAssembly`|<span data-ttu-id="13e16-133">`mdAssembly`トークンの重複を確認します。</span><span class="sxs-lookup"><span data-stu-id="13e16-133">Check for duplicates of `mdAssembly` tokens.</span></span>|  
|`MDDupDefault`|<span data-ttu-id="13e16-134">、 `mdMemberRef`、 `mdTypeRef`、、`mdSignature``mdTypeSpec`および`mdMethodSpec`トークンの重複をチェックします。</span><span class="sxs-lookup"><span data-stu-id="13e16-134">Check for duplicates of `mdMemberRef`, `mdTypeRef`, `mdSignature`, `mdTypeSpec`, and `mdMethodSpec` tokens.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="13e16-135">必要条件</span><span class="sxs-lookup"><span data-stu-id="13e16-135">Requirements</span></span>  
 <span data-ttu-id="13e16-136">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="13e16-136">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="13e16-137">**ヘッダー:** コルドル.h</span><span class="sxs-lookup"><span data-stu-id="13e16-137">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="13e16-138">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="13e16-138">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13e16-139">関連項目</span><span class="sxs-lookup"><span data-stu-id="13e16-139">See also</span></span>

- [<span data-ttu-id="13e16-140">メタデータ列挙体</span><span class="sxs-lookup"><span data-stu-id="13e16-140">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
