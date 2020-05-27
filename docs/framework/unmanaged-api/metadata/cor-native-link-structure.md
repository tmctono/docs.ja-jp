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
ms.openlocfilehash: a11b7d5939c4c20504b1ff3dfb4613f85bca0db4
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007976"
---
# <a name="cor_native_link-structure"></a><span data-ttu-id="462ef-102">COR_NATIVE_LINK 構造体</span><span class="sxs-lookup"><span data-stu-id="462ef-102">COR_NATIVE_LINK Structure</span></span>
<span data-ttu-id="462ef-103">ネイティブ コードのリンクに使用される情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="462ef-103">Contains information that is used to link native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="462ef-104">構文</span><span class="sxs-lookup"><span data-stu-id="462ef-104">Syntax</span></span>  
  
```cpp  
typedef struct
{  
    BYTE        m_linkType;  
    BYTE        m_flags;  
    mdMemberRef m_entryPoint;  
} COR_NATIVE_LINK;  
```  
  
## <a name="members"></a><span data-ttu-id="462ef-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="462ef-105">Members</span></span>  
  
|<span data-ttu-id="462ef-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="462ef-106">Member</span></span>|<span data-ttu-id="462ef-107">説明</span><span class="sxs-lookup"><span data-stu-id="462ef-107">Description</span></span>|  
|------------|-----------------|  
|`m_linkType`|<span data-ttu-id="462ef-108">ネイティブコードでリンクされる型。</span><span class="sxs-lookup"><span data-stu-id="462ef-108">The type to be linked in native code.</span></span> <span data-ttu-id="462ef-109">この値は、 [CorNativeLinkType](cornativelinktype-enumeration.md)値の1つです。</span><span class="sxs-lookup"><span data-stu-id="462ef-109">This value is one of the [CorNativeLinkType](cornativelinktype-enumeration.md) values.</span></span>|  
|`m_flags`|<span data-ttu-id="462ef-110">ネイティブコードをリンクするときにリンカーによって使用されるフラグ。</span><span class="sxs-lookup"><span data-stu-id="462ef-110">Flags used by the linker when linking native code.</span></span> <span data-ttu-id="462ef-111">この値は、 [CorNativeLinkFlags](cornativelinkflags-enumeration.md)値の1つです。</span><span class="sxs-lookup"><span data-stu-id="462ef-111">This value is one of the [CorNativeLinkFlags](cornativelinkflags-enumeration.md) values.</span></span>|  
|`m_entryPoint`|<span data-ttu-id="462ef-112">エントリポイントを表す MemberRef メタデータトークン。</span><span class="sxs-lookup"><span data-stu-id="462ef-112">The MemberRef metadata token that represents the entry point.</span></span> <span data-ttu-id="462ef-113">形式は `lib:entrypoint` です。</span><span class="sxs-lookup"><span data-stu-id="462ef-113">The format is `lib:entrypoint`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="462ef-114">必要条件</span><span class="sxs-lookup"><span data-stu-id="462ef-114">Requirements</span></span>  
 <span data-ttu-id="462ef-115">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="462ef-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="462ef-116">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="462ef-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="462ef-117">**ライブラリ:** Mscoree.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="462ef-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="462ef-118">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="462ef-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="462ef-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="462ef-119">See also</span></span>

- [<span data-ttu-id="462ef-120">メタデータ構造体</span><span class="sxs-lookup"><span data-stu-id="462ef-120">Metadata Structures</span></span>](metadata-structures.md)
- [<span data-ttu-id="462ef-121">CorNativeLinkType 列挙型</span><span class="sxs-lookup"><span data-stu-id="462ef-121">CorNativeLinkType Enumeration</span></span>](cornativelinktype-enumeration.md)
- [<span data-ttu-id="462ef-122">CorNativeLinkFlags 列挙型</span><span class="sxs-lookup"><span data-stu-id="462ef-122">CorNativeLinkFlags Enumeration</span></span>](cornativelinkflags-enumeration.md)
