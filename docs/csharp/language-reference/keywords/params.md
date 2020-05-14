---
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
ms.openlocfilehash: 77d7fd19ff57f80f401191027e2fae95026e1966
ms.sourcegitcommit: 465547886a1224a5435c3ac349c805e39ce77706
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2020
ms.locfileid: "81738837"
---
# <a name="params-c-reference"></a><span data-ttu-id="d754d-102">params (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="d754d-102">params (C# Reference)</span></span>

<span data-ttu-id="d754d-103">`params` キーワードを使用すると、可変数個の引数を受け取る[メソッド パラメーター](method-parameters.md)を指定できます。</span><span class="sxs-lookup"><span data-stu-id="d754d-103">By using the `params` keyword, you can specify a [method parameter](method-parameters.md) that takes a variable number of arguments.</span></span> <span data-ttu-id="d754d-104">パラメーターの型は 1 次元配列でなければなりません。</span><span class="sxs-lookup"><span data-stu-id="d754d-104">The parameter type must be a single-dimensional array.</span></span>

<span data-ttu-id="d754d-105">1 つのメソッド宣言内では、`params` キーワード以後にパラメーターを追加できないため、1 つの `params` キーワードだけを使用できます。</span><span class="sxs-lookup"><span data-stu-id="d754d-105">No additional parameters are permitted after the `params` keyword in a method declaration, and only one `params` keyword is permitted in a method declaration.</span></span>

<span data-ttu-id="d754d-106">`params` パラメーターの宣言された型が 1 次元配列でない場合は、コンパイラ エラー [CS0225](../../misc/cs0225.md) が発生します。</span><span class="sxs-lookup"><span data-stu-id="d754d-106">If the declared type of the `params` parameter is not a single-dimensional array, compiler error [CS0225](../../misc/cs0225.md) occurs.</span></span>

<span data-ttu-id="d754d-107">`params` パラメーターを使用してメソッドを呼び出す場合は、以下を渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="d754d-107">When you call a method with a `params` parameter, you can pass in:</span></span>

- <span data-ttu-id="d754d-108">配列要素の型の引数のコンマ区切りのリスト。</span><span class="sxs-lookup"><span data-stu-id="d754d-108">A comma-separated list of arguments of the type of the array elements.</span></span>
- <span data-ttu-id="d754d-109">指定した型の引数の配列。</span><span class="sxs-lookup"><span data-stu-id="d754d-109">An array of arguments of the specified type.</span></span>
- <span data-ttu-id="d754d-110">引数なし。</span><span class="sxs-lookup"><span data-stu-id="d754d-110">No arguments.</span></span> <span data-ttu-id="d754d-111">引数を渡さない場合、`params` リストの長さはゼロになります。</span><span class="sxs-lookup"><span data-stu-id="d754d-111">If you send no arguments, the length of the `params` list is zero.</span></span>

## <a name="example"></a><span data-ttu-id="d754d-112">例</span><span class="sxs-lookup"><span data-stu-id="d754d-112">Example</span></span>

<span data-ttu-id="d754d-113">次の例に示すように、さまざまな方法で `params` パラメーターに引数を渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="d754d-113">The following example demonstrates various ways in which arguments can be sent to a `params` parameter.</span></span>

[!code-csharp[csrefKeywordsMethodParams#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsMethodParams/CS/csrefKeywordsMethodParams.cs#5)]

## <a name="c-language-specification"></a><span data-ttu-id="d754d-114">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="d754d-114">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="d754d-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="d754d-115">See also</span></span>

- [<span data-ttu-id="d754d-116">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="d754d-116">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="d754d-117">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="d754d-117">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="d754d-118">C# のキーワード</span><span class="sxs-lookup"><span data-stu-id="d754d-118">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="d754d-119">メソッド パラメーター</span><span class="sxs-lookup"><span data-stu-id="d754d-119">Method Parameters</span></span>](method-parameters.md)
