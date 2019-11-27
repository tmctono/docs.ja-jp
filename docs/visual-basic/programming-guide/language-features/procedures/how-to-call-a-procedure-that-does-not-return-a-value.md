---
title: '方法 : 値を返さないプロシージャを呼び出す'
ms.date: 07/20/2015
helpviewer_keywords:
- procedure calls [Visual Basic], returning values
- Visual Basic code, procedures
- procedures [Visual Basic], calling
ms.assetid: 259b49a3-a3c1-4254-ba8c-73cdc4127703
ms.openlocfilehash: 3a5de98c6edf795a11bd9f0465aa6919f09eebfa
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74340957"
---
# <a name="how-to-call-a-procedure-that-does-not-return-a-value-visual-basic"></a><span data-ttu-id="fb266-102">方法: 値を返さないプロシージャを呼び出す (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fb266-102">How to: Call a Procedure that Does Not Return a Value (Visual Basic)</span></span>
<span data-ttu-id="fb266-103">`Sub` プロシージャは、呼び出し元のコードに値を返しません。</span><span class="sxs-lookup"><span data-stu-id="fb266-103">A `Sub` procedure does not return a value to the calling code.</span></span> <span data-ttu-id="fb266-104">これは、スタンドアロンの呼び出しステートメントを使用して明示的に呼び出します。</span><span class="sxs-lookup"><span data-stu-id="fb266-104">You call it explicitly with a stand-alone calling statement.</span></span> <span data-ttu-id="fb266-105">単に式の中で名前を使用して呼び出すことはできません。</span><span class="sxs-lookup"><span data-stu-id="fb266-105">You cannot call it by simply using its name within an expression.</span></span>  
  
### <a name="to-call-a-sub-procedure"></a><span data-ttu-id="fb266-106">Sub プロシージャを呼び出すには</span><span class="sxs-lookup"><span data-stu-id="fb266-106">To call a Sub procedure</span></span>  
  
1. <span data-ttu-id="fb266-107">`Sub` プロシージャの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="fb266-107">Specify the name of the `Sub` procedure.</span></span>  
  
2. <span data-ttu-id="fb266-108">引数リストを囲むには、プロシージャ名をかっこで囲みます。</span><span class="sxs-lookup"><span data-stu-id="fb266-108">Follow the procedure name with parentheses to enclose the argument list.</span></span> <span data-ttu-id="fb266-109">引数がない場合は、必要に応じてかっこを省略できます。</span><span class="sxs-lookup"><span data-stu-id="fb266-109">If there are no arguments, you can optionally omit the parentheses.</span></span> <span data-ttu-id="fb266-110">ただし、かっこを使用すると、コードが読みやすくなります。</span><span class="sxs-lookup"><span data-stu-id="fb266-110">However, using the parentheses makes your code easier to read.</span></span>  
  
3. <span data-ttu-id="fb266-111">引数リストに引数をコンマで区切ってかっこ内に配置します。</span><span class="sxs-lookup"><span data-stu-id="fb266-111">Place the arguments in the argument list within the parentheses, separated by commas.</span></span> <span data-ttu-id="fb266-112">引数は、`Sub` プロシージャが対応するパラメーターを定義する順序と同じ順序で指定してください。</span><span class="sxs-lookup"><span data-stu-id="fb266-112">Be sure you supply the arguments in the same order that the `Sub` procedure defines the corresponding parameters.</span></span>  
  
     <span data-ttu-id="fb266-113">次の例では、Visual Basic <xref:Microsoft.VisualBasic.Interaction.AppActivate%2A> 関数を呼び出して、アプリケーションウィンドウをアクティブにします。</span><span class="sxs-lookup"><span data-stu-id="fb266-113">The following example calls the Visual Basic <xref:Microsoft.VisualBasic.Interaction.AppActivate%2A> function to activate an application window.</span></span> <span data-ttu-id="fb266-114"><xref:Microsoft.VisualBasic.Interaction.AppActivate%2A> は、ウィンドウのタイトルを唯一の引数として受け取ります。</span><span class="sxs-lookup"><span data-stu-id="fb266-114"><xref:Microsoft.VisualBasic.Interaction.AppActivate%2A> takes the window title as its sole argument.</span></span> <span data-ttu-id="fb266-115">呼び出し元のコードに値は返されません。</span><span class="sxs-lookup"><span data-stu-id="fb266-115">It does not return a value to the calling code.</span></span> <span data-ttu-id="fb266-116">メモ帳のプロセスが実行されていない場合、この例では <xref:System.ArgumentException>がスローされます。</span><span class="sxs-lookup"><span data-stu-id="fb266-116">If a Notepad process is not running, the example throws an <xref:System.ArgumentException>.</span></span> <span data-ttu-id="fb266-117">`Shell` の手順では、アプリケーションが指定されたパスにあることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="fb266-117">The `Shell` procedure assumes the applications are in the paths specified.</span></span>  
  
     [!code-vb[VbVbalrCatRef#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCatRef/VB/Class1.vb#11)]  
  
## <a name="see-also"></a><span data-ttu-id="fb266-118">参照</span><span class="sxs-lookup"><span data-stu-id="fb266-118">See also</span></span>

- <xref:Microsoft.VisualBasic.Interaction.Shell%2A>
- <xref:System.ArgumentException>
- [<span data-ttu-id="fb266-119">手順</span><span class="sxs-lookup"><span data-stu-id="fb266-119">Procedures</span></span>](./index.md)
- [<span data-ttu-id="fb266-120">Sub プロシージャ</span><span class="sxs-lookup"><span data-stu-id="fb266-120">Sub Procedures</span></span>](./sub-procedures.md)
- [<span data-ttu-id="fb266-121">プロシージャのパラメーターと引数</span><span class="sxs-lookup"><span data-stu-id="fb266-121">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="fb266-122">Sub ステートメント</span><span class="sxs-lookup"><span data-stu-id="fb266-122">Sub Statement</span></span>](../../../../visual-basic/language-reference/statements/sub-statement.md)
- [<span data-ttu-id="fb266-123">方法 : プロシージャを作成する</span><span class="sxs-lookup"><span data-stu-id="fb266-123">How to: Create a Procedure</span></span>](./how-to-create-a-procedure.md)
- [<span data-ttu-id="fb266-124">方法: 値を返すプロシージャを呼び出す</span><span class="sxs-lookup"><span data-stu-id="fb266-124">How to: Call a Procedure That Returns a Value</span></span>](./how-to-call-a-procedure-that-returns-a-value.md)
- [<span data-ttu-id="fb266-125">方法: Visual Basic でイベントハンドラーを呼び出す</span><span class="sxs-lookup"><span data-stu-id="fb266-125">How to: Call an Event Handler in Visual Basic</span></span>](./how-to-call-an-event-handler.md)
