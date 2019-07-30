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
ms.openlocfilehash: 030986111a50ab59c605a1d683fedc118d10b260
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/30/2019
ms.locfileid: "68626615"
---
# <a name="error-types-visual-basic"></a><span data-ttu-id="14e6a-102">エラーの種類 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="14e6a-102">Error Types (Visual Basic)</span></span>
<span data-ttu-id="14e6a-103">Visual Basic では、エラーは構文エラー、実行時エラー、および論理エラーの3つのカテゴリのいずれかに分類されます。</span><span class="sxs-lookup"><span data-stu-id="14e6a-103">In Visual Basic, errors fall into one of three categories: syntax errors, run-time errors, and logic errors.</span></span>

## <a name="syntax-errors"></a><span data-ttu-id="14e6a-104">構文エラー</span><span class="sxs-lookup"><span data-stu-id="14e6a-104">Syntax Errors</span></span>
 <span data-ttu-id="14e6a-105">*構文エラー*は、コードの記述中に表示されるエラーです。</span><span class="sxs-lookup"><span data-stu-id="14e6a-105">*Syntax errors* are those that appear while you write code.</span></span> <span data-ttu-id="14e6a-106">Visual Studio を使用している場合、コード**エディター**ウィンドウでコードを入力すると、Visual Basic によってコードがチェックされ、単語のスペルミスや言語要素の不適切な使用などの誤りが発生した場合に警告が表示されます。</span><span class="sxs-lookup"><span data-stu-id="14e6a-106">If you're using Visual Studio, Visual Basic checks your code as you type it in the **Code Editor** window and alerts you if you make a mistake, such as misspelling a word or using a language element improperly.</span></span> <span data-ttu-id="14e6a-107">コマンドラインからコンパイルした場合、Visual Basic には、構文エラーに関する情報を含むコンパイラエラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="14e6a-107">If you compile from the command line, Visual Basic displays a compiler error with information about the syntax error.</span></span> <span data-ttu-id="14e6a-108">構文エラーは、最も一般的なエラーの種類です。</span><span class="sxs-lookup"><span data-stu-id="14e6a-108">Syntax errors are the most common type of errors.</span></span> <span data-ttu-id="14e6a-109">コーディング環境では、問題が発生するとすぐに簡単に修正できます。</span><span class="sxs-lookup"><span data-stu-id="14e6a-109">You can fix them easily in the coding environment as soon as they occur.</span></span>

> [!NOTE]
>  <span data-ttu-id="14e6a-110">ステートメント`Option Explicit`は、構文エラーを回避するための1つの手段です。</span><span class="sxs-lookup"><span data-stu-id="14e6a-110">The `Option Explicit` statement is one means of avoiding syntax errors.</span></span> <span data-ttu-id="14e6a-111">これにより、アプリケーションで使用されるすべての変数が事前に宣言されます。</span><span class="sxs-lookup"><span data-stu-id="14e6a-111">It forces you to declare, in advance, all the variables to be used in the application.</span></span> <span data-ttu-id="14e6a-112">そのため、これらの変数がコード内で使用されている場合は、すべての活字エラーが即座にキャッチされ、修正できます。</span><span class="sxs-lookup"><span data-stu-id="14e6a-112">Therefore, when those variables are used in the code, any typographic errors are caught immediately and can be fixed.</span></span>

## <a name="run-time-errors"></a><span data-ttu-id="14e6a-113">実行時エラー</span><span class="sxs-lookup"><span data-stu-id="14e6a-113">Run-Time Errors</span></span>
 <span data-ttu-id="14e6a-114">*実行時エラー*は、コードをコンパイルして実行した後にのみ表示されるエラーです。</span><span class="sxs-lookup"><span data-stu-id="14e6a-114">*Run-time errors* are those that appear only after you compile and run your code.</span></span> <span data-ttu-id="14e6a-115">このようなコードには、構文エラーがないにもかかわらず、実行できないと思われるコードが含まれます。</span><span class="sxs-lookup"><span data-stu-id="14e6a-115">These involve code that may appear to be correct in that it has no syntax errors, but that will not execute.</span></span> <span data-ttu-id="14e6a-116">たとえば、ファイルを開くためのコード行が正しく記述されているとします。</span><span class="sxs-lookup"><span data-stu-id="14e6a-116">For example, you might correctly write a line of code to open a file.</span></span> <span data-ttu-id="14e6a-117">ただし、ファイルが存在しない場合、アプリケーションはファイルを開くことができず、例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="14e6a-117">But if the file does not exist, the application cannot open the file, and it throws an exception.</span></span> <span data-ttu-id="14e6a-118">ほとんどのランタイムエラーは、問題のあるコードを書き直すか、[例外処理](../../language-reference/statements/try-catch-finally-statement.md)を使用して再コンパイルし、再実行することによって修正できます。</span><span class="sxs-lookup"><span data-stu-id="14e6a-118">You can fix most run-time errors by rewriting the faulty code or by using [exception handling](../../language-reference/statements/try-catch-finally-statement.md), and then recompiling and rerunning it.</span></span>
  
## <a name="logic-errors"></a><span data-ttu-id="14e6a-119">ロジックエラー</span><span class="sxs-lookup"><span data-stu-id="14e6a-119">Logic Errors</span></span>
 <span data-ttu-id="14e6a-120">*ロジックエラー*は、アプリケーションが使用された後に表示されるエラーです。</span><span class="sxs-lookup"><span data-stu-id="14e6a-120">*Logic errors* are those that appear once the application is in use.</span></span> <span data-ttu-id="14e6a-121">ほとんどの場合、開発者によって作成された仮定に誤りがあるか、またはユーザーの操作に対する応答として望ましくないまたは予期しない結果になります。</span><span class="sxs-lookup"><span data-stu-id="14e6a-121">They are most often faulty assumptions made by the developer, or unwanted or unexpected results in response to user actions.</span></span> <span data-ttu-id="14e6a-122">たとえば、誤って入力されたキーによってメソッドに誤った情報が提供されることがあります。そうでない場合は、常に有効な値がメソッドに渡されると想定できます。</span><span class="sxs-lookup"><span data-stu-id="14e6a-122">For example, a mistyped key might provide incorrect information to a method, or you may assume that a valid value is always supplied to a method when that is not the case.</span></span> <span data-ttu-id="14e6a-123">ロジックエラーは[例外処理](../../language-reference/statements/try-catch-finally-statement.md)を使用して処理できますが (たとえば、引数が`Nothing`であるかどうかをテストしてをスロー <xref:System.ArgumentNullException>するなど)、ほとんどの場合、ロジックでエラーを修正し、適用.</span><span class="sxs-lookup"><span data-stu-id="14e6a-123">Although logic errors can be handled by using [exception handling](../../language-reference/statements/try-catch-finally-statement.md) (for example, by testing whether an argument is `Nothing` and throwing an <xref:System.ArgumentNullException>), most commonly they should be addressed by correcting the error in logic and recompiling the application.</span></span>

## <a name="see-also"></a><span data-ttu-id="14e6a-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="14e6a-124">See also</span></span>

- [<span data-ttu-id="14e6a-125">Try...Catch...Finally ステートメント</span><span class="sxs-lookup"><span data-stu-id="14e6a-125">Try...Catch...Finally Statement</span></span>](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
- [<span data-ttu-id="14e6a-126">デバッガーの基本事項</span><span class="sxs-lookup"><span data-stu-id="14e6a-126">Debugger Basics</span></span>](/visualstudio/debugger/debugger-basics)
