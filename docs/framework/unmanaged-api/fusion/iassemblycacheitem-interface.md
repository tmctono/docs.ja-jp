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
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59188553"
---
# <a name="iassemblycacheitem-interface"></a><span data-ttu-id="41d96-102">IAssemblyCacheItem インターフェイス</span><span class="sxs-lookup"><span data-stu-id="41d96-102">IAssemblyCacheItem Interface</span></span>
<span data-ttu-id="41d96-103">グローバル アセンブリ キャッシュ内の 1 つのアセンブリを表します。</span><span class="sxs-lookup"><span data-stu-id="41d96-103">Represents a single assembly in the global assembly cache.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="41d96-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="41d96-104">Methods</span></span>  
  
|<span data-ttu-id="41d96-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="41d96-105">Method</span></span>|<span data-ttu-id="41d96-106">説明</span><span class="sxs-lookup"><span data-stu-id="41d96-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="41d96-107">AbortItem メソッド</span><span class="sxs-lookup"><span data-stu-id="41d96-107">AbortItem Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-abortitem-method.md)|<span data-ttu-id="41d96-108">リリースされる前に、クリーンアップ操作を実行する、グローバル アセンブリ キャッシュにアセンブリを使用します。</span><span class="sxs-lookup"><span data-stu-id="41d96-108">Allows the assembly in the global assembly cache to perform cleanup operations before it is released.</span></span>|  
|[<span data-ttu-id="41d96-109">Commit メソッド</span><span class="sxs-lookup"><span data-stu-id="41d96-109">Commit Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-commit-method.md)|<span data-ttu-id="41d96-110">メモリにキャッシュされたアセンブリ参照をコミットします。</span><span class="sxs-lookup"><span data-stu-id="41d96-110">Commits the cached assembly reference to memory.</span></span>|  
|[<span data-ttu-id="41d96-111">CreateStream メソッド</span><span class="sxs-lookup"><span data-stu-id="41d96-111">CreateStream Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-createstream-method.md)|<span data-ttu-id="41d96-112">指定した名前と形式を使用するストリームを作成します。</span><span class="sxs-lookup"><span data-stu-id="41d96-112">Creates a stream with the specified name and format.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="41d96-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="41d96-113">Requirements</span></span>  
 <span data-ttu-id="41d96-114">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="41d96-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="41d96-115">**ヘッダー:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="41d96-115">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="41d96-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="41d96-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41d96-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="41d96-117">See also</span></span>

- [<span data-ttu-id="41d96-118">Fusion インターフェイス</span><span class="sxs-lookup"><span data-stu-id="41d96-118">Fusion Interfaces</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)
- [<span data-ttu-id="41d96-119">グローバル アセンブリ キャッシュ</span><span class="sxs-lookup"><span data-stu-id="41d96-119">Global Assembly Cache</span></span>](../../../../docs/framework/app-domains/gac.md)
- [<span data-ttu-id="41d96-120">IAssemblyCache インターフェイス</span><span class="sxs-lookup"><span data-stu-id="41d96-120">IAssemblyCache Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-interface.md)
