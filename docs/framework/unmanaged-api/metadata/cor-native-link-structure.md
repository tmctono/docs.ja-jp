---
title: COR_NATIVE_LINK 構造体
ms.date: 03/30/2017
api_name:
- COR_NATIVE_LINK
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- COR_NATIVE_LINK
helpviewer_keywords:
- COR_NATIVE_LINK structure [.NET Framework metadata]
ms.assetid: 6ef78d3c-1c69-4141-b687-dcb065b7a74d
topic_type:
- apiref
ms.openlocfilehash: d03c22c455f0e44ce32d4593d9eee50ceef94a22
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74443948"
---
# <a name="cor_native_link-structure"></a><span data-ttu-id="1f5d6-102">COR_NATIVE_LINK 構造体</span><span class="sxs-lookup"><span data-stu-id="1f5d6-102">COR_NATIVE_LINK Structure</span></span>
<span data-ttu-id="1f5d6-103">ネイティブ コードのリンクに使用される情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="1f5d6-103">Contains information that is used to link native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1f5d6-104">構文</span><span class="sxs-lookup"><span data-stu-id="1f5d6-104">Syntax</span></span>  
  
```cpp  
typedef struct   
{  
    BYTE        m_linkType;  
    BYTE        m_flags;  
    mdMemberRef m_entryPoint;  
} COR_NATIVE_LINK;  
```  
  
## <a name="members"></a><span data-ttu-id="1f5d6-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="1f5d6-105">Members</span></span>  
  
|<span data-ttu-id="1f5d6-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="1f5d6-106">Member</span></span>|<span data-ttu-id="1f5d6-107">説明</span><span class="sxs-lookup"><span data-stu-id="1f5d6-107">Description</span></span>|  
|------------|-----------------|  
|`m_linkType`|<span data-ttu-id="1f5d6-108">The type to be linked in native code.</span><span class="sxs-lookup"><span data-stu-id="1f5d6-108">The type to be linked in native code.</span></span> <span data-ttu-id="1f5d6-109">This value is one of the [CorNativeLinkType](../../../../docs/framework/unmanaged-api/metadata/cornativelinktype-enumeration.md) values.</span><span class="sxs-lookup"><span data-stu-id="1f5d6-109">This value is one of the [CorNativeLinkType](../../../../docs/framework/unmanaged-api/metadata/cornativelinktype-enumeration.md) values.</span></span>|  
|`m_flags`|<span data-ttu-id="1f5d6-110">Flags used by the linker when linking native code.</span><span class="sxs-lookup"><span data-stu-id="1f5d6-110">Flags used by the linker when linking native code.</span></span> <span data-ttu-id="1f5d6-111">This value is one of the [CorNativeLinkFlags](../../../../docs/framework/unmanaged-api/metadata/cornativelinkflags-enumeration.md) values.</span><span class="sxs-lookup"><span data-stu-id="1f5d6-111">This value is one of the [CorNativeLinkFlags](../../../../docs/framework/unmanaged-api/metadata/cornativelinkflags-enumeration.md) values.</span></span>|  
|`m_entryPoint`|<span data-ttu-id="1f5d6-112">The MemberRef metadata token that represents the entry point.</span><span class="sxs-lookup"><span data-stu-id="1f5d6-112">The MemberRef metadata token that represents the entry point.</span></span> <span data-ttu-id="1f5d6-113">The format is `lib:entrypoint`.</span><span class="sxs-lookup"><span data-stu-id="1f5d6-113">The format is `lib:entrypoint`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="1f5d6-114">［要件］</span><span class="sxs-lookup"><span data-stu-id="1f5d6-114">Requirements</span></span>  
 <span data-ttu-id="1f5d6-115">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1f5d6-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1f5d6-116">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="1f5d6-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="1f5d6-117">**Library:** Used as a resource in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="1f5d6-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="1f5d6-118">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1f5d6-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f5d6-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="1f5d6-119">See also</span></span>

- [<span data-ttu-id="1f5d6-120">メタデータ構造体</span><span class="sxs-lookup"><span data-stu-id="1f5d6-120">Metadata Structures</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-structures.md)
- [<span data-ttu-id="1f5d6-121">CorNativeLinkType 列挙型</span><span class="sxs-lookup"><span data-stu-id="1f5d6-121">CorNativeLinkType Enumeration</span></span>](../../../../docs/framework/unmanaged-api/metadata/cornativelinktype-enumeration.md)
- [<span data-ttu-id="1f5d6-122">CorNativeLinkFlags 列挙型</span><span class="sxs-lookup"><span data-stu-id="1f5d6-122">CorNativeLinkFlags Enumeration</span></span>](../../../../docs/framework/unmanaged-api/metadata/cornativelinkflags-enumeration.md)
