---
title: オブジェクト変数の宣言 (Visual Basic)
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
ms.openlocfilehash: 9e57d49965537a45bc62b9078079389efcfb2e2c
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64598744"
---
# <a name="object-variable-declaration-visual-basic"></a><span data-ttu-id="40740-102">オブジェクト変数の宣言 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="40740-102">Object Variable Declaration (Visual Basic)</span></span>
<span data-ttu-id="40740-103">オブジェクト変数を宣言するのにには、通常の宣言ステートメントを使用します。</span><span class="sxs-lookup"><span data-stu-id="40740-103">You use a normal declaration statement to declare an object variable.</span></span> <span data-ttu-id="40740-104">どちらかのデータ型を指定する`Object`(つまり、[オブジェクト データ型](../../../../visual-basic/language-reference/data-types/object-data-type.md)) または固有のオブジェクトの作成元のクラス。</span><span class="sxs-lookup"><span data-stu-id="40740-104">For the data type, you specify either `Object` (that is, the [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md)) or a more specific class from which the object is to be created.</span></span>  
  
 <span data-ttu-id="40740-105">として変数を宣言する`Object`として宣言することと同じ<xref:System.Object?displayProperty=nameWithType>します。</span><span class="sxs-lookup"><span data-stu-id="40740-105">Declaring a variable as `Object` is the same as declaring it as <xref:System.Object?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="40740-106">特定のオブジェクト クラスを使用して変数を宣言するときに、すべてのメソッドとそのクラスと継承するクラスによって公開されるプロパティにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="40740-106">When you declare a variable with a specific object class, it can access all the methods and properties exposed by that class and the classes from which it inherits.</span></span> <span data-ttu-id="40740-107">使用して変数を宣言する場合<xref:System.Object>のメンバーだけにアクセスできる、<xref:System.Object>クラスにしない限り`Option Strict Off`遅延バインドできるようにします。</span><span class="sxs-lookup"><span data-stu-id="40740-107">If you declare the variable with <xref:System.Object>, it can access only the members of the <xref:System.Object> class, unless you turn `Option Strict Off` to allow late binding.</span></span>  
  
## <a name="declaration-syntax"></a><span data-ttu-id="40740-108">宣言の構文</span><span class="sxs-lookup"><span data-stu-id="40740-108">Declaration Syntax</span></span>  
 <span data-ttu-id="40740-109">オブジェクト変数を宣言するのにには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="40740-109">Use the following syntax to declare an object variable:</span></span>  
  
```vb  
Dim variablename As [New] { objectclass | Object }  
```  
  
 <span data-ttu-id="40740-110">指定することも[パブリック](../../../../visual-basic/language-reference/modifiers/public.md)、 [Protected](../../../../visual-basic/language-reference/modifiers/protected.md)、[フレンド](../../../../visual-basic/language-reference/modifiers/friend.md)、 `Protected Friend`、[プライベート](../../../../visual-basic/language-reference/modifiers/private.md)、 [Shared](../../../../visual-basic/language-reference/modifiers/shared.md)、または[静的](../../../../visual-basic/language-reference/modifiers/static.md)で宣言します。</span><span class="sxs-lookup"><span data-stu-id="40740-110">You can also specify [Public](../../../../visual-basic/language-reference/modifiers/public.md), [Protected](../../../../visual-basic/language-reference/modifiers/protected.md), [Friend](../../../../visual-basic/language-reference/modifiers/friend.md), `Protected Friend`, [Private](../../../../visual-basic/language-reference/modifiers/private.md), [Shared](../../../../visual-basic/language-reference/modifiers/shared.md), or [Static](../../../../visual-basic/language-reference/modifiers/static.md) in the declaration.</span></span> <span data-ttu-id="40740-111">次の例の宣言は有効です。</span><span class="sxs-lookup"><span data-stu-id="40740-111">The following example declarations are valid:</span></span>  
  
```vb  
Private objA As Object  
Static objB As System.Windows.Forms.Label  
Dim objC As System.OperatingSystem  
```  
  
## <a name="late-binding-and-early-binding"></a><span data-ttu-id="40740-112">遅延バインディングと、事前バインディング</span><span class="sxs-lookup"><span data-stu-id="40740-112">Late Binding and Early Binding</span></span>  
 <span data-ttu-id="40740-113">場合があります、特定のクラスが、コードが実行されるまで不明です。</span><span class="sxs-lookup"><span data-stu-id="40740-113">Sometimes the specific class is unknown until your code runs.</span></span> <span data-ttu-id="40740-114">この場合でオブジェクト変数を宣言する必要があります、`Object`データ型。</span><span class="sxs-lookup"><span data-stu-id="40740-114">In this case, you must declare the object variable with the `Object` data type.</span></span> <span data-ttu-id="40740-115">これは、オブジェクトの任意の型への参照を一般的なをで作成され、特定のクラスは、実行時に割り当てられています。</span><span class="sxs-lookup"><span data-stu-id="40740-115">This creates a general reference to any type of object, and the specific class is assigned at run time.</span></span> <span data-ttu-id="40740-116">これは呼び出されます*遅延バインディング*します。</span><span class="sxs-lookup"><span data-stu-id="40740-116">This is called *late binding*.</span></span> <span data-ttu-id="40740-117">遅延バインディングには、追加の実行時間が必要です。</span><span class="sxs-lookup"><span data-stu-id="40740-117">Late binding requires additional execution time.</span></span> <span data-ttu-id="40740-118">メソッドとそれに割り当てる最も最近クラスのプロパティに、コードも制限されます。</span><span class="sxs-lookup"><span data-stu-id="40740-118">It also limits your code to the methods and properties of the class you have most recently assigned to it.</span></span> <span data-ttu-id="40740-119">これにより、別のクラスのメンバーにアクセスしようとすると、コード実行時エラーが発生することができます。</span><span class="sxs-lookup"><span data-stu-id="40740-119">This can cause run-time errors if your code attempts to access members of a different class.</span></span>  
  
 <span data-ttu-id="40740-120">コンパイル時に特定のクラスを認識する場合は、そのクラスのオブジェクト変数を宣言する必要があります。</span><span class="sxs-lookup"><span data-stu-id="40740-120">When you know the specific class at compile time, you should declare the object variable to be of that class.</span></span> <span data-ttu-id="40740-121">これは、*事前バインディング*と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="40740-121">This is called *early binding*.</span></span> <span data-ttu-id="40740-122">事前バインディングでは、パフォーマンスが向上し、すべてのメソッドおよび特定のクラスのプロパティへのアクセスをコードが保証されます。</span><span class="sxs-lookup"><span data-stu-id="40740-122">Early binding improves performance and guarantees your code access to all the methods and properties of the specific class.</span></span> <span data-ttu-id="40740-123">変数の場合は前の例を宣言で`objA`クラスのオブジェクトのみを使用して<xref:System.Windows.Forms.Label?displayProperty=nameWithType>、指定する必要があります`As System.Windows.Forms.Label`で宣言します。</span><span class="sxs-lookup"><span data-stu-id="40740-123">In the preceding example declarations, if variable `objA` uses only objects of class <xref:System.Windows.Forms.Label?displayProperty=nameWithType>, you should specify `As System.Windows.Forms.Label` in its declaration.</span></span>  
  
### <a name="advantages-of-early-binding"></a><span data-ttu-id="40740-124">事前バインディングの利点</span><span class="sxs-lookup"><span data-stu-id="40740-124">Advantages of Early Binding</span></span>  
 <span data-ttu-id="40740-125">特定のクラスとしてオブジェクト変数を宣言するにはいくつかの利点。</span><span class="sxs-lookup"><span data-stu-id="40740-125">Declaring an object variable as a specific class gives you several advantages:</span></span>  
  
- <span data-ttu-id="40740-126">自動的な型チェック</span><span class="sxs-lookup"><span data-stu-id="40740-126">Automatic type checking</span></span>  
  
- <span data-ttu-id="40740-127">特定のクラスのすべてのメンバーへのアクセスを保証</span><span class="sxs-lookup"><span data-stu-id="40740-127">Guaranteed access to all members of the specific class</span></span>  
  
- <span data-ttu-id="40740-128">コード エディターで Microsoft IntelliSense サポート</span><span class="sxs-lookup"><span data-stu-id="40740-128">Microsoft IntelliSense support in the Code Editor</span></span>  
  
- <span data-ttu-id="40740-129">コードの読みやすくします。</span><span class="sxs-lookup"><span data-stu-id="40740-129">Improved readability of your code</span></span>  
  
- <span data-ttu-id="40740-130">コードのエラーの減少</span><span class="sxs-lookup"><span data-stu-id="40740-130">Fewer errors in your code</span></span>  
  
- <span data-ttu-id="40740-131">エラーが検出は、コンパイル時ではなく実行時間</span><span class="sxs-lookup"><span data-stu-id="40740-131">Errors caught at compile time rather than run time</span></span>  
  
- <span data-ttu-id="40740-132">コードの実行を高速化</span><span class="sxs-lookup"><span data-stu-id="40740-132">Faster code execution</span></span>  
  
## <a name="access-to-object-variable-members"></a><span data-ttu-id="40740-133">オブジェクト変数のメンバーへのアクセス</span><span class="sxs-lookup"><span data-stu-id="40740-133">Access to Object Variable Members</span></span>  
 <span data-ttu-id="40740-134">ときに`Option Strict`なって`On`メソッドとプロパティを宣言するクラスのオブジェクト変数にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="40740-134">When `Option Strict` is turned `On`, an object variable can access only the methods and properties of the class with which you declare it.</span></span> <span data-ttu-id="40740-135">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="40740-135">The following example illustrates this.</span></span>  
  
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
  
 <span data-ttu-id="40740-136">この例の場合、 `p` で使用できるのは <xref:System.Object> クラス自体のメンバーのみです。 `Left` プロパティは含まれません。</span><span class="sxs-lookup"><span data-stu-id="40740-136">In this example, `p` can use only the members of the <xref:System.Object> class itself, which do not include the `Left` property.</span></span> <span data-ttu-id="40740-137">一方、 `q` は、 <xref:System.Windows.Forms.Label>型として宣言されているため、 <xref:System.Windows.Forms.Label> 名前空間の <xref:System.Windows.Forms> クラスのすべてのメソッドとプロパティを使用できます。</span><span class="sxs-lookup"><span data-stu-id="40740-137">On the other hand, `q` was declared to be of type <xref:System.Windows.Forms.Label>, so it can use all the methods and properties of the <xref:System.Windows.Forms.Label> class in the <xref:System.Windows.Forms> namespace.</span></span>  
  
## <a name="flexibility-of-object-variables"></a><span data-ttu-id="40740-138">オブジェクト変数の柔軟性</span><span class="sxs-lookup"><span data-stu-id="40740-138">Flexibility of Object Variables</span></span>  
 <span data-ttu-id="40740-139">継承階層内のオブジェクトを操作するときに、オブジェクト変数を宣言するために使用するクラスの選択があります。</span><span class="sxs-lookup"><span data-stu-id="40740-139">When working with objects in an inheritance hierarchy, you have a choice of which class to use for declaring your object variables.</span></span> <span data-ttu-id="40740-140">クラスを選択するときに、クラスのメンバーへのアクセスに対してオブジェクトの割り当ての柔軟性のバランスを考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="40740-140">In making this choice, you must balance flexibility of object assignment against access to members of a class.</span></span> <span data-ttu-id="40740-141">たとえば、継承階層につながる、<xref:System.Windows.Forms.Form?displayProperty=nameWithType>クラス。</span><span class="sxs-lookup"><span data-stu-id="40740-141">For example, consider the inheritance hierarchy that leads to the <xref:System.Windows.Forms.Form?displayProperty=nameWithType> class:</span></span>  
  
 <xref:System.Object>  
  
 &nbsp;&nbsp;<xref:System.MarshalByRefObject>  
  
 &nbsp;&nbsp;&nbsp;&nbsp;<xref:System.ComponentModel.Component>  
  
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<xref:System.Windows.Forms.Control>  
  
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<xref:System.Windows.Forms.ScrollableControl>  
  
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<xref:System.Windows.Forms.ContainerControl>  
  
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<xref:System.Windows.Forms.Form>  
  
 <span data-ttu-id="40740-142">アプリケーションと呼ばれるフォーム クラスを定義するとします`specialForm`、クラスから継承される<xref:System.Windows.Forms.Form>します。</span><span class="sxs-lookup"><span data-stu-id="40740-142">Suppose your application defines a form class called `specialForm`, which inherits from class <xref:System.Windows.Forms.Form>.</span></span> <span data-ttu-id="40740-143">具体的を参照するオブジェクト変数を宣言する`specialForm`次の例に示すように、します。</span><span class="sxs-lookup"><span data-stu-id="40740-143">You can declare an object variable that refers specifically to `specialForm`, as the following example shows.</span></span>  
  
```vb  
Public Class specialForm  
    Inherits System.Windows.Forms.Form  
    ' Insert code defining methods and properties of specialForm.  
End Class  
Dim nextForm As New specialForm  
```  
  
 <span data-ttu-id="40740-144">前の例で、宣言の制限、変数`nextForm`クラスのオブジェクトに`specialForm`がすべてのメソッドとプロパティのも、`specialForm`できる`nextForm`元となるすべてのクラスのすべてのメンバーだけでなく、`specialForm`を継承します。</span><span class="sxs-lookup"><span data-stu-id="40740-144">The declaration in the preceding example limits the variable `nextForm` to objects of class `specialForm`, but it also makes all the methods and properties of `specialForm` available to `nextForm`, as well as all the members of all the classes from which `specialForm` inherits.</span></span>  
  
 <span data-ttu-id="40740-145">宣言する型にすることによりより一般的なオブジェクト変数を行うことができます<xref:System.Windows.Forms.Form>、次の例を示しています。</span><span class="sxs-lookup"><span data-stu-id="40740-145">You can make an object variable more general by declaring it to be of type <xref:System.Windows.Forms.Form>, as the following example shows.</span></span>  
  
```vb  
Dim anyForm As System.Windows.Forms.Form  
```  
  
 <span data-ttu-id="40740-146">上記の例では、宣言では、任意のフォームをアプリケーションを割り当てることができます`anyForm`します。</span><span class="sxs-lookup"><span data-stu-id="40740-146">The declaration in the preceding example lets you assign any form in your application to `anyForm`.</span></span> <span data-ttu-id="40740-147">ただしが`anyForm`クラスのすべてのメンバーにアクセスできる<xref:System.Windows.Forms.Form>、追加のメソッドやプロパティなど、特定の形式の定義のいずれかを使用できません`specialForm`します。</span><span class="sxs-lookup"><span data-stu-id="40740-147">However, although `anyForm` can access all the members of class <xref:System.Windows.Forms.Form>, it cannot use any of the additional methods or properties defined for specific forms such as `specialForm`.</span></span>  
  
 <span data-ttu-id="40740-148">基底クラスのすべてのメンバーは派生クラスで使用できますが、派生クラスの追加のメンバーは、基本クラスを使用できません。</span><span class="sxs-lookup"><span data-stu-id="40740-148">All the members of a base class are available to derived classes, but the additional members of a derived class are unavailable to the base class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40740-149">関連項目</span><span class="sxs-lookup"><span data-stu-id="40740-149">See also</span></span>

- [<span data-ttu-id="40740-150">オブジェクト変数</span><span class="sxs-lookup"><span data-stu-id="40740-150">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [<span data-ttu-id="40740-151">オブジェクト変数の代入</span><span class="sxs-lookup"><span data-stu-id="40740-151">Object Variable Assignment</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)
- [<span data-ttu-id="40740-152">オブジェクト変数の値</span><span class="sxs-lookup"><span data-stu-id="40740-152">Object Variable Values</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)
- [<span data-ttu-id="40740-153">方法: オブジェクト変数を宣言し、Visual Basic でオブジェクトを割り当てる</span><span class="sxs-lookup"><span data-stu-id="40740-153">How to: Declare an Object Variable and Assign an Object to It in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/variables/how-to-declare-an-object-variable-and-assign-an-object-to-it.md)
- [<span data-ttu-id="40740-154">方法: オブジェクトのメンバーへのアクセス</span><span class="sxs-lookup"><span data-stu-id="40740-154">How to: Access Members of an Object</span></span>](../../../../visual-basic/programming-guide/language-features/variables/how-to-access-members-of-an-object.md)
- [<span data-ttu-id="40740-155">New 演算子</span><span class="sxs-lookup"><span data-stu-id="40740-155">New Operator</span></span>](../../../../visual-basic/language-reference/operators/new-operator.md)
- [<span data-ttu-id="40740-156">Option Strict ステートメント</span><span class="sxs-lookup"><span data-stu-id="40740-156">Option Strict Statement</span></span>](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
- [<span data-ttu-id="40740-157">ローカル型の推論</span><span class="sxs-lookup"><span data-stu-id="40740-157">Local Type Inference</span></span>](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
