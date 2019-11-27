---
title: コード内の要素名としてのキーワード
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, naming conventions
- keywords [Visual Basic], in code
- name conflicts [Visual Basic]
- element names [Visual Basic], in code
ms.assetid: 2e4e8e02-23f7-49b9-a1c8-2b0402b6b525
ms.openlocfilehash: 4cdcda7c5c78481af1633bf29d75070c521ab393
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347388"
---
# <a name="keywords-as-element-names-in-code-visual-basic"></a><span data-ttu-id="341e5-102">コード内の要素名としてのキーワード (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="341e5-102">Keywords as Element Names in Code (Visual Basic)</span></span>
<span data-ttu-id="341e5-103">すべてのプログラム要素 (変数、クラス、メンバーなど) は、制限付きキーワードと同じ名前を持つことができます。</span><span class="sxs-lookup"><span data-stu-id="341e5-103">Any program element — such as a variable, class, or member — can have the same name as a restricted keyword.</span></span> <span data-ttu-id="341e5-104">たとえば、`Loop`という名前の変数を作成できます。</span><span class="sxs-lookup"><span data-stu-id="341e5-104">For example, you can create a variable named `Loop`.</span></span> <span data-ttu-id="341e5-105">ただし、制限された `Loop` キーワードと同じ名前を持つバージョンを参照するには、次の例に示すように、完全修飾文字列を使用するか、角かっこ (`[ ]`) で囲む必要があります。</span><span class="sxs-lookup"><span data-stu-id="341e5-105">However, to refer to your version of it — which has the same name as the restricted `Loop` keyword — you must either precede it with a full qualification string or enclose it in square brackets (`[ ]`), as the following example shows.</span></span>  
  
 [!code-vb[VbVbcnConventions#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#8)]  
  
 <span data-ttu-id="341e5-106">これらのいずれも実行しない場合、Visual Basic は、次の例に示すように、組み込みの `Loop` キーワードを使用することを前提として、エラーを生成します。</span><span class="sxs-lookup"><span data-stu-id="341e5-106">If you do not do either of these, then Visual Basic assumes use of the intrinsic `Loop` keyword and produces an error, as in the following example:</span></span>  
  
 `' The following statement causes a compiler error.`  
  
 `Loop.Visible = True`  
  
 <span data-ttu-id="341e5-107">フォームとコントロールを参照する場合や、変数を宣言する場合、または制限されたキーワードと同じ名前のプロシージャを定義する場合は、角かっこを使用できます。</span><span class="sxs-lookup"><span data-stu-id="341e5-107">You can use square brackets when referring to forms and controls, and when declaring a variable or defining a procedure with the same name as a restricted keyword.</span></span> <span data-ttu-id="341e5-108">名前を修飾したり、角かっこを含めたりすることは簡単ではありません。したがって、コードにエラーが発生して読みにくくなります。</span><span class="sxs-lookup"><span data-stu-id="341e5-108">It can be easy to forget to qualify names or include square brackets, and thus introduce errors into your code and make it harder to read.</span></span> <span data-ttu-id="341e5-109">このため、プログラム要素の名前として制限付きキーワードを使用しないことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="341e5-109">For this reason, we recommend that you not use restricted keywords as the names of program elements.</span></span> <span data-ttu-id="341e5-110">ただし、Visual Basic の将来のバージョンで、既存のフォーム名またはコントロール名と競合する新しいキーワードが定義されている場合は、新しいバージョンで動作するようにコードを更新するときに、この手法を使用できます。</span><span class="sxs-lookup"><span data-stu-id="341e5-110">However, if a future version of Visual Basic defines a new keyword that conflicts with an existing form or control name, then you can use this technique when updating your code to work with the new version.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="341e5-111">プログラムには、他の参照アセンブリによって提供される要素名を含めることもできます。</span><span class="sxs-lookup"><span data-stu-id="341e5-111">Your program also might include element names provided by other referenced assemblies.</span></span> <span data-ttu-id="341e5-112">これらの名前が制限付きキーワードと競合している場合は、角かっこを配置すると、Visual Basic によって定義済みの要素として解釈されます。</span><span class="sxs-lookup"><span data-stu-id="341e5-112">If these names conflict with restricted keywords, then placing square brackets around them causes Visual Basic to interpret them as your defined elements.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="341e5-113">参照</span><span class="sxs-lookup"><span data-stu-id="341e5-113">See also</span></span>

- [<span data-ttu-id="341e5-114">Visual Basic 名前付け規則</span><span class="sxs-lookup"><span data-stu-id="341e5-114">Visual Basic Naming Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)
- [<span data-ttu-id="341e5-115">プログラム構造とコード規則</span><span class="sxs-lookup"><span data-stu-id="341e5-115">Program Structure and Code Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)
- [<span data-ttu-id="341e5-116">キーワード</span><span class="sxs-lookup"><span data-stu-id="341e5-116">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
