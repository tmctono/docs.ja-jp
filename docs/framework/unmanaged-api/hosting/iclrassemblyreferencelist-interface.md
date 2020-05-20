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
ms.openlocfilehash: f1aa40ef868bf6ff7730e01ab66a6fec58af1196
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615879"
---
# <a name="iclrassemblyreferencelist-interface"></a><span data-ttu-id="188fe-102">ICLRAssemblyReferenceList インターフェイス</span><span class="sxs-lookup"><span data-stu-id="188fe-102">ICLRAssemblyReferenceList Interface</span></span>
<span data-ttu-id="188fe-103">ホストではなく、共通言語ランタイム (CLR) によって読み込まれるアセンブリの一覧を管理します。</span><span class="sxs-lookup"><span data-stu-id="188fe-103">Manages a list of assemblies that are loaded by the common language runtime (CLR) and not by the host.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="188fe-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="188fe-104">Methods</span></span>  
  
|<span data-ttu-id="188fe-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="188fe-105">Method</span></span>|<span data-ttu-id="188fe-106">説明</span><span class="sxs-lookup"><span data-stu-id="188fe-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="188fe-107">IsAssemblyReferenceInList メソッド</span><span class="sxs-lookup"><span data-stu-id="188fe-107">IsAssemblyReferenceInList Method</span></span>](iclrassemblyreferencelist-isassemblyreferenceinlist-method.md)|<span data-ttu-id="188fe-108">指定されたポインターがリスト内のアセンブリを参照しているかどうかを示す値を取得します。</span><span class="sxs-lookup"><span data-stu-id="188fe-108">Gets a value that indicates whether the supplied pointer references an assembly in the list.</span></span>|  
|[<span data-ttu-id="188fe-109">IsStringAssemblyReferenceInList メソッド</span><span class="sxs-lookup"><span data-stu-id="188fe-109">IsStringAssemblyReferenceInList Method</span></span>](iclrassemblyreferencelist-isstringassemblyreferenceinlist-method.md)|<span data-ttu-id="188fe-110">指定された名前がリスト内のアセンブリの名前と一致するかどうかを示す値を取得します。</span><span class="sxs-lookup"><span data-stu-id="188fe-110">Gets a value that indicates whether the supplied name matches the name of an assembly in the list.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="188fe-111">解説</span><span class="sxs-lookup"><span data-stu-id="188fe-111">Remarks</span></span>  
 <span data-ttu-id="188fe-112">[ICLRAssemblyIdentityManager:: GetCLRAssemblyReferenceList](iclrassemblyidentitymanager-getclrassemblyreferencelist-method.md)メソッドを呼び出して、のインスタンスへのポインターを取得 `ICLRAssemblyReferenceList` します。</span><span class="sxs-lookup"><span data-stu-id="188fe-112">Call the [ICLRAssemblyIdentityManager::GetCLRAssemblyReferenceList](iclrassemblyidentitymanager-getclrassemblyreferencelist-method.md) method to get a pointer to an instance of `ICLRAssemblyReferenceList`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="188fe-113">要件</span><span class="sxs-lookup"><span data-stu-id="188fe-113">Requirements</span></span>  
 <span data-ttu-id="188fe-114">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="188fe-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="188fe-115">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="188fe-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="188fe-116">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="188fe-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="188fe-117">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="188fe-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="188fe-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="188fe-118">See also</span></span>

- [<span data-ttu-id="188fe-119">ICLRAssemblyIdentityManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="188fe-119">ICLRAssemblyIdentityManager Interface</span></span>](iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="188fe-120">IHostAssemblyStore インターフェイス</span><span class="sxs-lookup"><span data-stu-id="188fe-120">IHostAssemblyStore Interface</span></span>](ihostassemblystore-interface.md)
- [<span data-ttu-id="188fe-121">ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="188fe-121">Hosting Interfaces</span></span>](hosting-interfaces.md)
