---
title: '方法 : 例外を明示的にスローする'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- exceptions, try/catch blocks
- FileNotFoundException class
- try/catch blocks
- exceptions, throwing
- implicitly throwing exceptions
ms.assetid: 72bdd157-caa9-4478-9ee3-cb4500b84528
ms.openlocfilehash: 750da20b8c1c40901cc363ac0eff8af888821ce9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/15/2020
ms.locfileid: "75708863"
---
# <a name="how-to-explicitly-throw-exceptions"></a><span data-ttu-id="29741-102">例外を明示的にスローする方法</span><span class="sxs-lookup"><span data-stu-id="29741-102">How to explicitly throw exceptions</span></span>

<span data-ttu-id="29741-103">明示的に例外をスローするには、C# の [`throw`](../../csharp/language-reference/keywords/throw.md) または Visual Basic の [`Throw`](../../visual-basic/language-reference/statements/throw-statement.md) ステートメントを使用します。</span><span class="sxs-lookup"><span data-stu-id="29741-103">You can explicitly throw an exception using the C# [`throw`](../../csharp/language-reference/keywords/throw.md) or the Visual Basic [`Throw`](../../visual-basic/language-reference/statements/throw-statement.md) statement.</span></span> <span data-ttu-id="29741-104">`throw` ステートメントを使って、キャッチした例外をもう一度スローすることもできます。</span><span class="sxs-lookup"><span data-stu-id="29741-104">You can also throw a caught exception again using the `throw` statement.</span></span> <span data-ttu-id="29741-105">再スローされる例外に情報を追加して、デバッグ時により多くの情報を提供するコーディング手法をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="29741-105">It is good coding practice to add information to an exception that is re-thrown to provide more information when debugging.</span></span>

<span data-ttu-id="29741-106">次のコード例では、`try`/`catch` ブロックを使用して可能性のある <xref:System.IO.FileNotFoundException> をキャッチします。</span><span class="sxs-lookup"><span data-stu-id="29741-106">The following code example uses a `try`/`catch` block to catch a possible <xref:System.IO.FileNotFoundException>.</span></span> <span data-ttu-id="29741-107">次の `try` ブロックは、`catch` をキャッチし、データ ファイルが見つからない場合に、メッセージをコンソールに出力する <xref:System.IO.FileNotFoundException> ブロックです。</span><span class="sxs-lookup"><span data-stu-id="29741-107">Following the `try` block is a `catch` block that catches the <xref:System.IO.FileNotFoundException> and writes a message to the console if the data file is not found.</span></span> <span data-ttu-id="29741-108">次のステートメントは、新しい `throw` をスローして、テキスト情報を例外に追加する <xref:System.IO.FileNotFoundException> ステートメントです。</span><span class="sxs-lookup"><span data-stu-id="29741-108">The next statement is the `throw` statement that throws a new <xref:System.IO.FileNotFoundException> and adds text information to the exception.</span></span>

[!code-csharp[Exception.Throwing#1](~/samples/snippets/csharp/VS_Snippets_CLR/Exception.Throwing/CS/throw.cs#1)]
[!code-vb[Exception.Throwing#1](~/samples/snippets/visualbasic/VS_Snippets_CLR/Exception.Throwing/VB/throw.vb#1)]  

## <a name="see-also"></a><span data-ttu-id="29741-109">参照</span><span class="sxs-lookup"><span data-stu-id="29741-109">See also</span></span>

- [<span data-ttu-id="29741-110">例外</span><span class="sxs-lookup"><span data-stu-id="29741-110">Exceptions</span></span>](index.md)
