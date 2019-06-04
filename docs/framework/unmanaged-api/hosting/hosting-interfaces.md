---
title: ホスト インターフェイス
ms.date: 03/30/2017
helpviewer_keywords:
- interfaces [.NET Framework hosting]
- hosting interfaces [.NET Framework]
- unmanaged interfaces [.NET Framework], hosting
ms.assetid: cc64cb05-38da-418e-815a-daac8e8e26e5
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 46ff6032f2cdbd4a5f294198fe3bf71862c67528
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2019
ms.locfileid: "66490246"
---
# <a name="hosting-interfaces"></a><span data-ttu-id="eb13e-102">ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="eb13e-102">Hosting Interfaces</span></span>
<span data-ttu-id="eb13e-103">アンマネージ インターフェイスについて説明をアプリケーションに共通言語ランタイム (CLR) を統合するホストを使用できます。</span><span class="sxs-lookup"><span data-stu-id="eb13e-103">This section describes the interfaces that unmanaged hosts can use to integrate the common language runtime (CLR) into their applications.</span></span>  
  
 <span data-ttu-id="eb13e-104">.NET Framework version 2.0 のホスティング インターフェイスは、.NET Framework version 1.0 および 1.1 のインターフェイスを優先します。</span><span class="sxs-lookup"><span data-stu-id="eb13e-104">The .NET Framework version 2.0 hosting interfaces supersede the .NET Framework version 1.0 and 1.1 interfaces.</span></span> <span data-ttu-id="eb13e-105">2 つのインターフェイスのセット間に大きな違いがあります。</span><span class="sxs-lookup"><span data-stu-id="eb13e-105">There are significant differences between the two sets of interfaces.</span></span> <span data-ttu-id="eb13e-106">両者を混在させると、予期しない動作が発生する可能性があります、お勧めできません。</span><span class="sxs-lookup"><span data-stu-id="eb13e-106">Mixing them could cause unexpected behavior and is not recommended.</span></span>  
  
 <span data-ttu-id="eb13e-107">.NET Framework バージョン 3.0 および 3.5 では、.NET Framework version 2.0 のホスト インターフェイスを使用し、ホスティング機能は導入されません。</span><span class="sxs-lookup"><span data-stu-id="eb13e-107">The .NET Framework versions 3.0 and 3.5 use the .NET Framework version 2.0 hosting interfaces, and do not introduce any hosting features.</span></span>  
  
 <span data-ttu-id="eb13e-108">.NET Framework 4 ホスト インターフェイスでは、.NET Framework 2.0 インターフェイスを優先します。</span><span class="sxs-lookup"><span data-stu-id="eb13e-108">The .NET Framework 4 hosting interfaces supersede the .NET Framework 2.0 interfaces.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="eb13e-109">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="eb13e-109">In This Section</span></span>  
 [<span data-ttu-id="eb13e-110">非推奨の CLR のホスト インターフェイスおよびコクラス</span><span class="sxs-lookup"><span data-stu-id="eb13e-110">Deprecated CLR Hosting Interfaces and Coclasses</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-interfaces-and-coclasses.md)  
 <span data-ttu-id="eb13e-111">.NET Framework version 1.0 および 1.1 で導入されたホスティング インターフェイスをについて説明します。</span><span class="sxs-lookup"><span data-stu-id="eb13e-111">Describes the hosting interfaces introduced in the .NET Framework versions 1.0 and 1.1.</span></span>  
  
 [<span data-ttu-id="eb13e-112">CLR ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="eb13e-112">CLR Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces.md)  
 <span data-ttu-id="eb13e-113">.NET Framework version 2.0 で導入されたホスティング インターフェイスをについて説明します。</span><span class="sxs-lookup"><span data-stu-id="eb13e-113">Describes the hosting interfaces introduced in the .NET Framework version 2.0.</span></span>  
  
 [<span data-ttu-id="eb13e-114">.NET Framework 4 および 4.5 で追加された CLR ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="eb13e-114">CLR Hosting Interfaces Added in the .NET Framework 4 and 4.5</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)  
 <span data-ttu-id="eb13e-115">.NET Framework 4 で導入されたホスティング インターフェイスをについて説明します。</span><span class="sxs-lookup"><span data-stu-id="eb13e-115">Describes the hosting interfaces introduced in the .NET Framework 4.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="eb13e-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="eb13e-116">Related Sections</span></span>  
 [<span data-ttu-id="eb13e-117">ホスト コクラス</span><span class="sxs-lookup"><span data-stu-id="eb13e-117">Hosting Coclasses</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-coclasses.md)  
  
 [<span data-ttu-id="eb13e-118">非推奨の CLR ホスト関数</span><span class="sxs-lookup"><span data-stu-id="eb13e-118">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)  
  
 [<span data-ttu-id="eb13e-119">ホスティングの列挙型</span><span class="sxs-lookup"><span data-stu-id="eb13e-119">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)  
  
 [<span data-ttu-id="eb13e-120">ホスト構造体</span><span class="sxs-lookup"><span data-stu-id="eb13e-120">Hosting Structures</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)  
  
 [<span data-ttu-id="eb13e-121">ホスティング</span><span class="sxs-lookup"><span data-stu-id="eb13e-121">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)  
  
 <span data-ttu-id="eb13e-122">[ランタイム ホスト](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/a51xd4ze(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="eb13e-122">[Runtime Hosts](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/a51xd4ze(v=vs.100))</span></span>
