---
description: return ステートメント - C# リファレンス
title: return ステートメント - C# リファレンス
ms.date: 07/20/2015
f1_keywords:
- return_CSharpKeyword
- return
helpviewer_keywords:
- return statement [C#]
- return keyword [C#]
ms.assetid: 6da6e152-5b58-4448-8f3f-470dd0617ecd
ms.openlocfilehash: 486db846304c0972942ff58f3d5b276083681abe
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/30/2020
ms.locfileid: "89137003"
---
# <a name="return-c-reference"></a><span data-ttu-id="f0736-103">return (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="f0736-103">return (C# Reference)</span></span>

<span data-ttu-id="f0736-104">`return` ステートメントは、メソッドの実行を終了し、呼び出し側のメソッドに制御を戻します。</span><span class="sxs-lookup"><span data-stu-id="f0736-104">The `return` statement terminates execution of the method in which it appears and returns control to the calling method.</span></span> <span data-ttu-id="f0736-105">省略可能な値を返すこともできます。</span><span class="sxs-lookup"><span data-stu-id="f0736-105">It can also return an optional value.</span></span> <span data-ttu-id="f0736-106">メソッドが `void` 型の場合、`return` ステートメントは省略できます。</span><span class="sxs-lookup"><span data-stu-id="f0736-106">If the method is a `void` type, the `return` statement can be omitted.</span></span>

 <span data-ttu-id="f0736-107">return ステートメントが `try` ブロック内にある場合は、制御が呼び出し側のメソッドに返される前に、`finally` ブロック (存在する場合) が実行されます。</span><span class="sxs-lookup"><span data-stu-id="f0736-107">If the return statement is inside a `try` block, the `finally` block, if one exists, will be executed before control returns to the calling method.</span></span>

## <a name="example"></a><span data-ttu-id="f0736-108">例</span><span class="sxs-lookup"><span data-stu-id="f0736-108">Example</span></span>

 <span data-ttu-id="f0736-109">次の例では、メソッド `CalculateArea()` がローカル変数 `area` を `double` 値として返します。</span><span class="sxs-lookup"><span data-stu-id="f0736-109">In the following example, the method `CalculateArea()` returns the local variable `area` as a `double` value.</span></span>

[!code-csharp[csrefKeywordsJump#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#6)]  

## <a name="c-language-specification"></a><span data-ttu-id="f0736-110">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="f0736-110">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="f0736-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="f0736-111">See also</span></span>

- [<span data-ttu-id="f0736-112">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="f0736-112">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="f0736-113">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="f0736-113">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="f0736-114">C# のキーワード</span><span class="sxs-lookup"><span data-stu-id="f0736-114">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="f0736-115">return ステートメント</span><span class="sxs-lookup"><span data-stu-id="f0736-115">return Statement</span></span>](/cpp/cpp/return-statement-cpp)
