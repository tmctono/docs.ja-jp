---
title: LINQ と文字列 (C#)
ms.date: 07/20/2015
ms.assetid: dbe2d657-b3f3-487e-b645-21fb2d71cd7b
ms.openlocfilehash: b805bc7318b8c5fe70ab1c060d1058a6bbc4f177
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2020
ms.locfileid: "75635536"
---
# <a name="linq-and-strings-c"></a><span data-ttu-id="030df-102">LINQ と文字列 (C#)</span><span class="sxs-lookup"><span data-stu-id="030df-102">LINQ and strings (C#)</span></span>

<span data-ttu-id="030df-103">文字列やそのコレクションは、LINQ を使って照会したり変換したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="030df-103">LINQ can be used to query and transform strings and collections of strings.</span></span> <span data-ttu-id="030df-104">特に、テキスト ファイル内の半構造化されたデータでその利便性が発揮されます。</span><span class="sxs-lookup"><span data-stu-id="030df-104">It can be especially useful with semi-structured data in text files.</span></span> <span data-ttu-id="030df-105">LINQ クエリは、従来の文字列関数や正規表現と組み合わせることができます。</span><span class="sxs-lookup"><span data-stu-id="030df-105">LINQ queries can be combined with traditional string functions and regular expressions.</span></span> <span data-ttu-id="030df-106">たとえば、<xref:System.String.Split%2A?displayProperty=nameWithType> または <xref:System.Text.RegularExpressions.Regex.Split%2A?displayProperty=nameWithType> メソッドを使用して、文字列の配列を作成し、その後で LINQ を使用してクエリを実行したり変更したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="030df-106">For example, you can use the <xref:System.String.Split%2A?displayProperty=nameWithType> or <xref:System.Text.RegularExpressions.Regex.Split%2A?displayProperty=nameWithType> method to create an array of strings that you can then query or modify by using LINQ.</span></span> <span data-ttu-id="030df-107">LINQ クエリの <xref:System.Text.RegularExpressions.Regex.IsMatch%2A?displayProperty=nameWithType> 句で `where` メソッドを使用できます。</span><span class="sxs-lookup"><span data-stu-id="030df-107">You can use the <xref:System.Text.RegularExpressions.Regex.IsMatch%2A?displayProperty=nameWithType> method in the `where` clause of a LINQ query.</span></span> <span data-ttu-id="030df-108">LINQ を使用して、正規表現によって返される <xref:System.Text.RegularExpressions.MatchCollection> の結果に対してクエリを実行したり変更したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="030df-108">And you can use LINQ to query or modify the <xref:System.Text.RegularExpressions.MatchCollection> results returned by a regular expression.</span></span>

<span data-ttu-id="030df-109">このセクションで説明する手法を使えば、半構造化されたテキスト データを XML に変換することもできます。</span><span class="sxs-lookup"><span data-stu-id="030df-109">You can also use the techniques described in this section to transform semi-structured text data to XML.</span></span> <span data-ttu-id="030df-110">詳細については、「[CSV ファイルから XML を生成する方法](how-to-generate-xml-from-csv-files.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="030df-110">For more information, see [How to generate XML from CSV files](how-to-generate-xml-from-csv-files.md).</span></span>

<span data-ttu-id="030df-111">このセクションの例は、次の 2 つのカテゴリに分かれています。</span><span class="sxs-lookup"><span data-stu-id="030df-111">The examples in this section fall into two categories:</span></span>

## <a name="querying-a-block-of-text"></a><span data-ttu-id="030df-112">テキスト ブロックに対するクエリ</span><span class="sxs-lookup"><span data-stu-id="030df-112">Querying a block of text</span></span>

<span data-ttu-id="030df-113"><xref:System.String.Split%2A?displayProperty=nameWithType> メソッドまたは <xref:System.Text.RegularExpressions.Regex.Split%2A?displayProperty=nameWithType> メソッドを使用して、テキスト ブロックをクエリ可能な小さな文字列の配列に分割することによって、テキスト ブロックのクエリ、分析、および変更を実行できます。</span><span class="sxs-lookup"><span data-stu-id="030df-113">You can query, analyze, and modify text blocks by splitting them into a queryable array of smaller strings by using the <xref:System.String.Split%2A?displayProperty=nameWithType> method or the <xref:System.Text.RegularExpressions.Regex.Split%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="030df-114">単語や文、段落、ページなどの単位にソース テキストを分割できるほか、クエリ内で必要であれば、さらに細かく分割することもできます。</span><span class="sxs-lookup"><span data-stu-id="030df-114">You can split the source text into words, sentences, paragraphs, pages, or any other criteria, and then perform additional splits if they are required in your query.</span></span>

- [<span data-ttu-id="030df-115">文字列での単語の出現回数をカウントする方法 (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="030df-115">How to count occurrences of a word in a string (LINQ) (C#)</span></span>](how-to-count-occurrences-of-a-word-in-a-string-linq.md)  
  <span data-ttu-id="030df-116">テキストに対する単純なクエリを LINQ で行う方法が紹介されています。</span><span class="sxs-lookup"><span data-stu-id="030df-116">Shows how to use LINQ for simple querying over text.</span></span>

- [<span data-ttu-id="030df-117">指定されたワードのセットを含む文章を照会する方法 (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="030df-117">How to query for sentences that contain a specified set of words (LINQ) (C#)</span></span>](how-to-query-for-sentences-that-contain-a-specified-set-of-words-linq.md)

  <span data-ttu-id="030df-118">区切りを指定してテキスト ファイルを分割する方法やその各構成要素に対してクエリを実行する方法が紹介されています。</span><span class="sxs-lookup"><span data-stu-id="030df-118">Shows how to split text files on arbitrary boundaries and how to perform queries against each part.</span></span>

- [<span data-ttu-id="030df-119">文字列内の文字を照会する方法 (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="030df-119">How to query for characters in a string (LINQ) (C#)</span></span>](how-to-query-for-characters-in-a-string-linq.md)

  <span data-ttu-id="030df-120">文字列がクエリ可能型であることを実証します。</span><span class="sxs-lookup"><span data-stu-id="030df-120">Demonstrates that a string is a queryable type.</span></span>

- [<span data-ttu-id="030df-121">LINQ クエリと正規表現を組み合わせる方法 (C#)</span><span class="sxs-lookup"><span data-stu-id="030df-121">How to combine LINQ queries with regular expressions (C#)</span></span>](how-to-combine-linq-queries-with-regular-expressions.md)

  <span data-ttu-id="030df-122">LINQ クエリで正規表現を使い、フィルター処理されたクエリ結果に対して複雑なパターン マッチを行う方法が紹介されています。</span><span class="sxs-lookup"><span data-stu-id="030df-122">Shows how to use regular expressions in LINQ queries for complex pattern matching on filtered query results.</span></span>

## <a name="querying-semi-structured-data-in-text-format"></a><span data-ttu-id="030df-123">半構造化されたテキスト形式データに対するクエリ</span><span class="sxs-lookup"><span data-stu-id="030df-123">Querying semi-structured data in text format</span></span>

<span data-ttu-id="030df-124">テキスト ファイルにはさまざまな種類がありますが、タブ区切りファイルやコンマ区切りファイル、固定長行など同様の形式を持った一連の行で構成されていることは少なくありません。</span><span class="sxs-lookup"><span data-stu-id="030df-124">Many different types of text files consist of a series of lines, often with similar formatting, such as tab- or comma-delimited files or fixed-length lines.</span></span> <span data-ttu-id="030df-125">そのようなテキスト ファイルをメモリに読み込んだ後、LINQ を使って、必要な行を照会したり編集したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="030df-125">After you read such a text file into memory, you can use LINQ to query and/or modify the lines.</span></span> <span data-ttu-id="030df-126">複数ソースからのデータを組み合わせる作業も LINQ クエリなら簡単に行うことができます。</span><span class="sxs-lookup"><span data-stu-id="030df-126">LINQ queries also simplify the task of combining data from multiple sources.</span></span>

- [<span data-ttu-id="030df-127">2 つのリストの差集合を見つける方法 (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="030df-127">How to find the set difference between two lists (LINQ) (C#)</span></span>](how-to-find-the-set-difference-between-two-lists-linq.md)

  <span data-ttu-id="030df-128">ある特定のリストには存在しているものの、それ以外には存在しない文字列をすべて探す方法が紹介されています。</span><span class="sxs-lookup"><span data-stu-id="030df-128">Shows how to find all the strings that are present in one list but not the other.</span></span>

- [<span data-ttu-id="030df-129">任意のワードまたはフィールドを基準にテキスト データの並べ替えまたはフィルター処理を実行する方法 (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="030df-129">How to sort or filter text data by any word or field (LINQ) (C#)</span></span>](how-to-sort-or-filter-text-data-by-any-word-or-field-linq.md)

  <span data-ttu-id="030df-130">単語やフィールドに基づいてテキスト行を並べ替える方法が紹介されています。</span><span class="sxs-lookup"><span data-stu-id="030df-130">Shows how to sort text lines based on any word or field.</span></span>

- [<span data-ttu-id="030df-131">区切りファイルのフィールドの順序を変更する方法 (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="030df-131">How to reorder the fields of a delimited file (LINQ) (C#)</span></span>](how-to-reorder-the-fields-of-a-delimited-file-linq.md)

  <span data-ttu-id="030df-132">.csv ファイルの行に含まれるフィールドを並べ替える方法が紹介されています。</span><span class="sxs-lookup"><span data-stu-id="030df-132">Shows how to reorder fields in a line in a .csv file.</span></span>

- [<span data-ttu-id="030df-133">文字列コレクションを結合および比較する方法 (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="030df-133">How to combine and compare string collections (LINQ) (C#)</span></span>](how-to-combine-and-compare-string-collections-linq.md)

  <span data-ttu-id="030df-134">文字列リストをさまざまな方法で結合する方法が紹介されています。</span><span class="sxs-lookup"><span data-stu-id="030df-134">Shows how to combine string lists in various ways.</span></span>

- [<span data-ttu-id="030df-135">複数のソースからオブジェクト コレクションにデータを設定する方法 (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="030df-135">How to populate object collections from multiple sources (LINQ) (C#)</span></span>](how-to-populate-object-collections-from-multiple-sources-linq.md)

  <span data-ttu-id="030df-136">複数のテキスト ファイルをデータ ソースとしてオブジェクトのコレクションを作成する方法が紹介されています。</span><span class="sxs-lookup"><span data-stu-id="030df-136">Shows how to create object collections by using multiple text files as data sources.</span></span>

- [<span data-ttu-id="030df-137">異種ファイルのコンテンツを結合する方法 (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="030df-137">How to join content from dissimilar files (LINQ) (C#)</span></span>](how-to-join-content-from-dissimilar-files-linq.md)
  
  <span data-ttu-id="030df-138">2 つのリストに含まれる文字列を、一致するキーを使って 1 つの文字列に結合する方法が紹介されています。</span><span class="sxs-lookup"><span data-stu-id="030df-138">Shows how to combine strings in two lists into a single string by using a matching key.</span></span>

- [<span data-ttu-id="030df-139">グループを使用して 1 つのファイルを複数のファイルに分割する方法 (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="030df-139">How to split a file into many files by using groups (LINQ) (C#)</span></span>](how-to-split-a-file-into-many-files-by-using-groups-linq.md)
  
  <span data-ttu-id="030df-140">1 つのファイルをデータ ソースとして新しいファイルを作成する方法が紹介されています。</span><span class="sxs-lookup"><span data-stu-id="030df-140">Shows how to create new files by using a single file as a data source.</span></span>

- [<span data-ttu-id="030df-141">CSV テキスト ファイルの列値を計算する方法 (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="030df-141">How to compute column values in a CSV text file (LINQ) (C#)</span></span>](how-to-compute-column-values-in-a-csv-text-file-linq.md)
  
  <span data-ttu-id="030df-142">.csv ファイルでテキスト データに対して数学的計算を実行する方法が紹介されています。</span><span class="sxs-lookup"><span data-stu-id="030df-142">Shows how to perform mathematical computations on text data in .csv files.</span></span>

## <a name="see-also"></a><span data-ttu-id="030df-143">参照</span><span class="sxs-lookup"><span data-stu-id="030df-143">See also</span></span>

- [<span data-ttu-id="030df-144">統合言語クエリ (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="030df-144">Language-Integrated Query (LINQ) (C#)</span></span>](index.md)
- [<span data-ttu-id="030df-145">CSV ファイルから XML を生成する方法</span><span class="sxs-lookup"><span data-stu-id="030df-145">How to generate XML from CSV files</span></span>](how-to-generate-xml-from-csv-files.md)
