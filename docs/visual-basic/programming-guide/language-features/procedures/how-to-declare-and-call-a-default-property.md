---
title: '方法: 宣言し、Visual Basic では、既定のプロパティを呼び出す'
ms.date: 07/20/2015
helpviewer_keywords:
- defaults [Visual Basic], properties
- properties [Visual Basic], default
- procedures [Visual Basic], defining
- default properties [Visual Basic], in Visual Basic
- Visual Basic code, procedures
- Visual Basic code, properties
- default properties
ms.assetid: 68b4026e-09ef-4613-808e-f6287494ff63
ms.openlocfilehash: 9ca9a0ccdac3ac13429928233a0c09d58427ce74
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61665768"
---
# <a name="how-to-declare-and-call-a-default-property-in-visual-basic"></a><span data-ttu-id="42a42-102">方法: 宣言し、Visual Basic では、既定のプロパティを呼び出す</span><span class="sxs-lookup"><span data-stu-id="42a42-102">How to: Declare and Call a Default Property in Visual Basic</span></span>
<span data-ttu-id="42a42-103">A*プロパティの既定*クラスまたは構造体のプロパティで、指定しなくても、コードにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="42a42-103">A *default property* is a class or structure property that your code can access without specifying it.</span></span> <span data-ttu-id="42a42-104">呼び出し元のコードは、クラスまたは構造体がないプロパティ、およびコンテキスト プロパティへのアクセスを許可、存在する場合、Visual Basic がそのクラスまたは構造体の既定のプロパティにアクセスを解決します。</span><span class="sxs-lookup"><span data-stu-id="42a42-104">When calling code names a class or structure but not a property, and the context allows access to a property, Visual Basic resolves the access to that class or structure's default property if one exists.</span></span>  
  
 <span data-ttu-id="42a42-105">クラスまたは構造体が多くて 1 つの既定のプロパティ。</span><span class="sxs-lookup"><span data-stu-id="42a42-105">A class or structure can have at most one default property.</span></span> <span data-ttu-id="42a42-106">ただし、既定プロパティはオーバー ロードし、その 1 つ以上のバージョンがあります。</span><span class="sxs-lookup"><span data-stu-id="42a42-106">However, you can overload a default property and have more than one version of it.</span></span>  
  
 <span data-ttu-id="42a42-107">詳細については、次を参照してください。[既定](../../../../visual-basic/language-reference/modifiers/default.md)します。</span><span class="sxs-lookup"><span data-stu-id="42a42-107">For more information, see [Default](../../../../visual-basic/language-reference/modifiers/default.md).</span></span>  
  
### <a name="to-declare-a-default-property"></a><span data-ttu-id="42a42-108">既定のプロパティを宣言するには</span><span class="sxs-lookup"><span data-stu-id="42a42-108">To declare a default property</span></span>  
  
1. <span data-ttu-id="42a42-109">通常の方法でプロパティを宣言します。</span><span class="sxs-lookup"><span data-stu-id="42a42-109">Declare the property in the normal way.</span></span> <span data-ttu-id="42a42-110">指定しない、`Shared`または`Private`キーワード。</span><span class="sxs-lookup"><span data-stu-id="42a42-110">Do not specify the `Shared` or `Private` keyword.</span></span>  
  
2. <span data-ttu-id="42a42-111">含める、`Default`プロパティ宣言でキーワード。</span><span class="sxs-lookup"><span data-stu-id="42a42-111">Include the `Default` keyword in the property declaration.</span></span>  
  
3. <span data-ttu-id="42a42-112">プロパティの少なくとも 1 つのパラメーターを指定します。</span><span class="sxs-lookup"><span data-stu-id="42a42-112">Specify at least one parameter for the property.</span></span> <span data-ttu-id="42a42-113">少なくとも 1 つの引数を受け取らない既定のプロパティを定義することはできません。</span><span class="sxs-lookup"><span data-stu-id="42a42-113">You cannot define a default property that does not take at least one argument.</span></span>  
  
     [!code-vb[VbVbcnProcedures#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#17)]  
  
### <a name="to-call-a-default-property"></a><span data-ttu-id="42a42-114">既定のプロパティを呼び出す</span><span class="sxs-lookup"><span data-stu-id="42a42-114">To call a default property</span></span>  
  
1. <span data-ttu-id="42a42-115">それを含むクラスまたは構造体の型の変数を宣言します。</span><span class="sxs-lookup"><span data-stu-id="42a42-115">Declare a variable of the containing class or structure type.</span></span>  
  
     [!code-vb[VbVbcnProcedures#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#16)]  
  
2. <span data-ttu-id="42a42-116">プロパティ名を通常は式の中で単独で変数名を使用します。</span><span class="sxs-lookup"><span data-stu-id="42a42-116">Use the variable name alone in an expression where you would normally include the property name.</span></span>  
  
     [!code-vb[VbVbcnProcedures#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#21)]  
  
3. <span data-ttu-id="42a42-117">引数リストをかっこで、変数名に従ってください。</span><span class="sxs-lookup"><span data-stu-id="42a42-117">Follow the variable name with an argument list in parentheses.</span></span> <span data-ttu-id="42a42-118">既定のプロパティは、少なくとも 1 つの引数を受け取る必要があります。</span><span class="sxs-lookup"><span data-stu-id="42a42-118">A default property must take at least one argument.</span></span>  
  
     [!code-vb[VbVbcnProcedures#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#20)]  
  
4. <span data-ttu-id="42a42-119">プロパティの既定値を取得するには、次の等値または式の中で、引数リストでという名前の変数を使用 (`=`)、代入ステートメントにサインインします。</span><span class="sxs-lookup"><span data-stu-id="42a42-119">To retrieve the default property value, use the variable name, with an argument list, in an expression or following the equal (`=`) sign in an assignment statement.</span></span>  
  
     [!code-vb[VbVbcnProcedures#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#15)]  
  
5. <span data-ttu-id="42a42-120">プロパティの既定値を設定するには、代入ステートメントの左側にある、引数のリストを持つという名前の変数を使用します。</span><span class="sxs-lookup"><span data-stu-id="42a42-120">To set the default property value, use the variable name, with an argument list, on the left side of an assignment statement.</span></span>  
  
     [!code-vb[VbVbcnProcedures#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#14)]  
  
6. <span data-ttu-id="42a42-121">他のプロパティにアクセスするための作業と同様、という名前の変数と共に既定のプロパティ名を必ず指定することができます。</span><span class="sxs-lookup"><span data-stu-id="42a42-121">You can always specify the default property name together with the variable name, just as you would do to access any other property.</span></span>  
  
     [!code-vb[VbVbcnProcedures#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#19)]  
  
## <a name="example"></a><span data-ttu-id="42a42-122">例</span><span class="sxs-lookup"><span data-stu-id="42a42-122">Example</span></span>  
 <span data-ttu-id="42a42-123">次の例では、クラスの既定のプロパティを宣言します。</span><span class="sxs-lookup"><span data-stu-id="42a42-123">The following example declares a default property on a class.</span></span>  
  
 [!code-vb[VbVbcnProcedures#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#12)]  
  
## <a name="example"></a><span data-ttu-id="42a42-124">例</span><span class="sxs-lookup"><span data-stu-id="42a42-124">Example</span></span>  
 <span data-ttu-id="42a42-125">次の例では、既定のプロパティを呼び出す方法`myProperty`クラス`class1`します。</span><span class="sxs-lookup"><span data-stu-id="42a42-125">The following example demonstrates how to call the default property `myProperty` on class `class1`.</span></span> <span data-ttu-id="42a42-126">次の 3 つの代入ステートメントで値を格納する`myProperty`、および<xref:Microsoft.VisualBasic.Interaction.MsgBox%2A>呼び出しは、値を読み取ります。</span><span class="sxs-lookup"><span data-stu-id="42a42-126">The three assignment statements store values in `myProperty`, and the <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> call reads the values.</span></span>  
  
 [!code-vb[VbVbcnProcedures#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#13)]  
  
 <span data-ttu-id="42a42-127">既定のプロパティの最も一般的な用途は、<xref:Microsoft.VisualBasic.Collection.Item%2A>さまざまなコレクション クラスのプロパティ。</span><span class="sxs-lookup"><span data-stu-id="42a42-127">The most common use of a default property is the <xref:Microsoft.VisualBasic.Collection.Item%2A> property on various collection classes.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="42a42-128">信頼性の高いプログラミング</span><span class="sxs-lookup"><span data-stu-id="42a42-128">Robust Programming</span></span>  
 <span data-ttu-id="42a42-129">既定のプロパティは、ソース コードの文字のわずかな低下につながるが行えるように、コードが読みにくくします。</span><span class="sxs-lookup"><span data-stu-id="42a42-129">Default properties can result in a small reduction in source code-characters, but they can make your code more difficult to read.</span></span> <span data-ttu-id="42a42-130">クラスまたは構造体名への参照を行うときに、呼び出し元のコードがクラスまたは構造に習熟していない場合にすることはできません特定その参照が、クラスまたは構造体自体、または既定のプロパティにアクセスするかどうか。</span><span class="sxs-lookup"><span data-stu-id="42a42-130">If the calling code is not familiar with your class or structure, when it makes a reference to the class or structure name it cannot be certain whether that reference accesses the class or structure itself, or a default property.</span></span> <span data-ttu-id="42a42-131">これについては、コンパイラ エラーまたはランタイム ロジックの微妙なエラーにつながります。</span><span class="sxs-lookup"><span data-stu-id="42a42-131">This can lead to compiler errors or subtle run-time logic errors.</span></span>  
  
 <span data-ttu-id="42a42-132">常を使用して既定のプロパティのエラーの可能性を低くことができますやや、 [Option Strict ステートメント](../../../../visual-basic/language-reference/statements/option-strict-statement.md)コンパイラ型チェックを設定する`On`します。</span><span class="sxs-lookup"><span data-stu-id="42a42-132">You can somewhat reduce the chance of default property errors by always using the [Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md) to set compiler type checking to `On`.</span></span>  
  
 <span data-ttu-id="42a42-133">使用して、定義済みのクラスまたは構造体コードで判断する必要があります、既定のプロパティがあるかどうかであればしようとしている場合、名前は。</span><span class="sxs-lookup"><span data-stu-id="42a42-133">If you are planning to use a predefined class or structure in your code, you must determine whether it has a default property, and if so, what its name is.</span></span>  
  
 <span data-ttu-id="42a42-134">このような短所のためには、既定のプロパティを定義しないを検討してください。</span><span class="sxs-lookup"><span data-stu-id="42a42-134">Because of these disadvantages, you should consider not defining default properties.</span></span> <span data-ttu-id="42a42-135">コードを読みやすくは必要がありますも常に明示的に参照するすべてのプロパティを検討してくださいも既定のプロパティ。</span><span class="sxs-lookup"><span data-stu-id="42a42-135">For code readability, you should also consider always referring to all properties explicitly, even default properties.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42a42-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="42a42-136">See also</span></span>

- [<span data-ttu-id="42a42-137">Property プロシージャ</span><span class="sxs-lookup"><span data-stu-id="42a42-137">Property Procedures</span></span>](./property-procedures.md)
- [<span data-ttu-id="42a42-138">プロシージャのパラメーターと引数</span><span class="sxs-lookup"><span data-stu-id="42a42-138">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="42a42-139">Property ステートメント</span><span class="sxs-lookup"><span data-stu-id="42a42-139">Property Statement</span></span>](../../../../visual-basic/language-reference/statements/property-statement.md)
- [<span data-ttu-id="42a42-140">Default</span><span class="sxs-lookup"><span data-stu-id="42a42-140">Default</span></span>](../../../../visual-basic/language-reference/modifiers/default.md)
- [<span data-ttu-id="42a42-141">Visual Basic でのプロパティと変数の違い</span><span class="sxs-lookup"><span data-stu-id="42a42-141">Differences Between Properties and Variables in Visual Basic</span></span>](./differences-between-properties-and-variables.md)
- [<span data-ttu-id="42a42-142">方法: プロパティを作成します。</span><span class="sxs-lookup"><span data-stu-id="42a42-142">How to: Create a Property</span></span>](./how-to-create-a-property.md)
- [<span data-ttu-id="42a42-143">方法: 混合アクセス レベルを持つプロパティを宣言します。</span><span class="sxs-lookup"><span data-stu-id="42a42-143">How to: Declare a Property with Mixed Access Levels</span></span>](./how-to-declare-a-property-with-mixed-access-levels.md)
- [<span data-ttu-id="42a42-144">方法: プロパティ プロシージャを呼び出す</span><span class="sxs-lookup"><span data-stu-id="42a42-144">How to: Call a Property Procedure</span></span>](./how-to-call-a-property-procedure.md)
- [<span data-ttu-id="42a42-145">方法: プロパティに値を格納します。</span><span class="sxs-lookup"><span data-stu-id="42a42-145">How to: Put a Value in a Property</span></span>](./how-to-put-a-value-in-a-property.md)
- [<span data-ttu-id="42a42-146">方法: プロパティから値を取得します。</span><span class="sxs-lookup"><span data-stu-id="42a42-146">How to: Get a Value from a Property</span></span>](./how-to-get-a-value-from-a-property.md)
