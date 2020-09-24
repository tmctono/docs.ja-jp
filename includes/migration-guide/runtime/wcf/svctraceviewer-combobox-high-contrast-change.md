---
ms.openlocfilehash: 4bc8db52efdfe483acb4f6b6e33c4fa7716e0b79
ms.sourcegitcommit: 261e0c98a111357692b3b63c596edf0cacf72991
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2020
ms.locfileid: "90770944"
---
### <a name="svctraceviewer-combobox-high-contrast-change"></a><span data-ttu-id="e2ed3-101">svcTraceViewer ComboBox のハイ コントラストの変更</span><span class="sxs-lookup"><span data-stu-id="e2ed3-101">svcTraceViewer ComboBox high contrast change</span></span>

#### <a name="details"></a><span data-ttu-id="e2ed3-102">説明</span><span class="sxs-lookup"><span data-stu-id="e2ed3-102">Details</span></span>

<span data-ttu-id="e2ed3-103">[Microsoft Service Trace Viewer ツール](~/docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md)では、特定のハイ コントラストのテーマで ComboBox コントロールが適切な色で表示されませんでした。</span><span class="sxs-lookup"><span data-stu-id="e2ed3-103">In the [Microsoft Service Trace Viewer tool](~/docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md), ComboBox controls were not displayed in the correct color in certain high contrast themes.</span></span> <span data-ttu-id="e2ed3-104">この問題は .NET Framework 4.7.2 で修正されました。</span><span class="sxs-lookup"><span data-stu-id="e2ed3-104">The issue was fixed in .NET Framework 4.7.2.</span></span> <span data-ttu-id="e2ed3-105">しかし、.NET Framework SDK の下位互換性要件により、既定ではお客様に修正が示されませんでした。</span><span class="sxs-lookup"><span data-stu-id="e2ed3-105">However, due to .NET Framework SDK backward compatibility requirements, the fix was not visible to customers by default.</span></span> <span data-ttu-id="e2ed3-106">.NET 4.8 では、次の [AppContext 構成スイッチ](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md)を svcTraceViewer.exe.config ファイルに追加することで、この変更が示されます。</span><span class="sxs-lookup"><span data-stu-id="e2ed3-106">.NET 4.8 surfaces this change by adding the following [AppContext configuration switches](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) to the svcTraceViewer.exe.config file:</span></span>

```xml
<AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=false;Switch.UseLegacyAccessibilityFeatures.2=false" />
```

#### <a name="suggestion"></a><span data-ttu-id="e2ed3-107">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="e2ed3-107">Suggestion</span></span>

<span data-ttu-id="e2ed3-108">ハイ コントラストの動作を変更したくない場合は、svcTraceViewer.exe.config ファイルから次のセクションを削除することで、無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="e2ed3-108">If you don't want to have the high contrast behavior change, you can disable it by removing the following section from the svcTraceViewer.exe.config file:</span></span>

```xml
<AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=false;Switch.UseLegacyAccessibilityFeatures.2=false" />
```

| <span data-ttu-id="e2ed3-109">名前</span><span class="sxs-lookup"><span data-stu-id="e2ed3-109">Name</span></span>    | <span data-ttu-id="e2ed3-110">[値]</span><span class="sxs-lookup"><span data-stu-id="e2ed3-110">Value</span></span>   |
|:--------|:--------|
| <span data-ttu-id="e2ed3-111">スコープ</span><span class="sxs-lookup"><span data-stu-id="e2ed3-111">Scope</span></span>   | <span data-ttu-id="e2ed3-112">エッジ</span><span class="sxs-lookup"><span data-stu-id="e2ed3-112">Edge</span></span>    |
| <span data-ttu-id="e2ed3-113">バージョン</span><span class="sxs-lookup"><span data-stu-id="e2ed3-113">Version</span></span> | <span data-ttu-id="e2ed3-114">4.8</span><span class="sxs-lookup"><span data-stu-id="e2ed3-114">4.8</span></span>     |
| <span data-ttu-id="e2ed3-115">種類</span><span class="sxs-lookup"><span data-stu-id="e2ed3-115">Type</span></span>    | <span data-ttu-id="e2ed3-116">ランタイム</span><span class="sxs-lookup"><span data-stu-id="e2ed3-116">Runtime</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="e2ed3-117">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="e2ed3-117">Affected APIs</span></span>

<span data-ttu-id="e2ed3-118">API 分析では検出できません。</span><span class="sxs-lookup"><span data-stu-id="e2ed3-118">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
