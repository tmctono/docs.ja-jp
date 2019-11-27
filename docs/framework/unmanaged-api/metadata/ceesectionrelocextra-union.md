---
title: CeeSectionRelocExtra 共用体
ms.date: 03/30/2017
api_name:
- CeeSectionRelocExtra Union
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CeeSectionRelocExtra
helpviewer_keywords:
- CeeSectionRelocExtra union [.NET Framework metadata]
ms.assetid: d9568cf6-7f98-4cd6-ab36-0a2bd509afcc
topic_type:
- apiref
ms.openlocfilehash: 7becace679b62a635d8231c3d42213f247f44190
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74444168"
---
# <a name="ceesectionrelocextra-union"></a><span data-ttu-id="4fa13-102">CeeSectionRelocExtra 共用体</span><span class="sxs-lookup"><span data-stu-id="4fa13-102">CeeSectionRelocExtra Union</span></span>
<span data-ttu-id="4fa13-103">セクションを再配置するために[ICeeGen](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)インターフェイスによって使用されるアドレスオフセットを表します。</span><span class="sxs-lookup"><span data-stu-id="4fa13-103">Represents an address offset that is used by the [ICeeGen](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md) interface to relocate a section.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4fa13-104">構文</span><span class="sxs-lookup"><span data-stu-id="4fa13-104">Syntax</span></span>  
  
```cpp  
typedef union  {  
    USHORT highAdj;  
} CeeSectionRelocExtra;  
```  
  
## <a name="members"></a><span data-ttu-id="4fa13-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="4fa13-105">Members</span></span>  
  
|<span data-ttu-id="4fa13-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="4fa13-106">Member</span></span>|<span data-ttu-id="4fa13-107">説明</span><span class="sxs-lookup"><span data-stu-id="4fa13-107">Description</span></span>|  
|------------|-----------------|  
|`highAdj`|<span data-ttu-id="4fa13-108">セクションの上限アドレスの調整。</span><span class="sxs-lookup"><span data-stu-id="4fa13-108">The upper address adjustment for the section.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="4fa13-109">要件</span><span class="sxs-lookup"><span data-stu-id="4fa13-109">Requirements</span></span>  
 <span data-ttu-id="4fa13-110">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4fa13-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4fa13-111">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="4fa13-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="4fa13-112">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="4fa13-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="4fa13-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4fa13-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4fa13-114">参照</span><span class="sxs-lookup"><span data-stu-id="4fa13-114">See also</span></span>

- [<span data-ttu-id="4fa13-115">メタデータ共用体</span><span class="sxs-lookup"><span data-stu-id="4fa13-115">Metadata Unions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-unions.md)
