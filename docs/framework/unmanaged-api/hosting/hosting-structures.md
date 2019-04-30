---
title: ホスト構造体
ms.date: 03/30/2017
helpviewer_keywords:
- hosting structures [.NET Framework]
- unmanaged structures [.NET Framework], hosting
- structures [.NET Framework hosting]
ms.assetid: 492e010f-7493-4134-9505-f7008ccdaae6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 01b12af8c3c3a2f834827ff14665050e07b31467
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61985596"
---
# <a name="hosting-structures"></a><span data-ttu-id="c89d7-102">ホスト構造体</span><span class="sxs-lookup"><span data-stu-id="c89d7-102">Hosting Structures</span></span>
<span data-ttu-id="c89d7-103">このセクションでは、ホスティング API で使用されるアンマネージ構造体について説明します。</span><span class="sxs-lookup"><span data-stu-id="c89d7-103">This section describes the unmanaged structures that the hosting API uses.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c89d7-104">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="c89d7-104">In This Section</span></span>  
 [<span data-ttu-id="c89d7-105">AssemblyBindInfo 構造体</span><span class="sxs-lookup"><span data-stu-id="c89d7-105">AssemblyBindInfo Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/assemblybindinfo-structure.md)  
 <span data-ttu-id="c89d7-106">参照アセンブリに関する詳細情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="c89d7-106">Provides detailed information about the referenced assembly.</span></span>  
  
 [<span data-ttu-id="c89d7-107">BucketParameters 構造体</span><span class="sxs-lookup"><span data-stu-id="c89d7-107">BucketParameters Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/bucketparameters-structure.md)  
 <span data-ttu-id="c89d7-108">イベントに関連付けられている現在の例外のイベントと、パラメーターの型名を格納します。</span><span class="sxs-lookup"><span data-stu-id="c89d7-108">Stores the type name of an event and the parameters for the current exception that is associated with the event.</span></span>  
  
 [<span data-ttu-id="c89d7-109">COR_GC_STATS 構造体</span><span class="sxs-lookup"><span data-stu-id="c89d7-109">COR_GC_STATS Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md)  
 <span data-ttu-id="c89d7-110">共通言語ランタイム (CLR) のガベージ コレクションのメカニズムについての統計情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="c89d7-110">Provides statistics about the garbage collection mechanism of the common language runtime (CLR).</span></span>  
  
 [<span data-ttu-id="c89d7-111">COR_GC_THREAD_STATS 構造体</span><span class="sxs-lookup"><span data-stu-id="c89d7-111">COR_GC_THREAD_STATS Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/cor-gc-thread-stats-structure.md)  
 <span data-ttu-id="c89d7-112">ガベージ コレクションに関連するスレッドごとの統計情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="c89d7-112">Contains per-thread statistics pertaining to garbage collection.</span></span>  
  
 [<span data-ttu-id="c89d7-113">CustomDumpItem 構造体</span><span class="sxs-lookup"><span data-stu-id="c89d7-113">CustomDumpItem Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/customdumpitem-structure.md)  
 <span data-ttu-id="c89d7-114">エラー報告でのカスタム ダンプに追加する項目をについて説明します。</span><span class="sxs-lookup"><span data-stu-id="c89d7-114">Describes an item to be added to a custom dump in error reporting.</span></span>  
  
 [<span data-ttu-id="c89d7-115">MDAInfo 構造体</span><span class="sxs-lookup"><span data-stu-id="c89d7-115">MDAInfo Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/mdainfo-structure.md)  
 <span data-ttu-id="c89d7-116">詳細について説明します、 `Event_MDAFired` 、マネージ デバッグ アシスタント (MDA) の作成をトリガーするイベントです。</span><span class="sxs-lookup"><span data-stu-id="c89d7-116">Provides details about the `Event_MDAFired` event, which triggers the creation of a managed debugging assistant (MDA).</span></span>  
  
 [<span data-ttu-id="c89d7-117">ModuleBindInfo 構造体</span><span class="sxs-lookup"><span data-stu-id="c89d7-117">ModuleBindInfo Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/modulebindinfo-structure.md)  
 <span data-ttu-id="c89d7-118">参照されるモジュールとそれを含んでいるアセンブリに関する詳細情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="c89d7-118">Provides detailed information about the referenced module and the assembly that contains it.</span></span>  
  
 [<span data-ttu-id="c89d7-119">StackOverflowInfo 構造体</span><span class="sxs-lookup"><span data-stu-id="c89d7-119">StackOverflowInfo Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/stackoverflowinfo-structure.md)  
 <span data-ttu-id="c89d7-120">オーバーフローによりスローされた例外でオーバーフローが発生しましたが、情報の種類を格納します。</span><span class="sxs-lookup"><span data-stu-id="c89d7-120">Stores the type of overflow that occurred and information on the exception that was thrown due to the overflow.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="c89d7-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="c89d7-121">Related Sections</span></span>  
 [<span data-ttu-id="c89d7-122">ホスト コクラス</span><span class="sxs-lookup"><span data-stu-id="c89d7-122">Hosting Coclasses</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-coclasses.md)  
  
 [<span data-ttu-id="c89d7-123">ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c89d7-123">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
  
 [<span data-ttu-id="c89d7-124">非推奨の CLR ホスト関数</span><span class="sxs-lookup"><span data-stu-id="c89d7-124">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)  
  
 [<span data-ttu-id="c89d7-125">ホスティングの列挙型</span><span class="sxs-lookup"><span data-stu-id="c89d7-125">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
