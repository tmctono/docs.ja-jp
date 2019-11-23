---
title: CorLocalRefPreservation 列挙型
ms.date: 03/30/2017
api_name:
- CorLocalRefPreservation
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorLocalRefPreservation
helpviewer_keywords:
- CorLocalRefPreservation enumeration [.NET Framework metadata]
ms.assetid: 44757163-1228-4213-a4c4-d4de503cc75d
topic_type:
- apiref
ms.openlocfilehash: 706ea37101f9f961e92d8cef2cf508c1dd0d56c1
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74450246"
---
# <a name="corlocalrefpreservation-enumeration"></a><span data-ttu-id="d94aa-102">CorLocalRefPreservation 列挙型</span><span class="sxs-lookup"><span data-stu-id="d94aa-102">CorLocalRefPreservation Enumeration</span></span>
<span data-ttu-id="d94aa-103">ローカル参照の処理のためのフラグ値が格納されます。</span><span class="sxs-lookup"><span data-stu-id="d94aa-103">Contains flag values for the treatment of local references.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d94aa-104">構文</span><span class="sxs-lookup"><span data-stu-id="d94aa-104">Syntax</span></span>  
  
```cpp  
typedef enum CorLocalRefPreservation  
{  
    MDPreserveLocalRefsNone     =   0x00000000,  
    MDPreserveLocalTypeRef      =   0x00000001,  
    MDPreserveLocalMemberRef    =   0x00000002  
} CorLocalRefPreservation;  
```  
  
## <a name="members"></a><span data-ttu-id="d94aa-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="d94aa-105">Members</span></span>  
  
|<span data-ttu-id="d94aa-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="d94aa-106">Member</span></span>|<span data-ttu-id="d94aa-107">説明</span><span class="sxs-lookup"><span data-stu-id="d94aa-107">Description</span></span>|  
|------------|-----------------|  
|`MDPreserveLocalRefsNone`|<span data-ttu-id="d94aa-108">Preserve no local references.</span><span class="sxs-lookup"><span data-stu-id="d94aa-108">Preserve no local references.</span></span>|  
|`MDPreserveLocalTypeRef`|<span data-ttu-id="d94aa-109">Preserve local type references.</span><span class="sxs-lookup"><span data-stu-id="d94aa-109">Preserve local type references.</span></span>|  
|`MDPreserveLocalMemberRef`|<span data-ttu-id="d94aa-110">Preserve local member references.</span><span class="sxs-lookup"><span data-stu-id="d94aa-110">Preserve local member references.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d94aa-111">［要件］</span><span class="sxs-lookup"><span data-stu-id="d94aa-111">Requirements</span></span>  
 <span data-ttu-id="d94aa-112">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d94aa-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d94aa-113">**Header:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="d94aa-113">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="d94aa-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d94aa-114">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d94aa-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="d94aa-115">See also</span></span>

- [<span data-ttu-id="d94aa-116">メタデータ列挙型</span><span class="sxs-lookup"><span data-stu-id="d94aa-116">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
