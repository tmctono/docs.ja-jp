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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 32f27d6c15a99282eee20d2563a4ca741238d846
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61638516"
---
# <a name="iclrreferenceassemblyenum-interface"></a><span data-ttu-id="cc666-102">ICLRReferenceAssemblyEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="cc666-102">ICLRReferenceAssemblyEnum Interface</span></span>
<span data-ttu-id="cc666-103">ホスト ファイルまたはアセンブリの id データを作成し、それらの id を理解したりしなくても、共通言語ランタイム (CLR) の内部を使用してストリームによって参照されるアセンブリのセットを操作できるようにするメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="cc666-103">Provides methods that allow the host to manipulate the set of assemblies referenced by a file or stream using assembly identity data that is internal to the common language runtime (CLR), without needing to create or understand those identities.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="cc666-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="cc666-104">Methods</span></span>  
  
|<span data-ttu-id="cc666-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="cc666-105">Method</span></span>|<span data-ttu-id="cc666-106">説明</span><span class="sxs-lookup"><span data-stu-id="cc666-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="cc666-107">Get メソッド</span><span class="sxs-lookup"><span data-stu-id="cc666-107">Get Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrreferenceassemblyenum-get-method.md)|<span data-ttu-id="cc666-108">指定したインデックス位置にあるアセンブリの id を取得します。</span><span class="sxs-lookup"><span data-stu-id="cc666-108">Gets the assembly identity at the supplied index.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="cc666-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="cc666-109">Requirements</span></span>  
 <span data-ttu-id="cc666-110">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="cc666-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cc666-111">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="cc666-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="cc666-112">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="cc666-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="cc666-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cc666-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc666-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="cc666-114">See also</span></span>

- [<span data-ttu-id="cc666-115">ICLRAssemblyIdentityManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="cc666-115">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="cc666-116">ICLRAssemblyReferenceList インターフェイス</span><span class="sxs-lookup"><span data-stu-id="cc666-116">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="cc666-117">ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="cc666-117">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
