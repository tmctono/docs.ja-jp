---
title: '方法: プロパティ プロシージャを呼び出す'
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, procedures
- Visual Basic code, properties
- procedures [Visual Basic], calling
- properties [Visual Basic], property procedures
- procedure calls [Visual Basic], property procedures
ms.assetid: 96bc4d74-d9c3-4b7a-954d-58ac8553cd94
ms.openlocfilehash: 006961a0f1d4be6b0d52be5bc273dad9733bfe56
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2020
ms.locfileid: "84388700"
---
# <a name="how-to-call-a-property-procedure-visual-basic"></a><span data-ttu-id="10818-102">方法: プロパティ プロシージャを呼び出す (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="10818-102">How to: Call a Property Procedure (Visual Basic)</span></span>
<span data-ttu-id="10818-103">プロパティ プロシージャを呼び出すには、プロパティに値を格納するか、その値を取得します。</span><span class="sxs-lookup"><span data-stu-id="10818-103">You call a property procedure by storing a value in the property or retrieving its value.</span></span> <span data-ttu-id="10818-104">プロパティには、変数にアクセスするのと同じ方法でアクセスします。</span><span class="sxs-lookup"><span data-stu-id="10818-104">You access a property the same way you access a variable.</span></span>  
  
 <span data-ttu-id="10818-105">プロパティの `Set` プロシージャによって値が格納され、その `Get` プロシージャによって値が取得されます。</span><span class="sxs-lookup"><span data-stu-id="10818-105">The property's `Set` procedure stores a value, and its `Get` procedure retrieves the value.</span></span> <span data-ttu-id="10818-106">ただし、これらのプロシージャを名前で明示的に呼び出すことはしません。</span><span class="sxs-lookup"><span data-stu-id="10818-106">However, you do not explicitly call these procedures by name.</span></span> <span data-ttu-id="10818-107">変数の値を格納または取得する場合と同様に、代入ステートメントまたは式でもプロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="10818-107">You use the property in an assignment statement or an expression, just as you would store or retrieve the value of a variable.</span></span> <span data-ttu-id="10818-108">Visual Basic によってプロパティのプロシージャが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="10818-108">Visual Basic makes the calls to the property's procedures.</span></span>  
  
### <a name="to-call-a-propertys-get-procedure"></a><span data-ttu-id="10818-109">プロパティの Get プロシージャを呼び出すには</span><span class="sxs-lookup"><span data-stu-id="10818-109">To call a property's Get procedure</span></span>  
  
1. <span data-ttu-id="10818-110">式内のプロパティ名は、変数名を使用する場合と同じように使用します。</span><span class="sxs-lookup"><span data-stu-id="10818-110">Use the property name in an expression the same way you would use a variable name.</span></span> <span data-ttu-id="10818-111">変数または定数を使用できる場所であればどこでもプロパティを使用できます。</span><span class="sxs-lookup"><span data-stu-id="10818-111">You can use a property anywhere you can use a variable or a constant.</span></span>  
  
     <span data-ttu-id="10818-112">\- または -</span><span class="sxs-lookup"><span data-stu-id="10818-112">-or-</span></span>  
  
     <span data-ttu-id="10818-113">代入ステートメント内で等号 (`=`) の後にプロパティ名を使用します。</span><span class="sxs-lookup"><span data-stu-id="10818-113">Use the property name following the equal (`=`) sign in an assignment statement.</span></span>  
  
     <span data-ttu-id="10818-114">次の例では、<xref:Microsoft.VisualBasic.DateAndTime.Now%2A> プロパティの値を読み取ることで、その `Get` プロシージャを暗黙的に呼び出します。</span><span class="sxs-lookup"><span data-stu-id="10818-114">The following example reads the value of the <xref:Microsoft.VisualBasic.DateAndTime.Now%2A> property, implicitly calling its `Get` procedure.</span></span>  
  
     [!code-vb[VbVbalrDateProperties#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDateProperties/VB/Module1.vb#4)]  
  
2. <span data-ttu-id="10818-115">プロパティが引数を受け取る場合は、プロパティ名の後にかっこで囲んだ引数リストを指定します。</span><span class="sxs-lookup"><span data-stu-id="10818-115">If the property takes arguments, follow the property name with parentheses to enclose the argument list.</span></span> <span data-ttu-id="10818-116">引数がない場合は、必要に応じてかっこを省略できます。</span><span class="sxs-lookup"><span data-stu-id="10818-116">If there are no arguments, you can optionally omit the parentheses.</span></span>  
  
3. <span data-ttu-id="10818-117">引数リストの引数をコンマで区切ってかっこ内に配置します。</span><span class="sxs-lookup"><span data-stu-id="10818-117">Place the arguments in the argument list within the parentheses, separated by commas.</span></span> <span data-ttu-id="10818-118">プロパティで定義されている対応するパラメーターと同じ順序で引数を指定してください。</span><span class="sxs-lookup"><span data-stu-id="10818-118">Be sure you supply the arguments in the same order that the property defines the corresponding parameters.</span></span>  
  
 <span data-ttu-id="10818-119">プロパティの値は変数または定数の場合と同様に式に含められるか、または代入ステートメントの左辺にある変数またはプロパティに格納されます。</span><span class="sxs-lookup"><span data-stu-id="10818-119">The value of the property participates in the expression just as a variable or constant would, or it is stored in the variable or property on the left side of the assignment statement.</span></span>  
  
### <a name="to-call-a-propertys-set-procedure"></a><span data-ttu-id="10818-120">プロパティの Set プロシージャを呼び出すには</span><span class="sxs-lookup"><span data-stu-id="10818-120">To call a property's Set procedure</span></span>  
  
1. <span data-ttu-id="10818-121">代入ステートメントの左辺にプロパティ名を使用します。</span><span class="sxs-lookup"><span data-stu-id="10818-121">Use the property name on the left side of an assignment statement.</span></span>  
  
     <span data-ttu-id="10818-122">次の例では、<xref:Microsoft.VisualBasic.DateAndTime.TimeOfDay%2A> プロパティの値を設定して、`Set` プロシージャを暗黙的に呼び出します。</span><span class="sxs-lookup"><span data-stu-id="10818-122">The following example sets the value of the <xref:Microsoft.VisualBasic.DateAndTime.TimeOfDay%2A> property, implicitly calling the `Set` procedure.</span></span>  
  
     [!code-vb[VbVbcnProcedures#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#11)]  
  
2. <span data-ttu-id="10818-123">プロパティが引数を受け取る場合は、プロパティ名の後にかっこで囲んだ引数リストを指定します。</span><span class="sxs-lookup"><span data-stu-id="10818-123">If the property takes arguments, follow the property name with parentheses to enclose the argument list.</span></span> <span data-ttu-id="10818-124">引数がない場合は、必要に応じてかっこを省略できます。</span><span class="sxs-lookup"><span data-stu-id="10818-124">If there are no arguments, you can optionally omit the parentheses.</span></span>  
  
3. <span data-ttu-id="10818-125">引数リストの引数をコンマで区切ってかっこ内に配置します。</span><span class="sxs-lookup"><span data-stu-id="10818-125">Place the arguments in the argument list within the parentheses, separated by commas.</span></span> <span data-ttu-id="10818-126">プロパティで定義されている対応するパラメーターと同じ順序で引数を指定してください。</span><span class="sxs-lookup"><span data-stu-id="10818-126">Be sure you supply the arguments in the same order that the property defines the corresponding parameters.</span></span>  
  
 <span data-ttu-id="10818-127">代入ステートメントの右辺で生成された値がプロパティに格納されます。</span><span class="sxs-lookup"><span data-stu-id="10818-127">The value generated on the right side of the assignment statement is stored in the property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10818-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="10818-128">See also</span></span>

- [<span data-ttu-id="10818-129">Property プロシージャ</span><span class="sxs-lookup"><span data-stu-id="10818-129">Property Procedures</span></span>](./property-procedures.md)
- [<span data-ttu-id="10818-130">プロシージャのパラメーターと引数</span><span class="sxs-lookup"><span data-stu-id="10818-130">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="10818-131">Property ステートメント</span><span class="sxs-lookup"><span data-stu-id="10818-131">Property Statement</span></span>](../../../language-reference/statements/property-statement.md)
- [<span data-ttu-id="10818-132">Visual Basic のプロパティと変数の違い</span><span class="sxs-lookup"><span data-stu-id="10818-132">Differences Between Properties and Variables in Visual Basic</span></span>](./differences-between-properties-and-variables.md)
- [<span data-ttu-id="10818-133">方法: プロパティを作成する</span><span class="sxs-lookup"><span data-stu-id="10818-133">How to: Create a Property</span></span>](./how-to-create-a-property.md)
- [<span data-ttu-id="10818-134">方法: 複数のアクセス レベルを持つプロパティを宣言する</span><span class="sxs-lookup"><span data-stu-id="10818-134">How to: Declare a Property with Mixed Access Levels</span></span>](./how-to-declare-a-property-with-mixed-access-levels.md)
- [<span data-ttu-id="10818-135">方法: 既定のプロパティを宣言して呼び出す (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="10818-135">How to: Declare and Call a Default Property in Visual Basic</span></span>](./how-to-declare-and-call-a-default-property.md)
- [<span data-ttu-id="10818-136">方法: プロパティに値を格納する</span><span class="sxs-lookup"><span data-stu-id="10818-136">How to: Put a Value in a Property</span></span>](./how-to-put-a-value-in-a-property.md)
- [<span data-ttu-id="10818-137">方法: プロパティから値を取得する</span><span class="sxs-lookup"><span data-stu-id="10818-137">How to: Get a Value from a Property</span></span>](./how-to-get-a-value-from-a-property.md)
- [<span data-ttu-id="10818-138">Get ステートメント</span><span class="sxs-lookup"><span data-stu-id="10818-138">Get Statement</span></span>](../../../language-reference/statements/get-statement.md)
- [<span data-ttu-id="10818-139">Set ステートメント</span><span class="sxs-lookup"><span data-stu-id="10818-139">Set Statement</span></span>](../../../language-reference/statements/set-statement.md)
