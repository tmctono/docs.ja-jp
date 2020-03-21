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
ms.openlocfilehash: 154beef9398029f31dcb4d081019b9f292238af4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176475"
---
# <a name="customdumpitem-structure"></a><span data-ttu-id="ea49a-102">CustomDumpItem 構造体</span><span class="sxs-lookup"><span data-stu-id="ea49a-102">CustomDumpItem Structure</span></span>
<span data-ttu-id="ea49a-103">エラー報告でカスタム ダンプに追加する項目を記述します。</span><span class="sxs-lookup"><span data-stu-id="ea49a-103">Describes an item to be added to a custom dump in error reporting.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ea49a-104">構文</span><span class="sxs-lookup"><span data-stu-id="ea49a-104">Syntax</span></span>  
  
```cpp  
struct {  
    ECustomDumpItemKind itemKind;
    union {  
        UINT_PTR pReserved;  
    }  
} CustomDumpItem;  
```  
  
## <a name="members"></a><span data-ttu-id="ea49a-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="ea49a-105">Members</span></span>  
  
|<span data-ttu-id="ea49a-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="ea49a-106">Member</span></span>|<span data-ttu-id="ea49a-107">説明</span><span class="sxs-lookup"><span data-stu-id="ea49a-107">Description</span></span>|  
|------------|-----------------|  
|`itemKind`|<span data-ttu-id="ea49a-108">追加する項目の種類を示す[ECustomDumpItemKind](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpitemkind-enumeration.md)値。</span><span class="sxs-lookup"><span data-stu-id="ea49a-108">An [ECustomDumpItemKind](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpitemkind-enumeration.md) value that indicates the kind of item to be added.</span></span>|  
|`pReserved`|<span data-ttu-id="ea49a-109">現在は使用しません。</span><span class="sxs-lookup"><span data-stu-id="ea49a-109">Not currently used.</span></span> <span data-ttu-id="ea49a-110">共用体に追加される項目は、ポインター・サイズより大きくすることはできません。</span><span class="sxs-lookup"><span data-stu-id="ea49a-110">Any items added to the union must be no larger than pointer size.</span></span> <span data-ttu-id="ea49a-111">が必要`struct`な場合は、個別に割り当ててポイントする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ea49a-111">If a `struct` is required, you must allocate it separately and point to it.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ea49a-112">解説</span><span class="sxs-lookup"><span data-stu-id="ea49a-112">Remarks</span></span>  
 <span data-ttu-id="ea49a-113">[を](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-begincustomdump-method.md)指定`CustomDumpItem`します。</span><span class="sxs-lookup"><span data-stu-id="ea49a-113">[ICLRErrorReportingManager::BeginCustomDump](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-begincustomdump-method.md) takes a parameter of type `CustomDumpItem`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ea49a-114">必要条件</span><span class="sxs-lookup"><span data-stu-id="ea49a-114">Requirements</span></span>  
 <span data-ttu-id="ea49a-115">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ea49a-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ea49a-116">**ヘッダー:** MSCorEE.idl</span><span class="sxs-lookup"><span data-stu-id="ea49a-116">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="ea49a-117">**ライブラリ:** MSCorEE.dll にリソースとして含まれる</span><span class="sxs-lookup"><span data-stu-id="ea49a-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ea49a-118">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ea49a-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea49a-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="ea49a-119">See also</span></span>

- [<span data-ttu-id="ea49a-120">ホスト構造体</span><span class="sxs-lookup"><span data-stu-id="ea49a-120">Hosting Structures</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)
