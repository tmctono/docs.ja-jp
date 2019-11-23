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
ms.openlocfilehash: ffb5953c843a338b4548253457a0c3b1ca0c20f5
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74444302"
---
# <a name="assemblyflags-enumeration"></a><span data-ttu-id="6f47f-102">AssemblyFlags 列挙体</span><span class="sxs-lookup"><span data-stu-id="6f47f-102">AssemblyFlags Enumeration</span></span>
<span data-ttu-id="6f47f-103">Contains values that describe run-time features of an assembly.</span><span class="sxs-lookup"><span data-stu-id="6f47f-103">Contains values that describe run-time features of an assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6f47f-104">構文</span><span class="sxs-lookup"><span data-stu-id="6f47f-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    afImplicitExportedTypes = 0x0001,  
    afImplicitResources = 0x0002,  
    afNonSideBySideAppDomain = 0x0010,  
    afNonSideBySideProcess = 0x0020,  
    afNonSideBySideMachine = 0x0030  
} AssemblyFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="6f47f-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="6f47f-105">Members</span></span>  
  
|<span data-ttu-id="6f47f-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="6f47f-106">Member</span></span>|<span data-ttu-id="6f47f-107">説明</span><span class="sxs-lookup"><span data-stu-id="6f47f-107">Description</span></span>|  
|------------|-----------------|  
|`afImplicitExportedTypes`|<span data-ttu-id="6f47f-108">Specifies that exported type definitions are implicit within the files that comprise the assembly.</span><span class="sxs-lookup"><span data-stu-id="6f47f-108">Specifies that exported type definitions are implicit within the files that comprise the assembly.</span></span> <span data-ttu-id="6f47f-109">In the .NET Framework versions 1.0 and 1.1, this value is always assumed to be set.</span><span class="sxs-lookup"><span data-stu-id="6f47f-109">In the .NET Framework versions 1.0 and 1.1, this value is always assumed to be set.</span></span>|  
|`afImplicitResources`|<span data-ttu-id="6f47f-110">Specifies that resource definitions are implicit within the files that comprise the assembly.</span><span class="sxs-lookup"><span data-stu-id="6f47f-110">Specifies that resource definitions are implicit within the files that comprise the assembly.</span></span> <span data-ttu-id="6f47f-111">In the .NET Framework 1.0 and 1.1, this value is always assumed to be set.</span><span class="sxs-lookup"><span data-stu-id="6f47f-111">In the .NET Framework 1.0 and 1.1, this value is always assumed to be set.</span></span>|  
|`afNonSideBySideAppDomain`|<span data-ttu-id="6f47f-112">Specifies that the assembly cannot execute with other versions if they are running in the same application domain.</span><span class="sxs-lookup"><span data-stu-id="6f47f-112">Specifies that the assembly cannot execute with other versions if they are running in the same application domain.</span></span>|  
|`afNonSideBySideProcess`|<span data-ttu-id="6f47f-113">Specifies that the assembly cannot execute with other versions if they are running in the same process.</span><span class="sxs-lookup"><span data-stu-id="6f47f-113">Specifies that the assembly cannot execute with other versions if they are running in the same process.</span></span>|  
|`afNonSideBySideMachine`|<span data-ttu-id="6f47f-114">Specifies that the assembly cannot execute with other versions if they are running on the same computer.</span><span class="sxs-lookup"><span data-stu-id="6f47f-114">Specifies that the assembly cannot execute with other versions if they are running on the same computer.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6f47f-115">Remarks</span><span class="sxs-lookup"><span data-stu-id="6f47f-115">Remarks</span></span>  
 <span data-ttu-id="6f47f-116">The values between 0x0010 and 0x0070, inclusive, are used to describe side-by-side compatibility features of the referenced assembly.</span><span class="sxs-lookup"><span data-stu-id="6f47f-116">The values between 0x0010 and 0x0070, inclusive, are used to describe side-by-side compatibility features of the referenced assembly.</span></span> <span data-ttu-id="6f47f-117">If none of these values are set, the assembly is assumed to be side-by-side compatible.</span><span class="sxs-lookup"><span data-stu-id="6f47f-117">If none of these values are set, the assembly is assumed to be side-by-side compatible.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6f47f-118">［要件］</span><span class="sxs-lookup"><span data-stu-id="6f47f-118">Requirements</span></span>  
 <span data-ttu-id="6f47f-119">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6f47f-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6f47f-120">**Header:** MsCorEE.h</span><span class="sxs-lookup"><span data-stu-id="6f47f-120">**Header:** MsCorEE.h</span></span>  
  
 <span data-ttu-id="6f47f-121">**Library:** Included as a resource in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="6f47f-121">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="6f47f-122">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6f47f-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f47f-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="6f47f-123">See also</span></span>

- [<span data-ttu-id="6f47f-124">メタデータ列挙型</span><span class="sxs-lookup"><span data-stu-id="6f47f-124">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
- [<span data-ttu-id="6f47f-125">IMetaDataAssemblyEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6f47f-125">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
