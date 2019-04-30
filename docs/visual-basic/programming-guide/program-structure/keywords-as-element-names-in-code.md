---
title: コード内の要素名としてのキーワード (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, naming conventions
- keywords [Visual Basic], in code
- name conflicts [Visual Basic]
- element names [Visual Basic], in code
ms.assetid: 2e4e8e02-23f7-49b9-a1c8-2b0402b6b525
ms.openlocfilehash: c247ada67f6554362f287cf252dd49856c4995da
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61955585"
---
# <a name="keywords-as-element-names-in-code-visual-basic"></a><span data-ttu-id="3ae3f-102">コード内の要素名としてのキーワード (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3ae3f-102">Keywords as Element Names in Code (Visual Basic)</span></span>
<span data-ttu-id="3ae3f-103">すべてのプログラム要素-変数、クラス、またはメンバーなど、予約されたキーワードと同じ名前を持つことができます。</span><span class="sxs-lookup"><span data-stu-id="3ae3f-103">Any program element — such as a variable, class, or member — can have the same name as a restricted keyword.</span></span> <span data-ttu-id="3ae3f-104">たとえば、という名前の変数を作成することができます`Loop`します。</span><span class="sxs-lookup"><span data-stu-id="3ae3f-104">For example, you can create a variable named `Loop`.</span></span> <span data-ttu-id="3ae3f-105">ただし、そのバージョンを参照する —、制限されたのと同じ名前を持つ`Loop`キーワード-先頭の完全修飾文字列か、角かっこで囲む必要があります (`[ ]`) 次の例に示すように。</span><span class="sxs-lookup"><span data-stu-id="3ae3f-105">However, to refer to your version of it — which has the same name as the restricted `Loop` keyword — you must either precede it with a full qualification string or enclose it in square brackets (`[ ]`), as the following example shows.</span></span>  
  
 [!code-vb[VbVbcnConventions#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#8)]  
  
 <span data-ttu-id="3ae3f-106">これらのうち、どちらも行わないかどうかは、Visual Basic、組み込みの使用を前提としています`Loop`キーワードと、次の例のように、エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="3ae3f-106">If you do not do either of these, then Visual Basic assumes use of the intrinsic `Loop` keyword and produces an error, as in the following example:</span></span>  
  
 `' The following statement causes a compiler error.`  
  
 `Loop.Visible = True`  
  
 <span data-ttu-id="3ae3f-107">角かっこを使用するには、フォームとコントロールを参照するとき、および変数を宣言するか、予約キーワードと同じ名前のプロシージャを定義します。</span><span class="sxs-lookup"><span data-stu-id="3ae3f-107">You can use square brackets when referring to forms and controls, and when declaring a variable or defining a procedure with the same name as a restricted keyword.</span></span> <span data-ttu-id="3ae3f-108">名を修飾するまたは、角かっこを含めるとため、コードにエラーが発生し、読みにくくなるし忘れることができます。</span><span class="sxs-lookup"><span data-stu-id="3ae3f-108">It can be easy to forget to qualify names or include square brackets, and thus introduce errors into your code and make it harder to read.</span></span> <span data-ttu-id="3ae3f-109">このため、プログラム要素の名前として予約キーワードを使用しないことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="3ae3f-109">For this reason, we recommend that you not use restricted keywords as the names of program elements.</span></span> <span data-ttu-id="3ae3f-110">ただし、将来のバージョンの Visual Basic では、既存のフォームまたはコントロールの名前と競合する新しいキーワードを定義する場合しすることができますを使用して、この手法、コードを更新するときに、新しいバージョンを使用します。</span><span class="sxs-lookup"><span data-stu-id="3ae3f-110">However, if a future version of Visual Basic defines a new keyword that conflicts with an existing form or control name, then you can use this technique when updating your code to work with the new version.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3ae3f-111">プログラムは、他の参照先アセンブリによって提供される要素名もなどがあります。</span><span class="sxs-lookup"><span data-stu-id="3ae3f-111">Your program also might include element names provided by other referenced assemblies.</span></span> <span data-ttu-id="3ae3f-112">これらの名前が制限されているキーワードと競合する場合は、Visual Basic は定義された要素として解釈すると、周囲に角かっこでいます。</span><span class="sxs-lookup"><span data-stu-id="3ae3f-112">If these names conflict with restricted keywords, then placing square brackets around them causes Visual Basic to interpret them as your defined elements.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ae3f-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="3ae3f-113">See also</span></span>

- [<span data-ttu-id="3ae3f-114">Visual Basic の名前付け規則</span><span class="sxs-lookup"><span data-stu-id="3ae3f-114">Visual Basic Naming Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)
- [<span data-ttu-id="3ae3f-115">プログラム構造とコード規則</span><span class="sxs-lookup"><span data-stu-id="3ae3f-115">Program Structure and Code Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)
- [<span data-ttu-id="3ae3f-116">キーワード</span><span class="sxs-lookup"><span data-stu-id="3ae3f-116">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
