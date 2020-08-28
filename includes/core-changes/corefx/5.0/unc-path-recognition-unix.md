---
ms.openlocfilehash: 0246f325a6274082b7fb0d5590cec7c80687ae85
ms.sourcegitcommit: ef86c24c418439b8bb5e3e7d64bbdbe5e11c3e9c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/21/2020
ms.locfileid: "88720198"
---
### <a name="uri-recognition-of-unc-paths-on-unix"></a><span data-ttu-id="49740-101">Unix での UNC パスの URI 認識</span><span class="sxs-lookup"><span data-stu-id="49740-101">Uri recognition of UNC paths on Unix</span></span>

<span data-ttu-id="49740-102">Unix オペレーティング システム上で、2 つのスラッシュ (`//`) で始まる文字列が <xref:System.Uri> クラスによって UNC (汎用名前付け規則) パスとして認識されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="49740-102">The <xref:System.Uri> class now recognizes strings that start with two forward slashes (`//`) as universal naming convention (UNC) paths on Unix operating systems.</span></span> <span data-ttu-id="49740-103">この変更により、すべてのプラットフォームでそのような文字列の動作の一貫性が確保されるようになります。</span><span class="sxs-lookup"><span data-stu-id="49740-103">This change makes the behavior for such strings consistent across all platforms.</span></span>

#### <a name="change-description"></a><span data-ttu-id="49740-104">変更の説明</span><span class="sxs-lookup"><span data-stu-id="49740-104">Change description</span></span>

<span data-ttu-id="49740-105">以前のバージョンの .NET では、Unix オペレーティング システム上で、2 つのスラッシュで始まる文字列 (`//contoso`など) が <xref:System.Uri> クラスによって絶対ファイル パスとして認識されます。</span><span class="sxs-lookup"><span data-stu-id="49740-105">In previous versions of .NET, the <xref:System.Uri> class recognizes strings that start with with two forward slashes, for example, `//contoso`, as absolute file paths on Unix operating systems.</span></span> <span data-ttu-id="49740-106">ただし、Windows では、そのような文字列は UNC パスとして認識されます。</span><span class="sxs-lookup"><span data-stu-id="49740-106">However, on Windows, such strings are recognized as UNC paths.</span></span>

<span data-ttu-id="49740-107">.NET 5.0 以降、Unix を含むすべてのプラットフォーム上で、2 つのスラッシュで始まる文字列は <xref:System.Uri> クラスによって UNC パスとして認識されます。</span><span class="sxs-lookup"><span data-stu-id="49740-107">Starting in .NET 5.0,  the <xref:System.Uri> class recognizes strings that start with with two forward slashes as UNC paths on all platforms, including Unix.</span></span> <span data-ttu-id="49740-108">さらに、プロパティは UNC セマンティクスに従って動作します。</span><span class="sxs-lookup"><span data-stu-id="49740-108">In addition, properties behave according to UNC semantics:</span></span>

- <span data-ttu-id="49740-109"><xref:System.Uri.IsUnc?displayProperty=nameWithType> は、`true` を返します。</span><span class="sxs-lookup"><span data-stu-id="49740-109"><xref:System.Uri.IsUnc?displayProperty=nameWithType> returns `true`.</span></span>
- <span data-ttu-id="49740-110">パス内の円記号は、スラッシュに置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="49740-110">Backslashes in the path are replaced with forward slashes.</span></span> <span data-ttu-id="49740-111">たとえば、`//first\second` を `//first/second` にします。</span><span class="sxs-lookup"><span data-stu-id="49740-111">For example, `//first\second` becomes `//first/second`.</span></span>
- <span data-ttu-id="49740-112"><xref:System.Uri.LocalPath?displayProperty=nameWithType> によって文字のパーセントエンコードは行われません。</span><span class="sxs-lookup"><span data-stu-id="49740-112"><xref:System.Uri.LocalPath?displayProperty=nameWithType> doesn't percent-encode characters.</span></span> <span data-ttu-id="49740-113">たとえば、`//first/\uFFF0` は `//first/%EF%BF%B0` に変換 "*されません*"。</span><span class="sxs-lookup"><span data-stu-id="49740-113">For example, `//first/\uFFF0` is *not* converted to `//first/%EF%BF%B0`.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="49740-114">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="49740-114">Version introduced</span></span>

<span data-ttu-id="49740-115">5.0</span><span class="sxs-lookup"><span data-stu-id="49740-115">5.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="49740-116">推奨アクション</span><span class="sxs-lookup"><span data-stu-id="49740-116">Recommended action</span></span>

<span data-ttu-id="49740-117">開発者側では、何も行う必要はありません。</span><span class="sxs-lookup"><span data-stu-id="49740-117">No action is required on the part of the developer.</span></span>

#### <a name="category"></a><span data-ttu-id="49740-118">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="49740-118">Category</span></span>

<span data-ttu-id="49740-119">Core .NET ライブラリ</span><span class="sxs-lookup"><span data-stu-id="49740-119">Core .NET libraries</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="49740-120">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="49740-120">Affected APIs</span></span>

- <xref:System.Uri?displayProperty=fullName>

<!--

#### Affected APIs

- `T:System.Uri`

-->
