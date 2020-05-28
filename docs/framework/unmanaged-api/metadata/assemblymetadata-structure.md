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
ms.openlocfilehash: 5c7211fc2523b70313a1e4d4d9d2da0dcecd1d32
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/27/2020
ms.locfileid: "84009432"
---
# <a name="assemblymetadata-structure"></a><span data-ttu-id="f4fb6-102">ASSEMBLYMETADATA 構造体</span><span class="sxs-lookup"><span data-stu-id="f4fb6-102">ASSEMBLYMETADATA Structure</span></span>
<span data-ttu-id="f4fb6-103">バージョン、ロケール、プロセッサ、オペレーティングシステムのサポートレベルなど、参照されるアセンブリに関する情報を格納します。</span><span class="sxs-lookup"><span data-stu-id="f4fb6-103">Contains information about the referenced assembly, including its version and its level of support for locales, processors, and operating systems.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f4fb6-104">構文</span><span class="sxs-lookup"><span data-stu-id="f4fb6-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="members"></a><span data-ttu-id="f4fb6-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="f4fb6-105">Members</span></span>  
  
|<span data-ttu-id="f4fb6-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="f4fb6-106">Member</span></span>|<span data-ttu-id="f4fb6-107">説明</span><span class="sxs-lookup"><span data-stu-id="f4fb6-107">Description</span></span>|  
|------------|-----------------|  
|`usMajorVersion`|<span data-ttu-id="f4fb6-108">参照アセンブリのメジャーバージョン番号。</span><span class="sxs-lookup"><span data-stu-id="f4fb6-108">The major version number of the referenced assembly.</span></span> <span data-ttu-id="f4fb6-109">この値を0にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="f4fb6-109">This value cannot be zero.</span></span> <span data-ttu-id="f4fb6-110">のすべてのビットが設定されている場合は、 `usMajorVersion` メジャーバージョンが指定されていません。</span><span class="sxs-lookup"><span data-stu-id="f4fb6-110">If all the bits of `usMajorVersion` are set, the major version is not specified.</span></span>|  
|`usMinorVersion`|<span data-ttu-id="f4fb6-111">参照アセンブリのマイナーバージョン番号。</span><span class="sxs-lookup"><span data-stu-id="f4fb6-111">The minor version number of the referenced assembly.</span></span> <span data-ttu-id="f4fb6-112">この値を0にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="f4fb6-112">This value cannot be zero.</span></span> <span data-ttu-id="f4fb6-113">のすべてのビットが設定されている場合は、 `usMinorVersion` マイナーバージョンが指定されていません。</span><span class="sxs-lookup"><span data-stu-id="f4fb6-113">If all the bits of `usMinorVersion` are set, the minor version is not specified.</span></span>|  
|`usBuildNumber`|<span data-ttu-id="f4fb6-114">参照アセンブリのビルド番号。</span><span class="sxs-lookup"><span data-stu-id="f4fb6-114">The build number of the referenced assembly.</span></span> <span data-ttu-id="f4fb6-115">この値を0にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="f4fb6-115">This value cannot be zero.</span></span> <span data-ttu-id="f4fb6-116">のすべてのビットが設定されている場合は、 `usBuildNumber` ビルド番号が指定されていません。</span><span class="sxs-lookup"><span data-stu-id="f4fb6-116">If all the bits of `usBuildNumber` are set, the build number is not specified.</span></span>|  
|`usRevisionNumber`|<span data-ttu-id="f4fb6-117">参照アセンブリのリビジョン番号。</span><span class="sxs-lookup"><span data-stu-id="f4fb6-117">The revision number of the referenced assembly.</span></span> <span data-ttu-id="f4fb6-118">この値を0にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="f4fb6-118">This value cannot be zero.</span></span> <span data-ttu-id="f4fb6-119">のすべてのビットが設定されている場合は、 `usRevisionNumber` リビジョン番号が指定されていません。</span><span class="sxs-lookup"><span data-stu-id="f4fb6-119">If all the bits of `usRevisionNumber` are set, the revision number is not specified.</span></span>|  
|`szLocale`|<span data-ttu-id="f4fb6-120">RFC1766 仕様に準拠しているロケール名のリスト。セミコロンで区切られ、参照アセンブリによってサポートされるロケールを指定します。</span><span class="sxs-lookup"><span data-stu-id="f4fb6-120">A list of locale names conforming to the RFC1766 specification, separated by semicolons, specifying the locales supported by the referenced assembly.</span></span> <span data-ttu-id="f4fb6-121">Null 値は、ロケールに依存しないことを示します。</span><span class="sxs-lookup"><span data-stu-id="f4fb6-121">A null value indicates locale independence.</span></span> <span data-ttu-id="f4fb6-122">**注:** .NET Framework バージョン1.0 では、複数のロケールを指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="f4fb6-122">**Note:**  In the .NET Framework version 1.0 you cannot specify more than one locale.</span></span>|  
|`cbLocale`|<span data-ttu-id="f4fb6-123">のワイド文字のサイズ `szLocale` 。</span><span class="sxs-lookup"><span data-stu-id="f4fb6-123">The size in wide characters of `szLocale`.</span></span>|  
|`rdwProcessor`|<span data-ttu-id="f4fb6-124">参照アセンブリでサポートされているプロセッサの種類について、Winnt.h で定義されている識別子の配列。</span><span class="sxs-lookup"><span data-stu-id="f4fb6-124">An array of identifiers, as defined in Winnt.h, for the processor types that are supported by the referenced assembly.</span></span> <span data-ttu-id="f4fb6-125">NULL 値は、プロセッサに依存しないことを示します。</span><span class="sxs-lookup"><span data-stu-id="f4fb6-125">A NULL value indicates processor independence.</span></span>|  
|`ulProcessor`|<span data-ttu-id="f4fb6-126">`rdwProcessor` 配列の長さ。</span><span class="sxs-lookup"><span data-stu-id="f4fb6-126">The length of the `rdwProcessor` array.</span></span>|  
|`rOS`|<span data-ttu-id="f4fb6-127">参照アセンブリによってサポートされているオペレーティングシステムを指定する[Osinfo](osinfo-structure.md)インスタンスの配列。</span><span class="sxs-lookup"><span data-stu-id="f4fb6-127">An array of [OSINFO](osinfo-structure.md) instances specifying the operating systems that are supported by the referenced assembly.</span></span> <span data-ttu-id="f4fb6-128">NULL 値は、オペレーティングシステムに依存しないことを示します。</span><span class="sxs-lookup"><span data-stu-id="f4fb6-128">A NULL value indicates operating-system independence.</span></span>|  
|`ulOS`|<span data-ttu-id="f4fb6-129">`rOS` 配列の長さ。</span><span class="sxs-lookup"><span data-stu-id="f4fb6-129">The length of the `rOS` array.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f4fb6-130">必要条件</span><span class="sxs-lookup"><span data-stu-id="f4fb6-130">Requirements</span></span>  
 <span data-ttu-id="f4fb6-131">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f4fb6-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f4fb6-132">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="f4fb6-132">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f4fb6-133">**ライブラリ:** Mscoree.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="f4fb6-133">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f4fb6-134">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f4fb6-134">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4fb6-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="f4fb6-135">See also</span></span>

- [<span data-ttu-id="f4fb6-136">メタデータ構造体</span><span class="sxs-lookup"><span data-stu-id="f4fb6-136">Metadata Structures</span></span>](metadata-structures.md)
- [<span data-ttu-id="f4fb6-137">IMetaDataAssemblyEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f4fb6-137">IMetaDataAssemblyEmit Interface</span></span>](imetadataassemblyemit-interface.md)
- [<span data-ttu-id="f4fb6-138">OSINFO 構造体</span><span class="sxs-lookup"><span data-stu-id="f4fb6-138">OSINFO Structure</span></span>](osinfo-structure.md)
