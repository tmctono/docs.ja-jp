---
title: '方法: ラベル ステートメント (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- colons (:)
- statements [Visual Basic], labels
- ': separator character'
- Visual Basic code, labeling statements
ms.assetid: 38f1ff43-2054-42cb-963b-1998e60c6ed4
ms.openlocfilehash: 2f6f0362fcec170e677d153ad9f936a5c2e55ad7
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/28/2019
ms.locfileid: "56981206"
---
# <a name="how-to-label-statements-visual-basic"></a><span data-ttu-id="dfdb3-102">方法: ラベル ステートメント (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="dfdb3-102">How to: Label Statements (Visual Basic)</span></span>
<span data-ttu-id="dfdb3-103">ステートメント ブロックはコロンで区切られたコードの行で構成をされます。</span><span class="sxs-lookup"><span data-stu-id="dfdb3-103">Statement blocks are made up of lines of code delimited by colons.</span></span> <span data-ttu-id="dfdb3-104">行の識別文字列または整数に続くコードがあると言われますは*というラベルの付いた*します。</span><span class="sxs-lookup"><span data-stu-id="dfdb3-104">Lines of code preceded by an identifying string or integer are said to be *labeled*.</span></span> <span data-ttu-id="dfdb3-105">ステートメント ラベルは識別するために、使用するためのステートメントでなどのコード行をマークするために使用`On Error Goto`します。</span><span class="sxs-lookup"><span data-stu-id="dfdb3-105">Statement labels are used to mark a line of code to identify it for use with statements such as `On Error Goto`.</span></span>  
  
 <span data-ttu-id="dfdb3-106">ラベルとして使用できるは、有効な Visual Basic 識別子、プログラミング要素を識別するようなまたは整数リテラル。</span><span class="sxs-lookup"><span data-stu-id="dfdb3-106">Labels may be either valid Visual Basic identifiers—such as those that identify programming elements—or integer literals.</span></span> <span data-ttu-id="dfdb3-107">ラベルは、ソース コードの行の先頭に表示する必要があり、かどうかに続くステートメントで同じ行に関係なく、コロンの後にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="dfdb3-107">A label must appear at the beginning of a line of source code and must be followed by a colon, regardless of whether it is followed by a statement on the same line.</span></span>  
  
 <span data-ttu-id="dfdb3-108">コンパイラは、行の先頭に任意に定義済みの識別子が一致するかどうかをチェックして、ラベルを識別します。</span><span class="sxs-lookup"><span data-stu-id="dfdb3-108">The compiler identifies labels by checking whether the beginning of the line matches any already-defined identifier.</span></span> <span data-ttu-id="dfdb3-109">そうでない場合、コンパイラでは、ラベルが前提としています。</span><span class="sxs-lookup"><span data-stu-id="dfdb3-109">If it does not, the compiler assumes it is a label.</span></span>  
  
 <span data-ttu-id="dfdb3-110">ラベルは、独自の宣言領域があるし、他の識別子に干渉することはできません。</span><span class="sxs-lookup"><span data-stu-id="dfdb3-110">Labels have their own declaration space and do not interfere with other identifiers.</span></span> <span data-ttu-id="dfdb3-111">ラベルのスコープは、メソッドの本体です。</span><span class="sxs-lookup"><span data-stu-id="dfdb3-111">A label's scope is the body of the method.</span></span> <span data-ttu-id="dfdb3-112">ラベルの宣言は、あいまいな場合でも優先されます。</span><span class="sxs-lookup"><span data-stu-id="dfdb3-112">Label declaration takes precedence in any ambiguous situation.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="dfdb3-113">ラベルは、メソッド内で実行可能ステートメントでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="dfdb3-113">Labels can be used only on executable statements inside methods.</span></span>  
  
### <a name="to-label-a-line-of-code"></a><span data-ttu-id="dfdb3-114">ラベルのコード行に</span><span class="sxs-lookup"><span data-stu-id="dfdb3-114">To label a line of code</span></span>  
  
-   <span data-ttu-id="dfdb3-115">識別子の後にソース コードの行の先頭のコロンを配置します。</span><span class="sxs-lookup"><span data-stu-id="dfdb3-115">Place an identifier, followed by a colon, at the beginning of the line of source code.</span></span>  
  
     <span data-ttu-id="dfdb3-116">たとえば、次のコード行ラベルが付けられます`Jump`と`120`、それぞれします。</span><span class="sxs-lookup"><span data-stu-id="dfdb3-116">For example, the following lines of code are labeled with `Jump` and `120`, respectively:</span></span>  
  
     [!code-vb[VbVbalrStatements#708](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#708)]  
  
## <a name="see-also"></a><span data-ttu-id="dfdb3-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="dfdb3-117">See also</span></span>
- [<span data-ttu-id="dfdb3-118">ステートメント</span><span class="sxs-lookup"><span data-stu-id="dfdb3-118">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
- [<span data-ttu-id="dfdb3-119">宣言された要素の名前</span><span class="sxs-lookup"><span data-stu-id="dfdb3-119">Declared Element Names</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)
- [<span data-ttu-id="dfdb3-120">プログラム構造とコード規則</span><span class="sxs-lookup"><span data-stu-id="dfdb3-120">Program Structure and Code Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)
