---
ms.openlocfilehash: 9520f8c6b6671917f5694bc602293a00e2dab82d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2020
ms.locfileid: "74568215"
---
### <a name="ziparchiveentry-no-longer-handles-archives-with-inconsistent-entry-sizes"></a><span data-ttu-id="673ec-101">ZipArchiveEntry による、エントリ サイズに一貫性のないアーカイブ処理の中止</span><span class="sxs-lookup"><span data-stu-id="673ec-101">ZipArchiveEntry no longer handles archives with inconsistent entry sizes</span></span>

<span data-ttu-id="673ec-102">Zip アーカイブは、圧縮されているサイズと圧縮されていないサイズの両方を、中央ディレクトリとローカル ヘッダーに一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="673ec-102">Zip archives list both compressed size and uncompressed size in the central directory and local header.</span></span>  <span data-ttu-id="673ec-103">また、エントリ データ自体のサイズも示されます。</span><span class="sxs-lookup"><span data-stu-id="673ec-103">The entry data itself also indicates its size.</span></span>  <span data-ttu-id="673ec-104">.NET Core 2.2 以前のバージョンでは、これらの値の一貫性はチェックされませんでした。</span><span class="sxs-lookup"><span data-stu-id="673ec-104">In .NET Core 2.2 and earlier versions, these values were never checked for consistency.</span></span> <span data-ttu-id="673ec-105">.NET Core 3.0 より、これが開始します。</span><span class="sxs-lookup"><span data-stu-id="673ec-105">Starting with .NET Core 3.0, they now are.</span></span>

#### <a name="change-description"></a><span data-ttu-id="673ec-106">変更の説明</span><span class="sxs-lookup"><span data-stu-id="673ec-106">Change description</span></span>

<span data-ttu-id="673ec-107">.NET Core 2.2 以前のバージョンでは、<xref:System.IO.Compression.ZipArchiveEntry.Open?displayProperty=nameWithType> はローカル ヘッダーが zip ファイルの中央ヘッダーと一致しない場合でも成功します。</span><span class="sxs-lookup"><span data-stu-id="673ec-107">In .NET Core 2.2 and earlier versions, <xref:System.IO.Compression.ZipArchiveEntry.Open?displayProperty=nameWithType> succeeds even if the local header disagrees with the central header of the zip file.</span></span> <span data-ttu-id="673ec-108">圧縮されたストリームの末尾に達するまで、データは圧縮解除されます。これは、その長さが、中央ディレクトリ/ローカル ヘッダーに示されている圧縮されていないファイル サイズを超えている場合も同様です。</span><span class="sxs-lookup"><span data-stu-id="673ec-108">Data is decompressed until the end of the compressed stream is reached, even if its length exceeds the uncompressed file size listed in the central directory/local header.</span></span>

<span data-ttu-id="673ec-109">.NET Core 3.0 以降では、<xref:System.IO.Compression.ZipArchiveEntry.Open?displayProperty=nameWithType> メソッドによって、エントリの圧縮されたサイズと圧縮されていないサイズがローカル ヘッダーと中央ヘッダーで一致することが確認されます。</span><span class="sxs-lookup"><span data-stu-id="673ec-109">Starting with .NET Core 3.0, the <xref:System.IO.Compression.ZipArchiveEntry.Open?displayProperty=nameWithType> method checks that local header and central header agree on compressed and uncompressed sizes of an entry.</span></span>  <span data-ttu-id="673ec-110">そうでない場合、アーカイブのローカル ヘッダーやデータ記述子に zip ファイルの中央ディレクトリと一致しないサイズが一覧表示されている場合、メソッドによって <xref:System.IO.InvalidDataException> がスローされます。</span><span class="sxs-lookup"><span data-stu-id="673ec-110">If they do not, the method throws an <xref:System.IO.InvalidDataException> if the archive's local header and/or data descriptor list sizes that disagree with the central directory of the zip file.</span></span> <span data-ttu-id="673ec-111">エントリを読み取るときに、圧縮解除されたデータは、ヘッダーに一覧表示されている圧縮されていないファイル サイズにまで切り詰められます。</span><span class="sxs-lookup"><span data-stu-id="673ec-111">When reading an entry, decompressed data is truncated to the uncompressed file size listed in the header.</span></span>

<span data-ttu-id="673ec-112">この変更は、<xref:System.IO.Compression.ZipArchiveEntry> がそのデータのサイズを正しく表し、そのデータ量だけが読み取られるようにするために行われました。</span><span class="sxs-lookup"><span data-stu-id="673ec-112">This change was made to ensure that a <xref:System.IO.Compression.ZipArchiveEntry> correctly represents the size of its data and that only that amount of data is read.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="673ec-113">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="673ec-113">Version introduced</span></span>

<span data-ttu-id="673ec-114">3.0</span><span class="sxs-lookup"><span data-stu-id="673ec-114">3.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="673ec-115">推奨アクション</span><span class="sxs-lookup"><span data-stu-id="673ec-115">Recommended action</span></span>

<span data-ttu-id="673ec-116">この問題が発生している zip アーカイブをすべて再パッケージ化します。</span><span class="sxs-lookup"><span data-stu-id="673ec-116">Repackage any zip archive that exhibits these problems.</span></span>

#### <a name="category"></a><span data-ttu-id="673ec-117">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="673ec-117">Category</span></span>

<span data-ttu-id="673ec-118">CoreFx</span><span class="sxs-lookup"><span data-stu-id="673ec-118">CoreFx</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="673ec-119">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="673ec-119">Affected APIs</span></span>

- <xref:System.IO.Compression.ZipArchiveEntry.Open?displayProperty=nameWithType>
- <xref:System.IO.Compression.ZipFileExtensions.ExtractToDirectory%2A?displayProperty=nameWithType>
- <xref:System.IO.Compression.ZipFileExtensions.ExtractToFile%2A?displayProperty=nameWithType>
- <xref:System.IO.Compression.ZipFile.ExtractToDirectory%2A?displayProperty=nameWithType>

<!--

### Affected APIs

`M:System.IO.Compression.ZipArchiveEntry.Open`
`Overload:System.IO.Compression.ZipFileExtensions.ExtractToDirectory%2A`
`Overload:System.IO.Compression.ZipFileExtensions.ExtractToFile%2A`
`Overload:System.IO.Compression.ZipFile.ExtractToDirectory%2A`

-->
