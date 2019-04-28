---
title: Visual Basic におけるシャドウ
ms.date: 07/20/2015
helpviewer_keywords:
- inheritance [Visual Basic], shadowing
- overriding, and shadowing
- shadowing
- duplicate names [Visual Basic]
- shadowing, by inheritance
- declared elements [Visual Basic], referencing
- shadowing, by scope
- declared elements [Visual Basic], hiding
- naming conflicts, shadowing
- declared elements [Visual Basic], shadowing
- shadowing, and overriding
- scope [Visual Basic], shadowing
- Shadows keyword [Visual Basic], about
- objects [Visual Basic], names
- names [Visual Basic], shadowing
ms.assetid: 54bb4c25-12c4-4181-b4a0-93546053964e
ms.openlocfilehash: 9ad992a53618fa2f410e0b0fb23886c30136384f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61917908"
---
# <a name="shadowing-in-visual-basic"></a><span data-ttu-id="fcbb5-102">Visual Basic におけるシャドウ</span><span class="sxs-lookup"><span data-stu-id="fcbb5-102">Shadowing in Visual Basic</span></span>
<span data-ttu-id="fcbb5-103">2 つのプログラミング要素は、同じ名前を共有、うち 1 つが非表示できる、または*シャドウ*、もう 1 つ。</span><span class="sxs-lookup"><span data-stu-id="fcbb5-103">When two programming elements share the same name, one of them can hide, or *shadow*, the other one.</span></span> <span data-ttu-id="fcbb5-104">このような場合は、シャドウされた要素は参照できません。代わりに、コードでは、要素名を使用する場合、Visual Basic コンパイラに解決されますがシャドウする要素。</span><span class="sxs-lookup"><span data-stu-id="fcbb5-104">In such a situation, the shadowed element is not available for reference; instead, when your code uses the element name, the Visual Basic compiler resolves it to the shadowing element.</span></span>  
  
## <a name="purpose"></a><span data-ttu-id="fcbb5-105">目的</span><span class="sxs-lookup"><span data-stu-id="fcbb5-105">Purpose</span></span>  
 <span data-ttu-id="fcbb5-106">シャドウの主な目的、クラスのメンバーの定義を保護することです。</span><span class="sxs-lookup"><span data-stu-id="fcbb5-106">The main purpose of shadowing is to protect the definition of your class members.</span></span> <span data-ttu-id="fcbb5-107">基底クラスには、既に定義されている 1 つとして同じ名前の要素を作成する変更を行うこともできます。</span><span class="sxs-lookup"><span data-stu-id="fcbb5-107">The base class might undergo a change that creates an element with the same name as one you have already defined.</span></span> <span data-ttu-id="fcbb5-108">このような場合、`Shadows`するメンバーに解決するのには、クラスを通じて参照修飾子強制的に基本クラスの新しい要素の代わりに定義されました。</span><span class="sxs-lookup"><span data-stu-id="fcbb5-108">If this happens, the `Shadows` modifier forces references through your class to be resolved to the member you defined, instead of to the new base class element.</span></span>  
  
## <a name="types-of-shadowing"></a><span data-ttu-id="fcbb5-109">シャドウの種類</span><span class="sxs-lookup"><span data-stu-id="fcbb5-109">Types of Shadowing</span></span>  
 <span data-ttu-id="fcbb5-110">要素は、2 つの方法で別の要素をシャドウすることができます。</span><span class="sxs-lookup"><span data-stu-id="fcbb5-110">An element can shadow another element in two different ways.</span></span> <span data-ttu-id="fcbb5-111">要素はシャドウ ケースが実現されます、シャドウされた要素を含んでいるリージョンのサブ領域内で宣言できます*スコープによる*します。</span><span class="sxs-lookup"><span data-stu-id="fcbb5-111">The shadowing element can be declared inside a subregion of the region containing the shadowed element, in which case the shadowing is accomplished *through scope*.</span></span> <span data-ttu-id="fcbb5-112">派生クラスは、シャドウ ケースは、基底クラスのメンバーを再定義できますまたは*継承によって*します。</span><span class="sxs-lookup"><span data-stu-id="fcbb5-112">Or a deriving class can redefine a member of a base class, in which case the shadowing is done *through inheritance*.</span></span>  
  
### <a name="shadowing-through-scope"></a><span data-ttu-id="fcbb5-113">スコープによるシャドウ</span><span class="sxs-lookup"><span data-stu-id="fcbb5-113">Shadowing Through Scope</span></span>  
 <span data-ttu-id="fcbb5-114">プログラミング要素は、モジュール、クラスまたは構造体が同じ名前でスコープが異なることができます。</span><span class="sxs-lookup"><span data-stu-id="fcbb5-114">It is possible for programming elements in the same module, class, or structure to have the same name but different scope.</span></span> <span data-ttu-id="fcbb5-115">狭いスコープを持つ要素が他の要素をシャドウするこの方法で 2 つの要素が宣言されているし、コードが共有されている名前を指す、(ブロック スコープでは、最も狭い)。</span><span class="sxs-lookup"><span data-stu-id="fcbb5-115">When two elements are declared in this manner and the code refers to the name they share, the element with the narrower scope shadows the other element (block scope is the narrowest).</span></span>  
  
 <span data-ttu-id="fcbb5-116">たとえば、モジュールを定義できますを`Public`という名前の変数`temp`、モジュール内のプロシージャもという名前のローカル変数を宣言および`temp`。</span><span class="sxs-lookup"><span data-stu-id="fcbb5-116">For example, a module can define a `Public` variable named `temp`, and a procedure within the module can declare a local variable also named `temp`.</span></span> <span data-ttu-id="fcbb5-117">参照`temp`プロシージャ内からへの参照中に、ローカル変数にアクセス`temp`から外部プロシージャへのアクセス、`Public`変数。</span><span class="sxs-lookup"><span data-stu-id="fcbb5-117">References to `temp` from within the procedure access the local variable, while references to `temp` from outside the procedure access the `Public` variable.</span></span> <span data-ttu-id="fcbb5-118">この場合、プロシージャの変数`temp`モジュール変数のシャドウ`temp`します。</span><span class="sxs-lookup"><span data-stu-id="fcbb5-118">In this case, the procedure variable `temp` shadows the module variable `temp`.</span></span>  
  
 <span data-ttu-id="fcbb5-119">次の図は、2 つの変数、という名前の両方に`temp`します。</span><span class="sxs-lookup"><span data-stu-id="fcbb5-119">The following illustration shows two variables, both named `temp`.</span></span> <span data-ttu-id="fcbb5-120">ローカル変数`temp`メンバー変数のシャドウ`temp`独自のプロシージャ内からアクセスするときに`p`します。</span><span class="sxs-lookup"><span data-stu-id="fcbb5-120">The local variable `temp` shadows the member variable `temp` when accessed from within its own procedure `p`.</span></span> <span data-ttu-id="fcbb5-121">ただし、`MyClass`キーワードは、シャドウをバイパスし、メンバー変数にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="fcbb5-121">However, the `MyClass` keyword bypasses the shadowing and accesses the member variable.</span></span>  
  
 ![スコープによるシャドウを示しています。 グラフィック。](./media/shadowing/shadow-scope-diagram.gif)
  
 <span data-ttu-id="fcbb5-123">スコープによるシャドウの例は、次を参照してください。[方法。変数と同じ名前の変数を隠す](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md)します。</span><span class="sxs-lookup"><span data-stu-id="fcbb5-123">For an example of shadowing through scope, see [How to: Hide a Variable with the Same Name as Your Variable](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md).</span></span>  
  
### <a name="shadowing-through-inheritance"></a><span data-ttu-id="fcbb5-124">継承によるシャドウ</span><span class="sxs-lookup"><span data-stu-id="fcbb5-124">Shadowing Through Inheritance</span></span>  
 <span data-ttu-id="fcbb5-125">派生クラスでは、基本クラスから継承されたプログラミング要素を再定義を再定義する要素は、元の要素をシャドウします。</span><span class="sxs-lookup"><span data-stu-id="fcbb5-125">If a derived class redefines a programming element inherited from a base class, the redefining element shadows the original element.</span></span> <span data-ttu-id="fcbb5-126">その他の種類では、任意の種類の宣言された要素は、または一連のオーバー ロードされた要素をシャドウできます。</span><span class="sxs-lookup"><span data-stu-id="fcbb5-126">You can shadow any type of declared element, or set of overloaded elements, with any other type.</span></span> <span data-ttu-id="fcbb5-127">たとえば、`Integer`シャドウする変数を`Function`プロシージャ。</span><span class="sxs-lookup"><span data-stu-id="fcbb5-127">For example, an `Integer` variable can shadow a `Function` procedure.</span></span> <span data-ttu-id="fcbb5-128">別のプロシージャでプロシージャをシャドウする場合は、別のパラメーター リストと異なる戻り値の型を使用できます。</span><span class="sxs-lookup"><span data-stu-id="fcbb5-128">If you shadow a procedure with another procedure, you can use a different parameter list and a different return type.</span></span>  
  
 <span data-ttu-id="fcbb5-129">次の図は、基本クラス`b`と派生クラス`d`から継承する`b`します。</span><span class="sxs-lookup"><span data-stu-id="fcbb5-129">The following illustration shows a base class `b` and a derived class `d` that inherits from `b`.</span></span> <span data-ttu-id="fcbb5-130">基本クラスという名前のプロシージャを定義する`proc`と派生クラスは、同じ名前の別のプロシージャでシャドウします。</span><span class="sxs-lookup"><span data-stu-id="fcbb5-130">The base class defines a procedure named `proc`, and the derived class shadows it with another procedure of the same name.</span></span> <span data-ttu-id="fcbb5-131">最初の`Call`シャドウ ステートメントにアクセスする`proc`派生クラスでします。</span><span class="sxs-lookup"><span data-stu-id="fcbb5-131">The first `Call` statement accesses the shadowing `proc` in the derived class.</span></span> <span data-ttu-id="fcbb5-132">ただし、`MyBase`キーワードは、シャドウをバイパスし、基本クラスのシャドウされたプロシージャにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="fcbb5-132">However, the `MyBase` keyword bypasses the shadowing and accesses the shadowed procedure in the base class.</span></span>  
  
 ![継承によるシャドウのグラフィック ダイアグラム](./media/shadowing/shadowing-inherit-diagram.gif)  
  
 <span data-ttu-id="fcbb5-134">継承によるシャドウの例は、次を参照してください。[方法。変数と同じ名前の変数を隠す](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md)と[方法。継承された変数を非表示に](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-an-inherited-variable.md)します。</span><span class="sxs-lookup"><span data-stu-id="fcbb5-134">For an example of shadowing through inheritance, see [How to: Hide a Variable with the Same Name as Your Variable](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md) and [How to: Hide an Inherited Variable](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-an-inherited-variable.md).</span></span>  
  
#### <a name="shadowing-and-access-level"></a><span data-ttu-id="fcbb5-135">シャドウとアクセス レベル</span><span class="sxs-lookup"><span data-stu-id="fcbb5-135">Shadowing and Access Level</span></span>  
 <span data-ttu-id="fcbb5-136">シャドウの要素は常に、派生クラスを使用してコードからアクセス可能ではありません。</span><span class="sxs-lookup"><span data-stu-id="fcbb5-136">The shadowing element is not always accessible from the code using the derived class.</span></span> <span data-ttu-id="fcbb5-137">たとえば、宣言することがあります`Private`します。</span><span class="sxs-lookup"><span data-stu-id="fcbb5-137">For example, it might be declared `Private`.</span></span> <span data-ttu-id="fcbb5-138">このような場合は、シャドウ敗北は、コンパイラが同じ要素への参照を解決する場合がありますは行われません。</span><span class="sxs-lookup"><span data-stu-id="fcbb5-138">In such a case, shadowing is defeated and the compiler resolves any reference to the same element it would have if there had been no shadowing.</span></span> <span data-ttu-id="fcbb5-139">この要素は、最小の継承はステップ後方シャドウするクラスからアクセス可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="fcbb5-139">This element is the accessible element the fewest derivational steps backward from the shadowing class.</span></span> <span data-ttu-id="fcbb5-140">シャドウされた要素が、プロシージャの場合は、解像度は同じ名前のパラメーターの一覧で最も近い利用可能なバージョンを型を返します。</span><span class="sxs-lookup"><span data-stu-id="fcbb5-140">If the shadowed element is a procedure, the resolution is to the closest accessible version with the same name, parameter list, and return type.</span></span>  
  
 <span data-ttu-id="fcbb5-141">次の例では、3 つのクラスの継承階層を示します。</span><span class="sxs-lookup"><span data-stu-id="fcbb5-141">The following example shows an inheritance hierarchy of three classes.</span></span> <span data-ttu-id="fcbb5-142">各クラスを定義、`Sub`プロシージャ`display`、し、各派生クラスの影、`display`基底クラスのプロシージャです。</span><span class="sxs-lookup"><span data-stu-id="fcbb5-142">Each class defines a `Sub` procedure `display`, and each derived class shadows the `display` procedure in its base class.</span></span>  
  
```  
Public Class firstClass  
    Public Sub display()  
        MsgBox("This is firstClass")  
    End Sub  
End Class  
Public Class secondClass  
    Inherits firstClass  
    Private Shadows Sub display()  
        MsgBox("This is secondClass")  
    End Sub  
End Class  
Public Class thirdClass  
    Inherits secondClass  
    Public Shadows Sub display()  
        MsgBox("This is thirdClass")  
    End Sub  
End Class  
Module callDisplay  
    Dim first As New firstClass  
    Dim second As New secondClass  
    Dim third As New thirdClass  
    Public Sub callDisplayProcedures()  
        ' The following statement displays "This is firstClass".  
        first.display()  
        ' The following statement displays "This is firstClass".  
        second.display()  
        ' The following statement displays "This is thirdClass".  
        third.display()  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="fcbb5-143">前の例では、派生クラスで`secondClass`shadows`display`で、`Private`プロシージャ。</span><span class="sxs-lookup"><span data-stu-id="fcbb5-143">In the preceding example, the derived class `secondClass` shadows `display` with a `Private` procedure.</span></span> <span data-ttu-id="fcbb5-144">ときにモジュール`callDisplay`呼び出し`display`で`secondClass`、呼び出し元のコードが範囲外です`secondClass`ため秘密にアクセスできない`display`プロシージャ。</span><span class="sxs-lookup"><span data-stu-id="fcbb5-144">When module `callDisplay` calls `display` in `secondClass`, the calling code is outside `secondClass` and therefore cannot access the private `display` procedure.</span></span> <span data-ttu-id="fcbb5-145">シャドウは行われず、およびコンパイラが基底クラスへの参照を解決`display`プロシージャ。</span><span class="sxs-lookup"><span data-stu-id="fcbb5-145">Shadowing is defeated, and the compiler resolves the reference to the base class `display` procedure.</span></span>  
  
 <span data-ttu-id="fcbb5-146">ただし、さらに、派生クラス`thirdClass`宣言`display`として`Public`ため、コードでは、`callDisplay`アクセスできます。</span><span class="sxs-lookup"><span data-stu-id="fcbb5-146">However, the further derived class `thirdClass` declares `display` as `Public`, so the code in `callDisplay` can access it.</span></span>  
  
## <a name="shadowing-and-overriding"></a><span data-ttu-id="fcbb5-147">シャドウとオーバーライド</span><span class="sxs-lookup"><span data-stu-id="fcbb5-147">Shadowing and Overriding</span></span>  
 <span data-ttu-id="fcbb5-148">シャドウとオーバーライドを混同しないでください。</span><span class="sxs-lookup"><span data-stu-id="fcbb5-148">Do not confuse shadowing with overriding.</span></span> <span data-ttu-id="fcbb5-149">どちらも、派生クラスは基底クラスから継承し、1 つの宣言された要素と他の再定義に使用されます。</span><span class="sxs-lookup"><span data-stu-id="fcbb5-149">Both are used when a derived class inherits from a base class, and both redefine one declared element with another.</span></span> <span data-ttu-id="fcbb5-150">2 つの重要な違いがあります。</span><span class="sxs-lookup"><span data-stu-id="fcbb5-150">But there are significant differences between the two.</span></span> <span data-ttu-id="fcbb5-151">比較については、次を参照してください。[の相違点の間でシャドウとオーバーライド](../../../../visual-basic/programming-guide/language-features/declared-elements/differences-between-shadowing-and-overriding.md)します。</span><span class="sxs-lookup"><span data-stu-id="fcbb5-151">For a comparison, see [Differences Between Shadowing and Overriding](../../../../visual-basic/programming-guide/language-features/declared-elements/differences-between-shadowing-and-overriding.md).</span></span>  
  
## <a name="shadowing-and-overloading"></a><span data-ttu-id="fcbb5-152">シャドウとオーバー ロード</span><span class="sxs-lookup"><span data-stu-id="fcbb5-152">Shadowing and Overloading</span></span>  
 <span data-ttu-id="fcbb5-153">派生クラスで 1 つ以上の要素と同じ基本クラスの要素をシャドウする場合は、その要素のオーバー ロードされたバージョンがシャドウする要素になります。</span><span class="sxs-lookup"><span data-stu-id="fcbb5-153">If you shadow the same base class element with more than one element in your derived class, the shadowing elements become overloaded versions of that element.</span></span> <span data-ttu-id="fcbb5-154">詳細については、「 [Procedure Overloading](../../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fcbb5-154">For more information, see [Procedure Overloading](../../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md).</span></span>  
  
## <a name="accessing-a-shadowed-element"></a><span data-ttu-id="fcbb5-155">シャドウされた要素へのアクセス</span><span class="sxs-lookup"><span data-stu-id="fcbb5-155">Accessing a Shadowed Element</span></span>  
 <span data-ttu-id="fcbb5-156">派生クラスから、要素にアクセスするときに通常の方法、派生クラスの現在のインスタンスを通じて、要素名で修飾して、`Me`キーワード。</span><span class="sxs-lookup"><span data-stu-id="fcbb5-156">When you access an element from a derived class, you normally do so through the current instance of that derived class, by qualifying the element name with the `Me` keyword.</span></span> <span data-ttu-id="fcbb5-157">修飾基本クラスの要素をアクセスするには、派生クラスが基底クラス内の要素をシャドウする場合、`MyBase`キーワード。</span><span class="sxs-lookup"><span data-stu-id="fcbb5-157">If your derived class shadows the element in the base class, you can access the base class element by qualifying it with the `MyBase` keyword.</span></span>  
  
 <span data-ttu-id="fcbb5-158">シャドウされた要素へのアクセスの例は、次を参照してください。[方法。変数にアクセスする派生クラスによって非表示に](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md)します。</span><span class="sxs-lookup"><span data-stu-id="fcbb5-158">For an example of accessing a shadowed element, see [How to: Access a Variable Hidden by a Derived Class](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md).</span></span>  
  
### <a name="declaration-of-the-object-variable"></a><span data-ttu-id="fcbb5-159">オブジェクト変数の宣言</span><span class="sxs-lookup"><span data-stu-id="fcbb5-159">Declaration of the Object Variable</span></span>  
 <span data-ttu-id="fcbb5-160">オブジェクト変数を作成する方法は、派生クラスは、シャドウ要素またはシャドウされた要素にアクセスするかどうかも影響します。</span><span class="sxs-lookup"><span data-stu-id="fcbb5-160">How you create the object variable can also affect whether the derived class accesses a shadowing element or the shadowed element.</span></span> <span data-ttu-id="fcbb5-161">次の例では、派生クラスでは、2 つのオブジェクトを作成しますが、として基本クラスと派生クラスとしてもう 1 つのオブジェクトが宣言されています。</span><span class="sxs-lookup"><span data-stu-id="fcbb5-161">The following example creates two objects from a derived class, but one object is declared as the base class and the other as the derived class.</span></span>  
  
```  
Public Class baseCls  
    ' The following statement declares the element that is to be shadowed.  
    Public z As Integer = 100  
End Class  
Public Class dervCls  
    Inherits baseCls  
    ' The following statement declares the shadowing element.  
    Public Shadows z As String = "*"  
End Class  
Public Class useClasses  
    ' The following statement creates the object declared as the base class.  
    Dim basObj As baseCls = New dervCls()  
    ' Note that dervCls widens to its base class baseCls.  
    ' The following statement creates the object declared as the derived class.  
    Dim derObj As dervCls = New dervCls()  
    Public Sub showZ()   
    ' The following statement outputs 100 (the shadowed element).  
        MsgBox("Accessed through base class: " & basObj.z)  
    ' The following statement outputs "*" (the shadowing element).  
        MsgBox("Accessed through derived class: " & derObj.z)  
    End Sub  
End Class  
```  
  
 <span data-ttu-id="fcbb5-162">前の例では、変数`basObj`基底クラスとして宣言されます。</span><span class="sxs-lookup"><span data-stu-id="fcbb5-162">In the preceding example, the variable `basObj` is declared as the base class.</span></span> <span data-ttu-id="fcbb5-163">割り当てを`dervCls`オブジェクトをそれには、拡大変換であるためです。</span><span class="sxs-lookup"><span data-stu-id="fcbb5-163">Assigning a `dervCls` object to it constitutes a widening conversion and is therefore valid.</span></span> <span data-ttu-id="fcbb5-164">基底クラスが、変数のシャドウのバージョンにアクセスできませんただし、 `z` 、派生クラスでは、そのため、コンパイラは`basObj.z`元の基本クラスの値にします。</span><span class="sxs-lookup"><span data-stu-id="fcbb5-164">However, the base class cannot access the shadowing version of the variable `z` in the derived class, so the compiler resolves `basObj.z` to the original base class value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fcbb5-165">関連項目</span><span class="sxs-lookup"><span data-stu-id="fcbb5-165">See also</span></span>

- [<span data-ttu-id="fcbb5-166">宣言された要素の参照</span><span class="sxs-lookup"><span data-stu-id="fcbb5-166">References to Declared Elements</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
- [<span data-ttu-id="fcbb5-167">Visual Basic におけるスコープ</span><span class="sxs-lookup"><span data-stu-id="fcbb5-167">Scope in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)
- [<span data-ttu-id="fcbb5-168">拡大変換と縮小変換</span><span class="sxs-lookup"><span data-stu-id="fcbb5-168">Widening and Narrowing Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [<span data-ttu-id="fcbb5-169">Shadows</span><span class="sxs-lookup"><span data-stu-id="fcbb5-169">Shadows</span></span>](../../../../visual-basic/language-reference/modifiers/shadows.md)
- [<span data-ttu-id="fcbb5-170">Overrides</span><span class="sxs-lookup"><span data-stu-id="fcbb5-170">Overrides</span></span>](../../../../visual-basic/language-reference/modifiers/overrides.md)
- [<span data-ttu-id="fcbb5-171">Me、My、MyBase、および MyClass</span><span class="sxs-lookup"><span data-stu-id="fcbb5-171">Me, My, MyBase, and MyClass</span></span>](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
- [<span data-ttu-id="fcbb5-172">継承の基本</span><span class="sxs-lookup"><span data-stu-id="fcbb5-172">Inheritance Basics</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
