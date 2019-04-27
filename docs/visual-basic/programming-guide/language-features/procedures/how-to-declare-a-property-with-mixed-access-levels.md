---
title: '方法: 混合アクセス レベル (Visual Basic) を持つプロパティを宣言します。'
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
ms.openlocfilehash: e899b57e02f492b0e4909aca84c069e5b7688618
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61863689"
---
# <a name="how-to-declare-a-property-with-mixed-access-levels-visual-basic"></a><span data-ttu-id="802d8-102">方法: 混合アクセス レベル (Visual Basic) を持つプロパティを宣言します。</span><span class="sxs-lookup"><span data-stu-id="802d8-102">How to: Declare a Property with Mixed Access Levels (Visual Basic)</span></span>
<span data-ttu-id="802d8-103">場合は、`Get`と`Set`手順が異なるアクセス レベルのプロパティについてでより制限の緩やかなレベルを使用することができます、`Property`ステートメントといずれかより制限の厳しいレベル、`Get`または`Set`ステートメント。</span><span class="sxs-lookup"><span data-stu-id="802d8-103">If you want the `Get` and `Set` procedures on a property to have different access levels, you can use the more permissive level in the `Property` statement and the more restrictive level in either the `Get` or `Set` statement.</span></span> <span data-ttu-id="802d8-104">プロパティの値を取得できるコードの特定の部分と値を変更することができるコードの他の特定の部分を使う場合は、プロパティに混合アクセス レベルを使用します。</span><span class="sxs-lookup"><span data-stu-id="802d8-104">You use mixed access levels on a property when you want certain parts of the code to be able to get the property's value, and certain other parts of the code to be able to change the value.</span></span>  
  
 <span data-ttu-id="802d8-105">アクセス レベルの詳細については、次を参照してください。[アクセス レベルを Visual Basic で](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)します。</span><span class="sxs-lookup"><span data-stu-id="802d8-105">For more information on access levels, see [Access levels in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
### <a name="to-declare-a-property-with-mixed-access-levels"></a><span data-ttu-id="802d8-106">混合アクセス レベルを持つプロパティを宣言するには</span><span class="sxs-lookup"><span data-stu-id="802d8-106">To declare a property with mixed access levels</span></span>  
  
1. <span data-ttu-id="802d8-107">通常の方法でプロパティを宣言しより制限の少ないアクセス レベルを指定 (など`Public`) で、`Property`ステートメント。</span><span class="sxs-lookup"><span data-stu-id="802d8-107">Declare the property in the normal way, and specify the less restrictive access level (such as `Public`) in the `Property` statement.</span></span>  
  
2. <span data-ttu-id="802d8-108">いずれかを宣言、`Get`または`Set`より制限の厳しいアクセス レベルを指定する手順 (など`Friend`)。</span><span class="sxs-lookup"><span data-stu-id="802d8-108">Declare either the `Get` or the `Set` procedure specifying the more restrictive access level (such as `Friend`).</span></span>  
  
3. <span data-ttu-id="802d8-109">その他のプロパティ プロシージャでは、アクセス レベルを指定しません。</span><span class="sxs-lookup"><span data-stu-id="802d8-109">Do not specify an access level on the other property procedure.</span></span> <span data-ttu-id="802d8-110">アクセス レベルで宣言されていると想定して、`Property`ステートメント。</span><span class="sxs-lookup"><span data-stu-id="802d8-110">It assumes the access level declared in the `Property` statement.</span></span> <span data-ttu-id="802d8-111">プロパティ プロシージャの 1 つだけにアクセスを制限することができます。</span><span class="sxs-lookup"><span data-stu-id="802d8-111">You can restrict access on only one of the property procedures.</span></span>  
  
     [!code-vb[VbVbcnProcedures#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#10)]  
  
     <span data-ttu-id="802d8-112">前の例では、`Get`手順では、同じ`Protected`プロパティ自体としてのアクセス中に、`Set`手順では`Private`アクセス。</span><span class="sxs-lookup"><span data-stu-id="802d8-112">In the preceding example, the `Get` procedure has the same `Protected` access as the property itself, while the `Set` procedure has `Private` access.</span></span> <span data-ttu-id="802d8-113">派生したクラス`employee`読み取ることができます、`salary`値のみが、`employee`クラスで設定できます。</span><span class="sxs-lookup"><span data-stu-id="802d8-113">A class derived from `employee` can read the `salary` value, but only the `employee` class can set it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="802d8-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="802d8-114">See also</span></span>

- [<span data-ttu-id="802d8-115">プロシージャ</span><span class="sxs-lookup"><span data-stu-id="802d8-115">Procedures</span></span>](./index.md)
- [<span data-ttu-id="802d8-116">Property プロシージャ</span><span class="sxs-lookup"><span data-stu-id="802d8-116">Property Procedures</span></span>](./property-procedures.md)
- [<span data-ttu-id="802d8-117">プロシージャのパラメーターと引数</span><span class="sxs-lookup"><span data-stu-id="802d8-117">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="802d8-118">Property ステートメント</span><span class="sxs-lookup"><span data-stu-id="802d8-118">Property Statement</span></span>](../../../../visual-basic/language-reference/statements/property-statement.md)
- [<span data-ttu-id="802d8-119">Visual Basic でのプロパティと変数の違い</span><span class="sxs-lookup"><span data-stu-id="802d8-119">Differences Between Properties and Variables in Visual Basic</span></span>](./differences-between-properties-and-variables.md)
- [<span data-ttu-id="802d8-120">方法: プロパティを作成します。</span><span class="sxs-lookup"><span data-stu-id="802d8-120">How to: Create a Property</span></span>](./how-to-create-a-property.md)
- [<span data-ttu-id="802d8-121">方法: プロパティ プロシージャを呼び出す</span><span class="sxs-lookup"><span data-stu-id="802d8-121">How to: Call a Property Procedure</span></span>](./how-to-call-a-property-procedure.md)
- [<span data-ttu-id="802d8-122">方法: 宣言し、Visual Basic では、既定のプロパティを呼び出す</span><span class="sxs-lookup"><span data-stu-id="802d8-122">How to: Declare and Call a Default Property in Visual Basic</span></span>](./how-to-declare-and-call-a-default-property.md)
- [<span data-ttu-id="802d8-123">方法: プロパティに値を格納します。</span><span class="sxs-lookup"><span data-stu-id="802d8-123">How to: Put a Value in a Property</span></span>](./how-to-put-a-value-in-a-property.md)
- [<span data-ttu-id="802d8-124">方法: プロパティから値を取得します。</span><span class="sxs-lookup"><span data-stu-id="802d8-124">How to: Get a Value from a Property</span></span>](./how-to-get-a-value-from-a-property.md)
