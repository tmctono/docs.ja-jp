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
ms.openlocfilehash: 92430f23b3d4d6237d0b6ec606ce2cb9b945f6f8
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2019
ms.locfileid: "65590032"
---
# <a name="calling-a-property-or-method-using-a-string-name-visual-basic"></a><span data-ttu-id="7d426-102">文字列名によるプロパティまたはメソッドの呼び出し (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7d426-102">Calling a Property or Method Using a String Name (Visual Basic)</span></span>
<span data-ttu-id="7d426-103">ほとんどの場合は、デザイン時に、オブジェクトのメソッドとプロパティを検出し、それらを処理するコードを記述できます。</span><span class="sxs-lookup"><span data-stu-id="7d426-103">In most cases, you can discover the properties and methods of an object at design time, and write code to handle them.</span></span> <span data-ttu-id="7d426-104">ただし、場合によっては可能性がありますいないオブジェクトのプロパティとメソッドを事前にわかって、またはプロパティを指定するか、実行時にメソッドを実行するエンドユーザーの有効化の柔軟性をするだけです。</span><span class="sxs-lookup"><span data-stu-id="7d426-104">However, in some cases you may not know about an object's properties and methods in advance, or you may just want the flexibility of enabling an end user to specify properties or execute methods at run time.</span></span>  
  
## <a name="callbyname-function"></a><span data-ttu-id="7d426-105">CallByName 関数</span><span class="sxs-lookup"><span data-stu-id="7d426-105">CallByName Function</span></span>  
 <span data-ttu-id="7d426-106">たとえば、オペレーターを COM コンポーネントに渡すことによって、ユーザーが入力した式を評価するクライアント アプリケーションを検討してください。</span><span class="sxs-lookup"><span data-stu-id="7d426-106">Consider, for example, a client application that evaluates expressions entered by the user by passing an operator to a COM component.</span></span> <span data-ttu-id="7d426-107">新しい演算子を必要とするコンポーネントを新しい関数を常に追加するとします。</span><span class="sxs-lookup"><span data-stu-id="7d426-107">Suppose you are constantly adding new functions to the component that require new operators.</span></span> <span data-ttu-id="7d426-108">標準のオブジェクトへのアクセス方法を使用する場合は、再コンパイルし、新しい演算子を使用できるように、クライアント アプリケーションを再配布する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7d426-108">When you use standard object access techniques, you must recompile and redistribute the client application before it could use the new operators.</span></span> <span data-ttu-id="7d426-109">これを回避するには、使用することができます、`CallByName`関数を文字列として、アプリケーションを変更することがなく、新しい演算子を渡します。</span><span class="sxs-lookup"><span data-stu-id="7d426-109">To avoid this, you can use the `CallByName` function to pass the new operators as strings, without changing the application.</span></span>  
  
 <span data-ttu-id="7d426-110">`CallByName`関数では、実行時にプロパティまたはメソッドを指定する文字列を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="7d426-110">The `CallByName` function lets you use a string to specify a property or method at run time.</span></span> <span data-ttu-id="7d426-111">署名、`CallByName`関数に次のようになります。</span><span class="sxs-lookup"><span data-stu-id="7d426-111">The signature for the `CallByName` function looks like this:</span></span>  
  
 <span data-ttu-id="7d426-112">*結果* = `CallByName`(*オブジェクト*、 *ProcedureName*、 *CallType*、*引数*())</span><span class="sxs-lookup"><span data-stu-id="7d426-112">*Result* = `CallByName`(*Object*, *ProcedureName*, *CallType*, *Arguments*())</span></span>  
  
 <span data-ttu-id="7d426-113">最初の引数*オブジェクト*、に対して操作を実行するオブジェクトの名前を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="7d426-113">The first argument, *Object*, takes the name of the object you want to act upon.</span></span> <span data-ttu-id="7d426-114">*ProcedureName*引数には、呼び出されるメソッドまたはプロパティ プロシージャの名前を含む文字列。</span><span class="sxs-lookup"><span data-stu-id="7d426-114">The *ProcedureName* argument takes a string that contains the name of the method or property procedure to be invoked.</span></span> <span data-ttu-id="7d426-115">*CallType*引数には、プロシージャを呼び出すの型を表す定数。 メソッド (`Microsoft.VisualBasic.CallType.Method`)、読み取りプロパティ (`Microsoft.VisualBasic.CallType.Get`)、またはプロパティの設定 (`Microsoft.VisualBasic.CallType.Set`)。</span><span class="sxs-lookup"><span data-stu-id="7d426-115">The *CallType* argument takes a constant that represents the type of procedure to invoke: a method (`Microsoft.VisualBasic.CallType.Method`), a property read (`Microsoft.VisualBasic.CallType.Get`), or a property set (`Microsoft.VisualBasic.CallType.Set`).</span></span> <span data-ttu-id="7d426-116">*引数*引数は省略可能な型の配列を受け取る`Object`プロシージャに引数を格納しています。</span><span class="sxs-lookup"><span data-stu-id="7d426-116">The *Arguments* argument, which is optional, takes an array of type `Object` that contains any arguments to the procedure.</span></span>  
  
 <span data-ttu-id="7d426-117">使用することができます`CallByName`が、現在のソリューション内のクラスとは .NET Framework アセンブリから COM オブジェクトまたはオブジェクトへのアクセスには使用ほとんどの場合は。</span><span class="sxs-lookup"><span data-stu-id="7d426-117">You can use `CallByName` with classes in your current solution, but it is most often used to access COM objects or objects from .NET Framework assemblies.</span></span>  
  
 <span data-ttu-id="7d426-118">という名前のクラスを格納するアセンブリへの参照を追加するとします`MathClass`、という名前の新しい関数を持つ`SquareRoot`次のコードに示すように、します。</span><span class="sxs-lookup"><span data-stu-id="7d426-118">Suppose you add a reference to an assembly that contains a class named `MathClass`, which has a new function named `SquareRoot`, as shown in the following code:</span></span>  
  
 [!code-vb[VbVbalrOOP#53](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#53)]  
  
 <span data-ttu-id="7d426-119">アプリケーションでは、どのメソッドが呼び出されるコントロールとその引数をテキスト ボックス コントロールを使用できます。</span><span class="sxs-lookup"><span data-stu-id="7d426-119">Your application could use text box controls to control which method will be called and its arguments.</span></span> <span data-ttu-id="7d426-120">たとえば場合、`TextBox1`評価される式が含まれていますと`TextBox2`は関数の名前を入力するために使用、することができますを使用して、次のコードを呼び出す、`SquareRoot`関数内の式で`TextBox1`:</span><span class="sxs-lookup"><span data-stu-id="7d426-120">For example, if `TextBox1` contains the expression to be evaluated, and `TextBox2` is used to enter the name of the function, you can use the following code to invoke the `SquareRoot` function on the expression in `TextBox1`:</span></span>  
  
 [!code-vb[VbVbalrOOP#54](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#54)]  
  
 <span data-ttu-id="7d426-121">「64」に入力した場合`TextBox1`で"SquareRoot"`TextBox2`を呼び出して、`CallMath`プロシージャ、内の数値の平方根`TextBox1`が評価されます。</span><span class="sxs-lookup"><span data-stu-id="7d426-121">If you enter "64" in `TextBox1`, "SquareRoot" in `TextBox2`, and then call the `CallMath` procedure, the square root of the number in `TextBox1` is evaluated.</span></span> <span data-ttu-id="7d426-122">例のコードを呼び出す、 `SquareRoot` (必須の引数として評価される式を含む文字列を扱う) に機能し、「8」を返します`TextBox1`(の平方根 64)。</span><span class="sxs-lookup"><span data-stu-id="7d426-122">The code in the example invokes the `SquareRoot` function (which takes a string that contains the expression to be evaluated as a required argument) and returns "8" in `TextBox1` (the square root of 64).</span></span> <span data-ttu-id="7d426-123">もちろん、ユーザーが入力に無効な文字列`TextBox2`文字列には、メソッドではなくプロパティの名前が含まれている場合は、メソッドがあるその他の必要な引数は、実行時エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="7d426-123">Of course, if the user enters an invalid string in `TextBox2`, if the string contains the name of a property instead of a method, or if the method had an additional required argument, a run-time error occurs.</span></span> <span data-ttu-id="7d426-124">使用する場合は、堅牢なエラー処理コードを追加する必要が`CallByName`これらやその他のエラーを予測します。</span><span class="sxs-lookup"><span data-stu-id="7d426-124">You have to add robust error-handling code when you use `CallByName` to anticipate these or any other errors.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7d426-125">中に、`CallByName`関数は、場合によっては便利なことがあります、パフォーマンスに与える影響に対するその有用性を比較検討する必要があります: を使用して`CallByName`プロシージャを呼び出すには、遅延バインディング呼び出しよりもわずかに遅くなります。</span><span class="sxs-lookup"><span data-stu-id="7d426-125">While the `CallByName` function may be useful in some cases, you must weigh its usefulness against the performance implications — using `CallByName` to invoke a procedure is slightly slower than a late-bound call.</span></span> <span data-ttu-id="7d426-126">繰り返し呼び出されます、このようなループ内で関数を呼び出す場合`CallByName`パフォーマンスに深刻な影響があることができます。</span><span class="sxs-lookup"><span data-stu-id="7d426-126">If you are invoking a function that is called repeatedly, such as inside a loop, `CallByName` can have a severe effect on performance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d426-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="7d426-127">See also</span></span>

- <xref:Microsoft.VisualBasic.Interaction.CallByName%2A>
- [<span data-ttu-id="7d426-128">オブジェクトの型の決定</span><span class="sxs-lookup"><span data-stu-id="7d426-128">Determining Object Type</span></span>](../../../../visual-basic/programming-guide/language-features/early-late-binding/determining-object-type.md)
