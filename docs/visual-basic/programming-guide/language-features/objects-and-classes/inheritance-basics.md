---
title: 継承の基本 (Visual Basic)
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
ms.openlocfilehash: a31f69459465368dc7519b5126c6c4eb72e25d29
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64663006"
---
# <a name="inheritance-basics-visual-basic"></a><span data-ttu-id="cf03d-102">継承の基本 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="cf03d-102">Inheritance Basics (Visual Basic)</span></span>
<span data-ttu-id="cf03d-103">`Inherits`ステートメントを使用して、という新しいクラスを宣言、*クラスを派生*と呼ばれる、既存のクラスに基づいて、*基本クラス*します。</span><span class="sxs-lookup"><span data-stu-id="cf03d-103">The `Inherits` statement is used to declare a new class, called a *derived class*, based on an existing class, known as a *base class*.</span></span> <span data-ttu-id="cf03d-104">派生クラスでは、継承、およびプロパティ、メソッド、イベント、フィールド、および基底クラスで定義された定数は、拡張できます。</span><span class="sxs-lookup"><span data-stu-id="cf03d-104">Derived classes inherit, and can extend, the properties, methods, events, fields, and constants defined in the base class.</span></span> <span data-ttu-id="cf03d-105">次のセクションでは、いくつかの継承のルールについて説明し、方法クラスを変更する際、修飾子を継承または継承されます。</span><span class="sxs-lookup"><span data-stu-id="cf03d-105">The following section describes some of the rules for inheritance, and the modifiers you can use to change the way classes inherit or are inherited:</span></span>  
  
- <span data-ttu-id="cf03d-106">既定では、すべてのクラスは継承とマークされていない限り、`NotInheritable`キーワード。</span><span class="sxs-lookup"><span data-stu-id="cf03d-106">By default, all classes are inheritable unless marked with the `NotInheritable` keyword.</span></span> <span data-ttu-id="cf03d-107">クラスは、プロジェクト内の他のクラスとは、プロジェクトを参照するその他のアセンブリのクラスから継承できます。</span><span class="sxs-lookup"><span data-stu-id="cf03d-107">Classes can inherit from other classes in your project or from classes in other assemblies that your project references.</span></span>  
  
- <span data-ttu-id="cf03d-108">複数の継承を許可する言語とは異なり Visual Basic では単一継承のみです。派生クラスでは、1 つだけの基本クラスを持つことができます。</span><span class="sxs-lookup"><span data-stu-id="cf03d-108">Unlike languages that allow multiple inheritance, Visual Basic allows only single inheritance in classes; that is, derived classes can have only one base class.</span></span> <span data-ttu-id="cf03d-109">クラスには、多重継承することはできません、クラスは、同じ結果を効果的に実現できますが、複数のインターフェイスを実装できます。</span><span class="sxs-lookup"><span data-stu-id="cf03d-109">Although multiple inheritance is not allowed in classes, classes can implement multiple interfaces, which can effectively accomplish the same ends.</span></span>  
  
- <span data-ttu-id="cf03d-110">基底クラスでの制限付きの項目を公開することを防ぐためには、派生クラスのアクセスの種類に等しくないか、基底クラスよりもより制限の厳しいする必要があります。</span><span class="sxs-lookup"><span data-stu-id="cf03d-110">To prevent exposing restricted items in a base class, the access type of a derived class must be equal to or more restrictive than its base class.</span></span> <span data-ttu-id="cf03d-111">など、`Public`クラスは継承できません、`Friend`または`Private`クラス、および`Friend`クラスは継承できません、`Private`クラス。</span><span class="sxs-lookup"><span data-stu-id="cf03d-111">For example, a `Public` class cannot inherit a `Friend` or a `Private` class, and a `Friend` class cannot inherit a `Private` class.</span></span>  
  
## <a name="inheritance-modifiers"></a><span data-ttu-id="cf03d-112">継承修飾子</span><span class="sxs-lookup"><span data-stu-id="cf03d-112">Inheritance Modifiers</span></span>  
 <span data-ttu-id="cf03d-113">Visual Basic では、次のクラス レベルのステートメントと継承をサポートする修飾子が導入されています。</span><span class="sxs-lookup"><span data-stu-id="cf03d-113">Visual Basic introduces the following class-level statements and modifiers to support inheritance:</span></span>  
  
- <span data-ttu-id="cf03d-114">`Inherits` ステートメント: 基本クラスを指定します。</span><span class="sxs-lookup"><span data-stu-id="cf03d-114">`Inherits` statement — Specifies the base class.</span></span>  
  
- <span data-ttu-id="cf03d-115">`NotInheritable` 修飾子: プログラマがクラスの基底クラスとして使用するを防ぎます。</span><span class="sxs-lookup"><span data-stu-id="cf03d-115">`NotInheritable` modifier — Prevents programmers from using the class as a base class.</span></span>  
  
- <span data-ttu-id="cf03d-116">`MustInherit` 修飾子: のみ、基本クラスとして使用するため、クラスは意図するを指定します。</span><span class="sxs-lookup"><span data-stu-id="cf03d-116">`MustInherit` modifier — Specifies that the class is intended for use as a base class only.</span></span> <span data-ttu-id="cf03d-117">インスタンス`MustInherit`クラスを直接作成することはできません。 できますのみ作成する必要が派生クラスの基本クラスのインスタンス。</span><span class="sxs-lookup"><span data-stu-id="cf03d-117">Instances of `MustInherit` classes cannot be created directly; they can only be created as base class instances of a derived class.</span></span> <span data-ttu-id="cf03d-118">(C++ などの他のプログラミング言語とC#、という用語を使用して、*抽象クラス*にこのようなクラスについて説明します)。</span><span class="sxs-lookup"><span data-stu-id="cf03d-118">(Other programming languages, such as C++ and C#, use the term *abstract class* to describe such a class.)</span></span>  
  
## <a name="overriding-properties-and-methods-in-derived-classes"></a><span data-ttu-id="cf03d-119">派生クラスでプロパティとメソッドをオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="cf03d-119">Overriding Properties and Methods in Derived Classes</span></span>  
 <span data-ttu-id="cf03d-120">既定では、派生クラスは、その基本クラスからプロパティとメソッドを継承します。</span><span class="sxs-lookup"><span data-stu-id="cf03d-120">By default, a derived class inherits properties and methods from its base class.</span></span> <span data-ttu-id="cf03d-121">できる場合は、継承されたプロパティまたはメソッドが派生クラスで異なった動作、*オーバーライド*します。</span><span class="sxs-lookup"><span data-stu-id="cf03d-121">If an inherited property or method has to behave differently in the derived class it can be *overridden*.</span></span> <span data-ttu-id="cf03d-122">つまり、派生クラスでメソッドの新しい実装を定義できます。</span><span class="sxs-lookup"><span data-stu-id="cf03d-122">That is, you can define a new implementation of the method in the derived class.</span></span> <span data-ttu-id="cf03d-123">プロパティやメソッドのオーバーライド方法を制御するには、次の修飾子を使用します。</span><span class="sxs-lookup"><span data-stu-id="cf03d-123">The following modifiers are used to control how properties and methods are overridden:</span></span>  
  
- <span data-ttu-id="cf03d-124">`Overridable` 派生クラスでオーバーライドするクラスでプロパティまたはメソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="cf03d-124">`Overridable` — Allows a property or method in a class to be overridden in a derived class.</span></span>  
  
- <span data-ttu-id="cf03d-125">`Overrides` -よりも優先、`Overridable`プロパティまたはメソッドの基本クラスで定義します。</span><span class="sxs-lookup"><span data-stu-id="cf03d-125">`Overrides` — Overrides an `Overridable` property or method defined in the base class.</span></span>  
  
- <span data-ttu-id="cf03d-126">`NotOverridable` — から継承するクラスでオーバーライドされるプロパティまたはメソッドを防止します。</span><span class="sxs-lookup"><span data-stu-id="cf03d-126">`NotOverridable` — Prevents a property or method from being overridden in an inheriting class.</span></span> <span data-ttu-id="cf03d-127">既定では、`Public`メソッドは`NotOverridable`します。</span><span class="sxs-lookup"><span data-stu-id="cf03d-127">By default, `Public` methods are `NotOverridable`.</span></span>  
  
- <span data-ttu-id="cf03d-128">`MustOverride` 派生クラスでプロパティまたはメソッドをオーバーライドする必要があります。</span><span class="sxs-lookup"><span data-stu-id="cf03d-128">`MustOverride` — Requires that a derived class override the property or method.</span></span> <span data-ttu-id="cf03d-129">ときに、`MustOverride`キーワードを使用して、メソッド定義から成る、 `Sub`、 `Function`、または`Property`ステートメント。</span><span class="sxs-lookup"><span data-stu-id="cf03d-129">When the `MustOverride` keyword is used, the method definition consists of just the `Sub`, `Function`, or `Property` statement.</span></span> <span data-ttu-id="cf03d-130">その他のステートメントは許可されずとは具体的にはない`End Sub`または`End Function`ステートメント。</span><span class="sxs-lookup"><span data-stu-id="cf03d-130">No other statements are allowed, and specifically there is no `End Sub` or `End Function` statement.</span></span> <span data-ttu-id="cf03d-131">`MustOverride` メソッドを宣言する必要があります`MustInherit`クラス。</span><span class="sxs-lookup"><span data-stu-id="cf03d-131">`MustOverride` methods must be declared in `MustInherit` classes.</span></span>  
  
 <span data-ttu-id="cf03d-132">給与支払いを処理するクラスを定義するとします。</span><span class="sxs-lookup"><span data-stu-id="cf03d-132">Suppose you want to define classes to handle payroll.</span></span> <span data-ttu-id="cf03d-133">ジェネリック型を定義することが`Payroll`クラスを含む、`RunPayroll`典型的な 1 週間の給与を計算するメソッド。</span><span class="sxs-lookup"><span data-stu-id="cf03d-133">You could define a generic `Payroll` class that contains a `RunPayroll` method that calculates payroll for a typical week.</span></span> <span data-ttu-id="cf03d-134">使用して`Payroll`のより特化された基底クラスとして`BonusPayroll`クラスは、従業員のボーナスを配布するときにされる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="cf03d-134">You could then use `Payroll` as a base class for a more specialized `BonusPayroll` class, which could be used when distributing employee bonuses.</span></span>  
  
 <span data-ttu-id="cf03d-135">`BonusPayroll`クラスが継承、および、上書き、`PayEmployee`ベースで定義されたメソッド`Payroll`クラス。</span><span class="sxs-lookup"><span data-stu-id="cf03d-135">The `BonusPayroll` class can inherit, and override, the `PayEmployee` method defined in the base `Payroll` class.</span></span>  
  
 <span data-ttu-id="cf03d-136">次の例は、基底クラスを定義`Payroll,`と派生クラスでは、 `BonusPayroll`、継承されたメソッドをオーバーライドする`PayEmployee`します。</span><span class="sxs-lookup"><span data-stu-id="cf03d-136">The following example defines a base class, `Payroll,` and a derived class, `BonusPayroll`, which overrides an inherited method, `PayEmployee`.</span></span> <span data-ttu-id="cf03d-137">プロシージャ、`RunPayroll`を作成し、渡します、`Payroll`オブジェクトと`BonusPayroll`関数にオブジェクト`Pay`、実行する、`PayEmployee`両方のオブジェクトのメソッド。</span><span class="sxs-lookup"><span data-stu-id="cf03d-137">A procedure, `RunPayroll`, creates and then passes a `Payroll` object and a `BonusPayroll` object to a function, `Pay`, that executes the `PayEmployee` method of both objects.</span></span>  
  
 [!code-vb[VbVbalrOOP#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#28)]  
  
## <a name="the-mybase-keyword"></a><span data-ttu-id="cf03d-138">MyBase キーワード</span><span class="sxs-lookup"><span data-stu-id="cf03d-138">The MyBase Keyword</span></span>  
 <span data-ttu-id="cf03d-139">`MyBase`キーワードはクラスの現在のインスタンスの基底クラスを参照するオブジェクト変数のように動作します。</span><span class="sxs-lookup"><span data-stu-id="cf03d-139">The `MyBase` keyword behaves like an object variable that refers to the base class of the current instance of a class.</span></span> <span data-ttu-id="cf03d-140">`MyBase` オーバーライドまたは派生クラスでシャドウされている基本クラスのメンバーへのアクセスによく使用されます。</span><span class="sxs-lookup"><span data-stu-id="cf03d-140">`MyBase` is frequently used to access base class members that are overridden or shadowed in a derived class.</span></span> <span data-ttu-id="cf03d-141">具体的には、`MyBase.New`派生クラスのコンス トラクターから基本クラスのコンス トラクターを明示的に呼び出しに使用されます。</span><span class="sxs-lookup"><span data-stu-id="cf03d-141">In particular, `MyBase.New` is used to explicitly call a base class constructor from a derived class constructor.</span></span>  
  
 <span data-ttu-id="cf03d-142">たとえば、基本クラスから継承されたメソッドをオーバーライドする派生クラスを設計するとします。</span><span class="sxs-lookup"><span data-stu-id="cf03d-142">For example, suppose you are designing a derived class that overrides a method inherited from the base class.</span></span> <span data-ttu-id="cf03d-143">オーバーライドされたメソッドは、基本クラスのメソッドを呼び出すし、次のコード フラグメントで示すように、戻り値を変更します。</span><span class="sxs-lookup"><span data-stu-id="cf03d-143">The overridden method can call the method in the base class and modify the return value as shown in the following code fragment:</span></span>  
  
 [!code-vb[VbVbalrOOP#109](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#109)]  
  
 <span data-ttu-id="cf03d-144">次の一覧の使用に関する制限事項を示します`MyBase`:</span><span class="sxs-lookup"><span data-stu-id="cf03d-144">The following list describes restrictions on using `MyBase`:</span></span>  
  
- <span data-ttu-id="cf03d-145">`MyBase` 直接の基本クラスとその継承されたメンバーを参照します。</span><span class="sxs-lookup"><span data-stu-id="cf03d-145">`MyBase` refers to the immediate base class and its inherited members.</span></span> <span data-ttu-id="cf03d-146">使用することはできませんにアクセスする`Private`クラスのメンバー。</span><span class="sxs-lookup"><span data-stu-id="cf03d-146">It cannot be used to access `Private` members in the class.</span></span>  
  
- <span data-ttu-id="cf03d-147">`MyBase` キーワード、実際のオブジェクトではありません。</span><span class="sxs-lookup"><span data-stu-id="cf03d-147">`MyBase` is a keyword, not a real object.</span></span> <span data-ttu-id="cf03d-148">`MyBase` 変数に割り当てられている、プロシージャに渡されるまたはで使用されることはできません、`Is`比較します。</span><span class="sxs-lookup"><span data-stu-id="cf03d-148">`MyBase` cannot be assigned to a variable, passed to procedures, or used in an `Is` comparison.</span></span>  
  
- <span data-ttu-id="cf03d-149">メソッドを`MyBase`を修飾すると、直接の基本クラスで定義する必要はありませんが間接的に継承された基本クラスで定義することがあります。</span><span class="sxs-lookup"><span data-stu-id="cf03d-149">The method that `MyBase` qualifies does not have to be defined in the immediate base class; it may instead be defined in an indirectly inherited base class.</span></span> <span data-ttu-id="cf03d-150">修飾された参照の順序で`MyBase`を正しくコンパイルするいくつかの基本クラスは、呼び出しに表示されるパラメーターの型と名前に一致するメソッドを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="cf03d-150">In order for a reference qualified by `MyBase` to compile correctly, some base class must contain a method matching the name and types of parameters that appear in the call.</span></span>  
  
- <span data-ttu-id="cf03d-151">使用することはできません`MyBase`を呼び出す`MustOverride`基底クラス メソッド。</span><span class="sxs-lookup"><span data-stu-id="cf03d-151">You cannot use `MyBase` to call `MustOverride` base class methods.</span></span>  
  
- <span data-ttu-id="cf03d-152">`MyBase` 自体を修飾するためには使用できません。</span><span class="sxs-lookup"><span data-stu-id="cf03d-152">`MyBase` cannot be used to qualify itself.</span></span> <span data-ttu-id="cf03d-153">そのため、次のコードが無効です。</span><span class="sxs-lookup"><span data-stu-id="cf03d-153">Therefore, the following code is not valid:</span></span>  
  
     `MyBase.MyBase.BtnOK_Click()`  
  
- <span data-ttu-id="cf03d-154">`MyBase` モジュールでは使用できません。</span><span class="sxs-lookup"><span data-stu-id="cf03d-154">`MyBase` cannot be used in modules.</span></span>  
  
- <span data-ttu-id="cf03d-155">`MyBase` としてマークされている基本クラスのメンバーのアクセスに使用することはできません`Friend`基底クラスが別のアセンブリの場合。</span><span class="sxs-lookup"><span data-stu-id="cf03d-155">`MyBase` cannot be used to access base class members that are marked as `Friend` if the base class is in a different assembly.</span></span>  
  
 <span data-ttu-id="cf03d-156">別の例と詳細については、次を参照してください。[方法。変数にアクセスする派生クラスによって非表示に](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md)します。</span><span class="sxs-lookup"><span data-stu-id="cf03d-156">For more information and another example, see [How to: Access a Variable Hidden by a Derived Class](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md).</span></span>  
  
## <a name="the-myclass-keyword"></a><span data-ttu-id="cf03d-157">MyClass キーワード</span><span class="sxs-lookup"><span data-stu-id="cf03d-157">The MyClass Keyword</span></span>  
 <span data-ttu-id="cf03d-158">`MyClass`キーワードが最初に実装されているクラスの現在のインスタンスを参照するオブジェクト変数のように動作します。</span><span class="sxs-lookup"><span data-stu-id="cf03d-158">The `MyClass` keyword behaves like an object variable that refers to the current instance of a class as originally implemented.</span></span> <span data-ttu-id="cf03d-159">`MyClass` よう`Me`ですべてのメソッドとプロパティを呼び出すが、`MyClass`メソッドまたはプロパティとして扱われます[NotOverridable](../../../../visual-basic/language-reference/modifiers/notoverridable.md)します。</span><span class="sxs-lookup"><span data-stu-id="cf03d-159">`MyClass` resembles `Me`, but every method and property call on `MyClass` is treated as if the method or property were [NotOverridable](../../../../visual-basic/language-reference/modifiers/notoverridable.md).</span></span> <span data-ttu-id="cf03d-160">そのため、メソッドまたはプロパティは、派生クラスでオーバーライドすることでは影響ありません。</span><span class="sxs-lookup"><span data-stu-id="cf03d-160">Therefore, the method or property is not affected by overriding in a derived class.</span></span>  
  
- <span data-ttu-id="cf03d-161">`MyClass` キーワード、実際のオブジェクトではありません。</span><span class="sxs-lookup"><span data-stu-id="cf03d-161">`MyClass` is a keyword, not a real object.</span></span> <span data-ttu-id="cf03d-162">`MyClass` 変数に割り当てられている、プロシージャに渡されるまたはで使用されることはできません、`Is`比較します。</span><span class="sxs-lookup"><span data-stu-id="cf03d-162">`MyClass` cannot be assigned to a variable, passed to procedures, or used in an `Is` comparison.</span></span>  
  
- <span data-ttu-id="cf03d-163">`MyClass` 外側のクラスとその継承されたメンバーを参照します。</span><span class="sxs-lookup"><span data-stu-id="cf03d-163">`MyClass` refers to the containing class and its inherited members.</span></span>  
  
- <span data-ttu-id="cf03d-164">`MyClass` 修飾子として使用できる`Shared`メンバー。</span><span class="sxs-lookup"><span data-stu-id="cf03d-164">`MyClass` can be used as a qualifier for `Shared` members.</span></span>  
  
- <span data-ttu-id="cf03d-165">`MyClass` 内で使用することはできません、`Shared`メソッドがクラスの共有メンバーにアクセスするインスタンス メソッド内で使用できます。</span><span class="sxs-lookup"><span data-stu-id="cf03d-165">`MyClass` cannot be used inside a `Shared` method, but can be used inside an instance method to access a shared member of a class.</span></span>  
  
- <span data-ttu-id="cf03d-166">`MyClass` 標準的なモジュールでは使用できません。</span><span class="sxs-lookup"><span data-stu-id="cf03d-166">`MyClass` cannot be used in standard modules.</span></span>  
  
- <span data-ttu-id="cf03d-167">`MyClass` 基底クラスで定義されていると、そのクラスで提供されるメソッドの実装を持たないメソッドを修飾するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="cf03d-167">`MyClass` can be used to qualify a method that is defined in a base class and that has no implementation of the method provided in that class.</span></span> <span data-ttu-id="cf03d-168">このような参照と同じ意味を持つ`MyBase.`*メソッド*します。</span><span class="sxs-lookup"><span data-stu-id="cf03d-168">Such a reference has the same meaning as `MyBase.`*Method*.</span></span>  
  
 <span data-ttu-id="cf03d-169">次の例では、比較`Me`と`MyClass`します。</span><span class="sxs-lookup"><span data-stu-id="cf03d-169">The following example compares `Me` and `MyClass`.</span></span>  
  
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
  
 <span data-ttu-id="cf03d-170">場合でも`derivedClass`オーバーライド`testMethod`、`MyClass`キーワード`useMyClass`の基底クラスのバージョンへの呼び出しをオーバーライドして、コンパイラと解決の効果を null `testMethod`。</span><span class="sxs-lookup"><span data-stu-id="cf03d-170">Even though `derivedClass` overrides `testMethod`, the `MyClass` keyword in `useMyClass` nullifies the effects of overriding, and the compiler resolves the call to the base class version of `testMethod`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf03d-171">関連項目</span><span class="sxs-lookup"><span data-stu-id="cf03d-171">See also</span></span>

- [<span data-ttu-id="cf03d-172">Inherits ステートメント</span><span class="sxs-lookup"><span data-stu-id="cf03d-172">Inherits Statement</span></span>](../../../../visual-basic/language-reference/statements/inherits-statement.md)
- [<span data-ttu-id="cf03d-173">Me、My、MyBase、および MyClass</span><span class="sxs-lookup"><span data-stu-id="cf03d-173">Me, My, MyBase, and MyClass</span></span>](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
