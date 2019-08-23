---
title: End ステートメント (Visual Basic)
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
ms.openlocfilehash: 9307cf10e6125441bd49baa0e663a5a13f234005
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69944463"
---
# <a name="end-statement"></a><span data-ttu-id="8202d-102">End ステートメント</span><span class="sxs-lookup"><span data-stu-id="8202d-102">End Statement</span></span>
<span data-ttu-id="8202d-103">直ちに実行を終了します。</span><span class="sxs-lookup"><span data-stu-id="8202d-103">Terminates execution immediately.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8202d-104">構文</span><span class="sxs-lookup"><span data-stu-id="8202d-104">Syntax</span></span>  
  
```  
End  
```  
  
## <a name="remarks"></a><span data-ttu-id="8202d-105">Remarks</span><span class="sxs-lookup"><span data-stu-id="8202d-105">Remarks</span></span>  
 <span data-ttu-id="8202d-106">`End`ステートメントをプロシージャ内の任意の場所に配置して、アプリケーション全体の実行を強制的に停止することができます。</span><span class="sxs-lookup"><span data-stu-id="8202d-106">You can place the `End` statement anywhere in a procedure to force the entire application to stop running.</span></span> <span data-ttu-id="8202d-107">`End``Open`ステートメントで開かれたすべてのファイルを閉じ、すべてのアプリケーションの変数をクリアします。</span><span class="sxs-lookup"><span data-stu-id="8202d-107">`End` closes any files opened with an `Open` statement and clears all the application's variables.</span></span> <span data-ttu-id="8202d-108">オブジェクトへの参照を保持しているプログラムが他になく、そのコードも実行されていない場合、アプリケーションはすぐに終了します。</span><span class="sxs-lookup"><span data-stu-id="8202d-108">The application closes as soon as there are no other programs holding references to its objects and none of its code is running.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8202d-109">ステートメントは、コードの実行を突然停止します。 `Dispose`また`Finalize` 、メソッド、メソッド、またはその他の Visual Basic コードを呼び出しません。 `End`</span><span class="sxs-lookup"><span data-stu-id="8202d-109">The `End` statement stops code execution abruptly, and does not invoke the `Dispose` or `Finalize` method, or any other Visual Basic code.</span></span> <span data-ttu-id="8202d-110">他のプログラムによって保持されているオブジェクト参照は無効になります。</span><span class="sxs-lookup"><span data-stu-id="8202d-110">Object references held by other programs are invalidated.</span></span> <span data-ttu-id="8202d-111">ステートメントが`Try`また`Finally`は`Catch`ブロック内で見つかった場合、コントロールは対応するブロックに渡されません。 `End`</span><span class="sxs-lookup"><span data-stu-id="8202d-111">If an `End` statement is encountered within a `Try` or `Catch` block, control does not pass to the corresponding `Finally` block.</span></span>  
  
 <span data-ttu-id="8202d-112">ステートメント`Stop`は実行を中断します`End`が、とは異なり、コンパイルされた実行可能 (.exe) ファイルに存在しない限り、ファイルを閉じたり変数をクリアしたりすることはありません。</span><span class="sxs-lookup"><span data-stu-id="8202d-112">The `Stop` statement suspends execution, but unlike `End`, it does not close any files or clear any variables, unless it is encountered in a compiled executable (.exe) file.</span></span>  
  
 <span data-ttu-id="8202d-113">は`End` 、開いている可能性のあるリソースには参加せずにアプリケーションを終了するため、使用する前に正常に終了するようにしてください。</span><span class="sxs-lookup"><span data-stu-id="8202d-113">Because `End` terminates your application without attending to any resources that might be open, you should try to close down cleanly before using it.</span></span> <span data-ttu-id="8202d-114">たとえば、アプリケーションでフォームが開いている場合は、コントロールがステートメントに`End`到達する前に、フォームを閉じる必要があります。</span><span class="sxs-lookup"><span data-stu-id="8202d-114">For example, if your application has any forms open, you should close them before control reaches the `End` statement.</span></span>  
  
 <span data-ttu-id="8202d-115">をすぐに`End`停止する必要がある場合にのみ、を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8202d-115">You should use `End` sparingly, and only when you need to stop immediately.</span></span> <span data-ttu-id="8202d-116">プロシージャを終了する通常の方法 ([Return statement](../../../visual-basic/language-reference/statements/return-statement.md)ステートメントと[Exit ステートメント](../../../visual-basic/language-reference/statements/exit-statement.md)) は、プロシージャを正常に終了するだけでなく、呼び出し元のコードが正常に終了する機会を与えることもできます。</span><span class="sxs-lookup"><span data-stu-id="8202d-116">The normal ways to terminate a procedure ([Return Statement](../../../visual-basic/language-reference/statements/return-statement.md) and [Exit Statement](../../../visual-basic/language-reference/statements/exit-statement.md)) not only close down the procedure cleanly but also give the calling code the opportunity to close down cleanly.</span></span> <span data-ttu-id="8202d-117">たとえば、コンソールアプリケーションは単`Return`に`Main`プロシージャから実行できます。</span><span class="sxs-lookup"><span data-stu-id="8202d-117">A console application, for example, can simply `Return` from the `Main` procedure.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="8202d-118">ステートメント`End`は、 <xref:System>名前<xref:System.Environment.Exit%2A>空間の<xref:System.Environment>クラスのメソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="8202d-118">The `End` statement calls the <xref:System.Environment.Exit%2A> method of the <xref:System.Environment> class in the <xref:System> namespace.</span></span> <span data-ttu-id="8202d-119"><xref:System.Environment.Exit%2A>にはアクセス許可`UnmanagedCode`が必要です。</span><span class="sxs-lookup"><span data-stu-id="8202d-119"><xref:System.Environment.Exit%2A> requires that you have `UnmanagedCode` permission.</span></span> <span data-ttu-id="8202d-120">そうしないと、 <xref:System.Security.SecurityException>エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="8202d-120">If you do not, a <xref:System.Security.SecurityException> error occurs.</span></span>  
  
 <span data-ttu-id="8202d-121">その後に追加のキーワードが続くと、 [end \<キーワード > ステートメント](../../../visual-basic/language-reference/statements/end-keyword-statement.md)は、適切なプロシージャまたはブロックの定義の末尾に記述ます。</span><span class="sxs-lookup"><span data-stu-id="8202d-121">When followed by an additional keyword, [End \<keyword> Statement](../../../visual-basic/language-reference/statements/end-keyword-statement.md) delineates the end of the definition of the appropriate procedure or block.</span></span> <span data-ttu-id="8202d-122">たとえば、は`End Function` `Function`プロシージャの定義を終了します。</span><span class="sxs-lookup"><span data-stu-id="8202d-122">For example, `End Function` terminates the definition of a `Function` procedure.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8202d-123">例</span><span class="sxs-lookup"><span data-stu-id="8202d-123">Example</span></span>  
 <span data-ttu-id="8202d-124">次の例では`End` 、ステートメントを使用して、ユーザーが要求した場合にコードの実行を終了します。</span><span class="sxs-lookup"><span data-stu-id="8202d-124">The following example uses the `End` statement to terminate code execution if the user requests it.</span></span>  
  
 [!code-vb[VbVersHelp60Controls#64](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVersHelp60Controls/VB/Form1.vb#64)]  
  
## <a name="smart-device-developer-notes"></a><span data-ttu-id="8202d-125">スマートデバイスの開発者向けメモ</span><span class="sxs-lookup"><span data-stu-id="8202d-125">Smart Device Developer Notes</span></span>  
 <span data-ttu-id="8202d-126">このステートメントはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="8202d-126">This statement is not supported.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8202d-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="8202d-127">See also</span></span>

- <xref:System.Security.Permissions.SecurityPermissionFlag>
- [<span data-ttu-id="8202d-128">Stop ステートメント</span><span class="sxs-lookup"><span data-stu-id="8202d-128">Stop Statement</span></span>](../../../visual-basic/language-reference/statements/stop-statement.md)
- [<span data-ttu-id="8202d-129">End \<キーワード > ステートメント</span><span class="sxs-lookup"><span data-stu-id="8202d-129">End \<keyword> Statement</span></span>](../../../visual-basic/language-reference/statements/end-keyword-statement.md)
