---
title: ICLRReferenceAssemblyEnum インターフェイス
ms.date: 03/30/2017
api_name:
- ICLRReferenceAssemblyEnum
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRReferenceAssemblyEnum
helpviewer_keywords:
- ICLRReferenceAssemblyEnum interface [.NET Framework hosting]
ms.assetid: 8adbf092-c3ba-4bee-b25b-0de6e43a4ce5
topic_type:
- apiref
ms.openlocfilehash: 9797c419251127ef07a8c2bee22132c3c2b82e36
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703317"
---
# <a name="iclrreferenceassemblyenum-interface"></a><span data-ttu-id="07d45-102">ICLRReferenceAssemblyEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="07d45-102">ICLRReferenceAssemblyEnum Interface</span></span>
<span data-ttu-id="07d45-103">共通言語ランタイム (CLR) の内部にあるアセンブリ id データを使用して、ファイルまたはストリームによって参照されるアセンブリのセットをホストが操作できるようにするメソッドを提供します。これらの id を作成したり、理解したりする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="07d45-103">Provides methods that allow the host to manipulate the set of assemblies referenced by a file or stream using assembly identity data that is internal to the common language runtime (CLR), without needing to create or understand those identities.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="07d45-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="07d45-104">Methods</span></span>  
  
|<span data-ttu-id="07d45-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="07d45-105">Method</span></span>|<span data-ttu-id="07d45-106">説明</span><span class="sxs-lookup"><span data-stu-id="07d45-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="07d45-107">Get メソッド</span><span class="sxs-lookup"><span data-stu-id="07d45-107">Get Method</span></span>](iclrreferenceassemblyenum-get-method.md)|<span data-ttu-id="07d45-108">指定されたインデックス位置にあるアセンブリ id を取得します。</span><span class="sxs-lookup"><span data-stu-id="07d45-108">Gets the assembly identity at the supplied index.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="07d45-109">要件</span><span class="sxs-lookup"><span data-stu-id="07d45-109">Requirements</span></span>  
 <span data-ttu-id="07d45-110">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="07d45-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="07d45-111">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="07d45-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="07d45-112">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="07d45-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="07d45-113">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="07d45-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07d45-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="07d45-114">See also</span></span>

- [<span data-ttu-id="07d45-115">ICLRAssemblyIdentityManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="07d45-115">ICLRAssemblyIdentityManager Interface</span></span>](iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="07d45-116">ICLRAssemblyReferenceList インターフェイス</span><span class="sxs-lookup"><span data-stu-id="07d45-116">ICLRAssemblyReferenceList Interface</span></span>](iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="07d45-117">ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="07d45-117">Hosting Interfaces</span></span>](hosting-interfaces.md)
