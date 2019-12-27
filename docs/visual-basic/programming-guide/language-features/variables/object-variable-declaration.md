---
title: オブジェクト変数の宣言
ms.date: 07/20/2015
helpviewer_keywords:
- early binding [Visual Basic]
- declarations [Visual Basic], class
- classes [Visual Basic], declaring
- binding [Visual Basic], late and early
- object variables [Visual Basic], declaring
- variables [Visual Basic], object
- declaring variables [Visual Basic], object variables
- declaring classes [Visual Basic]
- late binding [Visual Basic]
ms.assetid: 2a5a41a3-1aa8-4236-b1f0-2382af7bf715
ms.openlocfilehash: d1964e3768124dde1deeabfada9006ff5a59def0
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351812"
---
# <a name="object-variable-declaration-visual-basic"></a><span data-ttu-id="2f714-102">オブジェクト変数の宣言 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2f714-102">Object Variable Declaration (Visual Basic)</span></span>
<span data-ttu-id="2f714-103">通常の宣言ステートメントを使用して、オブジェクト変数を宣言します。</span><span class="sxs-lookup"><span data-stu-id="2f714-103">You use a normal declaration statement to declare an object variable.</span></span> <span data-ttu-id="2f714-104">データ型については、`Object` (つまり、[Object データ型](../../../../visual-basic/language-reference/data-types/object-data-type.md)) またはオブジェクトの作成元となるより具体的なクラスを指定します。</span><span class="sxs-lookup"><span data-stu-id="2f714-104">For the data type, you specify either `Object` (that is, the [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md)) or a more specific class from which the object is to be created.</span></span>  
  
 <span data-ttu-id="2f714-105">変数を `Object` として宣言することは、<xref:System.Object?displayProperty=nameWithType>として宣言することと同じです。</span><span class="sxs-lookup"><span data-stu-id="2f714-105">Declaring a variable as `Object` is the same as declaring it as <xref:System.Object?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="2f714-106">特定のオブジェクトクラスを使用して変数を宣言すると、そのクラスによって公開されているすべてのメソッドとプロパティ、およびそのクラスが継承するクラスにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="2f714-106">When you declare a variable with a specific object class, it can access all the methods and properties exposed by that class and the classes from which it inherits.</span></span> <span data-ttu-id="2f714-107"><xref:System.Object>を使用して変数を宣言すると、遅延バインディングを許可するように `Option Strict Off` 有効にしない限り、<xref:System.Object> クラスのメンバーにのみアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="2f714-107">If you declare the variable with <xref:System.Object>, it can access only the members of the <xref:System.Object> class, unless you turn `Option Strict Off` to allow late binding.</span></span>  
  
## <a name="declaration-syntax"></a><span data-ttu-id="2f714-108">宣言の構文</span><span class="sxs-lookup"><span data-stu-id="2f714-108">Declaration Syntax</span></span>  
 <span data-ttu-id="2f714-109">オブジェクト変数を宣言するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="2f714-109">Use the following syntax to declare an object variable:</span></span>  
  
```vb  
Dim variablename As [New] { objectclass | Object }  
```  
  
 <span data-ttu-id="2f714-110">宣言に [Public](../../../../visual-basic/language-reference/modifiers/public.md)、 [Protected](../../../../visual-basic/language-reference/modifiers/protected.md)、 [Friend](../../../../visual-basic/language-reference/modifiers/friend.md)、`Protected Friend`、 [Private](../../../../visual-basic/language-reference/modifiers/private.md)、 [Shared](../../../../visual-basic/language-reference/modifiers/shared.md)、または [Static](../../../../visual-basic/language-reference/modifiers/static.md)を指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="2f714-110">You can also specify [Public](../../../../visual-basic/language-reference/modifiers/public.md), [Protected](../../../../visual-basic/language-reference/modifiers/protected.md), [Friend](../../../../visual-basic/language-reference/modifiers/friend.md), `Protected Friend`, [Private](../../../../visual-basic/language-reference/modifiers/private.md), [Shared](../../../../visual-basic/language-reference/modifiers/shared.md), or [Static](../../../../visual-basic/language-reference/modifiers/static.md) in the declaration.</span></span> <span data-ttu-id="2f714-111">有効な宣言の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="2f714-111">The following example declarations are valid:</span></span>  
  
```vb  
Private objA As Object  
Static objB As System.Windows.Forms.Label  
Dim objC As System.OperatingSystem  
```  
  
## <a name="late-binding-and-early-binding"></a><span data-ttu-id="2f714-112">遅延バインディングと事前バインディング</span><span class="sxs-lookup"><span data-stu-id="2f714-112">Late Binding and Early Binding</span></span>  
 <span data-ttu-id="2f714-113">場合によっては、コードが実行されるまで特定のクラスが不明になることがあります。</span><span class="sxs-lookup"><span data-stu-id="2f714-113">Sometimes the specific class is unknown until your code runs.</span></span> <span data-ttu-id="2f714-114">この場合は、`Object` データ型を使用して、オブジェクト変数を宣言する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2f714-114">In this case, you must declare the object variable with the `Object` data type.</span></span> <span data-ttu-id="2f714-115">これにより、任意の型のオブジェクトへの一般的な参照が作成され、特定のクラスが実行時に割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="2f714-115">This creates a general reference to any type of object, and the specific class is assigned at run time.</span></span> <span data-ttu-id="2f714-116">これは、*遅延バインディング*と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="2f714-116">This is called *late binding*.</span></span> <span data-ttu-id="2f714-117">遅延バインディングでは、追加の実行時間が必要です。</span><span class="sxs-lookup"><span data-stu-id="2f714-117">Late binding requires additional execution time.</span></span> <span data-ttu-id="2f714-118">また、コードは、最後に割り当てられたクラスのメソッドとプロパティに限定されます。</span><span class="sxs-lookup"><span data-stu-id="2f714-118">It also limits your code to the methods and properties of the class you have most recently assigned to it.</span></span> <span data-ttu-id="2f714-119">これにより、コードが別のクラスのメンバーにアクセスしようとした場合に、実行時エラーが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="2f714-119">This can cause run-time errors if your code attempts to access members of a different class.</span></span>  
  
 <span data-ttu-id="2f714-120">コンパイル時に特定のクラスがわかっている場合は、そのクラスのオブジェクト変数を宣言する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2f714-120">When you know the specific class at compile time, you should declare the object variable to be of that class.</span></span> <span data-ttu-id="2f714-121">これは、*事前バインディング*と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="2f714-121">This is called *early binding*.</span></span> <span data-ttu-id="2f714-122">事前バインディングを使用すると、パフォーマンスが向上し、特定のクラスのすべてのメソッドとプロパティにコードからアクセスできるようになります。</span><span class="sxs-lookup"><span data-stu-id="2f714-122">Early binding improves performance and guarantees your code access to all the methods and properties of the specific class.</span></span> <span data-ttu-id="2f714-123">前の例の宣言では、変数 `objA` がクラス <xref:System.Windows.Forms.Label?displayProperty=nameWithType>のオブジェクトのみを使用する場合、その宣言に `As System.Windows.Forms.Label` を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2f714-123">In the preceding example declarations, if variable `objA` uses only objects of class <xref:System.Windows.Forms.Label?displayProperty=nameWithType>, you should specify `As System.Windows.Forms.Label` in its declaration.</span></span>  
  
### <a name="advantages-of-early-binding"></a><span data-ttu-id="2f714-124">事前バインディングの利点</span><span class="sxs-lookup"><span data-stu-id="2f714-124">Advantages of Early Binding</span></span>  
 <span data-ttu-id="2f714-125">オブジェクト変数を特定のクラスとして宣言すると、いくつかの利点があります。</span><span class="sxs-lookup"><span data-stu-id="2f714-125">Declaring an object variable as a specific class gives you several advantages:</span></span>  
  
- <span data-ttu-id="2f714-126">自動型チェック</span><span class="sxs-lookup"><span data-stu-id="2f714-126">Automatic type checking</span></span>  
  
- <span data-ttu-id="2f714-127">特定のクラスのすべてのメンバーへのアクセスが保証されます。</span><span class="sxs-lookup"><span data-stu-id="2f714-127">Guaranteed access to all members of the specific class</span></span>  
  
- <span data-ttu-id="2f714-128">コードエディターでの Microsoft IntelliSense のサポート</span><span class="sxs-lookup"><span data-stu-id="2f714-128">Microsoft IntelliSense support in the Code Editor</span></span>  
  
- <span data-ttu-id="2f714-129">コードの読みやすさの向上</span><span class="sxs-lookup"><span data-stu-id="2f714-129">Improved readability of your code</span></span>  
  
- <span data-ttu-id="2f714-130">コード内のエラーの数を減らす</span><span class="sxs-lookup"><span data-stu-id="2f714-130">Fewer errors in your code</span></span>  
  
- <span data-ttu-id="2f714-131">実行時ではなくコンパイル時に検出されたエラー</span><span class="sxs-lookup"><span data-stu-id="2f714-131">Errors caught at compile time rather than run time</span></span>  
  
- <span data-ttu-id="2f714-132">より高速なコード実行</span><span class="sxs-lookup"><span data-stu-id="2f714-132">Faster code execution</span></span>  
  
## <a name="access-to-object-variable-members"></a><span data-ttu-id="2f714-133">オブジェクト変数のメンバーへのアクセス</span><span class="sxs-lookup"><span data-stu-id="2f714-133">Access to Object Variable Members</span></span>  
 <span data-ttu-id="2f714-134">`Option Strict` が `On`されている場合、オブジェクト変数は、宣言したクラスのメソッドとプロパティにのみアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="2f714-134">When `Option Strict` is turned `On`, an object variable can access only the methods and properties of the class with which you declare it.</span></span> <span data-ttu-id="2f714-135">これを次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="2f714-135">The following example illustrates this.</span></span>  
  
```vb  
' Option statements must precede all other source file lines.  
Option Strict On  
' Imports statement must precede all declarations in the source file.  
Imports System.Windows.Forms  
Public Sub accessMembers()  
    Dim p As Object  
    Dim q As System.Windows.Forms.Label  
    p = New System.Windows.Forms.Label  
    q = New System.Windows.Forms.Label  
    Dim j, k As Integer  
    ' The following statement generates a compiler ERROR.  
    j = p.Left  
    ' The following statement retrieves the left edge of the label in pixels.  
    k = q.Left  
End Sub  
```  
  
 <span data-ttu-id="2f714-136">この例の場合、 `p` で使用できるのは <xref:System.Object> クラス自体のメンバーのみです。 `Left` プロパティは含まれません。</span><span class="sxs-lookup"><span data-stu-id="2f714-136">In this example, `p` can use only the members of the <xref:System.Object> class itself, which do not include the `Left` property.</span></span> <span data-ttu-id="2f714-137">一方、 `q` は、 <xref:System.Windows.Forms.Label>型として宣言されているため、 <xref:System.Windows.Forms.Label> 名前空間の <xref:System.Windows.Forms> クラスのすべてのメソッドとプロパティを使用できます。</span><span class="sxs-lookup"><span data-stu-id="2f714-137">On the other hand, `q` was declared to be of type <xref:System.Windows.Forms.Label>, so it can use all the methods and properties of the <xref:System.Windows.Forms.Label> class in the <xref:System.Windows.Forms> namespace.</span></span>  
  
## <a name="flexibility-of-object-variables"></a><span data-ttu-id="2f714-138">オブジェクト変数の柔軟性</span><span class="sxs-lookup"><span data-stu-id="2f714-138">Flexibility of Object Variables</span></span>  
 <span data-ttu-id="2f714-139">継承階層内のオブジェクトを操作する場合は、オブジェクト変数の宣言に使用するクラスを選択できます。</span><span class="sxs-lookup"><span data-stu-id="2f714-139">When working with objects in an inheritance hierarchy, you have a choice of which class to use for declaring your object variables.</span></span> <span data-ttu-id="2f714-140">この選択を行うには、オブジェクトの割り当ての柔軟性と、クラスのメンバーへのアクセスとのバランスを取る必要があります。</span><span class="sxs-lookup"><span data-stu-id="2f714-140">In making this choice, you must balance flexibility of object assignment against access to members of a class.</span></span> <span data-ttu-id="2f714-141">たとえば、<xref:System.Windows.Forms.Form?displayProperty=nameWithType> クラスにつながる継承階層を考えてみます。</span><span class="sxs-lookup"><span data-stu-id="2f714-141">For example, consider the inheritance hierarchy that leads to the <xref:System.Windows.Forms.Form?displayProperty=nameWithType> class:</span></span>  
  
 <xref:System.Object>  
  
 &nbsp;&nbsp;<xref:System.MarshalByRefObject>  
  
 &nbsp;&nbsp;&nbsp;&nbsp;<xref:System.ComponentModel.Component>  
  
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<xref:System.Windows.Forms.Control>  
  
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<xref:System.Windows.Forms.ScrollableControl>  
  
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<xref:System.Windows.Forms.ContainerControl>  
  
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<xref:System.Windows.Forms.Form>  
  
 <span data-ttu-id="2f714-142">たとえば、アプリケーションで `specialForm`というフォームクラスが定義されているとします。このクラスは、クラス <xref:System.Windows.Forms.Form>から継承されます。</span><span class="sxs-lookup"><span data-stu-id="2f714-142">Suppose your application defines a form class called `specialForm`, which inherits from class <xref:System.Windows.Forms.Form>.</span></span> <span data-ttu-id="2f714-143">次の例に示すように、特に `specialForm`を参照するオブジェクト変数を宣言できます。</span><span class="sxs-lookup"><span data-stu-id="2f714-143">You can declare an object variable that refers specifically to `specialForm`, as the following example shows.</span></span>  
  
```vb  
Public Class specialForm  
    Inherits System.Windows.Forms.Form  
    ' Insert code defining methods and properties of specialForm.  
End Class  
Dim nextForm As New specialForm  
```  
  
 <span data-ttu-id="2f714-144">前の例の宣言では、変数 `nextForm` を `specialForm`クラスのオブジェクトに限定していますが、`specialForm` のすべてのメソッドとプロパティを `nextForm`に使用できるだけでなく、`specialForm` が継承するすべてのクラスのすべてのメンバーも使用できます。</span><span class="sxs-lookup"><span data-stu-id="2f714-144">The declaration in the preceding example limits the variable `nextForm` to objects of class `specialForm`, but it also makes all the methods and properties of `specialForm` available to `nextForm`, as well as all the members of all the classes from which `specialForm` inherits.</span></span>  
  
 <span data-ttu-id="2f714-145">次の例に示すように <xref:System.Windows.Forms.Form>型として宣言することで、オブジェクト変数をより一般的なものにすることができます。</span><span class="sxs-lookup"><span data-stu-id="2f714-145">You can make an object variable more general by declaring it to be of type <xref:System.Windows.Forms.Form>, as the following example shows.</span></span>  
  
```vb  
Dim anyForm As System.Windows.Forms.Form  
```  
  
 <span data-ttu-id="2f714-146">前の例の宣言を使用すると、アプリケーションの任意のフォームを `anyForm`に割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="2f714-146">The declaration in the preceding example lets you assign any form in your application to `anyForm`.</span></span> <span data-ttu-id="2f714-147">ただし、`anyForm` はクラス <xref:System.Windows.Forms.Form>のすべてのメンバーにアクセスできますが、`specialForm`などの特定のフォームに対して定義されている追加のメソッドやプロパティを使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="2f714-147">However, although `anyForm` can access all the members of class <xref:System.Windows.Forms.Form>, it cannot use any of the additional methods or properties defined for specific forms such as `specialForm`.</span></span>  
  
 <span data-ttu-id="2f714-148">基底クラスのすべてのメンバーは派生クラスで使用できますが、派生クラスの追加メンバーを基底クラスで使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="2f714-148">All the members of a base class are available to derived classes, but the additional members of a derived class are unavailable to the base class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f714-149">参照</span><span class="sxs-lookup"><span data-stu-id="2f714-149">See also</span></span>

- [<span data-ttu-id="2f714-150">オブジェクト変数</span><span class="sxs-lookup"><span data-stu-id="2f714-150">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [<span data-ttu-id="2f714-151">オブジェクト変数の代入</span><span class="sxs-lookup"><span data-stu-id="2f714-151">Object Variable Assignment</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)
- [<span data-ttu-id="2f714-152">オブジェクト変数の値</span><span class="sxs-lookup"><span data-stu-id="2f714-152">Object Variable Values</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)
- [<span data-ttu-id="2f714-153">方法: オブジェクト変数を宣言し、その変数にオブジェクトを割り当てる Visual Basic</span><span class="sxs-lookup"><span data-stu-id="2f714-153">How to: Declare an Object Variable and Assign an Object to It in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/variables/how-to-declare-an-object-variable-and-assign-an-object-to-it.md)
- [<span data-ttu-id="2f714-154">方法: オブジェクトのメンバーにアクセスする</span><span class="sxs-lookup"><span data-stu-id="2f714-154">How to: Access Members of an Object</span></span>](../../../../visual-basic/programming-guide/language-features/variables/how-to-access-members-of-an-object.md)
- [<span data-ttu-id="2f714-155">New 演算子</span><span class="sxs-lookup"><span data-stu-id="2f714-155">New Operator</span></span>](../../../../visual-basic/language-reference/operators/new-operator.md)
- [<span data-ttu-id="2f714-156">Option Strict ステートメント</span><span class="sxs-lookup"><span data-stu-id="2f714-156">Option Strict Statement</span></span>](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
- [<span data-ttu-id="2f714-157">ローカル型の推論</span><span class="sxs-lookup"><span data-stu-id="2f714-157">Local Type Inference</span></span>](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
