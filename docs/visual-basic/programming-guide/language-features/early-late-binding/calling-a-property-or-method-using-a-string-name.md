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
ms.openlocfilehash: 9f28548c27545d94dde38cef3e9c56f98a69b259
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2020
ms.locfileid: "91086089"
---
# <a name="calling-a-property-or-method-using-a-string-name-visual-basic"></a><span data-ttu-id="287f2-102">文字列名によるプロパティまたはメソッドの呼び出し (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="287f2-102">Calling a Property or Method Using a String Name (Visual Basic)</span></span>

<span data-ttu-id="287f2-103">オブジェクトのプロパティやメソッドは、デザイン時に把握して、これらを処理するコードを作成できることがほとんどです。</span><span class="sxs-lookup"><span data-stu-id="287f2-103">In most cases, you can discover the properties and methods of an object at design time, and write code to handle them.</span></span> <span data-ttu-id="287f2-104">しかし、オブジェクトのプロパティやメソッドを事前に知ることができない場合や、実行時にエンド ユーザーがプロパティを指定したりメソッドを実行したりできる柔軟性を持たせたい場合があります。</span><span class="sxs-lookup"><span data-stu-id="287f2-104">However, in some cases you may not know about an object's properties and methods in advance, or you may just want the flexibility of enabling an end user to specify properties or execute methods at run time.</span></span>  
  
## <a name="callbyname-function"></a><span data-ttu-id="287f2-105">CallByName 関数</span><span class="sxs-lookup"><span data-stu-id="287f2-105">CallByName Function</span></span>  

 <span data-ttu-id="287f2-106">例として、COM コンポーネントにユーザーが演算子を渡すことで入力した式を評価する、クライアント アプリケーションを考えます。</span><span class="sxs-lookup"><span data-stu-id="287f2-106">Consider, for example, a client application that evaluates expressions entered by the user by passing an operator to a COM component.</span></span> <span data-ttu-id="287f2-107">ここでは、新しい演算子が必要な新しい関数を、継続的にコンポーネントに追加するものとします。</span><span class="sxs-lookup"><span data-stu-id="287f2-107">Suppose you are constantly adding new functions to the component that require new operators.</span></span> <span data-ttu-id="287f2-108">標準的なオブジェクトへのアクセス手法を使用する場合、新しい演算子を使用するには、クライアント アプリケーションを再コンパイルして配布し直す必要があります。</span><span class="sxs-lookup"><span data-stu-id="287f2-108">When you use standard object access techniques, you must recompile and redistribute the client application before it could use the new operators.</span></span> <span data-ttu-id="287f2-109">これは、`CallByName` 関数を使用して新しい演算子を文字列として渡すことで回避できます。アプリケーションを変更する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="287f2-109">To avoid this, you can use the `CallByName` function to pass the new operators as strings, without changing the application.</span></span>  
  
 <span data-ttu-id="287f2-110">`CallByName` 関数を使用すると、文字列を使用して実行時にプロパティまたはメソッドを指定することができます。</span><span class="sxs-lookup"><span data-stu-id="287f2-110">The `CallByName` function lets you use a string to specify a property or method at run time.</span></span> <span data-ttu-id="287f2-111">`CallByName` 関数のシグネチャは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="287f2-111">The signature for the `CallByName` function looks like this:</span></span>  
  
 <span data-ttu-id="287f2-112">*Result* = `CallByName`(<*オブジェクト*>, <*プロシージャ名*>, <*呼び出しの型*>, <*引数*>())</span><span class="sxs-lookup"><span data-stu-id="287f2-112">*Result* = `CallByName`(*Object*, *ProcedureName*, *CallType*, *Arguments*())</span></span>  
  
 <span data-ttu-id="287f2-113">最初の引数である <*オブジェクト*> は、処理対象のオブジェクトの名前を取ります。</span><span class="sxs-lookup"><span data-stu-id="287f2-113">The first argument, *Object*, takes the name of the object you want to act upon.</span></span> <span data-ttu-id="287f2-114"><*プロシージャ名*> 引数は、呼び出すメソッドまたはプロパティのプロシージャ名を含んだ文字列を取ります。</span><span class="sxs-lookup"><span data-stu-id="287f2-114">The *ProcedureName* argument takes a string that contains the name of the method or property procedure to be invoked.</span></span> <span data-ttu-id="287f2-115"><*呼び出しの型*> 引数は、メソッド (`Microsoft.VisualBasic.CallType.Method`)、読み取り対象のプロパティ (`Microsoft.VisualBasic.CallType.Get`)、設定対象のプロパティ (`Microsoft.VisualBasic.CallType.Set`) のいずれかのうち、呼び出すプロシージャの型を表す定数を取ります。</span><span class="sxs-lookup"><span data-stu-id="287f2-115">The *CallType* argument takes a constant that represents the type of procedure to invoke: a method (`Microsoft.VisualBasic.CallType.Method`), a property read (`Microsoft.VisualBasic.CallType.Get`), or a property set (`Microsoft.VisualBasic.CallType.Set`).</span></span> <span data-ttu-id="287f2-116"><*引数*> 引数は省略可能であり、プロシージャに渡す引数が含まれる `Object` 型の配列を取ります。</span><span class="sxs-lookup"><span data-stu-id="287f2-116">The *Arguments* argument, which is optional, takes an array of type `Object` that contains any arguments to the procedure.</span></span>  
  
 <span data-ttu-id="287f2-117">`CallByName` は、現在のソリューションのクラスと共に使用できますが、多くの場合は、COM オブジェクトまたは .NET Framework アセンブリのオブジェクトにアクセスするために使用します。</span><span class="sxs-lookup"><span data-stu-id="287f2-117">You can use `CallByName` with classes in your current solution, but it is most often used to access COM objects or objects from .NET Framework assemblies.</span></span>  
  
 <span data-ttu-id="287f2-118">次のコードに示すように、`SquareRoot` という名前の新しい関数を持つ、`MathClass` という名前のクラスが含まれるアセンブリへの参照を追加するとします。</span><span class="sxs-lookup"><span data-stu-id="287f2-118">Suppose you add a reference to an assembly that contains a class named `MathClass`, which has a new function named `SquareRoot`, as shown in the following code:</span></span>  
  
 [!code-vb[VbVbalrOOP#53](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#53)]  
  
 <span data-ttu-id="287f2-119">アプリケーションでテキスト ボックス コントロールを使用して、呼び出し対象のメソッドとその引数を制御できます。</span><span class="sxs-lookup"><span data-stu-id="287f2-119">Your application could use text box controls to control which method will be called and its arguments.</span></span> <span data-ttu-id="287f2-120">たとえば、`TextBox1` に評価対象の式が含まれており、`TextBox2` を使用して関数名を入力する場合、次のコードを使用することで、`TextBox1` 内の式を対象とする `SquareRoot` 関数を呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="287f2-120">For example, if `TextBox1` contains the expression to be evaluated, and `TextBox2` is used to enter the name of the function, you can use the following code to invoke the `SquareRoot` function on the expression in `TextBox1`:</span></span>  
  
 [!code-vb[VbVbalrOOP#54](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#54)]  
  
 <span data-ttu-id="287f2-121">`TextBox1` に「64」、`TextBox2` に「SquareRoot」と入力してから `CallMath` プロシージャを呼び出すと、`TextBox1` に含まれる数字の平方根が算出されます。</span><span class="sxs-lookup"><span data-stu-id="287f2-121">If you enter "64" in `TextBox1`, "SquareRoot" in `TextBox2`, and then call the `CallMath` procedure, the square root of the number in `TextBox1` is evaluated.</span></span> <span data-ttu-id="287f2-122">この例のコードでは、`SquareRoot` 関数 (評価対象の式が含まれる文字列を必須引数として取ります) を呼び出して、`TextBox1` で "8" (64 の平方根) を返します。</span><span class="sxs-lookup"><span data-stu-id="287f2-122">The code in the example invokes the `SquareRoot` function (which takes a string that contains the expression to be evaluated as a required argument) and returns "8" in `TextBox1` (the square root of 64).</span></span> <span data-ttu-id="287f2-123">当然のことながら、ユーザーが `TextBox2` に無効な文字列を入力するか、文字列にメソッド名ではなくプロパティ名が含まれているか、メソッドに追加の必須引数がある場合には、実行時エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="287f2-123">Of course, if the user enters an invalid string in `TextBox2`, if the string contains the name of a property instead of a method, or if the method had an additional required argument, a run-time error occurs.</span></span> <span data-ttu-id="287f2-124">`CallByName` を使用するときには、こうしたエラーやその他のエラーも考慮して、堅牢なエラー処理コードを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="287f2-124">You have to add robust error-handling code when you use `CallByName` to anticipate these or any other errors.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="287f2-125">`CallByName` 関数は便利な場合もありますが、その有用性をパフォーマンスに対する影響と比較して考慮するようにしてください。`CallByName` を使用してプロシージャを呼び出すと、遅延バインディング呼び出しに比べてやや時間がかかります。</span><span class="sxs-lookup"><span data-stu-id="287f2-125">While the `CallByName` function may be useful in some cases, you must weigh its usefulness against the performance implications — using `CallByName` to invoke a procedure is slightly slower than a late-bound call.</span></span> <span data-ttu-id="287f2-126">ループ内など、繰り返し呼び出される関数を呼び出す場合、`CallByName` を使用するとパフォーマンスに著しい負荷がかかる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="287f2-126">If you are invoking a function that is called repeatedly, such as inside a loop, `CallByName` can have a severe effect on performance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="287f2-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="287f2-127">See also</span></span>

- <xref:Microsoft.VisualBasic.Interaction.CallByName%2A>
- [<span data-ttu-id="287f2-128">オブジェクトの型の決定</span><span class="sxs-lookup"><span data-stu-id="287f2-128">Determining Object Type</span></span>](determining-object-type.md)
