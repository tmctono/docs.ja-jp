---
title: '例外: raise 関数'
description: エラーまたは例外条件が発生したことを示す F# の 'raise' 関数を使用する方法について説明します。
ms.date: 05/16/2016
ms.openlocfilehash: e0cc8da8310203c537b8081af8a225671bd8c6a3
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630290"
---
# <a name="exceptions-the-raise-function"></a><span data-ttu-id="d74e0-103">例外: raise 関数</span><span class="sxs-lookup"><span data-stu-id="d74e0-103">Exceptions: the raise Function</span></span>

<span data-ttu-id="d74e0-104">関数`raise`は、エラーまたは例外的な条件が発生したことを示すために使用されます。</span><span class="sxs-lookup"><span data-stu-id="d74e0-104">The `raise` function is used to indicate that an error or exceptional condition has occurred.</span></span> <span data-ttu-id="d74e0-105">エラーに関する情報は、例外オブジェクトでキャプチャされます。</span><span class="sxs-lookup"><span data-stu-id="d74e0-105">Information about the error is captured in an exception object.</span></span>

## <a name="syntax"></a><span data-ttu-id="d74e0-106">構文</span><span class="sxs-lookup"><span data-stu-id="d74e0-106">Syntax</span></span>

```fsharp
raise (expression)
```

## <a name="remarks"></a><span data-ttu-id="d74e0-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="d74e0-107">Remarks</span></span>

<span data-ttu-id="d74e0-108">関数`raise`は、例外オブジェクトを生成し、スタックアンワインドプロセスを開始します。</span><span class="sxs-lookup"><span data-stu-id="d74e0-108">The `raise` function generates an exception object and initiates a stack unwinding process.</span></span> <span data-ttu-id="d74e0-109">スタックアンワインドプロセスは共通言語ランタイム (CLR) によって管理されているため、このプロセスの動作は、他の .NET 言語と同じになります。</span><span class="sxs-lookup"><span data-stu-id="d74e0-109">The stack unwinding process is managed by the common language runtime (CLR), so the behavior of this process is the same as it is in any other .NET language.</span></span> <span data-ttu-id="d74e0-110">スタックアンワインドプロセスは、生成された例外に一致する例外ハンドラーを検索します。</span><span class="sxs-lookup"><span data-stu-id="d74e0-110">The stack unwinding process is a search for an exception handler that matches the generated exception.</span></span> <span data-ttu-id="d74e0-111">現在`try...with`の式 (存在する場合) で検索が開始されます。</span><span class="sxs-lookup"><span data-stu-id="d74e0-111">The search starts in the current `try...with` expression, if there is one.</span></span> <span data-ttu-id="d74e0-112">`with`ブロック内の各パターンは順番にチェックされます。</span><span class="sxs-lookup"><span data-stu-id="d74e0-112">Each pattern in the `with` block is checked, in order.</span></span> <span data-ttu-id="d74e0-113">一致する例外ハンドラーが見つかった場合、例外は処理されたと見なされます。それ以外の場合は、スタック`with`がアンワインドされ、一致するハンドラーが見つかるまで呼び出しチェーンのブロックアップがチェックされます。</span><span class="sxs-lookup"><span data-stu-id="d74e0-113">When a matching exception handler is found, the exception is considered handled; otherwise, the stack is unwound and `with` blocks up the call chain are checked until a matching handler is found.</span></span> <span data-ttu-id="d74e0-114">呼び出し`finally`チェーンで検出されたすべてのブロックも、スタックのアンワインドとして順番に実行されます。</span><span class="sxs-lookup"><span data-stu-id="d74e0-114">Any `finally` blocks that are encountered in the call chain are also executed in sequence as the stack unwinds.</span></span>

<span data-ttu-id="d74e0-115">関数は、 C#またC++はの`throw`と同じです。 `raise`</span><span class="sxs-lookup"><span data-stu-id="d74e0-115">The `raise` function is the equivalent of `throw` in C# or C++.</span></span> <span data-ttu-id="d74e0-116">Catch `reraise`ハンドラーでを使用して、同じ例外を呼び出しチェーンの上位に伝達します。</span><span class="sxs-lookup"><span data-stu-id="d74e0-116">Use `reraise` in a catch handler to propagate the same exception up the call chain.</span></span>

<span data-ttu-id="d74e0-117">次のコード例は、 `raise`関数を使用して例外を生成する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="d74e0-117">The following code examples illustrate the use of the `raise` function to generate an exception.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5801.fs)]

<span data-ttu-id="d74e0-118">関数`raise`は、次の例に示すように、.net の例外を発生させるためにも使用できます。</span><span class="sxs-lookup"><span data-stu-id="d74e0-118">The `raise` function can also be used to raise .NET exceptions, as shown in the following example.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5802.fs)]

## <a name="see-also"></a><span data-ttu-id="d74e0-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="d74e0-119">See also</span></span>

- [<span data-ttu-id="d74e0-120">例外処理</span><span class="sxs-lookup"><span data-stu-id="d74e0-120">Exception Handling</span></span>](index.md)
- [<span data-ttu-id="d74e0-121">例外の種類</span><span class="sxs-lookup"><span data-stu-id="d74e0-121">Exception Types</span></span>](exception-types.md)
- [<span data-ttu-id="d74e0-122">例外: `try...with`式</span><span class="sxs-lookup"><span data-stu-id="d74e0-122">Exceptions: The `try...with` Expression</span></span>](the-try-with-expression.md)
- [<span data-ttu-id="d74e0-123">例外: `try...finally`式</span><span class="sxs-lookup"><span data-stu-id="d74e0-123">Exceptions: The `try...finally` Expression</span></span>](the-try-finally-expression.md)
- [<span data-ttu-id="d74e0-124">例外: `failwith`関数</span><span class="sxs-lookup"><span data-stu-id="d74e0-124">Exceptions: The `failwith` Function</span></span>](the-failwith-function.md)
- [<span data-ttu-id="d74e0-125">例外: `invalidArg`関数</span><span class="sxs-lookup"><span data-stu-id="d74e0-125">Exceptions: The `invalidArg` Function</span></span>](the-invalidArg-function.md)
