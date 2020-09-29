---
title: '方法: 値を返さないプロシージャを呼び出す'
ms.date: 07/20/2015
helpviewer_keywords:
- procedure calls [Visual Basic], returning values
- Visual Basic code, procedures
- procedures [Visual Basic], calling
ms.assetid: 259b49a3-a3c1-4254-ba8c-73cdc4127703
ms.openlocfilehash: 2686a4d9dc10cde209f558771feeb5ba4f4ccb21
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2020
ms.locfileid: "91075006"
---
# <a name="how-to-call-a-procedure-that-does-not-return-a-value-visual-basic"></a><span data-ttu-id="ab30b-102">方法: 値を返さないプロシージャを呼び出す (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ab30b-102">How to: Call a Procedure that Does Not Return a Value (Visual Basic)</span></span>

<span data-ttu-id="ab30b-103">`Sub` プロシージャから呼び出し元コードに対しては値が返されません。</span><span class="sxs-lookup"><span data-stu-id="ab30b-103">A `Sub` procedure does not return a value to the calling code.</span></span> <span data-ttu-id="ab30b-104">これは、スタンドアロンの呼び出し元ステートメントを使用して明示的に呼び出します。</span><span class="sxs-lookup"><span data-stu-id="ab30b-104">You call it explicitly with a stand-alone calling statement.</span></span> <span data-ttu-id="ab30b-105">式内でその名前を使用するだけでは呼び出せません。</span><span class="sxs-lookup"><span data-stu-id="ab30b-105">You cannot call it by simply using its name within an expression.</span></span>  
  
### <a name="to-call-a-sub-procedure"></a><span data-ttu-id="ab30b-106">Sub プロシージャを呼び出すには</span><span class="sxs-lookup"><span data-stu-id="ab30b-106">To call a Sub procedure</span></span>  
  
1. <span data-ttu-id="ab30b-107">`Sub` プロシージャの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="ab30b-107">Specify the name of the `Sub` procedure.</span></span>  
  
2. <span data-ttu-id="ab30b-108">プロシージャ名の後にかっこを使用して引数リストを囲みます。</span><span class="sxs-lookup"><span data-stu-id="ab30b-108">Follow the procedure name with parentheses to enclose the argument list.</span></span> <span data-ttu-id="ab30b-109">引数がない場合は、必要に応じてかっこを省略できます。</span><span class="sxs-lookup"><span data-stu-id="ab30b-109">If there are no arguments, you can optionally omit the parentheses.</span></span> <span data-ttu-id="ab30b-110">ただし、かっこを使用すると、コードが読みやすくなります。</span><span class="sxs-lookup"><span data-stu-id="ab30b-110">However, using the parentheses makes your code easier to read.</span></span>  
  
3. <span data-ttu-id="ab30b-111">引数リストの引数をコンマで区切ってかっこ内に配置します。</span><span class="sxs-lookup"><span data-stu-id="ab30b-111">Place the arguments in the argument list within the parentheses, separated by commas.</span></span> <span data-ttu-id="ab30b-112">引数の指定は必ず、`Sub` プロシージャで定義されている対応するパラメーターと同じ順序で行ってください。</span><span class="sxs-lookup"><span data-stu-id="ab30b-112">Be sure you supply the arguments in the same order that the `Sub` procedure defines the corresponding parameters.</span></span>  
  
     <span data-ttu-id="ab30b-113">次の例では、Visual Basic <xref:Microsoft.VisualBasic.Interaction.AppActivate%2A> 関数を呼び出して、アプリケーション ウィンドウをアクティブにします。</span><span class="sxs-lookup"><span data-stu-id="ab30b-113">The following example calls the Visual Basic <xref:Microsoft.VisualBasic.Interaction.AppActivate%2A> function to activate an application window.</span></span> <span data-ttu-id="ab30b-114"><xref:Microsoft.VisualBasic.Interaction.AppActivate%2A> は、ウィンドウ タイトルを唯一の引数として受け取ります。</span><span class="sxs-lookup"><span data-stu-id="ab30b-114"><xref:Microsoft.VisualBasic.Interaction.AppActivate%2A> takes the window title as its sole argument.</span></span> <span data-ttu-id="ab30b-115">呼び出し元のコードには値が返されません。</span><span class="sxs-lookup"><span data-stu-id="ab30b-115">It does not return a value to the calling code.</span></span> <span data-ttu-id="ab30b-116">メモ帳プロセスが実行されていない場合、この例では <xref:System.ArgumentException> がスローされます。</span><span class="sxs-lookup"><span data-stu-id="ab30b-116">If a Notepad process is not running, the example throws an <xref:System.ArgumentException>.</span></span> <span data-ttu-id="ab30b-117">`Shell` プロシージャでは、アプリケーションが指定されたパスにあることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="ab30b-117">The `Shell` procedure assumes the applications are in the paths specified.</span></span>  
  
     [!code-vb[VbVbalrCatRef#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCatRef/VB/Class1.vb#11)]  
  
## <a name="see-also"></a><span data-ttu-id="ab30b-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="ab30b-118">See also</span></span>

- <xref:Microsoft.VisualBasic.Interaction.Shell%2A>
- <xref:System.ArgumentException>
- [<span data-ttu-id="ab30b-119">手順</span><span class="sxs-lookup"><span data-stu-id="ab30b-119">Procedures</span></span>](./index.md)
- [<span data-ttu-id="ab30b-120">Sub プロシージャ</span><span class="sxs-lookup"><span data-stu-id="ab30b-120">Sub Procedures</span></span>](./sub-procedures.md)
- [<span data-ttu-id="ab30b-121">プロシージャのパラメーターと引数</span><span class="sxs-lookup"><span data-stu-id="ab30b-121">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="ab30b-122">Sub ステートメント</span><span class="sxs-lookup"><span data-stu-id="ab30b-122">Sub Statement</span></span>](../../../language-reference/statements/sub-statement.md)
- [<span data-ttu-id="ab30b-123">方法: プロシージャを作成する</span><span class="sxs-lookup"><span data-stu-id="ab30b-123">How to: Create a Procedure</span></span>](./how-to-create-a-procedure.md)
- [<span data-ttu-id="ab30b-124">方法: 値を返すプロシージャを呼び出す</span><span class="sxs-lookup"><span data-stu-id="ab30b-124">How to: Call a Procedure That Returns a Value</span></span>](./how-to-call-a-procedure-that-returns-a-value.md)
- [<span data-ttu-id="ab30b-125">方法: Visual Basic でイベント ハンドラーを呼び出す</span><span class="sxs-lookup"><span data-stu-id="ab30b-125">How to: Call an Event Handler in Visual Basic</span></span>](./how-to-call-an-event-handler.md)
