---
ms.openlocfilehash: faf9459ab9002e6149560e2a3452265fa246bf6b
ms.sourcegitcommit: ef86c24c418439b8bb5e3e7d64bbdbe5e11c3e9c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/21/2020
ms.locfileid: "88720200"
---
### <a name="uri-paths-with-non-ascii-characters-parse-correctly-on-unix"></a><span data-ttu-id="db969-101">Unix 上で ASCII 以外の文字を含む URI パスが正しく解析される</span><span class="sxs-lookup"><span data-stu-id="db969-101">URI paths with non-ASCII characters parse correctly on Unix</span></span>

<span data-ttu-id="db969-102"><xref:System.Uri?displayProperty=fullName> クラス内のバグが修正され、Unix プラットフォーム上で ASCII 以外の文字を含む絶対 URI パスが正しく解析されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="db969-102">A bug was fixed in the <xref:System.Uri?displayProperty=fullName> class such that absolute URI paths that contain non-ASCII characters now parse correctly on Unix platforms.</span></span>

#### <a name="change-description"></a><span data-ttu-id="db969-103">変更の説明</span><span class="sxs-lookup"><span data-stu-id="db969-103">Change description</span></span>

<span data-ttu-id="db969-104">以前のバージョンの .NET では、Unix プラットフォーム上で ASCII 以外の文字を含む絶対 URI パスが正しく解析されず、パスのセグメントに重複が生じます。</span><span class="sxs-lookup"><span data-stu-id="db969-104">In previous versions of .NET, absolute URI paths that contain non-ASCII characters are parsed incorrectly on Unix platforms, and segments of the path are duplicated.</span></span> <span data-ttu-id="db969-105">(絶対パスとは、"/" で始まるものです)。 .NET 5.0 ではこの解析の問題が修正されました。</span><span class="sxs-lookup"><span data-stu-id="db969-105">(Absolute paths are those that start with "/".) The parsing issue has been fixed for .NET 5.0.</span></span> <span data-ttu-id="db969-106">以前のバージョンの .NET から .NET 5.0 以降に移行すると、<xref:System.Uri.AbsoluteUri?displayProperty=nameWithType>、<xref:System.Uri.ToString?displayProperty=nameWithType>、およびその他の <xref:System.Uri> メンバーによって生成され出力される値は異なるものとなります。</span><span class="sxs-lookup"><span data-stu-id="db969-106">If you move from a previous version of .NET to .NET 5.0 or later, you'll get different values produced by <xref:System.Uri.AbsoluteUri?displayProperty=nameWithType>, <xref:System.Uri.ToString?displayProperty=nameWithType>, and other <xref:System.Uri> members.</span></span>

<span data-ttu-id="db969-107">Unix 上で実行する場合は、次のコードの出力を検討してください。</span><span class="sxs-lookup"><span data-stu-id="db969-107">Consider the output of the following code when run on Unix.</span></span>

```csharp
var myUri = new Uri("/üri");

Console.WriteLine($"AbsoluteUri: {myUri.AbsoluteUri}");
Console.WriteLine($"ToString: {myUri.ToString()}");
```

<span data-ttu-id="db969-108">以前のバージョンの .NET での出力:</span><span class="sxs-lookup"><span data-stu-id="db969-108">Output on previous .NET version:</span></span>

```text
AbsoluteUri: /%C3%BCri/%C3%BCri
ToString: /üri/üri
```

<span data-ttu-id="db969-109">.NET 5.0 以降のバージョンでの出力:</span><span class="sxs-lookup"><span data-stu-id="db969-109">Output on .NET 5.0 or later version:</span></span>

```text
AbsoluteUri: /%C3%BCri
ToString: /üri
```

#### <a name="version-introduced"></a><span data-ttu-id="db969-110">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="db969-110">Version introduced</span></span>

<span data-ttu-id="db969-111">5.0</span><span class="sxs-lookup"><span data-stu-id="db969-111">5.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="db969-112">推奨アクション</span><span class="sxs-lookup"><span data-stu-id="db969-112">Recommended action</span></span>

<span data-ttu-id="db969-113">重複したパス セグメントの発生が予期される、および明らかであるコードがある場合は、そのコードを削除できます。</span><span class="sxs-lookup"><span data-stu-id="db969-113">If you have code that expects and accounts for the duplicated path segments, you can remove that code.</span></span>

#### <a name="category"></a><span data-ttu-id="db969-114">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="db969-114">Category</span></span>

<span data-ttu-id="db969-115">Core .NET ライブラリ</span><span class="sxs-lookup"><span data-stu-id="db969-115">Core .NET libraries</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="db969-116">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="db969-116">Affected APIs</span></span>

- <xref:System.Uri?displayProperty=fullName>

<!--

#### Affected APIs

- `T:System.Uri`

-->
