---
ms.openlocfilehash: 863e7035827537e0f943af05c2f0232029b99db8
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617193"
---
### <a name="entity-framework-version-must-match-the-net-framework-version"></a><span data-ttu-id="ec96e-101">Entity Framework バージョンは .NET Framework バージョンに一致する必要がある</span><span class="sxs-lookup"><span data-stu-id="ec96e-101">Entity Framework version must match the .NET Framework version</span></span>

#### <a name="details"></a><span data-ttu-id="ec96e-102">説明</span><span class="sxs-lookup"><span data-stu-id="ec96e-102">Details</span></span>

<span data-ttu-id="ec96e-103">Entity Framework (EF) のバージョンは、.NET Framework のバージョンと一致している必要があります。</span><span class="sxs-lookup"><span data-stu-id="ec96e-103">The Entity Framework (EF) version should be matched with the .NET Framework version.</span></span> <span data-ttu-id="ec96e-104">.NET Framework 4.5 には、Entity Framework 5 をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="ec96e-104">Entity Framework 5 is recommended for .NET Framework 4.5.</span></span> <span data-ttu-id="ec96e-105">.NET Framework 4.5 プロジェクトの EF 4.x に <xref:System.ComponentModel.DataAnnotations> に関する既知の問題がいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="ec96e-105">There are some known issues with EF 4.x in a .NET Framework 4.5 project around <xref:System.ComponentModel.DataAnnotations>.</span></span> <span data-ttu-id="ec96e-106">.NET Framework 4.5 では、これらは別のアセンブリに移動されたため、どの注釈を使用するかを決めるという問題があります。</span><span class="sxs-lookup"><span data-stu-id="ec96e-106">In .NET Framework 4.5, these were moved to a different assembly, so there are issues determining which annotations to use.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="ec96e-107">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="ec96e-107">Suggestion</span></span>

<span data-ttu-id="ec96e-108">.NET Framework 4.5 の場合、Entity Framework 5 にアップグレードする</span><span class="sxs-lookup"><span data-stu-id="ec96e-108">Upgrade to Entity Framework 5 for .NET Framework 4.5</span></span>

| <span data-ttu-id="ec96e-109">名前</span><span class="sxs-lookup"><span data-stu-id="ec96e-109">Name</span></span>    | <span data-ttu-id="ec96e-110">[値]</span><span class="sxs-lookup"><span data-stu-id="ec96e-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="ec96e-111">スコープ</span><span class="sxs-lookup"><span data-stu-id="ec96e-111">Scope</span></span>   | <span data-ttu-id="ec96e-112">Major</span><span class="sxs-lookup"><span data-stu-id="ec96e-112">Major</span></span>       |
| <span data-ttu-id="ec96e-113">バージョン</span><span class="sxs-lookup"><span data-stu-id="ec96e-113">Version</span></span> | <span data-ttu-id="ec96e-114">4.5</span><span class="sxs-lookup"><span data-stu-id="ec96e-114">4.5</span></span>         |
| <span data-ttu-id="ec96e-115">種類</span><span class="sxs-lookup"><span data-stu-id="ec96e-115">Type</span></span>    | <span data-ttu-id="ec96e-116">再ターゲット中</span><span class="sxs-lookup"><span data-stu-id="ec96e-116">Retargeting</span></span> |
