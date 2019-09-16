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
ms.openlocfilehash: 37133a90ae5bfa18ae17c279caff40d0d30ea25c
ms.sourcegitcommit: 33c8d6f7342a4bb2c577842b7f075b0e20a2fa40
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2019
ms.locfileid: "70928924"
---
# <a name="metadata-and-markdown-template"></a><span data-ttu-id="890fc-102">メタデータとマークダウン テンプレート</span><span class="sxs-lookup"><span data-stu-id="890fc-102">Metadata and Markdown Template</span></span>

<span data-ttu-id="890fc-103">この dotnet/ドキュメント テンプレートには、メタデータの設定に関するガイドラインだけでなく、マークダウン構文の例が含まれています。</span><span class="sxs-lookup"><span data-stu-id="890fc-103">This dotnet/docs template contains examples of Markdown syntax, as well as guidance on setting the metadata.</span></span> <span data-ttu-id="890fc-104">これを最大限に活用するには、[生のマークダウン](https://raw.githubusercontent.com/dotnet/docs/master/styleguide/template.md)と[表示ビュー](https://github.com/dotnet/docs/blob/master/styleguide/template.md)の両方を表示する必要があります (たとえば、生のマークダウンにはメタデータ ブロックが表示されますが、表示ビューには表示されません)。</span><span class="sxs-lookup"><span data-stu-id="890fc-104">To get the most of it, you must view both the [raw Markdown](https://raw.githubusercontent.com/dotnet/docs/master/styleguide/template.md) and the [rendered view](https://github.com/dotnet/docs/blob/master/styleguide/template.md) (for instance, the raw Markdown shows the metadata block, while the rendered view does not).</span></span>

<span data-ttu-id="890fc-105">マークダウン ファイルを作成する場合、このテンプレートを新しいファイルにコピーして、下記のようにメタデータを記入し、上の H1 見出しを記事のタイトルに設定して、コンテンツを削除します。</span><span class="sxs-lookup"><span data-stu-id="890fc-105">When creating a Markdown file, you should copy this template to a new file, fill out the metadata as specified below, set the H1 heading above to the title of the article, and delete the content.</span></span>

## <a name="metadata"></a><span data-ttu-id="890fc-106">メタデータ</span><span class="sxs-lookup"><span data-stu-id="890fc-106">Metadata</span></span>

<span data-ttu-id="890fc-107">完全なメタデータ ブロックは上部 ([生のマークダウン](https://raw.githubusercontent.com/dotnet/docs/master/styleguide/template.md)の) にあり、必須フィールドとオプション フィールドに分割されています。</span><span class="sxs-lookup"><span data-stu-id="890fc-107">The full metadata block is above (in the [raw Markdown](https://raw.githubusercontent.com/dotnet/docs/master/styleguide/template.md)), divided into required fields and optional fields.</span></span> <span data-ttu-id="890fc-108">次に注意事項をいくつか示します。</span><span class="sxs-lookup"><span data-stu-id="890fc-108">Some key notes:</span></span>

- <span data-ttu-id="890fc-109">コロン (:) とメタデータ要素の値の間にはスペースが**必要です**。</span><span class="sxs-lookup"><span data-stu-id="890fc-109">You **must** have a space between the colon (:) and the value for a metadata element.</span></span>
- <span data-ttu-id="890fc-110">省略可能なメタデータ要素に値がない場合は、# を使ってその要素をコメント アウトするか、削除します (空白のままにしたり、"na" を使用したりしないでください)。</span><span class="sxs-lookup"><span data-stu-id="890fc-110">If an optional metadata element doesn't have a value, comment out the element with a # or remove it (don't leave it blank or use "na").</span></span> <span data-ttu-id="890fc-111">コメント アウトされた要素に値を追加する場合は、# を必ず削除してください。</span><span class="sxs-lookup"><span data-stu-id="890fc-111">If you're adding a value to an element that was commented out, be sure to remove the #.</span></span>
- <span data-ttu-id="890fc-112">値 (タイトルなど) にコロンが含まれていると、メタデータ パーサーが中断します。</span><span class="sxs-lookup"><span data-stu-id="890fc-112">Colons in a value (for example, a title) break the metadata parser.</span></span> <span data-ttu-id="890fc-113">この場合は、タイトルを二重引用符で囲みます (例: `title: "Writing .NET Core console apps: An advanced step-by-step guide"`)。</span><span class="sxs-lookup"><span data-stu-id="890fc-113">In this case, surround the title with double quotes (for example, `title: "Writing .NET Core console apps: An advanced step-by-step guide"`).</span></span>
- <span data-ttu-id="890fc-114">**title**:検索エンジンの結果に表示されます。</span><span class="sxs-lookup"><span data-stu-id="890fc-114">**title**: Appears in search engine results.</span></span> <span data-ttu-id="890fc-115">タイトルは H1 見出しのタイトルと同一でなくてもかまいません。60 文字以下にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="890fc-115">The title shouldn't be identical to the title in your H1 heading, and it should contain 60 characters or less.</span></span>
- <span data-ttu-id="890fc-116">**説明**:記事の内容を要約します。</span><span class="sxs-lookup"><span data-stu-id="890fc-116">**description**: Summarizes the content of the article.</span></span> <span data-ttu-id="890fc-117">これは通常、検索結果ページに表示されますが、検索ランキングには使用されません。</span><span class="sxs-lookup"><span data-stu-id="890fc-117">It's usually shown in the search results page, but it isn't used for search ranking.</span></span> <span data-ttu-id="890fc-118">長さは、スペースを含め 115 から 145 文字にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="890fc-118">Its length should be 115-145 characters including spaces.</span></span>
- <span data-ttu-id="890fc-119">**author** および **ms.author**:"author" フィールドには、作成者のエイリアスではなく、**GitHub ユーザー名**を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="890fc-119">**author** and **ms.author**: The author field should contain the **GitHub username** of the author, not his/her alias.</span></span>  <span data-ttu-id="890fc-120">一方で、**ms.author** フィールドには、Microsoft エイリアスが記載され、記事の管理者が示されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="890fc-120">The **ms.author** field, on the other hand, should contain a Microsoft alias and indicates the person responsible for maintaining the article.</span></span>
- <span data-ttu-id="890fc-121">**ms.topic**:トピックの種類です。</span><span class="sxs-lookup"><span data-stu-id="890fc-121">**ms.topic**: The topic type.</span></span> <span data-ttu-id="890fc-122">最も一般的な値は `conceptual` であり、グローバル レベルに設定されています。</span><span class="sxs-lookup"><span data-stu-id="890fc-122">The most common value is `conceptual` and is set at a global level.</span></span> <span data-ttu-id="890fc-123">使用されるその他の一般的な値は、`tutorial`、`overview`、`reference` です。</span><span class="sxs-lookup"><span data-stu-id="890fc-123">Other common values used are `tutorial`, `overview`, and `reference`.</span></span>
- <span data-ttu-id="890fc-124">**ms.devlang** では、トピックに表示される言語フィルターが定義されます。</span><span class="sxs-lookup"><span data-stu-id="890fc-124">**ms.devlang** defines the language filter displayed for the topic.</span></span> <span data-ttu-id="890fc-125">「[サポートされる言語](#supported-languages)」セクションに、サポートされる値のリストが表示されます。</span><span class="sxs-lookup"><span data-stu-id="890fc-125">You can see a list of the supported values in the [Supported languages](#supported-languages) section.</span></span> <span data-ttu-id="890fc-126">トピックの中に複数のプログラミング言語がある場合にのみ設定が必要です。</span><span class="sxs-lookup"><span data-stu-id="890fc-126">Only needs to be set when there's more than one programming language covered in the topic.</span></span> <span data-ttu-id="890fc-127">通常、コンテンツ内にあるこの値については、`csharp`、`vb`、`fsharp`、`cpp` のみを使用します。</span><span class="sxs-lookup"><span data-stu-id="890fc-127">Typically, we only use `csharp`, `vb`, `fsharp`, and `cpp` for this value in our content.</span></span>
- <span data-ttu-id="890fc-128">**ms.prod**:BI の目的に使用される製品 ID です。</span><span class="sxs-lookup"><span data-stu-id="890fc-128">**ms.prod**: Product identification used for BI purposes.</span></span> <span data-ttu-id="890fc-129">これらは通常グローバル レベルに設定されているため、各記事のメタデータ ブロックには、通常は表示されません。</span><span class="sxs-lookup"><span data-stu-id="890fc-129">They're usually set at a global level, so they don't usually appear in the metadata block of each article.</span></span>
- <span data-ttu-id="890fc-130">**ms.technology**:追加の BI 分類です。</span><span class="sxs-lookup"><span data-stu-id="890fc-130">**ms.technology**: Additional BI classification.</span></span> <span data-ttu-id="890fc-131">サポートされる値の一部として、C# トピックの場合は `devlang-csharp`、F# トピックの場合は `devlang-fsharp`、VB トピックの場合は `devlang-visual-basic` があります。</span><span class="sxs-lookup"><span data-stu-id="890fc-131">Some of the supported values are: `devlang-csharp` for C# topics, `devlang-fsharp` for F# topics, and `devlang-visual-basic` for VB topics.</span></span> <span data-ttu-id="890fc-132">その他のガイドについては、値が異なるため、チームのメンバーに助言を求めてください。</span><span class="sxs-lookup"><span data-stu-id="890fc-132">For other guides, the values will vary, so ask a member of the team for guidance.</span></span>
- <span data-ttu-id="890fc-133">**ms.date**:MM/DD/YYYY 形式の日付です。</span><span class="sxs-lookup"><span data-stu-id="890fc-133">**ms.date**: A date in the format MM/dd/yyyy.</span></span> <span data-ttu-id="890fc-134">公開済みページに表示される日付です。前回、記事が大幅に編集されたか、"最新" であることが保証された (すなわち、記事がレビュー済みで、最新であるとみなされた) 日付を示します。</span><span class="sxs-lookup"><span data-stu-id="890fc-134">Displayed on the published page to indicate the last time the article was substantially edited or guaranteed "fresh" (that is, the article was reviewed and considered up-to-date).</span></span>
- <span data-ttu-id="890fc-135">**helpviewer_keywords**:エントリが、オフライン ブック インデックスに使用されます (Visual Studio の機能)。</span><span class="sxs-lookup"><span data-stu-id="890fc-135">**helpviewer_keywords**: Entries are used for the offline books index (functionality in Visual Studio).</span></span>
- <span data-ttu-id="890fc-136">**f1_keywords**:記事を F1 キーに接続します (Visual Studio の機能)。</span><span class="sxs-lookup"><span data-stu-id="890fc-136">**f1_keywords**: Connects the article to the F1 key (functionality in Visual Studio).</span></span>

## <a name="basic-markdown-gfm-and-special-characters"></a><span data-ttu-id="890fc-137">基本マークダウン、GFM、特殊文字</span><span class="sxs-lookup"><span data-stu-id="890fc-137">Basic Markdown, GFM, and special characters</span></span>

<span data-ttu-id="890fc-138">すべての基本マークダウンと GitHub Flavored Markdown (GFM) がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="890fc-138">All basic and GitHub Flavored Markdown (GFM) is supported.</span></span> <span data-ttu-id="890fc-139">それらの詳細については、次を参照してください。</span><span class="sxs-lookup"><span data-stu-id="890fc-139">For more information on these, see:</span></span>

- [<span data-ttu-id="890fc-140">Baseline Markdown syntax (ベースライン マークダウン構文)</span><span class="sxs-lookup"><span data-stu-id="890fc-140">Baseline Markdown syntax</span></span>](https://daringfireball.net/projects/markdown/syntax)
- [<span data-ttu-id="890fc-141">GFM documentation (GFM ドキュメント)</span><span class="sxs-lookup"><span data-stu-id="890fc-141">GFM documentation</span></span>](https://guides.github.com/features/mastering-markdown)

<span data-ttu-id="890fc-142">マークダウンでは書式設定に \*、\`、\# などの特殊文字を使用します。</span><span class="sxs-lookup"><span data-stu-id="890fc-142">Markdown uses special characters such as \*, \`, and \# for formatting.</span></span> <span data-ttu-id="890fc-143">これらの文字のいずれかをコンテンツに含める場合は、次の 2 つのどちらかを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="890fc-143">If you wish to include one of these characters in your content, you must do one of two things:</span></span>

- <span data-ttu-id="890fc-144">特殊文字の前にバックスラッシュを入力して、"エスケープ" する (たとえば、\* の場合は `\*`)</span><span class="sxs-lookup"><span data-stu-id="890fc-144">Put a backslash before the special character to "escape" it (for example, `\*` for a \*)</span></span>
- <span data-ttu-id="890fc-145">文字の [HTML エンティティ コード](https://www.ascii.cl/htmlcodes.htm)を使用する (たとえば、&#42 の場合は `&#42;`)。</span><span class="sxs-lookup"><span data-stu-id="890fc-145">Use the [HTML entity code](https://www.ascii.cl/htmlcodes.htm) for the character (for example, `&#42;` for a &#42;).</span></span>

## <a name="file-name"></a><span data-ttu-id="890fc-146">ファイル名</span><span class="sxs-lookup"><span data-stu-id="890fc-146">File name</span></span>

<span data-ttu-id="890fc-147">ファイル名には次の規則を使用します。</span><span class="sxs-lookup"><span data-stu-id="890fc-147">File names use the following rules:</span></span>

- <span data-ttu-id="890fc-148">小文字、数字、ハイフンのみを使用する。</span><span class="sxs-lookup"><span data-stu-id="890fc-148">Contain only lowercase letters, numbers, and hyphens.</span></span>
- <span data-ttu-id="890fc-149">スペースや句読点を使用しない。</span><span class="sxs-lookup"><span data-stu-id="890fc-149">No spaces or punctuation characters.</span></span> <span data-ttu-id="890fc-150">ハイフンを使用して、ファイル名の単語と数字を区切る。</span><span class="sxs-lookup"><span data-stu-id="890fc-150">Use the hyphens to separate words and numbers in the file name.</span></span>
- <span data-ttu-id="890fc-151">develop (開発)、buy (購入)、build (ビルド)、troubleshoot (トラブルシューティング) など、具体的な動作動詞を使用する。</span><span class="sxs-lookup"><span data-stu-id="890fc-151">Use action verbs that are specific, such as develop, buy, build, troubleshoot.</span></span> <span data-ttu-id="890fc-152">-ing 形の語は使用しません。</span><span class="sxs-lookup"><span data-stu-id="890fc-152">No -ing words.</span></span>
- <span data-ttu-id="890fc-153">小さな単語を使用しない。a、and、the、in、or などは含めません。</span><span class="sxs-lookup"><span data-stu-id="890fc-153">No small words - don't include a, and, the, in, or, etc.</span></span>
- <span data-ttu-id="890fc-154">マークダウンで記述し、.md ファイル拡張子を使用する必要がある。</span><span class="sxs-lookup"><span data-stu-id="890fc-154">Must be in Markdown and use the .md file extension.</span></span>
- <span data-ttu-id="890fc-155">ファイル名を極力短くする。</span><span class="sxs-lookup"><span data-stu-id="890fc-155">Keep file names reasonably short.</span></span> <span data-ttu-id="890fc-156">記事の URL の一部となるためです。</span><span class="sxs-lookup"><span data-stu-id="890fc-156">They are part of the URL for your articles.</span></span>

## <a name="headings"></a><span data-ttu-id="890fc-157">見出し</span><span class="sxs-lookup"><span data-stu-id="890fc-157">Headings</span></span>

<span data-ttu-id="890fc-158">文スタイルで大文字化します。</span><span class="sxs-lookup"><span data-stu-id="890fc-158">Use sentence-style capitalization.</span></span> <span data-ttu-id="890fc-159">見出しの最初の単語は常に大文字にします。ただし、タイトルまたは見出しのコロン後の単語は大文字にしないでください (例: "方法: sort")。</span><span class="sxs-lookup"><span data-stu-id="890fc-159">Always capitalize the first word of a heading, but don't capitalize the word following a colon in a title or heading (for example, "How to: sort an array").</span></span>

<span data-ttu-id="890fc-160">見出しは atx スタイルを使用して作成する必要があります。つまり、見出しを示すために行の先頭に 1 から 6 文字のハッシュ文字 (#) を使用します。これは、HTML 見出しレベルの H1 〜 H6 に対応します。</span><span class="sxs-lookup"><span data-stu-id="890fc-160">Headings should be done using atx-style, that is, use 1-6 hash characters (#) at the start of the line to indicate a heading, corresponding to HTML headings levels H1 through H6.</span></span> <span data-ttu-id="890fc-161">レベル 1 とレベル 2 のヘッダーの例が上で使用されています。</span><span class="sxs-lookup"><span data-stu-id="890fc-161">Examples of first- and second-level headers are used above.</span></span>

<span data-ttu-id="890fc-162">トピックのレベル 1 の見出し (H1) は 1 つだけにする**必要があります**。これがページ上のタイトルとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="890fc-162">There **must** be only one first-level heading (H1) in your topic, which will be displayed as the on-page title.</span></span>

<span data-ttu-id="890fc-163">見出しが `#` 文字で終わる場合は、タイトルを正しく表示するために末尾に余分の `#` 文字を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="890fc-163">If your heading finishes with a `#` character, you need to add an extra `#` character in the end in order for the title to render correctly.</span></span> <span data-ttu-id="890fc-164">たとえば、`# Async Programming in F# #` のようにします。</span><span class="sxs-lookup"><span data-stu-id="890fc-164">For example, `# Async Programming in F# #`.</span></span>

<span data-ttu-id="890fc-165">レベル 2 の見出しは、ページ上タイトルの下にある "この記事内" セクションに表示されるページ上の目次を生成します。</span><span class="sxs-lookup"><span data-stu-id="890fc-165">Second-level headings will generate the on-page TOC that appears in the "In this article" section underneath the on-page title.</span></span>

### <a name="third-level-heading"></a><span data-ttu-id="890fc-166">レベル 3 の見出し</span><span class="sxs-lookup"><span data-stu-id="890fc-166">Third-level heading</span></span>
#### <a name="fourth-level-heading"></a><span data-ttu-id="890fc-167">レベル 4 の見出し</span><span class="sxs-lookup"><span data-stu-id="890fc-167">Fourth-level heading</span></span>
##### <a name="fifth-level-heading"></a><span data-ttu-id="890fc-168">レベル 5 の見出し</span><span class="sxs-lookup"><span data-stu-id="890fc-168">Fifth level heading</span></span>
###### <a name="sixth-level-heading"></a><span data-ttu-id="890fc-169">レベル 6 の見出し</span><span class="sxs-lookup"><span data-stu-id="890fc-169">Sixth-level heading</span></span>

## <a name="text-styling"></a><span data-ttu-id="890fc-170">テキストのスタイル指定</span><span class="sxs-lookup"><span data-stu-id="890fc-170">Text styling</span></span>

<span data-ttu-id="890fc-171">"*斜体*" ファイル、フォルダー、パス (項目が長い場合は、独立した行に分割)、新しい用語に使用します。</span><span class="sxs-lookup"><span data-stu-id="890fc-171">*Italics* Use for files, folders, paths (for long items, split onto their own line), new terms.</span></span>

<span data-ttu-id="890fc-172">**太字** UI 要素に使用します。</span><span class="sxs-lookup"><span data-stu-id="890fc-172">**Bold** Use for UI elements.</span></span>

<span data-ttu-id="890fc-173">`Code` クリックできないようにするインライン コード、言語キーワード、NuGet パッケージ名、コマンドライン コマンド、データベース テーブルと列の名前、URL に使用します。</span><span class="sxs-lookup"><span data-stu-id="890fc-173">`Code` Use for inline code, language keywords, NuGet package names, command-line commands, database table and column names, and URLs that you don't want to be clickable.</span></span>

## <a name="links"></a><span data-ttu-id="890fc-174">リンク</span><span class="sxs-lookup"><span data-stu-id="890fc-174">Links</span></span>

### <a name="internal-links"></a><span data-ttu-id="890fc-175">内部リンク</span><span class="sxs-lookup"><span data-stu-id="890fc-175">Internal Links</span></span>

<span data-ttu-id="890fc-176">同じマークダウン ファイル内のヘッダーにリンクする (アンカー リンクとも呼ばれます) には、リンク先のヘッダーの ID を確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="890fc-176">To link to a header in the same Markdown file (also known as anchor links), you'll need to find out the id of the header you're trying to link to.</span></span> <span data-ttu-id="890fc-177">ID を確認するには、表示された記事のソースを表示して、ヘッダーの ID (例: `id="blockquote"`) を検索し、# に ID をつなげたものを使用してリンクします (例: `#blockquote`)。</span><span class="sxs-lookup"><span data-stu-id="890fc-177">To confirm the ID, view the source of the rendered article, find the id of the header (for example, `id="blockquote"`), and link using # + id (for example, `#blockquote`).</span></span>
<span data-ttu-id="890fc-178">ID はヘッダー テキストに基づいて自動生成されます。</span><span class="sxs-lookup"><span data-stu-id="890fc-178">The id is auto-generated based on the header text.</span></span> <span data-ttu-id="890fc-179">そのため、たとえば、`## Step 2` という名前の一意のセクションの場合、ID は `id="step-2"` のようになります。</span><span class="sxs-lookup"><span data-stu-id="890fc-179">So, for example, given a unique section named `## Step 2`, the id would look like this `id="step-2"`.</span></span>

- <span data-ttu-id="890fc-180">例: `[Declare inline blocks with a language identifier](#inline-code-blocks-with-language-identifier)` では、[言語識別子を使用して宣言インライン ブロック](#inline-code-blocks-with-language-identifier)が生成されます。</span><span class="sxs-lookup"><span data-stu-id="890fc-180">Example: `[Declare inline blocks with a language identifier](#inline-code-blocks-with-language-identifier)` produces [Declare inline blocks with a language identifier](#inline-code-blocks-with-language-identifier).</span></span>

<span data-ttu-id="890fc-181">同じリポジトリ内のマークダウン ファイルにリンクするには、ファイル名の末尾に ".md" を含めた[相対リンク](https://www.w3.org/TR/WD-html40-970917/htmlweb.html#h-5.1.2)を使用します。</span><span class="sxs-lookup"><span data-stu-id="890fc-181">To link to a Markdown file in the same repo, use [relative links](https://www.w3.org/TR/WD-html40-970917/htmlweb.html#h-5.1.2), including the ".md" at the end of the filename.</span></span>

- <span data-ttu-id="890fc-182">例: `[Readme file](../README.md)` では、[Readme ファイル](../README.md)が生成されます</span><span class="sxs-lookup"><span data-stu-id="890fc-182">Example: `[Readme file](../README.md)` produces [Readme file](../README.md).</span></span> <span data-ttu-id="890fc-183">(リンクは、大文字と小文字が区別されます)。</span><span class="sxs-lookup"><span data-stu-id="890fc-183">(Note that links are case-sensitive.)</span></span>
- <span data-ttu-id="890fc-184">例: `[Welcome to .NET](../docs/welcome.md)` では、「[.NET にようこそ](../docs/welcome.md)」が生成されます。</span><span class="sxs-lookup"><span data-stu-id="890fc-184">Example: `[Welcome to .NET](../docs/welcome.md)` produces [Welcome to .NET](../docs/welcome.md).</span></span>

<span data-ttu-id="890fc-185">同じリポジトリ内のマークダウン ファイルのヘッダーにリンクするには、相対リンクとハッシュタグ リンクを使用します。</span><span class="sxs-lookup"><span data-stu-id="890fc-185">To link to a header in a Markdown file in the same repo, use relative linking + hashtag linking.</span></span>

- <span data-ttu-id="890fc-186">例: `[.NET Community](../docs/welcome.md#open-source)` では、[.NET コミュニティ](../docs/welcome.md#open-source)が生成されます。</span><span class="sxs-lookup"><span data-stu-id="890fc-186">Example: `[.NET Community](../docs/welcome.md#open-source)` produces [.NET Community](../docs/welcome.md#open-source).</span></span>

<span data-ttu-id="890fc-187">ほとんどの場合は、相対リンクを使用し、リンクに `~/` を使用しないようにします。これは、相対リンクが GitHub のソース内で解決されるためです。</span><span class="sxs-lookup"><span data-stu-id="890fc-187">In most cases, we use the relative links and discourage the use of `~/` in links because relative links resolve in the source on GitHub.</span></span> <span data-ttu-id="890fc-188">ただし、依存リポジトリ内のファイルにリンクする場合は、`~/` 文字を使用してパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="890fc-188">However, whenever we link to a file in a dependent repo, we'll use the `~/` character to provide the path.</span></span> <span data-ttu-id="890fc-189">依存リポジトリ内のファイルは GitHub の別の場所にあるため、リンクがどのように記述されているかを問わず、相対リンクは正しく解決されません。</span><span class="sxs-lookup"><span data-stu-id="890fc-189">Because the files in the dependent repo are in a different location in GitHub the links won't resolve correctly with relative links regardless of how they were written.</span></span>

<span data-ttu-id="890fc-190">C# 言語仕様と Visual Basic 言語仕様は、言語リポジトリのソースを含めると、.NET ドキュメントに含まれます。</span><span class="sxs-lookup"><span data-stu-id="890fc-190">The C# language specification and the Visual Basic language specification are included in the .NET docs by including the source from the language repositories.</span></span> <span data-ttu-id="890fc-191">マークダウン ソースは、[csharplang](https://github.com/dotnet/csharplang) リポジトリと [visual basic](https://github.com/dotnet/vblang) リポジトリ内で管理されます。</span><span class="sxs-lookup"><span data-stu-id="890fc-191">The markdown sources are managed in the [csharplang](https://github.com/dotnet/csharplang) and [visual basic](https://github.com/dotnet/vblang) repositories.</span></span>

<span data-ttu-id="890fc-192">仕様へのリンクは、これらの仕様が含まれるソース ディレクトリを指す必要があります。</span><span class="sxs-lookup"><span data-stu-id="890fc-192">Links to the spec must point to the source directories where those specs are included.</span></span> <span data-ttu-id="890fc-193">C# の場合は **~/_csharplang/spec**、VB の場合は **~/_vblang/spec** です。</span><span class="sxs-lookup"><span data-stu-id="890fc-193">For C#, it's **~/_csharplang/spec** and for VB, it's **~/_vblang/spec**.</span></span>

- <span data-ttu-id="890fc-194">例: `[C# Query Expressions](~/_csharplang/spec/expressions.md#query-expressions)` では、[C# クエリ式が生成されます](~/_csharplang/spec/expressions.md#query-expressions)。</span><span class="sxs-lookup"><span data-stu-id="890fc-194">Example: `[C# Query Expressions](~/_csharplang/spec/expressions.md#query-expressions)` produces [C# Query Expressions](~/_csharplang/spec/expressions.md#query-expressions).</span></span>

### <a name="external-links"></a><span data-ttu-id="890fc-195">外部リンク</span><span class="sxs-lookup"><span data-stu-id="890fc-195">External Links</span></span>

<span data-ttu-id="890fc-196">外部ファイルにリンクするには、完全な URL をリンクとして使用します。</span><span class="sxs-lookup"><span data-stu-id="890fc-196">To link to an external file, use the full URL as the link.</span></span>

- <span data-ttu-id="890fc-197">例: `[GitHub](https://www.github.com)` では、[GitHub](https://www.github.com) が生成されます。</span><span class="sxs-lookup"><span data-stu-id="890fc-197">Example: `[GitHub](https://www.github.com)` produces [GitHub](https://www.github.com).</span></span>

<span data-ttu-id="890fc-198">URL がマークダウン ファイルに表示されると、クリック可能なリンクに変換されます。</span><span class="sxs-lookup"><span data-stu-id="890fc-198">If a URL appears in a Markdown file, it will be transformed into a clickable link.</span></span>

- <span data-ttu-id="890fc-199">例: `<https://www.github.com>` では、<https://www.github.com> が生成されます。</span><span class="sxs-lookup"><span data-stu-id="890fc-199">Example: `<https://www.github.com>` produces <https://www.github.com>.</span></span>

<span data-ttu-id="890fc-200">外部リンクの場合は、`https` プロトコルを優先します。</span><span class="sxs-lookup"><span data-stu-id="890fc-200">Prefer the `https` protocol for external links.</span></span> <span data-ttu-id="890fc-201">`https` をサポートしていないサイトの場合にのみ `http` リンクを使用します。</span><span class="sxs-lookup"><span data-stu-id="890fc-201">Only use `http` links for sites that do not support `https`.</span></span>

### <a name="links-to-apis"></a><span data-ttu-id="890fc-202">API へのリンク</span><span class="sxs-lookup"><span data-stu-id="890fc-202">Links to APIs</span></span>

<span data-ttu-id="890fc-203">ビルド システムには、外部リンクを使用せずに .NET API にリンクできるようにするいくつかの拡張機能が備えられています。</span><span class="sxs-lookup"><span data-stu-id="890fc-203">The build system has some extensions that allow us to link to .NET APIs without having to use external links.</span></span>
<span data-ttu-id="890fc-204">API にリンクする場合は、ソース コードから自動生成される一意識別子 (UID) を使用できます。</span><span class="sxs-lookup"><span data-stu-id="890fc-204">When linking to an API, you can use its unique identifier (UID) that is auto-generated from the source code.</span></span>

<span data-ttu-id="890fc-205">UID は、完全修飾型とメンバー名に相当します。</span><span class="sxs-lookup"><span data-stu-id="890fc-205">The UID equates to the fully qualified type and member name.</span></span>

<span data-ttu-id="890fc-206">UID の後に \* (または %2A) を追加した場合、リンクは特定の API ではなく、オーバーロード ページを表します。</span><span class="sxs-lookup"><span data-stu-id="890fc-206">If you add a \* (or %2A) after the UID, the link then represents the overload page and not a specific API.</span></span> <span data-ttu-id="890fc-207">たとえば、[List\<T>.BinarySearch(T, IComparer\<T>)](https://docs.microsoft.com/dotnet/api/system.collections.generic.list-1.binarysearch#System_Collections_Generic_List_1_BinarySearch__0_) などの特定のオーバーロードではなく、一般的な方法で [List\<T>.BinarySearch Method](https://docs.microsoft.com/dotnet/api/system.collections.generic.list-1.binarysearch) ページにリンクする場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="890fc-207">For example, you can use that when you want to link to the [List\<T>.BinarySearch Method](https://docs.microsoft.com/dotnet/api/system.collections.generic.list-1.binarysearch) page in a generic way instead of a specific overload such as [List\<T>.BinarySearch(T, IComparer\<T>)](https://docs.microsoft.com/dotnet/api/system.collections.generic.list-1.binarysearch#System_Collections_Generic_List_1_BinarySearch__0_).</span></span> <span data-ttu-id="890fc-208">また、メンバーがオーバーロードされていない場合は、\* を使ってメンバー ページにリンクすることもできます。これにより、UID にパラメーター リストを含める必要がなくなります。</span><span class="sxs-lookup"><span data-stu-id="890fc-208">You can also use \* to link to a member page when the member is not overloaded; this saves you from having to include the parameter list in the UID.</span></span>

<span data-ttu-id="890fc-209">特定のメソッドのオーバーロードにリンクするには、メソッドの各パラメーターの完全修飾型名を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="890fc-209">To link to a specific method overload, you must include the fully qualified type name of each of the method's parameters.</span></span> <span data-ttu-id="890fc-210">たとえば、\<xref:System.DateTime.ToString> はパラメーターなしの [DateTime.ToString](https://docs.microsoft.com/dotnet/api/system.datetime.tostring#System_DateTime_ToString) メソッドにリンクされますが、\<xref:System.DateTime.ToString(System.String,System.IFormatProvider)> は [DateTime.ToString(String,IFormatProvider)](https://docs.microsoft.com/dotnet/api/system.datetime.tostring#System_DateTime_ToString_System_String_System_IFormatProvider_) メソッドにリンクされます。</span><span class="sxs-lookup"><span data-stu-id="890fc-210">For example, \<xref:System.DateTime.ToString> links to the parameterless [DateTime.ToString](https://docs.microsoft.com/dotnet/api/system.datetime.tostring#System_DateTime_ToString) method, while \<xref:System.DateTime.ToString(System.String,System.IFormatProvider)> links to the  [DateTime.ToString(String,IFormatProvider)](https://docs.microsoft.com/dotnet/api/system.datetime.tostring#System_DateTime_ToString_System_String_System_IFormatProvider_) method.</span></span> <span data-ttu-id="890fc-211">オーバーロードされた特定のメンバーの UID を `https://xref.docs.microsoft.com/autocomplete` から見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="890fc-211">You can find the UIDs of a particular overloaded member from `https://xref.docs.microsoft.com/autocomplete`.</span></span> <span data-ttu-id="890fc-212">クエリ文字列 "?text= *\<type-member-name>* " では、UID を確認したい型またはメンバーを特定します。</span><span class="sxs-lookup"><span data-stu-id="890fc-212">The query string "?text=*\<type-member-name>*" identifies the type or member whose UIDs you'd like to see.</span></span> <span data-ttu-id="890fc-213">たとえば、`https://xref.docs.microsoft.com/autocomplete?text=string.format` では、[String.Format](https://docs.microsoft.com/dotnet/api/system.string.format) オーバーロードが取得されます。</span><span class="sxs-lookup"><span data-stu-id="890fc-213">For example, `https://xref.docs.microsoft.com/autocomplete?text=string.format` retrieves the [String.Format](https://docs.microsoft.com/dotnet/api/system.string.format) overloads.</span></span>

<span data-ttu-id="890fc-214">[System.Collections.Generic.List\<T>](https://docs.microsoft.com/dotnet/api/system.collections.generic.list-1) などのジェネリック型にリンクするには、\` (%60) 文字に続けてジェネリック型パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="890fc-214">To link to a generic type, such as [System.Collections.Generic.List\<T>](https://docs.microsoft.com/dotnet/api/system.collections.generic.list-1), you use the \` (%60) character followed by the number of generic type parameters.</span></span> <span data-ttu-id="890fc-215">たとえば、\<xref:System.Nullable%601> は [System.Nullable\<T>](https://docs.microsoft.com/dotnet/api/system.nullable-1) 型にリンクされますが、\<xref:System.Func%602> は [System.Func\<T,TResult>](https://docs.microsoft.com/dotnet/api/system.func-2) デリゲートにリンクされます。</span><span class="sxs-lookup"><span data-stu-id="890fc-215">For example, \<xref:System.Nullable%601> links to the [System.Nullable\<T>](https://docs.microsoft.com/dotnet/api/system.nullable-1) type, while \<xref:System.Func%602> links to the [System.Func\<T,TResult>](https://docs.microsoft.com/dotnet/api/system.func-2) delegate.</span></span>

<span data-ttu-id="890fc-216">次のいずれかの構文を使用できます。</span><span class="sxs-lookup"><span data-stu-id="890fc-216">You can use one of the following syntax:</span></span>

1. <span data-ttu-id="890fc-217">自動リンク: `<xref:UID>` または `<xref:UID?displayProperty=nameWithType>`</span><span class="sxs-lookup"><span data-stu-id="890fc-217">Auto-link: `<xref:UID>` or `<xref:UID?displayProperty=nameWithType>`</span></span>

   <span data-ttu-id="890fc-218">`displayProperty` クエリ パラメーターでは、完全修飾リンク テキストが生成されます。</span><span class="sxs-lookup"><span data-stu-id="890fc-218">The `displayProperty` query    parameter produces a fully qualified link text.</span></span> <span data-ttu-id="890fc-219">既定では、リンクテキストには、メンバーまたは型の名前のみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="890fc-219">By default, link text shows only the member or type name.</span></span>

2. <span data-ttu-id="890fc-220">マークダウン リンク: `[link text](xref:UID)`</span><span class="sxs-lookup"><span data-stu-id="890fc-220">Markdown link: `[link text](xref:UID)`</span></span>

   <span data-ttu-id="890fc-221">表示されるリンク テキストをカスタマイズする場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="890fc-221">Use when you want to customize the link text displayed.</span></span>

<span data-ttu-id="890fc-222">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="890fc-222">Examples:</span></span>

- <span data-ttu-id="890fc-223">`<xref:System.String>` は [String](https://docs.microsoft.com/dotnet/api/system.string) としてレンダリングされます</span><span class="sxs-lookup"><span data-stu-id="890fc-223">`<xref:System.String>` renders as [String](https://docs.microsoft.com/dotnet/api/system.string)</span></span>
- <span data-ttu-id="890fc-224">`<xref:System.String?displayProperty=nameWithType>` は [System.String](https://docs.microsoft.com/dotnet/api/system.string) としてレンダリングされます</span><span class="sxs-lookup"><span data-stu-id="890fc-224">`<xref:System.String?displayProperty=nameWithType>` renders as [System.String](https://docs.microsoft.com/dotnet/api/system.string)</span></span>
- <span data-ttu-id="890fc-225">`[String class](xref:System.String)` は [String class](https://docs.microsoft.com/dotnet/api/system.string) としてレンダリングされます</span><span class="sxs-lookup"><span data-stu-id="890fc-225">`[String class](xref:System.String)` renders as [String class](https://docs.microsoft.com/dotnet/api/system.string)</span></span>

<span data-ttu-id="890fc-226">この表記の使用に関する詳細は、「[Using cross reference (相互参照の使用)](https://dotnet.github.io/docfx/tutorial/links_and_cross_references.html#using-cross-reference)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="890fc-226">For more information about using this notation, see [Using cross reference](https://dotnet.github.io/docfx/tutorial/links_and_cross_references.html#using-cross-reference).</span></span>

<span data-ttu-id="890fc-227">UID を検索するには、2 つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="890fc-227">There are two ways to find the UID:</span></span>

- <span data-ttu-id="890fc-228">リンク先の API ページのソースを表示して、ms.assetid 値を検索します。</span><span class="sxs-lookup"><span data-stu-id="890fc-228">View the source for the API page you want to link to and find the ms.assetid value.</span></span> <span data-ttu-id="890fc-229">個別のオーバーロード値は、ソースには示されていないため注意してください。</span><span class="sxs-lookup"><span data-stu-id="890fc-229">Note that individual overload values are not shown in the source.</span></span>
- <span data-ttu-id="890fc-230">UID の検索には、次のツールを使用します: https://xref.docs.microsoft.com/autocomplete?text=tostring (tostring は、検索しようとしている API 名の一部に置き換えます)。</span><span class="sxs-lookup"><span data-stu-id="890fc-230">Use the following tool to search for UIDs: https://xref.docs.microsoft.com/autocomplete?text=tostring (replace tostring with parts of the API name you're trying to find).</span></span> <span data-ttu-id="890fc-231">ツールにより、UID の任意の部分で、指定した `text` クエリ パラメーターが検索されます。</span><span class="sxs-lookup"><span data-stu-id="890fc-231">The tool searches for the provided `text` query parameter in any part of the UID.</span></span> <span data-ttu-id="890fc-232">たとえば、メンバー名 (ToString)、メンバー名 (ToStri) の一部、型とメンバー名 (Double.ToString) などを検索できます。</span><span class="sxs-lookup"><span data-stu-id="890fc-232">For example, you can search for member name (ToString), partial member name (ToStri), type and member name (Double.ToString), etc.</span></span>

<span data-ttu-id="890fc-233">UID に特殊文字 \`、\# または \* が含まれる場合、UID 値はそれぞれ `%60`、`%23`、`%2A` として HTML をエンコードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="890fc-233">When the UID contains the special characters \`, \# or \*, the UID value needs to be HTML encoded as `%60`, `%23` and `%2A` respectively.</span></span> <span data-ttu-id="890fc-234">かっこがエンコードされていることもありますが、これは必須ではありません。</span><span class="sxs-lookup"><span data-stu-id="890fc-234">You'll sometimes see parentheses encoded but it's not a requirement.</span></span>

<span data-ttu-id="890fc-235">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="890fc-235">Examples:</span></span>

- <span data-ttu-id="890fc-236">System.Threading.Tasks.Task\`1 は `System.Threading.Tasks.Task%601` になります</span><span class="sxs-lookup"><span data-stu-id="890fc-236">System.Threading.Tasks.Task\`1 becomes `System.Threading.Tasks.Task%601`</span></span>
- <span data-ttu-id="890fc-237">System.Exception.\#ctor は `System.Exception.%23ctor` になります</span><span class="sxs-lookup"><span data-stu-id="890fc-237">System.Exception.\#ctor becomes `System.Exception.%23ctor`</span></span>
- <span data-ttu-id="890fc-238">System.Lazy\`1.\#ctor(System.Threading.LazyThreadSafetyMode) は `System.Lazy%601.%23ctor%28System.Threading.LazyThreadSafetyMode%29` になります</span><span class="sxs-lookup"><span data-stu-id="890fc-238">System.Lazy\`1.\#ctor(System.Threading.LazyThreadSafetyMode) becomes  `System.Lazy%601.%23ctor%28System.Threading.LazyThreadSafetyMode%29`</span></span>

## <a name="lists"></a><span data-ttu-id="890fc-239">表示内容</span><span class="sxs-lookup"><span data-stu-id="890fc-239">Lists</span></span>

### <a name="ordered-lists"></a><span data-ttu-id="890fc-240">番号付きリスト</span><span class="sxs-lookup"><span data-stu-id="890fc-240">Ordered lists</span></span>

1. <span data-ttu-id="890fc-241">This</span><span class="sxs-lookup"><span data-stu-id="890fc-241">This</span></span>
1. <span data-ttu-id="890fc-242">Is</span><span class="sxs-lookup"><span data-stu-id="890fc-242">Is</span></span>
1. <span data-ttu-id="890fc-243">An</span><span class="sxs-lookup"><span data-stu-id="890fc-243">An</span></span>
1. <span data-ttu-id="890fc-244">順序あり</span><span class="sxs-lookup"><span data-stu-id="890fc-244">Ordered</span></span>
1. <span data-ttu-id="890fc-245">リスト</span><span class="sxs-lookup"><span data-stu-id="890fc-245">List</span></span>

#### <a name="ordered-list-with-an-embedded-list"></a><span data-ttu-id="890fc-246">埋め込みリストを含む番号付きリスト</span><span class="sxs-lookup"><span data-stu-id="890fc-246">Ordered list with an embedded list</span></span>

1. <span data-ttu-id="890fc-247">Here</span><span class="sxs-lookup"><span data-stu-id="890fc-247">Here</span></span>
1. <span data-ttu-id="890fc-248">comes</span><span class="sxs-lookup"><span data-stu-id="890fc-248">comes</span></span>
1. <span data-ttu-id="890fc-249">1 つ</span><span class="sxs-lookup"><span data-stu-id="890fc-249">an</span></span>
1. <span data-ttu-id="890fc-250">embedded</span><span class="sxs-lookup"><span data-stu-id="890fc-250">embedded</span></span>
    1. <span data-ttu-id="890fc-251">Miss Scarlett</span><span class="sxs-lookup"><span data-stu-id="890fc-251">Miss Scarlett</span></span>
    1. <span data-ttu-id="890fc-252">Professor Plum</span><span class="sxs-lookup"><span data-stu-id="890fc-252">Professor Plum</span></span>
1. <span data-ttu-id="890fc-253">ordered</span><span class="sxs-lookup"><span data-stu-id="890fc-253">ordered</span></span>
1. <span data-ttu-id="890fc-254">リスト</span><span class="sxs-lookup"><span data-stu-id="890fc-254">list</span></span>

### <a name="unordered-lists"></a><span data-ttu-id="890fc-255">記号付きリスト</span><span class="sxs-lookup"><span data-stu-id="890fc-255">Unordered Lists</span></span>

- <span data-ttu-id="890fc-256">This</span><span class="sxs-lookup"><span data-stu-id="890fc-256">This</span></span>
- <span data-ttu-id="890fc-257">is</span><span class="sxs-lookup"><span data-stu-id="890fc-257">is</span></span>
- <span data-ttu-id="890fc-258">a</span><span class="sxs-lookup"><span data-stu-id="890fc-258">a</span></span>
- <span data-ttu-id="890fc-259">bulleted</span><span class="sxs-lookup"><span data-stu-id="890fc-259">bulleted</span></span>
- <span data-ttu-id="890fc-260">リスト</span><span class="sxs-lookup"><span data-stu-id="890fc-260">list</span></span>

#### <a name="unordered-list-with-an-embedded-list"></a><span data-ttu-id="890fc-261">埋め込みリストを含む記号付きリスト</span><span class="sxs-lookup"><span data-stu-id="890fc-261">Unordered list with an embedded list</span></span>

- <span data-ttu-id="890fc-262">This</span><span class="sxs-lookup"><span data-stu-id="890fc-262">This</span></span>
- <span data-ttu-id="890fc-263">bulleted</span><span class="sxs-lookup"><span data-stu-id="890fc-263">bulleted</span></span>
- <span data-ttu-id="890fc-264">リスト</span><span class="sxs-lookup"><span data-stu-id="890fc-264">list</span></span>
  - <span data-ttu-id="890fc-265">Mrs. Peacock</span><span class="sxs-lookup"><span data-stu-id="890fc-265">Mrs. Peacock</span></span>
  - <span data-ttu-id="890fc-266">Mr. Green</span><span class="sxs-lookup"><span data-stu-id="890fc-266">Mr. Green</span></span>
- <span data-ttu-id="890fc-267">次の値を含む</span><span class="sxs-lookup"><span data-stu-id="890fc-267">contains</span></span>
- <span data-ttu-id="890fc-268">その他</span><span class="sxs-lookup"><span data-stu-id="890fc-268">other</span></span>
  1. <span data-ttu-id="890fc-269">Colonel Mustard</span><span class="sxs-lookup"><span data-stu-id="890fc-269">Colonel Mustard</span></span>
  1. <span data-ttu-id="890fc-270">Mrs. White</span><span class="sxs-lookup"><span data-stu-id="890fc-270">Mrs. White</span></span>
- <span data-ttu-id="890fc-271">一覧</span><span class="sxs-lookup"><span data-stu-id="890fc-271">lists</span></span>

## <a name="horizontal-rule"></a><span data-ttu-id="890fc-272">水平線</span><span class="sxs-lookup"><span data-stu-id="890fc-272">Horizontal rule</span></span>

---

## <a name="tables"></a><span data-ttu-id="890fc-273">[テーブル]</span><span class="sxs-lookup"><span data-stu-id="890fc-273">Tables</span></span>

| <span data-ttu-id="890fc-274">[テーブル]</span><span class="sxs-lookup"><span data-stu-id="890fc-274">Tables</span></span>        | <span data-ttu-id="890fc-275">Are</span><span class="sxs-lookup"><span data-stu-id="890fc-275">Are</span></span>           | <span data-ttu-id="890fc-276">Cool</span><span class="sxs-lookup"><span data-stu-id="890fc-276">Cool</span></span>  |
| ------------- |:-------------:| -----:|
| <span data-ttu-id="890fc-277">列 3 は</span><span class="sxs-lookup"><span data-stu-id="890fc-277">col 3 is</span></span>      | <span data-ttu-id="890fc-278">右揃え</span><span class="sxs-lookup"><span data-stu-id="890fc-278">right-aligned</span></span> | <span data-ttu-id="890fc-279">$1600</span><span class="sxs-lookup"><span data-stu-id="890fc-279">$1600</span></span> |
| <span data-ttu-id="890fc-280">列 2 は</span><span class="sxs-lookup"><span data-stu-id="890fc-280">col 2 is</span></span>      | <span data-ttu-id="890fc-281">中央揃え</span><span class="sxs-lookup"><span data-stu-id="890fc-281">centered</span></span>      |   <span data-ttu-id="890fc-282">$12</span><span class="sxs-lookup"><span data-stu-id="890fc-282">$12</span></span> |
| <span data-ttu-id="890fc-283">列 1 は既定の</span><span class="sxs-lookup"><span data-stu-id="890fc-283">col 1 is default</span></span> | <span data-ttu-id="890fc-284">左揃え</span><span class="sxs-lookup"><span data-stu-id="890fc-284">left-aligned</span></span>     |    <span data-ttu-id="890fc-285">$1</span><span class="sxs-lookup"><span data-stu-id="890fc-285">$1</span></span> |

<span data-ttu-id="890fc-286">[Markdown Table Generator ツール](https://www.tablesgenerator.com/markdown_tables)を使用して、より簡単にテーブルを作成できます。</span><span class="sxs-lookup"><span data-stu-id="890fc-286">You can use a [Markdown table generator tool](https://www.tablesgenerator.com/markdown_tables) to help creating them more easily.</span></span>

## <a name="code"></a><span data-ttu-id="890fc-287">コード</span><span class="sxs-lookup"><span data-stu-id="890fc-287">Code</span></span>

<span data-ttu-id="890fc-288">コードを含める最善の方法は、実際に動作するサンプルからのスニペットを含める方法です。</span><span class="sxs-lookup"><span data-stu-id="890fc-288">The best way to include code is to include snippets from a working sample.</span></span> <span data-ttu-id="890fc-289">[貢献に関するガイド](../CONTRIBUTING.md#contributing-to-samples)の指示に従って、サンプルを作成します。</span><span class="sxs-lookup"><span data-stu-id="890fc-289">Create your sample following the instructions in the [contributing guide](../CONTRIBUTING.md#contributing-to-samples).</span></span>

<span data-ttu-id="890fc-290">次の構文を使用して、コードを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="890fc-290">You can include the code using the following syntax:</span></span>

```markdown
[!code-<language>[<name>](<pathToFile><queryoption><queryoptionvalue>)]
```

- <span data-ttu-id="890fc-291">`-<language>` ("*省略可能*" ですが、使用が "*推奨*" されます)</span><span class="sxs-lookup"><span data-stu-id="890fc-291">`-<language>` (*optional* but *recommended*)</span></span>
  - <span data-ttu-id="890fc-292">参照されるコード スニペットの言語。</span><span class="sxs-lookup"><span data-stu-id="890fc-292">Language of the code snippet being referenced.</span></span> <span data-ttu-id="890fc-293">サポートされる値のリストについては、「[サポートされる言語](#supported-languages)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="890fc-293">For a list of supported values, see [Supported languages](#supported-languages).</span></span>

- <span data-ttu-id="890fc-294">`<name>` ("*省略可能*")</span><span class="sxs-lookup"><span data-stu-id="890fc-294">`<name>` (*optional*)</span></span>
  - <span data-ttu-id="890fc-295">コード スニペットの名前。</span><span class="sxs-lookup"><span data-stu-id="890fc-295">Name for the code snippet.</span></span> <span data-ttu-id="890fc-296">出力 HTML には影響を与えませんが、使用すると、マークダウン ソースの読みやすさを向上できます。</span><span class="sxs-lookup"><span data-stu-id="890fc-296">It doesn’t have any impact on the output HTML, but you can use it to improve the readability of your Markdown source.</span></span>

- <span data-ttu-id="890fc-297">`<pathToFile>` ("*必須*")</span><span class="sxs-lookup"><span data-stu-id="890fc-297">`<pathToFile>` (*mandatory*)</span></span>
  - <span data-ttu-id="890fc-298">参照するコード スニペット ファイルを示す、ファイルシステム内の相対パス。</span><span class="sxs-lookup"><span data-stu-id="890fc-298">Relative path in the file system that indicates the code snippet file to reference.</span></span>

- <span data-ttu-id="890fc-299">`<queryoption>` および `<queryoptionvalue>` ("*省略可能*")</span><span class="sxs-lookup"><span data-stu-id="890fc-299">`<queryoption>` and `<queryoptionvalue>` (*optional*)</span></span>
  - <span data-ttu-id="890fc-300">ファイルからコードを取得する方法を指定するために一緒に使用します。</span><span class="sxs-lookup"><span data-stu-id="890fc-300">Used together to specify how the code should be retrieved from the file:</span></span>
    - <span data-ttu-id="890fc-301">`#`: `#L{startlinenumber}-L{endlinenumber}` (行の範囲) "*または*" `#{tagname}` (タグ名)。</span><span class="sxs-lookup"><span data-stu-id="890fc-301">`#`:  `#L{startlinenumber}-L{endlinenumber}` (line range) *or* `#{tagname}` (tag name).</span></span>
    <span data-ttu-id="890fc-302">行番号は変動するため、使用はお勧めしません。</span><span class="sxs-lookup"><span data-stu-id="890fc-302">We discourage the use of line numbers because they are very brittle.</span></span> <span data-ttu-id="890fc-303">コード スニペットの参照方法としては、タグ名が推奨されます。</span><span class="sxs-lookup"><span data-stu-id="890fc-303">Tag name is the preferred way of referencing code snippets.</span></span>
    - <span data-ttu-id="890fc-304">`range`:`?range=1,3-5` 行の範囲。</span><span class="sxs-lookup"><span data-stu-id="890fc-304">`range`: `?range=1,3-5` A range of lines.</span></span> <span data-ttu-id="890fc-305">この例では、行 1、3、4、5 が含まれます。</span><span class="sxs-lookup"><span data-stu-id="890fc-305">This example includes lines 1, 3, 4, and 5.</span></span>
    - <span data-ttu-id="890fc-306">`dedent`:`?dedent=8` スペースの数だけ、行のインデントを解除します。この例では 8 です。</span><span class="sxs-lookup"><span data-stu-id="890fc-306">`dedent`: `?dedent=8` Dedents the lines by a number of spaces--in this case, 8.</span></span> <span data-ttu-id="890fc-307">これは、ファイルの行のサブセットを選択する、`range` やその他のクエリ オプションと組み合わせることができます。</span><span class="sxs-lookup"><span data-stu-id="890fc-307">This can be combined with the `range` and other query options that select a subset of the lines of a file.</span></span>
    - <span data-ttu-id="890fc-308">`outdent`:`?outdent=8` スペースの数だけ、行のインデントを戻します。この例では 8 です。</span><span class="sxs-lookup"><span data-stu-id="890fc-308">`outdent`: `?outdent=8` Reverses the indent of the lines by a number of spaces--in this case, 8.</span></span> <span data-ttu-id="890fc-309">これは、ファイルの行のサブセットを選択する、`range` やその他のクエリ オプションと組み合わせることができます。</span><span class="sxs-lookup"><span data-stu-id="890fc-309">This can be combined with `range` and other query options that select a subset of the lines of a file.</span></span>

<span data-ttu-id="890fc-310">可能な限り、タグ名オプションを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="890fc-310">We recommend using the tag name option whenever possible.</span></span> <span data-ttu-id="890fc-311">タグ名は、領域の名前、またはソース コードに存在する `Snippettagname` 形式のコード コメントの名前です。</span><span class="sxs-lookup"><span data-stu-id="890fc-311">The tag name is the name of a region or of a code comment in the format of `Snippettagname` present in the source code.</span></span> <span data-ttu-id="890fc-312">次の例は、タグ名 `1` を参照する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="890fc-312">The following example shows how to refer to the tag name `1`:</span></span>

```markdown
[!code-csharp[csrefKeyword#1](../../../../samples/snippets/csharp/language-reference/keywords/throw/throw-1.cs#1)]
```

<span data-ttu-id="890fc-313">また、スニペット タグが[ここのソース ファイル](https://github.com/dotnet/samples/blob/master/snippets/csharp/language-reference/keywords/throw/throw-1.cs)でどのように構成されているかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="890fc-313">And you can see how the snippet tags are structured in [this source file](https://github.com/dotnet/samples/blob/master/snippets/csharp/language-reference/keywords/throw/throw-1.cs).</span></span> <span data-ttu-id="890fc-314">コード スニペット ソース ファイルでの言語別のタグ名の表記の詳細については、[DocFX ガイドライン](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html#tag-name-representation-in-code-snippet-source-file)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="890fc-314">For details about tag name representation in code snippet source files by language, see the [DocFX guidelines](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html#tag-name-representation-in-code-snippet-source-file).</span></span>

<span data-ttu-id="890fc-315">完全なプログラムからのスニペットを含めることで、すべてのコードが確実に継続的インテグレーション (CI) システムで処理されたものになります。</span><span class="sxs-lookup"><span data-stu-id="890fc-315">Including snippets from full programs ensures that all code runs through our Continuous Integration (CI) system.</span></span> <span data-ttu-id="890fc-316">ただし、コンパイル時のエラーやランタイム エラーの原因を表示する必要がある場合は、インライン コード ブロックを使用できます。</span><span class="sxs-lookup"><span data-stu-id="890fc-316">However, if you need to show something that causes compile time or runtime errors, you can use inline code blocks.</span></span>

### <a name="inline-code-blocks-with-language-identifier"></a><span data-ttu-id="890fc-317">言語識別子を持つインライン コード ブロック</span><span class="sxs-lookup"><span data-stu-id="890fc-317">Inline code blocks with language identifier</span></span>

<span data-ttu-id="890fc-318">3 つのバッククォート (\`\`\`) と言語 ID を使用して、言語固有のカラー コーディングをコード ブロックに適用します。</span><span class="sxs-lookup"><span data-stu-id="890fc-318">Use three backticks (\`\`\`) + a language ID to apply language-specific color coding to a code block.</span></span> <span data-ttu-id="890fc-319">次のサポートされる言語のリストは、各言語 ID に対するマークダウン ラベルを示しています。</span><span class="sxs-lookup"><span data-stu-id="890fc-319">Here is the list of supported languages showing the markdown label for each language ID.</span></span>

#### <a name="supported-languages"></a><span data-ttu-id="890fc-320">サポートされる言語</span><span class="sxs-lookup"><span data-stu-id="890fc-320">Supported languages</span></span>

|<span data-ttu-id="890fc-321">name</span><span class="sxs-lookup"><span data-stu-id="890fc-321">Name</span></span>|<span data-ttu-id="890fc-322">マークダウン ラベル</span><span class="sxs-lookup"><span data-stu-id="890fc-322">Markdown label</span></span>|
|-----|-------|
|<span data-ttu-id="890fc-323">ASP.NET (C#)</span><span class="sxs-lookup"><span data-stu-id="890fc-323">ASP.NET with C#</span></span>|<span data-ttu-id="890fc-324">aspx-csharp</span><span class="sxs-lookup"><span data-stu-id="890fc-324">aspx-csharp</span></span>|
|<span data-ttu-id="890fc-325">ASP.NET (VB)</span><span class="sxs-lookup"><span data-stu-id="890fc-325">ASP.NET with VB</span></span>|<span data-ttu-id="890fc-326">aspx-vb</span><span class="sxs-lookup"><span data-stu-id="890fc-326">aspx-vb</span></span>|
|<span data-ttu-id="890fc-327">Azure CLI</span><span class="sxs-lookup"><span data-stu-id="890fc-327">Azure CLI</span></span>|<span data-ttu-id="890fc-328">azurecli</span><span class="sxs-lookup"><span data-stu-id="890fc-328">azurecli</span></span>|
|<span data-ttu-id="890fc-329">AzCopy</span><span class="sxs-lookup"><span data-stu-id="890fc-329">AzCopy</span></span>|<span data-ttu-id="890fc-330">azcopy</span><span class="sxs-lookup"><span data-stu-id="890fc-330">azcopy</span></span>|
|<span data-ttu-id="890fc-331">C++</span><span class="sxs-lookup"><span data-stu-id="890fc-331">C++</span></span>|<span data-ttu-id="890fc-332">cpp</span><span class="sxs-lookup"><span data-stu-id="890fc-332">cpp</span></span>|
|<span data-ttu-id="890fc-333">C#</span><span class="sxs-lookup"><span data-stu-id="890fc-333">C#</span></span>|<span data-ttu-id="890fc-334">csharp</span><span class="sxs-lookup"><span data-stu-id="890fc-334">csharp</span></span>|
|<span data-ttu-id="890fc-335">C# (ブラウザー内)</span><span class="sxs-lookup"><span data-stu-id="890fc-335">C# in browser</span></span>|<span data-ttu-id="890fc-336">csharp-interactive</span><span class="sxs-lookup"><span data-stu-id="890fc-336">csharp-interactive</span></span>|
|<span data-ttu-id="890fc-337">コンソール</span><span class="sxs-lookup"><span data-stu-id="890fc-337">Console</span></span>|<span data-ttu-id="890fc-338">コンソール</span><span class="sxs-lookup"><span data-stu-id="890fc-338">console</span></span>|
|<span data-ttu-id="890fc-339">F#</span><span class="sxs-lookup"><span data-stu-id="890fc-339">F#</span></span>|<span data-ttu-id="890fc-340">fsharp</span><span class="sxs-lookup"><span data-stu-id="890fc-340">fsharp</span></span>|
|<span data-ttu-id="890fc-341">Java</span><span class="sxs-lookup"><span data-stu-id="890fc-341">Java</span></span>|<span data-ttu-id="890fc-342">java</span><span class="sxs-lookup"><span data-stu-id="890fc-342">java</span></span>|
|<span data-ttu-id="890fc-343">JavaScript</span><span class="sxs-lookup"><span data-stu-id="890fc-343">JavaScript</span></span>|<span data-ttu-id="890fc-344">javascript</span><span class="sxs-lookup"><span data-stu-id="890fc-344">javascript</span></span>|
|<span data-ttu-id="890fc-345">JSON</span><span class="sxs-lookup"><span data-stu-id="890fc-345">JSON</span></span>|<span data-ttu-id="890fc-346">json</span><span class="sxs-lookup"><span data-stu-id="890fc-346">json</span></span>|
|<span data-ttu-id="890fc-347">NodeJS</span><span class="sxs-lookup"><span data-stu-id="890fc-347">NodeJS</span></span>|<span data-ttu-id="890fc-348">nodejs</span><span class="sxs-lookup"><span data-stu-id="890fc-348">nodejs</span></span>|
|<span data-ttu-id="890fc-349">Objective-C</span><span class="sxs-lookup"><span data-stu-id="890fc-349">Objective-C</span></span>|<span data-ttu-id="890fc-350">objc</span><span class="sxs-lookup"><span data-stu-id="890fc-350">objc</span></span>|
|<span data-ttu-id="890fc-351">PHP</span><span class="sxs-lookup"><span data-stu-id="890fc-351">PHP</span></span>|<span data-ttu-id="890fc-352">php</span><span class="sxs-lookup"><span data-stu-id="890fc-352">php</span></span>|
|<span data-ttu-id="890fc-353">PowerShell</span><span class="sxs-lookup"><span data-stu-id="890fc-353">PowerShell</span></span>|<span data-ttu-id="890fc-354">powershell</span><span class="sxs-lookup"><span data-stu-id="890fc-354">powershell</span></span>|
|<span data-ttu-id="890fc-355">Python</span><span class="sxs-lookup"><span data-stu-id="890fc-355">Python</span></span>|<span data-ttu-id="890fc-356">Python</span><span class="sxs-lookup"><span data-stu-id="890fc-356">python</span></span>|
|<span data-ttu-id="890fc-357">Ruby</span><span class="sxs-lookup"><span data-stu-id="890fc-357">Ruby</span></span>|<span data-ttu-id="890fc-358">ruby</span><span class="sxs-lookup"><span data-stu-id="890fc-358">ruby</span></span>|
|<span data-ttu-id="890fc-359">SQL</span><span class="sxs-lookup"><span data-stu-id="890fc-359">SQL</span></span>|<span data-ttu-id="890fc-360">sql</span><span class="sxs-lookup"><span data-stu-id="890fc-360">sql</span></span>|
|<span data-ttu-id="890fc-361">Swift</span><span class="sxs-lookup"><span data-stu-id="890fc-361">Swift</span></span>|<span data-ttu-id="890fc-362">swift</span><span class="sxs-lookup"><span data-stu-id="890fc-362">swift</span></span>|
|<span data-ttu-id="890fc-363">VB</span><span class="sxs-lookup"><span data-stu-id="890fc-363">VB</span></span>|<span data-ttu-id="890fc-364">VB</span><span class="sxs-lookup"><span data-stu-id="890fc-364">vb</span></span>|
|<span data-ttu-id="890fc-365">XAML</span><span class="sxs-lookup"><span data-stu-id="890fc-365">XAML</span></span>|<span data-ttu-id="890fc-366">xaml</span><span class="sxs-lookup"><span data-stu-id="890fc-366">xaml</span></span>|
|<span data-ttu-id="890fc-367">XML</span><span class="sxs-lookup"><span data-stu-id="890fc-367">XML</span></span>|<span data-ttu-id="890fc-368">xml</span><span class="sxs-lookup"><span data-stu-id="890fc-368">xml</span></span>|

<span data-ttu-id="890fc-369">`csharp-interactive` 名で、C# 言語と、ブラウザーからサンプルを実行する機能を指定します。</span><span class="sxs-lookup"><span data-stu-id="890fc-369">The `csharp-interactive` name specifies the C# language, and the ability to run the samples from the browser.</span></span> <span data-ttu-id="890fc-370">このようなスニペットは Docker コンテナーでコンパイル、実行され、そのプログラム実行の結果がユーザーのブラウザー ウィンドウに表示されます。</span><span class="sxs-lookup"><span data-stu-id="890fc-370">These snippets are compiled and executed in a Docker container, and the results of that program execution are displayed in the user's browser window.</span></span>

<span data-ttu-id="890fc-371">C# (\`\`\`csharp)、Python (\`\`\`python)、PowerShell (\`\`\`powershell) の言語 ID を使用したコード ブロックの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="890fc-371">The following are examples of code blocks using the language IDs for C# (\`\`\`csharp), Python (\`\`\`python), and PowerShell (\`\`\`powershell).</span></span>

##### <a name="c9839"></a><span data-ttu-id="890fc-372">C&#9839;</span><span class="sxs-lookup"><span data-stu-id="890fc-372">C&#9839;</span></span>

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

#### <a name="python"></a><span data-ttu-id="890fc-373">Python</span><span class="sxs-lookup"><span data-stu-id="890fc-373">Python</span></span>

```python
friends = ['john', 'pat', 'gary', 'michael']
for i, name in enumerate(friends):
    print "iteration {iteration} is {name}".format(iteration=i, name=name)
```

#### <a name="powershell"></a><span data-ttu-id="890fc-374">PowerShell</span><span class="sxs-lookup"><span data-stu-id="890fc-374">PowerShell</span></span>

```powershell
Clear-Host
$Directory = "C:\Windows\"
$Files = Get-Childitem $Directory -recurse -Include *.log `
-ErrorAction SilentlyContinue
```

### <a name="generic-code-block"></a><span data-ttu-id="890fc-375">汎用のコード ブロック</span><span class="sxs-lookup"><span data-stu-id="890fc-375">Generic code block</span></span>

<span data-ttu-id="890fc-376">汎用のコード ブロック コーディングには、3 つのバッククォート (&#96;&#96;&#96;) を使用します。</span><span class="sxs-lookup"><span data-stu-id="890fc-376">Use three backticks (&#96;&#96;&#96;) for generic code block coding.</span></span>

> <span data-ttu-id="890fc-377">お勧めする方法は、前のセクションで説明したようにコード ブロックを言語識別子と併用して、ドキュメント サイトで構文が正しく強調表示されるようにすることです。</span><span class="sxs-lookup"><span data-stu-id="890fc-377">The recommended approach is to use code blocks with language identifiers as explained in the previous section to ensure the proper syntax highlighting in the documentation site.</span></span> <span data-ttu-id="890fc-378">汎用のコード ブロックは、必要な場合にのみ使用します。</span><span class="sxs-lookup"><span data-stu-id="890fc-378">Use generic code blocks only when necessary.</span></span>

```
function fancyAlert(arg) {
    if(arg) {
        $.docs({div:'#foo'})
    }
}
```

## <a name="blockquotes"></a><span data-ttu-id="890fc-379">ブロック引用</span><span class="sxs-lookup"><span data-stu-id="890fc-379">Blockquotes</span></span>

> <span data-ttu-id="890fc-380">1000 万年続いた干ばつにより、とうに恐竜の天下は終わっていた。</span><span class="sxs-lookup"><span data-stu-id="890fc-380">The drought had lasted now for ten million years, and the reign of the terrible lizards had long since ended.</span></span> <span data-ttu-id="890fc-381">いつかアフリカと呼ばれるであろう大陸の、ここ赤道上では、生存を賭けた戦いは激しさを増した新たなクライマックスを迎え、勝利者が誰になるのかまだ分からなかった。</span><span class="sxs-lookup"><span data-stu-id="890fc-381">Here on the Equator, in the continent which would one day be known as Africa, the battle for existence had reached a new climax of ferocity, and the victor was not yet in sight.</span></span> <span data-ttu-id="890fc-382">不毛で乾燥したこの地では、小型か敏捷かどう猛でなければ、栄えることはおろか、生き残る希望さえ持てなかった。</span><span class="sxs-lookup"><span data-stu-id="890fc-382">In this barren and desiccated land, only the small or the swift or the fierce could flourish, or even hope to survive.</span></span>

## <a name="images"></a><span data-ttu-id="890fc-383">イメージ</span><span class="sxs-lookup"><span data-stu-id="890fc-383">Images</span></span>

### <a name="static-image-or-animated-gif"></a><span data-ttu-id="890fc-384">静的イメージまたはアニメーション GIF</span><span class="sxs-lookup"><span data-stu-id="890fc-384">Static Image or Animated gif</span></span>

```markdown
![this is the alt text](../images/Logo_DotNet.png)
```

![これは代替テキストです](../images/Logo_DotNet.png)

### <a name="linked-image"></a><span data-ttu-id="890fc-386">リンク画像</span><span class="sxs-lookup"><span data-stu-id="890fc-386">Linked Image</span></span>

```markdown
[![alt text for linked image](../images/Logo_DotNet.png)](https://dot.net)
```

<span data-ttu-id="890fc-387">[![リンク画像の代替テキスト](../images/Logo_DotNet.png)](https://dot.net)</span><span class="sxs-lookup"><span data-stu-id="890fc-387">[![alt text for linked image](../images/Logo_DotNet.png)](https://dot.net)</span></span>

## <a name="videos"></a><span data-ttu-id="890fc-388">ビデオ</span><span class="sxs-lookup"><span data-stu-id="890fc-388">Videos</span></span>

<span data-ttu-id="890fc-389">現在、次の構文を使用して、Channel 9 と YouTube の両方のビデオを埋め込むことができます。</span><span class="sxs-lookup"><span data-stu-id="890fc-389">Currently, you can embed both Channel 9 and YouTube videos with the following syntax:</span></span>

### <a name="channel-9"></a><span data-ttu-id="890fc-390">Channel 9</span><span class="sxs-lookup"><span data-stu-id="890fc-390">Channel 9</span></span>

```markdown
> [!VIDEO <channel9_video_link>]
```

<span data-ttu-id="890fc-391">ビデオの正しい URL を取得するには、ビデオ フレームの下にある **[埋め込み]** タブを選択して、`<iframe>` 要素から URL をコピーします。</span><span class="sxs-lookup"><span data-stu-id="890fc-391">To get the video's correct URL, select the **Embed** tab below the video frame, and copy the URL from the `<iframe>` element.</span></span> <span data-ttu-id="890fc-392">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="890fc-392">For example:</span></span>

```markdown
> [!VIDEO https://channel9.msdn.com/Blogs/dotnet/NET-Core-20-Released/player]
```

### <a name="youtube"></a><span data-ttu-id="890fc-393">YouTube</span><span class="sxs-lookup"><span data-stu-id="890fc-393">YouTube</span></span>

<span data-ttu-id="890fc-394">ビデオの正しい URL を取得するには、ビデオ右クリックし、 **[埋め込みコードのコピー]** を選択して、`<iframe>` 要素から URL をコピーします。</span><span class="sxs-lookup"><span data-stu-id="890fc-394">To get the video's correct URL, right-click on the video, select **Copy Embed Code**, and copy the URL from the `<iframe>` element.</span></span>

```markdown
> [!VIDEO <youtube_video_link>]
```

<span data-ttu-id="890fc-395">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="890fc-395">For example:</span></span>

```markdown
> [!VIDEO https://www.youtube.com/embed/Q2mMbjw6cLA]
```

## <a name="docsmicrosoft-extensions"></a><span data-ttu-id="890fc-396">docs.microsoft 拡張機能</span><span class="sxs-lookup"><span data-stu-id="890fc-396">docs.microsoft extensions</span></span>

<span data-ttu-id="890fc-397">docs.microsoft により、GitHub Flavored Markdown にいくつかの拡張機能が追加されます。</span><span class="sxs-lookup"><span data-stu-id="890fc-397">docs.microsoft provides a few additional extensions to GitHub Flavored Markdown.</span></span>

### <a name="alerts"></a><span data-ttu-id="890fc-398">アラート</span><span class="sxs-lookup"><span data-stu-id="890fc-398">Alerts</span></span>

<span data-ttu-id="890fc-399">ドキュメント サイトに適切なスタイルで表示できるようにするため、次のアラート スタイルを使用することが重要です。</span><span class="sxs-lookup"><span data-stu-id="890fc-399">It's important to use the following alert styles so they render with the proper style in the documentation site.</span></span> <span data-ttu-id="890fc-400">ただし、GitHub のレンダリング エンジンではこれらは区別されません。</span><span class="sxs-lookup"><span data-stu-id="890fc-400">However, the rendering engine on GitHub doesn't diferentiate them.</span></span>

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

<span data-ttu-id="890fc-401">また、これらは次のように表示されます:![アラート スタイル](../images/alerts.png)</span><span class="sxs-lookup"><span data-stu-id="890fc-401">And they'll render like this: ![Alert styles](../images/alerts.png)</span></span>

### <a name="includes"></a><span data-ttu-id="890fc-402">含まれているバージョン</span><span class="sxs-lookup"><span data-stu-id="890fc-402">Includes</span></span>

<span data-ttu-id="890fc-403">Include を使用して、あるファイルのマークダウンを別のファイルに埋め込むことができます。</span><span class="sxs-lookup"><span data-stu-id="890fc-403">You can embed the Markdown of one file into another using an include.</span></span>

[!INCLUDE[sample include file](../includes/sampleinclude.md)]

### <a name="checked-lists"></a><span data-ttu-id="890fc-404">チェックされたファイル</span><span class="sxs-lookup"><span data-stu-id="890fc-404">Checked lists</span></span>

<span data-ttu-id="890fc-405">リストには、カスタム スタイルを使用できます。</span><span class="sxs-lookup"><span data-stu-id="890fc-405">A custom style is available for lists.</span></span> <span data-ttu-id="890fc-406">緑色のチェック マークが付けられたリストを表示できます。</span><span class="sxs-lookup"><span data-stu-id="890fc-406">You can render lists with green check marks.</span></span>

> [!div class="checklist"]
>
> - <span data-ttu-id="890fc-407">.NET Core アプリの作成方法</span><span class="sxs-lookup"><span data-stu-id="890fc-407">How to create a .NET Core app</span></span>
> - <span data-ttu-id="890fc-408">Microsoft.XmlSerializer.Generator パッケージへの参照を追加する方法</span><span class="sxs-lookup"><span data-stu-id="890fc-408">How to add a reference to the Microsoft.XmlSerializer.Generator package</span></span>
> - <span data-ttu-id="890fc-409">MyApp.csproj を編集して依存関係を追加する方法</span><span class="sxs-lookup"><span data-stu-id="890fc-409">How to edit your MyApp.csproj to add dependencies</span></span>
> - <span data-ttu-id="890fc-410">クラスと XmlSerializer を追加する方法</span><span class="sxs-lookup"><span data-stu-id="890fc-410">How to add a class and an XmlSerializer</span></span>
> - <span data-ttu-id="890fc-411">アプリケーションをビルドして実行する方法</span><span class="sxs-lookup"><span data-stu-id="890fc-411">How to build and run the application</span></span>

<span data-ttu-id="890fc-412">使用中のチェックされたリストの例は、[.NET Core ドキュメント](https://docs.microsoft.com/dotnet/core/additional-tools/xml-serializer-generator)で確認できます。</span><span class="sxs-lookup"><span data-stu-id="890fc-412">You can see an example of checked lists in action in the [.NET Core docs](https://docs.microsoft.com/dotnet/core/additional-tools/xml-serializer-generator).</span></span>

### <a name="buttons"></a><span data-ttu-id="890fc-413">ボタン</span><span class="sxs-lookup"><span data-stu-id="890fc-413">Buttons</span></span>

> [!div class="button"]
> [<span data-ttu-id="890fc-414">ボタン リンク</span><span class="sxs-lookup"><span data-stu-id="890fc-414">button links</span></span>](../docs/core/index.md)

<span data-ttu-id="890fc-415">使用中のボタンの例は、[Visual Studio ドキュメント](https://docs.microsoft.com/visualstudio/install/install-visual-studio#step-2---download-visual-studio)で確認できます。</span><span class="sxs-lookup"><span data-stu-id="890fc-415">You can see an example of buttons in action in the [Visual Studio docs](https://docs.microsoft.com/visualstudio/install/install-visual-studio#step-2---download-visual-studio).</span></span>

### <a name="selectors"></a><span data-ttu-id="890fc-416">セレクター</span><span class="sxs-lookup"><span data-stu-id="890fc-416">Selectors</span></span>

> [!div class="op_single_selector"]
>
> - [macOS](../docs/core/tutorials/using-on-macos.md)
> - [Windows](../docs/core/tutorials/with-visual-studio.md)

<span data-ttu-id="890fc-419">使用中のセレクターの例は、[Azure ドキュメント](https://docs.microsoft.com/azure/expressroute/expressroute-howto-circuit-classic)で確認できます。</span><span class="sxs-lookup"><span data-stu-id="890fc-419">You can see an example of selectors in action at the [Azure docs](https://docs.microsoft.com/azure/expressroute/expressroute-howto-circuit-classic).</span></span>

### <a name="step-by-steps"></a><span data-ttu-id="890fc-420">操作手順</span><span class="sxs-lookup"><span data-stu-id="890fc-420">Step-By-Steps</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="890fc-421">[前へ](../docs/csharp/expression-trees-interpreting.md)
>[次へ](../docs/csharp/expression-trees-translating.md)</span><span class="sxs-lookup"><span data-stu-id="890fc-421">[Previous](../docs/csharp/expression-trees-interpreting.md)
[Next](../docs/csharp/expression-trees-translating.md)</span></span>

<span data-ttu-id="890fc-422">使用中の操作手順の例は、[C# ガイド](https://docs.microsoft.com/dotnet/csharp/tour-of-csharp/program-structure)で確認できます。</span><span class="sxs-lookup"><span data-stu-id="890fc-422">You can see an example of step-by-steps in action at the [C# Guide](https://docs.microsoft.com/dotnet/csharp/tour-of-csharp/program-structure).</span></span>
