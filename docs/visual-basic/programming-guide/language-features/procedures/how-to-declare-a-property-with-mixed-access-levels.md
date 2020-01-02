---
title: '方法 : 複数のアクセス レベルを持つプロパティを宣言する'
ms.date: 07/20/2015
helpviewer_keywords:
- access levels [Visual Basic], properties
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- mixed access levels
- Visual Basic code, properties
- properties [Visual Basic], access levels
- Property statement [Visual Basic], declaring mixed access levels
ms.assetid: fdbb2d97-279a-4956-b26c-cbdfbc34915a
ms.openlocfilehash: d74e23f33fbf7d9d29ab84b9b1bd4fc08863ac48
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349697"
---
# <a name="how-to-declare-a-property-with-mixed-access-levels-visual-basic"></a><span data-ttu-id="21cd1-102">方法: 複数のアクセス レベルを持つプロパティを宣言する (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="21cd1-102">How to: Declare a Property with Mixed Access Levels (Visual Basic)</span></span>
<span data-ttu-id="21cd1-103">プロパティの `Get` および `Set` プロシージャのアクセスレベルを変更するには、`Property` ステートメントでより制限の緩いレベルを使用し、`Get` または `Set` ステートメントでより制限の厳しいレベルを使用できます。</span><span class="sxs-lookup"><span data-stu-id="21cd1-103">If you want the `Get` and `Set` procedures on a property to have different access levels, you can use the more permissive level in the `Property` statement and the more restrictive level in either the `Get` or `Set` statement.</span></span> <span data-ttu-id="21cd1-104">プロパティで混合アクセスレベルを使用するのは、コードの特定の部分がプロパティの値を取得できるようにする場合と、コードの他の部分で値を変更できるようにする場合です。</span><span class="sxs-lookup"><span data-stu-id="21cd1-104">You use mixed access levels on a property when you want certain parts of the code to be able to get the property's value, and certain other parts of the code to be able to change the value.</span></span>  
  
 <span data-ttu-id="21cd1-105">アクセスレベルの詳細については、「[Visual Basic でのアクセス レベル](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="21cd1-105">For more information on access levels, see [Access levels in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
### <a name="to-declare-a-property-with-mixed-access-levels"></a><span data-ttu-id="21cd1-106">混合アクセスレベルを持つプロパティを宣言するには</span><span class="sxs-lookup"><span data-stu-id="21cd1-106">To declare a property with mixed access levels</span></span>  
  
1. <span data-ttu-id="21cd1-107">通常の方法でプロパティを宣言し、`Property` ステートメントで制限の緩いアクセスレベル (`Public`など) を指定します。</span><span class="sxs-lookup"><span data-stu-id="21cd1-107">Declare the property in the normal way, and specify the less restrictive access level (such as `Public`) in the `Property` statement.</span></span>  
  
2. <span data-ttu-id="21cd1-108">より厳しいアクセスレベル (`Friend`など) を指定する `Get` または `Set` プロシージャを宣言します。</span><span class="sxs-lookup"><span data-stu-id="21cd1-108">Declare either the `Get` or the `Set` procedure specifying the more restrictive access level (such as `Friend`).</span></span>  
  
3. <span data-ttu-id="21cd1-109">他のプロパティプロシージャにアクセスレベルを指定しないでください。</span><span class="sxs-lookup"><span data-stu-id="21cd1-109">Do not specify an access level on the other property procedure.</span></span> <span data-ttu-id="21cd1-110">`Property` ステートメントで宣言されたアクセスレベルを前提としています。</span><span class="sxs-lookup"><span data-stu-id="21cd1-110">It assumes the access level declared in the `Property` statement.</span></span> <span data-ttu-id="21cd1-111">アクセスは、プロパティプロシージャのいずれか1つに対してのみ制限できます。</span><span class="sxs-lookup"><span data-stu-id="21cd1-111">You can restrict access on only one of the property procedures.</span></span>  
  
     [!code-vb[VbVbcnProcedures#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#10)]  
  
     <span data-ttu-id="21cd1-112">前の例では、`Get` プロシージャは、プロパティ自体と同じ `Protected` アクセスを持ちますが、`Set` プロシージャは `Private` アクセスします。</span><span class="sxs-lookup"><span data-stu-id="21cd1-112">In the preceding example, the `Get` procedure has the same `Protected` access as the property itself, while the `Set` procedure has `Private` access.</span></span> <span data-ttu-id="21cd1-113">`employee` から派生したクラスは `salary` 値を読み取ることができますが、設定できるのは `employee` クラスだけです。</span><span class="sxs-lookup"><span data-stu-id="21cd1-113">A class derived from `employee` can read the `salary` value, but only the `employee` class can set it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21cd1-114">参照</span><span class="sxs-lookup"><span data-stu-id="21cd1-114">See also</span></span>

- [<span data-ttu-id="21cd1-115">Visual Basic におけるプロシージャ</span><span class="sxs-lookup"><span data-stu-id="21cd1-115">Procedures</span></span>](./index.md)
- [<span data-ttu-id="21cd1-116">Property プロシージャ</span><span class="sxs-lookup"><span data-stu-id="21cd1-116">Property Procedures</span></span>](./property-procedures.md)
- [<span data-ttu-id="21cd1-117">プロシージャのパラメーターと引数</span><span class="sxs-lookup"><span data-stu-id="21cd1-117">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="21cd1-118">Property ステートメント</span><span class="sxs-lookup"><span data-stu-id="21cd1-118">Property Statement</span></span>](../../../../visual-basic/language-reference/statements/property-statement.md)
- [<span data-ttu-id="21cd1-119">Visual Basic のプロパティと変数の違い</span><span class="sxs-lookup"><span data-stu-id="21cd1-119">Differences Between Properties and Variables in Visual Basic</span></span>](./differences-between-properties-and-variables.md)
- [<span data-ttu-id="21cd1-120">方法 : プロパティを作成する</span><span class="sxs-lookup"><span data-stu-id="21cd1-120">How to: Create a Property</span></span>](./how-to-create-a-property.md)
- [<span data-ttu-id="21cd1-121">方法 : プロパティ プロシージャを呼び出す</span><span class="sxs-lookup"><span data-stu-id="21cd1-121">How to: Call a Property Procedure</span></span>](./how-to-call-a-property-procedure.md)
- [<span data-ttu-id="21cd1-122">方法: Visual Basic で既定のプロパティを宣言して呼び出す</span><span class="sxs-lookup"><span data-stu-id="21cd1-122">How to: Declare and Call a Default Property in Visual Basic</span></span>](./how-to-declare-and-call-a-default-property.md)
- [<span data-ttu-id="21cd1-123">方法 : プロパティに値を格納する</span><span class="sxs-lookup"><span data-stu-id="21cd1-123">How to: Put a Value in a Property</span></span>](./how-to-put-a-value-in-a-property.md)
- [<span data-ttu-id="21cd1-124">方法 : プロパティから値を取得する</span><span class="sxs-lookup"><span data-stu-id="21cd1-124">How to: Get a Value from a Property</span></span>](./how-to-get-a-value-from-a-property.md)
