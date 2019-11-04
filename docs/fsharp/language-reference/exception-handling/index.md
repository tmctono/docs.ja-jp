---
title: 例外処理
description: のF#例外処理の基本について説明し、例外処理式および関数へのリンクを紹介します。
ms.date: 05/16/2016
ms.openlocfilehash: e34a65dd7da9d706153254ac28e729de0745e4d0
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/01/2019
ms.locfileid: "73423065"
---
# <a name="exception-handling"></a><span data-ttu-id="16c86-103">例外処理</span><span class="sxs-lookup"><span data-stu-id="16c86-103">Exception Handling</span></span>

<span data-ttu-id="16c86-104">このセクションでは、F# 言語での例外処理のサポートについて説明します。</span><span class="sxs-lookup"><span data-stu-id="16c86-104">This section contains information about exception handling support in the F# language.</span></span>

## <a name="exception-handling-basics"></a><span data-ttu-id="16c86-105">例外処理の基礎</span><span class="sxs-lookup"><span data-stu-id="16c86-105">Exception Handling Basics</span></span>

<span data-ttu-id="16c86-106">例外処理は、.NET Framework においてエラー条件を処理するための標準的な方法です。</span><span class="sxs-lookup"><span data-stu-id="16c86-106">Exception handling is the standard way of handling error conditions in the .NET Framework.</span></span> <span data-ttu-id="16c86-107">したがって、F# を含むすべての .NET 言語でこのメカニズムがサポートされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="16c86-107">Thus, any .NET language must support this mechanism, including F#.</span></span> <span data-ttu-id="16c86-108">*例外*は、エラーに関する情報をカプセル化するオブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="16c86-108">An *exception* is an object that encapsulates information about an error.</span></span> <span data-ttu-id="16c86-109">エラーが発生すると、例外が生成され、通常の実行が停止します。</span><span class="sxs-lookup"><span data-stu-id="16c86-109">When errors occur, exceptions are raised and regular execution stops.</span></span> <span data-ttu-id="16c86-110">代わりに、ランタイムによって適切な例外ハンドラーが検索されます。</span><span class="sxs-lookup"><span data-stu-id="16c86-110">Instead, the runtime searches for an appropriate handler for the exception.</span></span> <span data-ttu-id="16c86-111">検索は、現在の関数で開始され、一致するハンドラーが見つかるまで、呼び出し元のレイヤーのスタックを上位に向かって検索します。</span><span class="sxs-lookup"><span data-stu-id="16c86-111">The search starts in the current function, and proceeds up the stack through the layers of callers until a matching handler is found.</span></span> <span data-ttu-id="16c86-112">見つかったハンドラーが実行されます。</span><span class="sxs-lookup"><span data-stu-id="16c86-112">Then the handler is executed.</span></span>

<span data-ttu-id="16c86-113">また、スタックはアンワインドされているため、ランタイムによって `finally` ブロック内のコードがすべて実行されます。これにより、アンワインド プロセスでオブジェクトが適切にクリーンアップされることが保証されます。</span><span class="sxs-lookup"><span data-stu-id="16c86-113">In addition, as the stack is unwound, the runtime executes any code in `finally` blocks, to guarantee that objects are cleaned up correctly during the unwinding process.</span></span>

## <a name="related-topics"></a><span data-ttu-id="16c86-114">関連トピック</span><span class="sxs-lookup"><span data-stu-id="16c86-114">Related Topics</span></span>

|<span data-ttu-id="16c86-115">Title</span><span class="sxs-lookup"><span data-stu-id="16c86-115">Title</span></span>|<span data-ttu-id="16c86-116">説明</span><span class="sxs-lookup"><span data-stu-id="16c86-116">Description</span></span>|
|-----|-----------|
|[<span data-ttu-id="16c86-117">例外の種類</span><span class="sxs-lookup"><span data-stu-id="16c86-117">Exception Types</span></span>](exception-types.md)|<span data-ttu-id="16c86-118">例外の種類を宣言する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="16c86-118">Describes how to declare an exception type.</span></span>|
|[<span data-ttu-id="16c86-119">例外: `try...with` 式</span><span class="sxs-lookup"><span data-stu-id="16c86-119">Exceptions: The `try...with` Expression</span></span>](the-try-with-expression.md)|<span data-ttu-id="16c86-120">例外処理をサポートする言語構成要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="16c86-120">Describes the language construct that supports exception handling.</span></span>|
|[<span data-ttu-id="16c86-121">例外: `try...finally` 式</span><span class="sxs-lookup"><span data-stu-id="16c86-121">Exceptions: The `try...finally` Expression</span></span>](the-try-finally-expression.md)|<span data-ttu-id="16c86-122">例外がスローされたときに、クリーンアップ コードをスタック アンワインドとして実行するための言語構成要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="16c86-122">Describes the language construct that enables you to execute clean-up code as the stack unwinds when an exception is thrown.</span></span>|
|[<span data-ttu-id="16c86-123">例外: `raise` 関数</span><span class="sxs-lookup"><span data-stu-id="16c86-123">Exceptions: the `raise` Function</span></span>](the-raise-Function.md)|<span data-ttu-id="16c86-124">例外オブジェクトをスローする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="16c86-124">Describes how to throw an exception object.</span></span>|
|[<span data-ttu-id="16c86-125">例外: `failwith` 関数</span><span class="sxs-lookup"><span data-stu-id="16c86-125">Exceptions: The `failwith` Function</span></span>](the-failwith-function.md)|<span data-ttu-id="16c86-126">F# の一般的な例外を生成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="16c86-126">Describes how to generate a general F# exception.</span></span>|
|[<span data-ttu-id="16c86-127">例外: `invalidArg` 関数</span><span class="sxs-lookup"><span data-stu-id="16c86-127">Exceptions: The `invalidArg` Function</span></span>](the-invalidArg-function.md)|<span data-ttu-id="16c86-128">無効な引数の例外を生成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="16c86-128">Describes how to generate an invalid argument exception.</span></span>|
