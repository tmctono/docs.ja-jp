---
ms.openlocfilehash: f78d15338aa49de5b729aca12964924a0df00ec6
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614835"
---
### <a name="improved-accessibility-for-some-net-sdk-tools"></a><span data-ttu-id="7efd1-101">一部の .NET SDK ツールのアクセシビリティが強化されました</span><span class="sxs-lookup"><span data-stu-id="7efd1-101">Improved accessibility for some .NET SDK tools</span></span>

#### <a name="details"></a><span data-ttu-id="7efd1-102">説明</span><span class="sxs-lookup"><span data-stu-id="7efd1-102">Details</span></span>

<span data-ttu-id="7efd1-103">.NET Framework SDK 4.7.1 では、さまざまなアクセシビリティの問題を修正することで、SvcConfigEditor.exe と SvcTraceViewer.exe のツールが改善されました。</span><span class="sxs-lookup"><span data-stu-id="7efd1-103">In the .NET Framework SDK 4.7.1, the SvcConfigEditor.exe and SvcTraceViewer.exe tools have been improved by fixing varied accessibility issues.</span></span> <span data-ttu-id="7efd1-104">その問題のほとんどは、名前の未定義や、特定の UI の自動化パターンが正しく実装されていないといった軽微なものです。</span><span class="sxs-lookup"><span data-stu-id="7efd1-104">Most of these were small issues like a name not being defined or certain UI automation patterns not being implemented correctly.</span></span> <span data-ttu-id="7efd1-105">このような問題は、多くのユーザーが認識しないものですが、スクリーン リーダーのような支援技術を使用するお客様はこれらの SDK ツールのアクセシビリティの強化を実感されるでしょう。</span><span class="sxs-lookup"><span data-stu-id="7efd1-105">While many users wouldn't be aware of these incorrect values, customers who use assistive technologies like screen readers will find these SDK tools more accessible.</span></span> <span data-ttu-id="7efd1-106">実際に、この修正によって、キーボード フォーカスの順序のような以前の動作がいくつか変更されます。これらのツールのアクセシビリティの修正をすべて取得するには、app.config ファイルを次のようにします。</span><span class="sxs-lookup"><span data-stu-id="7efd1-106">Certainly, these fixes change some previous behaviors, like keyboard focus order.In order to get all the accessibility fixes in these tools, you can the following to your app.config file:</span></span>

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=false"/>
</runtime>
```

| <span data-ttu-id="7efd1-107">名前</span><span class="sxs-lookup"><span data-stu-id="7efd1-107">Name</span></span>    | <span data-ttu-id="7efd1-108">[値]</span><span class="sxs-lookup"><span data-stu-id="7efd1-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="7efd1-109">スコープ</span><span class="sxs-lookup"><span data-stu-id="7efd1-109">Scope</span></span>   | <span data-ttu-id="7efd1-110">エッジ</span><span class="sxs-lookup"><span data-stu-id="7efd1-110">Edge</span></span>        |
| <span data-ttu-id="7efd1-111">Version</span><span class="sxs-lookup"><span data-stu-id="7efd1-111">Version</span></span> | <span data-ttu-id="7efd1-112">4.7.1</span><span class="sxs-lookup"><span data-stu-id="7efd1-112">4.7.1</span></span>       |
| <span data-ttu-id="7efd1-113">種類</span><span class="sxs-lookup"><span data-stu-id="7efd1-113">Type</span></span>    | <span data-ttu-id="7efd1-114">再ターゲット中</span><span class="sxs-lookup"><span data-stu-id="7efd1-114">Retargeting</span></span> |
