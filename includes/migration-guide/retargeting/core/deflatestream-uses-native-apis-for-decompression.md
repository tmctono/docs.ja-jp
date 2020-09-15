---
ms.openlocfilehash: 7e42a294b151d07a6fdc61308cdf92df7a31a1d6
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614721"
---
### <a name="deflatestream-uses-native-apis-for-decompression"></a><span data-ttu-id="93d74-101">DeflateStream で圧縮解除のためにネイティブ API が使用される</span><span class="sxs-lookup"><span data-stu-id="93d74-101">DeflateStream uses native APIs for decompression</span></span>

#### <a name="details"></a><span data-ttu-id="93d74-102">説明</span><span class="sxs-lookup"><span data-stu-id="93d74-102">Details</span></span>

<span data-ttu-id="93d74-103">.NET Framework 4.7.2 以降では、`T:System.IO.Compression.DeflateStream` クラスの圧縮解除の実装の際に、既定でネイティブの Windows API を使用するように変更されました。</span><span class="sxs-lookup"><span data-stu-id="93d74-103">Starting with the .NET Framework 4.7.2, the implementation of decompression in the `T:System.IO.Compression.DeflateStream` class has changed to use native Windows APIs by default.</span></span> <span data-ttu-id="93d74-104">通常は、これによりパフォーマンスが大幅に改善されます。</span><span class="sxs-lookup"><span data-stu-id="93d74-104">Typically, this results in a substantial performance improvement.</span></span> <span data-ttu-id="93d74-105">.NET Framework バージョン 4.7.2 以降を対象とするすべての .NET アプリケーションでは、ネイティブ実装が使用されます。この変更により、次のように動作にいくつか違いが生じる場合があります。</span><span class="sxs-lookup"><span data-stu-id="93d74-105">All .NET applications targeting the .NET Framework version 4.7.2 or higher use the native implementation.This change might result in some differences in behavior, which include:</span></span>

- <span data-ttu-id="93d74-106">例外メッセージが異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="93d74-106">Exception messages may be different.</span></span> <span data-ttu-id="93d74-107">ただし、スローされる例外の種類は変わりません。</span><span class="sxs-lookup"><span data-stu-id="93d74-107">However, the type of exception thrown remains the same.</span></span>
- <span data-ttu-id="93d74-108">操作を完了するのに十分なメモリがないなど、いくつかの特殊な状況が異なる方法で処理される場合があります。</span><span class="sxs-lookup"><span data-stu-id="93d74-108">Some special situations, such as not having enough memory to complete an operation, may be handled differently.</span></span>
- <span data-ttu-id="93d74-109">gzip ヘッダーの解析には、次のような違いが確認されています (注: 圧縮解除のために設定されている `GZipStream` のみが影響します)。</span><span class="sxs-lookup"><span data-stu-id="93d74-109">There are known differences for parsing gzip header (note: only `GZipStream` set for decompression is affected):</span></span>
- <span data-ttu-id="93d74-110">無効なヘッダーの解析時の例外がさまざまなタイミングでスローされる場合があります。</span><span class="sxs-lookup"><span data-stu-id="93d74-110">Exceptions when parsing invalid headers may be thrown at different times.</span></span>
- <span data-ttu-id="93d74-111">ネイティブ実装では、gzip ヘッダー内で予約されているいくつかのフラグの値 (つまり、[FLG](http://www.zlib.org/rfc-gzip.html#header-trailer)) が、仕様に基づいて設定されるように強制されます。これにより、以前は無効な値が無視されていた例外がスローされる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="93d74-111">The native implementation enforces that values for some reserved flags inside the gzip header (i.e. [FLG](http://www.zlib.org/rfc-gzip.html#header-trailer)) are set according to the specification, which may cause it to throw an exception where previously invalid values were ignored.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="93d74-112">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="93d74-112">Suggestion</span></span>

<span data-ttu-id="93d74-113">ネイティブ API での圧縮解除がアプリの動作に悪影響を与えている場合は、app.config ファイルの `runtime` セクションに `Switch.System.IO.Compression.DoNotUseNativeZipLibraryForDecompression` スイッチを追加して `true` に設定することで、この機能の選択を解除できます。</span><span class="sxs-lookup"><span data-stu-id="93d74-113">If decompression with native APIs has adversely affected the behavior of your app, you can opt out of this feature by adding the `Switch.System.IO.Compression.DoNotUseNativeZipLibraryForDecompression` switch to the `runtime` section of your app.config file and setting it to `true`:</span></span>

```xml
<?xml version="1.0" encoding="utf-8" ?>
<configuration>
  <runtime>
    <AppContextSwitchOverrides value="Switch.System.IO.Compression.DoNotUseNativeZipLibraryForDecompression=true" />
  </runtime>
</configuration>
```

| <span data-ttu-id="93d74-114">名前</span><span class="sxs-lookup"><span data-stu-id="93d74-114">Name</span></span>    | <span data-ttu-id="93d74-115">[値]</span><span class="sxs-lookup"><span data-stu-id="93d74-115">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="93d74-116">スコープ</span><span class="sxs-lookup"><span data-stu-id="93d74-116">Scope</span></span>   | <span data-ttu-id="93d74-117">マイナー</span><span class="sxs-lookup"><span data-stu-id="93d74-117">Minor</span></span>       |
| <span data-ttu-id="93d74-118">バージョン</span><span class="sxs-lookup"><span data-stu-id="93d74-118">Version</span></span> | <span data-ttu-id="93d74-119">4.7.2</span><span class="sxs-lookup"><span data-stu-id="93d74-119">4.7.2</span></span>       |
| <span data-ttu-id="93d74-120">種類</span><span class="sxs-lookup"><span data-stu-id="93d74-120">Type</span></span>    | <span data-ttu-id="93d74-121">再ターゲット中</span><span class="sxs-lookup"><span data-stu-id="93d74-121">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="93d74-122">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="93d74-122">Affected APIs</span></span>

- <xref:System.IO.Compression.DeflateStream?displayProperty=nameWithType>
- <xref:System.IO.Compression.GZipStream?displayProperty=nameWithType>
