---
title: 例外の使用 - C# プログラミング ガイド
description: 例外を使用する方法について説明します。 例外は、エラーが発生したコードによってスローされ、エラーを修正するコードによってキャッチされます。
ms.date: 07/20/2015
helpviewer_keywords:
- exception handling [C#], about exception handling
- exceptions [C#], about exceptions
ms.assetid: 71472c62-320a-470a-97d2-67995180389d
ms.openlocfilehash: fb45381f1c6cfa2f27d036ead8e662b7a0d8d924
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/28/2020
ms.locfileid: "87303375"
---
# <a name="use-exceptions-c-programming-guide"></a><span data-ttu-id="3eed6-104">例外の使用 (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="3eed6-104">Use exceptions (C# programming guide)</span></span>

<span data-ttu-id="3eed6-105">C# では、例外と呼ばれるメカニズムを使用して、プログラムの実行時に発生したエラーがプログラムに伝えられます。</span><span class="sxs-lookup"><span data-stu-id="3eed6-105">In C#, errors in the program at run time are propagated through the program by using a mechanism called exceptions.</span></span> <span data-ttu-id="3eed6-106">例外は、エラーが発生したコードによってスローされ、エラーを修正できるコードによってキャッチされます。</span><span class="sxs-lookup"><span data-stu-id="3eed6-106">Exceptions are thrown by code that encounters an error and caught by code that can correct the error.</span></span> <span data-ttu-id="3eed6-107">例外をスローできるのは、.NET ランタイム、またはプログラム内のコードです。</span><span class="sxs-lookup"><span data-stu-id="3eed6-107">Exceptions can be thrown by the .NET runtime or by code in a program.</span></span> <span data-ttu-id="3eed6-108">スローされた例外は、例外の `catch` ステートメントが見つかるまで呼び出し履歴をさかのぼります。</span><span class="sxs-lookup"><span data-stu-id="3eed6-108">Once an exception is thrown, it propagates up the call stack until a `catch` statement for the exception is found.</span></span> <span data-ttu-id="3eed6-109">キャッチされない例外は、システムが提供する汎用の例外ハンドラーによって処理されます。このとき、ダイアログ ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="3eed6-109">Uncaught exceptions are handled by a generic exception handler provided by the system that displays a dialog box.</span></span>  
  
 <span data-ttu-id="3eed6-110">例外は、<xref:System.Exception> から派生したクラスによって表されます。</span><span class="sxs-lookup"><span data-stu-id="3eed6-110">Exceptions are represented by classes derived from <xref:System.Exception>.</span></span> <span data-ttu-id="3eed6-111">このクラスは例外の型を識別し、例外に関する詳細情報が含まれたプロパティを保持します。</span><span class="sxs-lookup"><span data-stu-id="3eed6-111">This class identifies the type of exception and contains properties that have details about the exception.</span></span> <span data-ttu-id="3eed6-112">例外をスローするには、例外の派生クラスのインスタンスを作成し、必要に応じて例外のプロパティを設定してから、`throw` キーワードを使用してオブジェクトをスローする必要があります。</span><span class="sxs-lookup"><span data-stu-id="3eed6-112">Throwing an exception involves creating an instance of an exception-derived class, optionally configuring properties of the exception, and then throwing the object by using the `throw` keyword.</span></span> <span data-ttu-id="3eed6-113">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="3eed6-113">For example:</span></span>  
  
 [!code-csharp[csProgGuideExceptions#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideExceptions/CS/Exceptions.cs#1)]  
  
 <span data-ttu-id="3eed6-114">例外がスローされると、ランタイムは、現在のステートメントが `try` ブロック内に存在するかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="3eed6-114">After an exception is thrown, the runtime checks the current statement to see whether it is within a `try` block.</span></span> <span data-ttu-id="3eed6-115">存在する場合は、`try` ブロックに関連付けられている `catch` ブロックをチェックして、例外をキャッチできるかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="3eed6-115">If it is, any `catch` blocks associated with the `try` block are checked to see whether they can catch the exception.</span></span> <span data-ttu-id="3eed6-116">通常は、この `Catch` ブロックによって例外の型が指定されます。`catch` ブロックの型が、例外または例外の基底クラスの型と一致する場合、`catch` ブロックはメソッドを処理できます。</span><span class="sxs-lookup"><span data-stu-id="3eed6-116">`Catch` blocks typically specify exception types; if the type of the `catch` block is the same type as the exception, or a base class of the exception, the `catch` block can handle the method.</span></span> <span data-ttu-id="3eed6-117">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="3eed6-117">For example:</span></span>  
  
 [!code-csharp[csProgGuideExceptions#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideExceptions/CS/Exceptions.cs#2)]  
  
 <span data-ttu-id="3eed6-118">例外をスローするステートメントが `try` ブロックにない場合、または `try` ブロックにそのステートメントが含まれていても、対応する `catch` ブロックが存在しない場合は、ランタイムが呼び出し側のメソッドで `try` ステートメントと `catch` ブロックを探します。</span><span class="sxs-lookup"><span data-stu-id="3eed6-118">If the statement that throws an exception is not within a `try` block or if the `try` block that encloses it has no matching `catch` block, the runtime checks the calling method for a `try` statement and `catch` blocks.</span></span> <span data-ttu-id="3eed6-119">続けて、呼び出し履歴で、対応する `catch` ブロックを探します。</span><span class="sxs-lookup"><span data-stu-id="3eed6-119">The runtime continues up the calling stack, searching for a compatible `catch` block.</span></span> <span data-ttu-id="3eed6-120">`catch` ブロックが見つかり実行されると、その `catch` ブロックの後にある次のステートメントに制御が渡されます。</span><span class="sxs-lookup"><span data-stu-id="3eed6-120">After the `catch` block is found and executed, control is passed to the next statement after that `catch` block.</span></span>  
  
 <span data-ttu-id="3eed6-121">`try` ステートメントには、複数の `catch` ブロックを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="3eed6-121">A `try` statement can contain more than one `catch` block.</span></span> <span data-ttu-id="3eed6-122">例外を処理できる最初の `catch` ステートメントが実行され、その後の `catch` ステートメントは、対応していても無視されます。</span><span class="sxs-lookup"><span data-stu-id="3eed6-122">The first `catch` statement that can handle the exception is executed; any following `catch` statements, even if they are compatible, are ignored.</span></span> <span data-ttu-id="3eed6-123">そのため、catch ブロックは必ず特殊性が高いもの (または最も派生されたもの) から順に配置する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3eed6-123">Therefore, catch blocks should always be ordered from most specific (or most-derived) to least specific.</span></span> <span data-ttu-id="3eed6-124">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="3eed6-124">For example:</span></span>  
  
 [!code-csharp[csProgGuideExceptions#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideExceptions/CS/Exceptions.cs#3)]  
  
 <span data-ttu-id="3eed6-125">`catch` ブロックが実行される前に、ランタイムにより `finally` ブロックがチェックされます。</span><span class="sxs-lookup"><span data-stu-id="3eed6-125">Before the `catch` block is executed, the runtime checks for `finally` blocks.</span></span> <span data-ttu-id="3eed6-126">`Finally` ブロックを使用すると、中止された `try` ブロックによって残ることがある、あいまいな状態をクリーンアップできます。また、ランタイムのガベージ コレクターがオブジェクトを終了させるのを待たずに外部リソース (グラフィック ハンドル、データベース接続、ファイル ストリームなど) を解放することもできます。</span><span class="sxs-lookup"><span data-stu-id="3eed6-126">`Finally` blocks enable the programmer to clean up any ambiguous state that could be left over from an aborted `try` block, or to release any external resources (such as graphics handles, database connections or file streams) without waiting for the garbage collector in the runtime to finalize the objects.</span></span> <span data-ttu-id="3eed6-127">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="3eed6-127">For example:</span></span>  
  
 [!code-csharp[csProgGuideExceptions#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideExceptions/CS/Exceptions.cs#4)]  
  
 <span data-ttu-id="3eed6-128">`WriteByte()` が例外をスローした場合は、`file.Close()` を呼び出さないと、ファイルを再度開こうとする 2 番目の `try` ブロックのコードが失敗し、ファイルはロックされたままになります。</span><span class="sxs-lookup"><span data-stu-id="3eed6-128">If `WriteByte()` threw an exception, the code in the second `try` block that tries to reopen the file would fail if `file.Close()` is not called, and the file would remain locked.</span></span> <span data-ttu-id="3eed6-129">例外がスローされても `finally` ブロックは実行されるため、上の例の `finally` ブロックではファイルを適切に閉じて、エラーを回避できます。</span><span class="sxs-lookup"><span data-stu-id="3eed6-129">Because `finally` blocks are executed even if an exception is thrown, the `finally` block in the previous example allows for the file to be closed correctly and helps avoid an error.</span></span>  
  
 <span data-ttu-id="3eed6-130">例外がスローされた後、対応する `catch` ブロックが呼び出し履歴に見つからない場合は、次のいずれかが発生します。</span><span class="sxs-lookup"><span data-stu-id="3eed6-130">If no compatible `catch` block is found on the call stack after an exception is thrown, one of three things occurs:</span></span>  
  
- <span data-ttu-id="3eed6-131">例外がファイナライザーの内部で発生した場合、ファイナライザーは中止され、基本ファイナライザー (存在する場合) が呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="3eed6-131">If the exception is within a finalizer, the finalizer is aborted and the base finalizer, if any, is called.</span></span>  
  
- <span data-ttu-id="3eed6-132">呼び出し履歴に静的コンストラクターまたは静的フィールド初期化子が含まれている場合は、<xref:System.TypeInitializationException> がスローされ、新しい例外の <xref:System.Exception.InnerException%2A> プロパティに元の例外が割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="3eed6-132">If the call stack contains a static constructor, or a static field initializer, a <xref:System.TypeInitializationException> is thrown, with the original exception assigned to the <xref:System.Exception.InnerException%2A> property of the new exception.</span></span>  
  
- <span data-ttu-id="3eed6-133">スレッドの開始位置に到達すると、スレッドは終了します。</span><span class="sxs-lookup"><span data-stu-id="3eed6-133">If the start of the thread is reached, the thread is terminated.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3eed6-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="3eed6-134">See also</span></span>

- [<span data-ttu-id="3eed6-135">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="3eed6-135">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="3eed6-136">例外と例外処理</span><span class="sxs-lookup"><span data-stu-id="3eed6-136">Exceptions and Exception Handling</span></span>](./index.md)
