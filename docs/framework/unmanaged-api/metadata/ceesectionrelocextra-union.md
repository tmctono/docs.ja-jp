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
ms.openlocfilehash: d11fefe220fdb00457cc48a6cd166673350be049
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/27/2020
ms.locfileid: "84006034"
---
# <a name="ceesectionrelocextra-union"></a><span data-ttu-id="79a46-102">CeeSectionRelocExtra 共用体</span><span class="sxs-lookup"><span data-stu-id="79a46-102">CeeSectionRelocExtra Union</span></span>
<span data-ttu-id="79a46-103">セクションを再配置するために[ICeeGen](iceegen-interface.md)インターフェイスによって使用されるアドレスオフセットを表します。</span><span class="sxs-lookup"><span data-stu-id="79a46-103">Represents an address offset that is used by the [ICeeGen](iceegen-interface.md) interface to relocate a section.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="79a46-104">構文</span><span class="sxs-lookup"><span data-stu-id="79a46-104">Syntax</span></span>  
  
```cpp  
typedef union  {  
    USHORT highAdj;  
} CeeSectionRelocExtra;  
```  
  
## <a name="members"></a><span data-ttu-id="79a46-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="79a46-105">Members</span></span>  
  
|<span data-ttu-id="79a46-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="79a46-106">Member</span></span>|<span data-ttu-id="79a46-107">説明</span><span class="sxs-lookup"><span data-stu-id="79a46-107">Description</span></span>|  
|------------|-----------------|  
|`highAdj`|<span data-ttu-id="79a46-108">セクションの上限アドレスの調整。</span><span class="sxs-lookup"><span data-stu-id="79a46-108">The upper address adjustment for the section.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="79a46-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="79a46-109">Requirements</span></span>  
 <span data-ttu-id="79a46-110">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="79a46-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="79a46-111">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="79a46-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="79a46-112">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="79a46-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="79a46-113">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="79a46-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79a46-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="79a46-114">See also</span></span>

- [<span data-ttu-id="79a46-115">メタデータ共用体</span><span class="sxs-lookup"><span data-stu-id="79a46-115">Metadata Unions</span></span>](metadata-unions.md)
