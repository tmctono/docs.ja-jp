---
title: 例外の種類
description: 定義して、F# の例外の種類を使用する方法について説明します。
ms.date: 05/16/2016
ms.openlocfilehash: b7203dc042c7207bca95cfd0372790bfe52e0226
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2019
ms.locfileid: "65645564"
---
# <a name="exception-types"></a><span data-ttu-id="2a9e2-103">例外の種類</span><span class="sxs-lookup"><span data-stu-id="2a9e2-103">Exception Types</span></span>

<span data-ttu-id="2a9e2-104">F# の例外の 2 つのカテゴリがあります: .NET 例外の種類と F# の例外の種類。</span><span class="sxs-lookup"><span data-stu-id="2a9e2-104">There are two categories of exceptions in F#: .NET exception types and F# exception types.</span></span> <span data-ttu-id="2a9e2-105">このトピックでは、定義して、F# の例外の種類を使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="2a9e2-105">This topic describes how to define and use F# exception types.</span></span>

## <a name="syntax"></a><span data-ttu-id="2a9e2-106">構文</span><span class="sxs-lookup"><span data-stu-id="2a9e2-106">Syntax</span></span>

```fsharp
exception exception-type of argument-type
```

## <a name="remarks"></a><span data-ttu-id="2a9e2-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="2a9e2-107">Remarks</span></span>

<span data-ttu-id="2a9e2-108">前の構文で*例外型*新しい F# の例外型の名前を指定および*引数の型*この種類の例外が発生するときに指定できる引数の型を表します。</span><span class="sxs-lookup"><span data-stu-id="2a9e2-108">In the previous syntax, *exception-type* is the name of a new F# exception type, and *argument-type* represents the type of an argument that can be supplied when you raise an exception of this type.</span></span> <span data-ttu-id="2a9e2-109">タプル型を使用して複数の引数を指定することができます*引数型*します。</span><span class="sxs-lookup"><span data-stu-id="2a9e2-109">You can specify multiple arguments by using a tuple type for *argument-type*.</span></span>

<span data-ttu-id="2a9e2-110">一般的な定義、F#例外、次のようです。</span><span class="sxs-lookup"><span data-stu-id="2a9e2-110">A typical definition for an F# exception resembles the following.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5501.fs)]

<span data-ttu-id="2a9e2-111">使用してこの型の例外を生成することができます、`raise`関数は、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="2a9e2-111">You can generate an exception of this type by using the `raise` function, as follows.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5502.fs)]

<span data-ttu-id="2a9e2-112">使用することができます、F#例外の種類でフィルター内で直接、`try...with`式は、次の例に示すようにします。</span><span class="sxs-lookup"><span data-stu-id="2a9e2-112">You can use an F# exception type directly in the filters in a `try...with` expression, as shown in the following example.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5503.fs)]

<span data-ttu-id="2a9e2-113">例外の種類で定義された、 `exception` F# でのキーワードはから継承する新しい型`System.Exception`します。</span><span class="sxs-lookup"><span data-stu-id="2a9e2-113">The exception type that you define with the `exception` keyword in F# is a new type that inherits from `System.Exception`.</span></span>

## <a name="see-also"></a><span data-ttu-id="2a9e2-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="2a9e2-114">See also</span></span>

- [<span data-ttu-id="2a9e2-115">例外処理</span><span class="sxs-lookup"><span data-stu-id="2a9e2-115">Exception Handling</span></span>](index.md)
- [<span data-ttu-id="2a9e2-116">例外: `raise` 関数</span><span class="sxs-lookup"><span data-stu-id="2a9e2-116">Exceptions: the `raise` Function</span></span>](the-raise-function.md)
- [<span data-ttu-id="2a9e2-117">例外階層</span><span class="sxs-lookup"><span data-stu-id="2a9e2-117">Exception Hierarchy</span></span>](https://msdn.microsoft.com/library/z4c5tckx.aspx)
