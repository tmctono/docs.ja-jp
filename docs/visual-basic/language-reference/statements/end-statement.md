---
title: End ステートメント
ms.date: 07/20/2015
f1_keywords:
- vb.End
- End
helpviewer_keywords:
- execution [Visual Basic], ending
- files [Visual Basic], closing
- End keyword [Visual Basic], End statements
- programs [Visual Basic], quitting
- code, exiting
- program termination
- End statement [Visual Basic]
- execution [Visual Basic], stopping
ms.assetid: 0e64467c-0f34-4aab-9ddd-43f8b9d55d90
ms.openlocfilehash: cb2fb4abb21b7b9c6575cec4aca1374f63687607
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74343724"
---
# <a name="end-statement"></a><span data-ttu-id="42dac-102">End ステートメント</span><span class="sxs-lookup"><span data-stu-id="42dac-102">End Statement</span></span>
<span data-ttu-id="42dac-103">直ちに実行を終了します。</span><span class="sxs-lookup"><span data-stu-id="42dac-103">Terminates execution immediately.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="42dac-104">構文</span><span class="sxs-lookup"><span data-stu-id="42dac-104">Syntax</span></span>  
  
```vb  
End  
```  
  
## <a name="remarks"></a><span data-ttu-id="42dac-105">コメント</span><span class="sxs-lookup"><span data-stu-id="42dac-105">Remarks</span></span>  
 <span data-ttu-id="42dac-106">`End` ステートメントをプロシージャ内の任意の場所に配置して、アプリケーション全体の実行を強制的に停止することができます。</span><span class="sxs-lookup"><span data-stu-id="42dac-106">You can place the `End` statement anywhere in a procedure to force the entire application to stop running.</span></span> <span data-ttu-id="42dac-107">`End` `Open` ステートメントで開かれたすべてのファイルを閉じ、アプリケーションのすべての変数をクリアします。</span><span class="sxs-lookup"><span data-stu-id="42dac-107">`End` closes any files opened with an `Open` statement and clears all the application's variables.</span></span> <span data-ttu-id="42dac-108">オブジェクトへの参照を保持しているプログラムが他になく、そのコードも実行されていない場合、アプリケーションはすぐに終了します。</span><span class="sxs-lookup"><span data-stu-id="42dac-108">The application closes as soon as there are no other programs holding references to its objects and none of its code is running.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="42dac-109">`End` ステートメントは、コードの実行を突然停止し、`Dispose` または `Finalize` メソッド、またはその他の Visual Basic コードを呼び出しません。</span><span class="sxs-lookup"><span data-stu-id="42dac-109">The `End` statement stops code execution abruptly, and does not invoke the `Dispose` or `Finalize` method, or any other Visual Basic code.</span></span> <span data-ttu-id="42dac-110">他のプログラムによって保持されているオブジェクト参照は無効になります。</span><span class="sxs-lookup"><span data-stu-id="42dac-110">Object references held by other programs are invalidated.</span></span> <span data-ttu-id="42dac-111">`End` ステートメントが `Try` または `Catch` ブロック内で検出された場合、コントロールは対応する `Finally` ブロックに渡されません。</span><span class="sxs-lookup"><span data-stu-id="42dac-111">If an `End` statement is encountered within a `Try` or `Catch` block, control does not pass to the corresponding `Finally` block.</span></span>  
  
 <span data-ttu-id="42dac-112">`Stop` ステートメントは実行を中断しますが、`End`とは異なり、コンパイル済みの実行可能 (.exe) ファイルに存在しない限り、ファイルは閉じられず、変数はクリアされません。</span><span class="sxs-lookup"><span data-stu-id="42dac-112">The `Stop` statement suspends execution, but unlike `End`, it does not close any files or clear any variables, unless it is encountered in a compiled executable (.exe) file.</span></span>  
  
 <span data-ttu-id="42dac-113">`End` は、開いている可能性のあるリソースには参加せずにアプリケーションを終了するため、使用する前に、正常に終了するようにしてください。</span><span class="sxs-lookup"><span data-stu-id="42dac-113">Because `End` terminates your application without attending to any resources that might be open, you should try to close down cleanly before using it.</span></span> <span data-ttu-id="42dac-114">たとえば、アプリケーションでフォームが開いている場合は、コントロールが `End` ステートメントに到達する前に、それらを閉じる必要があります。</span><span class="sxs-lookup"><span data-stu-id="42dac-114">For example, if your application has any forms open, you should close them before control reaches the `End` statement.</span></span>  
  
 <span data-ttu-id="42dac-115">`End` は、すぐに停止する必要がある場合にのみ使用してください。</span><span class="sxs-lookup"><span data-stu-id="42dac-115">You should use `End` sparingly, and only when you need to stop immediately.</span></span> <span data-ttu-id="42dac-116">プロシージャを終了する通常の方法 ([Return ステートメント](../../../visual-basic/language-reference/statements/return-statement.md)ステートメントと[Exit ステートメント](../../../visual-basic/language-reference/statements/exit-statement.md)) は、プロシージャを正常に終了するだけでなく、呼び出し元のコードが正常に終了する機会を与えることもできます。</span><span class="sxs-lookup"><span data-stu-id="42dac-116">The normal ways to terminate a procedure ([Return Statement](../../../visual-basic/language-reference/statements/return-statement.md) and [Exit Statement](../../../visual-basic/language-reference/statements/exit-statement.md)) not only close down the procedure cleanly but also give the calling code the opportunity to close down cleanly.</span></span> <span data-ttu-id="42dac-117">たとえば、コンソールアプリケーションは、単純に `Main` プロシージャから `Return` できます。</span><span class="sxs-lookup"><span data-stu-id="42dac-117">A console application, for example, can simply `Return` from the `Main` procedure.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="42dac-118">`End` ステートメントは、<xref:System> 名前空間の <xref:System.Environment> クラスの <xref:System.Environment.Exit%2A> メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="42dac-118">The `End` statement calls the <xref:System.Environment.Exit%2A> method of the <xref:System.Environment> class in the <xref:System> namespace.</span></span> <span data-ttu-id="42dac-119"><xref:System.Environment.Exit%2A> には `UnmanagedCode` のアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="42dac-119"><xref:System.Environment.Exit%2A> requires that you have `UnmanagedCode` permission.</span></span> <span data-ttu-id="42dac-120">そうしないと、<xref:System.Security.SecurityException> エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="42dac-120">If you do not, a <xref:System.Security.SecurityException> error occurs.</span></span>  
  
 <span data-ttu-id="42dac-121">その後に追加のキーワードが続く場合は、 [end \<キーワード > ステートメント](../../../visual-basic/language-reference/statements/end-keyword-statement.md)によって、適切なプロシージャまたはブロックの定義の最後まで記述ます。</span><span class="sxs-lookup"><span data-stu-id="42dac-121">When followed by an additional keyword, [End \<keyword> Statement](../../../visual-basic/language-reference/statements/end-keyword-statement.md) delineates the end of the definition of the appropriate procedure or block.</span></span> <span data-ttu-id="42dac-122">たとえば、`End Function` は `Function` プロシージャの定義を終了します。</span><span class="sxs-lookup"><span data-stu-id="42dac-122">For example, `End Function` terminates the definition of a `Function` procedure.</span></span>  
  
## <a name="example"></a><span data-ttu-id="42dac-123">例</span><span class="sxs-lookup"><span data-stu-id="42dac-123">Example</span></span>  
 <span data-ttu-id="42dac-124">次の例では、`End` ステートメントを使用して、ユーザーから要求された場合にコードの実行を終了します。</span><span class="sxs-lookup"><span data-stu-id="42dac-124">The following example uses the `End` statement to terminate code execution if the user requests it.</span></span>  
  
 [!code-vb[VbVersHelp60Controls#64](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVersHelp60Controls/VB/Form1.vb#64)]  
  
## <a name="smart-device-developer-notes"></a><span data-ttu-id="42dac-125">スマートデバイスの開発者向けメモ</span><span class="sxs-lookup"><span data-stu-id="42dac-125">Smart Device Developer Notes</span></span>  
 <span data-ttu-id="42dac-126">このステートメントはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="42dac-126">This statement is not supported.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42dac-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="42dac-127">See also</span></span>

- <xref:System.Security.Permissions.SecurityPermissionFlag>
- [<span data-ttu-id="42dac-128">Stop ステートメント</span><span class="sxs-lookup"><span data-stu-id="42dac-128">Stop Statement</span></span>](../../../visual-basic/language-reference/statements/stop-statement.md)
- [<span data-ttu-id="42dac-129">End \<keyword > ステートメント</span><span class="sxs-lookup"><span data-stu-id="42dac-129">End \<keyword> Statement</span></span>](../../../visual-basic/language-reference/statements/end-keyword-statement.md)
