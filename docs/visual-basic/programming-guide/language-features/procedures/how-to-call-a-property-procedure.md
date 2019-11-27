---
title: '方法 : プロパティ プロシージャを呼び出す'
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, procedures
- Visual Basic code, properties
- procedures [Visual Basic], calling
- properties [Visual Basic], property procedures
- procedure calls [Visual Basic], property procedures
ms.assetid: 96bc4d74-d9c3-4b7a-954d-58ac8553cd94
ms.openlocfilehash: 52e6c62ffb81c480ccc1abf06f04eb780218dbf1
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74340555"
---
# <a name="how-to-call-a-property-procedure-visual-basic"></a><span data-ttu-id="45c7c-102">方法: プロパティ プロシージャを呼び出す (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="45c7c-102">How to: Call a Property Procedure (Visual Basic)</span></span>
<span data-ttu-id="45c7c-103">プロパティプロシージャを呼び出すには、プロパティに値を格納するか、値を取得します。</span><span class="sxs-lookup"><span data-stu-id="45c7c-103">You call a property procedure by storing a value in the property or retrieving its value.</span></span> <span data-ttu-id="45c7c-104">プロパティには、変数にアクセスするのと同じ方法でアクセスします。</span><span class="sxs-lookup"><span data-stu-id="45c7c-104">You access a property the same way you access a variable.</span></span>  
  
 <span data-ttu-id="45c7c-105">プロパティの `Set` プロシージャは値を格納し、その `Get` プロシージャは値を取得します。</span><span class="sxs-lookup"><span data-stu-id="45c7c-105">The property's `Set` procedure stores a value, and its `Get` procedure retrieves the value.</span></span> <span data-ttu-id="45c7c-106">ただし、これらのプロシージャを名前で明示的に呼び出すことはできません。</span><span class="sxs-lookup"><span data-stu-id="45c7c-106">However, you do not explicitly call these procedures by name.</span></span> <span data-ttu-id="45c7c-107">変数の値を格納または取得する場合と同様に、代入ステートメントまたは式でプロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="45c7c-107">You use the property in an assignment statement or an expression, just as you would store or retrieve the value of a variable.</span></span> <span data-ttu-id="45c7c-108">Visual Basic によって、プロパティのプロシージャが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="45c7c-108">Visual Basic makes the calls to the property's procedures.</span></span>  
  
### <a name="to-call-a-propertys-get-procedure"></a><span data-ttu-id="45c7c-109">プロパティの Get プロシージャを呼び出すには</span><span class="sxs-lookup"><span data-stu-id="45c7c-109">To call a property's Get procedure</span></span>  
  
1. <span data-ttu-id="45c7c-110">変数名を使用する場合と同じように、式でプロパティ名を使用します。</span><span class="sxs-lookup"><span data-stu-id="45c7c-110">Use the property name in an expression the same way you would use a variable name.</span></span> <span data-ttu-id="45c7c-111">変数または定数を使用できる場所であればどこでもプロパティを使用できます。</span><span class="sxs-lookup"><span data-stu-id="45c7c-111">You can use a property anywhere you can use a variable or a constant.</span></span>  
  
     <span data-ttu-id="45c7c-112">または</span><span class="sxs-lookup"><span data-stu-id="45c7c-112">-or-</span></span>  
  
     <span data-ttu-id="45c7c-113">代入ステートメントの等号 (`=`) の後にあるプロパティ名を使用します。</span><span class="sxs-lookup"><span data-stu-id="45c7c-113">Use the property name following the equal (`=`) sign in an assignment statement.</span></span>  
  
     <span data-ttu-id="45c7c-114">次の例では、<xref:Microsoft.VisualBasic.DateAndTime.Now%2A> プロパティの値を読み取り、その `Get` プロシージャを暗黙的に呼び出します。</span><span class="sxs-lookup"><span data-stu-id="45c7c-114">The following example reads the value of the <xref:Microsoft.VisualBasic.DateAndTime.Now%2A> property, implicitly calling its `Get` procedure.</span></span>  
  
     [!code-vb[VbVbalrDateProperties#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDateProperties/VB/Module1.vb#4)]  
  
2. <span data-ttu-id="45c7c-115">プロパティが引数を受け取る場合は、プロパティ名の後にかっこを付けて引数リストを囲みます。</span><span class="sxs-lookup"><span data-stu-id="45c7c-115">If the property takes arguments, follow the property name with parentheses to enclose the argument list.</span></span> <span data-ttu-id="45c7c-116">引数がない場合は、必要に応じてかっこを省略できます。</span><span class="sxs-lookup"><span data-stu-id="45c7c-116">If there are no arguments, you can optionally omit the parentheses.</span></span>  
  
3. <span data-ttu-id="45c7c-117">引数リストに引数をコンマで区切ってかっこ内に配置します。</span><span class="sxs-lookup"><span data-stu-id="45c7c-117">Place the arguments in the argument list within the parentheses, separated by commas.</span></span> <span data-ttu-id="45c7c-118">引数は、プロパティが対応するパラメーターを定義する順序と同じ順序で指定してください。</span><span class="sxs-lookup"><span data-stu-id="45c7c-118">Be sure you supply the arguments in the same order that the property defines the corresponding parameters.</span></span>  
  
 <span data-ttu-id="45c7c-119">プロパティの値は、変数または定数と同様に式に参加します。または、代入ステートメントの左側にある変数またはプロパティに格納されます。</span><span class="sxs-lookup"><span data-stu-id="45c7c-119">The value of the property participates in the expression just as a variable or constant would, or it is stored in the variable or property on the left side of the assignment statement.</span></span>  
  
### <a name="to-call-a-propertys-set-procedure"></a><span data-ttu-id="45c7c-120">プロパティの Set プロシージャを呼び出すには</span><span class="sxs-lookup"><span data-stu-id="45c7c-120">To call a property's Set procedure</span></span>  
  
1. <span data-ttu-id="45c7c-121">代入ステートメントの左側にあるプロパティ名を使用します。</span><span class="sxs-lookup"><span data-stu-id="45c7c-121">Use the property name on the left side of an assignment statement.</span></span>  
  
     <span data-ttu-id="45c7c-122">次の例では、<xref:Microsoft.VisualBasic.DateAndTime.TimeOfDay%2A> プロパティの値を設定し、`Set` プロシージャを暗黙的に呼び出します。</span><span class="sxs-lookup"><span data-stu-id="45c7c-122">The following example sets the value of the <xref:Microsoft.VisualBasic.DateAndTime.TimeOfDay%2A> property, implicitly calling the `Set` procedure.</span></span>  
  
     [!code-vb[VbVbcnProcedures#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#11)]  
  
2. <span data-ttu-id="45c7c-123">プロパティが引数を受け取る場合は、プロパティ名の後にかっこを付けて引数リストを囲みます。</span><span class="sxs-lookup"><span data-stu-id="45c7c-123">If the property takes arguments, follow the property name with parentheses to enclose the argument list.</span></span> <span data-ttu-id="45c7c-124">引数がない場合は、必要に応じてかっこを省略できます。</span><span class="sxs-lookup"><span data-stu-id="45c7c-124">If there are no arguments, you can optionally omit the parentheses.</span></span>  
  
3. <span data-ttu-id="45c7c-125">引数リストに引数をコンマで区切ってかっこ内に配置します。</span><span class="sxs-lookup"><span data-stu-id="45c7c-125">Place the arguments in the argument list within the parentheses, separated by commas.</span></span> <span data-ttu-id="45c7c-126">引数は、プロパティが対応するパラメーターを定義する順序と同じ順序で指定してください。</span><span class="sxs-lookup"><span data-stu-id="45c7c-126">Be sure you supply the arguments in the same order that the property defines the corresponding parameters.</span></span>  
  
 <span data-ttu-id="45c7c-127">代入ステートメントの右辺に生成される値は、プロパティに格納されます。</span><span class="sxs-lookup"><span data-stu-id="45c7c-127">The value generated on the right side of the assignment statement is stored in the property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45c7c-128">参照</span><span class="sxs-lookup"><span data-stu-id="45c7c-128">See also</span></span>

- [<span data-ttu-id="45c7c-129">Property プロシージャ</span><span class="sxs-lookup"><span data-stu-id="45c7c-129">Property Procedures</span></span>](./property-procedures.md)
- [<span data-ttu-id="45c7c-130">プロシージャのパラメーターと引数</span><span class="sxs-lookup"><span data-stu-id="45c7c-130">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="45c7c-131">Property ステートメント</span><span class="sxs-lookup"><span data-stu-id="45c7c-131">Property Statement</span></span>](../../../../visual-basic/language-reference/statements/property-statement.md)
- [<span data-ttu-id="45c7c-132">Visual Basic のプロパティと変数の違い</span><span class="sxs-lookup"><span data-stu-id="45c7c-132">Differences Between Properties and Variables in Visual Basic</span></span>](./differences-between-properties-and-variables.md)
- [<span data-ttu-id="45c7c-133">方法 : プロパティを作成する</span><span class="sxs-lookup"><span data-stu-id="45c7c-133">How to: Create a Property</span></span>](./how-to-create-a-property.md)
- [<span data-ttu-id="45c7c-134">方法 : 複数のアクセス レベルを持つプロパティを宣言する</span><span class="sxs-lookup"><span data-stu-id="45c7c-134">How to: Declare a Property with Mixed Access Levels</span></span>](./how-to-declare-a-property-with-mixed-access-levels.md)
- [<span data-ttu-id="45c7c-135">方法: Visual Basic で既定のプロパティを宣言して呼び出す</span><span class="sxs-lookup"><span data-stu-id="45c7c-135">How to: Declare and Call a Default Property in Visual Basic</span></span>](./how-to-declare-and-call-a-default-property.md)
- [<span data-ttu-id="45c7c-136">方法 : プロパティに値を格納する</span><span class="sxs-lookup"><span data-stu-id="45c7c-136">How to: Put a Value in a Property</span></span>](./how-to-put-a-value-in-a-property.md)
- [<span data-ttu-id="45c7c-137">方法 : プロパティから値を取得する</span><span class="sxs-lookup"><span data-stu-id="45c7c-137">How to: Get a Value from a Property</span></span>](./how-to-get-a-value-from-a-property.md)
- [<span data-ttu-id="45c7c-138">Get ステートメント</span><span class="sxs-lookup"><span data-stu-id="45c7c-138">Get Statement</span></span>](../../../../visual-basic/language-reference/statements/get-statement.md)
- [<span data-ttu-id="45c7c-139">Set ステートメント</span><span class="sxs-lookup"><span data-stu-id="45c7c-139">Set Statement</span></span>](../../../../visual-basic/language-reference/statements/set-statement.md)
