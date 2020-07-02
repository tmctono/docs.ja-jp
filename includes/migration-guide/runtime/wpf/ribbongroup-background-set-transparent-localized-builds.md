---
ms.openlocfilehash: a3ba42868577ac20ea2e082f90fc4973a1bfe108
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85622368"
---
### <a name="ribbongroup-background-is-set-to-transparent-in-localized-builds"></a><span data-ttu-id="8f963-101">ローカライズされたビルドで RibbonGroup の背景が透明に設定される</span><span class="sxs-lookup"><span data-stu-id="8f963-101">RibbonGroup background is set to transparent in localized builds</span></span>

#### <a name="details"></a><span data-ttu-id="8f963-102">説明</span><span class="sxs-lookup"><span data-stu-id="8f963-102">Details</span></span>

<span data-ttu-id="8f963-103">ローカライズされたビルドの <xref:System.Windows.Controls.Ribbon.RibbonGroup?displayProperty=fullName> の背景が常に透明のブラシで塗りつぶされており、UI の操作性が低下していました。</span><span class="sxs-lookup"><span data-stu-id="8f963-103"><xref:System.Windows.Controls.Ribbon.RibbonGroup?displayProperty=fullName> background on localized builds was always painted with Transparent brush, resulting in poor UI experience.</span></span> <span data-ttu-id="8f963-104">これは、.NET Framework 4.7 WPF 修正プログラムで修正されます。<xref:System.Windows.Controls.Ribbon.RibbonGroup?displayProperty=fullName> のローカライズされたリソースが更新され、正しいブラシが確実に選択されるようになります。</span><span class="sxs-lookup"><span data-stu-id="8f963-104">This is fixed in .NET Framework 4.7 WPF fix by updating the localized resources for <xref:System.Windows.Controls.Ribbon.RibbonGroup?displayProperty=fullName>, which in turn ensures that the correct brush is selected.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="8f963-105">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="8f963-105">Suggestion</span></span>

<span data-ttu-id="8f963-106">.NET Framework 4.7 にアップグレードします</span><span class="sxs-lookup"><span data-stu-id="8f963-106">Upgrade to .NET Framework 4.7</span></span>

| <span data-ttu-id="8f963-107">名前</span><span class="sxs-lookup"><span data-stu-id="8f963-107">Name</span></span>    | <span data-ttu-id="8f963-108">値</span><span class="sxs-lookup"><span data-stu-id="8f963-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="8f963-109">スコープ</span><span class="sxs-lookup"><span data-stu-id="8f963-109">Scope</span></span>   |<span data-ttu-id="8f963-110">エッジ</span><span class="sxs-lookup"><span data-stu-id="8f963-110">Edge</span></span>|
|<span data-ttu-id="8f963-111">バージョン</span><span class="sxs-lookup"><span data-stu-id="8f963-111">Version</span></span>|<span data-ttu-id="8f963-112">4.6.2</span><span class="sxs-lookup"><span data-stu-id="8f963-112">4.6.2</span></span>|
|<span data-ttu-id="8f963-113">種類</span><span class="sxs-lookup"><span data-stu-id="8f963-113">Type</span></span>|<span data-ttu-id="8f963-114">ランタイム</span><span class="sxs-lookup"><span data-stu-id="8f963-114">Runtime</span></span>|
