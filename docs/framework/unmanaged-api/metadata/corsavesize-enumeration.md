---
title: CorSaveSize 列挙型
ms.date: 03/30/2017
api_name:
- CorSaveSize
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorSaveSize
helpviewer_keywords:
- CorSaveSize enumeration [.NET Framework metadata]
ms.assetid: eb95ce39-5688-43c1-a34d-578794b32faa
topic_type:
- apiref
ms.openlocfilehash: 0f870d9d7d1bc292b213d690df508a6c28bac2ab
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74450101"
---
# <a name="corsavesize-enumeration"></a><span data-ttu-id="08a6b-102">CorSaveSize 列挙型</span><span class="sxs-lookup"><span data-stu-id="08a6b-102">CorSaveSize Enumeration</span></span>
<span data-ttu-id="08a6b-103">保存操作のサイズの照会で要求される精度のレベルを示す値が格納されます。</span><span class="sxs-lookup"><span data-stu-id="08a6b-103">Contains values indicating the level of precision required when querying for the size of a save operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="08a6b-104">構文</span><span class="sxs-lookup"><span data-stu-id="08a6b-104">Syntax</span></span>  
  
```cpp  
typedef enum CorSaveSize {  
    cssAccurate                = 0x0000,   
    cssQuick                   = 0x0001,   
    cssDiscardTransientCAs     = 0x0002  
} CorSaveSize;  
```  
  
## <a name="members"></a><span data-ttu-id="08a6b-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="08a6b-105">Members</span></span>  
  
|<span data-ttu-id="08a6b-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="08a6b-106">Member</span></span>|<span data-ttu-id="08a6b-107">説明</span><span class="sxs-lookup"><span data-stu-id="08a6b-107">Description</span></span>|  
|------------|-----------------|  
|`cssAccurate`|<span data-ttu-id="08a6b-108">Specifies that the return value should be exact.</span><span class="sxs-lookup"><span data-stu-id="08a6b-108">Specifies that the return value should be exact.</span></span>|  
|`cssQuick`|<span data-ttu-id="08a6b-109">Specifies that the return value should be estimated.</span><span class="sxs-lookup"><span data-stu-id="08a6b-109">Specifies that the return value should be estimated.</span></span>|  
|`cssDiscardTransientCAs`|<span data-ttu-id="08a6b-110">Specifies that discardable types should be removed.</span><span class="sxs-lookup"><span data-stu-id="08a6b-110">Specifies that discardable types should be removed.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="08a6b-111">［要件］</span><span class="sxs-lookup"><span data-stu-id="08a6b-111">Requirements</span></span>  
 <span data-ttu-id="08a6b-112">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="08a6b-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="08a6b-113">**Header:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="08a6b-113">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="08a6b-114">**Library:** Used as a resource in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="08a6b-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="08a6b-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="08a6b-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08a6b-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="08a6b-116">See also</span></span>

- [<span data-ttu-id="08a6b-117">メタデータ列挙型</span><span class="sxs-lookup"><span data-stu-id="08a6b-117">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
