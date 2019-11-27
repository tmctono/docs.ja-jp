---
title: CorNotificationForTokenMovement 列挙型
ms.date: 03/30/2017
api_name:
- CorNotificationForTokenMovement
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorNotificationForTokenMovement
helpviewer_keywords:
- CorNotificationForTokenMovement enumeration [.NET Framework metadata]
ms.assetid: 1edd1670-976a-4fc8-bef7-7c41e60ad989
topic_type:
- apiref
ms.openlocfilehash: 411fad0accb59431f776c5bd66e8bd3027ddd907
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74450146"
---
# <a name="cornotificationfortokenmovement-enumeration"></a><span data-ttu-id="ad58d-102">CorNotificationForTokenMovement 列挙型</span><span class="sxs-lookup"><span data-stu-id="ad58d-102">CorNotificationForTokenMovement Enumeration</span></span>
<span data-ttu-id="ad58d-103">トークンの再マップが発生したときにメタデータ API クライアントに送信される通知を指定します。</span><span class="sxs-lookup"><span data-stu-id="ad58d-103">Specifies the notifications that will be sent to the metadata API client when a token remap occurs.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ad58d-104">構文</span><span class="sxs-lookup"><span data-stu-id="ad58d-104">Syntax</span></span>  
  
```cpp  
typedef enum CorNotificationForTokenMovement {  
  
    MDNotifyDefault             = 0x0000000f,  
    MDNotifyAll                 = 0xffffffff,  
    MDNotifyNone                = 0x00000000,  
    MDNotifyMethodDef           = 0x00000001,  
    MDNotifyMemberRef           = 0x00000002,  
    MDNotifyFieldDef            = 0x00000004,  
    MDNotifyTypeRef             = 0x00000008,  
  
    MDNotifyTypeDef             = 0x00000010,  
    MDNotifyParamDef            = 0x00000020,  
    MDNotifyInterfaceImpl       = 0x00000040,  
    MDNotifyProperty            = 0x00000080,  
    MDNotifyEvent               = 0x00000100,  
    MDNotifySignature           = 0x00000200,  
    MDNotifyTypeSpec            = 0x00000400,  
    MDNotifyCustomAttribute     = 0x00000800,  
    MDNotifySecurityValue       = 0x00001000,  
    MDNotifyPermission          = 0x00002000,  
    MDNotifyModuleRef           = 0x00004000,  
  
    MDNotifyNameSpace           = 0x00008000,  
  
    MDNotifyAssemblyRef         = 0x01000000,  
    MDNotifyFile                = 0x02000000,  
    MDNotifyExportedType        = 0x04000000,  
    MDNotifyResource            = 0x08000000  
  
} CorNotificationForTokenMovement;  
```  
  
## <a name="members"></a><span data-ttu-id="ad58d-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="ad58d-105">Members</span></span>  
  
|<span data-ttu-id="ad58d-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="ad58d-106">Member</span></span>|<span data-ttu-id="ad58d-107">説明</span><span class="sxs-lookup"><span data-stu-id="ad58d-107">Description</span></span>|  
|------------|-----------------|  
|`MDNotifyDefault`|<span data-ttu-id="ad58d-108">`mdTypeRef`、`mdMethodDef`、`mdMemberRef`、または `mdFieldDef` のトークンが移動したときに通知します。</span><span class="sxs-lookup"><span data-stu-id="ad58d-108">Notify when `mdTypeRef`, `mdMethodDef`, `mdMemberRef`, or `mdFieldDef` tokens move.</span></span>|  
|`MDNotifyAll`|<span data-ttu-id="ad58d-109">任意のトークンが移動したときに通知します。</span><span class="sxs-lookup"><span data-stu-id="ad58d-109">Notify when any token moves.</span></span>|  
|`MDNotifyNone`|<span data-ttu-id="ad58d-110">トークンの移動時に通知しません。</span><span class="sxs-lookup"><span data-stu-id="ad58d-110">Do not notify when tokens move.</span></span>|  
|`MDNotifyMethodDef`|<span data-ttu-id="ad58d-111">`mdMethodDef` トークンが移動したときに通知します。</span><span class="sxs-lookup"><span data-stu-id="ad58d-111">Notify when an `mdMethodDef` token moves.</span></span>|  
|`MDNotifyMemberRef`|<span data-ttu-id="ad58d-112">`mdMemberRef` トークンが移動したときに通知します。</span><span class="sxs-lookup"><span data-stu-id="ad58d-112">Notify when an `mdMemberRef` token moves.</span></span>|  
|`MDNotifyFieldDef`|<span data-ttu-id="ad58d-113">`mdFieldDef` トークンが移動したときに通知します。</span><span class="sxs-lookup"><span data-stu-id="ad58d-113">Notify when an `mdFieldDef` token moves.</span></span>|  
|`MDNotifyTypeRef`|<span data-ttu-id="ad58d-114">`mdTypeRef` トークンが移動したときに通知します。</span><span class="sxs-lookup"><span data-stu-id="ad58d-114">Notify when an `mdTypeRef` token moves.</span></span>|  
|`MDNotifyTypeDef`|<span data-ttu-id="ad58d-115">`mdTypeDef` トークンが移動したときに通知します。</span><span class="sxs-lookup"><span data-stu-id="ad58d-115">Notify when an `mdTypeDef` token moves.</span></span>|  
|`MDNotifyParamDef`|<span data-ttu-id="ad58d-116">`mdParamDef` トークンが移動したときに通知します。</span><span class="sxs-lookup"><span data-stu-id="ad58d-116">Notify when an `mdParamDef` token moves.</span></span>|  
|`MDNotifyInterfaceImpl`|<span data-ttu-id="ad58d-117">`mdInterfaceImpl` トークンが移動したときに通知します。</span><span class="sxs-lookup"><span data-stu-id="ad58d-117">Notify when an `mdInterfaceImpl` token moves.</span></span>|  
|`MDNotifyProperty`|<span data-ttu-id="ad58d-118">`mdProperty` トークンが移動したときに通知します。</span><span class="sxs-lookup"><span data-stu-id="ad58d-118">Notify when an `mdProperty` token moves.</span></span>|  
|`MDNotifyEvent`|<span data-ttu-id="ad58d-119">`mdEvent` トークンが移動したときに通知します。</span><span class="sxs-lookup"><span data-stu-id="ad58d-119">Notify when an `mdEvent` token moves.</span></span>|  
|`MDNotifySignature`|<span data-ttu-id="ad58d-120">`mdSignature` トークンが移動したときに通知します。</span><span class="sxs-lookup"><span data-stu-id="ad58d-120">Notify when an `mdSignature` token moves.</span></span>|  
|`MDNotifyTypeSpec`|<span data-ttu-id="ad58d-121">`mdTypeSpec` トークンが移動したときに通知します。</span><span class="sxs-lookup"><span data-stu-id="ad58d-121">Notify when an `mdTypeSpec` token moves.</span></span>|  
|`MDNotifyCustomAttribute`|<span data-ttu-id="ad58d-122">`mdCustomAttribute` トークンが移動したときに通知します。</span><span class="sxs-lookup"><span data-stu-id="ad58d-122">Notify when an `mdCustomAttribute` token moves.</span></span>|  
|`MDNotifySecurityValue`|<span data-ttu-id="ad58d-123">`mdSecurityValue` トークンが移動したときに通知します。</span><span class="sxs-lookup"><span data-stu-id="ad58d-123">Notify when an `mdSecurityValue` token moves.</span></span>|  
|`MDNotifyPermission`|<span data-ttu-id="ad58d-124">`mdPermission` トークンが移動したときに通知します。</span><span class="sxs-lookup"><span data-stu-id="ad58d-124">Notify when an `mdPermission` token moves.</span></span>|  
|`MDNotifyModuleRef`|<span data-ttu-id="ad58d-125">`mdModuleRef` トークンが移動したときに通知します。</span><span class="sxs-lookup"><span data-stu-id="ad58d-125">Notify when an `mdModuleRef` token moves.</span></span>|  
|`MDNotifyNameSpace`|<span data-ttu-id="ad58d-126">`mdNameSpace` トークンが移動したときに通知します。</span><span class="sxs-lookup"><span data-stu-id="ad58d-126">Notify when an `mdNameSpace` token moves.</span></span>|  
|`MDNotifyAssemblyRef`|<span data-ttu-id="ad58d-127">`mdAssemblyRef` トークンが移動したときに通知します。</span><span class="sxs-lookup"><span data-stu-id="ad58d-127">Notify when an `mdAssemblyRef` token moves.</span></span>|  
|`MDNotifyFile`|<span data-ttu-id="ad58d-128">`mdFile` トークンが移動したときに通知します。</span><span class="sxs-lookup"><span data-stu-id="ad58d-128">Notify when an `mdFile` token moves.</span></span>|  
|`MDNotifyExportedType`|<span data-ttu-id="ad58d-129">`mdExportedType` トークンが移動したときに通知します。</span><span class="sxs-lookup"><span data-stu-id="ad58d-129">Notify when an `mdExportedType` token moves.</span></span>|  
|`MDNotifyResource`|<span data-ttu-id="ad58d-130">`mdManifestResource` トークンが移動したときに通知します。</span><span class="sxs-lookup"><span data-stu-id="ad58d-130">Notify when an `mdManifestResource` token moves.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ad58d-131">コメント</span><span class="sxs-lookup"><span data-stu-id="ad58d-131">Remarks</span></span>  
 <span data-ttu-id="ad58d-132">メタデータのマージ中に、トークンが再マップ (移動) される場合があります。</span><span class="sxs-lookup"><span data-stu-id="ad58d-132">A token may be re-mapped (that is, moved) during a metadata merge.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ad58d-133">要件</span><span class="sxs-lookup"><span data-stu-id="ad58d-133">Requirements</span></span>  
 <span data-ttu-id="ad58d-134">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ad58d-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ad58d-135">**ヘッダー:** CorHdr. h</span><span class="sxs-lookup"><span data-stu-id="ad58d-135">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="ad58d-136">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ad58d-136">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad58d-137">参照</span><span class="sxs-lookup"><span data-stu-id="ad58d-137">See also</span></span>

- [<span data-ttu-id="ad58d-138">メタデータ列挙型</span><span class="sxs-lookup"><span data-stu-id="ad58d-138">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
