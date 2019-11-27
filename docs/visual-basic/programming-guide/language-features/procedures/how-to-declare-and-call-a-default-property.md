---
title: '方法: 既定のプロパティを宣言して呼び出す'
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
ms.openlocfilehash: b01188ed8a9ff4da95a6975dcac3509625fdffb2
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349682"
---
# <a name="how-to-declare-and-call-a-default-property-in-visual-basic"></a><span data-ttu-id="a444e-102">方法: 既定のプロパティを宣言して呼び出す (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a444e-102">How to: Declare and Call a Default Property in Visual Basic</span></span>
<span data-ttu-id="a444e-103">*既定のプロパティ*は、コードがそれを指定せずにアクセスできるクラスまたは構造体のプロパティです。</span><span class="sxs-lookup"><span data-stu-id="a444e-103">A *default property* is a class or structure property that your code can access without specifying it.</span></span> <span data-ttu-id="a444e-104">コードでクラスまたは構造体を呼び出すが、プロパティにはアクセスできない場合、Visual Basic は、そのクラスまたは構造体の既定のプロパティへのアクセスを解決します (存在する場合)。</span><span class="sxs-lookup"><span data-stu-id="a444e-104">When calling code names a class or structure but not a property, and the context allows access to a property, Visual Basic resolves the access to that class or structure's default property if one exists.</span></span>  
  
 <span data-ttu-id="a444e-105">クラスまたは構造体は、最大で1つの既定のプロパティを持つことができます。</span><span class="sxs-lookup"><span data-stu-id="a444e-105">A class or structure can have at most one default property.</span></span> <span data-ttu-id="a444e-106">ただし、既定のプロパティをオーバーロードして、複数のバージョンを持つことができます。</span><span class="sxs-lookup"><span data-stu-id="a444e-106">However, you can overload a default property and have more than one version of it.</span></span>  
  
 <span data-ttu-id="a444e-107">詳細については、「 [Default](../../../../visual-basic/language-reference/modifiers/default.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a444e-107">For more information, see [Default](../../../../visual-basic/language-reference/modifiers/default.md).</span></span>  
  
### <a name="to-declare-a-default-property"></a><span data-ttu-id="a444e-108">既定のプロパティを宣言するには</span><span class="sxs-lookup"><span data-stu-id="a444e-108">To declare a default property</span></span>  
  
1. <span data-ttu-id="a444e-109">通常の方法でプロパティを宣言します。</span><span class="sxs-lookup"><span data-stu-id="a444e-109">Declare the property in the normal way.</span></span> <span data-ttu-id="a444e-110">`Shared` または `Private` キーワードを指定しないでください。</span><span class="sxs-lookup"><span data-stu-id="a444e-110">Do not specify the `Shared` or `Private` keyword.</span></span>  
  
2. <span data-ttu-id="a444e-111">プロパティ宣言に `Default` キーワードを含めます。</span><span class="sxs-lookup"><span data-stu-id="a444e-111">Include the `Default` keyword in the property declaration.</span></span>  
  
3. <span data-ttu-id="a444e-112">プロパティのパラメーターを少なくとも1つ指定してください。</span><span class="sxs-lookup"><span data-stu-id="a444e-112">Specify at least one parameter for the property.</span></span> <span data-ttu-id="a444e-113">少なくとも1つの引数を受け取らない既定のプロパティを定義することはできません。</span><span class="sxs-lookup"><span data-stu-id="a444e-113">You cannot define a default property that does not take at least one argument.</span></span>  
  
     [!code-vb[VbVbcnProcedures#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#17)]  
  
### <a name="to-call-a-default-property"></a><span data-ttu-id="a444e-114">既定のプロパティを呼び出すには</span><span class="sxs-lookup"><span data-stu-id="a444e-114">To call a default property</span></span>  
  
1. <span data-ttu-id="a444e-115">含んでいるクラスまたは構造体型の変数を宣言します。</span><span class="sxs-lookup"><span data-stu-id="a444e-115">Declare a variable of the containing class or structure type.</span></span>  
  
     [!code-vb[VbVbcnProcedures#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#16)]  
  
2. <span data-ttu-id="a444e-116">変数名は、通常、プロパティ名を含める式でのみ使用します。</span><span class="sxs-lookup"><span data-stu-id="a444e-116">Use the variable name alone in an expression where you would normally include the property name.</span></span>  
  
     [!code-vb[VbVbcnProcedures#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#21)]  
  
3. <span data-ttu-id="a444e-117">変数名の後にかっこで囲んだ引数リストを指定します。</span><span class="sxs-lookup"><span data-stu-id="a444e-117">Follow the variable name with an argument list in parentheses.</span></span> <span data-ttu-id="a444e-118">既定のプロパティは、少なくとも1つの引数を受け取る必要があります。</span><span class="sxs-lookup"><span data-stu-id="a444e-118">A default property must take at least one argument.</span></span>  
  
     [!code-vb[VbVbcnProcedures#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#20)]  
  
4. <span data-ttu-id="a444e-119">既定のプロパティ値を取得するには、式または代入ステートメントで等号 (`=`) に続く変数名を引数リストと共に使用します。</span><span class="sxs-lookup"><span data-stu-id="a444e-119">To retrieve the default property value, use the variable name, with an argument list, in an expression or following the equal (`=`) sign in an assignment statement.</span></span>  
  
     [!code-vb[VbVbcnProcedures#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#15)]  
  
5. <span data-ttu-id="a444e-120">既定のプロパティ値を設定するには、代入ステートメントの左側にある引数リストを持つ変数名を使用します。</span><span class="sxs-lookup"><span data-stu-id="a444e-120">To set the default property value, use the variable name, with an argument list, on the left side of an assignment statement.</span></span>  
  
     [!code-vb[VbVbcnProcedures#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#14)]  
  
6. <span data-ttu-id="a444e-121">他のプロパティにアクセスする場合と同じように、既定のプロパティ名は常に変数名と共に指定できます。</span><span class="sxs-lookup"><span data-stu-id="a444e-121">You can always specify the default property name together with the variable name, just as you would do to access any other property.</span></span>  
  
     [!code-vb[VbVbcnProcedures#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#19)]  
  
## <a name="example"></a><span data-ttu-id="a444e-122">例</span><span class="sxs-lookup"><span data-stu-id="a444e-122">Example</span></span>  
 <span data-ttu-id="a444e-123">次の例では、クラスの既定のプロパティを宣言しています。</span><span class="sxs-lookup"><span data-stu-id="a444e-123">The following example declares a default property on a class.</span></span>  
  
 [!code-vb[VbVbcnProcedures#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#12)]  
  
## <a name="example"></a><span data-ttu-id="a444e-124">例</span><span class="sxs-lookup"><span data-stu-id="a444e-124">Example</span></span>  
 <span data-ttu-id="a444e-125">次の例は、クラス `class1`で既定のプロパティ `myProperty` を呼び出す方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="a444e-125">The following example demonstrates how to call the default property `myProperty` on class `class1`.</span></span> <span data-ttu-id="a444e-126">3つの代入ステートメントは `myProperty`に値を格納し、<xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> 呼び出しは値を読み取ります。</span><span class="sxs-lookup"><span data-stu-id="a444e-126">The three assignment statements store values in `myProperty`, and the <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> call reads the values.</span></span>  
  
 [!code-vb[VbVbcnProcedures#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#13)]  
  
 <span data-ttu-id="a444e-127">既定のプロパティの最も一般的な用途は、さまざまなコレクションクラスの <xref:Microsoft.VisualBasic.Collection.Item%2A> プロパティです。</span><span class="sxs-lookup"><span data-stu-id="a444e-127">The most common use of a default property is the <xref:Microsoft.VisualBasic.Collection.Item%2A> property on various collection classes.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="a444e-128">堅牢性の高いプログラミング</span><span class="sxs-lookup"><span data-stu-id="a444e-128">Robust Programming</span></span>  
 <span data-ttu-id="a444e-129">既定のプロパティを使用すると、ソースコード文字が小さくなることがありますが、コードの読み取りが困難になる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a444e-129">Default properties can result in a small reduction in source code-characters, but they can make your code more difficult to read.</span></span> <span data-ttu-id="a444e-130">呼び出し元のコードがクラスまたは構造体に精通していない場合、クラスまたは構造体の名前への参照を作成するときに、その参照がクラスまたは構造体自体、または既定のプロパティにアクセスするかどうかを特定できません。</span><span class="sxs-lookup"><span data-stu-id="a444e-130">If the calling code is not familiar with your class or structure, when it makes a reference to the class or structure name it cannot be certain whether that reference accesses the class or structure itself, or a default property.</span></span> <span data-ttu-id="a444e-131">これにより、コンパイラエラーまたは微妙な実行時のロジックエラーが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a444e-131">This can lead to compiler errors or subtle run-time logic errors.</span></span>  
  
 <span data-ttu-id="a444e-132">[Option Strict ステートメント](../../../../visual-basic/language-reference/statements/option-strict-statement.md)を常に使用してコンパイラの型チェックを `On`に設定することにより、既定のプロパティエラーが発生する可能性を多少減らすことができます。</span><span class="sxs-lookup"><span data-stu-id="a444e-132">You can somewhat reduce the chance of default property errors by always using the [Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md) to set compiler type checking to `On`.</span></span>  
  
 <span data-ttu-id="a444e-133">定義済みのクラスまたは構造体をコード内で使用する予定の場合は、既定のプロパティがあるかどうかを判断し、存在する場合はその名前を確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a444e-133">If you are planning to use a predefined class or structure in your code, you must determine whether it has a default property, and if so, what its name is.</span></span>  
  
 <span data-ttu-id="a444e-134">これらの欠点があるため、既定のプロパティを定義しないことを検討してください。</span><span class="sxs-lookup"><span data-stu-id="a444e-134">Because of these disadvantages, you should consider not defining default properties.</span></span> <span data-ttu-id="a444e-135">コードを読みやすくするために、常にすべてのプロパティを明示的に参照することも検討する必要があります。既定のプロパティも同様です。</span><span class="sxs-lookup"><span data-stu-id="a444e-135">For code readability, you should also consider always referring to all properties explicitly, even default properties.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a444e-136">参照</span><span class="sxs-lookup"><span data-stu-id="a444e-136">See also</span></span>

- [<span data-ttu-id="a444e-137">Property プロシージャ</span><span class="sxs-lookup"><span data-stu-id="a444e-137">Property Procedures</span></span>](./property-procedures.md)
- [<span data-ttu-id="a444e-138">プロシージャのパラメーターと引数</span><span class="sxs-lookup"><span data-stu-id="a444e-138">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="a444e-139">Property ステートメント</span><span class="sxs-lookup"><span data-stu-id="a444e-139">Property Statement</span></span>](../../../../visual-basic/language-reference/statements/property-statement.md)
- [<span data-ttu-id="a444e-140">Shared</span><span class="sxs-lookup"><span data-stu-id="a444e-140">Default</span></span>](../../../../visual-basic/language-reference/modifiers/default.md)
- [<span data-ttu-id="a444e-141">Visual Basic のプロパティと変数の違い</span><span class="sxs-lookup"><span data-stu-id="a444e-141">Differences Between Properties and Variables in Visual Basic</span></span>](./differences-between-properties-and-variables.md)
- [<span data-ttu-id="a444e-142">方法 : プロパティを作成する</span><span class="sxs-lookup"><span data-stu-id="a444e-142">How to: Create a Property</span></span>](./how-to-create-a-property.md)
- [<span data-ttu-id="a444e-143">方法 : 複数のアクセス レベルを持つプロパティを宣言する</span><span class="sxs-lookup"><span data-stu-id="a444e-143">How to: Declare a Property with Mixed Access Levels</span></span>](./how-to-declare-a-property-with-mixed-access-levels.md)
- [<span data-ttu-id="a444e-144">方法 : プロパティ プロシージャを呼び出す</span><span class="sxs-lookup"><span data-stu-id="a444e-144">How to: Call a Property Procedure</span></span>](./how-to-call-a-property-procedure.md)
- [<span data-ttu-id="a444e-145">方法 : プロパティに値を格納する</span><span class="sxs-lookup"><span data-stu-id="a444e-145">How to: Put a Value in a Property</span></span>](./how-to-put-a-value-in-a-property.md)
- [<span data-ttu-id="a444e-146">方法 : プロパティから値を取得する</span><span class="sxs-lookup"><span data-stu-id="a444e-146">How to: Get a Value from a Property</span></span>](./how-to-get-a-value-from-a-property.md)
