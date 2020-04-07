---
ms.openlocfilehash: 8e077d5cde6e824af5aac3742308593f1d91dd92
ms.sourcegitcommit: a9b8945630426a575ab0a332e568edc807666d1b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/30/2020
ms.locfileid: "80391183"
---
### <a name="static-files-csv-content-type-changed-to-standards-compliant"></a><span data-ttu-id="41f3e-101">静的ファイル: CSV コンテンツ タイプが標準準拠に変更されました</span><span class="sxs-lookup"><span data-stu-id="41f3e-101">Static files: CSV content type changed to standards-compliant</span></span>

<span data-ttu-id="41f3e-102">ASP.NET Core 5.0 では、[静的ファイル ミドルウェア](/aspnet/core/fundamentals/static-files) によって *.csv* ファイルに使用される既定の `Content-Type` 応答ヘッダー値が、標準に準拠した値 `text/csv` に変更されました。</span><span class="sxs-lookup"><span data-stu-id="41f3e-102">In ASP.NET Core 5.0, the default `Content-Type` response header value that the [Static File Middleware](/aspnet/core/fundamentals/static-files) uses for *.csv* files has changed to the standards-compliant value `text/csv`.</span></span>

<span data-ttu-id="41f3e-103">この問題に関するディスカッションについては、[dotnet/aspnetcore#17385](https://github.com/dotnet/AspNetCore/issues/17385) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="41f3e-103">For discussion on this issue, see [dotnet/aspnetcore#17385](https://github.com/dotnet/AspNetCore/issues/17385).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="41f3e-104">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="41f3e-104">Version introduced</span></span>

<span data-ttu-id="41f3e-105">5.0 Preview 1</span><span class="sxs-lookup"><span data-stu-id="41f3e-105">5.0 Preview 1</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="41f3e-106">以前の動作</span><span class="sxs-lookup"><span data-stu-id="41f3e-106">Old behavior</span></span>

<span data-ttu-id="41f3e-107">`Content-Type` ヘッダー値 `application/octet-stream` が使用されていました。</span><span class="sxs-lookup"><span data-stu-id="41f3e-107">The `Content-Type` header value `application/octet-stream` was used.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="41f3e-108">新しい動作</span><span class="sxs-lookup"><span data-stu-id="41f3e-108">New behavior</span></span>

<span data-ttu-id="41f3e-109">`Content-Type` ヘッダー値 `text/csv` が使用されます。</span><span class="sxs-lookup"><span data-stu-id="41f3e-109">The `Content-Type` header value `text/csv` is used.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="41f3e-110">変更理由</span><span class="sxs-lookup"><span data-stu-id="41f3e-110">Reason for change</span></span>

<span data-ttu-id="41f3e-111">[RFC 7111](https://tools.ietf.org/html/rfc7111#section-5.1) 標準に準拠しています。</span><span class="sxs-lookup"><span data-stu-id="41f3e-111">Compliance with the [RFC 7111](https://tools.ietf.org/html/rfc7111#section-5.1) standard.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="41f3e-112">推奨アクション</span><span class="sxs-lookup"><span data-stu-id="41f3e-112">Recommended action</span></span>

<span data-ttu-id="41f3e-113">この変更によってアプリが影響を受ける場合は、ファイル拡張子と MIME の種類のマッピングをカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="41f3e-113">If this change impacts your app, you can customize the file extension-to-MIME type mapping.</span></span> <span data-ttu-id="41f3e-114">MIME の種類 `application/octet-stream` に戻すには、`Startup.Configure` でメソッド呼び出し <xref:Microsoft.AspNetCore.Builder.StaticFileExtensions.UseStaticFiles%2A> を変更します。</span><span class="sxs-lookup"><span data-stu-id="41f3e-114">To revert to the `application/octet-stream` MIME type, modify the <xref:Microsoft.AspNetCore.Builder.StaticFileExtensions.UseStaticFiles%2A> method call in `Startup.Configure`.</span></span> <span data-ttu-id="41f3e-115">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="41f3e-115">For example:</span></span>

```csharp
var provider = new FileExtensionContentTypeProvider();
provider.Mappings[".csv"] = MediaTypeNames.Application.Octet;

app.UseStaticFiles(new StaticFileOptions
{
    ContentTypeProvider = provider
});
```

<span data-ttu-id="41f3e-116">マッピングのカスタマイズの詳細については、「[FileExtensionContentTypeProvider](/aspnet/core/fundamentals/static-files#fileextensioncontenttypeprovider)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="41f3e-116">For more information on customizing the mapping, see [FileExtensionContentTypeProvider](/aspnet/core/fundamentals/static-files#fileextensioncontenttypeprovider).</span></span>

#### <a name="category"></a><span data-ttu-id="41f3e-117">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="41f3e-117">Category</span></span>

<span data-ttu-id="41f3e-118">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="41f3e-118">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="41f3e-119">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="41f3e-119">Affected APIs</span></span>

<xref:Microsoft.AspNetCore.StaticFiles.FileExtensionContentTypeProvider?displayProperty=nameWithType>

<!--

#### Affected APIs

`T:Microsoft.AspNetCore.StaticFiles.FileExtensionContentTypeProvider`

-->
