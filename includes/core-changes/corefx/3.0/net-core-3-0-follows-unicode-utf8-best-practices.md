---
ms.openlocfilehash: becae23cd810623bbb33c693b707c2d4735aeece
ms.sourcegitcommit: c2c1269a81ffdcfc8675bcd9a8505b1a11ffb271
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/25/2020
ms.locfileid: "82158478"
---
### <a name="replacing-ill-formed-utf-8-byte-sequences-follows-unicode-guidelines"></a><span data-ttu-id="64465-101">Unicode のガイドラインに従って不適切な形式の UTF-8 バイト シーケンスを置き換える</span><span class="sxs-lookup"><span data-stu-id="64465-101">Replacing ill-formed UTF-8 byte sequences follows Unicode guidelines</span></span>

<span data-ttu-id="64465-102"><xref:System.Text.UTF8Encoding> クラスで、バイトから文字へのコード変換中に不適切な形式の UTF-8 バイト シーケンスが検出された場合、そのシーケンスは出力文字列内で "�" (U+FFFD REPLACEMENT CHARACTER) 文字に置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="64465-102">When the <xref:System.Text.UTF8Encoding> class encounters an ill-formed UTF-8 byte sequence during a byte-to-character transcoding operation, it replaces that sequence with a '�' (U+FFFD REPLACEMENT CHARACTER) character in the output string.</span></span> <span data-ttu-id="64465-103">.NET Core 3.0 では、コード変換の操作中にこの置換を実行するための Unicode ベスト プラクティスに従うことで、以前のバージョンの .NET Core と .NET Framework との差別化が行われています。</span><span class="sxs-lookup"><span data-stu-id="64465-103">.NET Core 3.0 differs from previous versions of .NET Core and the .NET Framework by following the Unicode best practice for performing this replacement during the transcoding operation.</span></span>

<span data-ttu-id="64465-104">これは、新しい <xref:System.Text.Unicode.Utf8?displayProperty=nameWithType> 型および <xref:System.Text.Rune?displayProperty=nameWithType> 型の使用を含め、.NET 全体での UTF-8 の処理を向上させようとする、より大きな取り組みの一環です。</span><span class="sxs-lookup"><span data-stu-id="64465-104">This is part of a larger effort to improve UTF-8 handling throughout .NET, including by the new <xref:System.Text.Unicode.Utf8?displayProperty=nameWithType> and <xref:System.Text.Rune?displayProperty=nameWithType> types.</span></span> <span data-ttu-id="64465-105"><xref:System.Text.UTF8Encoding> 型では、新しく導入された型と一致する出力が生成されるよう、エラー処理のメカニズムが向上しています。</span><span class="sxs-lookup"><span data-stu-id="64465-105">The <xref:System.Text.UTF8Encoding> type was given improved error handling mechanics so that it produces output consistent with the newly introduced types.</span></span>

#### <a name="change-description"></a><span data-ttu-id="64465-106">変更の説明</span><span class="sxs-lookup"><span data-stu-id="64465-106">Change description</span></span>

<span data-ttu-id="64465-107">.NET Core 3.0 からは、バイトの文字列へのコード変換は、Unicode のベスト プラクティスに基づいて <xref:System.Text.UTF8Encoding> クラスによって文字列が置換されます。</span><span class="sxs-lookup"><span data-stu-id="64465-107">Starting with .NET Core 3.0, when transcoding bytes to characters, the <xref:System.Text.UTF8Encoding> class performs character substitution based on Unicode best practices.</span></span> <span data-ttu-id="64465-108">使用される置換メカニズムについては、[Unicode 標準のバージョン 12.0 のセクション 3.9 (PDF)](https://www.unicode.org/versions/Unicode12.0.0/ch03.pdf) の「_U+FFFD Substitution of Maximal Subparts_」 (最大サブパーツの U+FFFD 置換) という見出しを参照してください。</span><span class="sxs-lookup"><span data-stu-id="64465-108">The substitution mechanism used is described by [The Unicode Standard, Version 12.0, Sec. 3.9 (PDF)](https://www.unicode.org/versions/Unicode12.0.0/ch03.pdf) in the heading titled _U+FFFD Substitution of Maximal Subparts_.</span></span>

<span data-ttu-id="64465-109">この動作は、入力バイト シーケンスに不正な形式の UTF-8 データが含まれている場合_のみ_該当します。</span><span class="sxs-lookup"><span data-stu-id="64465-109">This behavior _only_ applies when the input byte sequence contains ill-formed UTF-8 data.</span></span> <span data-ttu-id="64465-110">また、<xref:System.Text.UTF8Encoding> インスタンスが `throwOnInvalidBytes: true` を使用して構築されている場合、`UTF8Encoding` インスタンスは U+FFFD 置換を実行せずに無効な入力のスローを続けます。</span><span class="sxs-lookup"><span data-stu-id="64465-110">Additionally, if the <xref:System.Text.UTF8Encoding> instance has been constructed with `throwOnInvalidBytes: true`, the `UTF8Encoding` instance will continue to throw on invalid input rather than perform U+FFFD replacement.</span></span> <span data-ttu-id="64465-111">`UTF8Encoding` コンストラクターについて詳しくは、「<xref:System.Text.UTF8Encoding.%23ctor(System.Boolean,System.Boolean)>」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="64465-111">For more information about the `UTF8Encoding` constructor, see <xref:System.Text.UTF8Encoding.%23ctor(System.Boolean,System.Boolean)>.</span></span>

<span data-ttu-id="64465-112">次の表では、不正な 3 バイトの入力でのこの変更の影響を示します。</span><span class="sxs-lookup"><span data-stu-id="64465-112">The following table illustrates the impact of this change with an invalid 3-byte input:</span></span>

| <span data-ttu-id="64465-113">不正形式の 3 バイトの入力</span><span class="sxs-lookup"><span data-stu-id="64465-113">Ill-formed 3-byte input</span></span> | <span data-ttu-id="64465-114">.NET Core 3.0 以前の出力</span><span class="sxs-lookup"><span data-stu-id="64465-114">Output before .NET Core 3.0</span></span>          | <span data-ttu-id="64465-115">.NET Core 3.0 以降の出力</span><span class="sxs-lookup"><span data-stu-id="64465-115">Output starting with .NET Core 3.0</span></span>        |
|-------------------------|--------------------------------------|-------------------------------------------|
| `[ ED A0 90 ]`          | <span data-ttu-id="64465-116">`[ FFFD FFFD ]` (2 文字の出力)</span><span class="sxs-lookup"><span data-stu-id="64465-116">`[ FFFD FFFD ]` (2-character output)</span></span> | <span data-ttu-id="64465-117">`[ FFFD FFFD FFFD ]` (3 文字の出力)</span><span class="sxs-lookup"><span data-stu-id="64465-117">`[ FFFD FFFD FFFD ]` (3-character output)</span></span> |

<span data-ttu-id="64465-118">3 文字の出力は、前にリンクした Unicode 標準の PDF の "_表 3-9_" に従って、優先される出力となります。</span><span class="sxs-lookup"><span data-stu-id="64465-118">The 3-char output is the preferred output, according to _Table 3-9_ of the previously linked Unicode Standard PDF.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="64465-119">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="64465-119">Version introduced</span></span>

<span data-ttu-id="64465-120">3.0</span><span class="sxs-lookup"><span data-stu-id="64465-120">3.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="64465-121">推奨アクション</span><span class="sxs-lookup"><span data-stu-id="64465-121">Recommended action</span></span>

<span data-ttu-id="64465-122">開発者側では、何も行う必要はありません。</span><span class="sxs-lookup"><span data-stu-id="64465-122">No action is required on the part of the developer.</span></span>

#### <a name="category"></a><span data-ttu-id="64465-123">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="64465-123">Category</span></span>

<span data-ttu-id="64465-124">Core .NET ライブラリ</span><span class="sxs-lookup"><span data-stu-id="64465-124">Core .NET libraries</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="64465-125">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="64465-125">Affected APIs</span></span>

- <xref:System.Text.UTF8Encoding.GetCharCount%2A?displayProperty=nameWithType>
- <xref:System.Text.UTF8Encoding.GetChars%2A?displayProperty=nameWithType>
- <xref:System.Text.UTF8Encoding.GetString(System.Byte[],System.Int32,System.Int32)?displayProperty=nameWithType>

<!--

### Affected APIs

- `Overload:System.Text.UTF8Encoding.GetCharCount`
- `Overload:System.Text.UTF8Encoding.GetChars`
- `M:System.Text.UTF8Encoding.GetString(System.Byte[],System.Int32,System.Int32)`

-->
