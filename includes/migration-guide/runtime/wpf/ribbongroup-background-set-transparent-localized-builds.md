---
ms.openlocfilehash: 921baed7381fad363cc832c6b6af69068c2c8f43
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/15/2020
ms.locfileid: "67802440"
---
### <a name="ribbongroup-background-is-set-to-transparent-in-localized-builds"></a><span data-ttu-id="c5180-101">ローカライズされたビルドで RibbonGroup の背景が透明に設定される</span><span class="sxs-lookup"><span data-stu-id="c5180-101">RibbonGroup background is set to transparent in localized builds</span></span>

|   |   |
|---|---|
|<span data-ttu-id="c5180-102">説明</span><span class="sxs-lookup"><span data-stu-id="c5180-102">Details</span></span>|<span data-ttu-id="c5180-103">ローカライズされたビルドの <xref:System.Windows.Controls.Ribbon.RibbonGroup?displayProperty=name> の背景が常に透明のブラシで塗りつぶされており、UI の操作性が低下していました。</span><span class="sxs-lookup"><span data-stu-id="c5180-103"><xref:System.Windows.Controls.Ribbon.RibbonGroup?displayProperty=name> background on localized builds was always painted with Transparent brush, resulting in poor UI experience.</span></span> <span data-ttu-id="c5180-104">これは、.NET Framework 4.7 WPF 修正プログラムで修正されます。<xref:System.Windows.Controls.Ribbon.RibbonGroup?displayProperty=name> のローカライズされたリソースが更新され、正しいブラシが確実に選択されるようになります。</span><span class="sxs-lookup"><span data-stu-id="c5180-104">This is fixed in .NET Framework 4.7 WPF fix by updating the localized resources for <xref:System.Windows.Controls.Ribbon.RibbonGroup?displayProperty=name>, which in turn ensures that the correct brush is selected.</span></span>|
|<span data-ttu-id="c5180-105">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="c5180-105">Suggestion</span></span>|<span data-ttu-id="c5180-106">.NET Framework 4.7 にアップグレードします</span><span class="sxs-lookup"><span data-stu-id="c5180-106">Upgrade to .NET Framework 4.7</span></span>|
|<span data-ttu-id="c5180-107">スコープ</span><span class="sxs-lookup"><span data-stu-id="c5180-107">Scope</span></span>|<span data-ttu-id="c5180-108">エッジ</span><span class="sxs-lookup"><span data-stu-id="c5180-108">Edge</span></span>|
|<span data-ttu-id="c5180-109">バージョン</span><span class="sxs-lookup"><span data-stu-id="c5180-109">Version</span></span>|<span data-ttu-id="c5180-110">4.6.2</span><span class="sxs-lookup"><span data-stu-id="c5180-110">4.6.2</span></span>|
|<span data-ttu-id="c5180-111">[種類]</span><span class="sxs-lookup"><span data-stu-id="c5180-111">Type</span></span>|<span data-ttu-id="c5180-112">ランタイム</span><span class="sxs-lookup"><span data-stu-id="c5180-112">Runtime</span></span>|
