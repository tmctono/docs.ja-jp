---
title: '方法: 自分で宣言した変数と同じ名前の変数を隠す'
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
ms.openlocfilehash: c1f4c2fbf339358be77e76468b1db94616bf04a2
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2020
ms.locfileid: "84357233"
---
# <a name="how-to-hide-a-variable-with-the-same-name-as-your-variable-visual-basic"></a><span data-ttu-id="89d36-102">方法: 自分で宣言した変数と同じ名前の変数を隠す (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="89d36-102">How to: Hide a Variable with the Same Name as Your Variable (Visual Basic)</span></span>

<span data-ttu-id="89d36-103">変数を隠すには、それを*シャドウ*します。つまり、同じ名前の変数でそれを再定義します。</span><span class="sxs-lookup"><span data-stu-id="89d36-103">You can hide a variable by *shadowing* it, that is, by redefining it with a variable of the same name.</span></span> <span data-ttu-id="89d36-104">隠す変数は、次の 2 つの方法でシャドウできます。</span><span class="sxs-lookup"><span data-stu-id="89d36-104">You can shadow the variable you want to hide in two ways:</span></span>

- <span data-ttu-id="89d36-105">**スコープによるシャドウ。**</span><span class="sxs-lookup"><span data-stu-id="89d36-105">**Shadowing Through Scope.**</span></span> <span data-ttu-id="89d36-106">スコープによってそれをシャドウするには、隠す変数が含まれている領域のサブ領域内でそれを再宣言します。</span><span class="sxs-lookup"><span data-stu-id="89d36-106">You can shadow it through scope by redeclaring it inside a subregion of the region containing the variable you want to hide.</span></span>

- <span data-ttu-id="89d36-107">**継承によるシャドウ。**</span><span class="sxs-lookup"><span data-stu-id="89d36-107">**Shadowing Through Inheritance.**</span></span> <span data-ttu-id="89d36-108">隠す変数がクラス レベルで定義されている場合は、派生クラスで [Shadows](../../../language-reference/modifiers/shadows.md) キーワードを使用してそれを再宣言することで、継承によってそれをシャドウできます。</span><span class="sxs-lookup"><span data-stu-id="89d36-108">If the variable you want to hide is defined at class level, you can shadow it through inheritance by redeclaring it with the [Shadows](../../../language-reference/modifiers/shadows.md) keyword in a derived class.</span></span>

## <a name="two-ways-to-hide-a-variable"></a><span data-ttu-id="89d36-109">変数を隠す 2 つの方法</span><span class="sxs-lookup"><span data-stu-id="89d36-109">Two Ways to Hide a Variable</span></span>

#### <a name="to-hide-a-variable-by-shadowing-it-through-scope"></a><span data-ttu-id="89d36-110">変数をスコープによってシャドウして隠すには</span><span class="sxs-lookup"><span data-stu-id="89d36-110">To hide a variable by shadowing it through scope</span></span>

1. <span data-ttu-id="89d36-111">隠す変数を定義している領域を特定し、独自の変数でそれを再定義するサブ領域を決定します。</span><span class="sxs-lookup"><span data-stu-id="89d36-111">Determine the region defining the variable you want to hide, and determine a subregion in which to redefine it with your variable.</span></span>

    |<span data-ttu-id="89d36-112">変数の領域</span><span class="sxs-lookup"><span data-stu-id="89d36-112">Variable's region</span></span>|<span data-ttu-id="89d36-113">その再定義に使用できるサブ領域</span><span class="sxs-lookup"><span data-stu-id="89d36-113">Allowable subregion for redefining it</span></span>|
    |-----------------------|-------------------------------------------|
    |<span data-ttu-id="89d36-114">Module</span><span class="sxs-lookup"><span data-stu-id="89d36-114">Module</span></span>|<span data-ttu-id="89d36-115">モジュール内のクラス</span><span class="sxs-lookup"><span data-stu-id="89d36-115">A class within the module</span></span>|
    |<span data-ttu-id="89d36-116">クラス</span><span class="sxs-lookup"><span data-stu-id="89d36-116">Class</span></span>|<span data-ttu-id="89d36-117">クラス内のサブクラス</span><span class="sxs-lookup"><span data-stu-id="89d36-117">A subclass within the class</span></span><br /><br /> <span data-ttu-id="89d36-118">クラス内のプロシージャ</span><span class="sxs-lookup"><span data-stu-id="89d36-118">A procedure within the class</span></span>|

    <span data-ttu-id="89d36-119">そのプロシージャ内のブロック (`If`...`End If` コンストラクションや `For` ループなど) でプロシージャ変数を再定義することはできません。</span><span class="sxs-lookup"><span data-stu-id="89d36-119">You cannot redefine a procedure variable in a block within that procedure, for example in an `If`...`End If` construction or a `For` loop.</span></span>

2. <span data-ttu-id="89d36-120">サブ領域がまだ存在しない場合は作成します。</span><span class="sxs-lookup"><span data-stu-id="89d36-120">Create the subregion if it does not already exist.</span></span>

3. <span data-ttu-id="89d36-121">サブ領域内で、シャドウ変数を宣言する [Dim ステートメント](../../../language-reference/statements/dim-statement.md)を記述します。</span><span class="sxs-lookup"><span data-stu-id="89d36-121">Within the subregion, write a [Dim Statement](../../../language-reference/statements/dim-statement.md) declaring the shadowing variable.</span></span>

    <span data-ttu-id="89d36-122">サブ領域内のコードで変数名を参照すると、コンパイラによって、シャドウしている変数への参照が解決されます。</span><span class="sxs-lookup"><span data-stu-id="89d36-122">When code inside the subregion refers to the variable name, the compiler resolves the reference to the shadowing variable.</span></span>

    <span data-ttu-id="89d36-123">次の例は、スコープによるシャドウに加えて、シャドウをバイパスする参照を示しています。</span><span class="sxs-lookup"><span data-stu-id="89d36-123">The following example illustrates shadowing through scope, as well as a reference that bypasses the shadowing.</span></span>

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

    <span data-ttu-id="89d36-124">前の例では、モジュール レベルとプロシージャ レベル (プロシージャ `show` 内) の両方で変数 `num` を宣言しています。</span><span class="sxs-lookup"><span data-stu-id="89d36-124">The preceding example declares the variable `num` both at module level and at procedure level (in the procedure `show`).</span></span> <span data-ttu-id="89d36-125">ローカル変数 `num` で、`show` 内のモジュールレベル変数 `num` をシャドウしているため、ローカル変数は 2 に設定されます。</span><span class="sxs-lookup"><span data-stu-id="89d36-125">The local variable `num` shadows the module-level variable `num` within `show`, so the local variable is set to 2.</span></span> <span data-ttu-id="89d36-126">ただし、`useModuleLevelNum` プロシージャの `num` をシャドウするローカル変数はありません。</span><span class="sxs-lookup"><span data-stu-id="89d36-126">However, there is no local variable to shadow `num` in the `useModuleLevelNum` procedure.</span></span> <span data-ttu-id="89d36-127">そのため、`useModuleLevelNum` では、モジュールレベル変数の値が 1 に設定されます。</span><span class="sxs-lookup"><span data-stu-id="89d36-127">Therefore, `useModuleLevelNum` sets the value of the module-level variable to 1.</span></span>

    <span data-ttu-id="89d36-128">`show` 内の `MsgBox` 呼び出しでは、モジュール名で `num` を修飾することによって、シャドウ メカニズムがバイパスされます。</span><span class="sxs-lookup"><span data-stu-id="89d36-128">The `MsgBox` call inside `show` bypasses the shadowing mechanism by qualifying `num` with the module name.</span></span> <span data-ttu-id="89d36-129">そのため、ローカル変数ではなくモジュールレベルの変数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="89d36-129">Therefore, it displays the module-level variable instead of the local variable.</span></span>

#### <a name="to-hide-a-variable-by-shadowing-it-through-inheritance"></a><span data-ttu-id="89d36-130">変数を継承によってシャドウして隠すには</span><span class="sxs-lookup"><span data-stu-id="89d36-130">To hide a variable by shadowing it through inheritance</span></span>

1. <span data-ttu-id="89d36-131">隠す変数がクラス内かつクラス レベル (プロシージャの外部) で宣言されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="89d36-131">Be sure the variable you want to hide is declared in a class, and at class level (outside any procedure).</span></span> <span data-ttu-id="89d36-132">それ以外の場合、継承によってそれをシャドウすることはできません。</span><span class="sxs-lookup"><span data-stu-id="89d36-132">Otherwise you cannot shadow it through inheritance.</span></span>

2. <span data-ttu-id="89d36-133">変数がまだ存在しない場合は、変数のクラスから派生したクラスを定義します。</span><span class="sxs-lookup"><span data-stu-id="89d36-133">Define a class derived from the variable's class if one does not already exist.</span></span>

3. <span data-ttu-id="89d36-134">派生クラス内で、変数を宣言する `Dim` ステートメントを記述します。</span><span class="sxs-lookup"><span data-stu-id="89d36-134">Inside the derived class, write a `Dim` statement declaring your variable.</span></span> <span data-ttu-id="89d36-135">宣言に [Shadows](../../../language-reference/modifiers/shadows.md) キーワードを含めます。</span><span class="sxs-lookup"><span data-stu-id="89d36-135">Include the [Shadows](../../../language-reference/modifiers/shadows.md) keyword in the declaration.</span></span>

    <span data-ttu-id="89d36-136">派生クラスのコードで変数名を参照すると、コンパイラによって、変数への参照が解決されます。</span><span class="sxs-lookup"><span data-stu-id="89d36-136">When code in the derived class refers to the variable name, the compiler resolves the reference to your variable.</span></span>

    <span data-ttu-id="89d36-137">次の例に、継承によるシャドウを示しています。</span><span class="sxs-lookup"><span data-stu-id="89d36-137">The following example illustrates shadowing through inheritance.</span></span> <span data-ttu-id="89d36-138">それによって、2 つの参照が作成されます。シャドウする変数にアクセスするものと、シャドウ処理をバイパスするものです。</span><span class="sxs-lookup"><span data-stu-id="89d36-138">It makes two references, one that accesses the shadowing variable and one that bypasses the shadowing.</span></span>

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

    <span data-ttu-id="89d36-139">前の例では、基底クラスで `shadowString` 変数を宣言し、派生クラスでそれをシャドウしています。</span><span class="sxs-lookup"><span data-stu-id="89d36-139">The preceding example declares the variable `shadowString` in the base class and shadows it in the derived class.</span></span> <span data-ttu-id="89d36-140">派生クラスのプロシージャ `showStrings` では、名前 `shadowString` が修飾されていない場合に、文字列のシャドウしているバージョンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="89d36-140">The procedure `showStrings` in the derived class displays the shadowing version of the string when the name `shadowString` is not qualified.</span></span> <span data-ttu-id="89d36-141">さらに、`shadowString` が `MyBase` キーワードで修飾されている場合は、シャドウされたバージョンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="89d36-141">It then displays the shadowed version when `shadowString` is qualified with the `MyBase` keyword.</span></span>

## <a name="robust-programming"></a><span data-ttu-id="89d36-142">信頼性の高いプログラミング</span><span class="sxs-lookup"><span data-stu-id="89d36-142">Robust Programming</span></span>

<span data-ttu-id="89d36-143">シャドウによって、同じ名前の変数の複数のバージョンが取り込まれます。</span><span class="sxs-lookup"><span data-stu-id="89d36-143">Shadowing introduces more than one version of a variable with the same name.</span></span> <span data-ttu-id="89d36-144">コード ステートメントで変数名を参照する場合、コンパイラによる参照の解決先のバージョンは、コード ステートメントの場所や修飾文字列の存在などの要因によって異なります。</span><span class="sxs-lookup"><span data-stu-id="89d36-144">When a code statement refers to the variable name, the version to which the compiler resolves the reference depends on factors such as the location of the code statement and the presence of a qualifying string.</span></span> <span data-ttu-id="89d36-145">これにより、シャドウされた変数の意図しないバージョンを参照するリスクが高まる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="89d36-145">This can increase the risk of referring to an unintended version of a shadowed variable.</span></span> <span data-ttu-id="89d36-146">シャドウされた変数へのすべての参照を完全に修飾することで、そのリスクを軽減することができます。</span><span class="sxs-lookup"><span data-stu-id="89d36-146">You can lower that risk by fully qualifying all references to a shadowed variable.</span></span>

## <a name="see-also"></a><span data-ttu-id="89d36-147">関連項目</span><span class="sxs-lookup"><span data-stu-id="89d36-147">See also</span></span>

- [<span data-ttu-id="89d36-148">宣言された要素の参照</span><span class="sxs-lookup"><span data-stu-id="89d36-148">References to Declared Elements</span></span>](references-to-declared-elements.md)
- [<span data-ttu-id="89d36-149">Visual Basic におけるシャドウ</span><span class="sxs-lookup"><span data-stu-id="89d36-149">Shadowing in Visual Basic</span></span>](shadowing.md)
- [<span data-ttu-id="89d36-150">シャドウとオーバーライドの違い</span><span class="sxs-lookup"><span data-stu-id="89d36-150">Differences Between Shadowing and Overriding</span></span>](differences-between-shadowing-and-overriding.md)
- [<span data-ttu-id="89d36-151">方法: 継承された変数を隠す</span><span class="sxs-lookup"><span data-stu-id="89d36-151">How to: Hide an Inherited Variable</span></span>](how-to-hide-an-inherited-variable.md)
- [<span data-ttu-id="89d36-152">方法: 派生クラスによって非表示になっている変数にアクセスする</span><span class="sxs-lookup"><span data-stu-id="89d36-152">How to: Access a Variable Hidden by a Derived Class</span></span>](how-to-access-a-variable-hidden-by-a-derived-class.md)
- [<span data-ttu-id="89d36-153">Overrides</span><span class="sxs-lookup"><span data-stu-id="89d36-153">Overrides</span></span>](../../../language-reference/modifiers/overrides.md)
- [<span data-ttu-id="89d36-154">Me、My、MyBase、および MyClass</span><span class="sxs-lookup"><span data-stu-id="89d36-154">Me, My, MyBase, and MyClass</span></span>](../../program-structure/me-my-mybase-and-myclass.md)
- [<span data-ttu-id="89d36-155">継承の基本</span><span class="sxs-lookup"><span data-stu-id="89d36-155">Inheritance Basics</span></span>](../objects-and-classes/inheritance-basics.md)
