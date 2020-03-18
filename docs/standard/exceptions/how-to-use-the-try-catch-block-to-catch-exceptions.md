---
title: '方法: Try ブロックと Catch ブロックを使用して例外をキャッチする'
ms.date: 02/06/2019
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- exceptions, try/catch blocks
- try blocks
- try/catch blocks
- catch blocks
ms.assetid: a3ce6dfd-1f64-471b-8ad8-8cfaf406275d
ms.openlocfilehash: 5a9218d394b76e897f4263708a10f1bc895ad4e1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/15/2020
ms.locfileid: "75708467"
---
# <a name="how-to-use-the-trycatch-block-to-catch-exceptions"></a><span data-ttu-id="cb275-102">Try ブロックと Catch ブロックを使用して例外をキャッチする方法</span><span class="sxs-lookup"><span data-stu-id="cb275-102">How to use the try/catch block to catch exceptions</span></span>

<span data-ttu-id="cb275-103">例外を発生またはスローする可能性のあるコード ステートメントはいずれも `try` ブロックに配置し、1 つまたは複数の例外を処理するのに使用されるステートメントは `catch` ブロックの下にある 1 つまたは複数の `try` ブロックに配置します。</span><span class="sxs-lookup"><span data-stu-id="cb275-103">Place any code statements that might raise or throw an exception in a `try` block, and place statements used to handle the exception or exceptions in one or more `catch` blocks below the `try` block.</span></span> <span data-ttu-id="cb275-104">各 `catch` ブロックには例外の種類が含まれており、その例外の種類を処理するのに必要なステートメントを追加で含めることができます。</span><span class="sxs-lookup"><span data-stu-id="cb275-104">Each `catch` block includes the exception type and can contain additional statements needed to handle that exception type.</span></span>

<span data-ttu-id="cb275-105">次の例では、<xref:System.IO.StreamReader> を使用して、*data.txt* と呼ばれるファイルを開き、そのファイルから行を取得します。</span><span class="sxs-lookup"><span data-stu-id="cb275-105">In the following example, a <xref:System.IO.StreamReader> opens a file called *data.txt* and retrieves a line from the file.</span></span> <span data-ttu-id="cb275-106">コードからは 3 つの例外のいずれかがスローされる可能性があります。そのため、コードは `try` ブロックに配置します。</span><span class="sxs-lookup"><span data-stu-id="cb275-106">Since the code might throw any of three exceptions, it's placed in a `try` block.</span></span> <span data-ttu-id="cb275-107">3 つの `catch` ブロックでは例外がキャッチされます。さらに結果をコンソールに表示してそれらの例外が処理されます。</span><span class="sxs-lookup"><span data-stu-id="cb275-107">Three `catch` blocks catch the exceptions and handle them by displaying the results to the console.</span></span>

[!code-csharp[CatchException#3](~/samples/snippets/csharp/VS_Snippets_CLR/CatchException/CS/catchexception2.cs#3)]
[!code-vb[CatchException#3](~/samples/snippets/visualbasic/VS_Snippets_CLR/CatchException/VB/catchexception2.vb#3)]

<span data-ttu-id="cb275-108">共通言語ランタイム (CLR) では、`catch` ブロックで処理されない例外がキャッチされます。</span><span class="sxs-lookup"><span data-stu-id="cb275-108">The Common Language Runtime (CLR) catches exceptions not handled by `catch` blocks.</span></span> <span data-ttu-id="cb275-109">CLR によって例外がキャッチされると、ご利用の CLR 構成に応じて次の結果のいずれかが発生する場合があります。</span><span class="sxs-lookup"><span data-stu-id="cb275-109">If an exception is caught by the CLR, one of the following results may occur depending on your CLR configuration:</span></span>

- <span data-ttu-id="cb275-110">**[デバッグ]** ダイアログ ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="cb275-110">A **Debug** dialog box appears.</span></span>
- <span data-ttu-id="cb275-111">プログラムの実行が停止され、例外情報を含むダイアログ ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="cb275-111">The program stops execution and a dialog box with exception information appears.</span></span>
- <span data-ttu-id="cb275-112">[標準エラー出力ストリーム](xref:System.Console.Error)にエラーが出力されます。</span><span class="sxs-lookup"><span data-stu-id="cb275-112">An error prints out to the [standard error output stream](xref:System.Console.Error).</span></span>

> [!NOTE]
> <span data-ttu-id="cb275-113">ほとんどのコードで例外がスローされる可能性があります。また、<xref:System.OutOfMemoryException> のように、CLR 自体によっていつでもスローされる可能性のある例外もあります。</span><span class="sxs-lookup"><span data-stu-id="cb275-113">Most code can throw an exception, and some exceptions, like <xref:System.OutOfMemoryException>, can be thrown by the CLR itself at any time.</span></span> <span data-ttu-id="cb275-114">アプリケーションではこのようの例外を処理する必要はありませんが、他のユーザーが使用するライブラリを記述する際には、必要となる可能性があるので注意してください。</span><span class="sxs-lookup"><span data-stu-id="cb275-114">While applications aren't required to deal with these exceptions, be aware of the possibility when writing libraries to be used by others.</span></span> <span data-ttu-id="cb275-115">`try` ブロック内でコードを設定するタイミングに関しては、「[例外の推奨事項](best-practices-for-exceptions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cb275-115">For suggestions on when to set code in a `try` block, see [Best Practices for Exceptions](best-practices-for-exceptions.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="cb275-116">参照</span><span class="sxs-lookup"><span data-stu-id="cb275-116">See also</span></span>

- [<span data-ttu-id="cb275-117">例外</span><span class="sxs-lookup"><span data-stu-id="cb275-117">Exceptions</span></span>](index.md)
- [<span data-ttu-id="cb275-118">.NET での I/O エラーの処理</span><span class="sxs-lookup"><span data-stu-id="cb275-118">Handling I/O errors in .NET</span></span>](../io/handling-io-errors.md)
