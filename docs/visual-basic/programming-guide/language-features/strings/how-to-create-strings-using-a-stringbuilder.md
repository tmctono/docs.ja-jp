---
title: '方法: StringBuilder を使用して文字列を作成する'
ms.date: 07/20/2015
helpviewer_keywords:
- StringBuilder class
- strings [Visual Basic], using StringBuilder
ms.assetid: 9c042880-aa16-432e-9ccb-cd00abda9ae3
ms.openlocfilehash: c41db584df83782dab99b90043045aa2cabcb6ff
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/20/2020
ms.locfileid: "81645325"
---
# <a name="how-to-create-strings-using-a-stringbuilder-in-visual-basic"></a><span data-ttu-id="f7f3d-102">方法: Visual Basic の StringBuilder を使用して文字列を作成する</span><span class="sxs-lookup"><span data-stu-id="f7f3d-102">How to: create strings using a StringBuilder in Visual Basic</span></span>

<span data-ttu-id="f7f3d-103">この例では、<xref:System.Text.StringBuilder> クラスを使用して、多数の短い文字列から長い文字列を作成します。</span><span class="sxs-lookup"><span data-stu-id="f7f3d-103">This example constructs a long string from many smaller strings using the <xref:System.Text.StringBuilder> class.</span></span> <span data-ttu-id="f7f3d-104">多数の文字列を連結する場合、<xref:System.Text.StringBuilder> クラスは `&=` 演算子よりも効率的です。</span><span class="sxs-lookup"><span data-stu-id="f7f3d-104">The <xref:System.Text.StringBuilder> class is more efficient than the `&=` operator for concatenating many strings.</span></span>

## <a name="example"></a><span data-ttu-id="f7f3d-105">例</span><span class="sxs-lookup"><span data-stu-id="f7f3d-105">Example</span></span>

<span data-ttu-id="f7f3d-106">次の例では、<xref:System.Text.StringBuilder> クラスのインスタンスを作成し、そのインスタンスに 1,000 個の文字列を追加した後、その文字列表現を返します。</span><span class="sxs-lookup"><span data-stu-id="f7f3d-106">The following example creates an instance of the <xref:System.Text.StringBuilder> class, appends 1,000 strings to that instance, and then returns its string representation:</span></span>

 [!code-vb[VbVbalrStrings#70](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#70)]

## <a name="see-also"></a><span data-ttu-id="f7f3d-107">関連項目</span><span class="sxs-lookup"><span data-stu-id="f7f3d-107">See also</span></span>

- [<span data-ttu-id="f7f3d-108">StringBuilder クラスの使用</span><span class="sxs-lookup"><span data-stu-id="f7f3d-108">Using the StringBuilder Class</span></span>](../../../../standard/base-types/stringbuilder.md)
- [<span data-ttu-id="f7f3d-109">& = 演算子</span><span class="sxs-lookup"><span data-stu-id="f7f3d-109">&= Operator</span></span>](../../../language-reference/operators/and-assignment-operator.md)
- [<span data-ttu-id="f7f3d-110">文字列</span><span class="sxs-lookup"><span data-stu-id="f7f3d-110">Strings</span></span>](index.md)
- [<span data-ttu-id="f7f3d-111">新しい文字列の作成</span><span class="sxs-lookup"><span data-stu-id="f7f3d-111">Creating New Strings</span></span>](../../../../standard/base-types/creating-new.md)
- [<span data-ttu-id="f7f3d-112">文字列の操作</span><span class="sxs-lookup"><span data-stu-id="f7f3d-112">Manipulating Strings</span></span>](../../../../standard/base-types/best-practices-strings.md)
