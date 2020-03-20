---
ms.openlocfilehash: db1d09c8c9e606b5327a42977a74a74703282d84
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2020
ms.locfileid: "74568100"
---
### <a name="net-core-30-follows-unicode-best-practices-when-replacing-ill-formed-utf-8-byte-sequences"></a><span data-ttu-id="35cc8-101">.NET Core 3.0 は不正な形式の UTF-8 バイト シーケンスを置換するときに Unicode のベスト プラクティスに従う</span><span class="sxs-lookup"><span data-stu-id="35cc8-101">.NET Core 3.0 follows Unicode best practices when replacing ill-formed UTF-8 byte sequences</span></span>

<span data-ttu-id="35cc8-102"><xref:System.Text.UTF8Encoding> クラスで、バイトから文字へのコード変換中に不適切な形式の UTF-8 バイト シーケンスが検出された場合、そのシーケンスは出力文字列内で '�' (U+FFFD REPLACEMENT CHARACTER) 文字に置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="35cc8-102">When the <xref:System.Text.UTF8Encoding> class encounters an ill-formed UTF-8 byte sequence during a byte-to-character transcoding operation, it will replace that sequence with a '�' (U+FFFD REPLACEMENT CHARACTER) character in the output string.</span></span> <span data-ttu-id="35cc8-103">.NET Core 3.0 では、コード変換の操作中にこの置換を実行するための Unicode ベスト プラクティスに従うことで、以前のバージョンの .NET Core と .NET Framework との差別化が行われています。</span><span class="sxs-lookup"><span data-stu-id="35cc8-103">.NET Core 3.0 differs from previous versions of .NET Core and the .NET Framework by following the Unicode best practice for performing this replacement during the transcoding operation.</span></span>

<span data-ttu-id="35cc8-104">これは、新しい <xref:System.Text.Unicode.Utf8?displayProperty=nameWithType> 型および <xref:System.Text.Rune?displayProperty=nameWithType> 型の使用を含め、.NET 全体での UTF-8 の処理を向上させようとする、より大きな取り組みの一環です。</span><span class="sxs-lookup"><span data-stu-id="35cc8-104">This is part of a larger effort to improve UTF-8 handling throughout .NET, including by the new <xref:System.Text.Unicode.Utf8?displayProperty=nameWithType> and <xref:System.Text.Rune?displayProperty=nameWithType> types.</span></span> <span data-ttu-id="35cc8-105"><xref:System.Text.UTF8Encoding> 型では、新しく導入された型と一致する出力が生成されるよう、エラー処理のメカニズムが向上しています。</span><span class="sxs-lookup"><span data-stu-id="35cc8-105">The <xref:System.Text.UTF8Encoding> type was given improved error handling mechanics so that it produces output consistent with the newly introduced types.</span></span>

#### <a name="change-description"></a><span data-ttu-id="35cc8-106">変更の説明</span><span class="sxs-lookup"><span data-stu-id="35cc8-106">Change description</span></span>

<span data-ttu-id="35cc8-107">.NET Core 3.0 からは、バイトの文字列へのコード変換は、Unicode のベスト プラクティスに基づいて <xref:System.Text.UTF8Encoding> クラスによって文字列が置換されます。</span><span class="sxs-lookup"><span data-stu-id="35cc8-107">Starting with .NET Core 3.0, when transcoding bytes to characters, the <xref:System.Text.UTF8Encoding> class performs character substitution based on Unicode best practices.</span></span> <span data-ttu-id="35cc8-108">使用される置換メカニズムについては、[Unicode 標準のバージョン 12.0 のセクション 3.9 (PDF)](https://www.unicode.org/versions/Unicode12.0.0/ch03.pdf) の「_U+FFFD Substitution of Maximal Subparts_」 (最大サブパーツの U+FFFD 置換) という見出しを参照してください。</span><span class="sxs-lookup"><span data-stu-id="35cc8-108">The substitution mechanism used is described by [The Unicode Standard, Version 12.0, Sec. 3.9 (PDF)](https://www.unicode.org/versions/Unicode12.0.0/ch03.pdf) in the heading titled _U+FFFD Substitution of Maximal Subparts_.</span></span>

<span data-ttu-id="35cc8-109">この動作は、入力バイト シーケンスに不正な形式の UTF-8 データが含まれている場合_のみ_該当します。</span><span class="sxs-lookup"><span data-stu-id="35cc8-109">This behavior _only_ applies when the input byte sequence contains ill-formed UTF-8 data.</span></span> <span data-ttu-id="35cc8-110">また、<xref:System.Text.UTF8Encoding> インスタンスが `throwOnInvalidBytes: true` を使用して構築されている場合 ([UTF8Encoding コンストラクターのドキュメント] を参照)<xref:System.Text.UTF8Encoding.%23ctor(System.Boolean,System.Boolean)>、`UTF8Encoding` インスタンスは U+FFFD 置換を実行せずに無効な入力のスローを続けます。</span><span class="sxs-lookup"><span data-stu-id="35cc8-110">Additionally, if the <xref:System.Text.UTF8Encoding> instance has been constructed with `throwOnInvalidBytes: true` (see the [UTF8Encoding constructor documentation](<xref:System.Text.UTF8Encoding.%23ctor(System.Boolean,System.Boolean)>, the `UTF8Encoding` instance will continue to throw on invalid input rather than perform U+FFFD replacement.</span></span>

<span data-ttu-id="35cc8-111">次に、不正な 3 バイトの入力でのこの変更の影響を示します。</span><span class="sxs-lookup"><span data-stu-id="35cc8-111">The following illustrates the impact of this change with an invalid 3-byte input:</span></span>

|<span data-ttu-id="35cc8-112">不正形式の 3 バイトの入力</span><span class="sxs-lookup"><span data-stu-id="35cc8-112">Ill-formed 3-byte input</span></span>|<span data-ttu-id="35cc8-113">.NET Core 3.0 以前の出力</span><span class="sxs-lookup"><span data-stu-id="35cc8-113">Output before .NET Core 3.0</span></span>|<span data-ttu-id="35cc8-114">.NET Core 3.0 以降の出力</span><span class="sxs-lookup"><span data-stu-id="35cc8-114">Output starting with .NET Core 3.0</span></span>|
|---|---|---|
| `[ ED A0 90 ]` | <span data-ttu-id="35cc8-115">`[ FFFD FFFD ]` (2 文字の出力)</span><span class="sxs-lookup"><span data-stu-id="35cc8-115">`[ FFFD FFFD ]` (2-character output)</span></span>| <span data-ttu-id="35cc8-116">`[ FFFD FFFD FFFD ]` (3 文字の出力)</span><span class="sxs-lookup"><span data-stu-id="35cc8-116">`[ FFFD FFFD FFFD ]` (3-character output)</span></span>|

<span data-ttu-id="35cc8-117">この 3 文字の出力は、前にリンクした Unicode 標準の PDF の_表 3-9_ に従って、優先される出力となります。</span><span class="sxs-lookup"><span data-stu-id="35cc8-117">This 3-char output is the preferred output, according to _Table 3-9_ of the previously linked Unicode Standard PDF.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="35cc8-118">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="35cc8-118">Version introduced</span></span>

<span data-ttu-id="35cc8-119">3.0</span><span class="sxs-lookup"><span data-stu-id="35cc8-119">3.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="35cc8-120">推奨アクション</span><span class="sxs-lookup"><span data-stu-id="35cc8-120">Recommended action</span></span>

<span data-ttu-id="35cc8-121">開発者側では、何も行う必要はありません。</span><span class="sxs-lookup"><span data-stu-id="35cc8-121">No action is required on the part of the developer.</span></span>

#### <a name="category"></a><span data-ttu-id="35cc8-122">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="35cc8-122">Category</span></span>

<span data-ttu-id="35cc8-123">CoreFx</span><span class="sxs-lookup"><span data-stu-id="35cc8-123">CoreFx</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="35cc8-124">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="35cc8-124">Affected APIs</span></span>

- <xref:System.Text.UTF8Encoding.GetCharCount%2A?displayProperty=nameWithType>
- <xref:System.Text.UTF8Encoding.GetChars%2A?displayProperty=nameWithType>
- <xref:System.Text.UTF8Encoding.GetString(System.Byte[],System.Int32,System.Int32)?displayProperty=nameWithType>

<!--

### Affected APIs

- `Overload:System.Text.UTF8Encoding.GetCharCount`
- `Overload:System.Text.UTF8Encoding.GetChars`
- `M:System.Text.UTF8Encoding.GetString(System.Byte[],System.Int32,System.Int32)`

-->
