---
title: 例外処理 - C# プログラミング ガイド
description: 例外処理について説明します。 try-catch、try-finally、および try-catch-finally ステートメントの例を確認してください。
ms.date: 07/20/2015
helpviewer_keywords:
- exception handling [C#], about exception handling
- exceptions [C#], handling
ms.assetid: b4e4ecf2-b907-4e58-891f-2563762258e9
ms.openlocfilehash: 8e55b44573c40f594e567fc5a4501689e66c7af4
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/28/2020
ms.locfileid: "87302036"
---
# <a name="exception-handling-c-programming-guide"></a><span data-ttu-id="61d57-104">例外処理 (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="61d57-104">Exception Handling (C# Programming Guide)</span></span>
<span data-ttu-id="61d57-105">[try](../../language-reference/keywords/try-catch.md) ブロックは、例外の影響を受ける可能性があるコードを区分化するために、 C# プログラマによって使用されます。</span><span class="sxs-lookup"><span data-stu-id="61d57-105">A [try](../../language-reference/keywords/try-catch.md) block is used by C# programmers to partition code that might be affected by an exception.</span></span> <span data-ttu-id="61d57-106">関連付けられた [catch](../../language-reference/keywords/try-catch.md) ブロックは、スローされた例外を処理するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="61d57-106">Associated [catch](../../language-reference/keywords/try-catch.md) blocks are used to handle any resulting exceptions.</span></span> <span data-ttu-id="61d57-107">[finally](../../language-reference/keywords/try-finally.md) ブロックには、`try` ブロックで例外がスローされたかどうかにかかわらず実行されるコードが記述されます (`try` ブロックに割り当てられたリソースの解放など)。</span><span class="sxs-lookup"><span data-stu-id="61d57-107">A [finally](../../language-reference/keywords/try-finally.md) block contains code that is run regardless of whether or not an exception is thrown in the `try` block, such as releasing resources that are allocated in the `try` block.</span></span> <span data-ttu-id="61d57-108">`try` ブロックには、1 つ以上の `catch` ブロック、`finally` ブロック、またはその両方が関連付けられる必要があります。</span><span class="sxs-lookup"><span data-stu-id="61d57-108">A `try` block requires one or more associated `catch` blocks, or a `finally` block, or both.</span></span>  
  
 <span data-ttu-id="61d57-109">次のコードは、`try-catch` ステートメント、`try-finally` ステートメント、および `try-catch-finally` ステートメントの例です。</span><span class="sxs-lookup"><span data-stu-id="61d57-109">The following examples show a `try-catch` statement, a `try-finally` statement, and a `try-catch-finally` statement.</span></span>  
  
 [!code-csharp[csProgGuideExceptions#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideExceptions/CS/Exceptions.cs#6)]  
  
 [!code-csharp[csProgGuideExceptions#7](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideExceptions/CS/Exceptions.cs#7)]  
  
 [!code-csharp[csProgGuideExceptions#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideExceptions/CS/Exceptions.cs#8)]  
  
 <span data-ttu-id="61d57-110">`try` ブロックに `catch` または `finally` ブロックがない場合は、コンパイル エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="61d57-110">A `try` block without a `catch` or `finally` block causes a compiler error.</span></span>  
  
## <a name="catch-blocks"></a><span data-ttu-id="61d57-111">catch ブロック</span><span class="sxs-lookup"><span data-stu-id="61d57-111">Catch Blocks</span></span>  
 <span data-ttu-id="61d57-112">`catch` ブロックでは、キャッチする例外の種類を指定できます。</span><span class="sxs-lookup"><span data-stu-id="61d57-112">A `catch` block can specify the type of exception to catch.</span></span> <span data-ttu-id="61d57-113">この型指定は、*例外フィルター*と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="61d57-113">The type specification is called an *exception filter*.</span></span> <span data-ttu-id="61d57-114">例外の種類は、<xref:System.Exception> から派生している必要があります。</span><span class="sxs-lookup"><span data-stu-id="61d57-114">The exception type should be derived from <xref:System.Exception>.</span></span> <span data-ttu-id="61d57-115">一般に、`try` ブロックでスローされる可能性があるすべての例外の処理方法を把握している場合や、`catch` ブロックの末尾に [throw](../../language-reference/keywords/throw.md) ステートメントを記述している場合を除いては、例外フィルターとして <xref:System.Exception> を指定することは避けてください。</span><span class="sxs-lookup"><span data-stu-id="61d57-115">In general, do not specify <xref:System.Exception> as the exception filter unless either you know how to handle all exceptions that might be thrown in the `try` block, or you have included a [throw](../../language-reference/keywords/throw.md) statement at the end of your `catch` block.</span></span>  
  
 <span data-ttu-id="61d57-116">複数の `catch` ブロックに異なる例外フィルターが含まれている場合は、それらを連結することができます。</span><span class="sxs-lookup"><span data-stu-id="61d57-116">Multiple `catch` blocks with different exception filters can be chained together.</span></span> <span data-ttu-id="61d57-117">`catch` ブロックはコード内で上から下に評価されますが、スローされた各例外に対して実行される `catch` ブロックは 1 つだけです。</span><span class="sxs-lookup"><span data-stu-id="61d57-117">The `catch` blocks are evaluated from top to bottom in your code, but only one `catch` block is executed for each exception that is thrown.</span></span> <span data-ttu-id="61d57-118">スローされた例外の厳密な型か、その基底クラスを指定する最初の `catch` ブロックが実行されます。</span><span class="sxs-lookup"><span data-stu-id="61d57-118">The first `catch` block that specifies the exact type or a base class of the thrown exception is executed.</span></span> <span data-ttu-id="61d57-119">一致する例外フィルターを指定した `catch` ブロックがない場合は、フィルターのない `catch` ブロックが選択されます (それがステートメント内に存在する場合)。</span><span class="sxs-lookup"><span data-stu-id="61d57-119">If no `catch` block specifies a matching exception filter, a `catch` block that does not have a filter is selected, if one is present in the statement.</span></span> <span data-ttu-id="61d57-120">最初に配置する `catch` ブロックでは、最も具体的な (つまり、最終派生の) 例外の種類を指定することが重要です。</span><span class="sxs-lookup"><span data-stu-id="61d57-120">It is important to position `catch` blocks with the most specific (that is, the most derived) exception types first.</span></span>  
  
 <span data-ttu-id="61d57-121">次の条件に該当する場合は、例外をキャッチする必要があります。</span><span class="sxs-lookup"><span data-stu-id="61d57-121">You should catch exceptions when the following conditions are true:</span></span>  
  
- <span data-ttu-id="61d57-122">例外がスローされる理由を十分に理解していて、かつ特定の回復手段を実装できる (<xref:System.IO.FileNotFoundException> オブジェクトをキャッチした場合に、ユーザーに新しいファイル名を入力するよう求めるなど)。</span><span class="sxs-lookup"><span data-stu-id="61d57-122">You have a good understanding of why the exception might be thrown, and you can implement a specific recovery, such as prompting the user to enter a new file name when you catch a <xref:System.IO.FileNotFoundException> object.</span></span>  
  
- <span data-ttu-id="61d57-123">より具体的な例外を新規に作成し、スローできる。</span><span class="sxs-lookup"><span data-stu-id="61d57-123">You can create and throw a new, more specific exception.</span></span>  
  
     [!code-csharp[csProgGuideExceptions#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideExceptions/CS/Exceptions.cs#9)]  
  
- <span data-ttu-id="61d57-124">例外を追加処理に渡す前に、その例外を部分的に処理する必要がある。</span><span class="sxs-lookup"><span data-stu-id="61d57-124">You want to partially handle an exception before passing it on for additional handling.</span></span> <span data-ttu-id="61d57-125">次の例では、例外を再スローする前に、エラー ログにエントリを追加する目的で `catch` ブロックが使用されています。</span><span class="sxs-lookup"><span data-stu-id="61d57-125">In the following example, a `catch` block is used to add an entry to an error log before re-throwing the exception.</span></span>  
  
     [!code-csharp[csProgGuideExceptions#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideExceptions/CS/Exceptions.cs#10)]  
  
## <a name="finally-blocks"></a><span data-ttu-id="61d57-126">Finally ブロック</span><span class="sxs-lookup"><span data-stu-id="61d57-126">Finally Blocks</span></span>  
 <span data-ttu-id="61d57-127">`finally` ブロックでは、`try` ブロックで実行されるアクションをクリーンアップすることができます。</span><span class="sxs-lookup"><span data-stu-id="61d57-127">A `finally` block enables you to clean up actions that are performed in a `try` block.</span></span> <span data-ttu-id="61d57-128">`finally` ブロック (存在する場合) は、最後 (`try` ブロックおよび一致する `catch` ブロックの後) に実行されます。</span><span class="sxs-lookup"><span data-stu-id="61d57-128">If present, the `finally` block executes last, after the `try` block and any matched `catch` block.</span></span> <span data-ttu-id="61d57-129">`finally` ブロックは、例外がスローされたかどうかや、例外の種類に一致する `catch` ブロックが見つかったかどうかにかかわらず、常に実行されます。</span><span class="sxs-lookup"><span data-stu-id="61d57-129">A `finally` block always runs, regardless of whether an exception is thrown or a `catch` block matching the exception type is found.</span></span>  
  
 <span data-ttu-id="61d57-130">`finally` ブロックは、ランタイム内のガベージ コレクターによってオブジェクトがファイナライズされるのを待つことなく、ファイル ストリーム、データベース接続、グラフィックス ハンドルなどのリソースを解放するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="61d57-130">The `finally` block can be used to release resources such as file streams, database connections, and graphics handles without waiting for the garbage collector in the runtime to finalize the objects.</span></span> <span data-ttu-id="61d57-131">詳しくは、「[using ステートメント](../../language-reference/keywords/using-statement.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="61d57-131">See [using Statement](../../language-reference/keywords/using-statement.md) for more information.</span></span>  
  
 <span data-ttu-id="61d57-132">次の例では、`try` ブロックで開かれたファイルを閉じるために `finally` ブロックが使用されています。</span><span class="sxs-lookup"><span data-stu-id="61d57-132">In the following example, the `finally` block is used to close a file that is opened in the `try` block.</span></span> <span data-ttu-id="61d57-133">ファイルを閉じる前に、ファイル ハンドルの状態が確認されています。</span><span class="sxs-lookup"><span data-stu-id="61d57-133">Notice that the state of the file handle is checked before the file is closed.</span></span> <span data-ttu-id="61d57-134">`try` ブロックがファイルを開けなかった場合は、ファイル ハンドルの値が `null` のままになり、`finally` ブロックはファイルを閉じようとしません。</span><span class="sxs-lookup"><span data-stu-id="61d57-134">If the `try` block cannot open the file, the file handle still has the value `null` and the `finally` block does not try to close it.</span></span> <span data-ttu-id="61d57-135">`try` ブロックでファイルが正常に開かれた場合は、開かれたファイルを `finally` ブロックが閉じます。</span><span class="sxs-lookup"><span data-stu-id="61d57-135">Alternatively, if the file is opened successfully in the `try` block, the `finally` block closes the open file.</span></span>  
  
 [!code-csharp[csProgGuideExceptions#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideExceptions/CS/Exceptions.cs#11)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="61d57-136">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="61d57-136">C# Language Specification</span></span>  

<span data-ttu-id="61d57-137">詳細については、「[C# 言語仕様](/dotnet/csharp/language-reference/language-specification/introduction)」の[例外](~/_csharplang/spec/exceptions.md)と [try ステートメント](~/_csharplang/spec/statements.md#the-try-statement)に関するセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="61d57-137">For more information, see [Exceptions](~/_csharplang/spec/exceptions.md) and [The try statement](~/_csharplang/spec/statements.md#the-try-statement) in the [C# Language Specification](/dotnet/csharp/language-reference/language-specification/introduction).</span></span> <span data-ttu-id="61d57-138">言語仕様は、C# の構文と使用法に関する信頼性のある情報源です。</span><span class="sxs-lookup"><span data-stu-id="61d57-138">The language specification is the definitive source for C# syntax and usage.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="61d57-139">関連項目</span><span class="sxs-lookup"><span data-stu-id="61d57-139">See also</span></span>

- [<span data-ttu-id="61d57-140">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="61d57-140">C# Reference</span></span>](../../language-reference/index.md)
- [<span data-ttu-id="61d57-141">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="61d57-141">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="61d57-142">例外と例外処理</span><span class="sxs-lookup"><span data-stu-id="61d57-142">Exceptions and Exception Handling</span></span>](./index.md)
- [<span data-ttu-id="61d57-143">try-catch</span><span class="sxs-lookup"><span data-stu-id="61d57-143">try-catch</span></span>](../../language-reference/keywords/try-catch.md)
- [<span data-ttu-id="61d57-144">try-finally</span><span class="sxs-lookup"><span data-stu-id="61d57-144">try-finally</span></span>](../../language-reference/keywords/try-finally.md)
- [<span data-ttu-id="61d57-145">try-catch-finally</span><span class="sxs-lookup"><span data-stu-id="61d57-145">try-catch-finally</span></span>](../../language-reference/keywords/try-catch-finally.md)
- [<span data-ttu-id="61d57-146">using ステートメント</span><span class="sxs-lookup"><span data-stu-id="61d57-146">using Statement</span></span>](../../language-reference/keywords/using-statement.md)
