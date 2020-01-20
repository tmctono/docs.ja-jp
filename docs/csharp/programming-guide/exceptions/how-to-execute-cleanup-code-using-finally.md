---
title: finally を使用してクリーンアップ コードを実行する方法 - C# プログラミング ガイド
ms.date: 07/20/2015
helpviewer_keywords:
- try/finally blocks [C#]
- exceptions [C#], try/finally block
- exception handling [C#], try/finally block
ms.assetid: 1b1e5aef-3f32-4a88-9d39-b5fffb33bdaf
ms.openlocfilehash: d1ba761e64053d656ad4cd004133fc455a57c6f6
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/07/2020
ms.locfileid: "75705276"
---
# <a name="how-to-execute-cleanup-code-using-finally-c-programming-guide"></a><span data-ttu-id="2c88c-102">finally を使用してクリーンアップ コードを実行する方法 (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="2c88c-102">How to execute cleanup code using finally (C# Programming Guide)</span></span>
<span data-ttu-id="2c88c-103">`finally` ステートメントの目的は、例外がスローされた場合でも、オブジェクト (一般に外部リソースを保持しているオブジェクト) に対して必要なクリーンアップをすぐに実行できるようにすることです。</span><span class="sxs-lookup"><span data-stu-id="2c88c-103">The purpose of a `finally` statement is to ensure that the necessary cleanup of objects, usually objects that are holding external resources, occurs immediately, even if an exception is thrown.</span></span> <span data-ttu-id="2c88c-104">次のように、共通言語ランタイムによってオブジェクトがガベージ コレクションされるまで待機するのではなく、オブジェクトを使用した後すぐに <xref:System.IO.FileStream> で <xref:System.IO.Stream.Close%2A> を呼び出すというのも、このようなクリーンアップの一例です。</span><span class="sxs-lookup"><span data-stu-id="2c88c-104">One example of such cleanup is calling <xref:System.IO.Stream.Close%2A> on a <xref:System.IO.FileStream> immediately after use instead of waiting for the object to be garbage collected by the common language runtime, as follows:</span></span>  
  
 [!code-csharp[csProgGuideExceptions#16](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideExceptions/CS/Exceptions.cs#16)]  
  
## <a name="example"></a><span data-ttu-id="2c88c-105">例</span><span class="sxs-lookup"><span data-stu-id="2c88c-105">Example</span></span>  
 <span data-ttu-id="2c88c-106">上のコードを `try-catch-finally` ステートメントに変えるには、次のようにクリーンアップ コードを作業コードから切り離します。</span><span class="sxs-lookup"><span data-stu-id="2c88c-106">To turn the previous code into a `try-catch-finally` statement, the cleanup code is separated from the working code, as follows.</span></span>  
  
 [!code-csharp[csProgGuideExceptions#17](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideExceptions/CS/Exceptions.cs#17)]  
  
 <span data-ttu-id="2c88c-107">`try` ブロック内では `OpenWrite()` 呼び出しの前のどの時点でも例外が発生する可能性があります。また、`OpenWrite()` 呼び出し自体が失敗する可能性もあります。そのため、ファイルを閉じようとしたときに、そのファイルが開いているという保証はありません。</span><span class="sxs-lookup"><span data-stu-id="2c88c-107">Because an exception can occur at any time within the `try` block before the `OpenWrite()` call, or the `OpenWrite()` call itself could fail, we are not guaranteed that the file is open when we try to close it.</span></span> <span data-ttu-id="2c88c-108">`finally` ブロックでは、<xref:System.IO.Stream.Close%2A> メソッドを呼び出す前に、<xref:System.IO.FileStream> オブジェクトが `null` でないことを確認するチェックが追加されます。</span><span class="sxs-lookup"><span data-stu-id="2c88c-108">The `finally` block adds a check to make sure that the <xref:System.IO.FileStream> object is not `null` before you call the <xref:System.IO.Stream.Close%2A> method.</span></span> <span data-ttu-id="2c88c-109">この `null` チェックがないと、`finally` ブロックからその <xref:System.NullReferenceException> がスローされる可能性がありますが、`finally` ブロックにおける例外のスローはできるだけ回避する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2c88c-109">Without the `null` check, the `finally` block could throw its own <xref:System.NullReferenceException>, but throwing exceptions in `finally` blocks should be avoided if it is possible.</span></span>  
  
 <span data-ttu-id="2c88c-110">データベース接続も、`finally` ブロックで閉じられる対象になります。</span><span class="sxs-lookup"><span data-stu-id="2c88c-110">A database connection is another good candidate for being closed in a `finally` block.</span></span> <span data-ttu-id="2c88c-111">データベース サーバーで許可される接続数は限られていることがあるため、データベース接続はできるだけ早く閉じる必要があります。</span><span class="sxs-lookup"><span data-stu-id="2c88c-111">Because the number of connections allowed to a database server is sometimes limited, you should close database connections as quickly as possible.</span></span> <span data-ttu-id="2c88c-112">接続を閉じる前に例外がスローされる場合も、ガベージ コレクションを待機するより、`finally` ブロックを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="2c88c-112">If an exception is thrown before you can close your connection, this is another case where using the `finally` block is better than waiting for garbage collection.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c88c-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="2c88c-113">See also</span></span>

- [<span data-ttu-id="2c88c-114">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="2c88c-114">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="2c88c-115">例外と例外処理</span><span class="sxs-lookup"><span data-stu-id="2c88c-115">Exceptions and Exception Handling</span></span>](./index.md)
- [<span data-ttu-id="2c88c-116">例外処理</span><span class="sxs-lookup"><span data-stu-id="2c88c-116">Exception Handling</span></span>](./exception-handling.md)
- [<span data-ttu-id="2c88c-117">using ステートメント</span><span class="sxs-lookup"><span data-stu-id="2c88c-117">using Statement</span></span>](../../language-reference/keywords/using-statement.md)
- [<span data-ttu-id="2c88c-118">try-catch</span><span class="sxs-lookup"><span data-stu-id="2c88c-118">try-catch</span></span>](../../language-reference/keywords/try-catch.md)
- [<span data-ttu-id="2c88c-119">try-finally</span><span class="sxs-lookup"><span data-stu-id="2c88c-119">try-finally</span></span>](../../language-reference/keywords/try-finally.md)
- [<span data-ttu-id="2c88c-120">try-catch-finally</span><span class="sxs-lookup"><span data-stu-id="2c88c-120">try-catch-finally</span></span>](../../language-reference/keywords/try-catch-finally.md)
