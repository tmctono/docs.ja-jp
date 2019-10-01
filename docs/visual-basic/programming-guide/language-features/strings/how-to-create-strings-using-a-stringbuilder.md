---
title: '方法: Visual Basic の StringBuilder を使用して文字列を作成する'
ms.date: 07/20/2015
helpviewer_keywords:
- StringBuilder class
- strings [Visual Basic], using StringBuilder
ms.assetid: 9c042880-aa16-432e-9ccb-cd00abda9ae3
ms.openlocfilehash: 19e036abc9d25ec7fdfd6c33ebb420ec4f503cbc
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2019
ms.locfileid: "71700103"
---
# <a name="how-to-create-strings-using-a-stringbuilder-in-visual-basic"></a><span data-ttu-id="72ddc-102">方法: Visual Basic の StringBuilder を使用して文字列を作成する</span><span class="sxs-lookup"><span data-stu-id="72ddc-102">How to: create strings using a StringBuilder in Visual Basic</span></span>

<span data-ttu-id="72ddc-103">この例では、<xref:System.Text.StringBuilder> クラスを使用して、多数の小さい文字列から長い文字列を構築します。</span><span class="sxs-lookup"><span data-stu-id="72ddc-103">This example constructs a long string from many smaller strings using the <xref:System.Text.StringBuilder> class.</span></span> <span data-ttu-id="72ddc-104">@No__t-0 クラスは、多数の文字列を連結するための `&=` 演算子よりも効率的です。</span><span class="sxs-lookup"><span data-stu-id="72ddc-104">The <xref:System.Text.StringBuilder> class is more efficient than the `&=` operator for concatenating many strings.</span></span>

## <a name="example"></a><span data-ttu-id="72ddc-105">例</span><span class="sxs-lookup"><span data-stu-id="72ddc-105">Example</span></span>

<span data-ttu-id="72ddc-106">次の例では、@no__t 0 クラスのインスタンスを作成し、そのインスタンスに1000文字列を追加して、その文字列形式を返します。</span><span class="sxs-lookup"><span data-stu-id="72ddc-106">The following example creates an instance of the <xref:System.Text.StringBuilder> class, appends 1,000 strings to that instance, and then returns its string representation:</span></span>

 [!code-vb[VbVbalrStrings#70](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#70)]

## <a name="see-also"></a><span data-ttu-id="72ddc-107">関連項目</span><span class="sxs-lookup"><span data-stu-id="72ddc-107">See also</span></span>

- [<span data-ttu-id="72ddc-108">StringBuilder クラスの使用</span><span class="sxs-lookup"><span data-stu-id="72ddc-108">Using the StringBuilder Class</span></span>](../../../../standard/base-types/stringbuilder.md)
- [<span data-ttu-id="72ddc-109">& = 演算子</span><span class="sxs-lookup"><span data-stu-id="72ddc-109">&= Operator</span></span>](../../../language-reference/operators/and-assignment-operator.md)
- [<span data-ttu-id="72ddc-110">文字列</span><span class="sxs-lookup"><span data-stu-id="72ddc-110">Strings</span></span>](index.md)
- [<span data-ttu-id="72ddc-111">新しい文字列の作成</span><span class="sxs-lookup"><span data-stu-id="72ddc-111">Creating New Strings</span></span>](../../../../standard/base-types/creating-new.md)
- [<span data-ttu-id="72ddc-112">文字列の操作</span><span class="sxs-lookup"><span data-stu-id="72ddc-112">Manipulating Strings</span></span>](../../../../standard/base-types/manipulating-strings.md)
