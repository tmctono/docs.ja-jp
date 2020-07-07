---
ms.openlocfilehash: 863e7035827537e0f943af05c2f0232029b99db8
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617193"
---
### <a name="entity-framework-version-must-match-the-net-framework-version"></a><span data-ttu-id="7398f-101">Entity Framework バージョンは .NET Framework バージョンに一致する必要がある</span><span class="sxs-lookup"><span data-stu-id="7398f-101">Entity Framework version must match the .NET Framework version</span></span>

#### <a name="details"></a><span data-ttu-id="7398f-102">説明</span><span class="sxs-lookup"><span data-stu-id="7398f-102">Details</span></span>

<span data-ttu-id="7398f-103">Entity Framework (EF) のバージョンは、.NET Framework のバージョンと一致している必要があります。</span><span class="sxs-lookup"><span data-stu-id="7398f-103">The Entity Framework (EF) version should be matched with the .NET Framework version.</span></span> <span data-ttu-id="7398f-104">.NET Framework 4.5 には、Entity Framework 5 をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="7398f-104">Entity Framework 5 is recommended for .NET Framework 4.5.</span></span> <span data-ttu-id="7398f-105">.NET Framework 4.5 プロジェクトの EF 4.x に <xref:System.ComponentModel.DataAnnotations> に関する既知の問題がいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="7398f-105">There are some known issues with EF 4.x in a .NET Framework 4.5 project around <xref:System.ComponentModel.DataAnnotations>.</span></span> <span data-ttu-id="7398f-106">.NET Framework 4.5 では、これらは別のアセンブリに移動されたため、どの注釈を使用するかを決めるという問題があります。</span><span class="sxs-lookup"><span data-stu-id="7398f-106">In .NET Framework 4.5, these were moved to a different assembly, so there are issues determining which annotations to use.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="7398f-107">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="7398f-107">Suggestion</span></span>

<span data-ttu-id="7398f-108">.NET Framework 4.5 の場合、Entity Framework 5 にアップグレードする</span><span class="sxs-lookup"><span data-stu-id="7398f-108">Upgrade to Entity Framework 5 for .NET Framework 4.5</span></span>

| <span data-ttu-id="7398f-109">名前</span><span class="sxs-lookup"><span data-stu-id="7398f-109">Name</span></span>    | <span data-ttu-id="7398f-110">[値]</span><span class="sxs-lookup"><span data-stu-id="7398f-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="7398f-111">スコープ</span><span class="sxs-lookup"><span data-stu-id="7398f-111">Scope</span></span>   | <span data-ttu-id="7398f-112">Major</span><span class="sxs-lookup"><span data-stu-id="7398f-112">Major</span></span>       |
| <span data-ttu-id="7398f-113">バージョン</span><span class="sxs-lookup"><span data-stu-id="7398f-113">Version</span></span> | <span data-ttu-id="7398f-114">4.5</span><span class="sxs-lookup"><span data-stu-id="7398f-114">4.5</span></span>         |
| <span data-ttu-id="7398f-115">種類</span><span class="sxs-lookup"><span data-stu-id="7398f-115">Type</span></span>    | <span data-ttu-id="7398f-116">再ターゲット中</span><span class="sxs-lookup"><span data-stu-id="7398f-116">Retargeting</span></span> |
