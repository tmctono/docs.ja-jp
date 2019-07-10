---
title: AssemblyFlags 列挙体
ms.date: 03/30/2017
api_name:
- AssemblyFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- AssemblyFlags
helpviewer_keywords:
- AssemblyFlags enumeration [.NET Framework metadata]
ms.assetid: 40f9bd9e-16ec-447e-81b0-168c875e9866
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 502e7841f8c413aa48732bcea0b6c2178d70c061
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67776450"
---
# <a name="assemblyflags-enumeration"></a><span data-ttu-id="b0a78-102">AssemblyFlags 列挙体</span><span class="sxs-lookup"><span data-stu-id="b0a78-102">AssemblyFlags Enumeration</span></span>
<span data-ttu-id="b0a78-103">アセンブリの実行時の機能を記述する値が含まれています。</span><span class="sxs-lookup"><span data-stu-id="b0a78-103">Contains values that describe run-time features of an assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b0a78-104">構文</span><span class="sxs-lookup"><span data-stu-id="b0a78-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    afImplicitExportedTypes = 0x0001,  
    afImplicitResources = 0x0002,  
    afNonSideBySideAppDomain = 0x0010,  
    afNonSideBySideProcess = 0x0020,  
    afNonSideBySideMachine = 0x0030  
} AssemblyFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="b0a78-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="b0a78-105">Members</span></span>  
  
|<span data-ttu-id="b0a78-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="b0a78-106">Member</span></span>|<span data-ttu-id="b0a78-107">説明</span><span class="sxs-lookup"><span data-stu-id="b0a78-107">Description</span></span>|  
|------------|-----------------|  
|`afImplicitExportedTypes`|<span data-ttu-id="b0a78-108">エクスポートされた種類の定義がアセンブリを構成するファイル内で暗黙的なを指定します。</span><span class="sxs-lookup"><span data-stu-id="b0a78-108">Specifies that exported type definitions are implicit within the files that comprise the assembly.</span></span> <span data-ttu-id="b0a78-109">.NET Framework バージョン 1.0 および 1.1 では、この値は常に設定されると想定します。</span><span class="sxs-lookup"><span data-stu-id="b0a78-109">In the .NET Framework versions 1.0 and 1.1, this value is always assumed to be set.</span></span>|  
|`afImplicitResources`|<span data-ttu-id="b0a78-110">リソース定義がアセンブリを構成するファイル内で暗黙的なを指定します。</span><span class="sxs-lookup"><span data-stu-id="b0a78-110">Specifies that resource definitions are implicit within the files that comprise the assembly.</span></span> <span data-ttu-id="b0a78-111">.NET Framework 1.0 および 1.1 では、この値は常に設定されると想定します。</span><span class="sxs-lookup"><span data-stu-id="b0a78-111">In the .NET Framework 1.0 and 1.1, this value is always assumed to be set.</span></span>|  
|`afNonSideBySideAppDomain`|<span data-ttu-id="b0a78-112">アセンブリは他のバージョンが同じアプリケーション ドメインで実行されている場合に実行できないことを指定します。</span><span class="sxs-lookup"><span data-stu-id="b0a78-112">Specifies that the assembly cannot execute with other versions if they are running in the same application domain.</span></span>|  
|`afNonSideBySideProcess`|<span data-ttu-id="b0a78-113">アセンブリは他のバージョンが同じプロセスで実行されている場合に実行できないことを指定します。</span><span class="sxs-lookup"><span data-stu-id="b0a78-113">Specifies that the assembly cannot execute with other versions if they are running in the same process.</span></span>|  
|`afNonSideBySideMachine`|<span data-ttu-id="b0a78-114">アセンブリは他のバージョンが同じコンピューターで実行されている場合に実行できないことを指定します。</span><span class="sxs-lookup"><span data-stu-id="b0a78-114">Specifies that the assembly cannot execute with other versions if they are running on the same computer.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b0a78-115">Remarks</span><span class="sxs-lookup"><span data-stu-id="b0a78-115">Remarks</span></span>  
 <span data-ttu-id="b0a78-116">参照アセンブリのサイド バイ サイドでの互換性機能を記述する 0x0010 と 0x0070、両端を含むまでの値が使用されます。</span><span class="sxs-lookup"><span data-stu-id="b0a78-116">The values between 0x0010 and 0x0070, inclusive, are used to describe side-by-side compatibility features of the referenced assembly.</span></span> <span data-ttu-id="b0a78-117">これらの値を設定すると、アセンブリがサイド バイ サイドで互換性のあると見なされます。</span><span class="sxs-lookup"><span data-stu-id="b0a78-117">If none of these values are set, the assembly is assumed to be side-by-side compatible.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b0a78-118">必要条件</span><span class="sxs-lookup"><span data-stu-id="b0a78-118">Requirements</span></span>  
 <span data-ttu-id="b0a78-119">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b0a78-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b0a78-120">**ヘッダー:** MsCorEE.h</span><span class="sxs-lookup"><span data-stu-id="b0a78-120">**Header:** MsCorEE.h</span></span>  
  
 <span data-ttu-id="b0a78-121">**ライブラリ:** MsCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="b0a78-121">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b0a78-122">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b0a78-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0a78-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="b0a78-123">See also</span></span>

- [<span data-ttu-id="b0a78-124">メタデータ列挙型</span><span class="sxs-lookup"><span data-stu-id="b0a78-124">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
- [<span data-ttu-id="b0a78-125">IMetaDataAssemblyEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b0a78-125">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
