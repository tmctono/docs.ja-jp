---
title: params キーワード - C# リファレンス
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- params_CSharpKeyword
- params
helpviewer_keywords:
- parameters [C#], params
- params keyword [C#]
ms.assetid: 1690815e-b52b-4967-8380-5780aff08012
ms.openlocfilehash: 772c8da879eeccbe484c631a47de7fe8a32ec8d2
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2019
ms.locfileid: "65633579"
---
# <a name="params-c-reference"></a><span data-ttu-id="89eca-102">params (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="89eca-102">params (C# Reference)</span></span>

<span data-ttu-id="89eca-103">`params` キーワードを使用すると、可変数個の引数を受け取る[メソッド パラメーター](method-parameters.md)を指定できます。</span><span class="sxs-lookup"><span data-stu-id="89eca-103">By using the `params` keyword, you can specify a [method parameter](method-parameters.md) that takes a variable number of arguments.</span></span>

<span data-ttu-id="89eca-104">パラメーター宣言で指定した型の引数のコンマ区切りのリスト、または指定した型の引数の配列を渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="89eca-104">You can send a comma-separated list of arguments of the type specified in the parameter declaration or an array of arguments of the specified type.</span></span> <span data-ttu-id="89eca-105">また、引数を渡さないこともできます。</span><span class="sxs-lookup"><span data-stu-id="89eca-105">You also can send no arguments.</span></span> <span data-ttu-id="89eca-106">引数を渡さない場合、`params` リストの長さはゼロになります。</span><span class="sxs-lookup"><span data-stu-id="89eca-106">If you send no arguments, the length of the `params` list is zero.</span></span>

<span data-ttu-id="89eca-107">1 つのメソッド宣言内では、`params` キーワード以後にパラメーターを追加できないため、1 つの `params` キーワードだけを使用できます。</span><span class="sxs-lookup"><span data-stu-id="89eca-107">No additional parameters are permitted after the `params` keyword in a method declaration, and only one `params` keyword is permitted in a method declaration.</span></span>

<span data-ttu-id="89eca-108">`params` パラメーターの宣言された型は、次の例のとおり、1 次元の配列にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="89eca-108">The declared type of the `params` parameter must be a single-dimensional array, as the following example shows.</span></span> <span data-ttu-id="89eca-109">そのようにしない場合、コンパイル エラー [CS0225](../../misc/cs0225.md) が発生します。</span><span class="sxs-lookup"><span data-stu-id="89eca-109">Otherwise, a compiler error [CS0225](../../misc/cs0225.md) occurs.</span></span>

## <a name="example"></a><span data-ttu-id="89eca-110">例</span><span class="sxs-lookup"><span data-stu-id="89eca-110">Example</span></span>

<span data-ttu-id="89eca-111">次の例に示すように、さまざまな方法で `params` パラメーターに引数を渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="89eca-111">The following example demonstrates various ways in which arguments can be sent to a `params` parameter.</span></span>

[!code-csharp[csrefKeywordsMethodParams#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsMethodParams/CS/csrefKeywordsMethodParams.cs#5)] 

## <a name="c-language-specification"></a><span data-ttu-id="89eca-112">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="89eca-112">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="89eca-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="89eca-113">See also</span></span>

- [<span data-ttu-id="89eca-114">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="89eca-114">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="89eca-115">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="89eca-115">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="89eca-116">C# のキーワード</span><span class="sxs-lookup"><span data-stu-id="89eca-116">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="89eca-117">メソッド パラメーター</span><span class="sxs-lookup"><span data-stu-id="89eca-117">Method Parameters</span></span>](method-parameters.md)
