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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a82ce9709e008e092c5f31372a89bf9a16e1f88b
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67767017"
---
# <a name="corcheckduplicatesfor-enumeration"></a><span data-ttu-id="00b58-102">CorCheckDuplicatesFor 列挙型</span><span class="sxs-lookup"><span data-stu-id="00b58-102">CorCheckDuplicatesFor Enumeration</span></span>
<span data-ttu-id="00b58-103">重複のチェックとメタデータ トークンを指定します。</span><span class="sxs-lookup"><span data-stu-id="00b58-103">Specifies the metadata tokens that will be checked for duplicates.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="00b58-104">構文</span><span class="sxs-lookup"><span data-stu-id="00b58-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="00b58-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="00b58-105">Members</span></span>  
  
|<span data-ttu-id="00b58-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="00b58-106">Member</span></span>|<span data-ttu-id="00b58-107">説明</span><span class="sxs-lookup"><span data-stu-id="00b58-107">Description</span></span>|  
|------------|-----------------|  
|`MDDupAll`|<span data-ttu-id="00b58-108">すべてのメタデータ トークンの重複を確認します。</span><span class="sxs-lookup"><span data-stu-id="00b58-108">Check all metadata tokens for duplicates.</span></span>|  
|`MDDupENC`|<span data-ttu-id="00b58-109">使用しません。</span><span class="sxs-lookup"><span data-stu-id="00b58-109">Not used.</span></span>|  
|`MDNoDupChecks`|<span data-ttu-id="00b58-110">メタデータ トークンの重複をチェックしません。</span><span class="sxs-lookup"><span data-stu-id="00b58-110">Do not check metadata tokens for duplicates.</span></span>|  
|`MDDupTypeDef`|<span data-ttu-id="00b58-111">重複をチェック`mdTypeDef`トークンです。</span><span class="sxs-lookup"><span data-stu-id="00b58-111">Check for duplicates of `mdTypeDef` tokens.</span></span>|  
|`MDDupInterfaceImpl`|<span data-ttu-id="00b58-112">重複をチェック`mdInterfaceImpl`トークンです。</span><span class="sxs-lookup"><span data-stu-id="00b58-112">Check for duplicates of `mdInterfaceImpl` tokens.</span></span>|  
|`MDDupMethodDef`|<span data-ttu-id="00b58-113">重複をチェック`mdMethodDef`トークンです。</span><span class="sxs-lookup"><span data-stu-id="00b58-113">Check for duplicates of `mdMethodDef` tokens.</span></span>|  
|`MDDupTypeRef`|<span data-ttu-id="00b58-114">重複をチェック`mdTypeRef`トークンです。</span><span class="sxs-lookup"><span data-stu-id="00b58-114">Check for duplicates of `mdTypeRef` tokens.</span></span>|  
|`MDDupMemberRef`|<span data-ttu-id="00b58-115">重複をチェック`mdMemberRef`トークンです。</span><span class="sxs-lookup"><span data-stu-id="00b58-115">Check for duplicates of `mdMemberRef` tokens.</span></span>|  
|`MDDupCustomAttribute`|<span data-ttu-id="00b58-116">重複をチェック`mdCustomAttribute`トークンです。</span><span class="sxs-lookup"><span data-stu-id="00b58-116">Check for duplicates of `mdCustomAttribute` tokens.</span></span>|  
|`MDDupParamDef`|<span data-ttu-id="00b58-117">重複をチェック`mdParamDef`トークンです。</span><span class="sxs-lookup"><span data-stu-id="00b58-117">Check for duplicates of `mdParamDef` tokens.</span></span>|  
|`MDDupPermission`|<span data-ttu-id="00b58-118">重複をチェック`mdPermission`トークンです。</span><span class="sxs-lookup"><span data-stu-id="00b58-118">Check for duplicates of `mdPermission` tokens.</span></span>|  
|`MDDupProperty`|<span data-ttu-id="00b58-119">重複をチェック`mdProperty`トークンです。</span><span class="sxs-lookup"><span data-stu-id="00b58-119">Check for duplicates of `mdProperty` tokens.</span></span>|  
|`MDDupEvent`|<span data-ttu-id="00b58-120">重複をチェック`mdEvent`トークンです。</span><span class="sxs-lookup"><span data-stu-id="00b58-120">Check for duplicates of `mdEvent` tokens.</span></span>|  
|`MDDupFieldDef`|<span data-ttu-id="00b58-121">重複をチェック`mdFieldDef`トークンです。</span><span class="sxs-lookup"><span data-stu-id="00b58-121">Check for duplicates of `mdFieldDef` tokens.</span></span>|  
|`MDDupSignature`|<span data-ttu-id="00b58-122">重複をチェック`mdSignature`トークンです。</span><span class="sxs-lookup"><span data-stu-id="00b58-122">Check for duplicates of `mdSignature` tokens.</span></span>|  
|`MDDupModuleRef`|<span data-ttu-id="00b58-123">重複をチェック`mdModuleRef`トークンです。</span><span class="sxs-lookup"><span data-stu-id="00b58-123">Check for duplicates of `mdModuleRef` tokens.</span></span>|  
|`MDDupTypeSpec`|<span data-ttu-id="00b58-124">重複をチェック`mdTypeSpec`トークンです。</span><span class="sxs-lookup"><span data-stu-id="00b58-124">Check for duplicates of `mdTypeSpec` tokens.</span></span>|  
|`MDDupImplMap`|<span data-ttu-id="00b58-125">重複をチェック`mdImplMap`トークンです。</span><span class="sxs-lookup"><span data-stu-id="00b58-125">Check for duplicates of `mdImplMap` tokens.</span></span>|  
|`MDDupAssemblyRef`|<span data-ttu-id="00b58-126">重複をチェック`mdAssemblyRef`トークンです。</span><span class="sxs-lookup"><span data-stu-id="00b58-126">Check for duplicates of `mdAssemblyRef` tokens.</span></span>|  
|`MDDupFile`|<span data-ttu-id="00b58-127">重複をチェック`mdFile`トークンです。</span><span class="sxs-lookup"><span data-stu-id="00b58-127">Check for duplicates of `mdFile` tokens.</span></span>|  
|`MDDupExportedType`|<span data-ttu-id="00b58-128">重複をチェック`mdExportedType`トークンです。</span><span class="sxs-lookup"><span data-stu-id="00b58-128">Check for duplicates of `mdExportedType` tokens.</span></span>|  
|`MDDupManifestResource`|<span data-ttu-id="00b58-129">重複をチェック`mdManifestResource`トークンです。</span><span class="sxs-lookup"><span data-stu-id="00b58-129">Check for duplicates of `mdManifestResource` tokens.</span></span>|  
|`MDDupGenericParam`|<span data-ttu-id="00b58-130">重複をチェック`mdGenericParam`トークンです。</span><span class="sxs-lookup"><span data-stu-id="00b58-130">Check for duplicates of `mdGenericParam` tokens.</span></span>|  
|`MDDupMethodSpec`|<span data-ttu-id="00b58-131">重複をチェック`mdMethodSpec`トークンです。</span><span class="sxs-lookup"><span data-stu-id="00b58-131">Check for duplicates of `mdMethodSpec` tokens.</span></span>|  
|`MDDupGenericParamConstraint`|<span data-ttu-id="00b58-132">重複をチェック`mdGenericParamConstraint`トークンです。</span><span class="sxs-lookup"><span data-stu-id="00b58-132">Check for duplicates of `mdGenericParamConstraint` tokens.</span></span>|  
|`MDDupAssembly`|<span data-ttu-id="00b58-133">重複をチェック`mdAssembly`トークンです。</span><span class="sxs-lookup"><span data-stu-id="00b58-133">Check for duplicates of `mdAssembly` tokens.</span></span>|  
|`MDDupDefault`|<span data-ttu-id="00b58-134">重複をチェック`mdMemberRef`、 `mdTypeRef`、 `mdSignature`、 `mdTypeSpec`、および`mdMethodSpec`トークンです。</span><span class="sxs-lookup"><span data-stu-id="00b58-134">Check for duplicates of `mdMemberRef`, `mdTypeRef`, `mdSignature`, `mdTypeSpec`, and `mdMethodSpec` tokens.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="00b58-135">必要条件</span><span class="sxs-lookup"><span data-stu-id="00b58-135">Requirements</span></span>  
 <span data-ttu-id="00b58-136">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="00b58-136">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="00b58-137">**ヘッダー:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="00b58-137">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="00b58-138">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="00b58-138">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00b58-139">関連項目</span><span class="sxs-lookup"><span data-stu-id="00b58-139">See also</span></span>

- [<span data-ttu-id="00b58-140">メタデータ列挙型</span><span class="sxs-lookup"><span data-stu-id="00b58-140">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
