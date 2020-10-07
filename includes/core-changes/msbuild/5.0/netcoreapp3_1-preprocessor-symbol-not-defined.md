---
ms.openlocfilehash: de35df21d1887bc95a3106edba312c53daad8b68
ms.sourcegitcommit: 4d45bda8cd9558ea8af4be591e3d5a29360c1ece
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/02/2020
ms.locfileid: "91654740"
---
### <a name="netcoreapp3_1-preprocessor-symbol-is-not-defined-when-targeting-net-5"></a><span data-ttu-id="1e6ef-101">.NET 5 を対象とする場合の NETCOREAPP3_1 プリプロセッサ シンボルが定義されていない</span><span class="sxs-lookup"><span data-stu-id="1e6ef-101">NETCOREAPP3_1 preprocessor symbol is not defined when targeting .NET 5</span></span>

<span data-ttu-id="1e6ef-102">.NET 5.0 RC2 以降のバージョンでは、プロジェクトでのプリプロセッサ シンボルの定義は対象とするバージョンに対してのみ行われ、以前のバージョンでは行われなくなります。</span><span class="sxs-lookup"><span data-stu-id="1e6ef-102">In .NET 5.0 RC2 and later versions, projects no longer define preprocessor symbols for earlier versions, but only for the version that they target.</span></span> <span data-ttu-id="1e6ef-103">これは、.NET Core 1.0 - 3.1 と同じ動作です。</span><span class="sxs-lookup"><span data-stu-id="1e6ef-103">This is the same behavior as .NET Core 1.0 - 3.1.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="1e6ef-104">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="1e6ef-104">Version introduced</span></span>

<span data-ttu-id="1e6ef-105">5.0 RC2</span><span class="sxs-lookup"><span data-stu-id="1e6ef-105">5.0 RC2</span></span>

#### <a name="change-description"></a><span data-ttu-id="1e6ef-106">変更内容</span><span class="sxs-lookup"><span data-stu-id="1e6ef-106">Change description</span></span>

<span data-ttu-id="1e6ef-107">.NET 5.0 Preview 7 から RC1 では、`net5.0` を対象とするプロジェクトで `NETCOREAPP3_1` と `NET5_0` の両方のプリプロセッサ シンボルが定義されます。</span><span class="sxs-lookup"><span data-stu-id="1e6ef-107">In .NET 5.0 preview 7 through RC1, projects that target `net5.0` define both `NETCOREAPP3_1` and `NET5_0` preprocessor symbols.</span></span> <span data-ttu-id="1e6ef-108">この動作変更は、.NET 5.0 以降で、条件付きコンパイルの[シンボルが累積になる](https://github.com/dotnet/designs/blob/main/accepted/2020/net5/net5.md#preprocessor-symbols)ことを意図したものでした。</span><span class="sxs-lookup"><span data-stu-id="1e6ef-108">The intent behind this behavior change was that starting with .NET 5.0, conditional compilation [symbols would be cumulative](https://github.com/dotnet/designs/blob/main/accepted/2020/net5/net5.md#preprocessor-symbols).</span></span>

<span data-ttu-id="1e6ef-109">.NET 5.0 RC2 以降では、プロジェクトは、以前のバージョンではなく、対象となるターゲット フレームワーク モニカー (TFM) のみに対するシンボルを定義します。</span><span class="sxs-lookup"><span data-stu-id="1e6ef-109">In .NET 5.0 RC2 and later, projects only define symbols for the target framework monikers (TFM) that it targets and not for any earlier versions.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="1e6ef-110">変更理由</span><span class="sxs-lookup"><span data-stu-id="1e6ef-110">Reason for change</span></span>

<span data-ttu-id="1e6ef-111">Preview 7 からの変更は、お客様からのフィードバックにより元に戻されました。</span><span class="sxs-lookup"><span data-stu-id="1e6ef-111">The change from preview 7 was reverted due to customer feedback.</span></span> <span data-ttu-id="1e6ef-112">以前のバージョンのシンボルの定義はお客様を驚かせ、混乱させました。C# のコンパイラにバグがあったと考えたお客様もいました。</span><span class="sxs-lookup"><span data-stu-id="1e6ef-112">Defining symbols for earlier versions surprised and confused customers, and some assumed it was a bug in the C# compiler.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="1e6ef-113">推奨アクション</span><span class="sxs-lookup"><span data-stu-id="1e6ef-113">Recommended action</span></span>

<span data-ttu-id="1e6ef-114">プロジェクトが `net5.0` 以上を対象とするときに `NETCOREAPP3_1` が定義されていることを `#if` ロジックで前提としていないことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="1e6ef-114">Make sure that your `#if` logic doesn't assume that `NETCOREAPP3_1` is defined when the project targets `net5.0` or higher.</span></span> <span data-ttu-id="1e6ef-115">代わりに、プロジェクトが `netcoreapp3.1` を明示的に対象としている場合は `NETCOREAPP3_1` のみが定義されることを前提としてください。</span><span class="sxs-lookup"><span data-stu-id="1e6ef-115">Instead, assume that `NETCOREAPP3_1` is only defined when the project explicitly targets `netcoreapp3.1`.</span></span>

<span data-ttu-id="1e6ef-116">たとえば、プロジェクトが .NET Core 2.1 および .NET Core 3.1 のマルチターゲットで、.NET Core 3.1 で導入された API を呼び出す場合、`#if` ロジックは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="1e6ef-116">For example, if your project multitargets for .NET Core 2.1 and .NET Core 3.1 and you call APIs that were introduced in .NET Core 3.1, your `#if` logic should look as follows:</span></span>

```csharp
#if NETCOREAPP2_1 || NETCOREAPP3_0
    // Fallback behavior for old versions.
#elif NETCOREAPP
    // Behavior for .NET Core 3.1 and later.
#endif
```

#### <a name="category"></a><span data-ttu-id="1e6ef-117">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="1e6ef-117">Category</span></span>

<span data-ttu-id="1e6ef-118">MSBuild</span><span class="sxs-lookup"><span data-stu-id="1e6ef-118">MSBuild</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="1e6ef-119">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="1e6ef-119">Affected APIs</span></span>

<span data-ttu-id="1e6ef-120">N/A</span><span class="sxs-lookup"><span data-stu-id="1e6ef-120">N/A</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
