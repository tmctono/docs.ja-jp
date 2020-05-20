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
ms.openlocfilehash: e1e114070f39e75254fc1bc0f8c1bf3e4733d5a2
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703378"
---
# <a name="iclrprobingassemblyenum-interface"></a><span data-ttu-id="6e923-102">ICLRProbingAssemblyEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6e923-102">ICLRProbingAssemblyEnum Interface</span></span>
<span data-ttu-id="6e923-103">共通言語ランタイム (CLR) の内部にあるアセンブリの id 情報を使用して、ホストがアセンブリのプローブ id を取得できるようにするメソッドを提供します。このメソッドは、その id を作成または理解する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="6e923-103">Provides methods that enable the host to get the probing identities of an assembly by using the assembly's identity information that is internal to the common language runtime (CLR), without needing to create or understand that identity.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="6e923-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="6e923-104">Methods</span></span>  
  
|<span data-ttu-id="6e923-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="6e923-105">Method</span></span>|<span data-ttu-id="6e923-106">説明</span><span class="sxs-lookup"><span data-stu-id="6e923-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="6e923-107">Get メソッド</span><span class="sxs-lookup"><span data-stu-id="6e923-107">Get Method</span></span>](iclrprobingassemblyenum-get-method.md)|<span data-ttu-id="6e923-108">指定したインデックス位置にあるアセンブリ id を取得します。</span><span class="sxs-lookup"><span data-stu-id="6e923-108">Gets the assembly identity at the specified index.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6e923-109">解説</span><span class="sxs-lookup"><span data-stu-id="6e923-109">Remarks</span></span>  
 <span data-ttu-id="6e923-110">[ICLRAssemblyIdentityManager:: GetProbingAssembliesFromReference](iclrassemblyidentitymanager-getprobingassembliesfromreference-method.md)などのメソッドは、 `ICLRProbingAssemblyEnum` インスタンスを返します。</span><span class="sxs-lookup"><span data-stu-id="6e923-110">Methods such as [ICLRAssemblyIdentityManager::GetProbingAssembliesFromReference](iclrassemblyidentitymanager-getprobingassembliesfromreference-method.md) return an `ICLRProbingAssemblyEnum` instance.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6e923-111">要件</span><span class="sxs-lookup"><span data-stu-id="6e923-111">Requirements</span></span>  
 <span data-ttu-id="6e923-112">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6e923-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6e923-113">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="6e923-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6e923-114">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="6e923-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6e923-115">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6e923-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e923-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="6e923-116">See also</span></span>

- [<span data-ttu-id="6e923-117">ICLRAssemblyIdentityManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6e923-117">ICLRAssemblyIdentityManager Interface</span></span>](iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="6e923-118">ICLRAssemblyReferenceList インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6e923-118">ICLRAssemblyReferenceList Interface</span></span>](iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="6e923-119">ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6e923-119">Hosting Interfaces</span></span>](hosting-interfaces.md)
