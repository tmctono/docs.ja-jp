---
description: パラメーター配列の params キーワード - C# リファレンス
title: パラメーター配列の params キーワード - C# リファレンス
ms.date: 07/20/2015
f1_keywords:
- params_CSharpKeyword
- params
helpviewer_keywords:
- parameters [C#], params
- params keyword [C#]
- parameter array
ms.assetid: 1690815e-b52b-4967-8380-5780aff08012
ms.openlocfilehash: a2726c725508cd297001aaabddeff414704d1115
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/30/2020
ms.locfileid: "89134472"
---
# <a name="params-c-reference"></a><span data-ttu-id="a980a-103">params (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="a980a-103">params (C# Reference)</span></span>

<span data-ttu-id="a980a-104">`params` キーワードを使用すると、可変数個の引数を受け取る[メソッド パラメーター](method-parameters.md)を指定できます。</span><span class="sxs-lookup"><span data-stu-id="a980a-104">By using the `params` keyword, you can specify a [method parameter](method-parameters.md) that takes a variable number of arguments.</span></span> <span data-ttu-id="a980a-105">パラメーターの型は 1 次元配列でなければなりません。</span><span class="sxs-lookup"><span data-stu-id="a980a-105">The parameter type must be a single-dimensional array.</span></span>

<span data-ttu-id="a980a-106">1 つのメソッド宣言内では、`params` キーワード以後にパラメーターを追加できないため、1 つの `params` キーワードだけを使用できます。</span><span class="sxs-lookup"><span data-stu-id="a980a-106">No additional parameters are permitted after the `params` keyword in a method declaration, and only one `params` keyword is permitted in a method declaration.</span></span>

<span data-ttu-id="a980a-107">`params` パラメーターの宣言された型が 1 次元配列でない場合は、コンパイラ エラー [CS0225](../../misc/cs0225.md) が発生します。</span><span class="sxs-lookup"><span data-stu-id="a980a-107">If the declared type of the `params` parameter is not a single-dimensional array, compiler error [CS0225](../../misc/cs0225.md) occurs.</span></span>

<span data-ttu-id="a980a-108">`params` パラメーターを使用してメソッドを呼び出す場合は、以下を渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="a980a-108">When you call a method with a `params` parameter, you can pass in:</span></span>

- <span data-ttu-id="a980a-109">配列要素の型の引数のコンマ区切りのリスト。</span><span class="sxs-lookup"><span data-stu-id="a980a-109">A comma-separated list of arguments of the type of the array elements.</span></span>
- <span data-ttu-id="a980a-110">指定した型の引数の配列。</span><span class="sxs-lookup"><span data-stu-id="a980a-110">An array of arguments of the specified type.</span></span>
- <span data-ttu-id="a980a-111">引数なし。</span><span class="sxs-lookup"><span data-stu-id="a980a-111">No arguments.</span></span> <span data-ttu-id="a980a-112">引数を渡さない場合、`params` リストの長さはゼロになります。</span><span class="sxs-lookup"><span data-stu-id="a980a-112">If you send no arguments, the length of the `params` list is zero.</span></span>

## <a name="example"></a><span data-ttu-id="a980a-113">例</span><span class="sxs-lookup"><span data-stu-id="a980a-113">Example</span></span>

<span data-ttu-id="a980a-114">次の例に示すように、さまざまな方法で `params` パラメーターに引数を渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="a980a-114">The following example demonstrates various ways in which arguments can be sent to a `params` parameter.</span></span>

[!code-csharp[csrefKeywordsMethodParams#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsMethodParams/CS/csrefKeywordsMethodParams.cs#5)]

## <a name="c-language-specification"></a><span data-ttu-id="a980a-115">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="a980a-115">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="a980a-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="a980a-116">See also</span></span>

- [<span data-ttu-id="a980a-117">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="a980a-117">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="a980a-118">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="a980a-118">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="a980a-119">C# のキーワード</span><span class="sxs-lookup"><span data-stu-id="a980a-119">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="a980a-120">メソッド パラメーター</span><span class="sxs-lookup"><span data-stu-id="a980a-120">Method Parameters</span></span>](method-parameters.md)
