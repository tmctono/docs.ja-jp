---
title: '方法 : 自分で宣言した変数と同じ名前の変数を隠す'
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
ms.openlocfilehash: 0915adbbabb778b1bdd3b6b30e56725a7e74867c
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345368"
---
# <a name="how-to-hide-a-variable-with-the-same-name-as-your-variable-visual-basic"></a><span data-ttu-id="eda9f-102">方法: 自分で宣言した変数と同じ名前の変数を隠す (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="eda9f-102">How to: Hide a Variable with the Same Name as Your Variable (Visual Basic)</span></span>

<span data-ttu-id="eda9f-103">変数を非表示にするには、その変数を同じ名前の変数で再定義することによって、その変数を*シャドウ*することができます。</span><span class="sxs-lookup"><span data-stu-id="eda9f-103">You can hide a variable by *shadowing* it, that is, by redefining it with a variable of the same name.</span></span> <span data-ttu-id="eda9f-104">非表示にする変数は、次の2つの方法でシャドウすることができます。</span><span class="sxs-lookup"><span data-stu-id="eda9f-104">You can shadow the variable you want to hide in two ways:</span></span>

- <span data-ttu-id="eda9f-105">**スコープによるシャドウ処理。**</span><span class="sxs-lookup"><span data-stu-id="eda9f-105">**Shadowing Through Scope.**</span></span> <span data-ttu-id="eda9f-106">スコープを通じてシャドウするには、非表示にする変数が含まれている領域のサブ領域内で再宣言します。</span><span class="sxs-lookup"><span data-stu-id="eda9f-106">You can shadow it through scope by redeclaring it inside a subregion of the region containing the variable you want to hide.</span></span>

- <span data-ttu-id="eda9f-107">**継承によるシャドウ処理。**</span><span class="sxs-lookup"><span data-stu-id="eda9f-107">**Shadowing Through Inheritance.**</span></span> <span data-ttu-id="eda9f-108">非表示にする変数がクラスレベルで定義されている場合は、派生クラスで[Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md)キーワードを使用して再宣言することで、継承によってシャドウできます。</span><span class="sxs-lookup"><span data-stu-id="eda9f-108">If the variable you want to hide is defined at class level, you can shadow it through inheritance by redeclaring it with the [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md) keyword in a derived class.</span></span>

## <a name="two-ways-to-hide-a-variable"></a><span data-ttu-id="eda9f-109">変数を非表示にする2つの方法</span><span class="sxs-lookup"><span data-stu-id="eda9f-109">Two Ways to Hide a Variable</span></span>

#### <a name="to-hide-a-variable-by-shadowing-it-through-scope"></a><span data-ttu-id="eda9f-110">スコープを使用して変数をシャドウすることによって変数を非表示にするには</span><span class="sxs-lookup"><span data-stu-id="eda9f-110">To hide a variable by shadowing it through scope</span></span>

1. <span data-ttu-id="eda9f-111">非表示にする変数を定義するリージョンを決定し、変数で再定義するサブ領域を決定します。</span><span class="sxs-lookup"><span data-stu-id="eda9f-111">Determine the region defining the variable you want to hide, and determine a subregion in which to redefine it with your variable.</span></span>

    |<span data-ttu-id="eda9f-112">変数の領域</span><span class="sxs-lookup"><span data-stu-id="eda9f-112">Variable's region</span></span>|<span data-ttu-id="eda9f-113">再定義に使用できるサブ領域</span><span class="sxs-lookup"><span data-stu-id="eda9f-113">Allowable subregion for redefining it</span></span>|
    |-----------------------|-------------------------------------------|
    |<span data-ttu-id="eda9f-114">モジュール</span><span class="sxs-lookup"><span data-stu-id="eda9f-114">Module</span></span>|<span data-ttu-id="eda9f-115">モジュール内のクラス</span><span class="sxs-lookup"><span data-stu-id="eda9f-115">A class within the module</span></span>|
    |<span data-ttu-id="eda9f-116">クラス</span><span class="sxs-lookup"><span data-stu-id="eda9f-116">Class</span></span>|<span data-ttu-id="eda9f-117">クラス内のサブクラスです。</span><span class="sxs-lookup"><span data-stu-id="eda9f-117">A subclass within the class</span></span><br /><br /> <span data-ttu-id="eda9f-118">クラス内のプロシージャ</span><span class="sxs-lookup"><span data-stu-id="eda9f-118">A procedure within the class</span></span>|

    <span data-ttu-id="eda9f-119">このプロシージャ内のブロックでプロシージャ変数を再定義することはできません。たとえば、`If`...`End If` コンストラクションや `For` ループなどです。</span><span class="sxs-lookup"><span data-stu-id="eda9f-119">You cannot redefine a procedure variable in a block within that procedure, for example in an `If`...`End If` construction or a `For` loop.</span></span>

2. <span data-ttu-id="eda9f-120">サブ領域がまだ存在しない場合は作成します。</span><span class="sxs-lookup"><span data-stu-id="eda9f-120">Create the subregion if it does not already exist.</span></span>

3. <span data-ttu-id="eda9f-121">サブ領域内で、シャドウする変数を宣言する[Dim ステートメント](../../../../visual-basic/language-reference/statements/dim-statement.md)を記述します。</span><span class="sxs-lookup"><span data-stu-id="eda9f-121">Within the subregion, write a [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md) declaring the shadowing variable.</span></span>

    <span data-ttu-id="eda9f-122">サブ領域内のコードが変数名を参照すると、コンパイラはシャドウしている変数への参照を解決します。</span><span class="sxs-lookup"><span data-stu-id="eda9f-122">When code inside the subregion refers to the variable name, the compiler resolves the reference to the shadowing variable.</span></span>

    <span data-ttu-id="eda9f-123">次の例は、スコープを使用したシャドウ処理と、シャドウをバイパスする参照を示しています。</span><span class="sxs-lookup"><span data-stu-id="eda9f-123">The following example illustrates shadowing through scope, as well as a reference that bypasses the shadowing.</span></span>

    ```vb
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

    <span data-ttu-id="eda9f-124">前の例では、モジュールレベルとプロシージャレベル (プロシージャ `show`) の両方で変数 `num` 宣言しています。</span><span class="sxs-lookup"><span data-stu-id="eda9f-124">The preceding example declares the variable `num` both at module level and at procedure level (in the procedure `show`).</span></span> <span data-ttu-id="eda9f-125">ローカル変数 `num`、`show`内のモジュールレベル変数 `num` をシャドウするため、ローカル変数は2に設定されます。</span><span class="sxs-lookup"><span data-stu-id="eda9f-125">The local variable `num` shadows the module-level variable `num` within `show`, so the local variable is set to 2.</span></span> <span data-ttu-id="eda9f-126">ただし、`useModuleLevelNum` の手順では、シャドウ `num` するローカル変数はありません。</span><span class="sxs-lookup"><span data-stu-id="eda9f-126">However, there is no local variable to shadow `num` in the `useModuleLevelNum` procedure.</span></span> <span data-ttu-id="eda9f-127">したがって、`useModuleLevelNum`、モジュールレベル変数の値を1に設定します。</span><span class="sxs-lookup"><span data-stu-id="eda9f-127">Therefore, `useModuleLevelNum` sets the value of the module-level variable to 1.</span></span>

    <span data-ttu-id="eda9f-128">`show` 内で `MsgBox` を呼び出すと、モジュール名を使用して `num` を修飾することにより、シャドウ機構がバイパスされます。</span><span class="sxs-lookup"><span data-stu-id="eda9f-128">The `MsgBox` call inside `show` bypasses the shadowing mechanism by qualifying `num` with the module name.</span></span> <span data-ttu-id="eda9f-129">そのため、ローカル変数の代わりにモジュールレベルの変数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="eda9f-129">Therefore, it displays the module-level variable instead of the local variable.</span></span>

#### <a name="to-hide-a-variable-by-shadowing-it-through-inheritance"></a><span data-ttu-id="eda9f-130">継承によって変数をシャドウして非表示にするには</span><span class="sxs-lookup"><span data-stu-id="eda9f-130">To hide a variable by shadowing it through inheritance</span></span>

1. <span data-ttu-id="eda9f-131">非表示にする変数がクラスで宣言されていること、およびクラスレベル (プロシージャの外側) で宣言されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="eda9f-131">Be sure the variable you want to hide is declared in a class, and at class level (outside any procedure).</span></span> <span data-ttu-id="eda9f-132">それ以外の場合、継承によってシャドウを行うことはできません。</span><span class="sxs-lookup"><span data-stu-id="eda9f-132">Otherwise you cannot shadow it through inheritance.</span></span>

2. <span data-ttu-id="eda9f-133">変数がまだ存在しない場合は、そのクラスから派生したクラスを定義します。</span><span class="sxs-lookup"><span data-stu-id="eda9f-133">Define a class derived from the variable's class if one does not already exist.</span></span>

3. <span data-ttu-id="eda9f-134">派生クラス内で、変数を宣言する `Dim` ステートメントを記述します。</span><span class="sxs-lookup"><span data-stu-id="eda9f-134">Inside the derived class, write a `Dim` statement declaring your variable.</span></span> <span data-ttu-id="eda9f-135">[Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md)キーワードを宣言に含めます。</span><span class="sxs-lookup"><span data-stu-id="eda9f-135">Include the [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md) keyword in the declaration.</span></span>

    <span data-ttu-id="eda9f-136">派生クラスのコードが変数名を参照すると、コンパイラは変数への参照を解決します。</span><span class="sxs-lookup"><span data-stu-id="eda9f-136">When code in the derived class refers to the variable name, the compiler resolves the reference to your variable.</span></span>

    <span data-ttu-id="eda9f-137">次の例は、継承によるシャドウ処理を示しています。</span><span class="sxs-lookup"><span data-stu-id="eda9f-137">The following example illustrates shadowing through inheritance.</span></span> <span data-ttu-id="eda9f-138">2つの参照が作成されます。1つはシャドウを行う変数にアクセスし、もう1つはシャドウ処理をバイパスします。</span><span class="sxs-lookup"><span data-stu-id="eda9f-138">It makes two references, one that accesses the shadowing variable and one that bypasses the shadowing.</span></span>

    ```vb
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

    <span data-ttu-id="eda9f-139">前の例では、基底クラスで `shadowString` 変数を宣言し、派生クラスでそれをシャドウしています。</span><span class="sxs-lookup"><span data-stu-id="eda9f-139">The preceding example declares the variable `shadowString` in the base class and shadows it in the derived class.</span></span> <span data-ttu-id="eda9f-140">派生クラスのプロシージャ `showStrings` は、名前 `shadowString` が修飾されていない場合に、文字列のシャドウバージョンを表示します。</span><span class="sxs-lookup"><span data-stu-id="eda9f-140">The procedure `showStrings` in the derived class displays the shadowing version of the string when the name `shadowString` is not qualified.</span></span> <span data-ttu-id="eda9f-141">`shadowString` が `MyBase` キーワードで修飾されている場合は、シャドウされたバージョンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="eda9f-141">It then displays the shadowed version when `shadowString` is qualified with the `MyBase` keyword.</span></span>

## <a name="robust-programming"></a><span data-ttu-id="eda9f-142">堅牢性の高いプログラミング</span><span class="sxs-lookup"><span data-stu-id="eda9f-142">Robust Programming</span></span>

<span data-ttu-id="eda9f-143">シャドウでは、同じ名前の変数の複数のバージョンが導入されます。</span><span class="sxs-lookup"><span data-stu-id="eda9f-143">Shadowing introduces more than one version of a variable with the same name.</span></span> <span data-ttu-id="eda9f-144">コードステートメントが変数名を参照する場合、コンパイラが参照を解決するバージョンは、コードステートメントの場所や修飾文字列の存在などの要因によって異なります。</span><span class="sxs-lookup"><span data-stu-id="eda9f-144">When a code statement refers to the variable name, the version to which the compiler resolves the reference depends on factors such as the location of the code statement and the presence of a qualifying string.</span></span> <span data-ttu-id="eda9f-145">これにより、シャドウされた変数の意図しないバージョンを参照するリスクが増加する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="eda9f-145">This can increase the risk of referring to an unintended version of a shadowed variable.</span></span> <span data-ttu-id="eda9f-146">シャドウされた変数へのすべての参照を完全に修飾することで、そのリスクを軽減することができます。</span><span class="sxs-lookup"><span data-stu-id="eda9f-146">You can lower that risk by fully qualifying all references to a shadowed variable.</span></span>

## <a name="see-also"></a><span data-ttu-id="eda9f-147">参照</span><span class="sxs-lookup"><span data-stu-id="eda9f-147">See also</span></span>

- [<span data-ttu-id="eda9f-148">宣言された要素の参照</span><span class="sxs-lookup"><span data-stu-id="eda9f-148">References to Declared Elements</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
- [<span data-ttu-id="eda9f-149">Visual Basic でのシャドウ処理</span><span class="sxs-lookup"><span data-stu-id="eda9f-149">Shadowing in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
- [<span data-ttu-id="eda9f-150">シャドウとオーバーライドの違い</span><span class="sxs-lookup"><span data-stu-id="eda9f-150">Differences Between Shadowing and Overriding</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/differences-between-shadowing-and-overriding.md)
- [<span data-ttu-id="eda9f-151">方法: 継承された変数を隠す</span><span class="sxs-lookup"><span data-stu-id="eda9f-151">How to: Hide an Inherited Variable</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-an-inherited-variable.md)
- [<span data-ttu-id="eda9f-152">方法: 派生クラスによって非表示になっている変数にアクセスする</span><span class="sxs-lookup"><span data-stu-id="eda9f-152">How to: Access a Variable Hidden by a Derived Class</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md)
- [<span data-ttu-id="eda9f-153">Overrides</span><span class="sxs-lookup"><span data-stu-id="eda9f-153">Overrides</span></span>](../../../../visual-basic/language-reference/modifiers/overrides.md)
- [<span data-ttu-id="eda9f-154">Me、My、MyBase、および MyClass</span><span class="sxs-lookup"><span data-stu-id="eda9f-154">Me, My, MyBase, and MyClass</span></span>](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
- [<span data-ttu-id="eda9f-155">継承の基本</span><span class="sxs-lookup"><span data-stu-id="eda9f-155">Inheritance Basics</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
