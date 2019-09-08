---
title: IAssemblyCache インターフェイス
ms.date: 03/30/2017
api_name:
- IAssemblyCache
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyCache
helpviewer_keywords:
- IAssemblyCache interface [.NET Framework fusion]
ms.assetid: 71ea170f-872d-4fc5-81b6-27da1dec9b19
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6dab5fe941fce3c23ba718906b29c80c6d257c2f
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796770"
---
# <a name="iassemblycache-interface"></a><span data-ttu-id="44c4d-102">IAssemblyCache インターフェイス</span><span class="sxs-lookup"><span data-stu-id="44c4d-102">IAssemblyCache Interface</span></span>
<span data-ttu-id="44c4d-103">Fusion テクノロジによって使用されるグローバルアセンブリキャッシュを表します。</span><span class="sxs-lookup"><span data-stu-id="44c4d-103">Represents the global assembly cache for use by the fusion technology.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="44c4d-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="44c4d-104">Methods</span></span>  
  
|<span data-ttu-id="44c4d-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="44c4d-105">Method</span></span>|<span data-ttu-id="44c4d-106">説明</span><span class="sxs-lookup"><span data-stu-id="44c4d-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="44c4d-107">CreateAssemblyCacheItem メソッド</span><span class="sxs-lookup"><span data-stu-id="44c4d-107">CreateAssemblyCacheItem Method</span></span>](iassemblycache-createassemblycacheitem-method.md)|<span data-ttu-id="44c4d-108">新しい[Iassemblycacheitem](iassemblycacheitem-interface.md)への参照を取得します。</span><span class="sxs-lookup"><span data-stu-id="44c4d-108">Gets a reference to a new [IAssemblyCacheItem](iassemblycacheitem-interface.md).</span></span>|  
|[<span data-ttu-id="44c4d-109">CreateAssemblyScavenger メソッド</span><span class="sxs-lookup"><span data-stu-id="44c4d-109">CreateAssemblyScavenger Method</span></span>](iassemblycache-createassemblyscavenger-method.md)|<span data-ttu-id="44c4d-110">Fusion テクノロジによる内部使用のために予約されています。</span><span class="sxs-lookup"><span data-stu-id="44c4d-110">Reserved for internal use by the fusion technology.</span></span>|  
|[<span data-ttu-id="44c4d-111">InstallAssembly メソッド</span><span class="sxs-lookup"><span data-stu-id="44c4d-111">InstallAssembly Method</span></span>](iassemblycache-installassembly-method.md)|<span data-ttu-id="44c4d-112">指定したアセンブリをグローバルアセンブリキャッシュにインストールします。</span><span class="sxs-lookup"><span data-stu-id="44c4d-112">Installs the specified assembly in the global assembly cache.</span></span>|  
|[<span data-ttu-id="44c4d-113">QueryAssemblyInfo メソッド</span><span class="sxs-lookup"><span data-stu-id="44c4d-113">QueryAssemblyInfo Method</span></span>](iassemblycache-queryassemblyinfo-method.md)|<span data-ttu-id="44c4d-114">指定したアセンブリに関する要求されたデータを取得します。</span><span class="sxs-lookup"><span data-stu-id="44c4d-114">Gets the requested data about the specified assembly.</span></span>|  
|[<span data-ttu-id="44c4d-115">UninstallAssembly メソッド</span><span class="sxs-lookup"><span data-stu-id="44c4d-115">UninstallAssembly Method</span></span>](iassemblycache-uninstallassembly-method.md)|<span data-ttu-id="44c4d-116">指定したアセンブリをグローバルアセンブリキャッシュからアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="44c4d-116">Uninstalls the specified assembly from the global assembly cache.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="44c4d-117">必要条件</span><span class="sxs-lookup"><span data-stu-id="44c4d-117">Requirements</span></span>  
 <span data-ttu-id="44c4d-118">**・** [システム要件](../../get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="44c4d-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="44c4d-119">**ヘッダー:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="44c4d-119">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="44c4d-120">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="44c4d-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44c4d-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="44c4d-121">See also</span></span>

- [<span data-ttu-id="44c4d-122">Fusion インターフェイス</span><span class="sxs-lookup"><span data-stu-id="44c4d-122">Fusion Interfaces</span></span>](fusion-interfaces.md)
- [<span data-ttu-id="44c4d-123">グローバル アセンブリ キャッシュ</span><span class="sxs-lookup"><span data-stu-id="44c4d-123">Global Assembly Cache</span></span>](../../app-domains/gac.md)
