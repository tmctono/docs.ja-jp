---
title: XML ドキュメント コメント - C# プログラミング ガイド
description: XML ドキュメントのコメントについて説明します。 特別なコメント フィールドに XML 要素を含め、ご自分のコードのドキュメントを作成できます。
ms.date: 07/20/2015
f1_keywords:
- cs.xml
helpviewer_keywords:
- XML [C#], code comments
- comments [C#], XML
- documentation comments [C#]
- C# source code files
- C# language, XML code comments
- XML documentation comments [C#]
ms.assetid: 803b7f7b-7428-4725-b5db-9a6cff273199
ms.openlocfilehash: fbdeb53331d9fc63d24a3322ea13863d7c0a3630
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/29/2020
ms.locfileid: "87381880"
---
# <a name="xml-documentation-comments-c-programming-guide"></a><span data-ttu-id="6e8f8-104">XML ドキュメント コメント (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="6e8f8-104">XML documentation comments (C# programming guide)</span></span>

<span data-ttu-id="6e8f8-105">C# では、ソース コード内で、コメントの対象となるコード ブロック直前の特別なコメント フィールド (トリプル スラッシュで示す) に XML 要素を配置することで、コード用のドキュメントを作成できます。例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="6e8f8-105">In C#, you can create documentation for your code by including XML elements in special comment fields (indicated by triple slashes) in the source code directly before the code block to which the comments refer, for example.</span></span>

```csharp
/// <summary>
///  This class performs an important function.
/// </summary>
public class MyClass {}
```

<span data-ttu-id="6e8f8-106">[-doc](../../language-reference/compiler-options/doc-compiler-option.md) オプションを使用してコンパイルすると、コンパイラは、ソース コード内のすべての XML タグを検索して、XML ドキュメント ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="6e8f8-106">When you compile with the [-doc](../../language-reference/compiler-options/doc-compiler-option.md) option, the compiler will search for all XML tags in the source code and create an XML documentation file.</span></span> <span data-ttu-id="6e8f8-107">コンパイラによって生成されたファイルに基づいて最終的なドキュメントを作成するには、カスタム ツールを作成するか、[DocFX](https://dotnet.github.io/docfx/) や [Sandcastle](https://github.com/EWSoftware/SHFB) などのツールを使用します。</span><span class="sxs-lookup"><span data-stu-id="6e8f8-107">To create the final documentation based on the compiler-generated file, you can create a custom tool or use a tool such as [DocFX](https://dotnet.github.io/docfx/) or [Sandcastle](https://github.com/EWSoftware/SHFB).</span></span>

<span data-ttu-id="6e8f8-108">XML 要素を参照するには (たとえば、XML ドキュメント コメントに記述する特定の XML 要素を関数で処理する場合)、標準の引用のしくみを使用できます (`<` と `>`)。</span><span class="sxs-lookup"><span data-stu-id="6e8f8-108">To refer to XML elements (for example, your function processes specific XML elements that you want to describe in an XML documentation comment), you can use the standard quoting mechanism (`<` and `>`).</span></span>  <span data-ttu-id="6e8f8-109">コード参照 (`cref`) 要素でジェネリック識別子を参照するには、エスケープ文字 (たとえば、`cref="List&lt;T&gt;"`) または中かっこ (`cref="List{T}"`) を使用できます。</span><span class="sxs-lookup"><span data-stu-id="6e8f8-109">To refer to generic identifiers in code reference (`cref`) elements, you can use either the escape characters (for example, `cref="List&lt;T&gt;"`) or braces (`cref="List{T}"`).</span></span>  <span data-ttu-id="6e8f8-110">特殊なケースとして、コンパイラは中かっこを山かっことして解析し、ジェネリック識別子を参照するときにドキュメント コメントの編集があまり面倒にならないようにしています。</span><span class="sxs-lookup"><span data-stu-id="6e8f8-110">As a special case, the compiler parses the braces as angle brackets to make the documentation comment less cumbersome to author when referring to generic identifiers.</span></span>

> [!NOTE]
> <span data-ttu-id="6e8f8-111">XML ドキュメント コメントはメタデータではなく、コンパイルされたアセンブリに含まれないため、リフレクションでアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="6e8f8-111">The XML documentation comments are not metadata; they are not included in the compiled assembly and therefore they are not accessible through reflection.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="6e8f8-112">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="6e8f8-112">In this section</span></span>

- [<span data-ttu-id="6e8f8-113">ドキュメント コメント用の推奨タグ</span><span class="sxs-lookup"><span data-stu-id="6e8f8-113">Recommended tags for documentation comments</span></span>](./recommended-tags-for-documentation-comments.md)

- [<span data-ttu-id="6e8f8-114">XML ファイルの処理</span><span class="sxs-lookup"><span data-stu-id="6e8f8-114">Processing the XML file</span></span>](./processing-the-xml-file.md)

- [<span data-ttu-id="6e8f8-115">ドキュメント タグの区切り記号</span><span class="sxs-lookup"><span data-stu-id="6e8f8-115">Delimiters for documentation tags</span></span>](./delimiters-for-documentation-tags.md)

- [<span data-ttu-id="6e8f8-116">XML ドキュメント機能を使用する方法</span><span class="sxs-lookup"><span data-stu-id="6e8f8-116">How to use the XML documentation features</span></span>](./how-to-use-the-xml-documentation-features.md)

## <a name="related-sections"></a><span data-ttu-id="6e8f8-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="6e8f8-117">Related sections</span></span>

<span data-ttu-id="6e8f8-118">詳細については次を参照してください:</span><span class="sxs-lookup"><span data-stu-id="6e8f8-118">For more information, see:</span></span>

- [<span data-ttu-id="6e8f8-119">-doc (ドキュメント コメントの処理)</span><span class="sxs-lookup"><span data-stu-id="6e8f8-119">-doc (Process Documentation Comments)</span></span>](../../language-reference/compiler-options/doc-compiler-option.md)

## <a name="c-language-specification"></a><span data-ttu-id="6e8f8-120">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="6e8f8-120">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="6e8f8-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="6e8f8-121">See also</span></span>

- [<span data-ttu-id="6e8f8-122">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="6e8f8-122">C# Programming Guide</span></span>](../index.md)
