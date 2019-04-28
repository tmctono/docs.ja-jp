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
ms.openlocfilehash: dff1b9bb9e87f827663786cac3f33531db41b2c1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61757067"
---
# <a name="object-variable-assignment-visual-basic"></a><span data-ttu-id="cb188-102">オブジェクト変数への代入 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="cb188-102">Object Variable Assignment (Visual Basic)</span></span>
<span data-ttu-id="cb188-103">オブジェクトをオブジェクト変数に代入するのにには、通常代入ステートメントを使用します。</span><span class="sxs-lookup"><span data-stu-id="cb188-103">You use a normal assignment statement to assign an object to an object variable.</span></span> <span data-ttu-id="cb188-104">オブジェクト式を割り当てることができます、または[Nothing](../../../../visual-basic/language-reference/nothing.md)キーワードでは、次の例として示します。</span><span class="sxs-lookup"><span data-stu-id="cb188-104">You can assign an object expression or the [Nothing](../../../../visual-basic/language-reference/nothing.md) keyword, as the following example illustrates.</span></span>  
  
```  
Dim thisObject As Object  
' The following statement assigns an object reference.  
thisObject = Form1  
' The following statement discontinues association with any object.  
thisObject = Nothing  
```  
  
 <span data-ttu-id="cb188-105">`Nothing` 変数に現在割り当てられているオブジェクトが存在しないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="cb188-105">`Nothing` means there is no object currently assigned to the variable.</span></span>  
  
## <a name="initialization"></a><span data-ttu-id="cb188-106">初期化</span><span class="sxs-lookup"><span data-stu-id="cb188-106">Initialization</span></span>  
 <span data-ttu-id="cb188-107">コードが実行されている変数に初期化されるオブジェクトが開始すると`Nothing`します。</span><span class="sxs-lookup"><span data-stu-id="cb188-107">When your code begins running, your object variables are initialized to `Nothing`.</span></span> <span data-ttu-id="cb188-108">宣言には初期化が含まれているが、宣言ステートメントの実行時に指定する値を再初期化されます。</span><span class="sxs-lookup"><span data-stu-id="cb188-108">Those whose declarations include initialization are reinitialized to the values you specify when the declaration statements are executed.</span></span>  
  
 <span data-ttu-id="cb188-109">使用して、宣言で初期化を含めることができます、[新規](../../../../visual-basic/language-reference/operators/new-operator.md)キーワード。</span><span class="sxs-lookup"><span data-stu-id="cb188-109">You can include initialization in your declaration by using the [New](../../../../visual-basic/language-reference/operators/new-operator.md) keyword.</span></span> <span data-ttu-id="cb188-110">次の宣言ステートメントは、オブジェクト変数を宣言`testUri`と`ver`し、特定のオブジェクトを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="cb188-110">The following declaration statements declare object variables `testUri` and `ver` and assign specific objects to them.</span></span> <span data-ttu-id="cb188-111">それぞれは、オブジェクトを初期化するために、適切なクラスのオーバー ロードされたコンス トラクターのいずれかを使用します。</span><span class="sxs-lookup"><span data-stu-id="cb188-111">Each uses one of the overloaded constructors of the appropriate class to initialize the object.</span></span>  
  
```  
Dim testUri As New System.Uri("https://www.microsoft.com")  
Dim ver As New System.Version(6, 1, 0)  
```  
  
## <a name="disassociation"></a><span data-ttu-id="cb188-112">関連付けの解除</span><span class="sxs-lookup"><span data-stu-id="cb188-112">Disassociation</span></span>  
 <span data-ttu-id="cb188-113">オブジェクト変数を設定`Nothing`と特定のオブジェクト変数の関連付けは失われます。</span><span class="sxs-lookup"><span data-stu-id="cb188-113">Setting an object variable to `Nothing` discontinues the association of the variable with any specific object.</span></span> <span data-ttu-id="cb188-114">こうと、誤って、変数を変更することで、オブジェクトを変更します。</span><span class="sxs-lookup"><span data-stu-id="cb188-114">This prevents you from accidentally changing the object by changing the variable.</span></span> <span data-ttu-id="cb188-115">オブジェクト変数は、次の例として有効なオブジェクトをポイントするかどうかをテストすることもできます。</span><span class="sxs-lookup"><span data-stu-id="cb188-115">It also allows you to test whether the object variable points to a valid object, as the following example shows.</span></span>  
  
```  
If otherObject IsNot Nothing Then  
    ' otherObject refers to a valid object, so your code can use it.  
End If  
```  
  
 <span data-ttu-id="cb188-116">変数が参照するオブジェクトが別のアプリケーションの場合は、このテストはそのアプリケーションが終了またはだけオブジェクトを無効にするかどうかを判断できません。</span><span class="sxs-lookup"><span data-stu-id="cb188-116">If the object your variable refers to is in another application, this test cannot determine whether that application has terminated or just invalidated the object.</span></span>  
  
 <span data-ttu-id="cb188-117">オブジェクト変数の値を持つ`Nothing`ともいいます、 *null 参照*します。</span><span class="sxs-lookup"><span data-stu-id="cb188-117">An object variable with a value of `Nothing` is also called a *null reference*.</span></span>  
  
## <a name="current-instance"></a><span data-ttu-id="cb188-118">現在のインスタンス</span><span class="sxs-lookup"><span data-stu-id="cb188-118">Current Instance</span></span>  
 <span data-ttu-id="cb188-119">*現在インスタンス*オブジェクトが現在のコードが実行されている 1 つ。</span><span class="sxs-lookup"><span data-stu-id="cb188-119">The *current instance* of an object is the one in which the code is currently executing.</span></span> <span data-ttu-id="cb188-120">プロシージャ内にある、すべてのコードの実行後、現在のインスタンスは、プロシージャが呼び出された 1 つが。</span><span class="sxs-lookup"><span data-stu-id="cb188-120">Since all code executes inside a procedure, the current instance is the one in which the procedure was invoked.</span></span>  
  
 <span data-ttu-id="cb188-121">`Me`キーワードは、現在のインスタンスを参照するオブジェクト変数として機能します。</span><span class="sxs-lookup"><span data-stu-id="cb188-121">The `Me` keyword acts as an object variable referring to the current instance.</span></span> <span data-ttu-id="cb188-122">プロシージャがない場合[Shared](../../../../visual-basic/language-reference/modifiers/shared.md)、使用できる、`Me`キーワードを現在のインスタンスへのポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="cb188-122">If a procedure is not [Shared](../../../../visual-basic/language-reference/modifiers/shared.md), it can use the `Me` keyword to obtain a pointer to the current instance.</span></span> <span data-ttu-id="cb188-123">共有プロシージャは、クラスの特定のインスタンスに関連付けすることはできません。</span><span class="sxs-lookup"><span data-stu-id="cb188-123">Shared procedures cannot be associated with a specific instance of a class.</span></span>  
  
 <span data-ttu-id="cb188-124">使用して`Me`は現在のインスタンスを別のモジュール内のプロシージャに渡すために特に便利です。</span><span class="sxs-lookup"><span data-stu-id="cb188-124">Using `Me` is particularly useful for passing the current instance to a procedure in another module.</span></span> <span data-ttu-id="cb188-125">たとえば、さまざまな XML ドキュメントがあり、それらすべてにいくつかの標準のテキストを追加することです。</span><span class="sxs-lookup"><span data-stu-id="cb188-125">For example, suppose you have a number of XML documents and wish to add some standard text to all of them.</span></span> <span data-ttu-id="cb188-126">次の例では、これを実行するプロシージャを定義します。</span><span class="sxs-lookup"><span data-stu-id="cb188-126">The following example defines a procedure to do this.</span></span>  
  
```  
Sub addStandardText(XmlDoc As System.Xml.XmlDocument)  
    XmlDoc.CreateTextNode("This text goes into every XML document.")  
End Sub  
```  
  
 <span data-ttu-id="cb188-127">すべての XML ドキュメント オブジェクトでしたし、プロシージャを呼び出すし、現在のインスタンスを引数として渡します。</span><span class="sxs-lookup"><span data-stu-id="cb188-127">Every XML document object could then call the procedure and pass its current instance as an argument.</span></span> <span data-ttu-id="cb188-128">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="cb188-128">The following example demonstrates this.</span></span>  
  
```  
addStandardText(Me)  
```  
  
## <a name="see-also"></a><span data-ttu-id="cb188-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="cb188-129">See also</span></span>

- [<span data-ttu-id="cb188-130">オブジェクト変数</span><span class="sxs-lookup"><span data-stu-id="cb188-130">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [<span data-ttu-id="cb188-131">オブジェクト変数の宣言</span><span class="sxs-lookup"><span data-stu-id="cb188-131">Object Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)
- [<span data-ttu-id="cb188-132">オブジェクト変数の値</span><span class="sxs-lookup"><span data-stu-id="cb188-132">Object Variable Values</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)
- [<span data-ttu-id="cb188-133">方法: オブジェクト変数を宣言し、Visual Basic でオブジェクトを割り当てる</span><span class="sxs-lookup"><span data-stu-id="cb188-133">How to: Declare an Object Variable and Assign an Object to It in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/variables/how-to-declare-an-object-variable-and-assign-an-object-to-it.md)
- [<span data-ttu-id="cb188-134">方法: オブジェクトが変数になる任意のインスタンスを参照していません</span><span class="sxs-lookup"><span data-stu-id="cb188-134">How to: Make an Object Variable Not Refer to Any Instance</span></span>](../../../../visual-basic/programming-guide/language-features/variables/how-to-make-an-object-variable-not-refer-to-any-instance.md)
- [<span data-ttu-id="cb188-135">Me、My、MyBase、および MyClass</span><span class="sxs-lookup"><span data-stu-id="cb188-135">Me, My, MyBase, and MyClass</span></span>](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
