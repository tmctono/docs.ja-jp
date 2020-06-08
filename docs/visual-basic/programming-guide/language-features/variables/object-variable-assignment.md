---
title: オブジェクト変数の代入
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
ms.openlocfilehash: 9ae1a307e8c886166d516140b7f100a411cedcfa
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410375"
---
# <a name="object-variable-assignment-visual-basic"></a><span data-ttu-id="564bf-102">オブジェクト変数への代入 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="564bf-102">Object Variable Assignment (Visual Basic)</span></span>

<span data-ttu-id="564bf-103">オブジェクトにオブジェクト変数を代入するには、通常の代入ステートメントを使用します。</span><span class="sxs-lookup"><span data-stu-id="564bf-103">You use a normal assignment statement to assign an object to an object variable.</span></span> <span data-ttu-id="564bf-104">次の例で示すように、オブジェクト式または [Nothing](../../../language-reference/nothing.md) キーワードを代入することができます。</span><span class="sxs-lookup"><span data-stu-id="564bf-104">You can assign an object expression or the [Nothing](../../../language-reference/nothing.md) keyword, as the following example illustrates.</span></span>

```vb
Dim thisObject As Object
' The following statement assigns an object reference.
thisObject = Form1
' The following statement discontinues association with any object.
thisObject = Nothing
```

<span data-ttu-id="564bf-105">`Nothing` は、現在変数に代入されているオブジェクトがないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="564bf-105">`Nothing` means there is no object currently assigned to the variable.</span></span>

## <a name="initialization"></a><span data-ttu-id="564bf-106">初期化</span><span class="sxs-lookup"><span data-stu-id="564bf-106">Initialization</span></span>

<span data-ttu-id="564bf-107">コードの実行が開始されると、オブジェクト変数は、`Nothing` に初期化されます。</span><span class="sxs-lookup"><span data-stu-id="564bf-107">When your code begins running, your object variables are initialized to `Nothing`.</span></span> <span data-ttu-id="564bf-108">宣言に初期化を含むものは、宣言ステートメントの実行時に、指定された値に再初期化されます。</span><span class="sxs-lookup"><span data-stu-id="564bf-108">Those whose declarations include initialization are reinitialized to the values you specify when the declaration statements are executed.</span></span>

<span data-ttu-id="564bf-109">宣言に初期化を含めるには、[New](../../../language-reference/operators/new-operator.md) キーワードを使用します。</span><span class="sxs-lookup"><span data-stu-id="564bf-109">You can include initialization in your declaration by using the [New](../../../language-reference/operators/new-operator.md) keyword.</span></span> <span data-ttu-id="564bf-110">次の宣言ステートメントは、オブジェクト変数 `testUri` と `ver` を宣言し、それらに特定のオブジェクトを代入します。</span><span class="sxs-lookup"><span data-stu-id="564bf-110">The following declaration statements declare object variables `testUri` and `ver` and assign specific objects to them.</span></span> <span data-ttu-id="564bf-111">それぞれは、適切なクラスのオーバーロードされたコンストラクターのいずれかを使用して、オブジェクトを初期化します。</span><span class="sxs-lookup"><span data-stu-id="564bf-111">Each uses one of the overloaded constructors of the appropriate class to initialize the object.</span></span>

```vb
Dim testUri As New System.Uri("https://www.microsoft.com")
Dim ver As New System.Version(6, 1, 0)
```

## <a name="disassociation"></a><span data-ttu-id="564bf-112">関連付けの解除</span><span class="sxs-lookup"><span data-stu-id="564bf-112">Disassociation</span></span>

<span data-ttu-id="564bf-113">オブジェクト変数を `Nothing` に設定すると、変数と特定のオブジェクトの関連付けは解除されます。</span><span class="sxs-lookup"><span data-stu-id="564bf-113">Setting an object variable to `Nothing` discontinues the association of the variable with any specific object.</span></span> <span data-ttu-id="564bf-114">これにより、変数の変更によってオブジェクトが誤って変更されることがなくなります。</span><span class="sxs-lookup"><span data-stu-id="564bf-114">This prevents you from accidentally changing the object by changing the variable.</span></span> <span data-ttu-id="564bf-115">また、次の例で示すように、オブジェクト変数が有効なオブジェクトを指しているかどうかをテストすることもできます。</span><span class="sxs-lookup"><span data-stu-id="564bf-115">It also allows you to test whether the object variable points to a valid object, as the following example shows.</span></span>

```vb
If otherObject IsNot Nothing Then
    ' otherObject refers to a valid object, so your code can use it.
End If
```

<span data-ttu-id="564bf-116">変数が参照するオブジェクトが別のアプリケーション内にある場合、このテストでは、そのアプリケーションが終了したか、またはオブジェクトを無効にしただけであるかを判断することはできません。</span><span class="sxs-lookup"><span data-stu-id="564bf-116">If the object your variable refers to is in another application, this test cannot determine whether that application has terminated or just invalidated the object.</span></span>

<span data-ttu-id="564bf-117">値が `Nothing` に設定されたオブジェクト変数は、"*null 参照*" とも呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="564bf-117">An object variable with a value of `Nothing` is also called a *null reference*.</span></span>

## <a name="current-instance"></a><span data-ttu-id="564bf-118">現在のインスタンス</span><span class="sxs-lookup"><span data-stu-id="564bf-118">Current Instance</span></span>

<span data-ttu-id="564bf-119">オブジェクトの "*現在のインスタンス*" は、コードで現在実行されているインスタンスです。</span><span class="sxs-lookup"><span data-stu-id="564bf-119">The *current instance* of an object is the one in which the code is currently executing.</span></span> <span data-ttu-id="564bf-120">すべてのコードはプロシージャ内で実行されるため、現在のインスタンスは、プロシージャを呼び出したインスタンスです。</span><span class="sxs-lookup"><span data-stu-id="564bf-120">Since all code executes inside a procedure, the current instance is the one in which the procedure was invoked.</span></span>

<span data-ttu-id="564bf-121">`Me` キーワードは、現在のインスタンスを参照するオブジェクト変数として機能します。</span><span class="sxs-lookup"><span data-stu-id="564bf-121">The `Me` keyword acts as an object variable referring to the current instance.</span></span> <span data-ttu-id="564bf-122">プロシージャが [Shared](../../../language-reference/modifiers/shared.md) ではない場合、`Me` キーワードを使用して、現在のインスタンスへのポインターを取得できます。</span><span class="sxs-lookup"><span data-stu-id="564bf-122">If a procedure is not [Shared](../../../language-reference/modifiers/shared.md), it can use the `Me` keyword to obtain a pointer to the current instance.</span></span> <span data-ttu-id="564bf-123">Shared プロシージャを、クラスの特定のインスタンスに関連付けることはできません。</span><span class="sxs-lookup"><span data-stu-id="564bf-123">Shared procedures cannot be associated with a specific instance of a class.</span></span>

<span data-ttu-id="564bf-124">`Me` は、現在のインスタンスを別のモジュールのプロシージャに渡す場合に使用すると特に有用です。</span><span class="sxs-lookup"><span data-stu-id="564bf-124">Using `Me` is particularly useful for passing the current instance to a procedure in another module.</span></span> <span data-ttu-id="564bf-125">たとえば、複数の XML ドキュメントがあり、これらのすべてに何らかの標準テキストを追加したいとします。</span><span class="sxs-lookup"><span data-stu-id="564bf-125">For example, suppose you have a number of XML documents and wish to add some standard text to all of them.</span></span> <span data-ttu-id="564bf-126">次の例は、このためのプロシージャを定義します。</span><span class="sxs-lookup"><span data-stu-id="564bf-126">The following example defines a procedure to do this.</span></span>

```vb
Sub addStandardText(XmlDoc As System.Xml.XmlDocument)
    XmlDoc.CreateTextNode("This text goes into every XML document.")
End Sub
```

<span data-ttu-id="564bf-127">すべての XML ドキュメント オブジェクトは、このプロシージャを呼び出して、その現在のインスタンスを引数として渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="564bf-127">Every XML document object could then call the procedure and pass its current instance as an argument.</span></span> <span data-ttu-id="564bf-128">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="564bf-128">The following example demonstrates this.</span></span>

```vb
addStandardText(Me)
```

## <a name="see-also"></a><span data-ttu-id="564bf-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="564bf-129">See also</span></span>

- [<span data-ttu-id="564bf-130">オブジェクト変数</span><span class="sxs-lookup"><span data-stu-id="564bf-130">Object Variables</span></span>](object-variables.md)
- [<span data-ttu-id="564bf-131">オブジェクト変数の宣言</span><span class="sxs-lookup"><span data-stu-id="564bf-131">Object Variable Declaration</span></span>](object-variable-declaration.md)
- [<span data-ttu-id="564bf-132">オブジェクト変数の値</span><span class="sxs-lookup"><span data-stu-id="564bf-132">Object Variable Values</span></span>](object-variable-values.md)
- [<span data-ttu-id="564bf-133">方法: Visual Basic でオブジェクト変数を宣言してオブジェクトを代入する</span><span class="sxs-lookup"><span data-stu-id="564bf-133">How to: Declare an Object Variable and Assign an Object to It in Visual Basic</span></span>](how-to-declare-an-object-variable-and-assign-an-object-to-it.md)
- [<span data-ttu-id="564bf-134">方法: オブジェクト変数がインスタンスを参照しないようにする</span><span class="sxs-lookup"><span data-stu-id="564bf-134">How to: Make an Object Variable Not Refer to Any Instance</span></span>](how-to-make-an-object-variable-not-refer-to-any-instance.md)
- [<span data-ttu-id="564bf-135">Me、My、MyBase、および MyClass</span><span class="sxs-lookup"><span data-stu-id="564bf-135">Me, My, MyBase, and MyClass</span></span>](../../program-structure/me-my-mybase-and-myclass.md)
