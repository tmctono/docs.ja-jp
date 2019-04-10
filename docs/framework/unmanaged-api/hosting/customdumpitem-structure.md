---
title: CustomDumpItem 構造体
ms.date: 03/30/2017
api_name:
- CustomDumpItem
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CustomDumpItem
helpviewer_keywords:
- CustomDumpItem structure [.NET Framework hosting]
ms.assetid: fd9085ff-7beb-4c38-97f0-037cd8ba4f65
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9000f35e9a8f7ecc6c40cf0ef9c220fc9f4f9c10
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59185927"
---
# <a name="customdumpitem-structure"></a><span data-ttu-id="7f5a5-102">CustomDumpItem 構造体</span><span class="sxs-lookup"><span data-stu-id="7f5a5-102">CustomDumpItem Structure</span></span>
<span data-ttu-id="7f5a5-103">エラー報告でのカスタム ダンプに追加する項目をについて説明します。</span><span class="sxs-lookup"><span data-stu-id="7f5a5-103">Describes an item to be added to a custom dump in error reporting.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7f5a5-104">構文</span><span class="sxs-lookup"><span data-stu-id="7f5a5-104">Syntax</span></span>  
  
```  
struct {  
    ECustomDumpItemKind itemKind;   
    union {  
        UINT_PTR pReserved;  
    }  
} CustomDumpItem;  
```  
  
## <a name="members"></a><span data-ttu-id="7f5a5-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="7f5a5-105">Members</span></span>  
  
|<span data-ttu-id="7f5a5-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="7f5a5-106">Member</span></span>|<span data-ttu-id="7f5a5-107">説明</span><span class="sxs-lookup"><span data-stu-id="7f5a5-107">Description</span></span>|  
|------------|-----------------|  
|`itemKind`|<span data-ttu-id="7f5a5-108">[ECustomDumpItemKind](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpitemkind-enumeration.md)を追加する項目の種類を示す値。</span><span class="sxs-lookup"><span data-stu-id="7f5a5-108">An [ECustomDumpItemKind](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpitemkind-enumeration.md) value that indicates the kind of item to be added.</span></span>|  
|`pReserved`|<span data-ttu-id="7f5a5-109">使用されていません。</span><span class="sxs-lookup"><span data-stu-id="7f5a5-109">Not currently used.</span></span> <span data-ttu-id="7f5a5-110">和集合に追加する項目は、ポインターのサイズを超えるである必要があります。</span><span class="sxs-lookup"><span data-stu-id="7f5a5-110">Any items added to the union must be no larger than pointer size.</span></span> <span data-ttu-id="7f5a5-111">場合、`struct`は必要に応じて、個別に割り当ててし、ポイントすると、します。</span><span class="sxs-lookup"><span data-stu-id="7f5a5-111">If a `struct` is required, you must allocate it separately and point to it.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7f5a5-112">Remarks</span><span class="sxs-lookup"><span data-stu-id="7f5a5-112">Remarks</span></span>  
 <span data-ttu-id="7f5a5-113">[Iclrerrorreportingmanager::begincustomdump](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-begincustomdump-method.md)型のパラメーターを受け取る`CustomDumpItem`します。</span><span class="sxs-lookup"><span data-stu-id="7f5a5-113">[ICLRErrorReportingManager::BeginCustomDump](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-begincustomdump-method.md) takes a parameter of type `CustomDumpItem`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7f5a5-114">必要条件</span><span class="sxs-lookup"><span data-stu-id="7f5a5-114">Requirements</span></span>  
 <span data-ttu-id="7f5a5-115">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="7f5a5-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7f5a5-116">**ヘッダー:** MSCorEE.idl</span><span class="sxs-lookup"><span data-stu-id="7f5a5-116">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="7f5a5-117">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="7f5a5-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="7f5a5-118">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="7f5a5-118">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="7f5a5-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="7f5a5-119">See also</span></span>

- [<span data-ttu-id="7f5a5-120">ホスト構造体</span><span class="sxs-lookup"><span data-stu-id="7f5a5-120">Hosting Structures</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)
