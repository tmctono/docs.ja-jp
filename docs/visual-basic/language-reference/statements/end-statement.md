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
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74343724"
---
# <a name="end-statement"></a><span data-ttu-id="6b7a5-102">End ステートメント</span><span class="sxs-lookup"><span data-stu-id="6b7a5-102">End Statement</span></span>
<span data-ttu-id="6b7a5-103">直ちに実行を終了します。</span><span class="sxs-lookup"><span data-stu-id="6b7a5-103">Terminates execution immediately.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6b7a5-104">構文</span><span class="sxs-lookup"><span data-stu-id="6b7a5-104">Syntax</span></span>  
  
```vb  
End  
```  
  
## <a name="remarks"></a><span data-ttu-id="6b7a5-105">Remarks</span><span class="sxs-lookup"><span data-stu-id="6b7a5-105">Remarks</span></span>  
 <span data-ttu-id="6b7a5-106">プロシージャの任意の場所に `End` ステートメントを配置して、アプリケーション全体の実行を強制的に停止することができます。</span><span class="sxs-lookup"><span data-stu-id="6b7a5-106">You can place the `End` statement anywhere in a procedure to force the entire application to stop running.</span></span> <span data-ttu-id="6b7a5-107">`End` によって、`Open` ステートメントを使用して開いたファイルがすべて閉じられ、アプリケーションのすべての変数がクリアされます。</span><span class="sxs-lookup"><span data-stu-id="6b7a5-107">`End` closes any files opened with an `Open` statement and clears all the application's variables.</span></span> <span data-ttu-id="6b7a5-108">オブジェクトへの参照を保持している他のプログラムがなくなり、そのコードが実行されなくなると、アプリケーションはすぐに終了します。</span><span class="sxs-lookup"><span data-stu-id="6b7a5-108">The application closes as soon as there are no other programs holding references to its objects and none of its code is running.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6b7a5-109">`End` ステートメントを使用すると、コードの実行は突然停止され、`Dispose` または `Finalize` メソッド、またはその他の Visual Basic コードは呼び出されません。</span><span class="sxs-lookup"><span data-stu-id="6b7a5-109">The `End` statement stops code execution abruptly, and does not invoke the `Dispose` or `Finalize` method, or any other Visual Basic code.</span></span> <span data-ttu-id="6b7a5-110">他のプログラムに保持されているオブジェクト参照は無効になります。</span><span class="sxs-lookup"><span data-stu-id="6b7a5-110">Object references held by other programs are invalidated.</span></span> <span data-ttu-id="6b7a5-111">`Try` または `Catch` ブロック内に `End` ステートメントが存在すると、制御は対応する `Finally` ブロックには渡されません。</span><span class="sxs-lookup"><span data-stu-id="6b7a5-111">If an `End` statement is encountered within a `Try` or `Catch` block, control does not pass to the corresponding `Finally` block.</span></span>  
  
 <span data-ttu-id="6b7a5-112">`Stop` ステートメントでは実行が中断されますが、`End` とは異なり、コンパイル済みの実行可能 (.exe) ファイルで検出されていない限り、ファイルを閉じたり、変数をクリアしたりしません。</span><span class="sxs-lookup"><span data-stu-id="6b7a5-112">The `Stop` statement suspends execution, but unlike `End`, it does not close any files or clear any variables, unless it is encountered in a compiled executable (.exe) file.</span></span>  
  
 <span data-ttu-id="6b7a5-113">`End` を使用すると、開いている可能性のあるリソースを処理することなくアプリケーションが終了するため、使用する前に完全に終了するようにします。</span><span class="sxs-lookup"><span data-stu-id="6b7a5-113">Because `End` terminates your application without attending to any resources that might be open, you should try to close down cleanly before using it.</span></span> <span data-ttu-id="6b7a5-114">たとえば、アプリケーションでフォームを開いている場合は、コントロールが `End` ステートメントに到達する前にフォームを閉じる必要があります。</span><span class="sxs-lookup"><span data-stu-id="6b7a5-114">For example, if your application has any forms open, you should close them before control reaches the `End` statement.</span></span>  
  
 <span data-ttu-id="6b7a5-115">`End` は慎重に使用し、すぐに停止する必要がある場合にのみ使用してください。</span><span class="sxs-lookup"><span data-stu-id="6b7a5-115">You should use `End` sparingly, and only when you need to stop immediately.</span></span> <span data-ttu-id="6b7a5-116">プロシージャを終了する通常の方法 ([Return ステートメント](../../../visual-basic/language-reference/statements/return-statement.md)と [Exit ステートメント](../../../visual-basic/language-reference/statements/exit-statement.md)) では、プロシージャが完全に終了されるだけでなく、呼び出し元のコードにも正常に終了する機会が与えられます。</span><span class="sxs-lookup"><span data-stu-id="6b7a5-116">The normal ways to terminate a procedure ([Return Statement](../../../visual-basic/language-reference/statements/return-statement.md) and [Exit Statement](../../../visual-basic/language-reference/statements/exit-statement.md)) not only close down the procedure cleanly but also give the calling code the opportunity to close down cleanly.</span></span> <span data-ttu-id="6b7a5-117">たとえば、コンソール アプリケーションでは、`Main` プロシージャから単に `Return` を実行できます。</span><span class="sxs-lookup"><span data-stu-id="6b7a5-117">A console application, for example, can simply `Return` from the `Main` procedure.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="6b7a5-118">`End` ステートメントを使用すると、<xref:System> 名前空間内の <xref:System.Environment> クラスの <xref:System.Environment.Exit%2A> メソッドが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="6b7a5-118">The `End` statement calls the <xref:System.Environment.Exit%2A> method of the <xref:System.Environment> class in the <xref:System> namespace.</span></span> <span data-ttu-id="6b7a5-119"><xref:System.Environment.Exit%2A> を使用するには `UnmanagedCode` アクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="6b7a5-119"><xref:System.Environment.Exit%2A> requires that you have `UnmanagedCode` permission.</span></span> <span data-ttu-id="6b7a5-120">そうしないと、<xref:System.Security.SecurityException> エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="6b7a5-120">If you do not, a <xref:System.Security.SecurityException> error occurs.</span></span>  
  
 <span data-ttu-id="6b7a5-121">その後に追加のキーワードが続く場合、[End \<keyword> ステートメント](../../../visual-basic/language-reference/statements/end-keyword-statement.md)を使用して、適切なプロシージャまたはブロックの定義の終わりを示します。</span><span class="sxs-lookup"><span data-stu-id="6b7a5-121">When followed by an additional keyword, [End \<keyword> Statement](../../../visual-basic/language-reference/statements/end-keyword-statement.md) delineates the end of the definition of the appropriate procedure or block.</span></span> <span data-ttu-id="6b7a5-122">たとえば、`End Function` を使用して `Function` プロシージャの定義を終了します。</span><span class="sxs-lookup"><span data-stu-id="6b7a5-122">For example, `End Function` terminates the definition of a `Function` procedure.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6b7a5-123">例</span><span class="sxs-lookup"><span data-stu-id="6b7a5-123">Example</span></span>  
 <span data-ttu-id="6b7a5-124">次の例では、`End` ステートメントを使用して、ユーザーから要求された場合にコードの実行を終了します。</span><span class="sxs-lookup"><span data-stu-id="6b7a5-124">The following example uses the `End` statement to terminate code execution if the user requests it.</span></span>  
  
 [!code-vb[VbVersHelp60Controls#64](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVersHelp60Controls/VB/Form1.vb#64)]  
  
## <a name="smart-device-developer-notes"></a><span data-ttu-id="6b7a5-125">スマート デバイス開発者向けのメモ</span><span class="sxs-lookup"><span data-stu-id="6b7a5-125">Smart Device Developer Notes</span></span>  
 <span data-ttu-id="6b7a5-126">このステートメントはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="6b7a5-126">This statement is not supported.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b7a5-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="6b7a5-127">See also</span></span>

- <xref:System.Security.Permissions.SecurityPermissionFlag>
- [<span data-ttu-id="6b7a5-128">Stop ステートメント</span><span class="sxs-lookup"><span data-stu-id="6b7a5-128">Stop Statement</span></span>](../../../visual-basic/language-reference/statements/stop-statement.md)
- [<span data-ttu-id="6b7a5-129">End \<キーワード> ステートメント</span><span class="sxs-lookup"><span data-stu-id="6b7a5-129">End \<keyword> Statement</span></span>](../../../visual-basic/language-reference/statements/end-keyword-statement.md)
