---
title: Property プロシージャ
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
ms.openlocfilehash: cb5b0e12512e476b7c96bbfb19f8e4f470f6b498
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2020
ms.locfileid: "84363734"
---
# <a name="property-procedures-visual-basic"></a><span data-ttu-id="73f14-102">Property プロシージャ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="73f14-102">Property Procedures (Visual Basic)</span></span>

<span data-ttu-id="73f14-103">プロパティ プロシージャは、モジュール、クラス、または構造体のカスタム プロパティを操作する一連の Visual Basic ステートメントです。</span><span class="sxs-lookup"><span data-stu-id="73f14-103">A property procedure is a series of Visual Basic statements that manipulate a custom property on a module, class, or structure.</span></span> <span data-ttu-id="73f14-104">プロパティ プロシージャは、"*プロパティ アクセサー*" とも呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="73f14-104">Property procedures are also known as *property accessors*.</span></span>

<span data-ttu-id="73f14-105">Visual Basic には、次のプロパティ プロシージャが用意されています。</span><span class="sxs-lookup"><span data-stu-id="73f14-105">Visual Basic provides for the following property procedures:</span></span>

- <span data-ttu-id="73f14-106">`Get` プロシージャは、プロパティの値を返します。</span><span class="sxs-lookup"><span data-stu-id="73f14-106">A `Get` procedure returns the value of a property.</span></span> <span data-ttu-id="73f14-107">式でプロパティにアクセスするときに呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="73f14-107">It is called when you access the property in an expression.</span></span>
- <span data-ttu-id="73f14-108">`Set` プロシージャは、プロパティを値 (オブジェクト参照を含む) に設定します。</span><span class="sxs-lookup"><span data-stu-id="73f14-108">A `Set` procedure sets a property to a value, including an object reference.</span></span> <span data-ttu-id="73f14-109">プロパティに値を割り当てるときに呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="73f14-109">It is called when you assign a value to the property.</span></span>

<span data-ttu-id="73f14-110">通常は、`Get` および `Set` ステートメントを使用して、プロパティ プロシージャをペアで定義しますが、プロパティが読み取り専用 ([Get ステートメント](../../../language-reference/statements/get-statement.md)) または書き込み専用 ([Set ステートメント](../../../language-reference/statements/set-statement.md)) の場合は、いずれかのプロシージャだけを定義できます。</span><span class="sxs-lookup"><span data-stu-id="73f14-110">You usually define property procedures in pairs, using the `Get` and `Set` statements, but you can define either procedure alone if the property is read-only ([Get Statement](../../../language-reference/statements/get-statement.md)) or write-only ([Set Statement](../../../language-reference/statements/set-statement.md)).</span></span>

<span data-ttu-id="73f14-111">自動実装プロパティを使用する場合は、`Get` および `Set` プロシージャを省略できます。</span><span class="sxs-lookup"><span data-stu-id="73f14-111">You can omit the `Get` and `Set` procedure when using an auto-implemented property.</span></span> <span data-ttu-id="73f14-112">詳細については、「[自動実装プロパティ](./auto-implemented-properties.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="73f14-112">For more information, see [Auto-Implemented Properties](./auto-implemented-properties.md).</span></span>

<span data-ttu-id="73f14-113">プロパティは、クラス、構造体、モジュールで定義できます。</span><span class="sxs-lookup"><span data-stu-id="73f14-113">You can define properties in classes, structures, and modules.</span></span> <span data-ttu-id="73f14-114">プロパティは既定で `Public` であるため、プロパティのコンテナーにアクセスできるアプリケーション内のどこからでも呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="73f14-114">Properties are `Public` by default, which means you can call them from anywhere in your application that can access the property's container.</span></span>

<span data-ttu-id="73f14-115">プロパティと変数の比較については、「[Differences Between Properties and Variables in Visual Basic (Visual Basic のプロパティと変数の違い)](differences-between-properties-and-variables.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="73f14-115">For a comparison of properties and variables, see [Differences Between Properties and Variables in Visual Basic](differences-between-properties-and-variables.md).</span></span>

## <a name="declaration-syntax"></a><span data-ttu-id="73f14-116">宣言の構文</span><span class="sxs-lookup"><span data-stu-id="73f14-116">Declaration syntax</span></span>

<span data-ttu-id="73f14-117">プロパティ自体は、[Property ステートメント](../../../language-reference/statements/property-statement.md)と `End Property` ステートメントで囲まれたコード ブロックによって定義されます。</span><span class="sxs-lookup"><span data-stu-id="73f14-117">A property itself is defined by a block of code enclosed within the [Property Statement](../../../language-reference/statements/property-statement.md) and the `End Property` statement.</span></span> <span data-ttu-id="73f14-118">このブロック内では、各プロパティ プロシージャは、宣言ステートメント (`Get` または `Set`) と、対応する `End` 宣言で囲まれた内部ブロックとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="73f14-118">Inside this block, each property procedure appears as an internal block enclosed within a declaration statement (`Get` or `Set`) and the matching `End` declaration.</span></span>

<span data-ttu-id="73f14-119">プロパティとそのプロシージャを宣言するための構文は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="73f14-119">The syntax for declaring a property and its procedures is as follows:</span></span>

```vb
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
' - or -
[Default] [Modifiers] Property PropertyName [(ParameterList)] [As DataType]
```

<span data-ttu-id="73f14-120">`Modifiers` では、アクセス レベルと、オーバーロード、オーバーライド、共有、シャドウに関する情報、およびプロパティが読み取り専用または書き込み専用かどうかを指定できます。</span><span class="sxs-lookup"><span data-stu-id="73f14-120">The `Modifiers` can specify access level and information regarding overloading, overriding, sharing, and shadowing, as well as whether the property is read-only or write-only.</span></span> <span data-ttu-id="73f14-121">`Get` または `Set` プロシージャの `AccessLevel` には、プロパティ自体に指定されたアクセス レベルよりも制限の厳しい任意のレベルを指定できます。</span><span class="sxs-lookup"><span data-stu-id="73f14-121">The `AccessLevel` on the `Get` or `Set` procedure can be any level that is more restrictive than the access level specified for the property itself.</span></span> <span data-ttu-id="73f14-122">詳細については、「[Property Statement (Property ステートメント)](../../../language-reference/statements/property-statement.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="73f14-122">For more information, see [Property Statement](../../../language-reference/statements/property-statement.md).</span></span>

### <a name="data-type"></a><span data-ttu-id="73f14-123">データの種類</span><span class="sxs-lookup"><span data-stu-id="73f14-123">Data Type</span></span>

<span data-ttu-id="73f14-124">プロパティのデータ型とプリンシパル アクセス レベルは、プロパティ プロシージャではなく、`Property` ステートメントで定義されます。</span><span class="sxs-lookup"><span data-stu-id="73f14-124">A property's data type and principal access level are defined in the `Property` statement, not in the property procedures.</span></span> <span data-ttu-id="73f14-125">プロパティはデータ型を 1 つだけ持つことができます。</span><span class="sxs-lookup"><span data-stu-id="73f14-125">A property can have only one data type.</span></span> <span data-ttu-id="73f14-126">たとえば、`Decimal` 値を格納し、`Double` 値を取得するプロパティを定義することはできません。</span><span class="sxs-lookup"><span data-stu-id="73f14-126">For example, you cannot define a property to store a `Decimal` value but retrieve a `Double` value.</span></span>

### <a name="access-level"></a><span data-ttu-id="73f14-127">アクセス レベル</span><span class="sxs-lookup"><span data-stu-id="73f14-127">Access Level</span></span>

<span data-ttu-id="73f14-128">プロパティのプリンシパル アクセス レベルを定義し、プロパティ プロシージャの 1 つでアクセス レベルをさらに制限できます。</span><span class="sxs-lookup"><span data-stu-id="73f14-128">However, you can define a principal access level for a property and further restrict the access level in one of its property procedures.</span></span> <span data-ttu-id="73f14-129">たとえば、`Public` プロパティを定義し、`Private Set` プロシージャを定義できます。</span><span class="sxs-lookup"><span data-stu-id="73f14-129">For example, you can define a `Public` property and then define a `Private Set` procedure.</span></span> <span data-ttu-id="73f14-130">`Get` プロシージャは `Public` のままです。</span><span class="sxs-lookup"><span data-stu-id="73f14-130">The `Get` procedure remains `Public`.</span></span> <span data-ttu-id="73f14-131">アクセス レベルは、プロパティのプロシージャの 1 つでのみ変更することができ、プリンシパル アクセス レベルよりも厳しい制限にすることだけが可能です。</span><span class="sxs-lookup"><span data-stu-id="73f14-131">You can change the access level in only one of a property's procedures, and you can only make it more restrictive than the principal access level.</span></span> <span data-ttu-id="73f14-132">詳細については、「[方法:方法: 複数のアクセス レベルを持つプロパティを宣言する](how-to-declare-a-property-with-mixed-access-levels.md) をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="73f14-132">For more information, see [How to: Declare a Property with Mixed Access Levels](how-to-declare-a-property-with-mixed-access-levels.md).</span></span>

## <a name="parameter-declaration"></a><span data-ttu-id="73f14-133">パラメーターの宣言</span><span class="sxs-lookup"><span data-stu-id="73f14-133">Parameter declaration</span></span>

<span data-ttu-id="73f14-134">引渡し方法に `ByVal` を指定する必要がある点を除き、[Sub プロシージャ](sub-procedures.md)の場合と同様に各パラメーターを宣言します。</span><span class="sxs-lookup"><span data-stu-id="73f14-134">You declare each parameter the same way you do for [Sub Procedures](sub-procedures.md), except that the passing mechanism must be `ByVal`.</span></span>

<span data-ttu-id="73f14-135">パラメーター リストの各パラメーターの構文は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="73f14-135">The syntax for each parameter in the parameter list is as follows:</span></span>

```vb
[Optional] ByVal [ParamArray] parametername As datatype
```

<span data-ttu-id="73f14-136">パラメーターが省略可能な場合は、宣言の一部として既定値も指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="73f14-136">If the parameter is optional, you must also supply a default value as part of its declaration.</span></span> <span data-ttu-id="73f14-137">既定値を指定するための構文は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="73f14-137">The syntax for specifying a default value is as follows:</span></span>

```vb
Optional ByVal parametername As datatype = defaultvalue
```

## <a name="property-value"></a><span data-ttu-id="73f14-138">プロパティ値</span><span class="sxs-lookup"><span data-stu-id="73f14-138">Property value</span></span>

<span data-ttu-id="73f14-139">`Get` プロシージャでは、戻り値は呼び出し元の式にプロパティの値として指定されます。</span><span class="sxs-lookup"><span data-stu-id="73f14-139">In a `Get` procedure, the return value is supplied to the calling expression as the value of the property.</span></span>

<span data-ttu-id="73f14-140">`Set` プロシージャでは、新しいプロパティ値が `Set` ステートメントのパラメーターに渡されます。</span><span class="sxs-lookup"><span data-stu-id="73f14-140">In a `Set` procedure, the new property value is passed to the parameter of the `Set` statement.</span></span> <span data-ttu-id="73f14-141">パラメーターを明示的に宣言する場合は、プロパティと同じデータ型で宣言する必要があります。</span><span class="sxs-lookup"><span data-stu-id="73f14-141">If you explicitly declare a parameter, you must declare it with the same data type as the property.</span></span> <span data-ttu-id="73f14-142">パラメーターを宣言していない場合、コンパイラは暗黙的な `Value` パラメーターを使用して、プロパティに割り当てられる新しい値を表します。</span><span class="sxs-lookup"><span data-stu-id="73f14-142">If you do not declare a parameter, the compiler uses the implicit parameter `Value` to represent the new value to be assigned to the property.</span></span>

## <a name="calling-syntax"></a><span data-ttu-id="73f14-143">呼び出しの構文</span><span class="sxs-lookup"><span data-stu-id="73f14-143">Calling syntax</span></span>

<span data-ttu-id="73f14-144">プロパティを参照することにより、プロパティ プロシージャを暗黙的に呼び出します。</span><span class="sxs-lookup"><span data-stu-id="73f14-144">You invoke a property procedure implicitly by making reference to the property.</span></span> <span data-ttu-id="73f14-145">プロパティの名前は、変数の名前を使用する場合と同様に使用します。ただし、省略可能ではないすべての引数に値を指定する必要があり、引数リストをかっこで囲む必要があります。</span><span class="sxs-lookup"><span data-stu-id="73f14-145">You use the name of the property the same way you would use the name of a variable, except that you must provide values for all arguments that are not optional, and you must enclose the argument list in parentheses.</span></span> <span data-ttu-id="73f14-146">引数を指定しない場合は、必要に応じてかっこを省略できます。</span><span class="sxs-lookup"><span data-stu-id="73f14-146">If no arguments are supplied, you can optionally omit the parentheses.</span></span>

<span data-ttu-id="73f14-147">`Set` プロシージャの暗黙的な呼び出しの構文は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="73f14-147">The syntax for an implicit call to a `Set` procedure is as follows:</span></span>

```vb
propertyname[(argumentlist)] = expression
```

<span data-ttu-id="73f14-148">`Get` プロシージャの暗黙的な呼び出しの構文は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="73f14-148">The syntax for an implicit call to a `Get` procedure is as follows:</span></span>

```vb
lvalue = propertyname[(argumentlist)]
Do While (propertyname[(argumentlist)] > expression)
```

### <a name="illustration-of-declaration-and-call"></a><span data-ttu-id="73f14-149">宣言と呼び出しの実例</span><span class="sxs-lookup"><span data-stu-id="73f14-149">Illustration of declaration and call</span></span>

<span data-ttu-id="73f14-150">次のプロパティは、フル ネームを 2 つの構成要素名 (名と姓) として格納します。</span><span class="sxs-lookup"><span data-stu-id="73f14-150">The following property stores a full name as two constituent names, the first name and the last name.</span></span> <span data-ttu-id="73f14-151">呼び出し元のコードが `fullName` を読み取ると、`Get` プロシージャが 2 つの構成要素名を結合し、フル ネームを返します。</span><span class="sxs-lookup"><span data-stu-id="73f14-151">When the calling code reads `fullName`, the `Get` procedure combines the two constituent names and returns the full name.</span></span> <span data-ttu-id="73f14-152">呼び出し元のコードが新しいフル ネームを割り当てると、`Set` プロシージャがそれを 2 つの構成要素名に分割することを試みます。</span><span class="sxs-lookup"><span data-stu-id="73f14-152">When the calling code assigns a new full name, the `Set` procedure attempts to break it into two constituent names.</span></span> <span data-ttu-id="73f14-153">スペースが見つからない場合は、すべてが名として格納されます。</span><span class="sxs-lookup"><span data-stu-id="73f14-153">If it does not find a space, it stores it all as the first name.</span></span>

[!code-vb[VbVbcnProcedures#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#8)]

<span data-ttu-id="73f14-154">次の例は、`fullName` のプロパティ プロシージャの一般的な呼び出しを示しています。</span><span class="sxs-lookup"><span data-stu-id="73f14-154">The following example shows typical calls to the property procedures of `fullName`:</span></span>

[!code-vb[VbVbcnProcedures#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#9)]

## <a name="see-also"></a><span data-ttu-id="73f14-155">関連項目</span><span class="sxs-lookup"><span data-stu-id="73f14-155">See also</span></span>

- [<span data-ttu-id="73f14-156">手順</span><span class="sxs-lookup"><span data-stu-id="73f14-156">Procedures</span></span>](index.md)
- [<span data-ttu-id="73f14-157">Function プロシージャ</span><span class="sxs-lookup"><span data-stu-id="73f14-157">Function Procedures</span></span>](function-procedures.md)
- [<span data-ttu-id="73f14-158">演算子プロシージャ</span><span class="sxs-lookup"><span data-stu-id="73f14-158">Operator Procedures</span></span>](operator-procedures.md)
- [<span data-ttu-id="73f14-159">プロシージャのパラメーターと引数</span><span class="sxs-lookup"><span data-stu-id="73f14-159">Procedure Parameters and Arguments</span></span>](procedure-parameters-and-arguments.md)
- [<span data-ttu-id="73f14-160">Visual Basic のプロパティと変数の違い</span><span class="sxs-lookup"><span data-stu-id="73f14-160">Differences Between Properties and Variables in Visual Basic</span></span>](differences-between-properties-and-variables.md)
- [<span data-ttu-id="73f14-161">方法: プロパティを作成する</span><span class="sxs-lookup"><span data-stu-id="73f14-161">How to: Create a Property</span></span>](how-to-create-a-property.md)
- [<span data-ttu-id="73f14-162">方法: プロパティ プロシージャを呼び出す</span><span class="sxs-lookup"><span data-stu-id="73f14-162">How to: Call a Property Procedure</span></span>](how-to-call-a-property-procedure.md)
- [<span data-ttu-id="73f14-163">方法: 既定のプロパティを宣言して呼び出す (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="73f14-163">How to: Declare and Call a Default Property in Visual Basic</span></span>](how-to-declare-and-call-a-default-property.md)
- [<span data-ttu-id="73f14-164">方法: プロパティに値を格納する</span><span class="sxs-lookup"><span data-stu-id="73f14-164">How to: Put a Value in a Property</span></span>](how-to-put-a-value-in-a-property.md)
- [<span data-ttu-id="73f14-165">方法: プロパティから値を取得する</span><span class="sxs-lookup"><span data-stu-id="73f14-165">How to: Get a Value from a Property</span></span>](how-to-get-a-value-from-a-property.md)
