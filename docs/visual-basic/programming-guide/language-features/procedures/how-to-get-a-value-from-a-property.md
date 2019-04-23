---
title: '方法: プロパティ (Visual Basic) から値を取得します。'
ms.date: 07/20/2015
helpviewer_keywords:
- property values [Visual Basic]
- Visual Basic code, procedures
- values [Visual Basic], properties
- Visual Basic code, properties
- properties [Visual Basic], values
ms.assetid: 3954423e-6ab7-4a4c-b55c-a8d27be47891
ms.openlocfilehash: 5e2676a0880092a78405fe5dafa0469161b85610
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59302934"
---
# <a name="how-to-get-a-value-from-a-property-visual-basic"></a><span data-ttu-id="0f586-102">方法: プロパティ (Visual Basic) から値を取得します。</span><span class="sxs-lookup"><span data-stu-id="0f586-102">How to: Get a Value from a Property (Visual Basic)</span></span>
<span data-ttu-id="0f586-103">プロパティの値を取得するには、式の中で、プロパティ名を含めます。</span><span class="sxs-lookup"><span data-stu-id="0f586-103">You retrieve a property's value by including the property name in an expression.</span></span>  
  
 <span data-ttu-id="0f586-104">プロパティの`Get`プロシージャが、値を取得しますが、明示的に呼び出さない場合、名前でします。</span><span class="sxs-lookup"><span data-stu-id="0f586-104">The property's `Get` procedure retrieves the value, but you do not explicitly call it by name.</span></span> <span data-ttu-id="0f586-105">変数を使用する場合と同様に、プロパティを使用するとします。</span><span class="sxs-lookup"><span data-stu-id="0f586-105">You use the property just as you would use a variable.</span></span> <span data-ttu-id="0f586-106">Visual Basic では、プロパティのプロシージャ呼び出しを行います。</span><span class="sxs-lookup"><span data-stu-id="0f586-106">Visual Basic makes the calls to the property's procedures.</span></span>  
  
### <a name="to-retrieve-a-value-from-a-property"></a><span data-ttu-id="0f586-107">プロパティの値を取得するには</span><span class="sxs-lookup"><span data-stu-id="0f586-107">To retrieve a value from a property</span></span>  
  
1. <span data-ttu-id="0f586-108">式、変数名を使用する場合と同じ方法でプロパティ名を使用します。</span><span class="sxs-lookup"><span data-stu-id="0f586-108">Use the property name in an expression the same way you would use a variable name.</span></span> <span data-ttu-id="0f586-109">プロパティを使用する変数または定数を使用する任意の場所。</span><span class="sxs-lookup"><span data-stu-id="0f586-109">You can use a property anywhere you can use a variable or a constant.</span></span>  
  
     <span data-ttu-id="0f586-110">- または -</span><span class="sxs-lookup"><span data-stu-id="0f586-110">-or-</span></span>  
  
     <span data-ttu-id="0f586-111">等号の後、プロパティ名を使用して (`=`)、代入ステートメントにサインインします。</span><span class="sxs-lookup"><span data-stu-id="0f586-111">Use the property name following the equal (`=`) sign in an assignment statement.</span></span>  
  
     <span data-ttu-id="0f586-112">次の例は、Visual Basic の値を読み取ります`Now`プロパティ、暗黙的に呼び出して、`Get`プロシージャ。</span><span class="sxs-lookup"><span data-stu-id="0f586-112">The following example reads the value of the Visual Basic `Now` property, implicitly calling its `Get` procedure.</span></span>  
  
     [!code-vb[VbVbalrDateProperties#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDateProperties/VB/Module1.vb#4)]  
  
2. <span data-ttu-id="0f586-113">プロパティが引数を受け取る場合は、次の引数リストを囲むためにかっこによるプロパティ名。</span><span class="sxs-lookup"><span data-stu-id="0f586-113">If the property takes arguments, follow the property name with parentheses to enclose the argument list.</span></span> <span data-ttu-id="0f586-114">引数がない場合、かっこを省略することができます。</span><span class="sxs-lookup"><span data-stu-id="0f586-114">If there are no arguments, you can optionally omit the parentheses.</span></span>  
  
3. <span data-ttu-id="0f586-115">コンマで区切り、かっこ内の引数リストで、引数を配置します。</span><span class="sxs-lookup"><span data-stu-id="0f586-115">Place the arguments in the argument list within the parentheses, separated by commas.</span></span> <span data-ttu-id="0f586-116">プロパティが、対応するパラメーターを定義するのと同じ順序で引数を指定してください。</span><span class="sxs-lookup"><span data-stu-id="0f586-116">Be sure you supply the arguments in the same order that the property defines the corresponding parameters.</span></span>  
  
 <span data-ttu-id="0f586-117">プロパティの値が、式、変数と同様に参加する定数または変数または代入ステートメントの左側にあるプロパティに格納されます。</span><span class="sxs-lookup"><span data-stu-id="0f586-117">The value of the property participates in the expression just as a variable or constant would, or it is stored in the variable or property on the left side of the assignment statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f586-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="0f586-118">See also</span></span>

- [<span data-ttu-id="0f586-119">プロシージャ</span><span class="sxs-lookup"><span data-stu-id="0f586-119">Procedures</span></span>](./index.md)
- [<span data-ttu-id="0f586-120">Property プロシージャ</span><span class="sxs-lookup"><span data-stu-id="0f586-120">Property Procedures</span></span>](./property-procedures.md)
- [<span data-ttu-id="0f586-121">プロシージャのパラメーターと引数</span><span class="sxs-lookup"><span data-stu-id="0f586-121">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="0f586-122">Property ステートメント</span><span class="sxs-lookup"><span data-stu-id="0f586-122">Property Statement</span></span>](../../../../visual-basic/language-reference/statements/property-statement.md)
- [<span data-ttu-id="0f586-123">Visual Basic でのプロパティと変数の違い</span><span class="sxs-lookup"><span data-stu-id="0f586-123">Differences Between Properties and Variables in Visual Basic</span></span>](./differences-between-properties-and-variables.md)
- [<span data-ttu-id="0f586-124">方法: プロパティを作成します。</span><span class="sxs-lookup"><span data-stu-id="0f586-124">How to: Create a Property</span></span>](./how-to-create-a-property.md)
- [<span data-ttu-id="0f586-125">方法: 混合アクセス レベルを持つプロパティを宣言します。</span><span class="sxs-lookup"><span data-stu-id="0f586-125">How to: Declare a Property with Mixed Access Levels</span></span>](./how-to-declare-a-property-with-mixed-access-levels.md)
- [<span data-ttu-id="0f586-126">方法: プロパティ プロシージャを呼び出す</span><span class="sxs-lookup"><span data-stu-id="0f586-126">How to: Call a Property Procedure</span></span>](./how-to-call-a-property-procedure.md)
- [<span data-ttu-id="0f586-127">方法: 宣言し、Visual Basic では、既定のプロパティを呼び出す</span><span class="sxs-lookup"><span data-stu-id="0f586-127">How to: Declare and Call a Default Property in Visual Basic</span></span>](./how-to-declare-and-call-a-default-property.md)
- [<span data-ttu-id="0f586-128">方法: プロパティに値を格納します。</span><span class="sxs-lookup"><span data-stu-id="0f586-128">How to: Put a Value in a Property</span></span>](./how-to-put-a-value-in-a-property.md)
