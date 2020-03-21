---
title: シャドウ
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
ms.openlocfilehash: 20a33478f622fca6d3183772f53dcb3e72f79409
ms.sourcegitcommit: 43d10ef65f0f1fd6c3b515e363bde11a3fcd8d6d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2020
ms.locfileid: "78266886"
---
# <a name="shadowing-in-visual-basic"></a><span data-ttu-id="b6e31-102">Visual Basic におけるシャドウ</span><span class="sxs-lookup"><span data-stu-id="b6e31-102">Shadowing in Visual Basic</span></span>
<span data-ttu-id="b6e31-103">2 つのプログラミング要素が同じ名前を共有する場合、そのうちの 1 つが隠れたり *、シャドウ*したりできます。</span><span class="sxs-lookup"><span data-stu-id="b6e31-103">When two programming elements share the same name, one of them can hide, or *shadow*, the other one.</span></span> <span data-ttu-id="b6e31-104">このような場合、シャドウされた要素は参照できません。代わりに、コードで要素名を使用すると、Visual Basic コンパイラは要素をシャドウする要素に解決します。</span><span class="sxs-lookup"><span data-stu-id="b6e31-104">In such a situation, the shadowed element is not available for reference; instead, when your code uses the element name, the Visual Basic compiler resolves it to the shadowing element.</span></span>  
  
## <a name="purpose"></a><span data-ttu-id="b6e31-105">目的</span><span class="sxs-lookup"><span data-stu-id="b6e31-105">Purpose</span></span>  
 <span data-ttu-id="b6e31-106">シャドウの主な目的は、クラス メンバーの定義を保護することです。</span><span class="sxs-lookup"><span data-stu-id="b6e31-106">The main purpose of shadowing is to protect the definition of your class members.</span></span> <span data-ttu-id="b6e31-107">基本クラスは、既に定義した要素と同じ名前の要素を作成する変更を受ける場合があります。</span><span class="sxs-lookup"><span data-stu-id="b6e31-107">The base class might undergo a change that creates an element with the same name as one you have already defined.</span></span> <span data-ttu-id="b6e31-108">この場合、修飾子は`Shadows`、クラスを通じて参照を新しい基本クラスの要素ではなく、定義したメンバーに解決するように強制します。</span><span class="sxs-lookup"><span data-stu-id="b6e31-108">If this happens, the `Shadows` modifier forces references through your class to be resolved to the member you defined, instead of to the new base class element.</span></span>  
  
## <a name="types-of-shadowing"></a><span data-ttu-id="b6e31-109">シャドウの種類</span><span class="sxs-lookup"><span data-stu-id="b6e31-109">Types of Shadowing</span></span>  
 <span data-ttu-id="b6e31-110">要素は、2 つの異なる方法で別の要素をシャドウできます。</span><span class="sxs-lookup"><span data-stu-id="b6e31-110">An element can shadow another element in two different ways.</span></span> <span data-ttu-id="b6e31-111">シャドウ要素は、シャドウされた要素を含む領域のサブ領域内で宣言*できます。*</span><span class="sxs-lookup"><span data-stu-id="b6e31-111">The shadowing element can be declared inside a subregion of the region containing the shadowed element, in which case the shadowing is accomplished *through scope*.</span></span> <span data-ttu-id="b6e31-112">または、派生クラスは基本クラスのメンバーを再定義*できます。*</span><span class="sxs-lookup"><span data-stu-id="b6e31-112">Or a deriving class can redefine a member of a base class, in which case the shadowing is done *through inheritance*.</span></span>  
  
### <a name="shadowing-through-scope"></a><span data-ttu-id="b6e31-113">スコープを通じてシャドウ</span><span class="sxs-lookup"><span data-stu-id="b6e31-113">Shadowing Through Scope</span></span>  
 <span data-ttu-id="b6e31-114">同じモジュール、クラス、または構造体内のプログラミング要素の名前は同じでスコープが異なる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="b6e31-114">It is possible for programming elements in the same module, class, or structure to have the same name but different scope.</span></span> <span data-ttu-id="b6e31-115">2 つの要素がこの方法で宣言され、コードが共有する名前を参照する場合、スコープが狭い要素は他の要素をシャドウします (ブロック スコープは最も狭くなります)。</span><span class="sxs-lookup"><span data-stu-id="b6e31-115">When two elements are declared in this manner and the code refers to the name they share, the element with the narrower scope shadows the other element (block scope is the narrowest).</span></span>  
  
 <span data-ttu-id="b6e31-116">たとえば、モジュールは という名前`Public``temp`の変数を定義でき、モジュール内のプロシージャは、 という名前`temp`のローカル変数も宣言できます。</span><span class="sxs-lookup"><span data-stu-id="b6e31-116">For example, a module can define a `Public` variable named `temp`, and a procedure within the module can declare a local variable also named `temp`.</span></span> <span data-ttu-id="b6e31-117">プロシージャ内`temp`からの参照はローカル変数にアクセスし、プロシージャの外部`temp`からの参照は変数にアクセス`Public`します。</span><span class="sxs-lookup"><span data-stu-id="b6e31-117">References to `temp` from within the procedure access the local variable, while references to `temp` from outside the procedure access the `Public` variable.</span></span> <span data-ttu-id="b6e31-118">この場合、プロシージャ変数は`temp`モジュール変数`temp`をシャドウします。</span><span class="sxs-lookup"><span data-stu-id="b6e31-118">In this case, the procedure variable `temp` shadows the module variable `temp`.</span></span>  
  
 <span data-ttu-id="b6e31-119">次の図は、 という 2`temp`つの変数を示しています。</span><span class="sxs-lookup"><span data-stu-id="b6e31-119">The following illustration shows two variables, both named `temp`.</span></span> <span data-ttu-id="b6e31-120">ローカル変数`temp`は、独自のプロシージャ`temp``p`内からアクセスすると、メンバー変数をシャドウします。</span><span class="sxs-lookup"><span data-stu-id="b6e31-120">The local variable `temp` shadows the member variable `temp` when accessed from within its own procedure `p`.</span></span> <span data-ttu-id="b6e31-121">ただし、キーワード`MyClass`はシャドウをバイパスし、メンバー変数にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="b6e31-121">However, the `MyClass` keyword bypasses the shadowing and accesses the member variable.</span></span>  
  
 ![スコープを通じてシャドウを表示するグラフィック。](./media/shadowing/shadow-scope-diagram.gif)
  
 <span data-ttu-id="b6e31-123">スコープを使用してシャドウを行う例については、「[方法 : 変数と同じ名前の変数を非表示にする](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b6e31-123">For an example of shadowing through scope, see [How to: Hide a Variable with the Same Name as Your Variable](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md).</span></span>  
  
### <a name="shadowing-through-inheritance"></a><span data-ttu-id="b6e31-124">継承によるシャドウ</span><span class="sxs-lookup"><span data-stu-id="b6e31-124">Shadowing Through Inheritance</span></span>  
 <span data-ttu-id="b6e31-125">派生クラスが基本クラスから継承されたプログラミング要素を再定義する場合、再定義する要素は元の要素をシャドウします。</span><span class="sxs-lookup"><span data-stu-id="b6e31-125">If a derived class redefines a programming element inherited from a base class, the redefining element shadows the original element.</span></span> <span data-ttu-id="b6e31-126">宣言された要素、またはオーバーロードされた要素のセットを、他の型でシャドウできます。</span><span class="sxs-lookup"><span data-stu-id="b6e31-126">You can shadow any type of declared element, or set of overloaded elements, with any other type.</span></span> <span data-ttu-id="b6e31-127">たとえば、変数は`Integer`プロシージャを`Function`シャドウできます。</span><span class="sxs-lookup"><span data-stu-id="b6e31-127">For example, an `Integer` variable can shadow a `Function` procedure.</span></span> <span data-ttu-id="b6e31-128">別のプロシージャでプロシージャをシャドウする場合は、別のパラメーター リストと別の戻り値の型を使用できます。</span><span class="sxs-lookup"><span data-stu-id="b6e31-128">If you shadow a procedure with another procedure, you can use a different parameter list and a different return type.</span></span>  
  
 <span data-ttu-id="b6e31-129">次の図は、基底`b`クラスと、`d`を`b`継承する派生クラスを示しています。</span><span class="sxs-lookup"><span data-stu-id="b6e31-129">The following illustration shows a base class `b` and a derived class `d` that inherits from `b`.</span></span> <span data-ttu-id="b6e31-130">基本クラスは という名前`proc`のプロシージャを定義し、派生クラスは同じ名前の別のプロシージャを使用してそのプロシージャをシャドウします。</span><span class="sxs-lookup"><span data-stu-id="b6e31-130">The base class defines a procedure named `proc`, and the derived class shadows it with another procedure of the same name.</span></span> <span data-ttu-id="b6e31-131">最初`Call`のステートメントは、派生クラスの`proc`シャドウにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="b6e31-131">The first `Call` statement accesses the shadowing `proc` in the derived class.</span></span> <span data-ttu-id="b6e31-132">ただし、この`MyBase`キーワードはシャドウをバイパスし、基本クラスのシャドウされたプロシージャにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="b6e31-132">However, the `MyBase` keyword bypasses the shadowing and accesses the shadowed procedure in the base class.</span></span>  
  
 ![継承によるシャドウのグラフィック ダイアグラム](./media/shadowing/shadowing-inherit-diagram.gif)  
  
 <span data-ttu-id="b6e31-134">継承によるシャドウの例については、「 方法[: 変数と同じ名前の変数を非表示にする](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md)」および「[方法 : 継承された変数を非表示にする](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-an-inherited-variable.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b6e31-134">For an example of shadowing through inheritance, see [How to: Hide a Variable with the Same Name as Your Variable](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md) and [How to: Hide an Inherited Variable](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-an-inherited-variable.md).</span></span>  
  
#### <a name="shadowing-and-access-level"></a><span data-ttu-id="b6e31-135">シャドウとアクセス レベル</span><span class="sxs-lookup"><span data-stu-id="b6e31-135">Shadowing and Access Level</span></span>  
 <span data-ttu-id="b6e31-136">シャドウ要素は、派生クラスを使用するコードから常にアクセスできるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="b6e31-136">The shadowing element is not always accessible from the code using the derived class.</span></span> <span data-ttu-id="b6e31-137">たとえば、それが宣言`Private`されている場合があります。</span><span class="sxs-lookup"><span data-stu-id="b6e31-137">For example, it might be declared `Private`.</span></span> <span data-ttu-id="b6e31-138">このような場合、シャドウは負け、コンパイラはシャドウが存在しなかった場合と同じ要素への参照を解決します。</span><span class="sxs-lookup"><span data-stu-id="b6e31-138">In such a case, shadowing is defeated and the compiler resolves any reference to the same element it would have if there had been no shadowing.</span></span> <span data-ttu-id="b6e31-139">この要素は、シャドウイング クラスから戻る最も少ない派生ステップでアクセス可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="b6e31-139">This element is the accessible element the fewest derivational steps backward from the shadowing class.</span></span> <span data-ttu-id="b6e31-140">シャドウされた要素がプロシージャの場合、解決方法は、同じ名前、パラメーター リスト、および戻り値の型を持つ最も近いアクセス可能なバージョンに対する解決です。</span><span class="sxs-lookup"><span data-stu-id="b6e31-140">If the shadowed element is a procedure, the resolution is to the closest accessible version with the same name, parameter list, and return type.</span></span>  
  
 <span data-ttu-id="b6e31-141">次の例は、3 つのクラスの継承階層を示しています。</span><span class="sxs-lookup"><span data-stu-id="b6e31-141">The following example shows an inheritance hierarchy of three classes.</span></span> <span data-ttu-id="b6e31-142">各クラスは`Sub`プロシージャ`display`を定義し、各派生`display`クラスは基本クラス内のプロシージャをシャドウします。</span><span class="sxs-lookup"><span data-stu-id="b6e31-142">Each class defines a `Sub` procedure `display`, and each derived class shadows the `display` procedure in its base class.</span></span>  
  
```vb  
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
  
 <span data-ttu-id="b6e31-143">前の例では、派生クラス`secondClass`のシャドウ`display`とプロシージャの`Private`使用。</span><span class="sxs-lookup"><span data-stu-id="b6e31-143">In the preceding example, the derived class `secondClass` shadows `display` with a `Private` procedure.</span></span> <span data-ttu-id="b6e31-144">モジュール`callDisplay`が`display`で`secondClass`呼び出されると、呼`secondClass`び出し元のコード`display`は外部にあるため、プライベート プロシージャにアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="b6e31-144">When module `callDisplay` calls `display` in `secondClass`, the calling code is outside `secondClass` and therefore cannot access the private `display` procedure.</span></span> <span data-ttu-id="b6e31-145">シャドウ処理は敗北し、コンパイラは基本クラス`display`のプロシージャへの参照を解決します。</span><span class="sxs-lookup"><span data-stu-id="b6e31-145">Shadowing is defeated, and the compiler resolves the reference to the base class `display` procedure.</span></span>  
  
 <span data-ttu-id="b6e31-146">ただし、さらに派生`thirdClass`クラスは`display``Public`として宣言するため、 の`callDisplay`コードからアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="b6e31-146">However, the further derived class `thirdClass` declares `display` as `Public`, so the code in `callDisplay` can access it.</span></span>  
  
## <a name="shadowing-and-overriding"></a><span data-ttu-id="b6e31-147">シャドウとオーバーライド</span><span class="sxs-lookup"><span data-stu-id="b6e31-147">Shadowing and Overriding</span></span>  
 <span data-ttu-id="b6e31-148">シャドウとオーバーライドを混同しないでください。</span><span class="sxs-lookup"><span data-stu-id="b6e31-148">Do not confuse shadowing with overriding.</span></span> <span data-ttu-id="b6e31-149">両方とも、派生クラスが基本クラスから継承し、宣言された要素を別の要素で再定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="b6e31-149">Both are used when a derived class inherits from a base class, and both redefine one declared element with another.</span></span> <span data-ttu-id="b6e31-150">しかし、両者には大きな違いがあります。</span><span class="sxs-lookup"><span data-stu-id="b6e31-150">But there are significant differences between the two.</span></span> <span data-ttu-id="b6e31-151">比較については、「[シャドウとオーバーライドの違い](../../../../visual-basic/programming-guide/language-features/declared-elements/differences-between-shadowing-and-overriding.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b6e31-151">For a comparison, see [Differences Between Shadowing and Overriding](../../../../visual-basic/programming-guide/language-features/declared-elements/differences-between-shadowing-and-overriding.md).</span></span>  
  
## <a name="shadowing-and-overloading"></a><span data-ttu-id="b6e31-152">シャドウとオーバーロード</span><span class="sxs-lookup"><span data-stu-id="b6e31-152">Shadowing and Overloading</span></span>  
 <span data-ttu-id="b6e31-153">派生クラス内の複数の要素を使用して同じ基本クラス要素をシャドウすると、シャドウする要素はその要素のオーバーロードされたバージョンになります。</span><span class="sxs-lookup"><span data-stu-id="b6e31-153">If you shadow the same base class element with more than one element in your derived class, the shadowing elements become overloaded versions of that element.</span></span> <span data-ttu-id="b6e31-154">詳細については、「 [Procedure Overloading](../../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b6e31-154">For more information, see [Procedure Overloading](../../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md).</span></span>  
  
## <a name="accessing-a-shadowed-element"></a><span data-ttu-id="b6e31-155">シャドウされた要素へのアクセス</span><span class="sxs-lookup"><span data-stu-id="b6e31-155">Accessing a Shadowed Element</span></span>  
 <span data-ttu-id="b6e31-156">派生クラスから要素にアクセスする場合、通常は、`Me`その派生クラスの現在のインスタンスを通じて、要素名をキーワードで修飾します。</span><span class="sxs-lookup"><span data-stu-id="b6e31-156">When you access an element from a derived class, you normally do so through the current instance of that derived class, by qualifying the element name with the `Me` keyword.</span></span> <span data-ttu-id="b6e31-157">派生クラスが基本クラスの要素をシャドウする場合は、キーワードで修飾することで基本クラスの要素に`MyBase`アクセスできます。</span><span class="sxs-lookup"><span data-stu-id="b6e31-157">If your derived class shadows the element in the base class, you can access the base class element by qualifying it with the `MyBase` keyword.</span></span>  
  
 <span data-ttu-id="b6e31-158">シャドウされた要素にアクセスする例については、「 方法[: 派生クラスによって非表示になっている変数にアクセス](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md)する 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b6e31-158">For an example of accessing a shadowed element, see [How to: Access a Variable Hidden by a Derived Class](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md).</span></span>  
  
### <a name="declaration-of-the-object-variable"></a><span data-ttu-id="b6e31-159">オブジェクト変数の宣言</span><span class="sxs-lookup"><span data-stu-id="b6e31-159">Declaration of the Object Variable</span></span>  
 <span data-ttu-id="b6e31-160">オブジェクト変数の作成方法は、派生クラスがシャドウする要素またはシャドウされた要素のいずれにアクセスするかにも影響を与えます。</span><span class="sxs-lookup"><span data-stu-id="b6e31-160">How you create the object variable can also affect whether the derived class accesses a shadowing element or the shadowed element.</span></span> <span data-ttu-id="b6e31-161">次の例では、派生クラスから 2 つのオブジェクトを作成しますが、一方のオブジェクトは基本クラスとして宣言され、もう 1 つのオブジェクトは派生クラスとして宣言されます。</span><span class="sxs-lookup"><span data-stu-id="b6e31-161">The following example creates two objects from a derived class, but one object is declared as the base class and the other as the derived class.</span></span>  
  
```vb  
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
  
 <span data-ttu-id="b6e31-162">前の例では、変数`basObj`は基本クラスとして宣言されています。</span><span class="sxs-lookup"><span data-stu-id="b6e31-162">In the preceding example, the variable `basObj` is declared as the base class.</span></span> <span data-ttu-id="b6e31-163">オブジェクトを`dervCls`オブジェクトに割り当てることは、拡大変換を構成するため有効です。</span><span class="sxs-lookup"><span data-stu-id="b6e31-163">Assigning a `dervCls` object to it constitutes a widening conversion and is therefore valid.</span></span> <span data-ttu-id="b6e31-164">ただし、基本クラスは、派生クラス内の変数`z`のシャドウバージョンにアクセスできないため、コンパイラは元の基本クラス`basObj.z`の値に解決されます。</span><span class="sxs-lookup"><span data-stu-id="b6e31-164">However, the base class cannot access the shadowing version of the variable `z` in the derived class, so the compiler resolves `basObj.z` to the original base class value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6e31-165">関連項目</span><span class="sxs-lookup"><span data-stu-id="b6e31-165">See also</span></span>

- [<span data-ttu-id="b6e31-166">References to Declared Elements</span><span class="sxs-lookup"><span data-stu-id="b6e31-166">References to Declared Elements</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
- [<span data-ttu-id="b6e31-167">Visual Basic におけるスコープ</span><span class="sxs-lookup"><span data-stu-id="b6e31-167">Scope in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)
- [<span data-ttu-id="b6e31-168">Widening and Narrowing Conversions</span><span class="sxs-lookup"><span data-stu-id="b6e31-168">Widening and Narrowing Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [<span data-ttu-id="b6e31-169">Shadows</span><span class="sxs-lookup"><span data-stu-id="b6e31-169">Shadows</span></span>](../../../../visual-basic/language-reference/modifiers/shadows.md)
- [<span data-ttu-id="b6e31-170">Overrides</span><span class="sxs-lookup"><span data-stu-id="b6e31-170">Overrides</span></span>](../../../../visual-basic/language-reference/modifiers/overrides.md)
- [<span data-ttu-id="b6e31-171">Me、My、MyBase、および MyClass</span><span class="sxs-lookup"><span data-stu-id="b6e31-171">Me, My, MyBase, and MyClass</span></span>](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
- [<span data-ttu-id="b6e31-172">継承の基本</span><span class="sxs-lookup"><span data-stu-id="b6e31-172">Inheritance Basics</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
