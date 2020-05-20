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
ms.openlocfilehash: 5c77a332593ba470d2e29b87cba182a770d5db7e
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616438"
---
# <a name="customdumpitem-structure"></a><span data-ttu-id="ecfb1-102">CustomDumpItem 構造体</span><span class="sxs-lookup"><span data-stu-id="ecfb1-102">CustomDumpItem Structure</span></span>
<span data-ttu-id="ecfb1-103">エラー報告のカスタムダンプに追加するアイテムについて説明します。</span><span class="sxs-lookup"><span data-stu-id="ecfb1-103">Describes an item to be added to a custom dump in error reporting.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ecfb1-104">構文</span><span class="sxs-lookup"><span data-stu-id="ecfb1-104">Syntax</span></span>  
  
```cpp  
struct {  
    ECustomDumpItemKind itemKind;
    union {  
        UINT_PTR pReserved;  
    }  
} CustomDumpItem;  
```  
  
## <a name="members"></a><span data-ttu-id="ecfb1-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="ecfb1-105">Members</span></span>  
  
|<span data-ttu-id="ecfb1-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="ecfb1-106">Member</span></span>|<span data-ttu-id="ecfb1-107">説明</span><span class="sxs-lookup"><span data-stu-id="ecfb1-107">Description</span></span>|  
|------------|-----------------|  
|`itemKind`|<span data-ttu-id="ecfb1-108">追加する項目の種類を示す[ECustomDumpItemKind](ecustomdumpitemkind-enumeration.md)値。</span><span class="sxs-lookup"><span data-stu-id="ecfb1-108">An [ECustomDumpItemKind](ecustomdumpitemkind-enumeration.md) value that indicates the kind of item to be added.</span></span>|  
|`pReserved`|<span data-ttu-id="ecfb1-109">現在は使用しません。</span><span class="sxs-lookup"><span data-stu-id="ecfb1-109">Not currently used.</span></span> <span data-ttu-id="ecfb1-110">共用体に追加された項目は、ポインターサイズ以下である必要があります。</span><span class="sxs-lookup"><span data-stu-id="ecfb1-110">Any items added to the union must be no larger than pointer size.</span></span> <span data-ttu-id="ecfb1-111">`struct`が必要な場合は、それを個別に割り当てて、それをポイントする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ecfb1-111">If a `struct` is required, you must allocate it separately and point to it.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ecfb1-112">解説</span><span class="sxs-lookup"><span data-stu-id="ecfb1-112">Remarks</span></span>  
 <span data-ttu-id="ecfb1-113">[ICLRErrorReportingManager:: BeginCustomDump](iclrerrorreportingmanager-begincustomdump-method.md)は、型のパラメーターを受け取り `CustomDumpItem` ます。</span><span class="sxs-lookup"><span data-stu-id="ecfb1-113">[ICLRErrorReportingManager::BeginCustomDump](iclrerrorreportingmanager-begincustomdump-method.md) takes a parameter of type `CustomDumpItem`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ecfb1-114">要件</span><span class="sxs-lookup"><span data-stu-id="ecfb1-114">Requirements</span></span>  
 <span data-ttu-id="ecfb1-115">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ecfb1-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ecfb1-116">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="ecfb1-116">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="ecfb1-117">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="ecfb1-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ecfb1-118">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ecfb1-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ecfb1-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="ecfb1-119">See also</span></span>

- [<span data-ttu-id="ecfb1-120">ホスト構造体</span><span class="sxs-lookup"><span data-stu-id="ecfb1-120">Hosting Structures</span></span>](hosting-structures.md)
