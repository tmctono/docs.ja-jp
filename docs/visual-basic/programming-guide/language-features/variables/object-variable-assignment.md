---
title: オブジェクト変数への代入 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Nothing keyword [Visual Basic], object variable assignment
- object variables [Visual Basic], initializing
- variables [Visual Basic], initializing
- objects [Visual Basic], current instance
- object variables [Visual Basic], assigning
- variables [Visual Basic], object variables
- current instance [Visual Basic], defined
- variables [Visual Basic], assigning
- assignment statements [Visual Basic], object variable assignment
- Me keyword [Visual Basic], as object variable
ms.assetid: 3706811d-fd40-44fe-8727-d692e8e55d6d
ms.openlocfilehash: 59dea45511ba8d7d10c95cf17e47981124c532e4
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/30/2019
ms.locfileid: "68631054"
---
# <a name="object-variable-assignment-visual-basic"></a><span data-ttu-id="023d5-102">オブジェクト変数への代入 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="023d5-102">Object Variable Assignment (Visual Basic)</span></span>

<span data-ttu-id="023d5-103">オブジェクトをオブジェクト変数に割り当てるには、通常の代入ステートメントを使用します。</span><span class="sxs-lookup"><span data-stu-id="023d5-103">You use a normal assignment statement to assign an object to an object variable.</span></span> <span data-ttu-id="023d5-104">次の例に示すように、オブジェクト式または[Nothing](../../../../visual-basic/language-reference/nothing.md)キーワードを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="023d5-104">You can assign an object expression or the [Nothing](../../../../visual-basic/language-reference/nothing.md) keyword, as the following example illustrates.</span></span>

```vb
Dim thisObject As Object
' The following statement assigns an object reference.
thisObject = Form1
' The following statement discontinues association with any object.
thisObject = Nothing
```

<span data-ttu-id="023d5-105">`Nothing`は、変数に現在割り当てられているオブジェクトがないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="023d5-105">`Nothing` means there is no object currently assigned to the variable.</span></span>

## <a name="initialization"></a><span data-ttu-id="023d5-106">初期化</span><span class="sxs-lookup"><span data-stu-id="023d5-106">Initialization</span></span>

<span data-ttu-id="023d5-107">コードの実行が開始されると、オブジェクト変数は`Nothing`に初期化されます。</span><span class="sxs-lookup"><span data-stu-id="023d5-107">When your code begins running, your object variables are initialized to `Nothing`.</span></span> <span data-ttu-id="023d5-108">宣言を含む宣言がある場合は、宣言ステートメントの実行時に指定した値に再初期化されます。</span><span class="sxs-lookup"><span data-stu-id="023d5-108">Those whose declarations include initialization are reinitialized to the values you specify when the declaration statements are executed.</span></span>

<span data-ttu-id="023d5-109">[新しい](../../../../visual-basic/language-reference/operators/new-operator.md)キーワードを使用して、宣言に初期化を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="023d5-109">You can include initialization in your declaration by using the [New](../../../../visual-basic/language-reference/operators/new-operator.md) keyword.</span></span> <span data-ttu-id="023d5-110">次の宣言ステートメントは、オブジェクト`testUri`変数`ver`を宣言し、その変数に特定のオブジェクトを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="023d5-110">The following declaration statements declare object variables `testUri` and `ver` and assign specific objects to them.</span></span> <span data-ttu-id="023d5-111">各は、適切なクラスのオーバーロードされたコンストラクターの1つを使用してオブジェクトを初期化します。</span><span class="sxs-lookup"><span data-stu-id="023d5-111">Each uses one of the overloaded constructors of the appropriate class to initialize the object.</span></span>

```vb
Dim testUri As New System.Uri("https://www.microsoft.com")
Dim ver As New System.Version(6, 1, 0)
```

## <a name="disassociation"></a><span data-ttu-id="023d5-112">関連付け</span><span class="sxs-lookup"><span data-stu-id="023d5-112">Disassociation</span></span>

<span data-ttu-id="023d5-113">オブジェクト変数をに設定`Nothing`すると、変数と特定のオブジェクトとの関連付けが中断されます。</span><span class="sxs-lookup"><span data-stu-id="023d5-113">Setting an object variable to `Nothing` discontinues the association of the variable with any specific object.</span></span> <span data-ttu-id="023d5-114">これにより、変数を変更しても誤ってオブジェクトが変更されることがなくなります。</span><span class="sxs-lookup"><span data-stu-id="023d5-114">This prevents you from accidentally changing the object by changing the variable.</span></span> <span data-ttu-id="023d5-115">また、次の例に示すように、オブジェクト変数が有効なオブジェクトを指しているかどうかをテストすることもできます。</span><span class="sxs-lookup"><span data-stu-id="023d5-115">It also allows you to test whether the object variable points to a valid object, as the following example shows.</span></span>

```vb
If otherObject IsNot Nothing Then
    ' otherObject refers to a valid object, so your code can use it.
End If
```

<span data-ttu-id="023d5-116">変数が参照しているオブジェクトが別のアプリケーション内にある場合、このテストでは、そのアプリケーションが終了したか、またはオブジェクトを無効にしただけであるかどうかを判断できません。</span><span class="sxs-lookup"><span data-stu-id="023d5-116">If the object your variable refers to is in another application, this test cannot determine whether that application has terminated or just invalidated the object.</span></span>

<span data-ttu-id="023d5-117">値がの`Nothing`オブジェクト変数は、 *null 参照*とも呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="023d5-117">An object variable with a value of `Nothing` is also called a *null reference*.</span></span>

## <a name="current-instance"></a><span data-ttu-id="023d5-118">現在のインスタンス</span><span class="sxs-lookup"><span data-stu-id="023d5-118">Current Instance</span></span>

<span data-ttu-id="023d5-119">オブジェクトの*現在のインスタンス*は、コードが現在実行されているものです。</span><span class="sxs-lookup"><span data-stu-id="023d5-119">The *current instance* of an object is the one in which the code is currently executing.</span></span> <span data-ttu-id="023d5-120">すべてのコードはプロシージャ内で実行されるため、現在のインスタンスはプロシージャが呼び出されたものです。</span><span class="sxs-lookup"><span data-stu-id="023d5-120">Since all code executes inside a procedure, the current instance is the one in which the procedure was invoked.</span></span>

<span data-ttu-id="023d5-121">キーワード`Me`は、現在のインスタンスを参照するオブジェクト変数として機能します。</span><span class="sxs-lookup"><span data-stu-id="023d5-121">The `Me` keyword acts as an object variable referring to the current instance.</span></span> <span data-ttu-id="023d5-122">プロシージャが[共有](../../../../visual-basic/language-reference/modifiers/shared.md)されていない場合は、 `Me`キーワードを使用して、現在のインスタンスへのポインターを取得できます。</span><span class="sxs-lookup"><span data-stu-id="023d5-122">If a procedure is not [Shared](../../../../visual-basic/language-reference/modifiers/shared.md), it can use the `Me` keyword to obtain a pointer to the current instance.</span></span> <span data-ttu-id="023d5-123">共有プロシージャをクラスの特定のインスタンスに関連付けることはできません。</span><span class="sxs-lookup"><span data-stu-id="023d5-123">Shared procedures cannot be associated with a specific instance of a class.</span></span>

<span data-ttu-id="023d5-124">を`Me`使用すると、現在のインスタンスを別のモジュール内のプロシージャに渡す場合に特に便利です。</span><span class="sxs-lookup"><span data-stu-id="023d5-124">Using `Me` is particularly useful for passing the current instance to a procedure in another module.</span></span> <span data-ttu-id="023d5-125">たとえば、いくつかの XML ドキュメントがあり、それらすべてに標準テキストを追加したいとします。</span><span class="sxs-lookup"><span data-stu-id="023d5-125">For example, suppose you have a number of XML documents and wish to add some standard text to all of them.</span></span> <span data-ttu-id="023d5-126">次の例では、これを実行するプロシージャを定義します。</span><span class="sxs-lookup"><span data-stu-id="023d5-126">The following example defines a procedure to do this.</span></span>

```vb
Sub addStandardText(XmlDoc As System.Xml.XmlDocument)
    XmlDoc.CreateTextNode("This text goes into every XML document.")
End Sub
```

<span data-ttu-id="023d5-127">その後、すべての XML ドキュメントオブジェクトがプロシージャを呼び出し、その現在のインスタンスを引数として渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="023d5-127">Every XML document object could then call the procedure and pass its current instance as an argument.</span></span> <span data-ttu-id="023d5-128">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="023d5-128">The following example demonstrates this.</span></span>

```vb
addStandardText(Me)
```

## <a name="see-also"></a><span data-ttu-id="023d5-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="023d5-129">See also</span></span>

- [<span data-ttu-id="023d5-130">オブジェクト変数</span><span class="sxs-lookup"><span data-stu-id="023d5-130">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [<span data-ttu-id="023d5-131">オブジェクト変数の宣言</span><span class="sxs-lookup"><span data-stu-id="023d5-131">Object Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)
- [<span data-ttu-id="023d5-132">オブジェクト変数の値</span><span class="sxs-lookup"><span data-stu-id="023d5-132">Object Variable Values</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)
- [<span data-ttu-id="023d5-133">方法: オブジェクト変数を宣言し、その変数にオブジェクトを割り当てます Visual Basic</span><span class="sxs-lookup"><span data-stu-id="023d5-133">How to: Declare an Object Variable and Assign an Object to It in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/variables/how-to-declare-an-object-variable-and-assign-an-object-to-it.md)
- [<span data-ttu-id="023d5-134">方法: オブジェクト変数がインスタンスを参照しないようにする</span><span class="sxs-lookup"><span data-stu-id="023d5-134">How to: Make an Object Variable Not Refer to Any Instance</span></span>](../../../../visual-basic/programming-guide/language-features/variables/how-to-make-an-object-variable-not-refer-to-any-instance.md)
- [<span data-ttu-id="023d5-135">Me、My、MyBase、および MyClass</span><span class="sxs-lookup"><span data-stu-id="023d5-135">Me, My, MyBase, and MyClass</span></span>](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
