---
title: '方法: Visual Basic では、StringBuilder を使用して文字列を作成します。'
ms.date: 07/20/2015
helpviewer_keywords:
- StringBuilder class
- strings [Visual Basic], using StringBuilder
ms.assetid: 9c042880-aa16-432e-9ccb-cd00abda9ae3
ms.openlocfilehash: 00fefcc138164288d872cd339f165dc6ffc0131a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62032126"
---
# <a name="how-to-create-strings-using-a-stringbuilder-in-visual-basic"></a><span data-ttu-id="2edb7-102">方法: Visual Basic では、StringBuilder を使用して文字列を作成します。</span><span class="sxs-lookup"><span data-stu-id="2edb7-102">How to: Create Strings Using a StringBuilder in Visual Basic</span></span>
<span data-ttu-id="2edb7-103">この例を使用して多数の小さな文字列から長い文字列を構築します、<xref:System.Text.StringBuilder>クラス。</span><span class="sxs-lookup"><span data-stu-id="2edb7-103">This example constructs a long string from many smaller strings using the <xref:System.Text.StringBuilder> class.</span></span> <span data-ttu-id="2edb7-104"><xref:System.Text.StringBuilder>クラスより効率的、`&=`演算子の多くの文字列を連結します。</span><span class="sxs-lookup"><span data-stu-id="2edb7-104">The <xref:System.Text.StringBuilder> class is more efficient than the `&=` operator for concatenating many strings.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2edb7-105">例</span><span class="sxs-lookup"><span data-stu-id="2edb7-105">Example</span></span>  
 <span data-ttu-id="2edb7-106">次の例のインスタンスを作成する、<xref:System.Text.StringBuilder>クラス、1,000 の文字列をそのインスタンスに追加し、その文字列表現を返します。</span><span class="sxs-lookup"><span data-stu-id="2edb7-106">The following example creates an instance of the <xref:System.Text.StringBuilder> class, appends 1,000 strings to that instance, and then returns its string representation.</span></span>  
  
 [!code-vb[VbVbalrStrings#70](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#70)]  
  
## <a name="see-also"></a><span data-ttu-id="2edb7-107">関連項目</span><span class="sxs-lookup"><span data-stu-id="2edb7-107">See also</span></span>

- [<span data-ttu-id="2edb7-108">StringBuilder クラスの使用</span><span class="sxs-lookup"><span data-stu-id="2edb7-108">Using the StringBuilder Class</span></span>](../../../../standard/base-types/stringbuilder.md)
- [<span data-ttu-id="2edb7-109">& = 演算子</span><span class="sxs-lookup"><span data-stu-id="2edb7-109">&= Operator</span></span>](../../../../visual-basic/language-reference/operators/and-assignment-operator.md)
- [<span data-ttu-id="2edb7-110">文字列</span><span class="sxs-lookup"><span data-stu-id="2edb7-110">Strings</span></span>](../../../../visual-basic/programming-guide/language-features/strings/index.md)
- [<span data-ttu-id="2edb7-111">新しい文字列の作成</span><span class="sxs-lookup"><span data-stu-id="2edb7-111">Creating New Strings</span></span>](../../../../standard/base-types/creating-new.md)
- [<span data-ttu-id="2edb7-112">文字列の操作</span><span class="sxs-lookup"><span data-stu-id="2edb7-112">Manipulating Strings</span></span>](../../../../standard/base-types/manipulating-strings.md)
