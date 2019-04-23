---
title: '方法: (Visual Basic) の値を返さないプロシージャを呼び出す'
ms.date: 07/20/2015
helpviewer_keywords:
- procedure calls [Visual Basic], returning values
- Visual Basic code, procedures
- procedures [Visual Basic], calling
ms.assetid: 259b49a3-a3c1-4254-ba8c-73cdc4127703
ms.openlocfilehash: 6e3ce2a184ca5411a6a016929a16bf3d67e669ca
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59335473"
---
# <a name="how-to-call-a-procedure-that-does-not-return-a-value-visual-basic"></a><span data-ttu-id="3d841-102">方法: (Visual Basic) の値を返さないプロシージャを呼び出す</span><span class="sxs-lookup"><span data-stu-id="3d841-102">How to: Call a Procedure that Does Not Return a Value (Visual Basic)</span></span>
<span data-ttu-id="3d841-103">A`Sub`プロシージャが呼び出し元のコードに値を返しません。</span><span class="sxs-lookup"><span data-stu-id="3d841-103">A `Sub` procedure does not return a value to the calling code.</span></span> <span data-ttu-id="3d841-104">明示的に呼び出す、スタンドアロンの呼び出し元ステートメントを使用します。</span><span class="sxs-lookup"><span data-stu-id="3d841-104">You call it explicitly with a stand-alone calling statement.</span></span> <span data-ttu-id="3d841-105">単に式の中で名前を使用して呼び出すことはできません。</span><span class="sxs-lookup"><span data-stu-id="3d841-105">You cannot call it by simply using its name within an expression.</span></span>  
  
### <a name="to-call-a-sub-procedure"></a><span data-ttu-id="3d841-106">Sub プロシージャを呼び出す</span><span class="sxs-lookup"><span data-stu-id="3d841-106">To call a Sub procedure</span></span>  
  
1. <span data-ttu-id="3d841-107">名前を指定、`Sub`プロシージャ。</span><span class="sxs-lookup"><span data-stu-id="3d841-107">Specify the name of the `Sub` procedure.</span></span>  
  
2. <span data-ttu-id="3d841-108">引数リストを囲む中かっこでプロシージャ名に従ってください。</span><span class="sxs-lookup"><span data-stu-id="3d841-108">Follow the procedure name with parentheses to enclose the argument list.</span></span> <span data-ttu-id="3d841-109">引数がない場合、かっこを省略することができます。</span><span class="sxs-lookup"><span data-stu-id="3d841-109">If there are no arguments, you can optionally omit the parentheses.</span></span> <span data-ttu-id="3d841-110">ただし、かっこを使用して、コードを読みやすくします。</span><span class="sxs-lookup"><span data-stu-id="3d841-110">However, using the parentheses makes your code easier to read.</span></span>  
  
3. <span data-ttu-id="3d841-111">コンマで区切り、かっこ内の引数リストで、引数を配置します。</span><span class="sxs-lookup"><span data-stu-id="3d841-111">Place the arguments in the argument list within the parentheses, separated by commas.</span></span> <span data-ttu-id="3d841-112">同じ順序で引数を指定するかどうかを必ずを`Sub`プロシージャが、対応するパラメーターを定義します。</span><span class="sxs-lookup"><span data-stu-id="3d841-112">Be sure you supply the arguments in the same order that the `Sub` procedure defines the corresponding parameters.</span></span>  
  
     <span data-ttu-id="3d841-113">次の例では、Visual Basic<xref:Microsoft.VisualBasic.Interaction.AppActivate%2A>アプリケーション ウィンドウをアクティブ化する関数。</span><span class="sxs-lookup"><span data-stu-id="3d841-113">The following example calls the Visual Basic <xref:Microsoft.VisualBasic.Interaction.AppActivate%2A> function to activate an application window.</span></span> <span data-ttu-id="3d841-114"><xref:Microsoft.VisualBasic.Interaction.AppActivate%2A> ウィンドウのタイトルを単一の引数として受け取る。</span><span class="sxs-lookup"><span data-stu-id="3d841-114"><xref:Microsoft.VisualBasic.Interaction.AppActivate%2A> takes the window title as its sole argument.</span></span> <span data-ttu-id="3d841-115">呼び出し元のコードに値を返すことはできません。</span><span class="sxs-lookup"><span data-stu-id="3d841-115">It does not return a value to the calling code.</span></span> <span data-ttu-id="3d841-116">例がスローされます、メモ帳プロセスが実行されていない場合、<xref:System.ArgumentException>します。</span><span class="sxs-lookup"><span data-stu-id="3d841-116">If a Notepad process is not running, the example throws an <xref:System.ArgumentException>.</span></span> <span data-ttu-id="3d841-117">`Shell`プロシージャでは、アプリケーションは、指定されたパスに前提としています。</span><span class="sxs-lookup"><span data-stu-id="3d841-117">The `Shell` procedure assumes the applications are in the paths specified.</span></span>  
  
     [!code-vb[VbVbalrCatRef#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCatRef/VB/Class1.vb#11)]  
  
## <a name="see-also"></a><span data-ttu-id="3d841-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="3d841-118">See also</span></span>

- <xref:Microsoft.VisualBasic.Interaction.Shell%2A>
- <xref:System.ArgumentException>
- [<span data-ttu-id="3d841-119">プロシージャ</span><span class="sxs-lookup"><span data-stu-id="3d841-119">Procedures</span></span>](./index.md)
- [<span data-ttu-id="3d841-120">Sub プロシージャ</span><span class="sxs-lookup"><span data-stu-id="3d841-120">Sub Procedures</span></span>](./sub-procedures.md)
- [<span data-ttu-id="3d841-121">プロシージャのパラメーターと引数</span><span class="sxs-lookup"><span data-stu-id="3d841-121">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="3d841-122">Sub ステートメント</span><span class="sxs-lookup"><span data-stu-id="3d841-122">Sub Statement</span></span>](../../../../visual-basic/language-reference/statements/sub-statement.md)
- [<span data-ttu-id="3d841-123">方法: プロシージャを作成します。</span><span class="sxs-lookup"><span data-stu-id="3d841-123">How to: Create a Procedure</span></span>](./how-to-create-a-procedure.md)
- [<span data-ttu-id="3d841-124">方法: 値を返すプロシージャを呼び出す</span><span class="sxs-lookup"><span data-stu-id="3d841-124">How to: Call a Procedure That Returns a Value</span></span>](./how-to-call-a-procedure-that-returns-a-value.md)
- [<span data-ttu-id="3d841-125">方法: Visual Basic でイベント ハンドラーを呼び出す</span><span class="sxs-lookup"><span data-stu-id="3d841-125">How to: Call an Event Handler in Visual Basic</span></span>](./how-to-call-an-event-handler.md)
