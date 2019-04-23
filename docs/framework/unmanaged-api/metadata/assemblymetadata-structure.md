---
title: ASSEMBLYMETADATA 構造体
ms.date: 03/30/2017
api_name:
- ASSEMBLYMETADATA
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ASSEMBLYMETADATA
helpviewer_keywords:
- ASSEMBLYMETADATA structure [.NET Framework metadata]
ms.assetid: 1af98e57-9145-4d35-bb78-77d1da7c91a5
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8f0a9b9c149c86b4d9121275aa858dfdc0cdbac7
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59195164"
---
# <a name="assemblymetadata-structure"></a><span data-ttu-id="140dc-102">ASSEMBLYMETADATA 構造体</span><span class="sxs-lookup"><span data-stu-id="140dc-102">ASSEMBLYMETADATA Structure</span></span>
<span data-ttu-id="140dc-103">そのバージョンとそのロケール、プロセッサ、およびオペレーティング システムのサポートのレベルを含む、参照先アセンブリに関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="140dc-103">Contains information about the referenced assembly, including its version and its level of support for locales, processors, and operating systems.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="140dc-104">構文</span><span class="sxs-lookup"><span data-stu-id="140dc-104">Syntax</span></span>  
  
```  
typedef struct {  
    USHORT  usMajorVersion;  
    USHORT  usMinorVersion;  
    USHORT  usBuildNumber;  
    USHORT  usRevisionNumber;  
    LPWSTR  szLocale;  
    ULONG   cbLocale;  
    DWORD*  rdwProcessor[];  
    ULONG   ulProcessor  
    OSINFO* rOS[];  
    ULONG   ulOS;  
} ASSEMBLYMETADATA;  
```  
  
## <a name="members"></a><span data-ttu-id="140dc-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="140dc-105">Members</span></span>  
  
|<span data-ttu-id="140dc-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="140dc-106">Member</span></span>|<span data-ttu-id="140dc-107">説明</span><span class="sxs-lookup"><span data-stu-id="140dc-107">Description</span></span>|  
|------------|-----------------|  
|`usMajorVersion`|<span data-ttu-id="140dc-108">参照アセンブリのメジャー バージョン番号。</span><span class="sxs-lookup"><span data-stu-id="140dc-108">The major version number of the referenced assembly.</span></span> <span data-ttu-id="140dc-109">この値は、0 にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="140dc-109">This value cannot be zero.</span></span> <span data-ttu-id="140dc-110">場合のすべてのビット`usMajorVersion`メジャー バージョンが指定されていない、設定されます。</span><span class="sxs-lookup"><span data-stu-id="140dc-110">If all the bits of `usMajorVersion` are set, the major version is not specified.</span></span>|  
|`usMinorVersion`|<span data-ttu-id="140dc-111">参照アセンブリのマイナー バージョン番号。</span><span class="sxs-lookup"><span data-stu-id="140dc-111">The minor version number of the referenced assembly.</span></span> <span data-ttu-id="140dc-112">この値は、0 にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="140dc-112">This value cannot be zero.</span></span> <span data-ttu-id="140dc-113">場合のすべてのビット`usMinorVersion`マイナー バージョンが指定されていない、設定されます。</span><span class="sxs-lookup"><span data-stu-id="140dc-113">If all the bits of `usMinorVersion` are set, the minor version is not specified.</span></span>|  
|`usBuildNumber`|<span data-ttu-id="140dc-114">参照アセンブリのビルド番号。</span><span class="sxs-lookup"><span data-stu-id="140dc-114">The build number of the referenced assembly.</span></span> <span data-ttu-id="140dc-115">この値は、0 にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="140dc-115">This value cannot be zero.</span></span> <span data-ttu-id="140dc-116">場合のすべてのビット`usBuildNumber`は設定されて、ビルド番号が指定されていません。</span><span class="sxs-lookup"><span data-stu-id="140dc-116">If all the bits of `usBuildNumber` are set, the build number is not specified.</span></span>|  
|`usRevisionNumber`|<span data-ttu-id="140dc-117">参照アセンブリのリビジョン番号。</span><span class="sxs-lookup"><span data-stu-id="140dc-117">The revision number of the referenced assembly.</span></span> <span data-ttu-id="140dc-118">この値は、0 にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="140dc-118">This value cannot be zero.</span></span> <span data-ttu-id="140dc-119">場合のすべてのビット`usRevisionNumber`は設定されて、リビジョン番号が指定されていません。</span><span class="sxs-lookup"><span data-stu-id="140dc-119">If all the bits of `usRevisionNumber` are set, the revision number is not specified.</span></span>|  
|`szLocale`|<span data-ttu-id="140dc-120">参照先アセンブリによってサポートされるロケールを指定する、セミコロンで区切られた、RFC1766 仕様に準拠しているロケール名の一覧。</span><span class="sxs-lookup"><span data-stu-id="140dc-120">A list of locale names conforming to the RFC1766 specification, separated by semicolons, specifying the locales supported by the referenced assembly.</span></span> <span data-ttu-id="140dc-121">Null 値には、ロケールに依存しないことを示します。</span><span class="sxs-lookup"><span data-stu-id="140dc-121">A null value indicates locale independence.</span></span> <span data-ttu-id="140dc-122">**注:**.NET framework バージョン 1.0 は、複数のロケールを指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="140dc-122">**Note:**  In the .NET Framework version 1.0 you cannot specify more than one locale.</span></span>|  
|`cbLocale`|<span data-ttu-id="140dc-123">ワイド文字単位サイズ`szLocale`します。</span><span class="sxs-lookup"><span data-stu-id="140dc-123">The size in wide characters of `szLocale`.</span></span>|  
|`rdwProcessor`|<span data-ttu-id="140dc-124">参照アセンブリでサポートされているプロセッサの種類について、Winnt.h で定義されている、識別子の配列。</span><span class="sxs-lookup"><span data-stu-id="140dc-124">An array of identifiers, as defined in Winnt.h, for the processor types that are supported by the referenced assembly.</span></span> <span data-ttu-id="140dc-125">NULL 値では、プロセッサの独立性を示します。</span><span class="sxs-lookup"><span data-stu-id="140dc-125">A NULL value indicates processor independence.</span></span>|  
|`ulProcessor`|<span data-ttu-id="140dc-126">長さ、`rdwProcessor`配列。</span><span class="sxs-lookup"><span data-stu-id="140dc-126">The length of the `rdwProcessor` array.</span></span>|  
|`rOS`|<span data-ttu-id="140dc-127">配列の[OSINFO](../../../../docs/framework/unmanaged-api/metadata/osinfo-structure.md)参照アセンブリでサポートされているオペレーティング システムを指定するインスタンス。</span><span class="sxs-lookup"><span data-stu-id="140dc-127">An array of [OSINFO](../../../../docs/framework/unmanaged-api/metadata/osinfo-structure.md) instances specifying the operating systems that are supported by the referenced assembly.</span></span> <span data-ttu-id="140dc-128">NULL 値には、オペレーティング システムに依存しないことを示します。</span><span class="sxs-lookup"><span data-stu-id="140dc-128">A NULL value indicates operating-system independence.</span></span>|  
|`ulOS`|<span data-ttu-id="140dc-129">長さ、`rOS`配列。</span><span class="sxs-lookup"><span data-stu-id="140dc-129">The length of the `rOS` array.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="140dc-130">必要条件</span><span class="sxs-lookup"><span data-stu-id="140dc-130">Requirements</span></span>  
 <span data-ttu-id="140dc-131">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="140dc-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="140dc-132">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="140dc-132">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="140dc-133">**ライブラリ:** MsCorEE.dll にリソースとして使用</span><span class="sxs-lookup"><span data-stu-id="140dc-133">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="140dc-134">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="140dc-134">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="140dc-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="140dc-135">See also</span></span>

- [<span data-ttu-id="140dc-136">メタデータ構造体</span><span class="sxs-lookup"><span data-stu-id="140dc-136">Metadata Structures</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-structures.md)
- [<span data-ttu-id="140dc-137">IMetaDataAssemblyEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="140dc-137">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
- [<span data-ttu-id="140dc-138">OSINFO 構造体</span><span class="sxs-lookup"><span data-stu-id="140dc-138">OSINFO Structure</span></span>](../../../../docs/framework/unmanaged-api/metadata/osinfo-structure.md)
