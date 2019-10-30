---
title: ホスト インターフェイス
ms.date: 03/30/2017
helpviewer_keywords:
- interfaces [.NET Framework hosting]
- hosting interfaces [.NET Framework]
- unmanaged interfaces [.NET Framework], hosting
ms.assetid: cc64cb05-38da-418e-815a-daac8e8e26e5
ms.openlocfilehash: 43b401885bb4de69a06496874f11cec6cdf04b22
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73126975"
---
# <a name="hosting-interfaces"></a><span data-ttu-id="a353b-102">ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a353b-102">Hosting Interfaces</span></span>
<span data-ttu-id="a353b-103">ここでは、アンマネージホストが共通言語ランタイム (CLR) をアプリケーションに統合するために使用できるインターフェイスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="a353b-103">This section describes the interfaces that unmanaged hosts can use to integrate the common language runtime (CLR) into their applications.</span></span>  
  
 <span data-ttu-id="a353b-104">.NET Framework バージョン2.0 のホストインターフェイスは、.NET Framework バージョン1.0 および1.1 インターフェイスより優先されます。</span><span class="sxs-lookup"><span data-stu-id="a353b-104">The .NET Framework version 2.0 hosting interfaces supersede the .NET Framework version 1.0 and 1.1 interfaces.</span></span> <span data-ttu-id="a353b-105">2つのインターフェイスセットには大きな違いがあります。</span><span class="sxs-lookup"><span data-stu-id="a353b-105">There are significant differences between the two sets of interfaces.</span></span> <span data-ttu-id="a353b-106">これらを混在させると、予期しない動作が発生する可能性があるため、推奨されません。</span><span class="sxs-lookup"><span data-stu-id="a353b-106">Mixing them could cause unexpected behavior and is not recommended.</span></span>  
  
 <span data-ttu-id="a353b-107">.NET Framework バージョン3.0 および3.5 では、.NET Framework バージョン2.0 のホストインターフェイスが使用され、ホスト機能は導入されません。</span><span class="sxs-lookup"><span data-stu-id="a353b-107">The .NET Framework versions 3.0 and 3.5 use the .NET Framework version 2.0 hosting interfaces, and do not introduce any hosting features.</span></span>  
  
 <span data-ttu-id="a353b-108">.NET Framework 4 のホストインターフェイスは、.NET Framework 2.0 インターフェイスより優先されます。</span><span class="sxs-lookup"><span data-stu-id="a353b-108">The .NET Framework 4 hosting interfaces supersede the .NET Framework 2.0 interfaces.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="a353b-109">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="a353b-109">In This Section</span></span>  
 [<span data-ttu-id="a353b-110">非推奨の CLR のホスト インターフェイスおよびコクラス</span><span class="sxs-lookup"><span data-stu-id="a353b-110">Deprecated CLR Hosting Interfaces and Coclasses</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-interfaces-and-coclasses.md)  
 <span data-ttu-id="a353b-111">.NET Framework バージョン1.0 および1.1 で導入されたホスティングインターフェイスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="a353b-111">Describes the hosting interfaces introduced in the .NET Framework versions 1.0 and 1.1.</span></span>  
  
 [<span data-ttu-id="a353b-112">CLR ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a353b-112">CLR Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces.md)  
 <span data-ttu-id="a353b-113">.NET Framework バージョン2.0 で導入されたホスティングインターフェイスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="a353b-113">Describes the hosting interfaces introduced in the .NET Framework version 2.0.</span></span>  
  
 [<span data-ttu-id="a353b-114">.NET Framework 4 および 4.5 で追加された CLR ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a353b-114">CLR Hosting Interfaces Added in the .NET Framework 4 and 4.5</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)  
 <span data-ttu-id="a353b-115">.NET Framework 4 で導入されたホスティングインターフェイスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="a353b-115">Describes the hosting interfaces introduced in the .NET Framework 4.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="a353b-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="a353b-116">Related Sections</span></span>  
 [<span data-ttu-id="a353b-117">ホスト コクラス</span><span class="sxs-lookup"><span data-stu-id="a353b-117">Hosting Coclasses</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-coclasses.md)  
  
 [<span data-ttu-id="a353b-118">非推奨の CLR ホスト関数</span><span class="sxs-lookup"><span data-stu-id="a353b-118">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)  
  
 [<span data-ttu-id="a353b-119">ホスティングの列挙型</span><span class="sxs-lookup"><span data-stu-id="a353b-119">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)  
  
 [<span data-ttu-id="a353b-120">ホスト構造体</span><span class="sxs-lookup"><span data-stu-id="a353b-120">Hosting Structures</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)  
  
 [<span data-ttu-id="a353b-121">ホスティング</span><span class="sxs-lookup"><span data-stu-id="a353b-121">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)  
  
 <span data-ttu-id="a353b-122">[ランタイム ホスト](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/a51xd4ze(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="a353b-122">[Runtime Hosts](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/a51xd4ze(v=vs.100))</span></span>
