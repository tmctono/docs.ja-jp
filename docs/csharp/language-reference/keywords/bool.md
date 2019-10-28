---
title: bool キーワード - C# リファレンス
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- bool_CSharpKeyword
- bool
helpviewer_keywords:
- bool keyword [C#]
ms.assetid: 551cfe35-2632-4343-af49-33ad12da08e2
ms.openlocfilehash: 880e8c0b733afbf5c09f543e06a5a4a858d2b456
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72771847"
---
# <a name="bool-c-reference"></a><span data-ttu-id="fdc6b-102">bool (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="fdc6b-102">bool (C# Reference)</span></span>

<span data-ttu-id="fdc6b-103">`bool` キーワードは <xref:System.Boolean?displayProperty=nameWithType> の別名です。</span><span class="sxs-lookup"><span data-stu-id="fdc6b-103">The `bool` keyword is an alias of <xref:System.Boolean?displayProperty=nameWithType>.</span></span> <span data-ttu-id="fdc6b-104">ブール値 ([true](true-literal.md) と [false](false-literal.md)) を格納する変数を宣言するために使われます。</span><span class="sxs-lookup"><span data-stu-id="fdc6b-104">It is used to declare variables to store the Boolean values: [true](true-literal.md) and [false](false-literal.md).</span></span>

> [!NOTE]
> <span data-ttu-id="fdc6b-105">3 値ロジックをサポートする必要がある場合は、`bool?` 型を使用します。たとえば、3 値ブール型をサポートするデータベースを操作する場合などです。</span><span class="sxs-lookup"><span data-stu-id="fdc6b-105">Use the `bool?` type, if you need to support the three-valued logic, for example, when you work with databases that support a three-valued Boolean type.</span></span> <span data-ttu-id="fdc6b-106">`bool?` オペランドの場合、定義済みの `&` 演算子と `|` 演算子は 3 値ロジックをサポートします。</span><span class="sxs-lookup"><span data-stu-id="fdc6b-106">For the `bool?` operands, the predefined `&` and `|` operators support the three-valued logic.</span></span> <span data-ttu-id="fdc6b-107">詳細については、「[Boolean logical operators (ブール論理演算子)](../operators/boolean-logical-operators.md)」記事の「[Nullable Boolean logical operators (null 許容論理演算子)](../operators/boolean-logical-operators.md#nullable-boolean-logical-operators)」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="fdc6b-107">For more information, see the [Nullable Boolean logical operators](../operators/boolean-logical-operators.md#nullable-boolean-logical-operators) section of the [Boolean logical operators](../operators/boolean-logical-operators.md) article.</span></span>

## <a name="literals"></a><span data-ttu-id="fdc6b-108">リテラル</span><span class="sxs-lookup"><span data-stu-id="fdc6b-108">Literals</span></span>

<span data-ttu-id="fdc6b-109">`bool` 変数にはブール値を代入できます。</span><span class="sxs-lookup"><span data-stu-id="fdc6b-109">You can assign a Boolean value to a `bool` variable.</span></span> <span data-ttu-id="fdc6b-110">また、`bool` として評価される式も `bool` 変数に代入できます。</span><span class="sxs-lookup"><span data-stu-id="fdc6b-110">You can also assign an expression that evaluates to `bool` to a `bool` variable.</span></span>

[!code-csharp[csrefKeywordsTypes#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#1)]

<span data-ttu-id="fdc6b-111">`bool` 変数の既定値は `false` です。</span><span class="sxs-lookup"><span data-stu-id="fdc6b-111">The default value of a `bool` variable is `false`.</span></span> <span data-ttu-id="fdc6b-112">`bool?` 変数の既定値は `null` です。</span><span class="sxs-lookup"><span data-stu-id="fdc6b-112">The default value of a `bool?` variable is `null`.</span></span>

## <a name="conversions"></a><span data-ttu-id="fdc6b-113">変換</span><span class="sxs-lookup"><span data-stu-id="fdc6b-113">Conversions</span></span>

<span data-ttu-id="fdc6b-114">C++ では、`bool` 型の値を `int` 型の値に変換できます。つまり、`false` はゼロと同等であり、`true` はゼロ以外の値と同等です。</span><span class="sxs-lookup"><span data-stu-id="fdc6b-114">In C++, a value of type `bool` can be converted to a value of type `int`; in other words, `false` is equivalent to zero and `true` is equivalent to nonzero values.</span></span> <span data-ttu-id="fdc6b-115">C# では、`bool` 型と他の型の間に変換はありません。</span><span class="sxs-lookup"><span data-stu-id="fdc6b-115">In C#, there is no conversion between the `bool` type and other types.</span></span> <span data-ttu-id="fdc6b-116">たとえば、次の `if` ステートメントは C# では無効です。</span><span class="sxs-lookup"><span data-stu-id="fdc6b-116">For example, the following `if` statement is invalid in C#:</span></span>

[!code-csharp[csrefKeywordsTypes#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#2)]

<span data-ttu-id="fdc6b-117">`int` 型の変数をテストするには、0 などの値と明示的に比較する必要があります。次はその例です。</span><span class="sxs-lookup"><span data-stu-id="fdc6b-117">To test a variable of the type `int`, you have to explicitly compare it to a value, such as zero, as follows:</span></span>

[!code-csharp[csrefKeywordsTypes#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#3)]

## <a name="example"></a><span data-ttu-id="fdc6b-118">例</span><span class="sxs-lookup"><span data-stu-id="fdc6b-118">Example</span></span>

<span data-ttu-id="fdc6b-119">この例のプログラムは、キーボードから文字された文字がアルファベットかどうかを調べます。</span><span class="sxs-lookup"><span data-stu-id="fdc6b-119">In this example, you enter a character from the keyboard and the program checks if the input character is a letter.</span></span> <span data-ttu-id="fdc6b-120">アルファベットである場合は、小文字か大文字かを調べます。</span><span class="sxs-lookup"><span data-stu-id="fdc6b-120">If it is a letter, it checks if it is lowercase or uppercase.</span></span> <span data-ttu-id="fdc6b-121">こうしたチェックは <xref:System.Char.IsLetter%2A> と <xref:System.Char.IsLower%2A> で実行され、どちらも `bool` 型を返します。</span><span class="sxs-lookup"><span data-stu-id="fdc6b-121">These checks are performed with the <xref:System.Char.IsLetter%2A>, and <xref:System.Char.IsLower%2A>, both of which return the `bool` type:</span></span>

[!code-csharp[csrefKeywordsTypes#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#4)]

## <a name="c-language-specification"></a><span data-ttu-id="fdc6b-122">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="fdc6b-122">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="fdc6b-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="fdc6b-123">See also</span></span>

- [<span data-ttu-id="fdc6b-124">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="fdc6b-124">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="fdc6b-125">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="fdc6b-125">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="fdc6b-126">C# のキーワード</span><span class="sxs-lookup"><span data-stu-id="fdc6b-126">C# Keywords</span></span>](./index.md)
- [<span data-ttu-id="fdc6b-127">整数型</span><span class="sxs-lookup"><span data-stu-id="fdc6b-127">Integral types</span></span>](../builtin-types/integral-numeric-types.md)
- [<span data-ttu-id="fdc6b-128">組み込み型の一覧表</span><span class="sxs-lookup"><span data-stu-id="fdc6b-128">Built-In Types Table</span></span>](./built-in-types-table.md)
