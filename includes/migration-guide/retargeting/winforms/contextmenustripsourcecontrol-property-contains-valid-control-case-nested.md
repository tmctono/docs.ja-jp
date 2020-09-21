---
ms.openlocfilehash: 5529b8379c5cb9f1bc525e0c2340f6b885e35822
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/15/2020
ms.locfileid: "90606816"
---
### <a name="contextmenustripsourcecontrol-property-contains-a-valid-control-in-the-case-of-nested-toolstripmenuitems"></a><span data-ttu-id="bcb19-101">入れ子になった ToolStripMenuItems の場合、ContextMenuStrip.SourceControl プロパティには有効なコントロールが含まれる</span><span class="sxs-lookup"><span data-stu-id="bcb19-101">ContextMenuStrip.SourceControl property contains a valid control in the case of nested ToolStripMenuItems</span></span>

#### <a name="details"></a><span data-ttu-id="bcb19-102">説明</span><span class="sxs-lookup"><span data-stu-id="bcb19-102">Details</span></span>

<span data-ttu-id="bcb19-103">.NET Framework 4.7.1 およびそれより前のバージョンの <xref:System.Windows.Forms.ContextMenuStrip.SourceControl?displayProperty=nameWithType> プロパティは、ユーザーが入れ子になった <xref:System.Windows.Forms.ToolStripMenuItem> コントロールからメニューを開いたとき、正しくない null を返します。</span><span class="sxs-lookup"><span data-stu-id="bcb19-103">In the .NET Framework 4.7.1 and previous versions, the <xref:System.Windows.Forms.ContextMenuStrip.SourceControl?displayProperty=nameWithType> property incorrectly returns null when the user opens the menu from nested <xref:System.Windows.Forms.ToolStripMenuItem> controls.</span></span> <span data-ttu-id="bcb19-104">.NET Framework 4.7.2 およびそれ以降では、<xref:System.Windows.Forms.ContextMenuStrip.SourceControl> プロパティには常に実際のソース コントロールが設定されます。</span><span class="sxs-lookup"><span data-stu-id="bcb19-104">In the .NET Framework 4.7.2 and later, <xref:System.Windows.Forms.ContextMenuStrip.SourceControl> property is always set to the actual source control.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="bcb19-105">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="bcb19-105">Suggestion</span></span>

<span data-ttu-id="bcb19-106">**これらの変更を選択する方法と選択しない方法** アプリケーションでこれらの変更を利用するには、.NET Framework 4.7.2 以降で実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bcb19-106">**How to opt in or out of these changes** In order for an application to benefit from these changes, it must run on the .NET Framework 4.7.2 or later.</span></span> <span data-ttu-id="bcb19-107">アプリケーションは、次のいずれかの方法でこれらの変更を利用できます。</span><span class="sxs-lookup"><span data-stu-id="bcb19-107">The application can benefit from these changes in either of the following ways:</span></span>

- <span data-ttu-id="bcb19-108">.NET Framework 4.7.2 を対象にします。</span><span class="sxs-lookup"><span data-stu-id="bcb19-108">It targets the .NET Framework 4.7.2.</span></span> <span data-ttu-id="bcb19-109">.NET Framework 4.7.2 以降を対象とする Windows フォーム アプリケーションでは、この変更が既定で有効になります。</span><span class="sxs-lookup"><span data-stu-id="bcb19-109">This change is enabled by default on Windows Forms applications that target the .NET Framework 4.7.2 or later.</span></span>
- <span data-ttu-id="bcb19-110">.NET Framework 4.7.1 以前を対象にして、下の例のように、app.config ファイルの `<runtime>` セクションに次の [AppContext スイッチ](../../../../docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md)を追加し、それを `false` に設定することで、以前のアクセシビリティ動作を無効にします。</span><span class="sxs-lookup"><span data-stu-id="bcb19-110">It targets the .NET Framework 4.7.1 or an earlier version and opts out of the legacy accessibility behaviors by adding the following [AppContext Switch](../../../../docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) to the `<runtime>` section of the app.config file and setting it to `false`, as the following example shows.</span></span>

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.Windows.Forms.UseLegacyContextMenuStripSourceControlValue=false"/>
</runtime>
```

<span data-ttu-id="bcb19-111">.NET Framework 4.7.2 以降を対象とするアプリケーションで以前の動作を残す場合、この AppContext スイッチを明示的に `true` に設定することで、以前のソース コントロール値を選択できます。</span><span class="sxs-lookup"><span data-stu-id="bcb19-111">Applications that target the .NET Framework 4.7.2 or later, and want to preserve the legacy behavior can opt in to the use of the legacy source control value by explicitly setting this AppContext switch to `true`.</span></span>

| <span data-ttu-id="bcb19-112">名前</span><span class="sxs-lookup"><span data-stu-id="bcb19-112">Name</span></span>    | <span data-ttu-id="bcb19-113">[値]</span><span class="sxs-lookup"><span data-stu-id="bcb19-113">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="bcb19-114">スコープ</span><span class="sxs-lookup"><span data-stu-id="bcb19-114">Scope</span></span>   | <span data-ttu-id="bcb19-115">エッジ</span><span class="sxs-lookup"><span data-stu-id="bcb19-115">Edge</span></span>        |
| <span data-ttu-id="bcb19-116">バージョン</span><span class="sxs-lookup"><span data-stu-id="bcb19-116">Version</span></span> | <span data-ttu-id="bcb19-117">4.7.2</span><span class="sxs-lookup"><span data-stu-id="bcb19-117">4.7.2</span></span>       |
| <span data-ttu-id="bcb19-118">種類</span><span class="sxs-lookup"><span data-stu-id="bcb19-118">Type</span></span>    | <span data-ttu-id="bcb19-119">再ターゲット中</span><span class="sxs-lookup"><span data-stu-id="bcb19-119">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="bcb19-120">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="bcb19-120">Affected APIs</span></span>

- <xref:System.Windows.Forms.ContextMenuStrip.SourceControl?displayProperty=nameWithType>
