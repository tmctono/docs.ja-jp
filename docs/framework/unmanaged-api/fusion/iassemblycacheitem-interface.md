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
ms.openlocfilehash: 193604068e379d62107b25f2bc348cd7c8bc6e98
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796712"
---
# <a name="iassemblycacheitem-interface"></a><span data-ttu-id="3130d-102">IAssemblyCacheItem インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3130d-102">IAssemblyCacheItem Interface</span></span>
<span data-ttu-id="3130d-103">グローバルアセンブリキャッシュ内の1つのアセンブリを表します。</span><span class="sxs-lookup"><span data-stu-id="3130d-103">Represents a single assembly in the global assembly cache.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3130d-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="3130d-104">Methods</span></span>  
  
|<span data-ttu-id="3130d-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="3130d-105">Method</span></span>|<span data-ttu-id="3130d-106">説明</span><span class="sxs-lookup"><span data-stu-id="3130d-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3130d-107">AbortItem メソッド</span><span class="sxs-lookup"><span data-stu-id="3130d-107">AbortItem Method</span></span>](iassemblycacheitem-abortitem-method.md)|<span data-ttu-id="3130d-108">アセンブリが解放される前に、グローバルアセンブリキャッシュ内のアセンブリでクリーンアップ操作を実行できるようにします。</span><span class="sxs-lookup"><span data-stu-id="3130d-108">Allows the assembly in the global assembly cache to perform cleanup operations before it is released.</span></span>|  
|[<span data-ttu-id="3130d-109">Commit メソッド</span><span class="sxs-lookup"><span data-stu-id="3130d-109">Commit Method</span></span>](iassemblycacheitem-commit-method.md)|<span data-ttu-id="3130d-110">キャッシュされたアセンブリ参照をメモリにコミットします。</span><span class="sxs-lookup"><span data-stu-id="3130d-110">Commits the cached assembly reference to memory.</span></span>|  
|[<span data-ttu-id="3130d-111">CreateStream メソッド</span><span class="sxs-lookup"><span data-stu-id="3130d-111">CreateStream Method</span></span>](iassemblycacheitem-createstream-method.md)|<span data-ttu-id="3130d-112">指定された名前と形式を使用してストリームを作成します。</span><span class="sxs-lookup"><span data-stu-id="3130d-112">Creates a stream with the specified name and format.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="3130d-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="3130d-113">Requirements</span></span>  
 <span data-ttu-id="3130d-114">**・** [システム要件](../../get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3130d-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3130d-115">**ヘッダー:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="3130d-115">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="3130d-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3130d-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3130d-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="3130d-117">See also</span></span>

- [<span data-ttu-id="3130d-118">Fusion インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3130d-118">Fusion Interfaces</span></span>](fusion-interfaces.md)
- [<span data-ttu-id="3130d-119">グローバル アセンブリ キャッシュ</span><span class="sxs-lookup"><span data-stu-id="3130d-119">Global Assembly Cache</span></span>](../../app-domains/gac.md)
- [<span data-ttu-id="3130d-120">IAssemblyCache インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3130d-120">IAssemblyCache Interface</span></span>](iassemblycache-interface.md)
