---
title: 文字列名によるプロパティまたはメソッドの呼び出し
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
ms.openlocfilehash: cb584f0dfbd905ca071f9a86b1eab231f3017538
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345209"
---
# <a name="calling-a-property-or-method-using-a-string-name-visual-basic"></a><span data-ttu-id="37154-102">文字列名によるプロパティまたはメソッドの呼び出し (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="37154-102">Calling a Property or Method Using a String Name (Visual Basic)</span></span>
<span data-ttu-id="37154-103">ほとんどの場合、オブジェクトのプロパティとメソッドをデザイン時に検出し、それらを処理するコードを記述できます。</span><span class="sxs-lookup"><span data-stu-id="37154-103">In most cases, you can discover the properties and methods of an object at design time, and write code to handle them.</span></span> <span data-ttu-id="37154-104">ただし、場合によっては、オブジェクトのプロパティやメソッドを事前に把握していない場合や、エンドユーザーが実行時にプロパティを指定したりメソッドを実行したりできるようにすることが必要になる場合もあります。</span><span class="sxs-lookup"><span data-stu-id="37154-104">However, in some cases you may not know about an object's properties and methods in advance, or you may just want the flexibility of enabling an end user to specify properties or execute methods at run time.</span></span>  
  
## <a name="callbyname-function"></a><span data-ttu-id="37154-105">CallByName 関数</span><span class="sxs-lookup"><span data-stu-id="37154-105">CallByName Function</span></span>  
 <span data-ttu-id="37154-106">たとえば、演算子を COM コンポーネントに渡すことによってユーザーによって入力された式を評価するクライアントアプリケーションなどを考えてみます。</span><span class="sxs-lookup"><span data-stu-id="37154-106">Consider, for example, a client application that evaluates expressions entered by the user by passing an operator to a COM component.</span></span> <span data-ttu-id="37154-107">新しい演算子を必要とする新しい関数をコンポーネントに常に追加するとします。</span><span class="sxs-lookup"><span data-stu-id="37154-107">Suppose you are constantly adding new functions to the component that require new operators.</span></span> <span data-ttu-id="37154-108">標準のオブジェクトアクセス手法を使用する場合は、新しい演算子を使用する前に、クライアントアプリケーションを再コンパイルして再配布する必要があります。</span><span class="sxs-lookup"><span data-stu-id="37154-108">When you use standard object access techniques, you must recompile and redistribute the client application before it could use the new operators.</span></span> <span data-ttu-id="37154-109">これを回避するには、`CallByName` 関数を使用して、アプリケーションを変更せずに、新しい演算子を文字列として渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="37154-109">To avoid this, you can use the `CallByName` function to pass the new operators as strings, without changing the application.</span></span>  
  
 <span data-ttu-id="37154-110">`CallByName` 関数を使用すると、実行時に文字列を使用してプロパティまたはメソッドを指定できます。</span><span class="sxs-lookup"><span data-stu-id="37154-110">The `CallByName` function lets you use a string to specify a property or method at run time.</span></span> <span data-ttu-id="37154-111">`CallByName` 関数のシグネチャは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="37154-111">The signature for the `CallByName` function looks like this:</span></span>  
  
 <span data-ttu-id="37154-112">*結果* = `CallByName`(*Object*、 *ProcedureName*、 *CallType*、 *Arguments*())</span><span class="sxs-lookup"><span data-stu-id="37154-112">*Result* = `CallByName`(*Object*, *ProcedureName*, *CallType*, *Arguments*())</span></span>  
  
 <span data-ttu-id="37154-113">最初の引数*object*は、操作対象のオブジェクトの名前を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="37154-113">The first argument, *Object*, takes the name of the object you want to act upon.</span></span> <span data-ttu-id="37154-114">*ProcedureName*引数は、呼び出されるメソッドまたはプロパティプロシージャの名前を含む文字列を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="37154-114">The *ProcedureName* argument takes a string that contains the name of the method or property procedure to be invoked.</span></span> <span data-ttu-id="37154-115">*CallType*引数は、呼び出すプロシージャの種類を表す定数を受け取ります。メソッド (`Microsoft.VisualBasic.CallType.Method`)、読み取りプロパティ (`Microsoft.VisualBasic.CallType.Get`)、またはプロパティセット (`Microsoft.VisualBasic.CallType.Set`) です。</span><span class="sxs-lookup"><span data-stu-id="37154-115">The *CallType* argument takes a constant that represents the type of procedure to invoke: a method (`Microsoft.VisualBasic.CallType.Method`), a property read (`Microsoft.VisualBasic.CallType.Get`), or a property set (`Microsoft.VisualBasic.CallType.Set`).</span></span> <span data-ttu-id="37154-116">*Arguments*引数 (省略可能) は、プロシージャの引数を含む `Object` 型の配列を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="37154-116">The *Arguments* argument, which is optional, takes an array of type `Object` that contains any arguments to the procedure.</span></span>  
  
 <span data-ttu-id="37154-117">現在のソリューションではクラスと共に `CallByName` を使用できますが、ほとんどの場合、.NET Framework アセンブリから COM オブジェクトまたはオブジェクトにアクセスするために使用されます。</span><span class="sxs-lookup"><span data-stu-id="37154-117">You can use `CallByName` with classes in your current solution, but it is most often used to access COM objects or objects from .NET Framework assemblies.</span></span>  
  
 <span data-ttu-id="37154-118">次のコードに示すように、`MathClass`という名前のクラスを含むアセンブリへの参照を追加するとします。このクラスには、`SquareRoot`という名前の新しい関数があります。</span><span class="sxs-lookup"><span data-stu-id="37154-118">Suppose you add a reference to an assembly that contains a class named `MathClass`, which has a new function named `SquareRoot`, as shown in the following code:</span></span>  
  
 [!code-vb[VbVbalrOOP#53](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#53)]  
  
 <span data-ttu-id="37154-119">アプリケーションでは、テキストボックスコントロールを使用して、呼び出すメソッドとその引数を制御できます。</span><span class="sxs-lookup"><span data-stu-id="37154-119">Your application could use text box controls to control which method will be called and its arguments.</span></span> <span data-ttu-id="37154-120">たとえば、評価する式が `TextBox1` に含まれていて、`TextBox2` を使用して関数の名前を入力した場合は、次のコードを使用して `TextBox1`の式で `SquareRoot` 関数を呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="37154-120">For example, if `TextBox1` contains the expression to be evaluated, and `TextBox2` is used to enter the name of the function, you can use the following code to invoke the `SquareRoot` function on the expression in `TextBox1`:</span></span>  
  
 [!code-vb[VbVbalrOOP#54](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#54)]  
  
 <span data-ttu-id="37154-121">`TextBox2`の `TextBox1`"SquareRoot" に「64」と入力し、`CallMath` プロシージャを呼び出すと、`TextBox1` 内の数値の平方根が評価されます。</span><span class="sxs-lookup"><span data-stu-id="37154-121">If you enter "64" in `TextBox1`, "SquareRoot" in `TextBox2`, and then call the `CallMath` procedure, the square root of the number in `TextBox1` is evaluated.</span></span> <span data-ttu-id="37154-122">この例のコードでは、`SquareRoot` 関数 (必須の引数として評価される式を含む文字列を受け取ります) を呼び出し、`TextBox1` (64 の平方根) で "8" を返します。</span><span class="sxs-lookup"><span data-stu-id="37154-122">The code in the example invokes the `SquareRoot` function (which takes a string that contains the expression to be evaluated as a required argument) and returns "8" in `TextBox1` (the square root of 64).</span></span> <span data-ttu-id="37154-123">もちろん、ユーザーが `TextBox2`に無効な文字列を入力した場合、文字列にメソッドではなくプロパティの名前が含まれている場合、またはメソッドに追加の必須引数がある場合は、実行時エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="37154-123">Of course, if the user enters an invalid string in `TextBox2`, if the string contains the name of a property instead of a method, or if the method had an additional required argument, a run-time error occurs.</span></span> <span data-ttu-id="37154-124">`CallByName` を使用してこれらのエラーやその他のエラーを予測する場合は、堅牢なエラー処理コードを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="37154-124">You have to add robust error-handling code when you use `CallByName` to anticipate these or any other errors.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="37154-125">`CallByName` 関数は役に立つ場合がありますが、パフォーマンスへの影響を考慮する必要があります。つまり、`CallByName` を使用してプロシージャを呼び出すと、遅延バインディングの呼び出しより少し遅くなります。</span><span class="sxs-lookup"><span data-stu-id="37154-125">While the `CallByName` function may be useful in some cases, you must weigh its usefulness against the performance implications — using `CallByName` to invoke a procedure is slightly slower than a late-bound call.</span></span> <span data-ttu-id="37154-126">ループの内部など、繰り返し呼び出される関数を呼び出す場合、`CallByName` はパフォーマンスに重大な影響を与える可能性があります。</span><span class="sxs-lookup"><span data-stu-id="37154-126">If you are invoking a function that is called repeatedly, such as inside a loop, `CallByName` can have a severe effect on performance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="37154-127">参照</span><span class="sxs-lookup"><span data-stu-id="37154-127">See also</span></span>

- <xref:Microsoft.VisualBasic.Interaction.CallByName%2A>
- [<span data-ttu-id="37154-128">オブジェクトの型の決定</span><span class="sxs-lookup"><span data-stu-id="37154-128">Determining Object Type</span></span>](../../../../visual-basic/programming-guide/language-features/early-late-binding/determining-object-type.md)
