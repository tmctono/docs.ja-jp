---
title: 文字列名によるプロパティまたはメソッドの呼び出し (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- passing operators [Visual Basic]
- strings [Visual Basic], passing new operators as
- objects [Visual Basic], setting properties
- setting properties, object properties at run time
- method calls [Visual Basic], strings
- methods [Visual Basic], calling with string names
- calling methods [Visual Basic], string names
- properties [Visual Basic], setting at run time
- CallByName function
ms.assetid: 79a7b8b4-b8c7-4ad8-aca8-12a9a2b32f03
ms.openlocfilehash: 0683047865f520a09b2d2fe196096286b7d78714
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69965398"
---
# <a name="calling-a-property-or-method-using-a-string-name-visual-basic"></a><span data-ttu-id="32be8-102">文字列名によるプロパティまたはメソッドの呼び出し (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="32be8-102">Calling a Property or Method Using a String Name (Visual Basic)</span></span>
<span data-ttu-id="32be8-103">ほとんどの場合、オブジェクトのプロパティとメソッドをデザイン時に検出し、それらを処理するコードを記述できます。</span><span class="sxs-lookup"><span data-stu-id="32be8-103">In most cases, you can discover the properties and methods of an object at design time, and write code to handle them.</span></span> <span data-ttu-id="32be8-104">ただし、場合によっては、オブジェクトのプロパティやメソッドを事前に把握していない場合や、エンドユーザーが実行時にプロパティを指定したりメソッドを実行したりできるようにすることが必要になる場合もあります。</span><span class="sxs-lookup"><span data-stu-id="32be8-104">However, in some cases you may not know about an object's properties and methods in advance, or you may just want the flexibility of enabling an end user to specify properties or execute methods at run time.</span></span>  
  
## <a name="callbyname-function"></a><span data-ttu-id="32be8-105">CallByName 関数</span><span class="sxs-lookup"><span data-stu-id="32be8-105">CallByName Function</span></span>  
 <span data-ttu-id="32be8-106">たとえば、演算子を COM コンポーネントに渡すことによってユーザーによって入力された式を評価するクライアントアプリケーションなどを考えてみます。</span><span class="sxs-lookup"><span data-stu-id="32be8-106">Consider, for example, a client application that evaluates expressions entered by the user by passing an operator to a COM component.</span></span> <span data-ttu-id="32be8-107">新しい演算子を必要とする新しい関数をコンポーネントに常に追加するとします。</span><span class="sxs-lookup"><span data-stu-id="32be8-107">Suppose you are constantly adding new functions to the component that require new operators.</span></span> <span data-ttu-id="32be8-108">標準のオブジェクトアクセス手法を使用する場合は、新しい演算子を使用する前に、クライアントアプリケーションを再コンパイルして再配布する必要があります。</span><span class="sxs-lookup"><span data-stu-id="32be8-108">When you use standard object access techniques, you must recompile and redistribute the client application before it could use the new operators.</span></span> <span data-ttu-id="32be8-109">これを回避するには、 `CallByName`関数を使用して、アプリケーションを変更せずに、新しい演算子を文字列として渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="32be8-109">To avoid this, you can use the `CallByName` function to pass the new operators as strings, without changing the application.</span></span>  
  
 <span data-ttu-id="32be8-110">関数`CallByName`を使用すると、実行時に文字列を使用してプロパティまたはメソッドを指定できます。</span><span class="sxs-lookup"><span data-stu-id="32be8-110">The `CallByName` function lets you use a string to specify a property or method at run time.</span></span> <span data-ttu-id="32be8-111">`CallByName`関数のシグネチャは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="32be8-111">The signature for the `CallByName` function looks like this:</span></span>  
  
 <span data-ttu-id="32be8-112">*Result*(Object、ProcedureName、CallType、Arguments ()) = `CallByName`</span><span class="sxs-lookup"><span data-stu-id="32be8-112">*Result* = `CallByName`(*Object*, *ProcedureName*, *CallType*, *Arguments*())</span></span>  
  
 <span data-ttu-id="32be8-113">最初の引数*object*は、操作対象のオブジェクトの名前を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="32be8-113">The first argument, *Object*, takes the name of the object you want to act upon.</span></span> <span data-ttu-id="32be8-114">*ProcedureName*引数は、呼び出されるメソッドまたはプロパティプロシージャの名前を含む文字列を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="32be8-114">The *ProcedureName* argument takes a string that contains the name of the method or property procedure to be invoked.</span></span> <span data-ttu-id="32be8-115">*CallType*引数は、呼び出すプロシージャの種類を表す定数を受け取ります。メソッド (`Microsoft.VisualBasic.CallType.Method`)、読み取りプロパティ (`Microsoft.VisualBasic.CallType.Get`)、またはプロパティセット (`Microsoft.VisualBasic.CallType.Set`) です。</span><span class="sxs-lookup"><span data-stu-id="32be8-115">The *CallType* argument takes a constant that represents the type of procedure to invoke: a method (`Microsoft.VisualBasic.CallType.Method`), a property read (`Microsoft.VisualBasic.CallType.Get`), or a property set (`Microsoft.VisualBasic.CallType.Set`).</span></span> <span data-ttu-id="32be8-116">*Arguments*引数 (省略可能) は、プロシージャへの任意の`Object`引数を含む型の配列を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="32be8-116">The *Arguments* argument, which is optional, takes an array of type `Object` that contains any arguments to the procedure.</span></span>  
  
 <span data-ttu-id="32be8-117">は、現在`CallByName`のソリューションでクラスと共に使用できますが、ほとんどの場合、.NET Framework アセンブリから COM オブジェクトまたはオブジェクトにアクセスするために使用されます。</span><span class="sxs-lookup"><span data-stu-id="32be8-117">You can use `CallByName` with classes in your current solution, but it is most often used to access COM objects or objects from .NET Framework assemblies.</span></span>  
  
 <span data-ttu-id="32be8-118">次のコードに示すように`MathClass` `SquareRoot`、という名前の新しい関数を持つという名前のクラスを含むアセンブリへの参照を追加するとします。</span><span class="sxs-lookup"><span data-stu-id="32be8-118">Suppose you add a reference to an assembly that contains a class named `MathClass`, which has a new function named `SquareRoot`, as shown in the following code:</span></span>  
  
 [!code-vb[VbVbalrOOP#53](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#53)]  
  
 <span data-ttu-id="32be8-119">アプリケーションでは、テキストボックスコントロールを使用して、呼び出すメソッドとその引数を制御できます。</span><span class="sxs-lookup"><span data-stu-id="32be8-119">Your application could use text box controls to control which method will be called and its arguments.</span></span> <span data-ttu-id="32be8-120">たとえば、に評価`TextBox1` `TextBox2`される式が含まれていて、を使用して関数の名前を入力する場合、 `SquareRoot`次のコードを使用しての`TextBox1`式で関数を呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="32be8-120">For example, if `TextBox1` contains the expression to be evaluated, and `TextBox2` is used to enter the name of the function, you can use the following code to invoke the `SquareRoot` function on the expression in `TextBox1`:</span></span>  
  
 [!code-vb[VbVbalrOOP#54](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#54)]  
  
 <span data-ttu-id="32be8-121">に`TextBox1`"64" を入力し、で`TextBox2`"SquareRoot" を指定した後`CallMath` 、プロシージャを呼び出すと、内`TextBox1`の数値の平方根が評価されます。</span><span class="sxs-lookup"><span data-stu-id="32be8-121">If you enter "64" in `TextBox1`, "SquareRoot" in `TextBox2`, and then call the `CallMath` procedure, the square root of the number in `TextBox1` is evaluated.</span></span> <span data-ttu-id="32be8-122">この例のコードでは、 `SquareRoot`関数 (必須の引数として評価される式を含む文字列を受け取ります) を呼び出し、で`TextBox1` "8" を返します (64 の平方根)。</span><span class="sxs-lookup"><span data-stu-id="32be8-122">The code in the example invokes the `SquareRoot` function (which takes a string that contains the expression to be evaluated as a required argument) and returns "8" in `TextBox1` (the square root of 64).</span></span> <span data-ttu-id="32be8-123">もちろん、ユーザーがで`TextBox2`無効な文字列を入力した場合、文字列にメソッドではなくプロパティの名前が含まれている場合、またはメソッドに追加の必須引数がある場合は、実行時エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="32be8-123">Of course, if the user enters an invalid string in `TextBox2`, if the string contains the name of a property instead of a method, or if the method had an additional required argument, a run-time error occurs.</span></span> <span data-ttu-id="32be8-124">を使用`CallByName`してこれらのエラーやその他のエラーを予測する場合は、堅牢なエラー処理コードを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="32be8-124">You have to add robust error-handling code when you use `CallByName` to anticipate these or any other errors.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="32be8-125">関数は`CallByName` 、状況によっては役に立つ場合がありますが、パフォーマンスへの影響`CallByName`に対してその有用性を比較する必要があります。を使用してプロシージャを呼び出すと、遅延バインディング呼び出しよりも少し遅くなります。</span><span class="sxs-lookup"><span data-stu-id="32be8-125">While the `CallByName` function may be useful in some cases, you must weigh its usefulness against the performance implications — using `CallByName` to invoke a procedure is slightly slower than a late-bound call.</span></span> <span data-ttu-id="32be8-126">ループの内部など、繰り返し呼び出される関数を呼び出す場合、 `CallByName`パフォーマンスに重大な影響を与える可能性があります。</span><span class="sxs-lookup"><span data-stu-id="32be8-126">If you are invoking a function that is called repeatedly, such as inside a loop, `CallByName` can have a severe effect on performance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32be8-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="32be8-127">See also</span></span>

- <xref:Microsoft.VisualBasic.Interaction.CallByName%2A>
- [<span data-ttu-id="32be8-128">オブジェクトの型の決定</span><span class="sxs-lookup"><span data-stu-id="32be8-128">Determining Object Type</span></span>](../../../../visual-basic/programming-guide/language-features/early-late-binding/determining-object-type.md)
