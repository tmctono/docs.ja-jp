---
title: Property プロシージャ (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Set statement [Visual Basic], Property procedures
- Visual Basic code, procedures
- return values [Visual Basic], Property procedures
- syntax [Visual Basic], Property procedures
- procedures [Visual Basic], property
- Visual Basic code, properties
- procedures [Visual Basic], calling
- properties [Visual Basic], custom
- property procedures
- Get statement [Visual Basic], property procedures
ms.assetid: 46a98379-e1a2-45dd-a48c-b51213f5ab07
ms.openlocfilehash: 47e93ee17f160ce5cd701fd0a12ec16b3997ce9b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61791860"
---
# <a name="property-procedures-visual-basic"></a><span data-ttu-id="1f828-102">Property プロシージャ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1f828-102">Property Procedures (Visual Basic)</span></span>
<span data-ttu-id="1f828-103">プロパティ プロシージャは、一連のモジュール、クラスまたは構造体のカスタム プロパティを操作する Visual Basic ステートメントです。</span><span class="sxs-lookup"><span data-stu-id="1f828-103">A property procedure is a series of Visual Basic statements that manipulate a custom property on a module, class, or structure.</span></span> <span data-ttu-id="1f828-104">プロパティ プロシージャとも呼ばれます*プロパティ アクセサー*します。</span><span class="sxs-lookup"><span data-stu-id="1f828-104">Property procedures are also known as *property accessors*.</span></span>  
  
 <span data-ttu-id="1f828-105">Visual Basic は、次のプロパティ プロシージャを提供します。</span><span class="sxs-lookup"><span data-stu-id="1f828-105">Visual Basic provides for the following property procedures:</span></span>  
  
- <span data-ttu-id="1f828-106">A`Get`プロパティの値を返します。</span><span class="sxs-lookup"><span data-stu-id="1f828-106">A `Get` procedure returns the value of a property.</span></span> <span data-ttu-id="1f828-107">式でプロパティにアクセスするときに呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="1f828-107">It is called when you access the property in an expression.</span></span>  
  
- <span data-ttu-id="1f828-108">A`Set`プロシージャに値をオブジェクト参照を含むプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="1f828-108">A `Set` procedure sets a property to a value, including an object reference.</span></span> <span data-ttu-id="1f828-109">プロパティに値を割り当てるときに呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="1f828-109">It is called when you assign a value to the property.</span></span>  
  
 <span data-ttu-id="1f828-110">使用して、ペアで、通常、プロパティ プロシージャを定義する、`Get`と`Set`プロパティが読み取り専用の場合は、ステートメントがからだけでいずれかの手順に定義することができます ([Get ステートメント](../../../../visual-basic/language-reference/statements/get-statement.md)) または書き込み専用 ([設定ステートメント](../../../../visual-basic/language-reference/statements/set-statement.md))。</span><span class="sxs-lookup"><span data-stu-id="1f828-110">You usually define property procedures in pairs, using the `Get` and `Set` statements, but you can define either procedure alone if the property is read-only ([Get Statement](../../../../visual-basic/language-reference/statements/get-statement.md)) or write-only ([Set Statement](../../../../visual-basic/language-reference/statements/set-statement.md)).</span></span>  
  
 <span data-ttu-id="1f828-111">省略することができます、`Get`と`Set`プロシージャの自動実装プロパティを使用する場合。</span><span class="sxs-lookup"><span data-stu-id="1f828-111">You can omit the `Get` and `Set` procedure when using an auto-implemented property.</span></span> <span data-ttu-id="1f828-112">詳細については、「[自動実装プロパティ](./auto-implemented-properties.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1f828-112">For more information, see [Auto-Implemented Properties](./auto-implemented-properties.md).</span></span>  
  
 <span data-ttu-id="1f828-113">プロパティは、クラス、構造、およびモジュールで定義できます。</span><span class="sxs-lookup"><span data-stu-id="1f828-113">You can define properties in classes, structures, and modules.</span></span> <span data-ttu-id="1f828-114">プロパティは、`Public`どこからでも呼び出すことを意味する既定では、プロパティのコンテナーにアクセスできるアプリケーションでします。</span><span class="sxs-lookup"><span data-stu-id="1f828-114">Properties are `Public` by default, which means you can call them from anywhere in your application that can access the property's container.</span></span>  
  
 <span data-ttu-id="1f828-115">プロパティと変数の比較は、次を参照してください。[プロパティ間の相違点と Visual Basic における変数](./differences-between-properties-and-variables.md)します。</span><span class="sxs-lookup"><span data-stu-id="1f828-115">For a comparison of properties and variables, see [Differences Between Properties and Variables in Visual Basic](./differences-between-properties-and-variables.md).</span></span>  
  
## <a name="declaration-syntax"></a><span data-ttu-id="1f828-116">宣言の構文</span><span class="sxs-lookup"><span data-stu-id="1f828-116">Declaration Syntax</span></span>  
 <span data-ttu-id="1f828-117">プロパティ自体がで囲まれたコードのブロックで定義されている、 [Property ステートメント](../../../../visual-basic/language-reference/statements/property-statement.md)と`End Property`ステートメント。</span><span class="sxs-lookup"><span data-stu-id="1f828-117">A property itself is defined by a block of code enclosed within the [Property Statement](../../../../visual-basic/language-reference/statements/property-statement.md) and the `End Property` statement.</span></span> <span data-ttu-id="1f828-118">このブロック内で各プロパティ プロシージャは、宣言ステートメントで囲まれた内部ブロックとして表示されます。 (`Get`または`Set`) と一致する`End`宣言します。</span><span class="sxs-lookup"><span data-stu-id="1f828-118">Inside this block, each property procedure appears as an internal block enclosed within a declaration statement (`Get` or `Set`) and the matching `End` declaration.</span></span>  
  
 <span data-ttu-id="1f828-119">プロパティと、プロシージャの宣言の構文は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="1f828-119">The syntax for declaring a property and its procedures is as follows:</span></span>  
  
```  
[Default] [Modifiers] Property PropertyName[(ParameterList)] [As DataType]  
    [AccessLevel] Get  
        ' Statements of the Get procedure.  
        ' The following statement returns an expression as the property's value.  
        Return Expression  
    End Get  
    [AccessLevel] Set[(ByVal NewValue As DataType)]  
        ' Statements of the Set procedure.  
        ' The following statement assigns newvalue as the property's value.  
        LValue = NewValue  
    End Set  
End Property  
- or -  
[Default] [Modifiers] Property PropertyName [(ParameterList)] [As DataType]  
```  
  
 <span data-ttu-id="1f828-120">`Modifiers`を指定できますアクセス レベルとオーバー ロード、オーバーライド、共有、およびシャドウ、に関する情報も、プロパティが読み取り専用または書き込み専用のかどうか。</span><span class="sxs-lookup"><span data-stu-id="1f828-120">The `Modifiers` can specify access level and information regarding overloading, overriding, sharing, and shadowing, as well as whether the property is read-only or write-only.</span></span> <span data-ttu-id="1f828-121">`AccessLevel`上、`Get`または`Set`プロシージャには、プロパティ自体に指定されたアクセス レベルより限定的な任意のレベルがあります。</span><span class="sxs-lookup"><span data-stu-id="1f828-121">The `AccessLevel` on the `Get` or `Set` procedure can be any level that is more restrictive than the access level specified for the property itself.</span></span> <span data-ttu-id="1f828-122">詳細については、次を参照してください。 [Property ステートメント](../../../../visual-basic/language-reference/statements/property-statement.md)します。</span><span class="sxs-lookup"><span data-stu-id="1f828-122">For more information, see [Property Statement](../../../../visual-basic/language-reference/statements/property-statement.md).</span></span>  
  
### <a name="data-type"></a><span data-ttu-id="1f828-123">データの種類</span><span class="sxs-lookup"><span data-stu-id="1f828-123">Data Type</span></span>  
 <span data-ttu-id="1f828-124">プロパティのデータ型とプリンシパルのアクセス レベルで定義されます、`Property`プロパティ プロシージャではなく、ステートメント。</span><span class="sxs-lookup"><span data-stu-id="1f828-124">A property's data type and principal access level are defined in the `Property` statement, not in the property procedures.</span></span> <span data-ttu-id="1f828-125">プロパティは、1 つのデータ型を持つことができます。</span><span class="sxs-lookup"><span data-stu-id="1f828-125">A property can have only one data type.</span></span> <span data-ttu-id="1f828-126">たとえば、格納するプロパティを定義することはできません、`Decimal`値しますが、取得、`Double`値。</span><span class="sxs-lookup"><span data-stu-id="1f828-126">For example, you cannot define a property to store a `Decimal` value but retrieve a `Double` value.</span></span>  
  
### <a name="access-level"></a><span data-ttu-id="1f828-127">アクセス レベル</span><span class="sxs-lookup"><span data-stu-id="1f828-127">Access Level</span></span>  
 <span data-ttu-id="1f828-128">ただし、プロパティのプリンシパルのアクセス レベルを定義し、さらに、プロパティ プロシージャのいずれかでアクセス レベルを制限できます。</span><span class="sxs-lookup"><span data-stu-id="1f828-128">However, you can define a principal access level for a property and further restrict the access level in one of its property procedures.</span></span> <span data-ttu-id="1f828-129">たとえば、定義することができます、`Public`プロパティを定義し、`Private Set`プロシージャ。</span><span class="sxs-lookup"><span data-stu-id="1f828-129">For example, you can define a `Public` property and then define a `Private Set` procedure.</span></span> <span data-ttu-id="1f828-130">`Get`プロシージャまま`Public`します。</span><span class="sxs-lookup"><span data-stu-id="1f828-130">The `Get` procedure remains `Public`.</span></span> <span data-ttu-id="1f828-131">行うことができますのみがプリンシパルのアクセス レベルよりもより制限の厳しいと、プロパティの手順の 1 つだけに、アクセス レベルを変更できます。</span><span class="sxs-lookup"><span data-stu-id="1f828-131">You can change the access level in only one of a property's procedures, and you can only make it more restrictive than the principal access level.</span></span> <span data-ttu-id="1f828-132">詳細については、「[方法 :混合アクセス レベルでプロパティを宣言](./how-to-declare-a-property-with-mixed-access-levels.md)します。</span><span class="sxs-lookup"><span data-stu-id="1f828-132">For more information, see [How to: Declare a Property with Mixed Access Levels](./how-to-declare-a-property-with-mixed-access-levels.md).</span></span>  
  
## <a name="parameter-declaration"></a><span data-ttu-id="1f828-133">パラメーターの宣言</span><span class="sxs-lookup"><span data-stu-id="1f828-133">Parameter Declaration</span></span>  
 <span data-ttu-id="1f828-134">各パラメーターのと同じ方法を宣言する[Sub プロシージャ](./sub-procedures.md)引き渡し方法がありますが、`ByVal`します。</span><span class="sxs-lookup"><span data-stu-id="1f828-134">You declare each parameter the same way you do for [Sub Procedures](./sub-procedures.md), except that the passing mechanism must be `ByVal`.</span></span>  
  
 <span data-ttu-id="1f828-135">パラメーター リスト内の各パラメーターの構文は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="1f828-135">The syntax for each parameter in the parameter list is as follows:</span></span>  
  
 `[Optional] ByVal [ParamArray] parametername As datatype`  
  
 <span data-ttu-id="1f828-136">パラメーターが省略可能な場合は、その宣言の一部として既定値も指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1f828-136">If the parameter is optional, you must also supply a default value as part of its declaration.</span></span> <span data-ttu-id="1f828-137">既定値を指定する構文は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="1f828-137">The syntax for specifying a default value is as follows:</span></span>  
  
 `Optional ByVal parametername As datatype = defaultvalue`  
  
## <a name="property-value"></a><span data-ttu-id="1f828-138">プロパティ値</span><span class="sxs-lookup"><span data-stu-id="1f828-138">Property Value</span></span>  
 <span data-ttu-id="1f828-139">`Get`プロシージャ、戻り値は、プロパティの値として呼び出し元の式に渡されます。</span><span class="sxs-lookup"><span data-stu-id="1f828-139">In a `Get` procedure, the return value is supplied to the calling expression as the value of the property.</span></span>  
  
 <span data-ttu-id="1f828-140">`Set`プロシージャのパラメーターに新しいプロパティ値が渡される、`Set`ステートメント。</span><span class="sxs-lookup"><span data-stu-id="1f828-140">In a `Set` procedure, the new property value is passed to the parameter of the `Set` statement.</span></span> <span data-ttu-id="1f828-141">パラメーターを明示的に宣言する場合は、プロパティと同じデータ型で宣言する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1f828-141">If you explicitly declare a parameter, you must declare it with the same data type as the property.</span></span> <span data-ttu-id="1f828-142">コンパイラは、暗黙のパラメーターを使用するパラメーターを宣言していない場合`Value`をプロパティに割り当てられる新しい値を表します。</span><span class="sxs-lookup"><span data-stu-id="1f828-142">If you do not declare a parameter, the compiler uses the implicit parameter `Value` to represent the new value to be assigned to the property.</span></span>  
  
## <a name="calling-syntax"></a><span data-ttu-id="1f828-143">呼び出し構文</span><span class="sxs-lookup"><span data-stu-id="1f828-143">Calling Syntax</span></span>  
 <span data-ttu-id="1f828-144">プロパティ プロシージャは、プロパティを参照することによって暗黙的を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="1f828-144">You invoke a property procedure implicitly by making reference to the property.</span></span> <span data-ttu-id="1f828-145">使用するプロパティの名前、変数の名前を使用する場合と同じ方法は、省略できないすべての引数の値を指定する必要がありますが、引数リストをかっこで囲む必要があります。</span><span class="sxs-lookup"><span data-stu-id="1f828-145">You use the name of the property the same way you would use the name of a variable, except that you must provide values for all arguments that are not optional, and you must enclose the argument list in parentheses.</span></span> <span data-ttu-id="1f828-146">引数が指定されていない場合、かっこを省略することができます。</span><span class="sxs-lookup"><span data-stu-id="1f828-146">If no arguments are supplied, you can optionally omit the parentheses.</span></span>  
  
 <span data-ttu-id="1f828-147">暗黙的な呼び出しの構文、`Set`手順のとおりです。</span><span class="sxs-lookup"><span data-stu-id="1f828-147">The syntax for an implicit call to a `Set` procedure is as follows:</span></span>  
  
 `propertyname[(argumentlist)] = expression`  
  
 <span data-ttu-id="1f828-148">暗黙的な呼び出しの構文、`Get`手順のとおりです。</span><span class="sxs-lookup"><span data-stu-id="1f828-148">The syntax for an implicit call to a `Get` procedure is as follows:</span></span>  
  
 `lvalue = propertyname[(argumentlist)]`  
  
 `Do While (propertyname[(argumentlist)] > expression)`  
  
### <a name="illustration-of-declaration-and-call"></a><span data-ttu-id="1f828-149">宣言と呼び出しの図</span><span class="sxs-lookup"><span data-stu-id="1f828-149">Illustration of Declaration and Call</span></span>  
 <span data-ttu-id="1f828-150">次のプロパティは、2 つの構成名、名、および、最後の名前として、完全な名前を格納します。</span><span class="sxs-lookup"><span data-stu-id="1f828-150">The following property stores a full name as two constituent names, the first name and the last name.</span></span> <span data-ttu-id="1f828-151">呼び出し元のコードを読み取るとき`fullName`、`Get`プロシージャは、2 つの構成名を結合し、完全な名前を返します。</span><span class="sxs-lookup"><span data-stu-id="1f828-151">When the calling code reads `fullName`, the `Get` procedure combines the two constituent names and returns the full name.</span></span> <span data-ttu-id="1f828-152">呼び出し元のコードによって、新しい完全な名前を割り当てられるとき、`Set`プロシージャは、それを 2 つの部分に分割しようと試みます。</span><span class="sxs-lookup"><span data-stu-id="1f828-152">When the calling code assigns a new full name, the `Set` procedure attempts to break it into two constituent names.</span></span> <span data-ttu-id="1f828-153">場所が見つからない場合すべて最初の名前として格納します。</span><span class="sxs-lookup"><span data-stu-id="1f828-153">If it does not find a space, it stores it all as the first name.</span></span>  
  
 [!code-vb[VbVbcnProcedures#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#8)]  
  
 <span data-ttu-id="1f828-154">次の例では、一般的なプロパティ プロシージャの呼び出し`fullName`します。</span><span class="sxs-lookup"><span data-stu-id="1f828-154">The following example shows typical calls to the property procedures of `fullName`.</span></span>  
  
 [!code-vb[VbVbcnProcedures#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#9)]  
  
## <a name="see-also"></a><span data-ttu-id="1f828-155">関連項目</span><span class="sxs-lookup"><span data-stu-id="1f828-155">See also</span></span>

- [<span data-ttu-id="1f828-156">プロシージャ</span><span class="sxs-lookup"><span data-stu-id="1f828-156">Procedures</span></span>](./index.md)
- [<span data-ttu-id="1f828-157">Function プロシージャ</span><span class="sxs-lookup"><span data-stu-id="1f828-157">Function Procedures</span></span>](./function-procedures.md)
- [<span data-ttu-id="1f828-158">演算子プロシージャ</span><span class="sxs-lookup"><span data-stu-id="1f828-158">Operator Procedures</span></span>](./operator-procedures.md)
- [<span data-ttu-id="1f828-159">プロシージャのパラメーターと引数</span><span class="sxs-lookup"><span data-stu-id="1f828-159">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="1f828-160">Visual Basic でのプロパティと変数の違い</span><span class="sxs-lookup"><span data-stu-id="1f828-160">Differences Between Properties and Variables in Visual Basic</span></span>](./differences-between-properties-and-variables.md)
- [<span data-ttu-id="1f828-161">方法: プロパティを作成します。</span><span class="sxs-lookup"><span data-stu-id="1f828-161">How to: Create a Property</span></span>](./how-to-create-a-property.md)
- [<span data-ttu-id="1f828-162">方法: プロパティ プロシージャを呼び出す</span><span class="sxs-lookup"><span data-stu-id="1f828-162">How to: Call a Property Procedure</span></span>](./how-to-call-a-property-procedure.md)
- [<span data-ttu-id="1f828-163">方法: 宣言し、Visual Basic では、既定のプロパティを呼び出す</span><span class="sxs-lookup"><span data-stu-id="1f828-163">How to: Declare and Call a Default Property in Visual Basic</span></span>](./how-to-declare-and-call-a-default-property.md)
- [<span data-ttu-id="1f828-164">方法: プロパティに値を格納します。</span><span class="sxs-lookup"><span data-stu-id="1f828-164">How to: Put a Value in a Property</span></span>](./how-to-put-a-value-in-a-property.md)
- [<span data-ttu-id="1f828-165">方法: プロパティから値を取得します。</span><span class="sxs-lookup"><span data-stu-id="1f828-165">How to: Get a Value from a Property</span></span>](./how-to-get-a-value-from-a-property.md)
