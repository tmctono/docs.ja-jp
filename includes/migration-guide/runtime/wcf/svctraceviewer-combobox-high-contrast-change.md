---
ms.openlocfilehash: 6a6c0af9cc0f3e5d1bbc3a4462a9ff7eaa748a5f
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497712"
---
### <a name="svctraceviewer-combobox-high-contrast-change"></a><span data-ttu-id="d7310-101">svcTraceViewer ComboBox のハイ コントラストの変更</span><span class="sxs-lookup"><span data-stu-id="d7310-101">svcTraceViewer ComboBox high contrast change</span></span>

#### <a name="details"></a><span data-ttu-id="d7310-102">説明</span><span class="sxs-lookup"><span data-stu-id="d7310-102">Details</span></span>

<span data-ttu-id="d7310-103">[Microsoft Service Trace Viewer ツール](~/docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md)では、特定のハイ コントラストのテーマで ComboBox コントロールが適切な色で表示されませんでした。</span><span class="sxs-lookup"><span data-stu-id="d7310-103">In the [Microsoft Service Trace Viewer tool](~/docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md), ComboBox controls were not displayed in the correct color in certain high contrast themes.</span></span> <span data-ttu-id="d7310-104">この問題は .NET Framework 4.7.2 で修正されました。</span><span class="sxs-lookup"><span data-stu-id="d7310-104">The issue was fixed in .NET Framework 4.7.2.</span></span> <span data-ttu-id="d7310-105">しかし、.NET Framework SDK の下位互換性要件により、既定ではお客様に修正が示されませんでした。</span><span class="sxs-lookup"><span data-stu-id="d7310-105">However, due to .NET Framework SDK backward compatibility requirements, the fix was not visible to customers by default.</span></span> <span data-ttu-id="d7310-106">.NET 4.8 では、次の [AppContext 構成スイッチ](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md)を svcTraceViewer.exe.config ファイルに追加することで、この変更が示されます。</span><span class="sxs-lookup"><span data-stu-id="d7310-106">.NET 4.8 surfaces this change by adding the following [AppContext configuration switches](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) to the svcTraceViewer.exe.config file:</span></span><pre><code class="lang-xml">&lt;AppContextSwitchOverrides value=&quot;Switch.UseLegacyAccessibilityFeatures=false;Switch.UseLegacyAccessibilityFeatures.2=false&quot; /&gt;&#13;&#10;</code></pre>

#### <a name="suggestion"></a><span data-ttu-id="d7310-107">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="d7310-107">Suggestion</span></span>

<ul><li><span data-ttu-id="d7310-108">変更を選択しない方法。ハイ コントラストの動作を変更したくない場合は、svcTraceViewer.exe.config ファイルから次のセクションを削除することで、無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="d7310-108">How to opt out of the change If you don't want to have the high contrast behavior change, you can disable it by removing the following section from the svcTraceViewer.exe.config file:</span></span></li></ul><pre><code class="lang-xml">&lt;AppContextSwitchOverrides value=&quot;Switch.UseLegacyAccessibilityFeatures=false;Switch.UseLegacyAccessibilityFeatures.2=false&quot; /&gt;&#13;&#10;</code></pre>

| <span data-ttu-id="d7310-109">名前</span><span class="sxs-lookup"><span data-stu-id="d7310-109">Name</span></span>    | <span data-ttu-id="d7310-110">[値]</span><span class="sxs-lookup"><span data-stu-id="d7310-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="d7310-111">スコープ</span><span class="sxs-lookup"><span data-stu-id="d7310-111">Scope</span></span>   |<span data-ttu-id="d7310-112">エッジ</span><span class="sxs-lookup"><span data-stu-id="d7310-112">Edge</span></span>|
|<span data-ttu-id="d7310-113">バージョン</span><span class="sxs-lookup"><span data-stu-id="d7310-113">Version</span></span>|<span data-ttu-id="d7310-114">4.8</span><span class="sxs-lookup"><span data-stu-id="d7310-114">4.8</span></span>|
|<span data-ttu-id="d7310-115">種類</span><span class="sxs-lookup"><span data-stu-id="d7310-115">Type</span></span>|<span data-ttu-id="d7310-116">ランタイム</span><span class="sxs-lookup"><span data-stu-id="d7310-116">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="d7310-117">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="d7310-117">Affected APIs</span></span>

<span data-ttu-id="d7310-118">API 分析では検出できません。</span><span class="sxs-lookup"><span data-stu-id="d7310-118">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
