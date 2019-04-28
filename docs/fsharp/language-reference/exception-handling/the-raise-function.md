---
title: '例外: raise 関数'
description: エラーまたは例外条件が発生したことを示す F# の 'raise' 関数を使用する方法について説明します。
ms.date: 05/16/2016
ms.openlocfilehash: 87773ead7773c62a325c7e7ff105c729e10dd69c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61772672"
---
# <a name="exceptions-the-raise-function"></a><span data-ttu-id="99b89-103">例外: raise 関数</span><span class="sxs-lookup"><span data-stu-id="99b89-103">Exceptions: the raise Function</span></span>

<span data-ttu-id="99b89-104">`raise`関数は、エラーまたは例外条件が発生したことを示すために使用します。</span><span class="sxs-lookup"><span data-stu-id="99b89-104">The `raise` function is used to indicate that an error or exceptional condition has occurred.</span></span> <span data-ttu-id="99b89-105">エラーに関する情報は、例外オブジェクトでキャプチャされます。</span><span class="sxs-lookup"><span data-stu-id="99b89-105">Information about the error is captured in an exception object.</span></span>

## <a name="syntax"></a><span data-ttu-id="99b89-106">構文</span><span class="sxs-lookup"><span data-stu-id="99b89-106">Syntax</span></span>

```fsharp
raise (expression)
```

## <a name="remarks"></a><span data-ttu-id="99b89-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="99b89-107">Remarks</span></span>

<span data-ttu-id="99b89-108">`raise`関数は、例外オブジェクトを生成し、スタック アンワインド プロセスを開始します。</span><span class="sxs-lookup"><span data-stu-id="99b89-108">The `raise` function generates an exception object and initiates a stack unwinding process.</span></span> <span data-ttu-id="99b89-109">スタック アンワインド プロセスは、他の任意の .NET 言語ではこのプロセスの動作は同じように、共通言語ランタイム (CLR) によって管理されます。</span><span class="sxs-lookup"><span data-stu-id="99b89-109">The stack unwinding process is managed by the common language runtime (CLR), so the behavior of this process is the same as it is in any other .NET language.</span></span> <span data-ttu-id="99b89-110">スタックのアンワインド プロセスは、生成された例外に一致する例外ハンドラーの検索です。</span><span class="sxs-lookup"><span data-stu-id="99b89-110">The stack unwinding process is a search for an exception handler that matches the generated exception.</span></span> <span data-ttu-id="99b89-111">現在の検索を開始`try...with`式、1 つを使用する必要がある場合。</span><span class="sxs-lookup"><span data-stu-id="99b89-111">The search starts in the current `try...with` expression, if there is one.</span></span> <span data-ttu-id="99b89-112">各パターンで、`with`の順序で、ブロックをチェックします。</span><span class="sxs-lookup"><span data-stu-id="99b89-112">Each pattern in the `with` block is checked, in order.</span></span> <span data-ttu-id="99b89-113">一致する例外ハンドラーが見つかると、例外が処理済みと見なされますそれ以外の場合、スタックがアンワインドされますと`with`一致するハンドラーが見つかるまで呼び出しチェーンのブロックがチェックされます。</span><span class="sxs-lookup"><span data-stu-id="99b89-113">When a matching exception handler is found, the exception is considered handled; otherwise, the stack is unwound and `with` blocks up the call chain are checked until a matching handler is found.</span></span> <span data-ttu-id="99b89-114">すべて`finally`スタック アンワインドとして、呼び出しチェーンに含まれるブロックがシーケンスの実行もします。</span><span class="sxs-lookup"><span data-stu-id="99b89-114">Any `finally` blocks that are encountered in the call chain are also executed in sequence as the stack unwinds.</span></span>

<span data-ttu-id="99b89-115">`raise`関数と同等の`throw`c# または C++ でします。</span><span class="sxs-lookup"><span data-stu-id="99b89-115">The `raise` function is the equivalent of `throw` in C# or C++.</span></span> <span data-ttu-id="99b89-116">使用`reraise`を同じ例外呼び出しチェーンの上位に伝達する catch ハンドラーにします。</span><span class="sxs-lookup"><span data-stu-id="99b89-116">Use `reraise` in a catch handler to propagate the same exception up the call chain.</span></span>

<span data-ttu-id="99b89-117">次のコード例は、の使用を示しています、`raise`例外を生成する関数。</span><span class="sxs-lookup"><span data-stu-id="99b89-117">The following code examples illustrate the use of the `raise` function to generate an exception.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5801.fs)]

<span data-ttu-id="99b89-118">`raise`次の例に示すようにも、関数を使用、.NET 例外を発生させることができます。</span><span class="sxs-lookup"><span data-stu-id="99b89-118">The `raise` function can also be used to raise .NET exceptions, as shown in the following example.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5802.fs)]

## <a name="see-also"></a><span data-ttu-id="99b89-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="99b89-119">See also</span></span>

- [<span data-ttu-id="99b89-120">例外処理</span><span class="sxs-lookup"><span data-stu-id="99b89-120">Exception Handling</span></span>](index.md)
- [<span data-ttu-id="99b89-121">例外の種類</span><span class="sxs-lookup"><span data-stu-id="99b89-121">Exception Types</span></span>](exception-types.md)
- [<span data-ttu-id="99b89-122">例外: `try...with`式</span><span class="sxs-lookup"><span data-stu-id="99b89-122">Exceptions: The `try...with` Expression</span></span>](the-try-with-expression.md)
- [<span data-ttu-id="99b89-123">例外: `try...finally`式</span><span class="sxs-lookup"><span data-stu-id="99b89-123">Exceptions: The `try...finally` Expression</span></span>](the-try-finally-expression.md)
- [<span data-ttu-id="99b89-124">例外: `failwith`関数</span><span class="sxs-lookup"><span data-stu-id="99b89-124">Exceptions: The `failwith` Function</span></span>](the-failwith-function.md)
- [<span data-ttu-id="99b89-125">例外: `invalidArg`関数</span><span class="sxs-lookup"><span data-stu-id="99b89-125">Exceptions: The `invalidArg` Function</span></span>](the-invalidArg-function.md)