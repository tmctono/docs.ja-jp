---
ms.openlocfilehash: 0b087fca59d60a086a9ea8b2bb19c09f646c3dfd
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/15/2020
ms.locfileid: "67858951"
---
### <a name="improved-accessibility-for-some-net-sdk-tools"></a><span data-ttu-id="8dfc7-101">一部の .NET SDK ツールのアクセシビリティが強化されました</span><span class="sxs-lookup"><span data-stu-id="8dfc7-101">Improved accessibility for some .NET SDK tools</span></span>

|   |   |
|---|---|
|<span data-ttu-id="8dfc7-102">説明</span><span class="sxs-lookup"><span data-stu-id="8dfc7-102">Details</span></span>|<span data-ttu-id="8dfc7-103">.NET Framework SDK 4.7.1 では、さまざまなアクセシビリティの問題を修正することで、SvcConfigEditor.exe と SvcTraceViewer.exe のツールが改善されました。</span><span class="sxs-lookup"><span data-stu-id="8dfc7-103">In the .NET Framework SDK 4.7.1, the SvcConfigEditor.exe and SvcTraceViewer.exe tools have been improved by fixing varied accessibility issues.</span></span> <span data-ttu-id="8dfc7-104">その問題のほとんどは、名前の未定義や、特定の UI の自動化パターンが正しく実装されていないといった軽微なものです。</span><span class="sxs-lookup"><span data-stu-id="8dfc7-104">Most of these were small issues like a name not being defined or certain UI automation patterns not being implemented correctly.</span></span> <span data-ttu-id="8dfc7-105">このような問題は、多くのユーザーが認識しないものですが、スクリーン リーダーのような支援技術を使用するお客様はこれらの SDK ツールのアクセシビリティの強化を実感されるでしょう。</span><span class="sxs-lookup"><span data-stu-id="8dfc7-105">While many users wouldn’t be aware of these incorrect values, customers who use assistive technologies like screen readers will find these SDK tools more accessible.</span></span> <span data-ttu-id="8dfc7-106">実際に、この修正によって、キーボード フォーカスの順序のような以前の動作がいくつか変更されます。これらのツールのアクセシビリティの修正をすべて取得するには、app.config ファイルを次のようにします。</span><span class="sxs-lookup"><span data-stu-id="8dfc7-106">Certainly, these fixes change some previous behaviors, like keyboard focus order.In order to get all the accessibility fixes in these tools, you can the following to your app.config file:</span></span><pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.UseLegacyAccessibilityFeatures=false&quot;/&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>|
|<span data-ttu-id="8dfc7-107">スコープ</span><span class="sxs-lookup"><span data-stu-id="8dfc7-107">Scope</span></span>|<span data-ttu-id="8dfc7-108">エッジ</span><span class="sxs-lookup"><span data-stu-id="8dfc7-108">Edge</span></span>|
|<span data-ttu-id="8dfc7-109">バージョン</span><span class="sxs-lookup"><span data-stu-id="8dfc7-109">Version</span></span>|<span data-ttu-id="8dfc7-110">4.7.1</span><span class="sxs-lookup"><span data-stu-id="8dfc7-110">4.7.1</span></span>|
|<span data-ttu-id="8dfc7-111">[種類]</span><span class="sxs-lookup"><span data-stu-id="8dfc7-111">Type</span></span>|<span data-ttu-id="8dfc7-112">再ターゲット中</span><span class="sxs-lookup"><span data-stu-id="8dfc7-112">Retargeting</span></span>|
