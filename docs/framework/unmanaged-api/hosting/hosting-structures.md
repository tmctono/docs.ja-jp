---
title: ホスト構造体
ms.date: 03/30/2017
helpviewer_keywords:
- hosting structures [.NET Framework]
- unmanaged structures [.NET Framework], hosting
- structures [.NET Framework hosting]
ms.assetid: 492e010f-7493-4134-9505-f7008ccdaae6
ms.openlocfilehash: 3d43225574b8794733ee2e83562699276ddc5bab
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73126938"
---
# <a name="hosting-structures"></a><span data-ttu-id="da402-102">ホスト構造体</span><span class="sxs-lookup"><span data-stu-id="da402-102">Hosting Structures</span></span>
<span data-ttu-id="da402-103">このセクションでは、ホスティング API が使用するアンマネージ構造体について説明します。</span><span class="sxs-lookup"><span data-stu-id="da402-103">This section describes the unmanaged structures that the hosting API uses.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="da402-104">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="da402-104">In This Section</span></span>  
 [<span data-ttu-id="da402-105">AssemblyBindInfo 構造体</span><span class="sxs-lookup"><span data-stu-id="da402-105">AssemblyBindInfo Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/assemblybindinfo-structure.md)  
 <span data-ttu-id="da402-106">参照アセンブリに関する詳細情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="da402-106">Provides detailed information about the referenced assembly.</span></span>  
  
 [<span data-ttu-id="da402-107">BucketParameters 構造体</span><span class="sxs-lookup"><span data-stu-id="da402-107">BucketParameters Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/bucketparameters-structure.md)  
 <span data-ttu-id="da402-108">イベントの型名と、イベントに関連付けられている現在の例外のパラメーターを格納します。</span><span class="sxs-lookup"><span data-stu-id="da402-108">Stores the type name of an event and the parameters for the current exception that is associated with the event.</span></span>  
  
 [<span data-ttu-id="da402-109">COR_GC_STATS 構造体</span><span class="sxs-lookup"><span data-stu-id="da402-109">COR_GC_STATS Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md)  
 <span data-ttu-id="da402-110">共通言語ランタイム (CLR) のガベージコレクション機構に関する統計情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="da402-110">Provides statistics about the garbage collection mechanism of the common language runtime (CLR).</span></span>  
  
 [<span data-ttu-id="da402-111">COR_GC_THREAD_STATS 構造体</span><span class="sxs-lookup"><span data-stu-id="da402-111">COR_GC_THREAD_STATS Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/cor-gc-thread-stats-structure.md)  
 <span data-ttu-id="da402-112">ガベージコレクションに関連するスレッドごとの統計情報を格納します。</span><span class="sxs-lookup"><span data-stu-id="da402-112">Contains per-thread statistics pertaining to garbage collection.</span></span>  
  
 [<span data-ttu-id="da402-113">CustomDumpItem 構造体</span><span class="sxs-lookup"><span data-stu-id="da402-113">CustomDumpItem Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/customdumpitem-structure.md)  
 <span data-ttu-id="da402-114">エラー報告のカスタムダンプに追加するアイテムについて説明します。</span><span class="sxs-lookup"><span data-stu-id="da402-114">Describes an item to be added to a custom dump in error reporting.</span></span>  
  
 [<span data-ttu-id="da402-115">MDAInfo 構造体</span><span class="sxs-lookup"><span data-stu-id="da402-115">MDAInfo Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/mdainfo-structure.md)  
 <span data-ttu-id="da402-116">マネージデバッグアシスタント (MDA) の作成をトリガーする `Event_MDAFired` イベントについて詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="da402-116">Provides details about the `Event_MDAFired` event, which triggers the creation of a managed debugging assistant (MDA).</span></span>  
  
 [<span data-ttu-id="da402-117">ModuleBindInfo 構造体</span><span class="sxs-lookup"><span data-stu-id="da402-117">ModuleBindInfo Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/modulebindinfo-structure.md)  
 <span data-ttu-id="da402-118">参照されるモジュールとそれを含むアセンブリに関する詳細情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="da402-118">Provides detailed information about the referenced module and the assembly that contains it.</span></span>  
  
 [<span data-ttu-id="da402-119">StackOverflowInfo 構造体</span><span class="sxs-lookup"><span data-stu-id="da402-119">StackOverflowInfo Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/stackoverflowinfo-structure.md)  
 <span data-ttu-id="da402-120">発生したオーバーフローの種類とオーバーフローによってスローされた例外に関する情報を格納します。</span><span class="sxs-lookup"><span data-stu-id="da402-120">Stores the type of overflow that occurred and information on the exception that was thrown due to the overflow.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="da402-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="da402-121">Related Sections</span></span>  
 [<span data-ttu-id="da402-122">ホスト コクラス</span><span class="sxs-lookup"><span data-stu-id="da402-122">Hosting Coclasses</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-coclasses.md)  
  
 [<span data-ttu-id="da402-123">ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="da402-123">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
  
 [<span data-ttu-id="da402-124">非推奨の CLR ホスト関数</span><span class="sxs-lookup"><span data-stu-id="da402-124">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)  
  
 [<span data-ttu-id="da402-125">ホスティングの列挙型</span><span class="sxs-lookup"><span data-stu-id="da402-125">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
