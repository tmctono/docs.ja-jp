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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7024140ed9b870b5db38dba7e9b13321dd37386a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59157587"
---
# <a name="cornativelink-structure"></a><span data-ttu-id="a0623-102">COR_NATIVE_LINK 構造体</span><span class="sxs-lookup"><span data-stu-id="a0623-102">COR_NATIVE_LINK Structure</span></span>
<span data-ttu-id="a0623-103">ネイティブ コードのリンクに使用される情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="a0623-103">Contains information that is used to link native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a0623-104">構文</span><span class="sxs-lookup"><span data-stu-id="a0623-104">Syntax</span></span>  
  
```  
typedef struct   
{  
    BYTE        m_linkType;  
    BYTE        m_flags;  
    mdMemberRef m_entryPoint;  
} COR_NATIVE_LINK;  
```  
  
## <a name="members"></a><span data-ttu-id="a0623-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="a0623-105">Members</span></span>  
  
|<span data-ttu-id="a0623-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="a0623-106">Member</span></span>|<span data-ttu-id="a0623-107">説明</span><span class="sxs-lookup"><span data-stu-id="a0623-107">Description</span></span>|  
|------------|-----------------|  
|`m_linkType`|<span data-ttu-id="a0623-108">ネイティブ コードにリンクされている型。</span><span class="sxs-lookup"><span data-stu-id="a0623-108">The type to be linked in native code.</span></span> <span data-ttu-id="a0623-109">この値は、のいずれか、 [CorNativeLinkType](../../../../docs/framework/unmanaged-api/metadata/cornativelinktype-enumeration.md)値。</span><span class="sxs-lookup"><span data-stu-id="a0623-109">This value is one of the [CorNativeLinkType](../../../../docs/framework/unmanaged-api/metadata/cornativelinktype-enumeration.md) values.</span></span>|  
|`m_flags`|<span data-ttu-id="a0623-110">ネイティブ コードをリンクするときに、リンカーで使用するフラグ。</span><span class="sxs-lookup"><span data-stu-id="a0623-110">Flags used by the linker when linking native code.</span></span> <span data-ttu-id="a0623-111">この値は、のいずれか、 [CorNativeLinkFlags](../../../../docs/framework/unmanaged-api/metadata/cornativelinkflags-enumeration.md)値。</span><span class="sxs-lookup"><span data-stu-id="a0623-111">This value is one of the [CorNativeLinkFlags](../../../../docs/framework/unmanaged-api/metadata/cornativelinkflags-enumeration.md) values.</span></span>|  
|`m_entryPoint`|<span data-ttu-id="a0623-112">エントリ ポイントを表す MemberRef メタデータ トークン。</span><span class="sxs-lookup"><span data-stu-id="a0623-112">The MemberRef metadata token that represents the entry point.</span></span> <span data-ttu-id="a0623-113">形式は`lib:entrypoint`します。</span><span class="sxs-lookup"><span data-stu-id="a0623-113">The format is `lib:entrypoint`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a0623-114">必要条件</span><span class="sxs-lookup"><span data-stu-id="a0623-114">Requirements</span></span>  
 <span data-ttu-id="a0623-115">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a0623-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a0623-116">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="a0623-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a0623-117">**ライブラリ:** MsCorEE.dll にリソースとして使用</span><span class="sxs-lookup"><span data-stu-id="a0623-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="a0623-118">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="a0623-118">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="a0623-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="a0623-119">See also</span></span>

- [<span data-ttu-id="a0623-120">メタデータ構造体</span><span class="sxs-lookup"><span data-stu-id="a0623-120">Metadata Structures</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-structures.md)
- [<span data-ttu-id="a0623-121">CorNativeLinkType 列挙型</span><span class="sxs-lookup"><span data-stu-id="a0623-121">CorNativeLinkType Enumeration</span></span>](../../../../docs/framework/unmanaged-api/metadata/cornativelinktype-enumeration.md)
- [<span data-ttu-id="a0623-122">CorNativeLinkFlags 列挙型</span><span class="sxs-lookup"><span data-stu-id="a0623-122">CorNativeLinkFlags Enumeration</span></span>](../../../../docs/framework/unmanaged-api/metadata/cornativelinkflags-enumeration.md)
