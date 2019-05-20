---
title: while - C# リファレンス
ms.custom: seodec18
ms.date: 05/28/2018
f1_keywords:
- while_CSharpKeyword
- while
helpviewer_keywords:
- while keyword [C#]
ms.assetid: 72a0765c-6852-4aca-b327-4a11cb7f5c59
ms.openlocfilehash: 2cf58e2edc5685032c2b9e590bc456e3a4e4d79b
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2019
ms.locfileid: "65633074"
---
# <a name="while-c-reference"></a><span data-ttu-id="82459-102">while (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="82459-102">while (C# Reference)</span></span>

<span data-ttu-id="82459-103">`while` ステートメントでは、指定されたブール式が `true` と評価される間に、ステートメントまたはステートメント ブロックが実行されます。</span><span class="sxs-lookup"><span data-stu-id="82459-103">The `while` statement executes a statement or a block of statements while a specified Boolean expression evaluates to `true`.</span></span> <span data-ttu-id="82459-104">ループの各実行の前に式が評価されるため、`while` ループは 0 回以上実行されます。</span><span class="sxs-lookup"><span data-stu-id="82459-104">Because that expression is evaluated before each execution of the loop, a `while` loop executes zero or more times.</span></span> <span data-ttu-id="82459-105">[do](do.md) ループは、これとは異なり、1 回以上実行されます。</span><span class="sxs-lookup"><span data-stu-id="82459-105">This differs from the [do](do.md) loop, which executes one or more times.</span></span>

<span data-ttu-id="82459-106">`while` ステートメント ブロック内の任意の位置で、[break](break.md) ステートメントを使用してループを抜けることができます。</span><span class="sxs-lookup"><span data-stu-id="82459-106">At any point within the `while` statement block, you can break out of the loop by using the [break](break.md) statement.</span></span>

<span data-ttu-id="82459-107">[continue](continue.md) ステートメントを使用すると、`while` 式の評価に直接ステップ実行できます。</span><span class="sxs-lookup"><span data-stu-id="82459-107">You can step directly to the evaluation of the `while` expression by using the [continue](continue.md) statement.</span></span> <span data-ttu-id="82459-108">式の評価が `true` の場合、ループの最初のステートメントから実行が続行されます。</span><span class="sxs-lookup"><span data-stu-id="82459-108">If the expression evaluates to `true`, execution continues at the first statement in the loop.</span></span> <span data-ttu-id="82459-109">それ以外の場合、実行は、ループの後の最初のステートメントから続行されます。</span><span class="sxs-lookup"><span data-stu-id="82459-109">Otherwise, execution continues at the first statement after the loop.</span></span>

<span data-ttu-id="82459-110">また、[goto](goto.md)、[return](return.md)、[throw](throw.md) ステートメントのいずれかを使って `while` ループを終了することもできます。</span><span class="sxs-lookup"><span data-stu-id="82459-110">You also can exit a `while` loop by the [goto](goto.md), [return](return.md), or [throw](throw.md) statements.</span></span>

## <a name="example"></a><span data-ttu-id="82459-111">例</span><span class="sxs-lookup"><span data-stu-id="82459-111">Example</span></span>

<span data-ttu-id="82459-112">`while` ステートメントの使用方法を次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="82459-112">The following example shows the usage of the `while` statement.</span></span> <span data-ttu-id="82459-113">**[実行]** を選択して、コード例を実行します。</span><span class="sxs-lookup"><span data-stu-id="82459-113">Select **Run** to run the example code.</span></span> <span data-ttu-id="82459-114">その後に、コードを変更し、もう一度実行することができます。</span><span class="sxs-lookup"><span data-stu-id="82459-114">After that you can modify the code and run it again.</span></span>

[!code-csharp-interactive[while loop example](~/samples/snippets/csharp/keywords/IterationKeywordsExamples.cs#3)]

## <a name="c-language-specification"></a><span data-ttu-id="82459-115">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="82459-115">C# language specification</span></span>

<span data-ttu-id="82459-116">詳細については、「[C# 言語仕様](../language-specification/index.md)」の [while ステートメント](~/_csharplang/spec/statements.md#the-while-statement)に関するセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="82459-116">For more information, see [The while statement](~/_csharplang/spec/statements.md#the-while-statement) section of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="82459-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="82459-117">See also</span></span>

- [<span data-ttu-id="82459-118">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="82459-118">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="82459-119">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="82459-119">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="82459-120">C# のキーワード</span><span class="sxs-lookup"><span data-stu-id="82459-120">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="82459-121">繰り返しステートメント</span><span class="sxs-lookup"><span data-stu-id="82459-121">Iteration Statements</span></span>](iteration-statements.md)
- [<span data-ttu-id="82459-122">do ステートメント</span><span class="sxs-lookup"><span data-stu-id="82459-122">do statement</span></span>](do.md)
