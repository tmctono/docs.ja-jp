---
ms.openlocfilehash: 9500907c6a1ba5b27008dcad4c9b47aef9092106
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/11/2019
ms.locfileid: "67802440"
---
### <a name="ribbongroup-background-is-set-to-transparent-in-localized-builds"></a><span data-ttu-id="6ff41-101">ローカライズされたビルドで RibbonGroup の背景が透明に設定される</span><span class="sxs-lookup"><span data-stu-id="6ff41-101">RibbonGroup background is set to transparent in localized builds</span></span>

|   |   |
|---|---|
|<span data-ttu-id="6ff41-102">説明</span><span class="sxs-lookup"><span data-stu-id="6ff41-102">Details</span></span>|<span data-ttu-id="6ff41-103">ローカライズされたビルドの <xref:System.Windows.Controls.Ribbon.RibbonGroup?displayProperty=name> の背景が常に透明のブラシで塗りつぶされており、UI の操作性が低下していました。</span><span class="sxs-lookup"><span data-stu-id="6ff41-103"><xref:System.Windows.Controls.Ribbon.RibbonGroup?displayProperty=name> background on localized builds was always painted with Transparent brush, resulting in poor UI experience.</span></span> <span data-ttu-id="6ff41-104">これは、.NET Framework 4.7 WPF 修正プログラムで修正されます。<xref:System.Windows.Controls.Ribbon.RibbonGroup?displayProperty=name> のローカライズされたリソースが更新され、正しいブラシが確実に選択されるようになります。</span><span class="sxs-lookup"><span data-stu-id="6ff41-104">This is fixed in .NET Framework 4.7 WPF fix by updating the localized resources for <xref:System.Windows.Controls.Ribbon.RibbonGroup?displayProperty=name>, which in turn ensures that the correct brush is selected.</span></span>|
|<span data-ttu-id="6ff41-105">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="6ff41-105">Suggestion</span></span>|<span data-ttu-id="6ff41-106">.NET Framework 4.7 にアップグレードします</span><span class="sxs-lookup"><span data-stu-id="6ff41-106">Upgrade to .NET Framework 4.7</span></span>|
|<span data-ttu-id="6ff41-107">スコープ</span><span class="sxs-lookup"><span data-stu-id="6ff41-107">Scope</span></span>|<span data-ttu-id="6ff41-108">エッジ</span><span class="sxs-lookup"><span data-stu-id="6ff41-108">Edge</span></span>|
|<span data-ttu-id="6ff41-109">Version</span><span class="sxs-lookup"><span data-stu-id="6ff41-109">Version</span></span>|<span data-ttu-id="6ff41-110">4.6.2</span><span class="sxs-lookup"><span data-stu-id="6ff41-110">4.6.2</span></span>|
|<span data-ttu-id="6ff41-111">型</span><span class="sxs-lookup"><span data-stu-id="6ff41-111">Type</span></span>|<span data-ttu-id="6ff41-112">ランタイム</span><span class="sxs-lookup"><span data-stu-id="6ff41-112">Runtime</span></span>|

