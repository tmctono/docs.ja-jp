---
title: '方法: 変数 (Visual Basic) と同じ名前の変数を非表示にします。'
ms.date: 07/20/2015
helpviewer_keywords:
- qualification [Visual Basic], of element names
- declarations [Visual Basic], elements
- element names [Visual Basic], qualification
- references [Visual Basic], declared elements
- declaration statements [Visual Basic], declared elements
- declaring elements [Visual Basic]
- referencing declared elements [Visual Basic]
- declared elements [Visual Basic], referencing
- declared elements [Visual Basic], about declared elements
ms.assetid: e39c0752-f19f-4d2e-a453-00df1b5fc7ee
ms.openlocfilehash: 3230dac924e9c22231494bfc8b81cd74e356bca3
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64610314"
---
# <a name="how-to-hide-a-variable-with-the-same-name-as-your-variable-visual-basic"></a><span data-ttu-id="685d1-102">方法: 変数 (Visual Basic) と同じ名前の変数を非表示にします。</span><span class="sxs-lookup"><span data-stu-id="685d1-102">How to: Hide a Variable with the Same Name as Your Variable (Visual Basic)</span></span>
<span data-ttu-id="685d1-103">変数を非表示にすることができます*シャドウ*は、これによって、同じ名前の変数で再定義します。</span><span class="sxs-lookup"><span data-stu-id="685d1-103">You can hide a variable by *shadowing* it, that is, by redefining it with a variable of the same name.</span></span> <span data-ttu-id="685d1-104">2 つの方法で非表示に変数をシャドウすることができます。</span><span class="sxs-lookup"><span data-stu-id="685d1-104">You can shadow the variable you want to hide in two ways:</span></span>  
  
- <span data-ttu-id="685d1-105">**スコープによるシャドウします。**</span><span class="sxs-lookup"><span data-stu-id="685d1-105">**Shadowing Through Scope.**</span></span> <span data-ttu-id="685d1-106">その操作は、非表示に変数を格納しているリージョンのサブ領域内で再宣言することによってスコープによるシャドウできます。</span><span class="sxs-lookup"><span data-stu-id="685d1-106">You can shadow it through scope by redeclaring it inside a subregion of the region containing the variable you want to hide.</span></span>  
  
- <span data-ttu-id="685d1-107">**継承によるシャドウします。**</span><span class="sxs-lookup"><span data-stu-id="685d1-107">**Shadowing Through Inheritance.**</span></span> <span data-ttu-id="685d1-108">クラス レベルで非表示にする、変数が定義されている場合、することができます、継承によるシャドウを再度宣言することによって、 [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md)派生クラスでのキーワード。</span><span class="sxs-lookup"><span data-stu-id="685d1-108">If the variable you want to hide is defined at class level, you can shadow it through inheritance by redeclaring it with the [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md) keyword in a derived class.</span></span>  
  
## <a name="two-ways-to-hide-a-variable"></a><span data-ttu-id="685d1-109">2 つの変数を非表示にする方法</span><span class="sxs-lookup"><span data-stu-id="685d1-109">Two Ways to Hide a Variable</span></span>  
  
#### <a name="to-hide-a-variable-by-shadowing-it-through-scope"></a><span data-ttu-id="685d1-110">スコープによるシャドウすることによって、変数を非表示にするには</span><span class="sxs-lookup"><span data-stu-id="685d1-110">To hide a variable by shadowing it through scope</span></span>  
  
1. <span data-ttu-id="685d1-111">を非表示にする変数を定義するリージョンを特定し、で、変数を使用してを再定義するサブ領域を決定します。</span><span class="sxs-lookup"><span data-stu-id="685d1-111">Determine the region defining the variable you want to hide, and determine a subregion in which to redefine it with your variable.</span></span>  
  
    |<span data-ttu-id="685d1-112">変数の領域</span><span class="sxs-lookup"><span data-stu-id="685d1-112">Variable's region</span></span>|<span data-ttu-id="685d1-113">再定義が使用可能なサブ地域</span><span class="sxs-lookup"><span data-stu-id="685d1-113">Allowable subregion for redefining it</span></span>|  
    |-----------------------|-------------------------------------------|  
    |<span data-ttu-id="685d1-114">Module</span><span class="sxs-lookup"><span data-stu-id="685d1-114">Module</span></span>|<span data-ttu-id="685d1-115">モジュール内のクラス</span><span class="sxs-lookup"><span data-stu-id="685d1-115">A class within the module</span></span>|  
    |<span data-ttu-id="685d1-116">クラス</span><span class="sxs-lookup"><span data-stu-id="685d1-116">Class</span></span>|<span data-ttu-id="685d1-117">クラス内のサブクラス</span><span class="sxs-lookup"><span data-stu-id="685d1-117">A subclass within the class</span></span><br /><br /> <span data-ttu-id="685d1-118">クラス内のプロシージャ</span><span class="sxs-lookup"><span data-stu-id="685d1-118">A procedure within the class</span></span>|  
  
     <span data-ttu-id="685d1-119">再定義できませんそのプロシージャ内のブロックでプロシージャの変数などの、 `If`...`End If`構築または`For`ループします。</span><span class="sxs-lookup"><span data-stu-id="685d1-119">You cannot redefine a procedure variable in a block within that procedure, for example in an `If`...`End If` construction or a `For` loop.</span></span>  
  
2. <span data-ttu-id="685d1-120">存在しない場合は、サブ領域を作成します。</span><span class="sxs-lookup"><span data-stu-id="685d1-120">Create the subregion if it does not already exist.</span></span>  
  
3. <span data-ttu-id="685d1-121">、地区内では、書き込み、 [Dim ステートメント](../../../../visual-basic/language-reference/statements/dim-statement.md)シャドウの変数を宣言します。</span><span class="sxs-lookup"><span data-stu-id="685d1-121">Within the subregion, write a [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md) declaring the shadowing variable.</span></span>  
  
     <span data-ttu-id="685d1-122">サブ領域内のコードは、変数名が参照されているとき、コンパイラは変数のシャドウへの参照を解決します。</span><span class="sxs-lookup"><span data-stu-id="685d1-122">When code inside the subregion refers to the variable name, the compiler resolves the reference to the shadowing variable.</span></span>  
  
     <span data-ttu-id="685d1-123">次の例では、シャドウの参照と同様に、スコープによるシャドウを示します。</span><span class="sxs-lookup"><span data-stu-id="685d1-123">The following example illustrates shadowing through scope, as well as a reference that bypasses the shadowing.</span></span>  
  
    ```  
    Module shadowByScope  
        ' The following statement declares num as a module-level variable.  
        Public num As Integer  
        Sub show()  
            ' The following statement declares num as a local variable.  
            Dim num As Integer  
            ' The following statement sets the value of the local variable.  
            num = 2  
            ' The following statement displays the module-level variable.  
            MsgBox(CStr(shadowByScope.num))  
        End Sub  
        Sub useModuleLevelNum()  
            ' The following statement sets the value of the module-level variable.  
            num = 1  
            show()  
        End Sub  
    End Module  
    ```  
  
     <span data-ttu-id="685d1-124">前の例は、変数を宣言して`num`モジュール レベルとプロシージャ レベルの両方 (の手順で`show`)。</span><span class="sxs-lookup"><span data-stu-id="685d1-124">The preceding example declares the variable `num` both at module level and at procedure level (in the procedure `show`).</span></span> <span data-ttu-id="685d1-125">ローカル変数`num`モジュール レベル変数をシャドウ`num`内`show`ので、ローカル変数が 2 に設定します。</span><span class="sxs-lookup"><span data-stu-id="685d1-125">The local variable `num` shadows the module-level variable `num` within `show`, so the local variable is set to 2.</span></span> <span data-ttu-id="685d1-126">ただし、シャドウをローカル変数がない`num`で、`useModuleLevelNum`プロシージャ。</span><span class="sxs-lookup"><span data-stu-id="685d1-126">However, there is no local variable to shadow `num` in the `useModuleLevelNum` procedure.</span></span> <span data-ttu-id="685d1-127">そのため、`useModuleLevelNum`モジュール レベル変数の値を 1 に設定します。</span><span class="sxs-lookup"><span data-stu-id="685d1-127">Therefore, `useModuleLevelNum` sets the value of the module-level variable to 1.</span></span>  
  
     <span data-ttu-id="685d1-128">`MsgBox`内で呼び出す`show`修飾することにより、シャドウ機構をバイパスする`num`モジュールの名前。</span><span class="sxs-lookup"><span data-stu-id="685d1-128">The `MsgBox` call inside `show` bypasses the shadowing mechanism by qualifying `num` with the module name.</span></span> <span data-ttu-id="685d1-129">そのため、ローカル変数の代わりに、モジュール レベル変数を表示します。</span><span class="sxs-lookup"><span data-stu-id="685d1-129">Therefore, it displays the module-level variable instead of the local variable.</span></span>  
  
#### <a name="to-hide-a-variable-by-shadowing-it-through-inheritance"></a><span data-ttu-id="685d1-130">継承によるシャドウすることによって、変数を非表示にするには</span><span class="sxs-lookup"><span data-stu-id="685d1-130">To hide a variable by shadowing it through inheritance</span></span>  
  
1. <span data-ttu-id="685d1-131">必ず、クラスでは、および (プロシージャ) の外側のクラス レベルで非表示にする、変数が宣言されてください。</span><span class="sxs-lookup"><span data-stu-id="685d1-131">Be sure the variable you want to hide is declared in a class, and at class level (outside any procedure).</span></span> <span data-ttu-id="685d1-132">それ以外の場合継承によるシャドウすることはできません。</span><span class="sxs-lookup"><span data-stu-id="685d1-132">Otherwise you cannot shadow it through inheritance.</span></span>  
  
2. <span data-ttu-id="685d1-133">既に存在しない場合、変数のクラスから派生したクラスを定義します。</span><span class="sxs-lookup"><span data-stu-id="685d1-133">Define a class derived from the variable's class if one does not already exist.</span></span>  
  
3. <span data-ttu-id="685d1-134">派生クラス内では、書き込み、`Dim`ステートメント、変数を宣言します。</span><span class="sxs-lookup"><span data-stu-id="685d1-134">Inside the derived class, write a `Dim` statement declaring your variable.</span></span> <span data-ttu-id="685d1-135">含める、 [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md)キーワードで宣言します。</span><span class="sxs-lookup"><span data-stu-id="685d1-135">Include the [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md) keyword in the declaration.</span></span>  
  
     <span data-ttu-id="685d1-136">派生クラスのコードは、変数名が参照されていると、コンパイラは、変数への参照を解決します。</span><span class="sxs-lookup"><span data-stu-id="685d1-136">When code in the derived class refers to the variable name, the compiler resolves the reference to your variable.</span></span>  
  
     <span data-ttu-id="685d1-137">次の例では、継承によるシャドウを示します。</span><span class="sxs-lookup"><span data-stu-id="685d1-137">The following example illustrates shadowing through inheritance.</span></span> <span data-ttu-id="685d1-138">2 つの参照変数のシャドウにアクセスする、シャドウになります。</span><span class="sxs-lookup"><span data-stu-id="685d1-138">It makes two references, one that accesses the shadowing variable and one that bypasses the shadowing.</span></span>  
  
    ```  
    Public Class shadowBaseClass  
        Public shadowString As String = "This is the base class string."  
    End Class  
    Public Class shadowDerivedClass  
        Inherits shadowBaseClass  
        Public Shadows shadowString As String = "This is the derived class string."  
        Public Sub showStrings()  
            Dim s As String = "Unqualified shadowString: " & shadowString &  
                 vbCrLf & "MyBase.shadowString: " & MyBase.shadowString  
            MsgBox(s)  
        End Sub  
    End Class  
    ```  
  
     <span data-ttu-id="685d1-139">前の例は、変数を宣言します`shadowString`基底クラスとその派生クラスでシャドウします。</span><span class="sxs-lookup"><span data-stu-id="685d1-139">The preceding example declares the variable `shadowString` in the base class and shadows it in the derived class.</span></span> <span data-ttu-id="685d1-140">プロシージャ`showStrings`派生クラスでは、シャドウのバージョンの文字列を表示します。 ときに、名前`shadowString`は修飾されません。</span><span class="sxs-lookup"><span data-stu-id="685d1-140">The procedure `showStrings` in the derived class displays the shadowing version of the string when the name `shadowString` is not qualified.</span></span> <span data-ttu-id="685d1-141">シャドウされたバージョンを次に、表示と`shadowString`で修飾されて、`MyBase`キーワード。</span><span class="sxs-lookup"><span data-stu-id="685d1-141">It then displays the shadowed version when `shadowString` is qualified with the `MyBase` keyword.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="685d1-142">信頼性の高いプログラミング</span><span class="sxs-lookup"><span data-stu-id="685d1-142">Robust Programming</span></span>  
 <span data-ttu-id="685d1-143">シャドウ処理には、1 つ以上のバージョンの同じ名前の変数が導入されています。</span><span class="sxs-lookup"><span data-stu-id="685d1-143">Shadowing introduces more than one version of a variable with the same name.</span></span> <span data-ttu-id="685d1-144">コード ステートメントは、変数名が参照されているときに、コンパイラの参照が解決されるバージョンは、コード ステートメントの場所と該当する文字列の存在などの要因によって異なります。</span><span class="sxs-lookup"><span data-stu-id="685d1-144">When a code statement refers to the variable name, the version to which the compiler resolves the reference depends on factors such as the location of the code statement and the presence of a qualifying string.</span></span> <span data-ttu-id="685d1-145">これにより、意図しないシャドウされた変数のバージョンを参照するリスクが増加することができます。</span><span class="sxs-lookup"><span data-stu-id="685d1-145">This can increase the risk of referring to an unintended version of a shadowed variable.</span></span> <span data-ttu-id="685d1-146">このリスクを低くには、シャドウされた変数へのすべての参照を完全に修飾します。</span><span class="sxs-lookup"><span data-stu-id="685d1-146">You can lower that risk by fully qualifying all references to a shadowed variable.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="685d1-147">関連項目</span><span class="sxs-lookup"><span data-stu-id="685d1-147">See also</span></span>

- [<span data-ttu-id="685d1-148">宣言された要素の参照</span><span class="sxs-lookup"><span data-stu-id="685d1-148">References to Declared Elements</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
- [<span data-ttu-id="685d1-149">Visual Basic におけるシャドウ</span><span class="sxs-lookup"><span data-stu-id="685d1-149">Shadowing in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
- [<span data-ttu-id="685d1-150">シャドウとオーバーライドの違い</span><span class="sxs-lookup"><span data-stu-id="685d1-150">Differences Between Shadowing and Overriding</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/differences-between-shadowing-and-overriding.md)
- [<span data-ttu-id="685d1-151">方法: 継承された変数を非表示にします。</span><span class="sxs-lookup"><span data-stu-id="685d1-151">How to: Hide an Inherited Variable</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-an-inherited-variable.md)
- [<span data-ttu-id="685d1-152">方法: 派生クラスによって非表示に変数にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="685d1-152">How to: Access a Variable Hidden by a Derived Class</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md)
- [<span data-ttu-id="685d1-153">Overrides</span><span class="sxs-lookup"><span data-stu-id="685d1-153">Overrides</span></span>](../../../../visual-basic/language-reference/modifiers/overrides.md)
- [<span data-ttu-id="685d1-154">Me、My、MyBase、および MyClass</span><span class="sxs-lookup"><span data-stu-id="685d1-154">Me, My, MyBase, and MyClass</span></span>](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
- [<span data-ttu-id="685d1-155">継承の基本</span><span class="sxs-lookup"><span data-stu-id="685d1-155">Inheritance Basics</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
