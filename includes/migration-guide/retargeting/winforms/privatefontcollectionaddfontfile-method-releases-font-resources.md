---
ms.openlocfilehash: 53ded5ae6e5a025fc7992da099c3481587bb6f31
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614905"
---
### <a name="privatefontcollectionaddfontfile-method-releases-font-resources"></a><span data-ttu-id="524c9-101">PrivateFontCollection.AddFontFile メソッドが Font リソースを解放する</span><span class="sxs-lookup"><span data-stu-id="524c9-101">PrivateFontCollection.AddFontFile method releases Font resources</span></span>

#### <a name="details"></a><span data-ttu-id="524c9-102">説明</span><span class="sxs-lookup"><span data-stu-id="524c9-102">Details</span></span>

<span data-ttu-id="524c9-103">.NET Framework 4.7.1 およびそれより前のバージョンの <xref:System.Drawing.Text.PrivateFontCollection?displayProperty=nameWithType> クラスは、<xref:System.Drawing.Text.PrivateFontCollection.AddFontFile(System.String)> メソッドを使用してこのコレクションに追加された <xref:System.Drawing.Font> オブジェクトの <xref:System.Drawing.Text.PrivateFontCollection> が破棄された後も、GDI+ フォント リソースを解放しません。</span><span class="sxs-lookup"><span data-stu-id="524c9-103">In the .NET Framework 4.7.1 and previous versions, the <xref:System.Drawing.Text.PrivateFontCollection?displayProperty=nameWithType> class does not release the GDI+ font resources after the <xref:System.Drawing.Text.PrivateFontCollection> is disposed for <xref:System.Drawing.Font> objects that are added to this collection using the <xref:System.Drawing.Text.PrivateFontCollection.AddFontFile(System.String)> method.</span></span> <span data-ttu-id="524c9-104">.NET Framework 4.7.2 およびそれより降の <xref:System.Drawing.Text.FontCollection.Dispose%2A> は、ファイルとしてコレクションに追加された GDI+ フォントを解放します。</span><span class="sxs-lookup"><span data-stu-id="524c9-104">In the .NET Framework 4.7.2 and later <xref:System.Drawing.Text.FontCollection.Dispose%2A> releases the GDI+ fonts that were added to the collection as files.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="524c9-105">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="524c9-105">Suggestion</span></span>

<span data-ttu-id="524c9-106">**これらの変更を選択する方法と選択しない方法** アプリケーションでこれらの変更を利用するには、.NET Framework 4.7.2 以降で実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="524c9-106">**How to opt in or out of these changes** In order for an application to benefit from these changes, it must run on the .NET Framework 4.7.2 or later.</span></span> <span data-ttu-id="524c9-107">アプリケーションは、次のいずれかの方法でこれらの変更を利用できます。</span><span class="sxs-lookup"><span data-stu-id="524c9-107">The application can benefit from these changes in either of the following ways:</span></span>

- <span data-ttu-id="524c9-108">.NET Framework 4.7.2 を対象にして再コンパイルします。</span><span class="sxs-lookup"><span data-stu-id="524c9-108">It is recompiled to target the .NET Framework 4.7.2.</span></span> <span data-ttu-id="524c9-109">.NET Framework 4.7.2 以降を対象とする Windows フォーム アプリケーションでは、この変更が既定で有効になります。</span><span class="sxs-lookup"><span data-stu-id="524c9-109">This change is enabled by default on Windows Forms applications that target the .NET Framework 4.7.2 or later.</span></span>
- <span data-ttu-id="524c9-110">.NET Framework 4.7.1 以前を対象にして、下の例のように、app.config ファイルの `<runtime>` セクションに次の [AppContext スイッチ](https://docs.microsoft.com/dotnet/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element)を追加し、それを `false` に設定することで、以前のアクセシビリティ動作を無効にします。</span><span class="sxs-lookup"><span data-stu-id="524c9-110">It targets the .NET Framework 4.7.1 or an earlier version and opts out of the legacy accessibility behaviors by adding the following [AppContext Switch](https://docs.microsoft.com/dotnet/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element) to the `<runtime>` section of the app.config file and setting it to `false`, as the following example shows.</span></span>

<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Drawing.Text.DoNotRemoveGdiFontsResourcesFromFontCollection=false&quot;/&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>

<span data-ttu-id="524c9-111">.NET Framework 4.7.2 以降を対象とするアプリケーションで以前の動作を残す場合、この AppContext スイッチを明示的に `true` に設定することで、フォント リソースを解放しないようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="524c9-111">Applications that target the .NET Framework 4.7.2 or later, and want to preserve the legacy behavior can opt in to not release font resources by explicitly setting this AppContext switch to `true`.</span></span>

| <span data-ttu-id="524c9-112">名前</span><span class="sxs-lookup"><span data-stu-id="524c9-112">Name</span></span>    | <span data-ttu-id="524c9-113">[値]</span><span class="sxs-lookup"><span data-stu-id="524c9-113">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="524c9-114">スコープ</span><span class="sxs-lookup"><span data-stu-id="524c9-114">Scope</span></span>   | <span data-ttu-id="524c9-115">エッジ</span><span class="sxs-lookup"><span data-stu-id="524c9-115">Edge</span></span>        |
| <span data-ttu-id="524c9-116">バージョン</span><span class="sxs-lookup"><span data-stu-id="524c9-116">Version</span></span> | <span data-ttu-id="524c9-117">4.7.2</span><span class="sxs-lookup"><span data-stu-id="524c9-117">4.7.2</span></span>       |
| <span data-ttu-id="524c9-118">種類</span><span class="sxs-lookup"><span data-stu-id="524c9-118">Type</span></span>    | <span data-ttu-id="524c9-119">再ターゲット中</span><span class="sxs-lookup"><span data-stu-id="524c9-119">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="524c9-120">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="524c9-120">Affected APIs</span></span>

- <xref:System.Drawing.Text.PrivateFontCollection.AddFontFile(System.String)?displayProperty=nameWithType>
- <xref:System.Drawing.Text.FontCollection.Dispose?displayProperty=nameWithType>
