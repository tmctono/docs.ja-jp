---
title: 型推論
description: について説明しますが、どのようにF#コンパイラ値、変数、パラメーター、および戻り値の型を推論します。
ms.date: 05/16/2016
ms.openlocfilehash: ab1a4aa8df4312287df749d5d6d0ea2858091152
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2019
ms.locfileid: "65641669"
---
# <a name="type-inference"></a><span data-ttu-id="8c746-103">型推論</span><span class="sxs-lookup"><span data-stu-id="8c746-103">Type Inference</span></span>

<span data-ttu-id="8c746-104">このトピックでは、F# コンパイラが値、変数、パラメーターおよび戻り値の型を推論する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="8c746-104">This topic describes how the F# compiler infers the types of values, variables, parameters and return values.</span></span>

## <a name="type-inference-in-general"></a><span data-ttu-id="8c746-105">推定の一般的な型します。</span><span class="sxs-lookup"><span data-stu-id="8c746-105">Type Inference in General</span></span>

<span data-ttu-id="8c746-106">型の推論という考え方は、F# の構成要素と、コンパイラには、型が推測できません増やした以外の種類を指定する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="8c746-106">The idea of type inference is that you do not have to specify the types of F# constructs except when the compiler cannot conclusively deduce the type.</span></span> <span data-ttu-id="8c746-107">F# は動的に型指定された言語に、F# での値が所有権が弱い型指定された、明示的な型情報を省略することは限りません。</span><span class="sxs-lookup"><span data-stu-id="8c746-107">Omitting explicit type information does not mean that F# is a dynamically typed language or that values in F# are weakly typed.</span></span> <span data-ttu-id="8c746-108">F#静的に型指定された言語、コンパイラはコンパイル時に、正確な型の各構成体を推測することを意味します。</span><span class="sxs-lookup"><span data-stu-id="8c746-108">F# is a statically typed language, which means that the compiler deduces an exact type for each construct during compilation.</span></span> <span data-ttu-id="8c746-109">コンパイラが各構成体の型を推測するのに十分な情報がない場合、コードのどこかに明示的な型の注釈を追加することで通常追加の型についてを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8c746-109">If there is not enough information for the compiler to deduce the types of each construct, you must supply additional type information, typically by adding explicit type annotations somewhere in the code.</span></span>

## <a name="inference-of-parameter-and-return-types"></a><span data-ttu-id="8c746-110">パラメーターと戻り値の型の推論</span><span class="sxs-lookup"><span data-stu-id="8c746-110">Inference of Parameter and Return Types</span></span>

<span data-ttu-id="8c746-111">パラメーター リストでは、各パラメーターの型を指定するのにはありません。</span><span class="sxs-lookup"><span data-stu-id="8c746-111">In a parameter list, you do not have to specify the type of each parameter.</span></span> <span data-ttu-id="8c746-112">まだF#、静的に型指定された言語では、したがってすべての値と式、この明確な型をコンパイル時にします。</span><span class="sxs-lookup"><span data-stu-id="8c746-112">And yet, F# is a statically typed language, and therefore every value and expression has a definite type at compile time.</span></span> <span data-ttu-id="8c746-113">明示的に指定されていないその型の場合は、コンパイラは、コンテキストに基づいて型を推測します。</span><span class="sxs-lookup"><span data-stu-id="8c746-113">For those types that you do not specify explicitly, the compiler infers the type based on the context.</span></span> <span data-ttu-id="8c746-114">型がない場合は指定された、ジェネリックと推論されます。</span><span class="sxs-lookup"><span data-stu-id="8c746-114">If the type is not otherwise specified, it is inferred to be generic.</span></span> <span data-ttu-id="8c746-115">コードでは、一貫性がない値を使用する場合、このような方法ではなく 1 つ型を推論、コンパイラがエラーを報告する、値の使用箇所をすべてを満たします。</span><span class="sxs-lookup"><span data-stu-id="8c746-115">If the code uses a value inconsistently, in such a way that there is no single inferred type that satisfies all the uses of a value, the compiler reports an error.</span></span>

<span data-ttu-id="8c746-116">関数の戻り値の型は、関数の最後の式の型によって決定されます。</span><span class="sxs-lookup"><span data-stu-id="8c746-116">The return type of a function is determined by the type of the last expression in the function.</span></span>

<span data-ttu-id="8c746-117">たとえば、次のコードでは、パラメーターの型で`a`と`b`および戻り値の型はすべてに推定`int`ためリテラル`100`の種類は`int`します。</span><span class="sxs-lookup"><span data-stu-id="8c746-117">For example, in the following code, the parameter types `a` and `b` and the return type are all inferred to be `int` because the literal `100` is of type `int`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-3/snippet301.fs)]

<span data-ttu-id="8c746-118">リテラルは、変更することによって型の推定の影響を与えることができます。</span><span class="sxs-lookup"><span data-stu-id="8c746-118">You can influence type inference by changing the literals.</span></span> <span data-ttu-id="8c746-119">行った場合、 `100` 、 `uint32` 、サフィックスが追加された`u`、種類の`a`、 `b`、および戻り値が推論されます`uint32`。</span><span class="sxs-lookup"><span data-stu-id="8c746-119">If you make the `100` a `uint32` by appending the suffix `u`, the types of `a`, `b`, and the return value are inferred to be `uint32`.</span></span>

<span data-ttu-id="8c746-120">影響を及ぼすことができます関数と、特定の型のみを使用するメソッドなど、型の制限を意味するその他のコンストラクトを使用して、型の推論します。</span><span class="sxs-lookup"><span data-stu-id="8c746-120">You can also influence type inference by using other constructs that imply restrictions on the type, such as functions and methods that work with only a particular type.</span></span>

<span data-ttu-id="8c746-121">また、適用できます明示的な型の注釈関数またはメソッド パラメーターまたは変数を式では、次の例に示すようにします。</span><span class="sxs-lookup"><span data-stu-id="8c746-121">Also, you can apply explicit type annotations to function or method parameters or to variables in expressions, as shown in the following examples.</span></span> <span data-ttu-id="8c746-122">さまざまな制約との間の競合が発生した場合、エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="8c746-122">Errors result if conflicts occur between different constraints.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-3/snippet302.fs)]

<span data-ttu-id="8c746-123">結局のところ、パラメーターの型の注釈を指定して、関数の戻り値を明示的に指定できます。</span><span class="sxs-lookup"><span data-stu-id="8c746-123">You can also explicitly specify the return value of a function by providing a type annotation after all the parameters.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-3/snippet303.fs)]

<span data-ttu-id="8c746-124">型の注釈がパラメーターに役立つ一般的なケースは、パラメーターはオブジェクト型であり、メンバーを使用する場合です。</span><span class="sxs-lookup"><span data-stu-id="8c746-124">A common case where a type annotation is useful on a parameter is when the parameter is an object type and you want to use a member.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-3/snippet304.fs)]

## <a name="automatic-generalization"></a><span data-ttu-id="8c746-125">自動ジェネリック化</span><span class="sxs-lookup"><span data-stu-id="8c746-125">Automatic Generalization</span></span>

<span data-ttu-id="8c746-126">場合は、関数コードでは、パラメーターの型に依存しない、パラメーターをジェネリックと見なします。</span><span class="sxs-lookup"><span data-stu-id="8c746-126">If the function code is not dependent on the type of a parameter, the compiler considers the parameter to be generic.</span></span> <span data-ttu-id="8c746-127">これは呼び出されます*自動ジェネリック化*複雑さを増大させることがなく汎用的なコードを記述するための強力なを指定できます。</span><span class="sxs-lookup"><span data-stu-id="8c746-127">This is called *automatic generalization*, and it can be a powerful aid to writing generic code without increasing complexity.</span></span>

<span data-ttu-id="8c746-128">たとえば、次の関数は、タプルに任意の型の 2 つのパラメーターを結合します。</span><span class="sxs-lookup"><span data-stu-id="8c746-128">For example, the following function combines two parameters of any type into a tuple.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-3/snippet305.fs)]

<span data-ttu-id="8c746-129">型が推論します。</span><span class="sxs-lookup"><span data-stu-id="8c746-129">The type is inferred to be</span></span>

```fsharp
'a -> 'b -> 'a * 'b
```

## <a name="additional-information"></a><span data-ttu-id="8c746-130">追加情報</span><span class="sxs-lookup"><span data-stu-id="8c746-130">Additional Information</span></span>

<span data-ttu-id="8c746-131">型の推定については、F# 言語仕様で詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="8c746-131">Type inference is described in more detail in the F# Language Specification.</span></span>

## <a name="see-also"></a><span data-ttu-id="8c746-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="8c746-132">See also</span></span>

- [<span data-ttu-id="8c746-133">自動ジェネリック化</span><span class="sxs-lookup"><span data-stu-id="8c746-133">Automatic Generalization</span></span>](generics/automatic-generalization.md)
