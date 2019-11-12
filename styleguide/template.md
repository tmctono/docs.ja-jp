---
title:
- 記事のタイトル
description: ''
author:
- GITHUB USERNAME
ms.author:
- MICROSOFT ALIAS OF INTERNAL OWNER
ms.date:
- CREATION/UPDATE DATE - MM/dd/yyyy
ms.topic:
- TOPIC TYPE
ms.prod:
- PRODUCT VALUE
helpviewer_keywords:
- OFFLINE BOOK INDEX ENTRIES
ms.openlocfilehash: e9a57cd569004edbe54645daa64e8c93b4afd67a
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2019
ms.locfileid: "73740075"
---
# <a name="metadata-and-markdown-template"></a><span data-ttu-id="e79bd-102">メタデータとマークダウン テンプレート</span><span class="sxs-lookup"><span data-stu-id="e79bd-102">Metadata and Markdown Template</span></span>

<span data-ttu-id="e79bd-103">この dotnet/ドキュメント テンプレートには、メタデータの設定に関するガイドラインだけでなく、マークダウン構文の例が含まれています。</span><span class="sxs-lookup"><span data-stu-id="e79bd-103">This dotnet/docs template contains examples of Markdown syntax, as well as guidance on setting the metadata.</span></span> <span data-ttu-id="e79bd-104">これを最大限に活用するには、[生のマークダウン](https://raw.githubusercontent.com/dotnet/docs/master/styleguide/template.md)と[表示ビュー](https://github.com/dotnet/docs/blob/master/styleguide/template.md)の両方を表示する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e79bd-104">To get the most of it, you must view both the [raw Markdown](https://raw.githubusercontent.com/dotnet/docs/master/styleguide/template.md) and the [rendered view](https://github.com/dotnet/docs/blob/master/styleguide/template.md).</span></span>

<span data-ttu-id="e79bd-105">マークダウン ファイルを作成する場合、このテンプレートを新しいファイルにコピーして、下記のようにメタデータを記入し、上の H1 見出しを記事のタイトルに設定して、コンテンツを削除します。</span><span class="sxs-lookup"><span data-stu-id="e79bd-105">When creating a Markdown file, you should copy this template to a new file, fill out the metadata as specified below, set the H1 heading above to the title of the article, and delete the content.</span></span>

## <a name="metadata"></a><span data-ttu-id="e79bd-106">メタデータ</span><span class="sxs-lookup"><span data-stu-id="e79bd-106">Metadata</span></span>

<span data-ttu-id="e79bd-107">完全なメタデータ ブロックは上部 ([生のマークダウン](https://raw.githubusercontent.com/dotnet/docs/master/styleguide/template.md)の) にあり、必須フィールドとオプション フィールドに分割されています。</span><span class="sxs-lookup"><span data-stu-id="e79bd-107">The full metadata block is above (in the [raw Markdown](https://raw.githubusercontent.com/dotnet/docs/master/styleguide/template.md)), divided into required fields and optional fields.</span></span> <span data-ttu-id="e79bd-108">次に注意事項をいくつか示します。</span><span class="sxs-lookup"><span data-stu-id="e79bd-108">Some key notes:</span></span>

- <span data-ttu-id="e79bd-109">コロン (:) とメタデータ要素の値の間にはスペースが**必要です**。</span><span class="sxs-lookup"><span data-stu-id="e79bd-109">You **must** have a space between the colon (:) and the value for a metadata element.</span></span>
- <span data-ttu-id="e79bd-110">省略可能なメタデータ要素に値がない場合は、# を使ってその要素をコメント アウトするか、削除します (空白のままにしたり、"na" を使用したりしないでください)。</span><span class="sxs-lookup"><span data-stu-id="e79bd-110">If an optional metadata element doesn't have a value, comment out the element with a # or remove it (don't leave it blank or use "na").</span></span> <span data-ttu-id="e79bd-111">コメント アウトされた要素に値を追加する場合は、# を必ず削除してください。</span><span class="sxs-lookup"><span data-stu-id="e79bd-111">If you're adding a value to an element that was commented out, be sure to remove the #.</span></span>
- <span data-ttu-id="e79bd-112">値 (タイトルなど) にコロンが含まれていると、メタデータ パーサーが中断します。</span><span class="sxs-lookup"><span data-stu-id="e79bd-112">Colons in a value (for example, a title) break the metadata parser.</span></span> <span data-ttu-id="e79bd-113">この場合は、タイトルを二重引用符で囲みます (例: `title: "Writing .NET Core console apps: An advanced step-by-step guide"`)。</span><span class="sxs-lookup"><span data-stu-id="e79bd-113">In this case, surround the title with double quotes (for example, `title: "Writing .NET Core console apps: An advanced step-by-step guide"`).</span></span>
- <span data-ttu-id="e79bd-114">**title**:検索エンジンの結果に表示されます。</span><span class="sxs-lookup"><span data-stu-id="e79bd-114">**title**: Appears in search engine results.</span></span> <span data-ttu-id="e79bd-115">タイトルは H1 見出しのタイトルと同一でなくてもかまいません。60 文字以下にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e79bd-115">The title shouldn't be identical to the title in your H1 heading, and it should contain 60 characters or less.</span></span>
- <span data-ttu-id="e79bd-116">**説明**:記事の内容を要約します。</span><span class="sxs-lookup"><span data-stu-id="e79bd-116">**description**: Summarizes the content of the article.</span></span> <span data-ttu-id="e79bd-117">これは通常、検索結果ページに表示されますが、検索ランキングには使用されません。</span><span class="sxs-lookup"><span data-stu-id="e79bd-117">It's usually shown in the search results page, but it isn't used for search ranking.</span></span> <span data-ttu-id="e79bd-118">長さは、スペースを含め 115 から 145 文字にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e79bd-118">Its length should be 115-145 characters including spaces.</span></span>
- <span data-ttu-id="e79bd-119">**author** および **ms.author**:"author" フィールドには、作成者のエイリアスではなく、**GitHub ユーザー名**を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="e79bd-119">**author** and **ms.author**: The author field should contain the **GitHub username** of the author, not his/her alias.</span></span>  <span data-ttu-id="e79bd-120">一方で、**ms.author** フィールドには、Microsoft エイリアスが記載され、記事の管理者が示されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="e79bd-120">The **ms.author** field, on the other hand, should contain a Microsoft alias and indicates the person responsible for maintaining the article.</span></span>
- <span data-ttu-id="e79bd-121">**ms.topic**:トピックの種類です。</span><span class="sxs-lookup"><span data-stu-id="e79bd-121">**ms.topic**: The topic type.</span></span> <span data-ttu-id="e79bd-122">最も一般的な値は `conceptual` であり、グローバル レベルに設定されています。</span><span class="sxs-lookup"><span data-stu-id="e79bd-122">The most common value is `conceptual` and is set at a global level.</span></span> <span data-ttu-id="e79bd-123">使用されるその他の一般的な値は、`tutorial`、`overview`、`reference` です。</span><span class="sxs-lookup"><span data-stu-id="e79bd-123">Other common values used are `tutorial`, `overview`, and `reference`.</span></span>
- <span data-ttu-id="e79bd-124">**dev_langs** では、トピックに表示される言語フィルターが定義されます。</span><span class="sxs-lookup"><span data-stu-id="e79bd-124">**dev_langs** defines the language filter displayed for the topic.</span></span> <span data-ttu-id="e79bd-125">「[サポートされる言語](#supported-languages)」セクションに、サポートされる値のリストが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e79bd-125">You can see a list of the supported values in the [Supported languages](#supported-languages) section.</span></span> <span data-ttu-id="e79bd-126">トピックの中に複数のプログラミング言語がある場合にのみ設定が必要です。</span><span class="sxs-lookup"><span data-stu-id="e79bd-126">Only needs to be set when there's more than one programming language covered in the topic.</span></span> <span data-ttu-id="e79bd-127">通常、コンテンツ内にあるこの値については、`csharp`、`vb`、`fsharp`、`cpp` のみを使用します。</span><span class="sxs-lookup"><span data-stu-id="e79bd-127">Typically, we only use `csharp`, `vb`, `fsharp`, and `cpp` for this value in our content.</span></span>
- <span data-ttu-id="e79bd-128">**ms.prod**:BI の目的に使用される製品 ID です。</span><span class="sxs-lookup"><span data-stu-id="e79bd-128">**ms.prod**: Product identification used for BI purposes.</span></span> <span data-ttu-id="e79bd-129">これらは通常グローバル レベルに設定されているため、各記事のメタデータ ブロックには、通常は表示されません。</span><span class="sxs-lookup"><span data-stu-id="e79bd-129">They're usually set at a global level, so they don't usually appear in the metadata block of each article.</span></span>
- <span data-ttu-id="e79bd-130">**ms.technology**:追加の BI 分類です。</span><span class="sxs-lookup"><span data-stu-id="e79bd-130">**ms.technology**: Additional BI classification.</span></span> <span data-ttu-id="e79bd-131">サポートされる値の一部として、C# トピックの場合は `devlang-csharp`、F# トピックの場合は `devlang-fsharp`、VB トピックの場合は `devlang-visual-basic` があります。</span><span class="sxs-lookup"><span data-stu-id="e79bd-131">Some of the supported values are: `devlang-csharp` for C# topics, `devlang-fsharp` for F# topics, and `devlang-visual-basic` for VB topics.</span></span> <span data-ttu-id="e79bd-132">その他のガイドについては、値が異なるため、チームのメンバーに助言を求めてください。</span><span class="sxs-lookup"><span data-stu-id="e79bd-132">For other guides, the values will vary, so ask a member of the team for guidance.</span></span>
- <span data-ttu-id="e79bd-133">**ms.date**:MM/DD/YYYY 形式の日付です。</span><span class="sxs-lookup"><span data-stu-id="e79bd-133">**ms.date**: A date in the format MM/dd/yyyy.</span></span> <span data-ttu-id="e79bd-134">公開済みページに表示される日付です。前回、記事が大幅に編集されたか、"最新" であることが保証された (すなわち、記事がレビュー済みで、最新であるとみなされた) 日付を示します。</span><span class="sxs-lookup"><span data-stu-id="e79bd-134">Displayed on the published page to indicate the last time the article was substantially edited or guaranteed "fresh" (that is, the article was reviewed and considered up-to-date).</span></span>
- <span data-ttu-id="e79bd-135">**helpviewer_keywords**:エントリが、オフライン ブック インデックスに使用されます (Visual Studio の機能)。</span><span class="sxs-lookup"><span data-stu-id="e79bd-135">**helpviewer_keywords**: Entries are used for the offline books index (functionality in Visual Studio).</span></span>
- <span data-ttu-id="e79bd-136">**f1_keywords**:記事を F1 キーに接続します (Visual Studio の機能)。</span><span class="sxs-lookup"><span data-stu-id="e79bd-136">**f1_keywords**: Connects the article to the F1 key (functionality in Visual Studio).</span></span>

## <a name="basic-markdown-gfm-and-special-characters"></a><span data-ttu-id="e79bd-137">基本マークダウン、GFM、特殊文字</span><span class="sxs-lookup"><span data-stu-id="e79bd-137">Basic Markdown, GFM, and special characters</span></span>

<span data-ttu-id="e79bd-138">すべての基本マークダウンと GitHub Flavored Markdown (GFM) がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="e79bd-138">All basic and GitHub Flavored Markdown (GFM) is supported.</span></span> <span data-ttu-id="e79bd-139">それらの詳細については、次を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e79bd-139">For more information on these, see:</span></span>

- [<span data-ttu-id="e79bd-140">Baseline Markdown syntax (ベースライン マークダウン構文)</span><span class="sxs-lookup"><span data-stu-id="e79bd-140">Baseline Markdown syntax</span></span>](https://daringfireball.net/projects/markdown/syntax)
- [<span data-ttu-id="e79bd-141">GFM documentation (GFM ドキュメント)</span><span class="sxs-lookup"><span data-stu-id="e79bd-141">GFM documentation</span></span>](https://guides.github.com/features/mastering-markdown)

<span data-ttu-id="e79bd-142">マークダウンでは書式設定に \*、\`、\# などの特殊文字を使用します。</span><span class="sxs-lookup"><span data-stu-id="e79bd-142">Markdown uses special characters such as \*, \`, and \# for formatting.</span></span> <span data-ttu-id="e79bd-143">これらの文字のいずれかをコンテンツに含める場合は、次の 2 つのどちらかを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="e79bd-143">If you wish to include one of these characters in your content, you must do one of two things:</span></span>

- <span data-ttu-id="e79bd-144">特殊文字の前にバックスラッシュを入力して、"エスケープ" する (たとえば、\* の場合は `\*`)</span><span class="sxs-lookup"><span data-stu-id="e79bd-144">Put a backslash before the special character to "escape" it (for example, `\*` for an \*)</span></span>
- <span data-ttu-id="e79bd-145">文字の [HTML エンティティ コード](https://www.ascii.cl/htmlcodes.htm)を使用する (たとえば、&#42 の場合は `&#42;`)。</span><span class="sxs-lookup"><span data-stu-id="e79bd-145">Use the [HTML entity code](https://www.ascii.cl/htmlcodes.htm) for the character (for example, `&#42;` for an &#42;).</span></span>

## <a name="file-name"></a><span data-ttu-id="e79bd-146">ファイル名</span><span class="sxs-lookup"><span data-stu-id="e79bd-146">File name</span></span>

<span data-ttu-id="e79bd-147">ファイル名には次の規則を使用します。</span><span class="sxs-lookup"><span data-stu-id="e79bd-147">File names use the following rules:</span></span>

- <span data-ttu-id="e79bd-148">小文字、数字、ハイフンのみを使用する。</span><span class="sxs-lookup"><span data-stu-id="e79bd-148">Contain only lowercase letters, numbers, and hyphens.</span></span>
- <span data-ttu-id="e79bd-149">スペースや句読点を使用しない。</span><span class="sxs-lookup"><span data-stu-id="e79bd-149">No spaces or punctuation characters.</span></span> <span data-ttu-id="e79bd-150">ハイフンを使用して、ファイル名の単語と数字を区切る。</span><span class="sxs-lookup"><span data-stu-id="e79bd-150">Use the hyphens to separate words and numbers in the file name.</span></span>
- <span data-ttu-id="e79bd-151">develop (開発)、buy (購入)、build (ビルド)、troubleshoot (トラブルシューティング) など、具体的な動作動詞を使用する。</span><span class="sxs-lookup"><span data-stu-id="e79bd-151">Use action verbs that are specific, such as develop, buy, build, troubleshoot.</span></span> <span data-ttu-id="e79bd-152">-ing 形の語は使用しません。</span><span class="sxs-lookup"><span data-stu-id="e79bd-152">No -ing words.</span></span>
- <span data-ttu-id="e79bd-153">小さな単語を使用しない。a、and、the、in、or などは含めません。</span><span class="sxs-lookup"><span data-stu-id="e79bd-153">No small words - don't include a, and, the, in, or, etc.</span></span>
- <span data-ttu-id="e79bd-154">マークダウンで記述し、.md ファイル拡張子を使用する必要がある。</span><span class="sxs-lookup"><span data-stu-id="e79bd-154">Must be in Markdown and use the .md file extension.</span></span>
- <span data-ttu-id="e79bd-155">ファイル名を極力短くする。</span><span class="sxs-lookup"><span data-stu-id="e79bd-155">Keep file names reasonably short.</span></span> <span data-ttu-id="e79bd-156">記事の URL の一部となるためです。</span><span class="sxs-lookup"><span data-stu-id="e79bd-156">They are part of the URL for your articles.</span></span>

## <a name="headings"></a><span data-ttu-id="e79bd-157">見出し</span><span class="sxs-lookup"><span data-stu-id="e79bd-157">Headings</span></span>

<span data-ttu-id="e79bd-158">文スタイルで大文字化します。</span><span class="sxs-lookup"><span data-stu-id="e79bd-158">Use sentence-style capitalization.</span></span> <span data-ttu-id="e79bd-159">見出しの最初の単語の最初の文字、固有名詞、コロンの後の最初の文字は大文字にします (たとえば、"Tutorial: Predict prices using regression with ML.NET")。</span><span class="sxs-lookup"><span data-stu-id="e79bd-159">Capitalize the first letter of the first word of a heading, proper nouns, and the first letter following a colon (for example, "Tutorial: Predict prices using regression with ML.NET").</span></span>

<span data-ttu-id="e79bd-160">"How to" の後にはコロンを追加しないでください (たとえば、"How to sort an array" とし、"How to: Sort an array" のようにはしません)。</span><span class="sxs-lookup"><span data-stu-id="e79bd-160">Don't add a colon after "How to" (for example, "How to sort an array" and not "How to: Sort an array").</span></span>

<span data-ttu-id="e79bd-161">見出しは atx スタイルを使用して作成する必要があります。つまり、見出しを示すために行の先頭に 1 から 6 文字のハッシュ文字 (#) を使用します。これは、HTML 見出しレベルの H1 〜 H6 に対応します。</span><span class="sxs-lookup"><span data-stu-id="e79bd-161">Headings should be done using atx-style, that is, use 1-6 hash characters (#) at the start of the line to indicate a heading, corresponding to HTML headings levels H1 through H6.</span></span> <span data-ttu-id="e79bd-162">レベル 1 とレベル 2 のヘッダーの例が上で使用されています。</span><span class="sxs-lookup"><span data-stu-id="e79bd-162">Examples of first- and second-level headers are used above.</span></span>

<span data-ttu-id="e79bd-163">トピックのレベル 1 の見出し (H1) は 1 つだけにする**必要があります**。これがページ上のタイトルとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="e79bd-163">There **must** be only one first-level heading (H1) in your topic, which will be displayed as the on-page title.</span></span>

<span data-ttu-id="e79bd-164">見出しが `#` 文字で終わっている場合は、タイトルが正しく表示されるようにエスケープする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e79bd-164">If your heading ends in a `#` character, you need to escape it for the title to render correctly.</span></span> <span data-ttu-id="e79bd-165">たとえば、`# Async programming in F\#` のようにします。</span><span class="sxs-lookup"><span data-stu-id="e79bd-165">For example, `# Async programming in F\#`.</span></span>

<span data-ttu-id="e79bd-166">レベル 2 の見出しは、ページ上タイトルの下にある "この記事内" セクションに表示されるページ上の目次を生成します。</span><span class="sxs-lookup"><span data-stu-id="e79bd-166">Second-level headings will generate the on-page TOC that appears in the "In this article" section underneath the on-page title.</span></span>

### <a name="third-level-heading"></a><span data-ttu-id="e79bd-167">レベル 3 の見出し</span><span class="sxs-lookup"><span data-stu-id="e79bd-167">Third-level heading</span></span>
#### <a name="fourth-level-heading"></a><span data-ttu-id="e79bd-168">レベル 4 の見出し</span><span class="sxs-lookup"><span data-stu-id="e79bd-168">Fourth-level heading</span></span>
##### <a name="fifth-level-heading"></a><span data-ttu-id="e79bd-169">レベル 5 の見出し</span><span class="sxs-lookup"><span data-stu-id="e79bd-169">Fifth level heading</span></span>
###### <a name="sixth-level-heading"></a><span data-ttu-id="e79bd-170">レベル 6 の見出し</span><span class="sxs-lookup"><span data-stu-id="e79bd-170">Sixth-level heading</span></span>

## <a name="text-styling"></a><span data-ttu-id="e79bd-171">テキストのスタイル指定</span><span class="sxs-lookup"><span data-stu-id="e79bd-171">Text styling</span></span>

<span data-ttu-id="e79bd-172">"*斜体*" ファイル、フォルダー、パス (項目が長い場合は、独立した行に分割)、新しい用語に使用します。</span><span class="sxs-lookup"><span data-stu-id="e79bd-172">*Italics* Use for files, folders, paths (for long items, split onto their own line), new terms.</span></span>

<span data-ttu-id="e79bd-173">**太字** UI 要素に使用します。</span><span class="sxs-lookup"><span data-stu-id="e79bd-173">**Bold** Use for UI elements.</span></span>

<span data-ttu-id="e79bd-174">`Code` クリックできないようにするインライン コード、言語キーワード、NuGet パッケージ名、コマンドライン コマンド、データベース テーブルと列の名前、URL に使用します。</span><span class="sxs-lookup"><span data-stu-id="e79bd-174">`Code` Use for inline code, language keywords, NuGet package names, command-line commands, database table and column names, and URLs that you don't want to be clickable.</span></span>

## <a name="links"></a><span data-ttu-id="e79bd-175">リンク</span><span class="sxs-lookup"><span data-stu-id="e79bd-175">Links</span></span>

### <a name="internal-links"></a><span data-ttu-id="e79bd-176">内部リンク</span><span class="sxs-lookup"><span data-stu-id="e79bd-176">Internal Links</span></span>

<span data-ttu-id="e79bd-177">同じマークダウン ファイル内のヘッダーにリンクする (アンカー リンクとも呼ばれます) には、リンク先のヘッダーの ID を確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e79bd-177">To link to a header in the same Markdown file (also known as anchor links), you'll need to find out the id of the header you're trying to link to.</span></span> <span data-ttu-id="e79bd-178">ID を確認するには、表示された記事のソースを表示して、ヘッダーの ID (例: `id="blockquote"`) を検索し、# に ID をつなげたものを使用してリンクします (例: `#blockquote`)。</span><span class="sxs-lookup"><span data-stu-id="e79bd-178">To confirm the ID, view the source of the rendered article, find the id of the header (for example, `id="blockquote"`), and link using # + id (for example, `#blockquote`).</span></span>
<span data-ttu-id="e79bd-179">ID はヘッダー テキストに基づいて自動生成されます。</span><span class="sxs-lookup"><span data-stu-id="e79bd-179">The id is auto-generated based on the header text.</span></span> <span data-ttu-id="e79bd-180">そのため、たとえば、`## Step 2` という名前の一意のセクションの場合、ID は `id="step-2"` のようになります。</span><span class="sxs-lookup"><span data-stu-id="e79bd-180">So, for example, given a unique section named `## Step 2`, the id would look like this `id="step-2"`.</span></span>

- <span data-ttu-id="e79bd-181">例: `[Declare inline blocks with a language identifier](#inline-code-blocks-with-language-identifier)` では、[言語識別子を使用して宣言インライン ブロック](#inline-code-blocks-with-language-identifier)が生成されます。</span><span class="sxs-lookup"><span data-stu-id="e79bd-181">Example: `[Declare inline blocks with a language identifier](#inline-code-blocks-with-language-identifier)` produces [Declare inline blocks with a language identifier](#inline-code-blocks-with-language-identifier).</span></span>

<span data-ttu-id="e79bd-182">同じリポジトリ内のマークダウン ファイルにリンクするには、ファイル名の末尾に ".md" を含めた[相対リンク](https://www.w3.org/TR/WD-html40-970917/htmlweb.html#h-5.1.2)を使用します。</span><span class="sxs-lookup"><span data-stu-id="e79bd-182">To link to a Markdown file in the same repo, use [relative links](https://www.w3.org/TR/WD-html40-970917/htmlweb.html#h-5.1.2), including the ".md" at the end of the filename.</span></span>

- <span data-ttu-id="e79bd-183">例: `[Readme file](../README.md)` では、[Readme ファイル](../README.md)が生成されます</span><span class="sxs-lookup"><span data-stu-id="e79bd-183">Example: `[Readme file](../README.md)` produces [Readme file](../README.md).</span></span> <span data-ttu-id="e79bd-184">(リンクは、大文字と小文字が区別されます)。</span><span class="sxs-lookup"><span data-stu-id="e79bd-184">(Note that links are case-sensitive.)</span></span>
- <span data-ttu-id="e79bd-185">例: `[Welcome to .NET](../docs/welcome.md)` では、「[.NET にようこそ](../docs/welcome.md)」が生成されます。</span><span class="sxs-lookup"><span data-stu-id="e79bd-185">Example: `[Welcome to .NET](../docs/welcome.md)` produces [Welcome to .NET](../docs/welcome.md).</span></span>

<span data-ttu-id="e79bd-186">同じリポジトリ内のマークダウン ファイルのヘッダーにリンクするには、相対リンクとハッシュタグ リンクを使用します。</span><span class="sxs-lookup"><span data-stu-id="e79bd-186">To link to a header in a Markdown file in the same repo, use relative linking + hashtag linking.</span></span>

- <span data-ttu-id="e79bd-187">例: `[.NET Community](../docs/welcome.md#open-source)` では、[.NET コミュニティ](../docs/welcome.md#open-source)が生成されます。</span><span class="sxs-lookup"><span data-stu-id="e79bd-187">Example: `[.NET Community](../docs/welcome.md#open-source)` produces [.NET Community](../docs/welcome.md#open-source).</span></span>

<span data-ttu-id="e79bd-188">ほとんどの場合は、相対リンクを使用し、リンクに `~/` を使用しないようにします。これは、相対リンクが GitHub のソース内で解決されるためです。</span><span class="sxs-lookup"><span data-stu-id="e79bd-188">In most cases, we use the relative links and discourage the use of `~/` in links because relative links resolve in the source on GitHub.</span></span> <span data-ttu-id="e79bd-189">ただし、依存リポジトリ内のファイルにリンクする場合は、`~/` 文字を使用してパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="e79bd-189">However, whenever we link to a file in a dependent repo, we'll use the `~/` character to provide the path.</span></span> <span data-ttu-id="e79bd-190">依存リポジトリ内のファイルは GitHub の別の場所にあるため、リンクがどのように記述されているかを問わず、相対リンクは正しく解決されません。</span><span class="sxs-lookup"><span data-stu-id="e79bd-190">Because the files in the dependent repo are in a different location in GitHub the links won't resolve correctly with relative links regardless of how they were written.</span></span>

<span data-ttu-id="e79bd-191">C# 言語仕様と Visual Basic 言語仕様は、言語リポジトリのソースを含めると、.NET ドキュメントに含まれます。</span><span class="sxs-lookup"><span data-stu-id="e79bd-191">The C# language specification and the Visual Basic language specification are included in the .NET docs by including the source from the language repositories.</span></span> <span data-ttu-id="e79bd-192">マークダウン ソースは、[csharplang](https://github.com/dotnet/csharplang) リポジトリと [visual basic](https://github.com/dotnet/vblang) リポジトリ内で管理されます。</span><span class="sxs-lookup"><span data-stu-id="e79bd-192">The markdown sources are managed in the [csharplang](https://github.com/dotnet/csharplang) and [visual basic](https://github.com/dotnet/vblang) repositories.</span></span>

<span data-ttu-id="e79bd-193">仕様へのリンクは、これらの仕様が含まれるソース ディレクトリを指す必要があります。</span><span class="sxs-lookup"><span data-stu-id="e79bd-193">Links to the spec must point to the source directories where those specs are included.</span></span> <span data-ttu-id="e79bd-194">C# の場合は **~/_csharplang/spec**、VB の場合は **~/_vblang/spec** です。</span><span class="sxs-lookup"><span data-stu-id="e79bd-194">For C#, it's **~/_csharplang/spec** and for VB, it's **~/_vblang/spec**.</span></span>

- <span data-ttu-id="e79bd-195">例: `[C# Query Expressions](~/_csharplang/spec/expressions.md#query-expressions)` では、[C# クエリ式が生成されます](~/_csharplang/spec/expressions.md#query-expressions)。</span><span class="sxs-lookup"><span data-stu-id="e79bd-195">Example: `[C# Query Expressions](~/_csharplang/spec/expressions.md#query-expressions)` produces [C# Query Expressions](~/_csharplang/spec/expressions.md#query-expressions).</span></span>

### <a name="external-links"></a><span data-ttu-id="e79bd-196">外部リンク</span><span class="sxs-lookup"><span data-stu-id="e79bd-196">External Links</span></span>

<span data-ttu-id="e79bd-197">外部ファイルにリンクするには、完全な URL をリンクとして使用します。</span><span class="sxs-lookup"><span data-stu-id="e79bd-197">To link to an external file, use the full URL as the link.</span></span>

- <span data-ttu-id="e79bd-198">例: `[GitHub](https://www.github.com)` では、[GitHub](https://www.github.com) が生成されます。</span><span class="sxs-lookup"><span data-stu-id="e79bd-198">Example: `[GitHub](https://www.github.com)` produces [GitHub](https://www.github.com).</span></span>

<span data-ttu-id="e79bd-199">URL がマークダウン ファイルに表示されると、クリック可能なリンクに変換されます。</span><span class="sxs-lookup"><span data-stu-id="e79bd-199">If a URL appears in a Markdown file, it will be transformed into a clickable link.</span></span>

- <span data-ttu-id="e79bd-200">例: `<https://www.github.com>` では、<https://www.github.com> が生成されます。</span><span class="sxs-lookup"><span data-stu-id="e79bd-200">Example: `<https://www.github.com>` produces <https://www.github.com>.</span></span>

<span data-ttu-id="e79bd-201">外部リンクの場合は、`https` プロトコルを優先します。</span><span class="sxs-lookup"><span data-stu-id="e79bd-201">Prefer the `https` protocol for external links.</span></span> <span data-ttu-id="e79bd-202">`https` をサポートしていないサイトの場合にのみ `http` リンクを使用します。</span><span class="sxs-lookup"><span data-stu-id="e79bd-202">Only use `http` links for sites that do not support `https`.</span></span>

### <a name="links-to-apis"></a><span data-ttu-id="e79bd-203">API へのリンク</span><span class="sxs-lookup"><span data-stu-id="e79bd-203">Links to APIs</span></span>

<span data-ttu-id="e79bd-204">ビルド システムには、外部リンクを使用せずに .NET API にリンクできるようにするいくつかの拡張機能が備えられています。</span><span class="sxs-lookup"><span data-stu-id="e79bd-204">The build system has some extensions that allow us to link to .NET APIs without having to use external links.</span></span>
<span data-ttu-id="e79bd-205">API にリンクする場合は、ソース コードから自動生成される一意識別子 (UID) を使用できます。</span><span class="sxs-lookup"><span data-stu-id="e79bd-205">When linking to an API, you can use its unique identifier (UID) that is auto-generated from the source code.</span></span>

<span data-ttu-id="e79bd-206">UID は、完全修飾型とメンバー名に相当します。</span><span class="sxs-lookup"><span data-stu-id="e79bd-206">The UID equates to the fully qualified type and member name.</span></span>

<span data-ttu-id="e79bd-207">UID の後に \* (または %2A) を追加した場合、リンクは特定の API ではなく、オーバーロード ページを表します。</span><span class="sxs-lookup"><span data-stu-id="e79bd-207">If you add a \* (or %2A) after the UID, the link then represents the overload page and not a specific API.</span></span> <span data-ttu-id="e79bd-208">たとえば、[List\<T>.BinarySearch(T, IComparer\<T>)](https://docs.microsoft.com/dotnet/api/system.collections.generic.list-1.binarysearch#System_Collections_Generic_List_1_BinarySearch__0_) などの特定のオーバーロードではなく、一般的な方法で [List\<T>.BinarySearch Method](https://docs.microsoft.com/dotnet/api/system.collections.generic.list-1.binarysearch) ページにリンクする場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="e79bd-208">For example, you can use that when you want to link to the [List\<T>.BinarySearch Method](https://docs.microsoft.com/dotnet/api/system.collections.generic.list-1.binarysearch) page in a generic way instead of a specific overload such as [List\<T>.BinarySearch(T, IComparer\<T>)](https://docs.microsoft.com/dotnet/api/system.collections.generic.list-1.binarysearch#System_Collections_Generic_List_1_BinarySearch__0_).</span></span> <span data-ttu-id="e79bd-209">また、メンバーがオーバーロードされていない場合は、\* を使ってメンバー ページにリンクすることもできます。これにより、UID にパラメーター リストを含める必要がなくなります。</span><span class="sxs-lookup"><span data-stu-id="e79bd-209">You can also use \* to link to a member page when the member is not overloaded; this saves you from having to include the parameter list in the UID.</span></span>

<span data-ttu-id="e79bd-210">特定のメソッドのオーバーロードにリンクするには、メソッドの各パラメーターの完全修飾型名を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="e79bd-210">To link to a specific method overload, you must include the fully qualified type name of each of the method's parameters.</span></span> <span data-ttu-id="e79bd-211">たとえば、\<xref:System.DateTime.ToString> はパラメーターなしの [DateTime.ToString](https://docs.microsoft.com/dotnet/api/system.datetime.tostring#System_DateTime_ToString) メソッドにリンクされますが、\<xref:System.DateTime.ToString(System.String,System.IFormatProvider)> は [DateTime.ToString(String,IFormatProvider)](https://docs.microsoft.com/dotnet/api/system.datetime.tostring#System_DateTime_ToString_System_String_System_IFormatProvider_) メソッドにリンクされます。</span><span class="sxs-lookup"><span data-stu-id="e79bd-211">For example, \<xref:System.DateTime.ToString> links to the parameterless [DateTime.ToString](https://docs.microsoft.com/dotnet/api/system.datetime.tostring#System_DateTime_ToString) method, while \<xref:System.DateTime.ToString(System.String,System.IFormatProvider)> links to the  [DateTime.ToString(String,IFormatProvider)](https://docs.microsoft.com/dotnet/api/system.datetime.tostring#System_DateTime_ToString_System_String_System_IFormatProvider_) method.</span></span> <span data-ttu-id="e79bd-212">オーバーロードされた特定のメンバーの UID を `https://xref.docs.microsoft.com/autocomplete` から見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="e79bd-212">You can find the UIDs of a particular overloaded member from `https://xref.docs.microsoft.com/autocomplete`.</span></span> <span data-ttu-id="e79bd-213">クエリ文字列 "?text= *\<type-member-name>* " では、UID を確認したい型またはメンバーを特定します。</span><span class="sxs-lookup"><span data-stu-id="e79bd-213">The query string "?text=*\<type-member-name>*" identifies the type or member whose UIDs you'd like to see.</span></span> <span data-ttu-id="e79bd-214">たとえば、`https://xref.docs.microsoft.com/autocomplete?text=string.format` では、[String.Format](https://docs.microsoft.com/dotnet/api/system.string.format) オーバーロードが取得されます。</span><span class="sxs-lookup"><span data-stu-id="e79bd-214">For example, `https://xref.docs.microsoft.com/autocomplete?text=string.format` retrieves the [String.Format](https://docs.microsoft.com/dotnet/api/system.string.format) overloads.</span></span>

<span data-ttu-id="e79bd-215">[System.Collections.Generic.List\<T>](https://docs.microsoft.com/dotnet/api/system.collections.generic.list-1) などのジェネリック型にリンクするには、\` (%60) 文字に続けてジェネリック型パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="e79bd-215">To link to a generic type, such as [System.Collections.Generic.List\<T>](https://docs.microsoft.com/dotnet/api/system.collections.generic.list-1), you use the \` (%60) character followed by the number of generic type parameters.</span></span> <span data-ttu-id="e79bd-216">たとえば、\<xref:System.Nullable%601> は [System.Nullable\<T>](https://docs.microsoft.com/dotnet/api/system.nullable-1) 型にリンクされますが、\<xref:System.Func%602> は [System.Func\<T,TResult>](https://docs.microsoft.com/dotnet/api/system.func-2) デリゲートにリンクされます。</span><span class="sxs-lookup"><span data-stu-id="e79bd-216">For example, \<xref:System.Nullable%601> links to the [System.Nullable\<T>](https://docs.microsoft.com/dotnet/api/system.nullable-1) type, while \<xref:System.Func%602> links to the [System.Func\<T,TResult>](https://docs.microsoft.com/dotnet/api/system.func-2) delegate.</span></span>

<span data-ttu-id="e79bd-217">次のいずれかの構文を使用できます。</span><span class="sxs-lookup"><span data-stu-id="e79bd-217">You can use one of the following syntax:</span></span>

1. <span data-ttu-id="e79bd-218">自動リンク: `<xref:UID>` または `<xref:UID?displayProperty=nameWithType>`</span><span class="sxs-lookup"><span data-stu-id="e79bd-218">Auto-link: `<xref:UID>` or `<xref:UID?displayProperty=nameWithType>`</span></span>

   <span data-ttu-id="e79bd-219">`displayProperty` クエリ パラメーターでは、完全修飾リンク テキストが生成されます。</span><span class="sxs-lookup"><span data-stu-id="e79bd-219">The `displayProperty` query    parameter produces a fully qualified link text.</span></span> <span data-ttu-id="e79bd-220">既定では、リンクテキストには、メンバーまたは型の名前のみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e79bd-220">By default, link text shows only the member or type name.</span></span>

2. <span data-ttu-id="e79bd-221">マークダウン リンク: `[link text](xref:UID)`</span><span class="sxs-lookup"><span data-stu-id="e79bd-221">Markdown link: `[link text](xref:UID)`</span></span>

   <span data-ttu-id="e79bd-222">表示されるリンク テキストをカスタマイズする場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="e79bd-222">Use when you want to customize the link text displayed.</span></span>

<span data-ttu-id="e79bd-223">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="e79bd-223">Examples:</span></span>

- <span data-ttu-id="e79bd-224">`<xref:System.String>` は [String](https://docs.microsoft.com/dotnet/api/system.string) としてレンダリングされます</span><span class="sxs-lookup"><span data-stu-id="e79bd-224">`<xref:System.String>` renders as [String](https://docs.microsoft.com/dotnet/api/system.string)</span></span>
- <span data-ttu-id="e79bd-225">`<xref:System.String?displayProperty=nameWithType>` は [System.String](https://docs.microsoft.com/dotnet/api/system.string) としてレンダリングされます</span><span class="sxs-lookup"><span data-stu-id="e79bd-225">`<xref:System.String?displayProperty=nameWithType>` renders as [System.String](https://docs.microsoft.com/dotnet/api/system.string)</span></span>
- <span data-ttu-id="e79bd-226">`[String class](xref:System.String)` は [String class](https://docs.microsoft.com/dotnet/api/system.string) としてレンダリングされます</span><span class="sxs-lookup"><span data-stu-id="e79bd-226">`[String class](xref:System.String)` renders as [String class](https://docs.microsoft.com/dotnet/api/system.string)</span></span>

<span data-ttu-id="e79bd-227">この表記の使用に関する詳細は、「[Using cross reference (相互参照の使用)](https://dotnet.github.io/docfx/tutorial/links_and_cross_references.html#using-cross-reference)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e79bd-227">For more information about using this notation, see [Using cross reference](https://dotnet.github.io/docfx/tutorial/links_and_cross_references.html#using-cross-reference).</span></span>

<span data-ttu-id="e79bd-228">UID を検索するには、2 つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="e79bd-228">There are two ways to find the UID:</span></span>

- <span data-ttu-id="e79bd-229">リンク先の API ページのソースを表示して、ms.assetid 値を検索します。</span><span class="sxs-lookup"><span data-stu-id="e79bd-229">View the source for the API page you want to link to and find the ms.assetid value.</span></span> <span data-ttu-id="e79bd-230">個別のオーバーロード値は、ソースには示されていないため注意してください。</span><span class="sxs-lookup"><span data-stu-id="e79bd-230">Note that individual overload values are not shown in the source.</span></span>
- <span data-ttu-id="e79bd-231">UID の検索には、次のツールを使用します: https://xref.docs.microsoft.com/autocomplete?text=tostring (tostring は、検索しようとしている API 名の一部に置き換えます)。</span><span class="sxs-lookup"><span data-stu-id="e79bd-231">Use the following tool to search for UIDs: https://xref.docs.microsoft.com/autocomplete?text=tostring (replace tostring with parts of the API name you're trying to find).</span></span> <span data-ttu-id="e79bd-232">ツールにより、UID の任意の部分で、指定した `text` クエリ パラメーターが検索されます。</span><span class="sxs-lookup"><span data-stu-id="e79bd-232">The tool searches for the provided `text` query parameter in any part of the UID.</span></span> <span data-ttu-id="e79bd-233">たとえば、メンバー名 (ToString)、メンバー名 (ToStri) の一部、型とメンバー名 (Double.ToString) などを検索できます。</span><span class="sxs-lookup"><span data-stu-id="e79bd-233">For example, you can search for member name (ToString), partial member name (ToStri), type and member name (Double.ToString), etc.</span></span>

<span data-ttu-id="e79bd-234">UID に特殊文字 \`、\# または \* が含まれる場合、UID 値はそれぞれ `%60`、`%23`、`%2A` として HTML をエンコードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e79bd-234">When the UID contains the special characters \`, \# or \*, the UID value needs to be HTML encoded as `%60`, `%23` and `%2A` respectively.</span></span> <span data-ttu-id="e79bd-235">かっこがエンコードされていることもありますが、これは必須ではありません。</span><span class="sxs-lookup"><span data-stu-id="e79bd-235">You'll sometimes see parentheses encoded but it's not a requirement.</span></span>

<span data-ttu-id="e79bd-236">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="e79bd-236">Examples:</span></span>

- <span data-ttu-id="e79bd-237">System.Threading.Tasks.Task\`1 は `System.Threading.Tasks.Task%601` になります</span><span class="sxs-lookup"><span data-stu-id="e79bd-237">System.Threading.Tasks.Task\`1 becomes `System.Threading.Tasks.Task%601`</span></span>
- <span data-ttu-id="e79bd-238">System.Exception.\#ctor は `System.Exception.%23ctor` になります</span><span class="sxs-lookup"><span data-stu-id="e79bd-238">System.Exception.\#ctor becomes `System.Exception.%23ctor`</span></span>
- <span data-ttu-id="e79bd-239">System.Lazy\`1.\#ctor(System.Threading.LazyThreadSafetyMode) は `System.Lazy%601.%23ctor%28System.Threading.LazyThreadSafetyMode%29` になります</span><span class="sxs-lookup"><span data-stu-id="e79bd-239">System.Lazy\`1.\#ctor(System.Threading.LazyThreadSafetyMode) becomes  `System.Lazy%601.%23ctor%28System.Threading.LazyThreadSafetyMode%29`</span></span>

## <a name="lists"></a><span data-ttu-id="e79bd-240">表示内容</span><span class="sxs-lookup"><span data-stu-id="e79bd-240">Lists</span></span>

### <a name="ordered-lists"></a><span data-ttu-id="e79bd-241">番号付きリスト</span><span class="sxs-lookup"><span data-stu-id="e79bd-241">Ordered lists</span></span>

1. <span data-ttu-id="e79bd-242">This</span><span class="sxs-lookup"><span data-stu-id="e79bd-242">This</span></span>
1. <span data-ttu-id="e79bd-243">Is</span><span class="sxs-lookup"><span data-stu-id="e79bd-243">Is</span></span>
1. <span data-ttu-id="e79bd-244">An</span><span class="sxs-lookup"><span data-stu-id="e79bd-244">An</span></span>
1. <span data-ttu-id="e79bd-245">順序あり</span><span class="sxs-lookup"><span data-stu-id="e79bd-245">Ordered</span></span>
1. <span data-ttu-id="e79bd-246">リスト</span><span class="sxs-lookup"><span data-stu-id="e79bd-246">List</span></span>

#### <a name="ordered-list-with-an-embedded-list"></a><span data-ttu-id="e79bd-247">埋め込みリストを含む番号付きリスト</span><span class="sxs-lookup"><span data-stu-id="e79bd-247">Ordered list with an embedded list</span></span>

1. <span data-ttu-id="e79bd-248">Here</span><span class="sxs-lookup"><span data-stu-id="e79bd-248">Here</span></span>
1. <span data-ttu-id="e79bd-249">comes</span><span class="sxs-lookup"><span data-stu-id="e79bd-249">comes</span></span>
1. <span data-ttu-id="e79bd-250">1 つ</span><span class="sxs-lookup"><span data-stu-id="e79bd-250">an</span></span>
1. <span data-ttu-id="e79bd-251">embedded</span><span class="sxs-lookup"><span data-stu-id="e79bd-251">embedded</span></span>
    1. <span data-ttu-id="e79bd-252">Miss Scarlett</span><span class="sxs-lookup"><span data-stu-id="e79bd-252">Miss Scarlett</span></span>
    1. <span data-ttu-id="e79bd-253">Professor Plum</span><span class="sxs-lookup"><span data-stu-id="e79bd-253">Professor Plum</span></span>
1. <span data-ttu-id="e79bd-254">ordered</span><span class="sxs-lookup"><span data-stu-id="e79bd-254">ordered</span></span>
1. <span data-ttu-id="e79bd-255">リスト</span><span class="sxs-lookup"><span data-stu-id="e79bd-255">list</span></span>

### <a name="unordered-lists"></a><span data-ttu-id="e79bd-256">記号付きリスト</span><span class="sxs-lookup"><span data-stu-id="e79bd-256">Unordered Lists</span></span>

- <span data-ttu-id="e79bd-257">This</span><span class="sxs-lookup"><span data-stu-id="e79bd-257">This</span></span>
- <span data-ttu-id="e79bd-258">is</span><span class="sxs-lookup"><span data-stu-id="e79bd-258">is</span></span>
- <span data-ttu-id="e79bd-259">a</span><span class="sxs-lookup"><span data-stu-id="e79bd-259">a</span></span>
- <span data-ttu-id="e79bd-260">bulleted</span><span class="sxs-lookup"><span data-stu-id="e79bd-260">bulleted</span></span>
- <span data-ttu-id="e79bd-261">リスト</span><span class="sxs-lookup"><span data-stu-id="e79bd-261">list</span></span>

#### <a name="unordered-list-with-an-embedded-list"></a><span data-ttu-id="e79bd-262">埋め込みリストを含む記号付きリスト</span><span class="sxs-lookup"><span data-stu-id="e79bd-262">Unordered list with an embedded list</span></span>

- <span data-ttu-id="e79bd-263">This</span><span class="sxs-lookup"><span data-stu-id="e79bd-263">This</span></span>
- <span data-ttu-id="e79bd-264">bulleted</span><span class="sxs-lookup"><span data-stu-id="e79bd-264">bulleted</span></span>
- <span data-ttu-id="e79bd-265">リスト</span><span class="sxs-lookup"><span data-stu-id="e79bd-265">list</span></span>
  - <span data-ttu-id="e79bd-266">Mrs. Peacock</span><span class="sxs-lookup"><span data-stu-id="e79bd-266">Mrs. Peacock</span></span>
  - <span data-ttu-id="e79bd-267">Mr. Green</span><span class="sxs-lookup"><span data-stu-id="e79bd-267">Mr. Green</span></span>
- <span data-ttu-id="e79bd-268">次の値を含む</span><span class="sxs-lookup"><span data-stu-id="e79bd-268">contains</span></span>
- <span data-ttu-id="e79bd-269">その他</span><span class="sxs-lookup"><span data-stu-id="e79bd-269">other</span></span>
  1. <span data-ttu-id="e79bd-270">Colonel Mustard</span><span class="sxs-lookup"><span data-stu-id="e79bd-270">Colonel Mustard</span></span>
  1. <span data-ttu-id="e79bd-271">Mrs. White</span><span class="sxs-lookup"><span data-stu-id="e79bd-271">Mrs. White</span></span>
- <span data-ttu-id="e79bd-272">一覧</span><span class="sxs-lookup"><span data-stu-id="e79bd-272">lists</span></span>

## <a name="horizontal-rule"></a><span data-ttu-id="e79bd-273">水平線</span><span class="sxs-lookup"><span data-stu-id="e79bd-273">Horizontal rule</span></span>

---

## <a name="tables"></a><span data-ttu-id="e79bd-274">[テーブル]</span><span class="sxs-lookup"><span data-stu-id="e79bd-274">Tables</span></span>

| <span data-ttu-id="e79bd-275">[テーブル]</span><span class="sxs-lookup"><span data-stu-id="e79bd-275">Tables</span></span>        | <span data-ttu-id="e79bd-276">Are</span><span class="sxs-lookup"><span data-stu-id="e79bd-276">Are</span></span>           | <span data-ttu-id="e79bd-277">Cool</span><span class="sxs-lookup"><span data-stu-id="e79bd-277">Cool</span></span>  |
| ------------- |:-------------:| -----:|
| <span data-ttu-id="e79bd-278">列 3 は</span><span class="sxs-lookup"><span data-stu-id="e79bd-278">col 3 is</span></span>      | <span data-ttu-id="e79bd-279">右揃え</span><span class="sxs-lookup"><span data-stu-id="e79bd-279">right-aligned</span></span> | <span data-ttu-id="e79bd-280">$1600</span><span class="sxs-lookup"><span data-stu-id="e79bd-280">$1600</span></span> |
| <span data-ttu-id="e79bd-281">列 2 は</span><span class="sxs-lookup"><span data-stu-id="e79bd-281">col 2 is</span></span>      | <span data-ttu-id="e79bd-282">中央揃え</span><span class="sxs-lookup"><span data-stu-id="e79bd-282">centered</span></span>      |   <span data-ttu-id="e79bd-283">$12</span><span class="sxs-lookup"><span data-stu-id="e79bd-283">$12</span></span> |
| <span data-ttu-id="e79bd-284">列 1 は既定の</span><span class="sxs-lookup"><span data-stu-id="e79bd-284">col 1 is default</span></span> | <span data-ttu-id="e79bd-285">左揃え</span><span class="sxs-lookup"><span data-stu-id="e79bd-285">left-aligned</span></span>     |    <span data-ttu-id="e79bd-286">$1</span><span class="sxs-lookup"><span data-stu-id="e79bd-286">$1</span></span> |

<span data-ttu-id="e79bd-287">[Markdown Table Generator ツール](https://www.tablesgenerator.com/markdown_tables)を使用して、より簡単にテーブルを作成できます。</span><span class="sxs-lookup"><span data-stu-id="e79bd-287">You can use a [Markdown table generator tool](https://www.tablesgenerator.com/markdown_tables) to help creating them more easily.</span></span>

## <a name="code"></a><span data-ttu-id="e79bd-288">コード</span><span class="sxs-lookup"><span data-stu-id="e79bd-288">Code</span></span>

<span data-ttu-id="e79bd-289">コードを含める最善の方法は、実際に動作するサンプルからのスニペットを含める方法です。</span><span class="sxs-lookup"><span data-stu-id="e79bd-289">The best way to include code is to include snippets from a working sample.</span></span> <span data-ttu-id="e79bd-290">[貢献に関するガイド](../CONTRIBUTING.md#contributing-to-samples)の指示に従って、サンプルを作成します。</span><span class="sxs-lookup"><span data-stu-id="e79bd-290">Create your sample following the instructions in the [contributing guide](../CONTRIBUTING.md#contributing-to-samples).</span></span>

<span data-ttu-id="e79bd-291">次の構文を使用して、コードを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="e79bd-291">You can include the code using the following syntax:</span></span>

```markdown
[!code-<language>[<name>](<pathToFile><queryoption><queryoptionvalue>)]
```

- <span data-ttu-id="e79bd-292">`-<language>` ("*省略可能*" ですが、使用が "*推奨*" されます)</span><span class="sxs-lookup"><span data-stu-id="e79bd-292">`-<language>` (*optional* but *recommended*)</span></span>
  - <span data-ttu-id="e79bd-293">参照されるコード スニペットの言語。</span><span class="sxs-lookup"><span data-stu-id="e79bd-293">Language of the code snippet being referenced.</span></span> <span data-ttu-id="e79bd-294">サポートされる値のリストについては、「[サポートされる言語](#supported-languages)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="e79bd-294">For a list of supported values, see [Supported languages](#supported-languages).</span></span>

- <span data-ttu-id="e79bd-295">`<name>` ("*省略可能*")</span><span class="sxs-lookup"><span data-stu-id="e79bd-295">`<name>` (*optional*)</span></span>
  - <span data-ttu-id="e79bd-296">コード スニペットの名前。</span><span class="sxs-lookup"><span data-stu-id="e79bd-296">Name for the code snippet.</span></span> <span data-ttu-id="e79bd-297">出力 HTML には影響を与えませんが、使用すると、マークダウン ソースの読みやすさを向上できます。</span><span class="sxs-lookup"><span data-stu-id="e79bd-297">It doesn’t have any impact on the output HTML, but you can use it to improve the readability of your Markdown source.</span></span>

- <span data-ttu-id="e79bd-298">`<pathToFile>` ("*必須*")</span><span class="sxs-lookup"><span data-stu-id="e79bd-298">`<pathToFile>` (*mandatory*)</span></span>
  - <span data-ttu-id="e79bd-299">参照するコード スニペット ファイルを示す、ファイルシステム内の相対パス。</span><span class="sxs-lookup"><span data-stu-id="e79bd-299">Relative path in the file system that indicates the code snippet file to reference.</span></span>

- <span data-ttu-id="e79bd-300">`<queryoption>` および `<queryoptionvalue>` ("*省略可能*")</span><span class="sxs-lookup"><span data-stu-id="e79bd-300">`<queryoption>` and `<queryoptionvalue>` (*optional*)</span></span>
  - <span data-ttu-id="e79bd-301">ファイルからコードを取得する方法を指定するために一緒に使用します。</span><span class="sxs-lookup"><span data-stu-id="e79bd-301">Used together to specify how the code should be retrieved from the file:</span></span>
    - <span data-ttu-id="e79bd-302">`#`: `#L{startlinenumber}-L{endlinenumber}` (行の範囲) "*または*" `#{tagname}` (タグ名)。</span><span class="sxs-lookup"><span data-stu-id="e79bd-302">`#`:  `#L{startlinenumber}-L{endlinenumber}` (line range) *or* `#{tagname}` (tag name).</span></span>
    <span data-ttu-id="e79bd-303">行番号は変動するため、使用はお勧めしません。</span><span class="sxs-lookup"><span data-stu-id="e79bd-303">We discourage the use of line numbers because they are very brittle.</span></span> <span data-ttu-id="e79bd-304">コード スニペットの参照方法としては、タグ名が推奨されます。</span><span class="sxs-lookup"><span data-stu-id="e79bd-304">Tag name is the preferred way of referencing code snippets.</span></span>
    - <span data-ttu-id="e79bd-305">`range`:`?range=1,3-5` 行の範囲。</span><span class="sxs-lookup"><span data-stu-id="e79bd-305">`range`: `?range=1,3-5` A range of lines.</span></span> <span data-ttu-id="e79bd-306">この例では、行 1、3、4、5 が含まれます。</span><span class="sxs-lookup"><span data-stu-id="e79bd-306">This example includes lines 1, 3, 4, and 5.</span></span>
    - <span data-ttu-id="e79bd-307">`dedent`:`?dedent=8` スペースの数だけ、行のインデントを解除します。この例では 8 です。</span><span class="sxs-lookup"><span data-stu-id="e79bd-307">`dedent`: `?dedent=8` Dedents the lines by a number of spaces--in this case, 8.</span></span> <span data-ttu-id="e79bd-308">これは、ファイルの行のサブセットを選択する、`range` やその他のクエリ オプションと組み合わせることができます。</span><span class="sxs-lookup"><span data-stu-id="e79bd-308">This can be combined with the `range` and other query options that select a subset of the lines of a file.</span></span>
    - <span data-ttu-id="e79bd-309">`outdent`:`?outdent=8` スペースの数だけ、行のインデントを戻します。この例では 8 です。</span><span class="sxs-lookup"><span data-stu-id="e79bd-309">`outdent`: `?outdent=8` Reverses the indent of the lines by a number of spaces--in this case, 8.</span></span> <span data-ttu-id="e79bd-310">これは、ファイルの行のサブセットを選択する、`range` やその他のクエリ オプションと組み合わせることができます。</span><span class="sxs-lookup"><span data-stu-id="e79bd-310">This can be combined with `range` and other query options that select a subset of the lines of a file.</span></span>

<span data-ttu-id="e79bd-311">可能な限り、タグ名オプションを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="e79bd-311">We recommend using the tag name option whenever possible.</span></span> <span data-ttu-id="e79bd-312">タグ名は、領域の名前、またはソース コードに存在する `Snippettagname` 形式のコード コメントの名前です。</span><span class="sxs-lookup"><span data-stu-id="e79bd-312">The tag name is the name of a region or of a code comment in the format of `Snippettagname` present in the source code.</span></span> <span data-ttu-id="e79bd-313">次の例は、タグ名 `1` を参照する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="e79bd-313">The following example shows how to refer to the tag name `1`:</span></span>

```markdown
[!code-csharp[csrefKeyword#1](../../../../samples/snippets/csharp/language-reference/keywords/throw/throw-1.cs#1)]
```

<span data-ttu-id="e79bd-314">また、スニペット タグが[ここのソース ファイル](https://github.com/dotnet/samples/blob/master/snippets/csharp/language-reference/keywords/throw/throw-1.cs)でどのように構成されているかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="e79bd-314">And you can see how the snippet tags are structured in [this source file](https://github.com/dotnet/samples/blob/master/snippets/csharp/language-reference/keywords/throw/throw-1.cs).</span></span> <span data-ttu-id="e79bd-315">コード スニペット ソース ファイルでの言語別のタグ名の表記の詳細については、[DocFX ガイドライン](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html#tag-name-representation-in-code-snippet-source-file)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e79bd-315">For details about tag name representation in code snippet source files by language, see the [DocFX guidelines](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html#tag-name-representation-in-code-snippet-source-file).</span></span>

<span data-ttu-id="e79bd-316">完全なプログラムからのスニペットを含めることで、すべてのコードが確実に継続的インテグレーション (CI) システムで処理されたものになります。</span><span class="sxs-lookup"><span data-stu-id="e79bd-316">Including snippets from full programs ensures that all code runs through our Continuous Integration (CI) system.</span></span> <span data-ttu-id="e79bd-317">ただし、コンパイル時のエラーやランタイム エラーの原因を表示する必要がある場合は、インライン コード ブロックを使用できます。</span><span class="sxs-lookup"><span data-stu-id="e79bd-317">However, if you need to show something that causes compile time or runtime errors, you can use inline code blocks.</span></span>

### <a name="inline-code-blocks-with-language-identifier"></a><span data-ttu-id="e79bd-318">言語識別子を持つインライン コード ブロック</span><span class="sxs-lookup"><span data-stu-id="e79bd-318">Inline code blocks with language identifier</span></span>

<span data-ttu-id="e79bd-319">3 つのバッククォート (\`\`\`) と言語 ID を使用して、言語固有のカラー コーディングをコード ブロックに適用します。</span><span class="sxs-lookup"><span data-stu-id="e79bd-319">Use three backticks (\`\`\`) + a language ID to apply language-specific color coding to a code block.</span></span> <span data-ttu-id="e79bd-320">次のサポートされる言語のリストは、各言語 ID に対するマークダウン ラベルを示しています。</span><span class="sxs-lookup"><span data-stu-id="e79bd-320">Here is the list of supported languages showing the markdown label for each language ID.</span></span>

#### <a name="supported-languages"></a><span data-ttu-id="e79bd-321">サポートされる言語</span><span class="sxs-lookup"><span data-stu-id="e79bd-321">Supported languages</span></span>

|<span data-ttu-id="e79bd-322">name</span><span class="sxs-lookup"><span data-stu-id="e79bd-322">Name</span></span>|<span data-ttu-id="e79bd-323">マークダウン ラベル</span><span class="sxs-lookup"><span data-stu-id="e79bd-323">Markdown label</span></span>|
|-----|-------|
|<span data-ttu-id="e79bd-324">.NET コンソール</span><span class="sxs-lookup"><span data-stu-id="e79bd-324">.NET Console</span></span>|<span data-ttu-id="e79bd-325">dotnetcli</span><span class="sxs-lookup"><span data-stu-id="e79bd-325">dotnetcli</span></span>|
|<span data-ttu-id="e79bd-326">ASP.NET (C#)</span><span class="sxs-lookup"><span data-stu-id="e79bd-326">ASP.NET (C#)</span></span>|<span data-ttu-id="e79bd-327">aspx-csharp</span><span class="sxs-lookup"><span data-stu-id="e79bd-327">aspx-csharp</span></span>|
|<span data-ttu-id="e79bd-328">ASP.NET (VB)</span><span class="sxs-lookup"><span data-stu-id="e79bd-328">ASP.NET (VB)</span></span>|<span data-ttu-id="e79bd-329">aspx-vb</span><span class="sxs-lookup"><span data-stu-id="e79bd-329">aspx-vb</span></span>|
|<span data-ttu-id="e79bd-330">Azure CLI</span><span class="sxs-lookup"><span data-stu-id="e79bd-330">Azure CLI</span></span>|<span data-ttu-id="e79bd-331">azurecli</span><span class="sxs-lookup"><span data-stu-id="e79bd-331">azurecli</span></span>|
|<span data-ttu-id="e79bd-332">AzCopy</span><span class="sxs-lookup"><span data-stu-id="e79bd-332">AzCopy</span></span>|<span data-ttu-id="e79bd-333">azcopy</span><span class="sxs-lookup"><span data-stu-id="e79bd-333">azcopy</span></span>|
|<span data-ttu-id="e79bd-334">Azure PowerShell</span><span class="sxs-lookup"><span data-stu-id="e79bd-334">Azure PowerShell</span></span>|<span data-ttu-id="e79bd-335">azurepowershell</span><span class="sxs-lookup"><span data-stu-id="e79bd-335">azurepowershell</span></span>|
|<span data-ttu-id="e79bd-336">Bash</span><span class="sxs-lookup"><span data-stu-id="e79bd-336">Bash</span></span>|<span data-ttu-id="e79bd-337">Bash</span><span class="sxs-lookup"><span data-stu-id="e79bd-337">bash</span></span>|
|<span data-ttu-id="e79bd-338">C++</span><span class="sxs-lookup"><span data-stu-id="e79bd-338">C++</span></span>|<span data-ttu-id="e79bd-339">cpp</span><span class="sxs-lookup"><span data-stu-id="e79bd-339">cpp</span></span>|
|<span data-ttu-id="e79bd-340">C++/CX</span><span class="sxs-lookup"><span data-stu-id="e79bd-340">C++/CX</span></span>|<span data-ttu-id="e79bd-341">cppcx</span><span class="sxs-lookup"><span data-stu-id="e79bd-341">cppcx</span></span>|
|<span data-ttu-id="e79bd-342">C++/WinRT</span><span class="sxs-lookup"><span data-stu-id="e79bd-342">C++/WinRT</span></span>|<span data-ttu-id="e79bd-343">cppwinrt</span><span class="sxs-lookup"><span data-stu-id="e79bd-343">cppwinrt</span></span>|
|<span data-ttu-id="e79bd-344">C#</span><span class="sxs-lookup"><span data-stu-id="e79bd-344">C#</span></span>|<span data-ttu-id="e79bd-345">csharp</span><span class="sxs-lookup"><span data-stu-id="e79bd-345">csharp</span></span>|
|<span data-ttu-id="e79bd-346">C# (ブラウザー内)</span><span class="sxs-lookup"><span data-stu-id="e79bd-346">C# in browser</span></span>|<span data-ttu-id="e79bd-347">csharp-interactive</span><span class="sxs-lookup"><span data-stu-id="e79bd-347">csharp-interactive</span></span>|
|<span data-ttu-id="e79bd-348">コンソール</span><span class="sxs-lookup"><span data-stu-id="e79bd-348">Console</span></span>|<span data-ttu-id="e79bd-349">コンソール</span><span class="sxs-lookup"><span data-stu-id="e79bd-349">console</span></span>|
|<span data-ttu-id="e79bd-350">CSHTML</span><span class="sxs-lookup"><span data-stu-id="e79bd-350">CSHTML</span></span>|<span data-ttu-id="e79bd-351">cshtml</span><span class="sxs-lookup"><span data-stu-id="e79bd-351">cshtml</span></span>|
|<span data-ttu-id="e79bd-352">DAX</span><span class="sxs-lookup"><span data-stu-id="e79bd-352">DAX</span></span>|<span data-ttu-id="e79bd-353">dax</span><span class="sxs-lookup"><span data-stu-id="e79bd-353">dax</span></span>|
|<span data-ttu-id="e79bd-354">Dockerfile</span><span class="sxs-lookup"><span data-stu-id="e79bd-354">Dockerfile</span></span>|<span data-ttu-id="e79bd-355">dockerfile</span><span class="sxs-lookup"><span data-stu-id="e79bd-355">dockerfile</span></span>|
|<span data-ttu-id="e79bd-356">F#</span><span class="sxs-lookup"><span data-stu-id="e79bd-356">F#</span></span>|<span data-ttu-id="e79bd-357">fsharp</span><span class="sxs-lookup"><span data-stu-id="e79bd-357">fsharp</span></span>|
|<span data-ttu-id="e79bd-358">移動</span><span class="sxs-lookup"><span data-stu-id="e79bd-358">Go</span></span>|<span data-ttu-id="e79bd-359">go</span><span class="sxs-lookup"><span data-stu-id="e79bd-359">go</span></span>|
|<span data-ttu-id="e79bd-360">HTML</span><span class="sxs-lookup"><span data-stu-id="e79bd-360">HTML</span></span>|<span data-ttu-id="e79bd-361">html</span><span class="sxs-lookup"><span data-stu-id="e79bd-361">html</span></span>|
|<span data-ttu-id="e79bd-362">HTTP</span><span class="sxs-lookup"><span data-stu-id="e79bd-362">HTTP</span></span>|<span data-ttu-id="e79bd-363">http</span><span class="sxs-lookup"><span data-stu-id="e79bd-363">http</span></span>|
|<span data-ttu-id="e79bd-364">Java</span><span class="sxs-lookup"><span data-stu-id="e79bd-364">Java</span></span>|<span data-ttu-id="e79bd-365">java</span><span class="sxs-lookup"><span data-stu-id="e79bd-365">java</span></span>|
|<span data-ttu-id="e79bd-366">JavaScript</span><span class="sxs-lookup"><span data-stu-id="e79bd-366">JavaScript</span></span>|<span data-ttu-id="e79bd-367">javascript</span><span class="sxs-lookup"><span data-stu-id="e79bd-367">javascript</span></span>|
|<span data-ttu-id="e79bd-368">JSON</span><span class="sxs-lookup"><span data-stu-id="e79bd-368">JSON</span></span>|<span data-ttu-id="e79bd-369">json</span><span class="sxs-lookup"><span data-stu-id="e79bd-369">json</span></span>|
|<span data-ttu-id="e79bd-370">Kusto クエリ言語</span><span class="sxs-lookup"><span data-stu-id="e79bd-370">Kusto Query Language</span></span>|<span data-ttu-id="e79bd-371">kusto</span><span class="sxs-lookup"><span data-stu-id="e79bd-371">kusto</span></span>|
|<span data-ttu-id="e79bd-372">Markdown</span><span class="sxs-lookup"><span data-stu-id="e79bd-372">Markdown</span></span>|<span data-ttu-id="e79bd-373">md</span><span class="sxs-lookup"><span data-stu-id="e79bd-373">md</span></span>|
|<span data-ttu-id="e79bd-374">NodeJS</span><span class="sxs-lookup"><span data-stu-id="e79bd-374">NodeJS</span></span>|<span data-ttu-id="e79bd-375">nodejs</span><span class="sxs-lookup"><span data-stu-id="e79bd-375">nodejs</span></span>|
|<span data-ttu-id="e79bd-376">Objective-C</span><span class="sxs-lookup"><span data-stu-id="e79bd-376">Objective-C</span></span>|<span data-ttu-id="e79bd-377">objc</span><span class="sxs-lookup"><span data-stu-id="e79bd-377">objc</span></span>|
|<span data-ttu-id="e79bd-378">OData</span><span class="sxs-lookup"><span data-stu-id="e79bd-378">OData</span></span>|<span data-ttu-id="e79bd-379">odata</span><span class="sxs-lookup"><span data-stu-id="e79bd-379">odata</span></span>|
|<span data-ttu-id="e79bd-380">PHP</span><span class="sxs-lookup"><span data-stu-id="e79bd-380">PHP</span></span>|<span data-ttu-id="e79bd-381">php</span><span class="sxs-lookup"><span data-stu-id="e79bd-381">php</span></span>|
|<span data-ttu-id="e79bd-382">protobuf</span><span class="sxs-lookup"><span data-stu-id="e79bd-382">protobuf</span></span>|<span data-ttu-id="e79bd-383">protobuf</span><span class="sxs-lookup"><span data-stu-id="e79bd-383">protobuf</span></span>|
|<span data-ttu-id="e79bd-384">PowerApps (ドット小数点区切り記号)</span><span class="sxs-lookup"><span data-stu-id="e79bd-384">PowerApps (dot decimal separator)</span></span>|<span data-ttu-id="e79bd-385">powerapps-dot</span><span class="sxs-lookup"><span data-stu-id="e79bd-385">powerapps-dot</span></span>|
|<span data-ttu-id="e79bd-386">PowerApps (コンマ小数点区切り記号)</span><span class="sxs-lookup"><span data-stu-id="e79bd-386">PowerApps (comma decimal separator)</span></span>|<span data-ttu-id="e79bd-387">powerapps-comma</span><span class="sxs-lookup"><span data-stu-id="e79bd-387">powerapps-comma</span></span>|
|<span data-ttu-id="e79bd-388">PowerShell</span><span class="sxs-lookup"><span data-stu-id="e79bd-388">PowerShell</span></span>|<span data-ttu-id="e79bd-389">powershell</span><span class="sxs-lookup"><span data-stu-id="e79bd-389">powershell</span></span>|
|<span data-ttu-id="e79bd-390">Python</span><span class="sxs-lookup"><span data-stu-id="e79bd-390">Python</span></span>|<span data-ttu-id="e79bd-391">Python</span><span class="sxs-lookup"><span data-stu-id="e79bd-391">python</span></span>|
|<span data-ttu-id="e79bd-392">Q#</span><span class="sxs-lookup"><span data-stu-id="e79bd-392">Q#</span></span>|<span data-ttu-id="e79bd-393">qsharp</span><span class="sxs-lookup"><span data-stu-id="e79bd-393">qsharp</span></span>|
|<span data-ttu-id="e79bd-394">R</span><span class="sxs-lookup"><span data-stu-id="e79bd-394">R</span></span>|<span data-ttu-id="e79bd-395">r</span><span class="sxs-lookup"><span data-stu-id="e79bd-395">r</span></span>|
|<span data-ttu-id="e79bd-396">Ruby</span><span class="sxs-lookup"><span data-stu-id="e79bd-396">Ruby</span></span>|<span data-ttu-id="e79bd-397">ruby</span><span class="sxs-lookup"><span data-stu-id="e79bd-397">ruby</span></span>|
|<span data-ttu-id="e79bd-398">SQL</span><span class="sxs-lookup"><span data-stu-id="e79bd-398">SQL</span></span>|<span data-ttu-id="e79bd-399">sql</span><span class="sxs-lookup"><span data-stu-id="e79bd-399">sql</span></span>|
|<span data-ttu-id="e79bd-400">Swift</span><span class="sxs-lookup"><span data-stu-id="e79bd-400">Swift</span></span>|<span data-ttu-id="e79bd-401">swift</span><span class="sxs-lookup"><span data-stu-id="e79bd-401">swift</span></span>|
|<span data-ttu-id="e79bd-402">TypeScript</span><span class="sxs-lookup"><span data-stu-id="e79bd-402">TypeScript</span></span>|<span data-ttu-id="e79bd-403">typescript</span><span class="sxs-lookup"><span data-stu-id="e79bd-403">typescript</span></span>|
|<span data-ttu-id="e79bd-404">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e79bd-404">Visual Basic</span></span>|<span data-ttu-id="e79bd-405">VB</span><span class="sxs-lookup"><span data-stu-id="e79bd-405">vb</span></span>|
|<span data-ttu-id="e79bd-406">VBScript</span><span class="sxs-lookup"><span data-stu-id="e79bd-406">VBScript</span></span>|<span data-ttu-id="e79bd-407">vbscript</span><span class="sxs-lookup"><span data-stu-id="e79bd-407">vbscript</span></span>|
|<span data-ttu-id="e79bd-408">XAML</span><span class="sxs-lookup"><span data-stu-id="e79bd-408">XAML</span></span>|<span data-ttu-id="e79bd-409">xaml</span><span class="sxs-lookup"><span data-stu-id="e79bd-409">xaml</span></span>|
|<span data-ttu-id="e79bd-410">XML</span><span class="sxs-lookup"><span data-stu-id="e79bd-410">XML</span></span>|<span data-ttu-id="e79bd-411">xml</span><span class="sxs-lookup"><span data-stu-id="e79bd-411">xml</span></span>|

<span data-ttu-id="e79bd-412">`csharp-interactive` 名で、C# 言語と、ブラウザーからサンプルを実行する機能を指定します。</span><span class="sxs-lookup"><span data-stu-id="e79bd-412">The `csharp-interactive` name specifies the C# language, and the ability to run the samples from the browser.</span></span> <span data-ttu-id="e79bd-413">このようなスニペットは Docker コンテナーでコンパイル、実行され、そのプログラム実行の結果がユーザーのブラウザー ウィンドウに表示されます。</span><span class="sxs-lookup"><span data-stu-id="e79bd-413">These snippets are compiled and executed in a Docker container, and the results of that program execution are displayed in the user's browser window.</span></span>

<span data-ttu-id="e79bd-414">C# (\`\`\`csharp)、Python (\`\`\`python)、PowerShell (\`\`\`powershell) の言語 ID を使用したコード ブロックの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="e79bd-414">The following are examples of code blocks using the language IDs for C# (\`\`\`csharp), Python (\`\`\`python), and PowerShell (\`\`\`powershell).</span></span>

##### <a name="c"></a><span data-ttu-id="e79bd-415">C\#</span><span class="sxs-lookup"><span data-stu-id="e79bd-415">C\#</span></span>

```csharp
using System;
namespace HelloWorld
{
    class Hello
    {
        static void Main()
        {
            Console.WriteLine("Hello World!");

            // Keep the console window open in debug mode.
            Console.WriteLine("Press any key to exit.");
            Console.ReadKey();
        }
    }
}
```

#### <a name="python"></a><span data-ttu-id="e79bd-416">Python</span><span class="sxs-lookup"><span data-stu-id="e79bd-416">Python</span></span>

```python
friends = ['john', 'pat', 'gary', 'michael']
for i, name in enumerate(friends):
    print "iteration {iteration} is {name}".format(iteration=i, name=name)
```

#### <a name="powershell"></a><span data-ttu-id="e79bd-417">PowerShell</span><span class="sxs-lookup"><span data-stu-id="e79bd-417">PowerShell</span></span>

```powershell
Clear-Host
$Directory = "C:\Windows\"
$Files = Get-Childitem $Directory -recurse -Include *.log `
-ErrorAction SilentlyContinue
```

### <a name="generic-code-block"></a><span data-ttu-id="e79bd-418">汎用のコード ブロック</span><span class="sxs-lookup"><span data-stu-id="e79bd-418">Generic code block</span></span>

<span data-ttu-id="e79bd-419">汎用のコード ブロック コーディングには、3 つのバッククォート (&#96;&#96;&#96;) を使用します。</span><span class="sxs-lookup"><span data-stu-id="e79bd-419">Use three backticks (&#96;&#96;&#96;) for generic code block coding.</span></span>

> <span data-ttu-id="e79bd-420">お勧めする方法は、前のセクションで説明したようにコード ブロックを言語識別子と併用して、ドキュメント サイトで構文が正しく強調表示されるようにすることです。</span><span class="sxs-lookup"><span data-stu-id="e79bd-420">The recommended approach is to use code blocks with language identifiers as explained in the previous section to ensure the proper syntax highlighting in the documentation site.</span></span> <span data-ttu-id="e79bd-421">汎用のコード ブロックは、必要な場合にのみ使用します。</span><span class="sxs-lookup"><span data-stu-id="e79bd-421">Use generic code blocks only when necessary.</span></span>

```
function fancyAlert(arg) {
    if(arg) {
        $.docs({div:'#foo'})
    }
}
```

## <a name="blockquotes"></a><span data-ttu-id="e79bd-422">ブロック引用</span><span class="sxs-lookup"><span data-stu-id="e79bd-422">Blockquotes</span></span>

> <span data-ttu-id="e79bd-423">1000 万年続いた干ばつにより、とうに恐竜の天下は終わっていた。</span><span class="sxs-lookup"><span data-stu-id="e79bd-423">The drought had lasted now for ten million years, and the reign of the terrible lizards had long since ended.</span></span> <span data-ttu-id="e79bd-424">いつかアフリカと呼ばれるであろう大陸の、ここ赤道上では、生存を賭けた戦いは激しさを増した新たなクライマックスを迎え、勝利者が誰になるのかまだ分からなかった。</span><span class="sxs-lookup"><span data-stu-id="e79bd-424">Here on the Equator, in the continent which would one day be known as Africa, the battle for existence had reached a new climax of ferocity, and the victor was not yet in sight.</span></span> <span data-ttu-id="e79bd-425">不毛で乾燥したこの地では、小型か敏捷かどう猛でなければ、栄えることはおろか、生き残る希望さえ持てなかった。</span><span class="sxs-lookup"><span data-stu-id="e79bd-425">In this barren and desiccated land, only the small or the swift or the fierce could flourish, or even hope to survive.</span></span>

## <a name="images"></a><span data-ttu-id="e79bd-426">イメージ</span><span class="sxs-lookup"><span data-stu-id="e79bd-426">Images</span></span>

### <a name="static-image-or-animated-gif"></a><span data-ttu-id="e79bd-427">静的イメージまたはアニメーション GIF</span><span class="sxs-lookup"><span data-stu-id="e79bd-427">Static Image or Animated gif</span></span>

```markdown
![this is the alt text](../images/Logo_DotNet.png)
```

![これは代替テキストです](../images/Logo_DotNet.png)

### <a name="linked-image"></a><span data-ttu-id="e79bd-429">リンク画像</span><span class="sxs-lookup"><span data-stu-id="e79bd-429">Linked Image</span></span>

```markdown
[![alt text for linked image](../images/Logo_DotNet.png)](https://dot.net)
```

<span data-ttu-id="e79bd-430">[![リンク画像の代替テキスト](../images/Logo_DotNet.png)](https://dot.net)</span><span class="sxs-lookup"><span data-stu-id="e79bd-430">[![alt text for linked image](../images/Logo_DotNet.png)](https://dot.net)</span></span>

## <a name="videos"></a><span data-ttu-id="e79bd-431">ビデオ</span><span class="sxs-lookup"><span data-stu-id="e79bd-431">Videos</span></span>

<span data-ttu-id="e79bd-432">現在、次の構文を使用して、Channel 9 と YouTube の両方のビデオを埋め込むことができます。</span><span class="sxs-lookup"><span data-stu-id="e79bd-432">Currently, you can embed both Channel 9 and YouTube videos with the following syntax:</span></span>

### <a name="channel-9"></a><span data-ttu-id="e79bd-433">Channel 9</span><span class="sxs-lookup"><span data-stu-id="e79bd-433">Channel 9</span></span>

```markdown
> [!VIDEO <channel9_video_link>]
```

<span data-ttu-id="e79bd-434">ビデオの正しい URL を取得するには、ビデオ フレームの下にある **[埋め込み]** タブを選択して、`<iframe>` 要素から URL をコピーします。</span><span class="sxs-lookup"><span data-stu-id="e79bd-434">To get the video's correct URL, select the **Embed** tab below the video frame, and copy the URL from the `<iframe>` element.</span></span> <span data-ttu-id="e79bd-435">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="e79bd-435">For example:</span></span>

```markdown
> [!VIDEO https://channel9.msdn.com/Blogs/dotnet/NET-Core-20-Released/player]
```

### <a name="youtube"></a><span data-ttu-id="e79bd-436">YouTube</span><span class="sxs-lookup"><span data-stu-id="e79bd-436">YouTube</span></span>

<span data-ttu-id="e79bd-437">ビデオの正しい URL を取得するには、ビデオ右クリックし、 **[埋め込みコードのコピー]** を選択して、`<iframe>` 要素から URL をコピーします。</span><span class="sxs-lookup"><span data-stu-id="e79bd-437">To get the video's correct URL, right-click on the video, select **Copy Embed Code**, and copy the URL from the `<iframe>` element.</span></span>

```markdown
> [!VIDEO <youtube_video_link>]
```

<span data-ttu-id="e79bd-438">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="e79bd-438">For example:</span></span>

```markdown
> [!VIDEO https://www.youtube.com/embed/Q2mMbjw6cLA]
```

## <a name="docsmicrosoft-extensions"></a><span data-ttu-id="e79bd-439">docs.microsoft 拡張機能</span><span class="sxs-lookup"><span data-stu-id="e79bd-439">docs.microsoft extensions</span></span>

<span data-ttu-id="e79bd-440">docs.microsoft により、GitHub Flavored Markdown にいくつかの拡張機能が追加されます。</span><span class="sxs-lookup"><span data-stu-id="e79bd-440">docs.microsoft provides a few additional extensions to GitHub Flavored Markdown.</span></span>

### <a name="alerts"></a><span data-ttu-id="e79bd-441">アラート</span><span class="sxs-lookup"><span data-stu-id="e79bd-441">Alerts</span></span>

<span data-ttu-id="e79bd-442">ドキュメント サイトに適切なスタイルで表示できるようにするため、次のアラート スタイルを使用することが重要です。</span><span class="sxs-lookup"><span data-stu-id="e79bd-442">It's important to use the following alert styles so they render with the proper style in the documentation site.</span></span> <span data-ttu-id="e79bd-443">ただし、GitHub のレンダリング エンジンではこれらは区別されません。</span><span class="sxs-lookup"><span data-stu-id="e79bd-443">However, the rendering engine on GitHub doesn't diferentiate them.</span></span>

```markdown
> [!NOTE]
> Information the user should notice even if skimming.

> [!TIP]
> Optional information to help a user be more successful.

> [!IMPORTANT]
> Essential information required for user success.

> [!CAUTION]
> Negative potential consequences of an action.

> [!WARNING]
> Dangerous certain consequences of an action.
```

<span data-ttu-id="e79bd-444">また、これらは次のように表示されます:![アラート スタイル](../images/alerts.png)</span><span class="sxs-lookup"><span data-stu-id="e79bd-444">And they'll render like this: ![Alert styles](../images/alerts.png)</span></span>

### <a name="includes"></a><span data-ttu-id="e79bd-445">含まれているバージョン</span><span class="sxs-lookup"><span data-stu-id="e79bd-445">Includes</span></span>

<span data-ttu-id="e79bd-446">Include を使用して、あるファイルのマークダウンを別のファイルに埋め込むことができます。</span><span class="sxs-lookup"><span data-stu-id="e79bd-446">You can embed the Markdown of one file into another using an include.</span></span>

[!INCLUDE[sample include file](../includes/sampleinclude.md)]

### <a name="checked-lists"></a><span data-ttu-id="e79bd-447">チェックされたファイル</span><span class="sxs-lookup"><span data-stu-id="e79bd-447">Checked lists</span></span>

<span data-ttu-id="e79bd-448">リストには、カスタム スタイルを使用できます。</span><span class="sxs-lookup"><span data-stu-id="e79bd-448">A custom style is available for lists.</span></span> <span data-ttu-id="e79bd-449">緑色のチェック マークが付けられたリストを表示できます。</span><span class="sxs-lookup"><span data-stu-id="e79bd-449">You can render lists with green check marks.</span></span>

> [!div class="checklist"]
>
> - <span data-ttu-id="e79bd-450">.NET Core アプリの作成方法</span><span class="sxs-lookup"><span data-stu-id="e79bd-450">How to create a .NET Core app</span></span>
> - <span data-ttu-id="e79bd-451">Microsoft.XmlSerializer.Generator パッケージへの参照を追加する方法</span><span class="sxs-lookup"><span data-stu-id="e79bd-451">How to add a reference to the Microsoft.XmlSerializer.Generator package</span></span>
> - <span data-ttu-id="e79bd-452">MyApp.csproj を編集して依存関係を追加する方法</span><span class="sxs-lookup"><span data-stu-id="e79bd-452">How to edit your MyApp.csproj to add dependencies</span></span>
> - <span data-ttu-id="e79bd-453">クラスと XmlSerializer を追加する方法</span><span class="sxs-lookup"><span data-stu-id="e79bd-453">How to add a class and an XmlSerializer</span></span>
> - <span data-ttu-id="e79bd-454">アプリケーションをビルドして実行する方法</span><span class="sxs-lookup"><span data-stu-id="e79bd-454">How to build and run the application</span></span>

<span data-ttu-id="e79bd-455">使用中のチェックされたリストの例は、[.NET Core ドキュメント](https://docs.microsoft.com/dotnet/core/additional-tools/xml-serializer-generator)で確認できます。</span><span class="sxs-lookup"><span data-stu-id="e79bd-455">You can see an example of checked lists in action in the [.NET Core docs](https://docs.microsoft.com/dotnet/core/additional-tools/xml-serializer-generator).</span></span>

### <a name="buttons"></a><span data-ttu-id="e79bd-456">ボタン</span><span class="sxs-lookup"><span data-stu-id="e79bd-456">Buttons</span></span>

> [!div class="button"]
> [<span data-ttu-id="e79bd-457">ボタン リンク</span><span class="sxs-lookup"><span data-stu-id="e79bd-457">button links</span></span>](../docs/core/index.md)

<span data-ttu-id="e79bd-458">使用中のボタンの例は、[Visual Studio ドキュメント](https://docs.microsoft.com/visualstudio/install/install-visual-studio#step-2---download-visual-studio)で確認できます。</span><span class="sxs-lookup"><span data-stu-id="e79bd-458">You can see an example of buttons in action in the [Visual Studio docs](https://docs.microsoft.com/visualstudio/install/install-visual-studio#step-2---download-visual-studio).</span></span>

### <a name="selectors"></a><span data-ttu-id="e79bd-459">セレクター</span><span class="sxs-lookup"><span data-stu-id="e79bd-459">Selectors</span></span>

> [!div class="op_single_selector"]
>
> - [macOS](../docs/core/tutorials/using-on-macos.md)
> - [Windows](../docs/core/tutorials/with-visual-studio.md)

<span data-ttu-id="e79bd-462">使用中のセレクターの例は、[Azure ドキュメント](https://docs.microsoft.com/azure/expressroute/expressroute-howto-circuit-classic)で確認できます。</span><span class="sxs-lookup"><span data-stu-id="e79bd-462">You can see an example of selectors in action at the [Azure docs](https://docs.microsoft.com/azure/expressroute/expressroute-howto-circuit-classic).</span></span>

### <a name="step-by-steps"></a><span data-ttu-id="e79bd-463">操作手順</span><span class="sxs-lookup"><span data-stu-id="e79bd-463">Step-By-Steps</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="e79bd-464">[前へ](../docs/csharp/expression-trees-interpreting.md)
>[次へ](../docs/csharp/expression-trees-translating.md)</span><span class="sxs-lookup"><span data-stu-id="e79bd-464">[Previous](../docs/csharp/expression-trees-interpreting.md)
[Next](../docs/csharp/expression-trees-translating.md)</span></span>

<span data-ttu-id="e79bd-465">使用中の操作手順の例は、[C# ガイド](https://docs.microsoft.com/dotnet/csharp/tour-of-csharp/program-structure)で確認できます。</span><span class="sxs-lookup"><span data-stu-id="e79bd-465">You can see an example of step-by-steps in action at the [C# Guide](https://docs.microsoft.com/dotnet/csharp/tour-of-csharp/program-structure).</span></span>
