---
title: String.Split を使用して文字列を解析する方法 (C# ガイド)
description: String.Split は、一連の区切り記号で分割された文字列の配列を返します。 文字列を解析する簡単な方法です。
ms.date: 01/03/2018
helpviewer_keywords:
- splitting strings [C#]
- Split method [C#]
- strings [C#], splitting
- parse strings
ms.assetid: 729c2923-4169-41c6-9c90-ef176c1e2953
ms.custom: mvc
ms.openlocfilehash: 4f0056426fb29ec3d76093e57fa45e2046f27a4f
ms.sourcegitcommit: 7137e12f54c4e83a94ae43ec320f8cf59c1772ea
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/10/2020
ms.locfileid: "84662993"
---
# <a name="how-to-parse-strings-using-stringsplit-in-c"></a><span data-ttu-id="16c8d-104">C\# で String.Split を使用して文字列を解析する方法</span><span class="sxs-lookup"><span data-stu-id="16c8d-104">How to parse strings using String.Split in C\#</span></span>

<span data-ttu-id="16c8d-105"><xref:System.String.Split%2A?displayProperty=nameWithType> メソッドは、1 つまたは複数の区切り記号に基づいて入力文字列を分割することで部分文字列の配列を作成します。</span><span class="sxs-lookup"><span data-stu-id="16c8d-105">The <xref:System.String.Split%2A?displayProperty=nameWithType> method creates an array of substrings by splitting the input string based on one or more delimiters.</span></span> <span data-ttu-id="16c8d-106">英語のように単語の間にスペースがある文章の場合に、単語の境界で文字列を分割する最も簡単な方法になります。</span><span class="sxs-lookup"><span data-stu-id="16c8d-106">It is often the easiest way to separate a string on word boundaries.</span></span> <span data-ttu-id="16c8d-107">他の特定の文字や文字列で文字列を分割する際にも利用されます。</span><span class="sxs-lookup"><span data-stu-id="16c8d-107">It is also used to split strings on other specific characters or strings.</span></span>

[!INCLUDE[interactive-note](~/includes/csharp-interactive-note.md)]

<span data-ttu-id="16c8d-108">次のコードは一般的なフレーズを単語ごとの文字列の配列に分割します。</span><span class="sxs-lookup"><span data-stu-id="16c8d-108">The following code splits a common phrase into an array of strings for each word.</span></span>

:::code language="csharp" interactive="try-dotnet-method" source="../../../samples/snippets/csharp/how-to/strings/ParseStringsUsingSplit.cs" id="Snippet1":::

<span data-ttu-id="16c8d-109">区切り文字のインスタンスごとに、返される配列で値が生成されます。</span><span class="sxs-lookup"><span data-stu-id="16c8d-109">Every instance of a separator character produces a value in the returned array.</span></span> <span data-ttu-id="16c8d-110">連続する区切り文字により、返される配列の値として空の文字列が生成されます。</span><span class="sxs-lookup"><span data-stu-id="16c8d-110">Consecutive separator characters produce the empty string as a value in the returned array.</span></span> <span data-ttu-id="16c8d-111">空白文字を区切り記号として使用する次の例では、空の文字列がどのように作成されるかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="16c8d-111">You can see how an empty string is created in the following example, which uses the space character as a separator.</span></span>

:::code language="csharp" interactive="try-dotnet-method" source="../../../samples/snippets/csharp/how-to/strings/ParseStringsUsingSplit.cs" id="Snippet2":::

<span data-ttu-id="16c8d-112">この動作により、コンマ区切り値 (CSV) ファイルなどの形式で表形式データを簡単に表すことができます。</span><span class="sxs-lookup"><span data-stu-id="16c8d-112">This behavior makes it easier for formats like comma-separated values (CSV) files representing tabular data.</span></span> <span data-ttu-id="16c8d-113">連続するコンマは空の列を表します。</span><span class="sxs-lookup"><span data-stu-id="16c8d-113">Consecutive commas represent a blank column.</span></span>

<span data-ttu-id="16c8d-114">任意の <xref:System.StringSplitOptions.RemoveEmptyEntries?displayProperty=nameWithType> パラメーターを渡し、返される配列で空の文字列を除外できます。</span><span class="sxs-lookup"><span data-stu-id="16c8d-114">You can pass an optional <xref:System.StringSplitOptions.RemoveEmptyEntries?displayProperty=nameWithType> parameter to exclude any empty strings in the returned array.</span></span> <span data-ttu-id="16c8d-115">返されるコレクションの処理が複雑な場合、[LINQ](../programming-guide/concepts/linq/index.md) を使用し、結果のシーケンスを操作できます。</span><span class="sxs-lookup"><span data-stu-id="16c8d-115">For more complicated processing of the returned collection, you can use [LINQ](../programming-guide/concepts/linq/index.md) to manipulate the result sequence.</span></span>

<span data-ttu-id="16c8d-116"><xref:System.String.Split%2A?displayProperty=nameWithType> では、複数の区切り文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="16c8d-116"><xref:System.String.Split%2A?displayProperty=nameWithType> can use multiple separator characters.</span></span>
<span data-ttu-id="16c8d-117">次の例ではスペース、コンマ、ピリオド、コロン、タブを使用しています。すべて、これらの区切り文字を格納した配列で <xref:System.String.Split%2A> に渡されます。</span><span class="sxs-lookup"><span data-stu-id="16c8d-117">The following example uses spaces, commas, periods, colons, and tabs, all passed in an array containing these separating characters, to <xref:System.String.Split%2A>.</span></span>
<span data-ttu-id="16c8d-118">コードの一番下にあるループは、返される配列の各単語を表示します。</span><span class="sxs-lookup"><span data-stu-id="16c8d-118">The loop at the bottom of the code displays each of the words in the returned array.</span></span>

:::code language="csharp" interactive="try-dotnet-method" source="../../../samples/snippets/csharp/how-to/strings/ParseStringsUsingSplit.cs" id="Snippet3":::

<span data-ttu-id="16c8d-119">区切りの連続するインスタンスにより、出力配列で空の文字列が生成されます。</span><span class="sxs-lookup"><span data-stu-id="16c8d-119">Consecutive instances of any separator produce the empty string in the output array:</span></span>

:::code language="csharp" interactive="try-dotnet-method" source="../../../samples/snippets/csharp/how-to/strings/ParseStringsUsingSplit.cs" id="Snippet4":::

<span data-ttu-id="16c8d-120"><xref:System.String.Split%2A?displayProperty=nameWithType> は、文字列の配列 (1 つの文字ではなく、対象の文字列を解析するための区切り記号として機能する文字シーケンス) を受け取ることができます。</span><span class="sxs-lookup"><span data-stu-id="16c8d-120"><xref:System.String.Split%2A?displayProperty=nameWithType> can take an array of strings (character sequences that act as separators for parsing the target string, instead of single characters).</span></span>

:::code language="csharp" interactive="try-dotnet-method" source="../../../samples/snippets/csharp/how-to/strings/ParseStringsUsingSplit.cs" id="Snippet5":::

## <a name="see-also"></a><span data-ttu-id="16c8d-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="16c8d-121">See also</span></span>

- [<span data-ttu-id="16c8d-122">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="16c8d-122">C# programming guide</span></span>](../programming-guide/index.md)
- [<span data-ttu-id="16c8d-123">文字列</span><span class="sxs-lookup"><span data-stu-id="16c8d-123">Strings</span></span>](../programming-guide/strings/index.md)
- [<span data-ttu-id="16c8d-124">.NET 正規表現</span><span class="sxs-lookup"><span data-stu-id="16c8d-124">.NET regular expressions</span></span>](../../standard/base-types/regular-expressions.md)
