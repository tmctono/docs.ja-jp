---
title: ドキュメント タグの区切り記号 - C# プログラミング ガイド
description: ドキュメント タグの区切り記号について説明します。 区切り記号を使用して、ドキュメント コメントの開始位置と終了位置をコンパイラに示します。
ms.date: 07/20/2015
helpviewer_keywords:
- XML [C#], delimiters
- /** */ delimiters for C# documentation tags
- /// delimiter for C# documentation
ms.assetid: 9b2bdd18-4f5c-4c0b-988e-fb992e0d233e
ms.openlocfilehash: 3191e32b0ff2dbde004abaab0b699cd61fcbb150
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/29/2020
ms.locfileid: "87381984"
---
# <a name="delimiters-for-documentation-tags-c-programming-guide"></a><span data-ttu-id="98792-104">ドキュメント タグの区切り記号 (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="98792-104">Delimiters for documentation tags (C# programming guide)</span></span>

<span data-ttu-id="98792-105">XML ドキュメント コメントでは区切り記号を使用し、ドキュメント コメントの開始位置と終了位置をコンパイラに示す必要があります。</span><span class="sxs-lookup"><span data-stu-id="98792-105">The use of XML doc comments requires delimiters, which indicate to the compiler where a documentation comment begins and ends.</span></span> <span data-ttu-id="98792-106">XML ドキュメント タグでは、次の種類の区切り記号を使用できます。</span><span class="sxs-lookup"><span data-stu-id="98792-106">You can use the following kinds of delimiters with the XML documentation tags:</span></span>

- `///`

  <span data-ttu-id="98792-107">単一行の区切り記号。</span><span class="sxs-lookup"><span data-stu-id="98792-107">Single-line delimiter.</span></span> <span data-ttu-id="98792-108">これは、ドキュメント例に示されている形式であり、C# プロジェクト テンプレートで使用されます。</span><span class="sxs-lookup"><span data-stu-id="98792-108">This is the form that is shown in documentation examples and used by the C# project templates.</span></span> <span data-ttu-id="98792-109">区切り記号の直後に空白文字が続く場合、その文字は XML 出力に含まれません。</span><span class="sxs-lookup"><span data-stu-id="98792-109">If there is a white space character following the delimiter, that character is not included in the XML output.</span></span>

  > [!NOTE]
  > <span data-ttu-id="98792-110">Visual Studio IDE (統合開発環境) では、コード エディターで `///` 区切り記号を入力すると、`<summary>` タグと `</summary>` タグが自動的に挿入され、これらのタグの内側にカーソルが移動します。</span><span class="sxs-lookup"><span data-stu-id="98792-110">The Visual Studio integrated development environment (IDE) automatically inserts the `<summary>` and `</summary>` tags and moves your cursor within these tags after you type the `///` delimiter in the code editor.</span></span> <span data-ttu-id="98792-111">[[オプション] ダイアログ ボックス](/visualstudio/ide/reference/options-text-editor-csharp-advanced)で、この機能をオンまたはオフにできます。</span><span class="sxs-lookup"><span data-stu-id="98792-111">You can turn this feature on or off in the [Options dialog box](/visualstudio/ide/reference/options-text-editor-csharp-advanced).</span></span>
  
- `/** */`

  <span data-ttu-id="98792-112">複数行の区切り記号。</span><span class="sxs-lookup"><span data-stu-id="98792-112">Multiline delimiters.</span></span>

  <span data-ttu-id="98792-113">`/** */` 区切り記号を使用する場合は、次のいくつかの書式設定規則に従う必要があります。</span><span class="sxs-lookup"><span data-stu-id="98792-113">There are some formatting rules to follow when you use the `/** */` delimiters:</span></span>
  
  - <span data-ttu-id="98792-114">`/**` 区切り記号がある行で、行の残りの部分が空白の場合、その行はコメントとして処理されません。</span><span class="sxs-lookup"><span data-stu-id="98792-114">On the line that contains the `/**` delimiter, if the remainder of the line is white space, the line is not processed for comments.</span></span> <span data-ttu-id="98792-115">`/**` 区切り記号の後の最初の文字が空白の場合、その空白文字は無視され、行の残りの部分が処理されます。</span><span class="sxs-lookup"><span data-stu-id="98792-115">If the first character after the `/**` delimiter is white space, that white space character is ignored and the rest of the line is processed.</span></span> <span data-ttu-id="98792-116">それ以外の場合、`/**` 区切り記号の後にある行のテキスト全体が、コメントの一部として処理されます。</span><span class="sxs-lookup"><span data-stu-id="98792-116">Otherwise, the entire text of the line after the `/**` delimiter is processed as part of the comment.</span></span>

  - <span data-ttu-id="98792-117">`*/` 区切り記号がある行で、`*/` 区切り記号までの部分がすべて空白の場合、その行は無視されます。</span><span class="sxs-lookup"><span data-stu-id="98792-117">On the line that contains the `*/` delimiter, if there is only white space up to the `*/` delimiter, that line is ignored.</span></span> <span data-ttu-id="98792-118">それ以外の場合、その行の `*/` 区切り記号までのテキストが、コメントの一部として処理されます。</span><span class="sxs-lookup"><span data-stu-id="98792-118">Otherwise, the text on the line up to the `*/` delimiter is processed as part of the comment.</span></span>
  
  - <span data-ttu-id="98792-119">`/**` 区切り記号で始まる行の後に来る行については、コンパイラは各行の先頭で共通のパターンを検索します。</span><span class="sxs-lookup"><span data-stu-id="98792-119">For the lines after the one that begins with the `/**` delimiter, the compiler looks for a common pattern at the beginning of each line.</span></span> <span data-ttu-id="98792-120">このパターンは、空白 (省略可能) + アスタリスク (`*`) + 空白 (省略可能) で構成されます。</span><span class="sxs-lookup"><span data-stu-id="98792-120">The pattern can consist of optional white space and an asterisk (`*`), followed by more optional white space.</span></span> <span data-ttu-id="98792-121">`/**` 区切り記号または `*/` 区切り記号で始まらない各行の先頭でコンパイラが共通のパターンを見つけた場合、各行のそのパターンは無視されます。</span><span class="sxs-lookup"><span data-stu-id="98792-121">If the compiler finds a common pattern at the beginning of each line that does not begin with the `/**` delimiter or the `*/` delimiter, it ignores that pattern for each line.</span></span>

  <span data-ttu-id="98792-122">これらの規則について、次の例で説明します。</span><span class="sxs-lookup"><span data-stu-id="98792-122">The following examples illustrate these rules.</span></span>

  - <span data-ttu-id="98792-123">次のコメントでは、`<summary>` で始まる行だけがコメントの一部として処理されます。</span><span class="sxs-lookup"><span data-stu-id="98792-123">The only part of the following comment that's processed is the line that begins with `<summary>`.</span></span> <span data-ttu-id="98792-124">次の 3 つのタグ形式は、いずれも同じコメントを生成します。</span><span class="sxs-lookup"><span data-stu-id="98792-124">The three tag formats produce the same comments.</span></span>

    ```csharp
    /** <summary>text</summary> */

    /**
    <summary>text</summary>
    */

    /**
     * <summary>text</summary>
    */
    ```

  - <span data-ttu-id="98792-125">コンパイラによって、2 行目と 3 行目の先頭で共通のパターン " \* " が識別されます。</span><span class="sxs-lookup"><span data-stu-id="98792-125">The compiler identifies a common pattern of " \* " at the beginning of the second and third lines.</span></span> <span data-ttu-id="98792-126">このパターンは出力に含まれません。</span><span class="sxs-lookup"><span data-stu-id="98792-126">The pattern is not included in the output.</span></span>

    ```csharp
    /**
     * <summary>
     * text </summary>*/
    ```

  - <span data-ttu-id="98792-127">次のコメントでは、3 行目の 2 番目の文字がアスタリスクではないため、コンパイラは共通のパターンを検索しません。</span><span class="sxs-lookup"><span data-stu-id="98792-127">The compiler finds no common pattern in the following comment because the second character on the third line is not an asterisk.</span></span> <span data-ttu-id="98792-128">このため、2 行目と 3 行目のすべてのテキストがコメントの一部として処理されます。</span><span class="sxs-lookup"><span data-stu-id="98792-128">Therefore, all text on the second and third lines is processed as part of the comment.</span></span>

    ```csharp
    /**
     * <summary>
       text </summary>
    */
    ```

  - <span data-ttu-id="98792-129">次のコメントでは、2 つの原因によりコンパイラはパターンを検出しません。</span><span class="sxs-lookup"><span data-stu-id="98792-129">The compiler finds no pattern in the following comment for two reasons.</span></span> <span data-ttu-id="98792-130">まず、アスタリスクの前の空白の数が一致していません。</span><span class="sxs-lookup"><span data-stu-id="98792-130">First, the number of spaces before the asterisk is not consistent.</span></span> <span data-ttu-id="98792-131">次に、5 行目がタブで始まっています。空白とタブは一致しません。</span><span class="sxs-lookup"><span data-stu-id="98792-131">Second, the fifth line begins with a tab, which does not match spaces.</span></span> <span data-ttu-id="98792-132">このため、2 行目から 5 行目のすべてのテキストがコメントの一部として処理されます。</span><span class="sxs-lookup"><span data-stu-id="98792-132">Therefore, all text from lines two through five is processed as part of the comment.</span></span>

    <!-- markdownlint-disable MD010 -->
    ```csharp
    /**
      * <summary>
      * text
     *  text2
        *  </summary>
    */
    ```
    <!-- markdownlint-enable MD010 -->

## <a name="see-also"></a><span data-ttu-id="98792-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="98792-133">See also</span></span>

- [<span data-ttu-id="98792-134">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="98792-134">C# programming guide</span></span>](../index.md)
- [<span data-ttu-id="98792-135">XML ドキュメント コメント</span><span class="sxs-lookup"><span data-stu-id="98792-135">XML documentation comments</span></span>](./index.md)
- [<span data-ttu-id="98792-136">-doc (C# コンパイラ オプション)</span><span class="sxs-lookup"><span data-stu-id="98792-136">-doc (C# compiler options)</span></span>](../../language-reference/compiler-options/doc-compiler-option.md)
