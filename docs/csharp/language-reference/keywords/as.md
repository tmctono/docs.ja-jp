---
title: as - C# リファレンス
ms.custom: seodec18
ms.date: 10/11/2018
f1_keywords:
- as_CSharpKeyword
- as
helpviewer_keywords:
- type conversion [C#], as keyword
- as keyword [C#]
ms.assetid: a9be126b-cbf4-4990-a70d-d0e1983cad0e
ms.openlocfilehash: 84e599340877ce52dc6242ea259c69672915c546
ms.sourcegitcommit: 10986410e59ff29f2ec55c6759bde3eb4d1a00cb
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/31/2019
ms.locfileid: "66422018"
---
# <a name="as-c-reference"></a><span data-ttu-id="ce654-102">as (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="ce654-102">as (C# Reference)</span></span>
<span data-ttu-id="ce654-103">`as` 演算子を使用して、互換性のある参照型または [null 許容型](../../../csharp/programming-guide/nullable-types/index.md)間で特定の型変換を実行できます。</span><span class="sxs-lookup"><span data-stu-id="ce654-103">You can use the `as` operator to perform certain types of conversions between compatible reference types or [nullable types](../../../csharp/programming-guide/nullable-types/index.md).</span></span> <span data-ttu-id="ce654-104">次のコードは一例を示しています。</span><span class="sxs-lookup"><span data-stu-id="ce654-104">The following code shows an example.</span></span>  
  
[!code-csharp[csrefKeywordsOperator#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#1)]

<span data-ttu-id="ce654-105">この例のように、変換が成功したかどうかを確認するには、`as` 式の結果を `null` と比較する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ce654-105">As the example shows, you need to compare the result of the `as` expression with `null` to check if a conversion is successful.</span></span> <span data-ttu-id="ce654-106">C# 7.0 以降は、[is](is.md) 式を使用して変換が成功したことをテストし、変換が成功したときに条件付きで変数を割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="ce654-106">Beginning with C# 7.0, you can use the [is](is.md) expression both to test that a conversion succeeds and conditionally assign a variable when the conversion succeeds.</span></span> <span data-ttu-id="ce654-107">多くのシナリオでは、`as` 演算子を使用するよりも簡潔です。</span><span class="sxs-lookup"><span data-stu-id="ce654-107">In many scenarios, it's more concise than using the `as` operator.</span></span> <span data-ttu-id="ce654-108">詳細については、[`is` 演算子](is.md)の記事の「[型パターン](is.md#type)」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ce654-108">For more information, see the [Type pattern](is.md#type) section of the [`is` operator](is.md) article.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="ce654-109">解説</span><span class="sxs-lookup"><span data-stu-id="ce654-109">Remarks</span></span>  
 <span data-ttu-id="ce654-110">`as` 演算子はキャスト演算と似ています。</span><span class="sxs-lookup"><span data-stu-id="ce654-110">The `as` operator is like a cast operation.</span></span> <span data-ttu-id="ce654-111">ただし、変換が可能でない場合、`as` は例外を発生させる代わりに `null` を返します。</span><span class="sxs-lookup"><span data-stu-id="ce654-111">However, if the conversion isn't possible, `as` returns `null` instead of raising an exception.</span></span> <span data-ttu-id="ce654-112">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="ce654-112">Consider the following example:</span></span>  
  
```csharp  
expression as type  
```  
  
 <span data-ttu-id="ce654-113">このコードは次の式と同等ですが、`expression` 変数は 1 回しか評価されません。</span><span class="sxs-lookup"><span data-stu-id="ce654-113">The code is equivalent to the following expression except that the `expression` variable is evaluated only one time.</span></span>  
  
```csharp  
expression is type ? (type)expression : (type)null  
```  
  
 <span data-ttu-id="ce654-114">なお、`as` 演算子は、参照変換、null 許容変換またはボックス変換のみ実行します。</span><span class="sxs-lookup"><span data-stu-id="ce654-114">Note that the `as` operator performs only reference conversions, nullable conversions, and boxing conversions.</span></span> <span data-ttu-id="ce654-115">`as` 演算子は、ユーザー定義変換など、他の変換を実行できないため、ユーザー定義変換を実行するには、代わりにキャスト式を使用します。</span><span class="sxs-lookup"><span data-stu-id="ce654-115">The `as` operator can't perform other conversions, such as user-defined conversions, which should instead be performed by using cast expressions.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ce654-116">例</span><span class="sxs-lookup"><span data-stu-id="ce654-116">Example</span></span>  

[!code-csharp[csrefKeywordsOperator#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#2)]
  
## <a name="c-language-specification"></a><span data-ttu-id="ce654-117">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="ce654-117">C# Language Specification</span></span>  

<span data-ttu-id="ce654-118">詳細については、「[C# 言語仕様](../language-specification/index.md)」の [as 演算子](~/_csharplang/spec/expressions.md#the-as-operator)に関するセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ce654-118">For more information, see [The as operator](~/_csharplang/spec/expressions.md#the-as-operator) in the [C# Language Specification](../language-specification/index.md).</span></span> <span data-ttu-id="ce654-119">言語仕様は、C# の構文と使用法に関する信頼性のある情報源です。</span><span class="sxs-lookup"><span data-stu-id="ce654-119">The language specification is the definitive source for C# syntax and usage.</span></span>
 
## <a name="see-also"></a><span data-ttu-id="ce654-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="ce654-120">See also</span></span>

- [<span data-ttu-id="ce654-121">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="ce654-121">C# Reference</span></span>](../../../csharp/language-reference/index.md)
- [<span data-ttu-id="ce654-122">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="ce654-122">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="ce654-123">C# のキーワード</span><span class="sxs-lookup"><span data-stu-id="ce654-123">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)
- [<span data-ttu-id="ce654-124">is</span><span class="sxs-lookup"><span data-stu-id="ce654-124">is</span></span>](../../../csharp/language-reference/keywords/is.md)
- [<span data-ttu-id="ce654-125">?:演算子</span><span class="sxs-lookup"><span data-stu-id="ce654-125">?: Operator</span></span>](../../../csharp/language-reference/operators/conditional-operator.md)
