---
title: '方法: 継承された変数を隠す'
ms.date: 07/20/2015
helpviewer_keywords:
- qualification [Visual Basic], of element names
- element names [Visual Basic], qualification
- references [Visual Basic], declared elements
- declaration statements [Visual Basic], declared elements
- referencing declared elements [Visual Basic]
- declared elements [Visual Basic], referencing
- declared elements [Visual Basic], about declared elements
- variables [Visual Basic], hiding inherited
ms.assetid: 765728d9-7351-4a30-999d-b5f34f024412
ms.openlocfilehash: f49bba0497f9f4f2774b01284c815bba9aaed119
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2020
ms.locfileid: "84357271"
---
# <a name="how-to-hide-an-inherited-variable-visual-basic"></a><span data-ttu-id="d0027-102">方法: 継承された変数を非表示にする (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d0027-102">How to: Hide an Inherited Variable (Visual Basic)</span></span>

<span data-ttu-id="d0027-103">派生クラスは、その基底クラスのすべての定義を継承します。</span><span class="sxs-lookup"><span data-stu-id="d0027-103">A derived class inherits all the definitions of its base class.</span></span> <span data-ttu-id="d0027-104">基底クラスの要素と同じ名前を使用して変数を定義する場合は、派生クラスで変数を定義するときに、その基底クラスの要素を非表示にする (*シャドウ*する) ことができます。</span><span class="sxs-lookup"><span data-stu-id="d0027-104">If you want to define a variable using the same name as an element of the base class, you can hide, or *shadow*, that base class element when you define your variable in the derived class.</span></span> <span data-ttu-id="d0027-105">これを行うと、シャドウのメカニズムを明示的にバイパスしない限り、派生クラスのコードは変数にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="d0027-105">If you do this, code in the derived class accesses your variable unless it explicitly bypasses the shadowing mechanism.</span></span>

<span data-ttu-id="d0027-106">継承された変数を非表示にするもう 1 つの理由は、基底クラスの改訂から保護するためです。</span><span class="sxs-lookup"><span data-stu-id="d0027-106">Another reason you might want to hide an inherited variable is to protect against base class revision.</span></span> <span data-ttu-id="d0027-107">基底クラスには、継承している要素を変える変更が加えられる場合があります。</span><span class="sxs-lookup"><span data-stu-id="d0027-107">The base class might undergo a change that alters the element you are inheriting.</span></span> <span data-ttu-id="d0027-108">この場合、`Shadows` 修飾子は、派生クラスからの参照が、基底クラス要素ではなく変数に強制的に解決されるようにします。</span><span class="sxs-lookup"><span data-stu-id="d0027-108">If this happens, the `Shadows` modifier forces references from the derived class to be resolved to your variable, instead of to the base class element.</span></span>

## <a name="to-hide-an-inherited-variable"></a><span data-ttu-id="d0027-109">継承された変数を非表示にするには</span><span class="sxs-lookup"><span data-stu-id="d0027-109">To hide an inherited variable</span></span>

1. <span data-ttu-id="d0027-110">非表示にする変数がクラス レベル (プロシージャの外側) で宣言されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="d0027-110">Be sure the variable you want to hide is declared at class level (outside any procedure).</span></span> <span data-ttu-id="d0027-111">そうでない場合、非表示にする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="d0027-111">Otherwise, you do not need to hide it.</span></span>
  
2. <span data-ttu-id="d0027-112">派生クラス内に、変数を宣言する [Dim ステートメント](../../../language-reference/statements/dim-statement.md)を記述します。</span><span class="sxs-lookup"><span data-stu-id="d0027-112">Inside your derived class, write a [Dim Statement](../../../language-reference/statements/dim-statement.md) declaring your variable.</span></span> <span data-ttu-id="d0027-113">継承された変数と同じ名前を使用します。</span><span class="sxs-lookup"><span data-stu-id="d0027-113">Use the same name as that of the inherited variable.</span></span>

3. <span data-ttu-id="d0027-114">宣言に [Shadows](../../../language-reference/modifiers/shadows.md) キーワードを含めます。</span><span class="sxs-lookup"><span data-stu-id="d0027-114">Include the [Shadows](../../../language-reference/modifiers/shadows.md) keyword in the declaration.</span></span>

     <span data-ttu-id="d0027-115">派生クラスのコードで変数名を参照すると、コンパイラによって、変数への参照が解決されます。</span><span class="sxs-lookup"><span data-stu-id="d0027-115">When code in the derived class refers to the variable name, the compiler resolves the reference to your variable.</span></span>

     <span data-ttu-id="d0027-116">次の例は、継承された変数のシャドウ処理を示しています。</span><span class="sxs-lookup"><span data-stu-id="d0027-116">The following example illustrates shadowing of an inherited variable:</span></span>
  
    ```vb  
    Public Class ShadowBaseClass  
        Public shadowString As String = "This is the base class string."  
    End Class  
    Public Class ShadowDerivedClass  
        Inherits ShadowBaseClass  
        Public Shadows shadowString As String = "This is the derived class string."  
        Public Sub ShowStrings()  
            Dim s As String = $"Unqualified shadowString: {shadowString}{vbCrLf}MyBase.shadowString: {MyBase.shadowString}"
            MsgBox(s)  
        End Sub  
    End Class  
    ```  
  
     <span data-ttu-id="d0027-117">前の例では、基底クラスで `shadowString` 変数を宣言し、派生クラスでそれをシャドウしています。</span><span class="sxs-lookup"><span data-stu-id="d0027-117">The preceding example declares the variable `shadowString` in the base class and shadows it in the derived class.</span></span> <span data-ttu-id="d0027-118">派生クラスのプロシージャ `ShowStrings` では、名前 `shadowString` が修飾されていない場合に、文字列のシャドウしているバージョンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d0027-118">The procedure `ShowStrings` in the derived class displays the shadowing version of the string when the name `shadowString` is not qualified.</span></span> <span data-ttu-id="d0027-119">さらに、`shadowString` が `MyBase` キーワードで修飾されている場合は、シャドウされたバージョンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d0027-119">It then displays the shadowed version when `shadowString` is qualified with the `MyBase` keyword.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="d0027-120">信頼性の高いプログラミング</span><span class="sxs-lookup"><span data-stu-id="d0027-120">Robust programming</span></span>

<span data-ttu-id="d0027-121">シャドウによって、同じ名前の変数の複数のバージョンが取り込まれます。</span><span class="sxs-lookup"><span data-stu-id="d0027-121">Shadowing introduces more than one version of a variable with the same name.</span></span> <span data-ttu-id="d0027-122">コード ステートメントで変数名を参照する場合、コンパイラによる参照の解決先のバージョンは、コード ステートメントの場所や修飾文字列の存在などの要因によって異なります。</span><span class="sxs-lookup"><span data-stu-id="d0027-122">When a code statement refers to the variable name, the version to which the compiler resolves the reference depends on factors such as the location of the code statement and the presence of a qualifying string.</span></span> <span data-ttu-id="d0027-123">これにより、シャドウされた変数の意図しないバージョンを参照するリスクが高まる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d0027-123">This can increase the risk of referring to an unintended version of a shadowed variable.</span></span> <span data-ttu-id="d0027-124">シャドウされた変数へのすべての参照を完全に修飾することで、そのリスクを軽減することができます。</span><span class="sxs-lookup"><span data-stu-id="d0027-124">You can lower that risk by fully qualifying all references to a shadowed variable.</span></span>

## <a name="see-also"></a><span data-ttu-id="d0027-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="d0027-125">See also</span></span>

- [<span data-ttu-id="d0027-126">宣言された要素の参照</span><span class="sxs-lookup"><span data-stu-id="d0027-126">References to Declared Elements</span></span>](references-to-declared-elements.md)
- [<span data-ttu-id="d0027-127">Visual Basic におけるシャドウ</span><span class="sxs-lookup"><span data-stu-id="d0027-127">Shadowing in Visual Basic</span></span>](shadowing.md)
- [<span data-ttu-id="d0027-128">シャドウとオーバーライドの違い</span><span class="sxs-lookup"><span data-stu-id="d0027-128">Differences Between Shadowing and Overriding</span></span>](differences-between-shadowing-and-overriding.md)
- [<span data-ttu-id="d0027-129">方法: 自分で宣言した変数と同じ名前の変数を非表示にする</span><span class="sxs-lookup"><span data-stu-id="d0027-129">How to: Hide a Variable with the Same Name as Your Variable</span></span>](how-to-hide-a-variable-with-the-same-name-as-your-variable.md)
- [<span data-ttu-id="d0027-130">方法: 派生クラスによって非表示になっている変数にアクセスする</span><span class="sxs-lookup"><span data-stu-id="d0027-130">How to: Access a Variable Hidden by a Derived Class</span></span>](how-to-access-a-variable-hidden-by-a-derived-class.md)
- [<span data-ttu-id="d0027-131">Overrides</span><span class="sxs-lookup"><span data-stu-id="d0027-131">Overrides</span></span>](../../../language-reference/modifiers/overrides.md)
- [<span data-ttu-id="d0027-132">Me、My、MyBase、および MyClass</span><span class="sxs-lookup"><span data-stu-id="d0027-132">Me, My, MyBase, and MyClass</span></span>](../../program-structure/me-my-mybase-and-myclass.md)
- [<span data-ttu-id="d0027-133">継承の基本</span><span class="sxs-lookup"><span data-stu-id="d0027-133">Inheritance Basics</span></span>](../objects-and-classes/inheritance-basics.md)
