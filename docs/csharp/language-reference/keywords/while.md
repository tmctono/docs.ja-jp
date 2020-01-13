---
title: while - C# リファレンス
ms.date: 05/28/2018
f1_keywords:
- while_CSharpKeyword
- while
helpviewer_keywords:
- while keyword [C#]
ms.assetid: 72a0765c-6852-4aca-b327-4a11cb7f5c59
ms.openlocfilehash: eb9aa2ea8d6b1c96e0be7d377f7c047194b598de
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/07/2020
ms.locfileid: "75712794"
---
# <a name="while-c-reference"></a><span data-ttu-id="7dd1d-102">while (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="7dd1d-102">while (C# Reference)</span></span>

<span data-ttu-id="7dd1d-103">`while` ステートメントでは、指定されたブール式が `true` と評価される間に、ステートメントまたはステートメント ブロックが実行されます。</span><span class="sxs-lookup"><span data-stu-id="7dd1d-103">The `while` statement executes a statement or a block of statements while a specified Boolean expression evaluates to `true`.</span></span> <span data-ttu-id="7dd1d-104">ループの各実行の前に式が評価されるため、`while` ループは 0 回以上実行されます。</span><span class="sxs-lookup"><span data-stu-id="7dd1d-104">Because that expression is evaluated before each execution of the loop, a `while` loop executes zero or more times.</span></span> <span data-ttu-id="7dd1d-105">[do](do.md) ループは、これとは異なり、1 回以上実行されます。</span><span class="sxs-lookup"><span data-stu-id="7dd1d-105">This differs from the [do](do.md) loop, which executes one or more times.</span></span>

<span data-ttu-id="7dd1d-106">`while` ステートメント ブロック内の任意の位置で、[break](break.md) ステートメントを使用してループを抜けることができます。</span><span class="sxs-lookup"><span data-stu-id="7dd1d-106">At any point within the `while` statement block, you can break out of the loop by using the [break](break.md) statement.</span></span>

<span data-ttu-id="7dd1d-107">[continue](continue.md) ステートメントを使用すると、`while` 式の評価に直接ステップ実行できます。</span><span class="sxs-lookup"><span data-stu-id="7dd1d-107">You can step directly to the evaluation of the `while` expression by using the [continue](continue.md) statement.</span></span> <span data-ttu-id="7dd1d-108">式の評価が `true` の場合、ループの最初のステートメントから実行が続行されます。</span><span class="sxs-lookup"><span data-stu-id="7dd1d-108">If the expression evaluates to `true`, execution continues at the first statement in the loop.</span></span> <span data-ttu-id="7dd1d-109">それ以外の場合、実行は、ループの後の最初のステートメントから続行されます。</span><span class="sxs-lookup"><span data-stu-id="7dd1d-109">Otherwise, execution continues at the first statement after the loop.</span></span>

<span data-ttu-id="7dd1d-110">また、[goto](goto.md)、[return](return.md)、[throw](throw.md) ステートメントのいずれかを使って `while` ループを終了することもできます。</span><span class="sxs-lookup"><span data-stu-id="7dd1d-110">You also can exit a `while` loop by the [goto](goto.md), [return](return.md), or [throw](throw.md) statements.</span></span>

## <a name="example"></a><span data-ttu-id="7dd1d-111">例</span><span class="sxs-lookup"><span data-stu-id="7dd1d-111">Example</span></span>

<span data-ttu-id="7dd1d-112">`while` ステートメントの使用方法を次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="7dd1d-112">The following example shows the usage of the `while` statement.</span></span> <span data-ttu-id="7dd1d-113">**[実行]** を選択して、コード例を実行します。</span><span class="sxs-lookup"><span data-stu-id="7dd1d-113">Select **Run** to run the example code.</span></span> <span data-ttu-id="7dd1d-114">その後に、コードを変更し、もう一度実行することができます。</span><span class="sxs-lookup"><span data-stu-id="7dd1d-114">After that you can modify the code and run it again.</span></span>

[!code-csharp-interactive[while loop example](~/samples/snippets/csharp/keywords/IterationKeywordsExamples.cs#3)]

## <a name="c-language-specification"></a><span data-ttu-id="7dd1d-115">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="7dd1d-115">C# language specification</span></span>

<span data-ttu-id="7dd1d-116">詳細については、「[C# 言語仕様](/dotnet/csharp/language-reference/language-specification/introduction)」の [while ステートメント](~/_csharplang/spec/statements.md#the-while-statement)に関するセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="7dd1d-116">For more information, see [The while statement](~/_csharplang/spec/statements.md#the-while-statement) section of the [C# language specification](/dotnet/csharp/language-reference/language-specification/introduction).</span></span>

## <a name="see-also"></a><span data-ttu-id="7dd1d-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="7dd1d-117">See also</span></span>

- [<span data-ttu-id="7dd1d-118">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="7dd1d-118">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="7dd1d-119">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="7dd1d-119">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="7dd1d-120">C# のキーワード</span><span class="sxs-lookup"><span data-stu-id="7dd1d-120">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="7dd1d-121">do ステートメント</span><span class="sxs-lookup"><span data-stu-id="7dd1d-121">do statement</span></span>](do.md)
