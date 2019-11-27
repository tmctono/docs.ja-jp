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
ms.openlocfilehash: 034b5c0ecf3be6e77048fb7318e931801575f07a
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345324"
---
# <a name="shadowing-in-visual-basic"></a><span data-ttu-id="ed3c8-102">Visual Basic におけるシャドウ</span><span class="sxs-lookup"><span data-stu-id="ed3c8-102">Shadowing in Visual Basic</span></span>
<span data-ttu-id="ed3c8-103">2つのプログラミング要素が同じ名前を共有している場合、そのうちの1つは、もう一方を非表示にしたり*影*を付けることができます。</span><span class="sxs-lookup"><span data-stu-id="ed3c8-103">When two programming elements share the same name, one of them can hide, or *shadow*, the other one.</span></span> <span data-ttu-id="ed3c8-104">このような状況では、シャドウされた要素を参照することはできません。代わりに、コードで要素名を使用すると、Visual Basic コンパイラによってシャドウ要素に解決されます。</span><span class="sxs-lookup"><span data-stu-id="ed3c8-104">In such a situation, the shadowed element is not available for reference; instead, when your code uses the element name, the Visual Basic compiler resolves it to the shadowing element.</span></span>  
  
## <a name="purpose"></a><span data-ttu-id="ed3c8-105">用途</span><span class="sxs-lookup"><span data-stu-id="ed3c8-105">Purpose</span></span>  
 <span data-ttu-id="ed3c8-106">シャドウの主な目的は、クラスメンバーの定義を保護することです。</span><span class="sxs-lookup"><span data-stu-id="ed3c8-106">The main purpose of shadowing is to protect the definition of your class members.</span></span> <span data-ttu-id="ed3c8-107">基本クラスには、既に定義されているものと同じ名前の要素を作成する変更が含まれる場合があります。</span><span class="sxs-lookup"><span data-stu-id="ed3c8-107">The base class might undergo a change that creates an element with the same name as one you have already defined.</span></span> <span data-ttu-id="ed3c8-108">この場合、`Shadows` 修飾子は、新しい基底クラス要素ではなく、定義したメンバーに解決されるように、クラスを通じて参照を強制します。</span><span class="sxs-lookup"><span data-stu-id="ed3c8-108">If this happens, the `Shadows` modifier forces references through your class to be resolved to the member you defined, instead of to the new base class element.</span></span>  
  
## <a name="types-of-shadowing"></a><span data-ttu-id="ed3c8-109">シャドウの種類</span><span class="sxs-lookup"><span data-stu-id="ed3c8-109">Types of Shadowing</span></span>  
 <span data-ttu-id="ed3c8-110">要素は、2つの異なる方法で別の要素をシャドウできます。</span><span class="sxs-lookup"><span data-stu-id="ed3c8-110">An element can shadow another element in two different ways.</span></span> <span data-ttu-id="ed3c8-111">シャドウ要素は、シャドウされた要素を含む領域のサブ領域内で宣言できます。この場合、シャドウは*スコープによって*行われます。</span><span class="sxs-lookup"><span data-stu-id="ed3c8-111">The shadowing element can be declared inside a subregion of the region containing the shadowed element, in which case the shadowing is accomplished *through scope*.</span></span> <span data-ttu-id="ed3c8-112">または、派生クラスで基底クラスのメンバーを再定義できます。この場合、シャドウは*継承によって*行われます。</span><span class="sxs-lookup"><span data-stu-id="ed3c8-112">Or a deriving class can redefine a member of a base class, in which case the shadowing is done *through inheritance*.</span></span>  
  
### <a name="shadowing-through-scope"></a><span data-ttu-id="ed3c8-113">スコープによるシャドウ処理</span><span class="sxs-lookup"><span data-stu-id="ed3c8-113">Shadowing Through Scope</span></span>  
 <span data-ttu-id="ed3c8-114">同じモジュール、クラス、または構造体のプログラミング要素が同じ名前でスコープが異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="ed3c8-114">It is possible for programming elements in the same module, class, or structure to have the same name but different scope.</span></span> <span data-ttu-id="ed3c8-115">2つの要素がこのように宣言されていて、コードが共有する名前を参照している場合、狭いスコープの要素は他の要素をシャドウします (ブロックスコープは最も狭いものです)。</span><span class="sxs-lookup"><span data-stu-id="ed3c8-115">When two elements are declared in this manner and the code refers to the name they share, the element with the narrower scope shadows the other element (block scope is the narrowest).</span></span>  
  
 <span data-ttu-id="ed3c8-116">たとえば、モジュールは `temp`という名前の `Public` 変数を定義できます。モジュール内のプロシージャは、`temp`という名前のローカル変数も宣言できます。</span><span class="sxs-lookup"><span data-stu-id="ed3c8-116">For example, a module can define a `Public` variable named `temp`, and a procedure within the module can declare a local variable also named `temp`.</span></span> <span data-ttu-id="ed3c8-117">プロシージャ内から `temp` への参照はローカル変数にアクセスしますが、プロシージャの外部から `temp` への参照は `Public` 変数にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="ed3c8-117">References to `temp` from within the procedure access the local variable, while references to `temp` from outside the procedure access the `Public` variable.</span></span> <span data-ttu-id="ed3c8-118">この場合、プロシージャ変数 `temp`、モジュール変数 `temp`をシャドウします。</span><span class="sxs-lookup"><span data-stu-id="ed3c8-118">In this case, the procedure variable `temp` shadows the module variable `temp`.</span></span>  
  
 <span data-ttu-id="ed3c8-119">次の図は、両方とも `temp`という名前の2つの変数を示しています。</span><span class="sxs-lookup"><span data-stu-id="ed3c8-119">The following illustration shows two variables, both named `temp`.</span></span> <span data-ttu-id="ed3c8-120">ローカル変数は、独自のプロシージャ `p`内からアクセスされるときに、メンバー変数 `temp` `temp` シャドウします。</span><span class="sxs-lookup"><span data-stu-id="ed3c8-120">The local variable `temp` shadows the member variable `temp` when accessed from within its own procedure `p`.</span></span> <span data-ttu-id="ed3c8-121">ただし、`MyClass` キーワードはシャドウをバイパスし、メンバー変数にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="ed3c8-121">However, the `MyClass` keyword bypasses the shadowing and accesses the member variable.</span></span>  
  
 ![スコープによるシャドウ処理を示すグラフィック。](./media/shadowing/shadow-scope-diagram.gif)
  
 <span data-ttu-id="ed3c8-123">スコープを使用したシャドウの例については、「[方法: 変数と同じ名前の変数を非表示に](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ed3c8-123">For an example of shadowing through scope, see [How to: Hide a Variable with the Same Name as Your Variable](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md).</span></span>  
  
### <a name="shadowing-through-inheritance"></a><span data-ttu-id="ed3c8-124">継承によるシャドウ処理</span><span class="sxs-lookup"><span data-stu-id="ed3c8-124">Shadowing Through Inheritance</span></span>  
 <span data-ttu-id="ed3c8-125">派生クラスが基底クラスから継承されたプログラミング要素を再定義する場合、再定義要素は元の要素をシャドウします。</span><span class="sxs-lookup"><span data-stu-id="ed3c8-125">If a derived class redefines a programming element inherited from a base class, the redefining element shadows the original element.</span></span> <span data-ttu-id="ed3c8-126">宣言された要素の型、またはオーバーロードされた要素のセットは、他の型を使用してシャドウできます。</span><span class="sxs-lookup"><span data-stu-id="ed3c8-126">You can shadow any type of declared element, or set of overloaded elements, with any other type.</span></span> <span data-ttu-id="ed3c8-127">たとえば、`Integer` 変数を使用すると、`Function` プロシージャをシャドウできます。</span><span class="sxs-lookup"><span data-stu-id="ed3c8-127">For example, an `Integer` variable can shadow a `Function` procedure.</span></span> <span data-ttu-id="ed3c8-128">別のプロシージャでプロシージャをシャドウする場合は、別のパラメーターリストと別の戻り値の型を使用できます。</span><span class="sxs-lookup"><span data-stu-id="ed3c8-128">If you shadow a procedure with another procedure, you can use a different parameter list and a different return type.</span></span>  
  
 <span data-ttu-id="ed3c8-129">次の図は、基本クラス `b` と、`b`から継承する派生クラス `d` を示しています。</span><span class="sxs-lookup"><span data-stu-id="ed3c8-129">The following illustration shows a base class `b` and a derived class `d` that inherits from `b`.</span></span> <span data-ttu-id="ed3c8-130">基底クラスは `proc`という名前のプロシージャを定義し、派生クラスは同じ名前の別のプロシージャでそれをシャドウします。</span><span class="sxs-lookup"><span data-stu-id="ed3c8-130">The base class defines a procedure named `proc`, and the derived class shadows it with another procedure of the same name.</span></span> <span data-ttu-id="ed3c8-131">最初の `Call` ステートメントは、派生クラスのシャドウ `proc` にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="ed3c8-131">The first `Call` statement accesses the shadowing `proc` in the derived class.</span></span> <span data-ttu-id="ed3c8-132">ただし、`MyBase` キーワードはシャドウをバイパスし、基本クラスのシャドウされたプロシージャにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="ed3c8-132">However, the `MyBase` keyword bypasses the shadowing and accesses the shadowed procedure in the base class.</span></span>  
  
 ![継承によるシャドウのグラフィック ダイアグラム](./media/shadowing/shadowing-inherit-diagram.gif)  
  
 <span data-ttu-id="ed3c8-134">継承によるシャドウ処理の例については、「[方法: 変数と同じ名前の変数を非表示](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md)にする」および「[方法: 継承された変数を非表示にする](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-an-inherited-variable.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ed3c8-134">For an example of shadowing through inheritance, see [How to: Hide a Variable with the Same Name as Your Variable](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md) and [How to: Hide an Inherited Variable](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-an-inherited-variable.md).</span></span>  
  
#### <a name="shadowing-and-access-level"></a><span data-ttu-id="ed3c8-135">シャドウとアクセスレベル</span><span class="sxs-lookup"><span data-stu-id="ed3c8-135">Shadowing and Access Level</span></span>  
 <span data-ttu-id="ed3c8-136">シャドウ要素は、派生クラスを使用してコードから常にアクセスできるとは限りません。</span><span class="sxs-lookup"><span data-stu-id="ed3c8-136">The shadowing element is not always accessible from the code using the derived class.</span></span> <span data-ttu-id="ed3c8-137">たとえば、`Private`として宣言されている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ed3c8-137">For example, it might be declared `Private`.</span></span> <span data-ttu-id="ed3c8-138">このような場合は、シャドウが解消され、シャドウが存在しない場合と同じ要素への参照がコンパイラによって解決されます。</span><span class="sxs-lookup"><span data-stu-id="ed3c8-138">In such a case, shadowing is defeated and the compiler resolves any reference to the same element it would have if there had been no shadowing.</span></span> <span data-ttu-id="ed3c8-139">この要素は、アクセス可能な要素であり、シャドウクラスから逆方向に derivational ステップが最も少ない。</span><span class="sxs-lookup"><span data-stu-id="ed3c8-139">This element is the accessible element the fewest derivational steps backward from the shadowing class.</span></span> <span data-ttu-id="ed3c8-140">シャドウされた要素がプロシージャの場合、解決策は、同じ名前、パラメーターリスト、および戻り値の型を持つアクセス可能な最も近いバージョンになります。</span><span class="sxs-lookup"><span data-stu-id="ed3c8-140">If the shadowed element is a procedure, the resolution is to the closest accessible version with the same name, parameter list, and return type.</span></span>  
  
 <span data-ttu-id="ed3c8-141">次の例は、3つのクラスの継承階層を示しています。</span><span class="sxs-lookup"><span data-stu-id="ed3c8-141">The following example shows an inheritance hierarchy of three classes.</span></span> <span data-ttu-id="ed3c8-142">各クラスは `Sub` プロシージャ `display`を定義します。各派生クラスは、基本クラスの `display` プロシージャをシャドウします。</span><span class="sxs-lookup"><span data-stu-id="ed3c8-142">Each class defines a `Sub` procedure `display`, and each derived class shadows the `display` procedure in its base class.</span></span>  
  
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
  
 <span data-ttu-id="ed3c8-143">前の例では、派生クラス `secondClass`、`Private` プロシージャと共に `display` シャドウしています。</span><span class="sxs-lookup"><span data-stu-id="ed3c8-143">In the preceding example, the derived class `secondClass` shadows `display` with a `Private` procedure.</span></span> <span data-ttu-id="ed3c8-144">モジュール `callDisplay` が `secondClass`で `display` を呼び出すと、呼び出し元のコードが `secondClass` 外部にあるため、プライベート `display` プロシージャにアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="ed3c8-144">When module `callDisplay` calls `display` in `secondClass`, the calling code is outside `secondClass` and therefore cannot access the private `display` procedure.</span></span> <span data-ttu-id="ed3c8-145">シャドウが解消され、コンパイラが基底クラス `display` プロシージャへの参照を解決します。</span><span class="sxs-lookup"><span data-stu-id="ed3c8-145">Shadowing is defeated, and the compiler resolves the reference to the base class `display` procedure.</span></span>  
  
 <span data-ttu-id="ed3c8-146">ただし、さらに派生したクラス `thirdClass` は `display` を `Public`として宣言するので、`callDisplay` のコードからアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="ed3c8-146">However, the further derived class `thirdClass` declares `display` as `Public`, so the code in `callDisplay` can access it.</span></span>  
  
## <a name="shadowing-and-overriding"></a><span data-ttu-id="ed3c8-147">シャドウとオーバーライド</span><span class="sxs-lookup"><span data-stu-id="ed3c8-147">Shadowing and Overriding</span></span>  
 <span data-ttu-id="ed3c8-148">シャドウは、オーバーライドと混同しないようにしてください。</span><span class="sxs-lookup"><span data-stu-id="ed3c8-148">Do not confuse shadowing with overriding.</span></span> <span data-ttu-id="ed3c8-149">どちらも、派生クラスが基底クラスから継承し、宣言された1つの要素を別の要素で再定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="ed3c8-149">Both are used when a derived class inherits from a base class, and both redefine one declared element with another.</span></span> <span data-ttu-id="ed3c8-150">ただし、2つの間には大きな違いがあります。</span><span class="sxs-lookup"><span data-stu-id="ed3c8-150">But there are significant differences between the two.</span></span> <span data-ttu-id="ed3c8-151">比較については、「[シャドウとオーバーライドの違い](../../../../visual-basic/programming-guide/language-features/declared-elements/differences-between-shadowing-and-overriding.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ed3c8-151">For a comparison, see [Differences Between Shadowing and Overriding](../../../../visual-basic/programming-guide/language-features/declared-elements/differences-between-shadowing-and-overriding.md).</span></span>  
  
## <a name="shadowing-and-overloading"></a><span data-ttu-id="ed3c8-152">シャドウとオーバーロード</span><span class="sxs-lookup"><span data-stu-id="ed3c8-152">Shadowing and Overloading</span></span>  
 <span data-ttu-id="ed3c8-153">派生クラス内の複数の要素を持つ同じ基底クラス要素をシャドウする場合、シャドウされる要素は、その要素のオーバーロードされたバージョンになります。</span><span class="sxs-lookup"><span data-stu-id="ed3c8-153">If you shadow the same base class element with more than one element in your derived class, the shadowing elements become overloaded versions of that element.</span></span> <span data-ttu-id="ed3c8-154">詳細については、「 [Procedure Overloading](../../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ed3c8-154">For more information, see [Procedure Overloading](../../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md).</span></span>  
  
## <a name="accessing-a-shadowed-element"></a><span data-ttu-id="ed3c8-155">シャドウ要素へのアクセス</span><span class="sxs-lookup"><span data-stu-id="ed3c8-155">Accessing a Shadowed Element</span></span>  
 <span data-ttu-id="ed3c8-156">派生クラスから要素にアクセスする場合、通常は、その派生クラスの現在のインスタンスを使用します。そのためには、要素名を `Me` キーワードで修飾します。</span><span class="sxs-lookup"><span data-stu-id="ed3c8-156">When you access an element from a derived class, you normally do so through the current instance of that derived class, by qualifying the element name with the `Me` keyword.</span></span> <span data-ttu-id="ed3c8-157">派生クラスが基底クラスの要素をシャドウする場合は、`MyBase` キーワードを使用して修飾することで、基底クラスの要素にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="ed3c8-157">If your derived class shadows the element in the base class, you can access the base class element by qualifying it with the `MyBase` keyword.</span></span>  
  
 <span data-ttu-id="ed3c8-158">シャドウされた要素にアクセスする例については、「[方法: 派生クラスによって非表示になっている変数にアクセスする](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ed3c8-158">For an example of accessing a shadowed element, see [How to: Access a Variable Hidden by a Derived Class](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md).</span></span>  
  
### <a name="declaration-of-the-object-variable"></a><span data-ttu-id="ed3c8-159">オブジェクト変数の宣言</span><span class="sxs-lookup"><span data-stu-id="ed3c8-159">Declaration of the Object Variable</span></span>  
 <span data-ttu-id="ed3c8-160">オブジェクト変数を作成する方法は、派生クラスがシャドウ要素またはシャドウされた要素にアクセスするかどうかにも影響します。</span><span class="sxs-lookup"><span data-stu-id="ed3c8-160">How you create the object variable can also affect whether the derived class accesses a shadowing element or the shadowed element.</span></span> <span data-ttu-id="ed3c8-161">次の例では、派生クラスから2つのオブジェクトを作成しますが、一方のオブジェクトは基底クラスとして、もう1つは派生クラスとして宣言されています。</span><span class="sxs-lookup"><span data-stu-id="ed3c8-161">The following example creates two objects from a derived class, but one object is declared as the base class and the other as the derived class.</span></span>  
  
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
  
 <span data-ttu-id="ed3c8-162">前の例では、変数 `basObj` が基本クラスとして宣言されています。</span><span class="sxs-lookup"><span data-stu-id="ed3c8-162">In the preceding example, the variable `basObj` is declared as the base class.</span></span> <span data-ttu-id="ed3c8-163">`dervCls` オブジェクトをこのオブジェクトに割り当てると、拡大変換が構成されるため、有効になります。</span><span class="sxs-lookup"><span data-stu-id="ed3c8-163">Assigning a `dervCls` object to it constitutes a widening conversion and is therefore valid.</span></span> <span data-ttu-id="ed3c8-164">ただし、基底クラスは派生クラスの変数 `z` のシャドウバージョンにアクセスできないため、コンパイラは `basObj.z` を元の基底クラスの値に解決します。</span><span class="sxs-lookup"><span data-stu-id="ed3c8-164">However, the base class cannot access the shadowing version of the variable `z` in the derived class, so the compiler resolves `basObj.z` to the original base class value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed3c8-165">参照</span><span class="sxs-lookup"><span data-stu-id="ed3c8-165">See also</span></span>

- [<span data-ttu-id="ed3c8-166">宣言された要素の参照</span><span class="sxs-lookup"><span data-stu-id="ed3c8-166">References to Declared Elements</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
- [<span data-ttu-id="ed3c8-167">Visual Basic 内のスコープ</span><span class="sxs-lookup"><span data-stu-id="ed3c8-167">Scope in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)
- [<span data-ttu-id="ed3c8-168">拡大変換と縮小変換</span><span class="sxs-lookup"><span data-stu-id="ed3c8-168">Widening and Narrowing Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [<span data-ttu-id="ed3c8-169">Shadows</span><span class="sxs-lookup"><span data-stu-id="ed3c8-169">Shadows</span></span>](../../../../visual-basic/language-reference/modifiers/shadows.md)
- [<span data-ttu-id="ed3c8-170">Overrides</span><span class="sxs-lookup"><span data-stu-id="ed3c8-170">Overrides</span></span>](../../../../visual-basic/language-reference/modifiers/overrides.md)
- [<span data-ttu-id="ed3c8-171">Me、My、MyBase、および MyClass</span><span class="sxs-lookup"><span data-stu-id="ed3c8-171">Me, My, MyBase, and MyClass</span></span>](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
- [<span data-ttu-id="ed3c8-172">継承の基本</span><span class="sxs-lookup"><span data-stu-id="ed3c8-172">Inheritance Basics</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
