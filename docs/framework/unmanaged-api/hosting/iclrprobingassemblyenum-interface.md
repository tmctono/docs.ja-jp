---
title: ICLRProbingAssemblyEnum インターフェイス
ms.date: 03/30/2017
api_name:
- ICLRProbingAssemblyEnum
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRProbingAssemblyEnum
helpviewer_keywords:
- ICLRProbingAssemblyEnum interface [.NET Framework hosting]
ms.assetid: e7d3ccab-b0f0-4872-8935-0ed72920171b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 118345f246de3d7ee68d51cf37e8cdea9de1fdba
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61638529"
---
# <a name="iclrprobingassemblyenum-interface"></a><span data-ttu-id="06963-102">ICLRProbingAssemblyEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="06963-102">ICLRProbingAssemblyEnum Interface</span></span>
<span data-ttu-id="06963-103">ホストを作成し、その id を理解したりしなくても、共通言語ランタイム (CLR) 内部にあるアセンブリの id 情報を使用してアセンブリのプローブの id を取得できるようにするメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="06963-103">Provides methods that enable the host to get the probing identities of an assembly by using the assembly's identity information that is internal to the common language runtime (CLR), without needing to create or understand that identity.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="06963-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="06963-104">Methods</span></span>  
  
|<span data-ttu-id="06963-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="06963-105">Method</span></span>|<span data-ttu-id="06963-106">説明</span><span class="sxs-lookup"><span data-stu-id="06963-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="06963-107">Get メソッド</span><span class="sxs-lookup"><span data-stu-id="06963-107">Get Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrprobingassemblyenum-get-method.md)|<span data-ttu-id="06963-108">指定したインデックス位置には、アセンブリの id を取得します。</span><span class="sxs-lookup"><span data-stu-id="06963-108">Gets the assembly identity at the specified index.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="06963-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="06963-109">Remarks</span></span>  
 <span data-ttu-id="06963-110">などのメソッド[iclrassemblyidentitymanager::getprobingassembliesfromreference](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getprobingassembliesfromreference-method.md)を返す、`ICLRProbingAssemblyEnum`インスタンス。</span><span class="sxs-lookup"><span data-stu-id="06963-110">Methods such as [ICLRAssemblyIdentityManager::GetProbingAssembliesFromReference](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getprobingassembliesfromreference-method.md) return an `ICLRProbingAssemblyEnum` instance.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="06963-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="06963-111">Requirements</span></span>  
 <span data-ttu-id="06963-112">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="06963-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="06963-113">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="06963-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="06963-114">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="06963-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="06963-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="06963-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06963-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="06963-116">See also</span></span>

- [<span data-ttu-id="06963-117">ICLRAssemblyIdentityManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="06963-117">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="06963-118">ICLRAssemblyReferenceList インターフェイス</span><span class="sxs-lookup"><span data-stu-id="06963-118">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="06963-119">ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="06963-119">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
