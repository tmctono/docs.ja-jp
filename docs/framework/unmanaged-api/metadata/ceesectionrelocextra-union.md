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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8a78a4b82d0b2064c90c938a8614b0c7594f7856
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62043291"
---
# <a name="ceesectionrelocextra-union"></a><span data-ttu-id="8bd51-102">CeeSectionRelocExtra 共用体</span><span class="sxs-lookup"><span data-stu-id="8bd51-102">CeeSectionRelocExtra Union</span></span>
<span data-ttu-id="8bd51-103">によって使用されるアドレスのオフセットを表す、 [ICeeGen](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)セクションを再配置するインターフェイス。</span><span class="sxs-lookup"><span data-stu-id="8bd51-103">Represents an address offset that is used by the [ICeeGen](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md) interface to relocate a section.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8bd51-104">構文</span><span class="sxs-lookup"><span data-stu-id="8bd51-104">Syntax</span></span>  
  
```  
typedef union  {  
    USHORT highAdj;  
} CeeSectionRelocExtra;  
```  
  
## <a name="members"></a><span data-ttu-id="8bd51-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="8bd51-105">Members</span></span>  
  
|<span data-ttu-id="8bd51-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="8bd51-106">Member</span></span>|<span data-ttu-id="8bd51-107">説明</span><span class="sxs-lookup"><span data-stu-id="8bd51-107">Description</span></span>|  
|------------|-----------------|  
|`highAdj`|<span data-ttu-id="8bd51-108">セクションの上位アドレスを調整します。</span><span class="sxs-lookup"><span data-stu-id="8bd51-108">The upper address adjustment for the section.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8bd51-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="8bd51-109">Requirements</span></span>  
 <span data-ttu-id="8bd51-110">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8bd51-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8bd51-111">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="8bd51-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8bd51-112">**ライブラリ:** MsCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="8bd51-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="8bd51-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8bd51-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8bd51-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="8bd51-114">See also</span></span>

- [<span data-ttu-id="8bd51-115">メタデータ共用体</span><span class="sxs-lookup"><span data-stu-id="8bd51-115">Metadata Unions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-unions.md)
