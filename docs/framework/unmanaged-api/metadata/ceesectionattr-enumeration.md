---
title: CeeSectionAttr 列挙型
ms.date: 03/30/2017
api_name:
- CeeSectionAttr
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CeeSectionAttr
helpviewer_keywords:
- CeeSectionAttr enumeration [.NET Framework metadata]
ms.assetid: 0db51881-b869-4677-a715-1726a9216489
topic_type:
- apiref
ms.openlocfilehash: 97b28c961f43388679615ac0d5b19c4c69df1e3d
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74444246"
---
# <a name="ceesectionattr-enumeration"></a><span data-ttu-id="77b4b-102">CeeSectionAttr 列挙型</span><span class="sxs-lookup"><span data-stu-id="77b4b-102">CeeSectionAttr Enumeration</span></span>
<span data-ttu-id="77b4b-103">Provides values that specify attributes of a section for use by the [ICeeGen](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md) interface.</span><span class="sxs-lookup"><span data-stu-id="77b4b-103">Provides values that specify attributes of a section for use by the [ICeeGen](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md) interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="77b4b-104">構文</span><span class="sxs-lookup"><span data-stu-id="77b4b-104">Syntax</span></span>  
  
```cpp  
typedef enum  {  
    sdNone      = 0,  
    sdReadOnly  = IMAGE_SCN_CNT_INITIALIZED_DATA |  
                  IMAGE_SCN_MEM_READ,  
    sdReadWrite = sdReadOnly | IMAGE_SCN_MEM_WRITE,  
    sdExecute   = IMAGE_SCN_MEM_READ | IMAGE_SCN_CNT_CODE |  
                  IMAGE_SCN_MEM_EXECUTE  
} CeeSectionAttr;  
```  
  
## <a name="members"></a><span data-ttu-id="77b4b-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="77b4b-105">Members</span></span>  
  
|<span data-ttu-id="77b4b-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="77b4b-106">Member</span></span>|<span data-ttu-id="77b4b-107">説明</span><span class="sxs-lookup"><span data-stu-id="77b4b-107">Description</span></span>|  
|------------|-----------------|  
|`sdNone`|<span data-ttu-id="77b4b-108">Section has no attributes.</span><span class="sxs-lookup"><span data-stu-id="77b4b-108">Section has no attributes.</span></span>|  
|`sdReadOnly`|<span data-ttu-id="77b4b-109">Section contains initialized data that can be only read, not updated.</span><span class="sxs-lookup"><span data-stu-id="77b4b-109">Section contains initialized data that can be only read, not updated.</span></span>|  
|`sdReadWrite`|<span data-ttu-id="77b4b-110">Section contains initialized data that can be read or updated.</span><span class="sxs-lookup"><span data-stu-id="77b4b-110">Section contains initialized data that can be read or updated.</span></span>|  
|`sdExecute`|<span data-ttu-id="77b4b-111">Section contains executable code that is allowed to be read and executed.</span><span class="sxs-lookup"><span data-stu-id="77b4b-111">Section contains executable code that is allowed to be read and executed.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="77b4b-112">［要件］</span><span class="sxs-lookup"><span data-stu-id="77b4b-112">Requirements</span></span>  
 <span data-ttu-id="77b4b-113">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="77b4b-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="77b4b-114">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="77b4b-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="77b4b-115">**Library:** Included as a resource in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="77b4b-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="77b4b-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="77b4b-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77b4b-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="77b4b-117">See also</span></span>

- [<span data-ttu-id="77b4b-118">メタデータ列挙型</span><span class="sxs-lookup"><span data-stu-id="77b4b-118">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
