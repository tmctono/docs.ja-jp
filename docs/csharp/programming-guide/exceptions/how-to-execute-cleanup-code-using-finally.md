---
title: finally を使用してクリーンアップ コードを実行する方法 - C# プログラミング ガイド
description: "'finally' ステートメントを使用してクリーンアップ コードを実行する方法について説明します。 finally ステートメントによって、オブジェクトの必要なクリーンアップが直ちに実行されます。"
ms.date: 07/20/2015
helpviewer_keywords:
- try/finally blocks [C#]
- exceptions [C#], try/finally block
- exception handling [C#], try/finally block
ms.assetid: 1b1e5aef-3f32-4a88-9d39-b5fffb33bdaf
ms.openlocfilehash: 148c1f9fba67659a07c667bb15619d6f3f7c3b2f
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/28/2020
ms.locfileid: "87302023"
---
# <a name="how-to-execute-cleanup-code-using-finally-c-programming-guide"></a><span data-ttu-id="b75ed-104">finally を使用してクリーンアップ コードを実行する方法 (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="b75ed-104">How to execute cleanup code using finally (C# Programming Guide)</span></span>
<span data-ttu-id="b75ed-105">`finally` ステートメントの目的は、例外がスローされた場合でも、オブジェクト (一般に外部リソースを保持しているオブジェクト) に対して必要なクリーンアップをすぐに実行できるようにすることです。</span><span class="sxs-lookup"><span data-stu-id="b75ed-105">The purpose of a `finally` statement is to ensure that the necessary cleanup of objects, usually objects that are holding external resources, occurs immediately, even if an exception is thrown.</span></span> <span data-ttu-id="b75ed-106">次のように、共通言語ランタイムによってオブジェクトがガベージ コレクションされるまで待機するのではなく、オブジェクトを使用した後すぐに <xref:System.IO.FileStream> で <xref:System.IO.Stream.Close%2A> を呼び出すというのも、このようなクリーンアップの一例です。</span><span class="sxs-lookup"><span data-stu-id="b75ed-106">One example of such cleanup is calling <xref:System.IO.Stream.Close%2A> on a <xref:System.IO.FileStream> immediately after use instead of waiting for the object to be garbage collected by the common language runtime, as follows:</span></span>  
  
 [!code-csharp[csProgGuideExceptions#16](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideExceptions/CS/Exceptions.cs#16)]  
  
## <a name="example"></a><span data-ttu-id="b75ed-107">例</span><span class="sxs-lookup"><span data-stu-id="b75ed-107">Example</span></span>  
 <span data-ttu-id="b75ed-108">上のコードを `try-catch-finally` ステートメントに変えるには、次のようにクリーンアップ コードを作業コードから切り離します。</span><span class="sxs-lookup"><span data-stu-id="b75ed-108">To turn the previous code into a `try-catch-finally` statement, the cleanup code is separated from the working code, as follows.</span></span>  
  
 [!code-csharp[csProgGuideExceptions#17](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideExceptions/CS/Exceptions.cs#17)]  
  
 <span data-ttu-id="b75ed-109">`try` ブロック内では `OpenWrite()` 呼び出しの前のどの時点でも例外が発生する可能性があります。また、`OpenWrite()` 呼び出し自体が失敗する可能性もあります。そのため、ファイルを閉じようとしたときに、そのファイルが開いているという保証はありません。</span><span class="sxs-lookup"><span data-stu-id="b75ed-109">Because an exception can occur at any time within the `try` block before the `OpenWrite()` call, or the `OpenWrite()` call itself could fail, we are not guaranteed that the file is open when we try to close it.</span></span> <span data-ttu-id="b75ed-110">`finally` ブロックでは、<xref:System.IO.Stream.Close%2A> メソッドを呼び出す前に、<xref:System.IO.FileStream> オブジェクトが `null` でないことを確認するチェックが追加されます。</span><span class="sxs-lookup"><span data-stu-id="b75ed-110">The `finally` block adds a check to make sure that the <xref:System.IO.FileStream> object is not `null` before you call the <xref:System.IO.Stream.Close%2A> method.</span></span> <span data-ttu-id="b75ed-111">この `null` チェックがないと、`finally` ブロックからその <xref:System.NullReferenceException> がスローされる可能性がありますが、`finally` ブロックにおける例外のスローはできるだけ回避する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b75ed-111">Without the `null` check, the `finally` block could throw its own <xref:System.NullReferenceException>, but throwing exceptions in `finally` blocks should be avoided if it is possible.</span></span>  
  
 <span data-ttu-id="b75ed-112">データベース接続も、`finally` ブロックで閉じられる対象になります。</span><span class="sxs-lookup"><span data-stu-id="b75ed-112">A database connection is another good candidate for being closed in a `finally` block.</span></span> <span data-ttu-id="b75ed-113">データベース サーバーで許可される接続数は限られていることがあるため、データベース接続はできるだけ早く閉じる必要があります。</span><span class="sxs-lookup"><span data-stu-id="b75ed-113">Because the number of connections allowed to a database server is sometimes limited, you should close database connections as quickly as possible.</span></span> <span data-ttu-id="b75ed-114">接続を閉じる前に例外がスローされる場合も、ガベージ コレクションを待機するより、`finally` ブロックを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="b75ed-114">If an exception is thrown before you can close your connection, this is another case where using the `finally` block is better than waiting for garbage collection.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b75ed-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="b75ed-115">See also</span></span>

- [<span data-ttu-id="b75ed-116">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="b75ed-116">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="b75ed-117">例外と例外処理</span><span class="sxs-lookup"><span data-stu-id="b75ed-117">Exceptions and Exception Handling</span></span>](./index.md)
- [<span data-ttu-id="b75ed-118">例外処理</span><span class="sxs-lookup"><span data-stu-id="b75ed-118">Exception Handling</span></span>](./exception-handling.md)
- [<span data-ttu-id="b75ed-119">using ステートメント</span><span class="sxs-lookup"><span data-stu-id="b75ed-119">using Statement</span></span>](../../language-reference/keywords/using-statement.md)
- [<span data-ttu-id="b75ed-120">try-catch</span><span class="sxs-lookup"><span data-stu-id="b75ed-120">try-catch</span></span>](../../language-reference/keywords/try-catch.md)
- [<span data-ttu-id="b75ed-121">try-finally</span><span class="sxs-lookup"><span data-stu-id="b75ed-121">try-finally</span></span>](../../language-reference/keywords/try-finally.md)
- [<span data-ttu-id="b75ed-122">try-catch-finally</span><span class="sxs-lookup"><span data-stu-id="b75ed-122">try-catch-finally</span></span>](../../language-reference/keywords/try-catch-finally.md)
