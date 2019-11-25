---
title: '方法: 派生クラスによって非表示になっている変数にアクセスする'
ms.date: 07/20/2015
helpviewer_keywords:
- qualification [Visual Basic], of element names
- base classes [Visual Basic], accessing elements
- element names [Visual Basic], qualification
- references [Visual Basic], declared elements
- declared elements [Visual Basic], referencing
- variables [Visual Basic], accessing hidden
ms.assetid: ae21a8ac-9cd4-4fba-a3ec-ecc4321ef93c
ms.openlocfilehash: 276cb1411c66e1f7205507a1b1053cc8642c7cb0
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345407"
---
# <a name="how-to-access-a-variable-hidden-by-a-derived-class-visual-basic"></a><span data-ttu-id="dcb62-102">方法: 派生クラスによって非表示になっている変数にアクセスする (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="dcb62-102">How to: Access a Variable Hidden by a Derived Class (Visual Basic)</span></span>

<span data-ttu-id="dcb62-103">When code in a derived class accesses a variable, the compiler normally resolves the reference to the closest accessible version, that is, the accessible version the fewest derivational steps backward from the accessing class.</span><span class="sxs-lookup"><span data-stu-id="dcb62-103">When code in a derived class accesses a variable, the compiler normally resolves the reference to the closest accessible version, that is, the accessible version the fewest derivational steps backward from the accessing class.</span></span> <span data-ttu-id="dcb62-104">If the variable is defined in the derived class, the code normally accesses that definition.</span><span class="sxs-lookup"><span data-stu-id="dcb62-104">If the variable is defined in the derived class, the code normally accesses that definition.</span></span>

<span data-ttu-id="dcb62-105">If the derived class variable shadows a variable in the base class, it hides the base class version.</span><span class="sxs-lookup"><span data-stu-id="dcb62-105">If the derived class variable shadows a variable in the base class, it hides the base class version.</span></span> <span data-ttu-id="dcb62-106">However, you can access the base class variable by qualifying it with the `MyBase` keyword.</span><span class="sxs-lookup"><span data-stu-id="dcb62-106">However, you can access the base class variable by qualifying it with the `MyBase` keyword.</span></span>

### <a name="to-access-a-base-class-variable-hidden-by-a-derived-class"></a><span data-ttu-id="dcb62-107">To access a base class variable hidden by a derived class</span><span class="sxs-lookup"><span data-stu-id="dcb62-107">To access a base class variable hidden by a derived class</span></span>

- <span data-ttu-id="dcb62-108">In an expression or assignment statement, precede the variable name with the `MyBase` keyword and a period (`.`).</span><span class="sxs-lookup"><span data-stu-id="dcb62-108">In an expression or assignment statement, precede the variable name with the `MyBase` keyword and a period (`.`).</span></span>

    <span data-ttu-id="dcb62-109">The compiler resolves the reference to the base class version of the variable.</span><span class="sxs-lookup"><span data-stu-id="dcb62-109">The compiler resolves the reference to the base class version of the variable.</span></span>

    <span data-ttu-id="dcb62-110">The following example illustrates shadowing through inheritance.</span><span class="sxs-lookup"><span data-stu-id="dcb62-110">The following example illustrates shadowing through inheritance.</span></span> <span data-ttu-id="dcb62-111">It makes two references, one that accesses the shadowing variable and one that bypasses the shadowing.</span><span class="sxs-lookup"><span data-stu-id="dcb62-111">It makes two references, one that accesses the shadowing variable and one that bypasses the shadowing.</span></span>

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

    <span data-ttu-id="dcb62-112">The preceding example declares the variable `shadowString` in the base class and shadows it in the derived class.</span><span class="sxs-lookup"><span data-stu-id="dcb62-112">The preceding example declares the variable `shadowString` in the base class and shadows it in the derived class.</span></span> <span data-ttu-id="dcb62-113">The procedure `showStrings` in the derived class displays the shadowing version of the string when the name `shadowString` is not qualified.</span><span class="sxs-lookup"><span data-stu-id="dcb62-113">The procedure `showStrings` in the derived class displays the shadowing version of the string when the name `shadowString` is not qualified.</span></span> <span data-ttu-id="dcb62-114">It then displays the shadowed version when `shadowString` is qualified with the `MyBase`  keyword.</span><span class="sxs-lookup"><span data-stu-id="dcb62-114">It then displays the shadowed version when `shadowString` is qualified with the `MyBase`  keyword.</span></span>

## <a name="robust-programming"></a><span data-ttu-id="dcb62-115">信頼性の高いプログラミング</span><span class="sxs-lookup"><span data-stu-id="dcb62-115">Robust Programming</span></span>

<span data-ttu-id="dcb62-116">To lower the risk of referring to an unintended version of a shadowed variable, you can fully qualify all references to a shadowed variable.</span><span class="sxs-lookup"><span data-stu-id="dcb62-116">To lower the risk of referring to an unintended version of a shadowed variable, you can fully qualify all references to a shadowed variable.</span></span> <span data-ttu-id="dcb62-117">Shadowing introduces more than one version of a variable with the same name.</span><span class="sxs-lookup"><span data-stu-id="dcb62-117">Shadowing introduces more than one version of a variable with the same name.</span></span> <span data-ttu-id="dcb62-118">When a code statement refers to the variable name, the version to which the compiler resolves the reference depends on factors such as the location of the code statement and the presence of a qualifying string.</span><span class="sxs-lookup"><span data-stu-id="dcb62-118">When a code statement refers to the variable name, the version to which the compiler resolves the reference depends on factors such as the location of the code statement and the presence of a qualifying string.</span></span> <span data-ttu-id="dcb62-119">This can increase the risk of referring to the wrong version of the variable.</span><span class="sxs-lookup"><span data-stu-id="dcb62-119">This can increase the risk of referring to the wrong version of the variable.</span></span>

## <a name="see-also"></a><span data-ttu-id="dcb62-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="dcb62-120">See also</span></span>

- [<span data-ttu-id="dcb62-121">宣言された要素の参照</span><span class="sxs-lookup"><span data-stu-id="dcb62-121">References to Declared Elements</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
- [<span data-ttu-id="dcb62-122">Shadowing in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="dcb62-122">Shadowing in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
- [<span data-ttu-id="dcb62-123">シャドウとオーバーライドの違い</span><span class="sxs-lookup"><span data-stu-id="dcb62-123">Differences Between Shadowing and Overriding</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/differences-between-shadowing-and-overriding.md)
- [<span data-ttu-id="dcb62-124">方法: 自分で宣言した変数と同じ名前の変数を隠す</span><span class="sxs-lookup"><span data-stu-id="dcb62-124">How to: Hide a Variable with the Same Name as Your Variable</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md)
- [<span data-ttu-id="dcb62-125">方法: 継承された変数を隠す</span><span class="sxs-lookup"><span data-stu-id="dcb62-125">How to: Hide an Inherited Variable</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-an-inherited-variable.md)
- [<span data-ttu-id="dcb62-126">Shadows</span><span class="sxs-lookup"><span data-stu-id="dcb62-126">Shadows</span></span>](../../../../visual-basic/language-reference/modifiers/shadows.md)
- [<span data-ttu-id="dcb62-127">Overrides</span><span class="sxs-lookup"><span data-stu-id="dcb62-127">Overrides</span></span>](../../../../visual-basic/language-reference/modifiers/overrides.md)
- [<span data-ttu-id="dcb62-128">Me、My、MyBase、および MyClass</span><span class="sxs-lookup"><span data-stu-id="dcb62-128">Me, My, MyBase, and MyClass</span></span>](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
- [<span data-ttu-id="dcb62-129">継承の基本</span><span class="sxs-lookup"><span data-stu-id="dcb62-129">Inheritance Basics</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
