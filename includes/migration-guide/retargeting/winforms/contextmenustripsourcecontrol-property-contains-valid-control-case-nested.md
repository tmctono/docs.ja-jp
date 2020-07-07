---
ms.openlocfilehash: 97299ddb9bee89c792ddb3d2b9c37516180996f7
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614878"
---
### <a name="contextmenustripsourcecontrol-property-contains-a-valid-control-in-the-case-of-nested-toolstripmenuitems"></a><span data-ttu-id="d51b1-101">入れ子になった ToolStripMenuItems の場合、ContextMenuStrip.SourceControl プロパティには有効なコントロールが含まれる</span><span class="sxs-lookup"><span data-stu-id="d51b1-101">ContextMenuStrip.SourceControl property contains a valid control in the case of nested ToolStripMenuItems</span></span>

#### <a name="details"></a><span data-ttu-id="d51b1-102">説明</span><span class="sxs-lookup"><span data-stu-id="d51b1-102">Details</span></span>

<span data-ttu-id="d51b1-103">.NET Framework 4.7.1 およびそれより前のバージョンの <xref:System.Windows.Forms.ContextMenuStrip.SourceControl?displayProperty=nameWithType> プロパティは、ユーザーが入れ子になった <xref:System.Windows.Forms.ToolStripMenuItem> コントロールからメニューを開いたとき、正しくない null を返します。</span><span class="sxs-lookup"><span data-stu-id="d51b1-103">In the .NET Framework 4.7.1 and previous versions, the <xref:System.Windows.Forms.ContextMenuStrip.SourceControl?displayProperty=nameWithType> property incorrectly returns null when the user opens the menu from nested <xref:System.Windows.Forms.ToolStripMenuItem> controls.</span></span> <span data-ttu-id="d51b1-104">.NET Framework 4.7.2 およびそれ以降では、<xref:System.Windows.Forms.ContextMenuStrip.SourceControl> プロパティには常に実際のソース コントロールが設定されます。</span><span class="sxs-lookup"><span data-stu-id="d51b1-104">In the .NET Framework 4.7.2 and later, <xref:System.Windows.Forms.ContextMenuStrip.SourceControl> property is always set to the actual source control.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="d51b1-105">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="d51b1-105">Suggestion</span></span>

<span data-ttu-id="d51b1-106">**これらの変更を選択する方法と選択しない方法** アプリケーションでこれらの変更を利用するには、.NET Framework 4.7.2 以降で実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d51b1-106">**How to opt in or out of these changes** In order for an application to benefit from these changes, it must run on the .NET Framework 4.7.2 or later.</span></span> <span data-ttu-id="d51b1-107">アプリケーションは、次のいずれかの方法でこれらの変更を利用できます。</span><span class="sxs-lookup"><span data-stu-id="d51b1-107">The application can benefit from these changes in either of the following ways:</span></span>

- <span data-ttu-id="d51b1-108">.NET Framework 4.7.2 を対象にします。</span><span class="sxs-lookup"><span data-stu-id="d51b1-108">It targets the .NET Framework 4.7.2.</span></span> <span data-ttu-id="d51b1-109">.NET Framework 4.7.2 以降を対象とする Windows フォーム アプリケーションでは、この変更が既定で有効になります。</span><span class="sxs-lookup"><span data-stu-id="d51b1-109">This change is enabled by default on Windows Forms applications that target the .NET Framework 4.7.2 or later.</span></span>
- <span data-ttu-id="d51b1-110">.NET Framework 4.7.1 以前を対象にして、下の例のように、app.config ファイルの `<runtime>` セクションに次の [AppContext スイッチ](https://docs.microsoft.com/dotnet/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element)を追加し、それを `false` に設定することで、以前のアクセシビリティ動作を無効にします。</span><span class="sxs-lookup"><span data-stu-id="d51b1-110">It targets the .NET Framework 4.7.1 or an earlier version and opts out of the legacy accessibility behaviors by adding the following [AppContext Switch](https://docs.microsoft.com/dotnet/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element) to the `<runtime>` section of the app.config file and setting it to `false`, as the following example shows.</span></span>

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.Windows.Forms.UseLegacyContextMenuStripSourceControlValue=false"/>
</runtime>
```

<span data-ttu-id="d51b1-111">.NET Framework 4.7.2 以降を対象とするアプリケーションで以前の動作を残す場合、この AppContext スイッチを明示的に `true` に設定することで、以前のソース コントロール値を選択できます。</span><span class="sxs-lookup"><span data-stu-id="d51b1-111">Applications that target the .NET Framework 4.7.2 or later, and want to preserve the legacy behavior can opt in to the use of the legacy source control value by explicitly setting this AppContext switch to `true`.</span></span>

| <span data-ttu-id="d51b1-112">名前</span><span class="sxs-lookup"><span data-stu-id="d51b1-112">Name</span></span>    | <span data-ttu-id="d51b1-113">[値]</span><span class="sxs-lookup"><span data-stu-id="d51b1-113">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="d51b1-114">スコープ</span><span class="sxs-lookup"><span data-stu-id="d51b1-114">Scope</span></span>   | <span data-ttu-id="d51b1-115">エッジ</span><span class="sxs-lookup"><span data-stu-id="d51b1-115">Edge</span></span>        |
| <span data-ttu-id="d51b1-116">バージョン</span><span class="sxs-lookup"><span data-stu-id="d51b1-116">Version</span></span> | <span data-ttu-id="d51b1-117">4.7.2</span><span class="sxs-lookup"><span data-stu-id="d51b1-117">4.7.2</span></span>       |
| <span data-ttu-id="d51b1-118">種類</span><span class="sxs-lookup"><span data-stu-id="d51b1-118">Type</span></span>    | <span data-ttu-id="d51b1-119">再ターゲット中</span><span class="sxs-lookup"><span data-stu-id="d51b1-119">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="d51b1-120">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="d51b1-120">Affected APIs</span></span>

- <xref:System.Windows.Forms.ContextMenuStrip.SourceControl?displayProperty=nameWithType>
