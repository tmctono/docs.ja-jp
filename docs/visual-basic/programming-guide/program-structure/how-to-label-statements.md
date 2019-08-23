---
title: '方法: ラベルステートメント (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- colons (:)
- statements [Visual Basic], labels
- ': separator character'
- Visual Basic code, labeling statements
ms.assetid: 38f1ff43-2054-42cb-963b-1998e60c6ed4
ms.openlocfilehash: 6b442b5a0ad731cfc490a7387c78ac9279dddaf0
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69961319"
---
# <a name="how-to-label-statements-visual-basic"></a><span data-ttu-id="00dab-102">方法: ラベルステートメント (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="00dab-102">How to: Label Statements (Visual Basic)</span></span>
<span data-ttu-id="00dab-103">ステートメントブロックは、コロンで区切られたコード行で構成されます。</span><span class="sxs-lookup"><span data-stu-id="00dab-103">Statement blocks are made up of lines of code delimited by colons.</span></span> <span data-ttu-id="00dab-104">識別文字列または整数で始まるコード行には、ラベルが*付け*られています。</span><span class="sxs-lookup"><span data-stu-id="00dab-104">Lines of code preceded by an identifying string or integer are said to be *labeled*.</span></span> <span data-ttu-id="00dab-105">ステートメントラベルは、など`On Error Goto`のステートメントで使用するために、コード行をマークするために使用されます。</span><span class="sxs-lookup"><span data-stu-id="00dab-105">Statement labels are used to mark a line of code to identify it for use with statements such as `On Error Goto`.</span></span>  
  
 <span data-ttu-id="00dab-106">ラベルは、プログラミング要素を識別する Visual Basic 識別子や、整数リテラルなど、有効な識別子である場合があります。</span><span class="sxs-lookup"><span data-stu-id="00dab-106">Labels may be either valid Visual Basic identifiers—such as those that identify programming elements—or integer literals.</span></span> <span data-ttu-id="00dab-107">ラベルは、ソースコードの行の先頭に記述する必要があります。また、同じ行にステートメントが続くかどうかに関係なく、コロンで続ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="00dab-107">A label must appear at the beginning of a line of source code and must be followed by a colon, regardless of whether it is followed by a statement on the same line.</span></span>  
  
 <span data-ttu-id="00dab-108">コンパイラは、行の先頭が既に定義されている識別子と一致するかどうかをチェックすることによって、ラベルを識別します。</span><span class="sxs-lookup"><span data-stu-id="00dab-108">The compiler identifies labels by checking whether the beginning of the line matches any already-defined identifier.</span></span> <span data-ttu-id="00dab-109">そうでない場合、コンパイラはこれがラベルであると見なします。</span><span class="sxs-lookup"><span data-stu-id="00dab-109">If it does not, the compiler assumes it is a label.</span></span>  
  
 <span data-ttu-id="00dab-110">ラベルには独自の宣言領域があり、他の識別子に干渉することはありません。</span><span class="sxs-lookup"><span data-stu-id="00dab-110">Labels have their own declaration space and do not interfere with other identifiers.</span></span> <span data-ttu-id="00dab-111">ラベルのスコープは、メソッドの本体です。</span><span class="sxs-lookup"><span data-stu-id="00dab-111">A label's scope is the body of the method.</span></span> <span data-ttu-id="00dab-112">ラベル宣言は、あいまいな状況で優先されます。</span><span class="sxs-lookup"><span data-stu-id="00dab-112">Label declaration takes precedence in any ambiguous situation.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="00dab-113">ラベルは、メソッド内の実行可能なステートメントでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="00dab-113">Labels can be used only on executable statements inside methods.</span></span>  
  
### <a name="to-label-a-line-of-code"></a><span data-ttu-id="00dab-114">コード行にラベルを付けるには</span><span class="sxs-lookup"><span data-stu-id="00dab-114">To label a line of code</span></span>  
  
- <span data-ttu-id="00dab-115">ソースコード行の先頭に、識別子、コロン、コロンの順に配置します。</span><span class="sxs-lookup"><span data-stu-id="00dab-115">Place an identifier, followed by a colon, at the beginning of the line of source code.</span></span>  
  
     <span data-ttu-id="00dab-116">たとえば、次のコード行は、それぞれ`Jump`および`120`でラベル付けされています。</span><span class="sxs-lookup"><span data-stu-id="00dab-116">For example, the following lines of code are labeled with `Jump` and `120`, respectively:</span></span>  
  
     [!code-vb[VbVbalrStatements#708](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#708)]  
  
## <a name="see-also"></a><span data-ttu-id="00dab-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="00dab-117">See also</span></span>

- [<span data-ttu-id="00dab-118">ステートメント</span><span class="sxs-lookup"><span data-stu-id="00dab-118">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
- [<span data-ttu-id="00dab-119">Declared Element Names</span><span class="sxs-lookup"><span data-stu-id="00dab-119">Declared Element Names</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)
- [<span data-ttu-id="00dab-120">プログラム構造とコード規則</span><span class="sxs-lookup"><span data-stu-id="00dab-120">Program Structure and Code Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)
