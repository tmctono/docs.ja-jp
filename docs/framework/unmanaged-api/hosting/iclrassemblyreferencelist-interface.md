---
title: ICLRAssemblyReferenceList インターフェイス
ms.date: 03/30/2017
api_name:
- ICLRAssemblyReferenceList
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAssemblyReferenceList
helpviewer_keywords:
- ICLRAssemblyReferenceList interface [.NET Framework hosting]
ms.assetid: 5f890fdf-d22a-429e-a35f-135273d1a636
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 43c40e833e3a250239e9e90667196a2a74a96e0b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61969963"
---
# <a name="iclrassemblyreferencelist-interface"></a><span data-ttu-id="e5e28-102">ICLRAssemblyReferenceList インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e5e28-102">ICLRAssemblyReferenceList Interface</span></span>
<span data-ttu-id="e5e28-103">共通言語ランタイム (CLR) では、ホストではなくに読み込まれるアセンブリの一覧を管理します。</span><span class="sxs-lookup"><span data-stu-id="e5e28-103">Manages a list of assemblies that are loaded by the common language runtime (CLR) and not by the host.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e5e28-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="e5e28-104">Methods</span></span>  
  
|<span data-ttu-id="e5e28-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="e5e28-105">Method</span></span>|<span data-ttu-id="e5e28-106">説明</span><span class="sxs-lookup"><span data-stu-id="e5e28-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e5e28-107">IsAssemblyReferenceInList メソッド</span><span class="sxs-lookup"><span data-stu-id="e5e28-107">IsAssemblyReferenceInList Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-isassemblyreferenceinlist-method.md)|<span data-ttu-id="e5e28-108">指定されたポインターが、リスト内のアセンブリを参照するかどうかを示す値を取得します。</span><span class="sxs-lookup"><span data-stu-id="e5e28-108">Gets a value that indicates whether the supplied pointer references an assembly in the list.</span></span>|  
|[<span data-ttu-id="e5e28-109">IsStringAssemblyReferenceInList メソッド</span><span class="sxs-lookup"><span data-stu-id="e5e28-109">IsStringAssemblyReferenceInList Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-isstringassemblyreferenceinlist-method.md)|<span data-ttu-id="e5e28-110">指定された名前が一覧内のアセンブリの名前と一致するかどうかを示す値を取得します。</span><span class="sxs-lookup"><span data-stu-id="e5e28-110">Gets a value that indicates whether the supplied name matches the name of an assembly in the list.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e5e28-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="e5e28-111">Remarks</span></span>  
 <span data-ttu-id="e5e28-112">呼び出す、 [iclrassemblyidentitymanager::getclrassemblyreferencelist](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getclrassemblyreferencelist-method.md)のインスタンスへのポインターを取得するメソッドを`ICLRAssemblyReferenceList`します。</span><span class="sxs-lookup"><span data-stu-id="e5e28-112">Call the [ICLRAssemblyIdentityManager::GetCLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getclrassemblyreferencelist-method.md) method to get a pointer to an instance of `ICLRAssemblyReferenceList`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e5e28-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="e5e28-113">Requirements</span></span>  
 <span data-ttu-id="e5e28-114">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e5e28-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e5e28-115">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="e5e28-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e5e28-116">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="e5e28-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e5e28-117">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e5e28-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5e28-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="e5e28-118">See also</span></span>

- [<span data-ttu-id="e5e28-119">ICLRAssemblyIdentityManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e5e28-119">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="e5e28-120">IHostAssemblyStore インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e5e28-120">IHostAssemblyStore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
- [<span data-ttu-id="e5e28-121">ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e5e28-121">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
