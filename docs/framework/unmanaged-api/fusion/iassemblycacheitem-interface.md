---
title: IAssemblyCacheItem インターフェイス
ms.date: 03/30/2017
api_name:
- IAssemblyCacheItem
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyCacheItem
helpviewer_keywords:
- IAssemblyCacheItem interface [.NET Framework fusion]
ms.assetid: ccc9387a-9f44-4f4f-bf8f-0ea6d2afa21b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fba17a2ffad9220acdbc79726efe0d3d4184978a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61697980"
---
# <a name="iassemblycacheitem-interface"></a><span data-ttu-id="bafff-102">IAssemblyCacheItem インターフェイス</span><span class="sxs-lookup"><span data-stu-id="bafff-102">IAssemblyCacheItem Interface</span></span>
<span data-ttu-id="bafff-103">グローバル アセンブリ キャッシュ内の 1 つのアセンブリを表します。</span><span class="sxs-lookup"><span data-stu-id="bafff-103">Represents a single assembly in the global assembly cache.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="bafff-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="bafff-104">Methods</span></span>  
  
|<span data-ttu-id="bafff-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="bafff-105">Method</span></span>|<span data-ttu-id="bafff-106">説明</span><span class="sxs-lookup"><span data-stu-id="bafff-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="bafff-107">AbortItem メソッド</span><span class="sxs-lookup"><span data-stu-id="bafff-107">AbortItem Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-abortitem-method.md)|<span data-ttu-id="bafff-108">リリースされる前に、クリーンアップ操作を実行する、グローバル アセンブリ キャッシュにアセンブリを使用します。</span><span class="sxs-lookup"><span data-stu-id="bafff-108">Allows the assembly in the global assembly cache to perform cleanup operations before it is released.</span></span>|  
|[<span data-ttu-id="bafff-109">Commit メソッド</span><span class="sxs-lookup"><span data-stu-id="bafff-109">Commit Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-commit-method.md)|<span data-ttu-id="bafff-110">メモリにキャッシュされたアセンブリ参照をコミットします。</span><span class="sxs-lookup"><span data-stu-id="bafff-110">Commits the cached assembly reference to memory.</span></span>|  
|[<span data-ttu-id="bafff-111">CreateStream メソッド</span><span class="sxs-lookup"><span data-stu-id="bafff-111">CreateStream Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-createstream-method.md)|<span data-ttu-id="bafff-112">指定した名前と形式を使用するストリームを作成します。</span><span class="sxs-lookup"><span data-stu-id="bafff-112">Creates a stream with the specified name and format.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="bafff-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="bafff-113">Requirements</span></span>  
 <span data-ttu-id="bafff-114">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="bafff-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bafff-115">**ヘッダー:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="bafff-115">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="bafff-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bafff-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bafff-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="bafff-117">See also</span></span>

- [<span data-ttu-id="bafff-118">Fusion インターフェイス</span><span class="sxs-lookup"><span data-stu-id="bafff-118">Fusion Interfaces</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)
- [<span data-ttu-id="bafff-119">グローバル アセンブリ キャッシュ</span><span class="sxs-lookup"><span data-stu-id="bafff-119">Global Assembly Cache</span></span>](../../../../docs/framework/app-domains/gac.md)
- [<span data-ttu-id="bafff-120">IAssemblyCache インターフェイス</span><span class="sxs-lookup"><span data-stu-id="bafff-120">IAssemblyCache Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-interface.md)
