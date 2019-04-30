---
title: エラーの種類 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- exceptions, types
- errors [Visual Basic], types
- errors [Visual Basic], logic
- errors [Visual Basic], syntax
- logic errors [Visual Basic], Visual Basic
- run-time errors [Visual Basic], types of errors
- syntax errors [Visual Basic], Visual Basic
ms.assetid: 3048aabf-8c97-4e13-9150-853769cb5f6f
ms.openlocfilehash: 07db963ac3cf9d1c0d17c420480189d362cdaf2c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61973174"
---
# <a name="error-types-visual-basic"></a><span data-ttu-id="18815-102">エラーの種類 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="18815-102">Error Types (Visual Basic)</span></span>
<span data-ttu-id="18815-103">Visual basic でのエラー (とも呼ばれる*例外*) 3 つのカテゴリに分類されます。 構文エラー、実行時エラー、および論理エラー。</span><span class="sxs-lookup"><span data-stu-id="18815-103">In Visual Basic, errors (also called *exceptions*) fall into one of three categories: syntax errors, run-time errors, and logic errors.</span></span>  
  
## <a name="syntax-errors"></a><span data-ttu-id="18815-104">構文エラー</span><span class="sxs-lookup"><span data-stu-id="18815-104">Syntax Errors</span></span>  
 <span data-ttu-id="18815-105">*構文エラー*はコードを記述するときに表示されます。</span><span class="sxs-lookup"><span data-stu-id="18815-105">*Syntax errors* are those that appear while you write code.</span></span> <span data-ttu-id="18815-106">Visual Basic で入力すると、コードを確認します、**コード エディター**ウィンドウと単語のスペルが間違ってなどの言語要素を正しくを使用して、操作を誤ったアラートを通知します。</span><span class="sxs-lookup"><span data-stu-id="18815-106">Visual Basic checks your code as you type it in the **Code Editor** window and alerts you if you make a mistake, such as misspelling a word or using a language element improperly.</span></span> <span data-ttu-id="18815-107">構文エラーは、エラーの最も一般的な種類です。</span><span class="sxs-lookup"><span data-stu-id="18815-107">Syntax errors are the most common type of errors.</span></span> <span data-ttu-id="18815-108">その解決簡単にコーディング環境で発生するとすぐにします。</span><span class="sxs-lookup"><span data-stu-id="18815-108">You can fix them easily in the coding environment as soon as they occur.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="18815-109">`Option Explicit`ステートメントが構文エラーを回避する 1 つのことを意味します。</span><span class="sxs-lookup"><span data-stu-id="18815-109">The `Option Explicit` statement is one means of avoiding syntax errors.</span></span> <span data-ttu-id="18815-110">アプリケーションで使用されるすべての変数を事前に宣言を強制的にされます。</span><span class="sxs-lookup"><span data-stu-id="18815-110">It forces you to declare, in advance, all the variables to be used in the application.</span></span> <span data-ttu-id="18815-111">したがって、コードでこれらの変数を使用している場合、入力ミスがすぐに検出され、修正できます。</span><span class="sxs-lookup"><span data-stu-id="18815-111">Therefore, when those variables are used in the code, any typographic errors are caught immediately and can be fixed.</span></span>  
  
## <a name="run-time-errors"></a><span data-ttu-id="18815-112">実行時エラー</span><span class="sxs-lookup"><span data-stu-id="18815-112">Run-Time Errors</span></span>  
 <span data-ttu-id="18815-113">*実行時エラー*は、コンパイルし、コードを実行した後にのみ出現します。</span><span class="sxs-lookup"><span data-stu-id="18815-113">*Run-time errors* are those that appear only after you compile and run your code.</span></span> <span data-ttu-id="18815-114">これらには、構文エラーを持ちませんが実行されませんが、正しく表示されるコードが含まれます。</span><span class="sxs-lookup"><span data-stu-id="18815-114">These involve code that may appear to be correct in that it has no syntax errors, but that will not execute.</span></span> <span data-ttu-id="18815-115">たとえば、ファイルを開くためのコードの行を正しく記述可能性があります。</span><span class="sxs-lookup"><span data-stu-id="18815-115">For example, you might correctly write a line of code to open a file.</span></span> <span data-ttu-id="18815-116">ファイルが壊れている場合は、アプリケーションを実行できませんが、`Open`関数、およびその実行を停止します。</span><span class="sxs-lookup"><span data-stu-id="18815-116">But if the file is corrupted, the application cannot carry out the `Open` function, and it stops running.</span></span> <span data-ttu-id="18815-117">ほとんどの実行時エラーを修正するには、欠陥のあるコードの書き直しを再コンパイルし、再実行することで。</span><span class="sxs-lookup"><span data-stu-id="18815-117">You can fix most run-time errors by rewriting the faulty code, and then recompiling and rerunning it.</span></span>  
  
## <a name="logic-errors"></a><span data-ttu-id="18815-118">論理エラー</span><span class="sxs-lookup"><span data-stu-id="18815-118">Logic Errors</span></span>  
 <span data-ttu-id="18815-119">*論理エラー*は、アプリケーションが使用すると表示されます。</span><span class="sxs-lookup"><span data-stu-id="18815-119">*Logic errors* are those that appear once the application is in use.</span></span> <span data-ttu-id="18815-120">ユーザー アクションへの応答でほとんどの多くの場合、不要なまたは予期しない結果が表示されます。</span><span class="sxs-lookup"><span data-stu-id="18815-120">They are most often unwanted or unexpected results in response to user actions.</span></span> <span data-ttu-id="18815-121">たとえば、入力の間違いキーまたはその他の外部の影響を与える可能性が、アプリケーションに必要なパラメーター内で動作しなくなったりします。</span><span class="sxs-lookup"><span data-stu-id="18815-121">For example, a mistyped key or other outside influence might cause your application to stop working within expected parameters, or altogether.</span></span> <span data-ttu-id="18815-122">論理エラーは、通常ではないため常に明確ではないを解決する最も困難な型です。</span><span class="sxs-lookup"><span data-stu-id="18815-122">Logic errors are generally the hardest type to fix, since it is not always clear where they originate.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18815-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="18815-123">See also</span></span>

- [<span data-ttu-id="18815-124">Try...Catch...Finally ステートメント</span><span class="sxs-lookup"><span data-stu-id="18815-124">Try...Catch...Finally Statement</span></span>](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
- [<span data-ttu-id="18815-125">デバッガーの基本事項</span><span class="sxs-lookup"><span data-stu-id="18815-125">Debugger Basics</span></span>](/visualstudio/debugger/debugger-basics)
