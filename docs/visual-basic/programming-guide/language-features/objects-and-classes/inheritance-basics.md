---
title: 継承の基本
ms.date: 07/20/2015
helpviewer_keywords:
- derived classes [Visual Basic], inheritance
- MyClass keyword [Visual Basic], using
- MyBase keyword [Visual Basic], using
- Inherits statement [Visual Basic], inheritance
- overriding, Overridable keyword
- MustInherit keyword [Visual Basic], using
- Overrides keyword [Visual Basic], using
- inheritance
- MustInherit classes [Visual Basic]
- MustOverride keyword [Visual Basic], using
- classes [Visual Basic], derived
- NotInheritable keyword [Visual Basic], using
- base classes [Visual Basic], extending properties and methods [Visual Basic]
- NotOverridable keyword [Visual Basic], using
- base classes [Visual Basic], inheritance
- abstract classes [Visual Basic], inheritance
- overriding, Overrides keyword
ms.assetid: dfc8deba-f5b3-4d1d-a937-7cb826446fc5
ms.openlocfilehash: 89fcf2a14d8938d536aa72628218242811baa1a2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401461"
---
# <a name="inheritance-basics-visual-basic"></a><span data-ttu-id="3cdfb-102">継承の基本 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3cdfb-102">Inheritance Basics (Visual Basic)</span></span>

<span data-ttu-id="3cdfb-103">この`Inherits`ステートメントは、*基本*クラス と呼ばれる既存のクラスに基づいて、*派生クラス*と呼ばれる新しいクラスを宣言するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="3cdfb-103">The `Inherits` statement is used to declare a new class, called a *derived class*, based on an existing class, known as a *base class*.</span></span> <span data-ttu-id="3cdfb-104">派生クラスは、基本クラスで定義されたプロパティ、メソッド、イベント、フィールド、および定数を継承し、拡張できます。</span><span class="sxs-lookup"><span data-stu-id="3cdfb-104">Derived classes inherit, and can extend, the properties, methods, events, fields, and constants defined in the base class.</span></span> <span data-ttu-id="3cdfb-105">次のセクションでは、継承の規則と、クラスの継承または継承方法を変更するために使用できる修飾子について説明します。</span><span class="sxs-lookup"><span data-stu-id="3cdfb-105">The following section describes some of the rules for inheritance, and the modifiers you can use to change the way classes inherit or are inherited:</span></span>

- <span data-ttu-id="3cdfb-106">デフォルトでは、キーワードでマークしない限り、すべてのクラス`NotInheritable`を継承できます。</span><span class="sxs-lookup"><span data-stu-id="3cdfb-106">By default, all classes are inheritable unless marked with the `NotInheritable` keyword.</span></span> <span data-ttu-id="3cdfb-107">クラスは、プロジェクト内の他のクラスから継承することも、プロジェクトが参照する他のアセンブリのクラスから継承することもできます。</span><span class="sxs-lookup"><span data-stu-id="3cdfb-107">Classes can inherit from other classes in your project or from classes in other assemblies that your project references.</span></span>

- <span data-ttu-id="3cdfb-108">複数の継承を許可する言語とは異なり、Visual Basic ではクラス内で単一の継承のみが許可されます。つまり、派生クラスは 1 つの基本クラスしか持てないです。</span><span class="sxs-lookup"><span data-stu-id="3cdfb-108">Unlike languages that allow multiple inheritance, Visual Basic allows only single inheritance in classes; that is, derived classes can have only one base class.</span></span> <span data-ttu-id="3cdfb-109">クラスでは多重継承は許可されていませんが、クラスは複数のインターフェイスを実装できるため、同じ目的を効果的に実現できます。</span><span class="sxs-lookup"><span data-stu-id="3cdfb-109">Although multiple inheritance is not allowed in classes, classes can implement multiple interfaces, which can effectively accomplish the same ends.</span></span>

- <span data-ttu-id="3cdfb-110">制限された項目が基本クラスに公開されないようにするには、派生クラスのアクセス型は、基本クラスと同じか、その基底クラスよりも制限の厳しい型である必要があります。</span><span class="sxs-lookup"><span data-stu-id="3cdfb-110">To prevent exposing restricted items in a base class, the access type of a derived class must be equal to or more restrictive than its base class.</span></span> <span data-ttu-id="3cdfb-111">たとえば、クラスは`Public`クラスまたは`Friend`クラスを`Private`継承できず、クラス`Friend`はクラスを`Private`継承できません。</span><span class="sxs-lookup"><span data-stu-id="3cdfb-111">For example, a `Public` class cannot inherit a `Friend` or a `Private` class, and a `Friend` class cannot inherit a `Private` class.</span></span>

## <a name="inheritance-modifiers"></a><span data-ttu-id="3cdfb-112">継承修飾子</span><span class="sxs-lookup"><span data-stu-id="3cdfb-112">Inheritance Modifiers</span></span>

<span data-ttu-id="3cdfb-113">Visual Basic では、継承をサポートするために、次のクラス レベルのステートメントと修飾子が導入されています。</span><span class="sxs-lookup"><span data-stu-id="3cdfb-113">Visual Basic introduces the following class-level statements and modifiers to support inheritance:</span></span>

- <span data-ttu-id="3cdfb-114">`Inherits`文 — 基本クラスを指定します。</span><span class="sxs-lookup"><span data-stu-id="3cdfb-114">`Inherits` statement — Specifies the base class.</span></span>

- <span data-ttu-id="3cdfb-115">`NotInheritable`修飾子 — プログラマがクラスを基本クラスとして使用できないようにします。</span><span class="sxs-lookup"><span data-stu-id="3cdfb-115">`NotInheritable` modifier — Prevents programmers from using the class as a base class.</span></span>

- <span data-ttu-id="3cdfb-116">`MustInherit`modifier — クラスが基本クラスとしてのみ使用されることを指定します。</span><span class="sxs-lookup"><span data-stu-id="3cdfb-116">`MustInherit` modifier — Specifies that the class is intended for use as a base class only.</span></span> <span data-ttu-id="3cdfb-117">クラスの`MustInherit`インスタンスを直接作成することはできません。派生クラスの基本クラスインスタンスとしてのみ作成できます。</span><span class="sxs-lookup"><span data-stu-id="3cdfb-117">Instances of `MustInherit` classes cannot be created directly; they can only be created as base class instances of a derived class.</span></span> <span data-ttu-id="3cdfb-118">(C++ や C# などの他のプログラミング言語では、*抽象クラス*という用語を使用してこのようなクラスを記述します)。</span><span class="sxs-lookup"><span data-stu-id="3cdfb-118">(Other programming languages, such as C++ and C#, use the term *abstract class* to describe such a class.)</span></span>

## <a name="overriding-properties-and-methods-in-derived-classes"></a><span data-ttu-id="3cdfb-119">派生クラスでのプロパティとメソッドのオーバーライド</span><span class="sxs-lookup"><span data-stu-id="3cdfb-119">Overriding Properties and Methods in Derived Classes</span></span>

<span data-ttu-id="3cdfb-120">既定では、派生クラスは基本クラスからプロパティとメソッドを継承します。</span><span class="sxs-lookup"><span data-stu-id="3cdfb-120">By default, a derived class inherits properties and methods from its base class.</span></span> <span data-ttu-id="3cdfb-121">継承されたプロパティまたはメソッドが派生クラスで異なる動作をする*必要がある場合*は、オーバーライドできます。</span><span class="sxs-lookup"><span data-stu-id="3cdfb-121">If an inherited property or method has to behave differently in the derived class it can be *overridden*.</span></span> <span data-ttu-id="3cdfb-122">つまり、派生クラスでメソッドの新しい実装を定義できます。</span><span class="sxs-lookup"><span data-stu-id="3cdfb-122">That is, you can define a new implementation of the method in the derived class.</span></span> <span data-ttu-id="3cdfb-123">プロパティやメソッドのオーバーライド方法を制御するには、次の修飾子を使用します。</span><span class="sxs-lookup"><span data-stu-id="3cdfb-123">The following modifiers are used to control how properties and methods are overridden:</span></span>

- <span data-ttu-id="3cdfb-124">`Overridable`— クラス内のプロパティまたはメソッドを派生クラスでオーバーライドできます。</span><span class="sxs-lookup"><span data-stu-id="3cdfb-124">`Overridable` — Allows a property or method in a class to be overridden in a derived class.</span></span>

- <span data-ttu-id="3cdfb-125">`Overrides`— 基本クラス`Overridable`で定義されたプロパティまたはメソッドをオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="3cdfb-125">`Overrides` — Overrides an `Overridable` property or method defined in the base class.</span></span>

- <span data-ttu-id="3cdfb-126">`NotOverridable`— 継承クラスでプロパティまたはメソッドがオーバーライドされないようにします。</span><span class="sxs-lookup"><span data-stu-id="3cdfb-126">`NotOverridable` — Prevents a property or method from being overridden in an inheriting class.</span></span> <span data-ttu-id="3cdfb-127">既定では、`Public`メソッドは`NotOverridable`です。</span><span class="sxs-lookup"><span data-stu-id="3cdfb-127">By default, `Public` methods are `NotOverridable`.</span></span>

- <span data-ttu-id="3cdfb-128">`MustOverride`— 派生クラスがプロパティまたはメソッドをオーバーライドする必要があります。</span><span class="sxs-lookup"><span data-stu-id="3cdfb-128">`MustOverride` — Requires that a derived class override the property or method.</span></span> <span data-ttu-id="3cdfb-129">キーワードを`MustOverride`使用する場合、メソッド定義は`Sub`、 、`Function`または`Property`ステートメントだけで構成されます。</span><span class="sxs-lookup"><span data-stu-id="3cdfb-129">When the `MustOverride` keyword is used, the method definition consists of just the `Sub`, `Function`, or `Property` statement.</span></span> <span data-ttu-id="3cdfb-130">他のステートメントは許可されず、具体的にはステートメントや`End Sub``End Function`ステートメントはありません。</span><span class="sxs-lookup"><span data-stu-id="3cdfb-130">No other statements are allowed, and specifically there is no `End Sub` or `End Function` statement.</span></span> <span data-ttu-id="3cdfb-131">`MustOverride`メソッドはクラスで`MustInherit`宣言する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3cdfb-131">`MustOverride` methods must be declared in `MustInherit` classes.</span></span>

<span data-ttu-id="3cdfb-132">給与計算を処理するクラスを定義するとします。</span><span class="sxs-lookup"><span data-stu-id="3cdfb-132">Suppose you want to define classes to handle payroll.</span></span> <span data-ttu-id="3cdfb-133">一般的な週の`Payroll`給与を計算する`RunPayroll`メソッドを含むジェネリック クラスを定義できます。</span><span class="sxs-lookup"><span data-stu-id="3cdfb-133">You could define a generic `Payroll` class that contains a `RunPayroll` method that calculates payroll for a typical week.</span></span> <span data-ttu-id="3cdfb-134">その後、従業員`Payroll`の賞与を配布するときに使用できる、`BonusPayroll`より専門的なクラスの基本クラスとして使用できます。</span><span class="sxs-lookup"><span data-stu-id="3cdfb-134">You could then use `Payroll` as a base class for a more specialized `BonusPayroll` class, which could be used when distributing employee bonuses.</span></span>

<span data-ttu-id="3cdfb-135">クラス`BonusPayroll`は、基本`Payroll`クラスで定義されているメソッド`PayEmployee`を継承し、オーバーライドできます。</span><span class="sxs-lookup"><span data-stu-id="3cdfb-135">The `BonusPayroll` class can inherit, and override, the `PayEmployee` method defined in the base `Payroll` class.</span></span>

<span data-ttu-id="3cdfb-136">次の例では、基本クラスと`Payroll,`、継承されたメソッド`BonusPayroll`をオーバーライドする派生クラス を定義`PayEmployee`します。</span><span class="sxs-lookup"><span data-stu-id="3cdfb-136">The following example defines a base class, `Payroll,` and a derived class, `BonusPayroll`, which overrides an inherited method, `PayEmployee`.</span></span> <span data-ttu-id="3cdfb-137">プロシージャ は`RunPayroll`、`Payroll`オブジェクトと`BonusPayroll`オブジェクトを作成し、`Pay`両方のオブジェクトの`PayEmployee`メソッドを実行する関数 に渡します。</span><span class="sxs-lookup"><span data-stu-id="3cdfb-137">A procedure, `RunPayroll`, creates and then passes a `Payroll` object and a `BonusPayroll` object to a function, `Pay`, that executes the `PayEmployee` method of both objects.</span></span>

[!code-vb[VbVbalrOOP#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#28)]

## <a name="the-mybase-keyword"></a><span data-ttu-id="3cdfb-138">マイベースキーワード</span><span class="sxs-lookup"><span data-stu-id="3cdfb-138">The MyBase Keyword</span></span>

<span data-ttu-id="3cdfb-139">キーワード`MyBase`は、クラスの現在のインスタンスの基本クラスを参照するオブジェクト変数のように動作します。</span><span class="sxs-lookup"><span data-stu-id="3cdfb-139">The `MyBase` keyword behaves like an object variable that refers to the base class of the current instance of a class.</span></span> <span data-ttu-id="3cdfb-140">`MyBase`は、派生クラスでオーバーライドまたはシャドウされる基本クラスのメンバーにアクセスするために頻繁に使用されます。</span><span class="sxs-lookup"><span data-stu-id="3cdfb-140">`MyBase` is frequently used to access base class members that are overridden or shadowed in a derived class.</span></span> <span data-ttu-id="3cdfb-141">特に、`MyBase.New`派生クラスのコンストラクターから基本クラスコンストラクターを明示的に呼び出すために使用されます。</span><span class="sxs-lookup"><span data-stu-id="3cdfb-141">In particular, `MyBase.New` is used to explicitly call a base class constructor from a derived class constructor.</span></span>

<span data-ttu-id="3cdfb-142">たとえば、基本クラスから継承されたメソッドをオーバーライドする派生クラスをデザインするとします。</span><span class="sxs-lookup"><span data-stu-id="3cdfb-142">For example, suppose you are designing a derived class that overrides a method inherited from the base class.</span></span> <span data-ttu-id="3cdfb-143">オーバーライドされたメソッドは、基本クラスのメソッドを呼び出し、次のコードに示すように戻り値を変更できます。</span><span class="sxs-lookup"><span data-stu-id="3cdfb-143">The overridden method can call the method in the base class and modify the return value as shown in the following code fragment:</span></span>

[!code-vb[VbVbalrOOP#109](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#109)]

<span data-ttu-id="3cdfb-144">を使用`MyBase`する場合の制限事項を次に示します。</span><span class="sxs-lookup"><span data-stu-id="3cdfb-144">The following list describes restrictions on using `MyBase`:</span></span>

- <span data-ttu-id="3cdfb-145">`MyBase`は、直接の基本クラスとその継承されたメンバーを指します。</span><span class="sxs-lookup"><span data-stu-id="3cdfb-145">`MyBase` refers to the immediate base class and its inherited members.</span></span> <span data-ttu-id="3cdfb-146">クラスのメンバーにアクセス`Private`するために使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="3cdfb-146">It cannot be used to access `Private` members in the class.</span></span>

- <span data-ttu-id="3cdfb-147">`MyBase`はキーワードであり、実際のオブジェクトではありません。</span><span class="sxs-lookup"><span data-stu-id="3cdfb-147">`MyBase` is a keyword, not a real object.</span></span> <span data-ttu-id="3cdfb-148">`MyBase`変数に代入したり、プロシージャに渡したり、比較で`Is`使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="3cdfb-148">`MyBase` cannot be assigned to a variable, passed to procedures, or used in an `Is` comparison.</span></span>

- <span data-ttu-id="3cdfb-149">修飾する`MyBase`メソッドは、直接の基本クラスで定義する必要はありません。代わりに、間接的に継承された基本クラスで定義できます。</span><span class="sxs-lookup"><span data-stu-id="3cdfb-149">The method that `MyBase` qualifies does not have to be defined in the immediate base class; it may instead be defined in an indirectly inherited base class.</span></span> <span data-ttu-id="3cdfb-150">修飾された参照を正しくコンパイル`MyBase`するためには、一部の基本クラスに、呼び出しに表示されるパラメーターの名前と型に一致するメソッドが含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="3cdfb-150">In order for a reference qualified by `MyBase` to compile correctly, some base class must contain a method matching the name and types of parameters that appear in the call.</span></span>

- <span data-ttu-id="3cdfb-151">基本クラスの`MyBase`メソッドを`MustOverride`呼び出すためには使用できません。</span><span class="sxs-lookup"><span data-stu-id="3cdfb-151">You cannot use `MyBase` to call `MustOverride` base class methods.</span></span>

- <span data-ttu-id="3cdfb-152">`MyBase`自身を修飾するために使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="3cdfb-152">`MyBase` cannot be used to qualify itself.</span></span> <span data-ttu-id="3cdfb-153">したがって、次のコードは無効です。</span><span class="sxs-lookup"><span data-stu-id="3cdfb-153">Therefore, the following code is not valid:</span></span>

  `MyBase.MyBase.BtnOK_Click()`

- <span data-ttu-id="3cdfb-154">`MyBase`モジュールでは使用できません。</span><span class="sxs-lookup"><span data-stu-id="3cdfb-154">`MyBase` cannot be used in modules.</span></span>

- <span data-ttu-id="3cdfb-155">`MyBase`基本クラスが別のアセンブリにある場合と同様`Friend`にマークされている基本クラス のメンバーにアクセスするためには使用できません。</span><span class="sxs-lookup"><span data-stu-id="3cdfb-155">`MyBase` cannot be used to access base class members that are marked as `Friend` if the base class is in a different assembly.</span></span>

<span data-ttu-id="3cdfb-156">詳細と別の例については、「[方法 : 派生クラスによって非表示になっている変数にアクセス](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md)する 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3cdfb-156">For more information and another example, see [How to: Access a Variable Hidden by a Derived Class](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md).</span></span>

## <a name="the-myclass-keyword"></a><span data-ttu-id="3cdfb-157">マイクラスキーワード</span><span class="sxs-lookup"><span data-stu-id="3cdfb-157">The MyClass Keyword</span></span>

<span data-ttu-id="3cdfb-158">キーワード`MyClass`は、最初に実装されたクラスの現在のインスタンスを参照するオブジェクト変数のように動作します。</span><span class="sxs-lookup"><span data-stu-id="3cdfb-158">The `MyClass` keyword behaves like an object variable that refers to the current instance of a class as originally implemented.</span></span> <span data-ttu-id="3cdfb-159">`MyClass`は`Me`似ていますが、メソッドやプロパティの`MyClass`呼び出しはすべて[NotOverridable](../../../../visual-basic/language-reference/modifiers/notoverridable.md)と見なされます。</span><span class="sxs-lookup"><span data-stu-id="3cdfb-159">`MyClass` resembles `Me`, but every method and property call on `MyClass` is treated as if the method or property were [NotOverridable](../../../../visual-basic/language-reference/modifiers/notoverridable.md).</span></span> <span data-ttu-id="3cdfb-160">したがって、メソッドまたはプロパティは、派生クラスでオーバーライドしても影響を受けません。</span><span class="sxs-lookup"><span data-stu-id="3cdfb-160">Therefore, the method or property is not affected by overriding in a derived class.</span></span>

- <span data-ttu-id="3cdfb-161">`MyClass`はキーワードであり、実際のオブジェクトではありません。</span><span class="sxs-lookup"><span data-stu-id="3cdfb-161">`MyClass` is a keyword, not a real object.</span></span> <span data-ttu-id="3cdfb-162">`MyClass`変数に代入したり、プロシージャに渡したり、比較で`Is`使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="3cdfb-162">`MyClass` cannot be assigned to a variable, passed to procedures, or used in an `Is` comparison.</span></span>

- <span data-ttu-id="3cdfb-163">`MyClass`は、含まれているクラスとその継承されたメンバを指します。</span><span class="sxs-lookup"><span data-stu-id="3cdfb-163">`MyClass` refers to the containing class and its inherited members.</span></span>

- <span data-ttu-id="3cdfb-164">`MyClass`は`Shared`、メンバーの修飾子として使用できます。</span><span class="sxs-lookup"><span data-stu-id="3cdfb-164">`MyClass` can be used as a qualifier for `Shared` members.</span></span>

- <span data-ttu-id="3cdfb-165">`MyClass`メソッド内では`Shared`使用できませんが、インスタンス メソッド内でクラスの共有メンバーにアクセスするために使用できます。</span><span class="sxs-lookup"><span data-stu-id="3cdfb-165">`MyClass` cannot be used inside a `Shared` method, but can be used inside an instance method to access a shared member of a class.</span></span>

- <span data-ttu-id="3cdfb-166">`MyClass`標準モジュールでは使用できません。</span><span class="sxs-lookup"><span data-stu-id="3cdfb-166">`MyClass` cannot be used in standard modules.</span></span>

- <span data-ttu-id="3cdfb-167">`MyClass`は、基本クラスで定義され、そのクラスで提供されるメソッドの実装を持たないメソッドを修飾するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="3cdfb-167">`MyClass` can be used to qualify a method that is defined in a base class and that has no implementation of the method provided in that class.</span></span> <span data-ttu-id="3cdfb-168">このような参照は、`MyBase.`*メソッド*と同じ意味を持ちます。</span><span class="sxs-lookup"><span data-stu-id="3cdfb-168">Such a reference has the same meaning as `MyBase.`*Method*.</span></span>

<span data-ttu-id="3cdfb-169">次の例では、 `Me` `MyClass`と を比較します。</span><span class="sxs-lookup"><span data-stu-id="3cdfb-169">The following example compares `Me` and `MyClass`.</span></span>

```vb
Class baseClass
    Public Overridable Sub testMethod()
        MsgBox("Base class string")
    End Sub
    Public Sub useMe()
        ' The following call uses the calling class's method, even if
        ' that method is an override.
        Me.testMethod()
    End Sub
    Public Sub useMyClass()
        ' The following call uses this instance's method and not any
        ' override.
        MyClass.testMethod()
    End Sub
End Class
Class derivedClass : Inherits baseClass
    Public Overrides Sub testMethod()
        MsgBox("Derived class string")
    End Sub
End Class
Class testClasses
    Sub startHere()
        Dim testObj As derivedClass = New derivedClass()
        ' The following call displays "Derived class string".
        testObj.useMe()
        ' The following call displays "Base class string".
        testObj.useMyClass()
    End Sub
End Class
```

<span data-ttu-id="3cdfb-170">`testMethod`オーバーライドでも`derivedClass`、 キーワードを`MyClass``useMyClass`オーバーライドすると、オーバーライドの影響が null になり、コンパイラは、基本クラスのバージョンの`testMethod`を解決します。</span><span class="sxs-lookup"><span data-stu-id="3cdfb-170">Even though `derivedClass` overrides `testMethod`, the `MyClass` keyword in `useMyClass` nullifies the effects of overriding, and the compiler resolves the call to the base class version of `testMethod`.</span></span>

## <a name="see-also"></a><span data-ttu-id="3cdfb-171">関連項目</span><span class="sxs-lookup"><span data-stu-id="3cdfb-171">See also</span></span>

- [<span data-ttu-id="3cdfb-172">Inherits ステートメント</span><span class="sxs-lookup"><span data-stu-id="3cdfb-172">Inherits Statement</span></span>](../../../../visual-basic/language-reference/statements/inherits-statement.md)
- [<span data-ttu-id="3cdfb-173">Me、My、MyBase、および MyClass</span><span class="sxs-lookup"><span data-stu-id="3cdfb-173">Me, My, MyBase, and MyClass</span></span>](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
