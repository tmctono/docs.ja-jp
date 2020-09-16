---
title: 例外の種類
description: 'F # の例外の種類を定義して使用する方法について説明します。'
ms.date: 05/16/2016
ms.openlocfilehash: 8b4ceec31a2d68abbcd025812ffeeefc0c090efb
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/15/2020
ms.locfileid: "90557230"
---
# <a name="exception-types"></a><span data-ttu-id="6f75e-103">例外の種類</span><span class="sxs-lookup"><span data-stu-id="6f75e-103">Exception Types</span></span>

<span data-ttu-id="6f75e-104">F # には、.NET の例外の種類と F # の例外の種類という2つのカテゴリがあります。</span><span class="sxs-lookup"><span data-stu-id="6f75e-104">There are two categories of exceptions in F#: .NET exception types and F# exception types.</span></span> <span data-ttu-id="6f75e-105">このトピックでは、F # の例外の種類を定義して使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="6f75e-105">This topic describes how to define and use F# exception types.</span></span>

## <a name="syntax"></a><span data-ttu-id="6f75e-106">構文</span><span class="sxs-lookup"><span data-stu-id="6f75e-106">Syntax</span></span>

```fsharp
exception exception-type of argument-type
```

## <a name="remarks"></a><span data-ttu-id="6f75e-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="6f75e-107">Remarks</span></span>

<span data-ttu-id="6f75e-108">前の構文では、 *例外の種類* は新しい F # の例外の種類の名前で、引数の *型* は、この型の例外を発生させたときに指定できる引数の型を表します。</span><span class="sxs-lookup"><span data-stu-id="6f75e-108">In the previous syntax, *exception-type* is the name of a new F# exception type, and *argument-type* represents the type of an argument that can be supplied when you raise an exception of this type.</span></span> <span data-ttu-id="6f75e-109">*引数の型*にタプル型を使用すると、複数の引数を指定できます。</span><span class="sxs-lookup"><span data-stu-id="6f75e-109">You can specify multiple arguments by using a tuple type for *argument-type*.</span></span>

<span data-ttu-id="6f75e-110">F # 例外の一般的な定義は、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="6f75e-110">A typical definition for an F# exception resembles the following.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5501.fs)]

<span data-ttu-id="6f75e-111">この型の例外を生成するには、次のように関数を使用し `raise` ます。</span><span class="sxs-lookup"><span data-stu-id="6f75e-111">You can generate an exception of this type by using the `raise` function, as follows.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5502.fs)]

<span data-ttu-id="6f75e-112">次の例に示すように、式のフィルターで F # の例外の種類を直接使用でき `try...with` ます。</span><span class="sxs-lookup"><span data-stu-id="6f75e-112">You can use an F# exception type directly in the filters in a `try...with` expression, as shown in the following example.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5503.fs)]

<span data-ttu-id="6f75e-113">F # でキーワードを使用して定義する例外の種類 `exception` は、から継承される新しい型です `System.Exception` 。</span><span class="sxs-lookup"><span data-stu-id="6f75e-113">The exception type that you define with the `exception` keyword in F# is a new type that inherits from `System.Exception`.</span></span>

## <a name="see-also"></a><span data-ttu-id="6f75e-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="6f75e-114">See also</span></span>

- [<span data-ttu-id="6f75e-115">例外処理</span><span class="sxs-lookup"><span data-stu-id="6f75e-115">Exception Handling</span></span>](index.md)
- [<span data-ttu-id="6f75e-116">例外: `raise` 関数</span><span class="sxs-lookup"><span data-stu-id="6f75e-116">Exceptions: the `raise` Function</span></span>](the-raise-function.md)
- [<span data-ttu-id="6f75e-117">例外階層</span><span class="sxs-lookup"><span data-stu-id="6f75e-117">Exception Hierarchy</span></span>](../../../standard/exceptions/index.md)
