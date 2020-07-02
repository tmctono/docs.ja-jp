---
ms.openlocfilehash: 811b1a91169eeebfa056d9ecdb07d342d3b32d85
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85615714"
---
### <a name="icontobitmap-successfully-converts-icons-with-png-frames-into-bitmap-objects"></a><span data-ttu-id="b3937-101">PNG フレームを含んだアイコンが Icon.ToBitmap によって、Bitmap オブジェクトに正常に変換されます</span><span class="sxs-lookup"><span data-stu-id="b3937-101">Icon.ToBitmap successfully converts icons with PNG frames into Bitmap objects</span></span>

#### <a name="details"></a><span data-ttu-id="b3937-102">説明</span><span class="sxs-lookup"><span data-stu-id="b3937-102">Details</span></span>

<span data-ttu-id="b3937-103">.NET Framework 4.6 以降を対象にしたアプリでは、<xref:System.Drawing.Icon.ToBitmap%2A?displayProperty=nameWithType> メソッドで、PNG フレームを含んだアイコンを正常に Bitmap オブジェクトに変換できます。</span><span class="sxs-lookup"><span data-stu-id="b3937-103">Starting with the apps that target the .NET Framework 4.6, the <xref:System.Drawing.Icon.ToBitmap%2A?displayProperty=nameWithType> method successfully converts icons with PNG frames into Bitmap objects.</span></span><p/><span data-ttu-id="b3937-104">.NET Framework 4.5.2 以前のバージョンを対象としたアプリでは、Icon オブジェクトに PNG フレームが含まれていると、<xref:System.Drawing.Icon.ToBitmap%2A?displayProperty=nameWithType> メソッドが <xref:System.ArgumentOutOfRangeException> の例外をスローします。</span><span class="sxs-lookup"><span data-stu-id="b3937-104">In apps that target the .NET Framework 4.5.2 and earlier versions, the  <xref:System.Drawing.Icon.ToBitmap%2A?displayProperty=nameWithType> method throws an <xref:System.ArgumentOutOfRangeException> exception if the Icon object has PNG frames.</span></span><p/><span data-ttu-id="b3937-105">この変更は、.NET Framework 4.6 を対象として再コンパイルされたアプリのうち、Icon オブジェクトに PNG フレームが含まれている場合は <xref:System.ArgumentOutOfRangeException> をスローするように特別な処理が実装されているアプリに影響します。</span><span class="sxs-lookup"><span data-stu-id="b3937-105">This change affects apps that are recompiled to target the .NET Framework 4.6 and that implement special handling for the <xref:System.ArgumentOutOfRangeException> that is thrown when an Icon object has PNG frames.</span></span> <span data-ttu-id="b3937-106">.NET Framework 4.6 で実行している場合は、正常に変換が行われ、 <xref:System.ArgumentOutOfRangeException> がスローされることはないため、例外ハンドラーは呼び出されません。</span><span class="sxs-lookup"><span data-stu-id="b3937-106">When running under the .NET Framework 4.6, the conversion is successful, an <xref:System.ArgumentOutOfRangeException> is no longer thrown, and therefore the exception handler is no longer invoked.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="b3937-107">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="b3937-107">Suggestion</span></span>

<span data-ttu-id="b3937-108">この動作に不都合がある場合は、次に示す要素を app.config ファイルの `<runtime>` セクションに追加することで、以前の動作を維持できます。</span><span class="sxs-lookup"><span data-stu-id="b3937-108">If this behavior is undesirable, you can retain the previous behavior by adding the following element to the `<runtime>` section of your app.config file:</span></span>

<pre><code class="lang-xml">&lt;AppContextSwitchOverrides&#13;&#10;value=&quot;Switch.System.Drawing.DontSupportPngFramesInIcons=true&quot; /&gt;&#13;&#10;</code></pre>

<span data-ttu-id="b3937-109">app.config ファイルに既に `AppContextSwitchOverrides` 要素が含まれている場合は、次に示すように新しい値を value 属性にマージする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b3937-109">If the app.config file already contains the `AppContextSwitchOverrides` element, the new value should be merged with the value attribute like this:</span></span>

<pre><code class="lang-xml">&lt;AppContextSwitchOverrides&#13;&#10;value=&quot;Switch.System.Drawing.DontSupportPngFramesInIcons=true;&lt;previous key&gt;=&lt;previous value&gt;&quot; /&gt;&#13;&#10;</code></pre>

| <span data-ttu-id="b3937-110">名前</span><span class="sxs-lookup"><span data-stu-id="b3937-110">Name</span></span>    | <span data-ttu-id="b3937-111">値</span><span class="sxs-lookup"><span data-stu-id="b3937-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="b3937-112">スコープ</span><span class="sxs-lookup"><span data-stu-id="b3937-112">Scope</span></span>   | <span data-ttu-id="b3937-113">マイナー</span><span class="sxs-lookup"><span data-stu-id="b3937-113">Minor</span></span>       |
| <span data-ttu-id="b3937-114">バージョン</span><span class="sxs-lookup"><span data-stu-id="b3937-114">Version</span></span> | <span data-ttu-id="b3937-115">4.6</span><span class="sxs-lookup"><span data-stu-id="b3937-115">4.6</span></span>         |
| <span data-ttu-id="b3937-116">種類</span><span class="sxs-lookup"><span data-stu-id="b3937-116">Type</span></span>    | <span data-ttu-id="b3937-117">再ターゲット中</span><span class="sxs-lookup"><span data-stu-id="b3937-117">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="b3937-118">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="b3937-118">Affected APIs</span></span>

- <xref:System.Drawing.Icon.ToBitmap?displayProperty=nameWithType>
