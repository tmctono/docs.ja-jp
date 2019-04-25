---
title: Visual Basic におけるジェネリック プロシージャ
ms.date: 07/20/2015
helpviewer_keywords:
- generic methods [Visual Basic], type inference
- generics [Visual Basic], type inference
- procedures [Visual Basic], generic
- generic procedures
- type inference, generics
- generic methods [Visual Basic]
- type inference
- generics [Visual Basic], procedures
- generic procedures [Visual Basic], type inference
ms.assetid: 95577b28-137f-4d5c-a149-919c828600e5
ms.openlocfilehash: 4aed16ce9eb59da54156a0cd5f1594819788521b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61906595"
---
# <a name="generic-procedures-in-visual-basic"></a><span data-ttu-id="34d99-102">Visual Basic におけるジェネリック プロシージャ</span><span class="sxs-lookup"><span data-stu-id="34d99-102">Generic Procedures in Visual Basic</span></span>
<span data-ttu-id="34d99-103">A*ジェネリック プロシージャ*も呼ばれ、*ジェネリック メソッド*、少なくとも 1 つの型パラメーターで定義されたプロシージャは。</span><span class="sxs-lookup"><span data-stu-id="34d99-103">A *generic procedure*, also called a *generic method*, is a procedure defined with at least one type parameter.</span></span> <span data-ttu-id="34d99-104">これにより、呼び出し元のコードでプロシージャを呼び出すたびにその要件にデータ型を調整できます。</span><span class="sxs-lookup"><span data-stu-id="34d99-104">This allows the calling code to tailor the data types to its requirements each time it calls the procedure.</span></span>  
  
 <span data-ttu-id="34d99-105">手順は、ジェネリック クラスまたはジェネリック構造体の内部で定義されていることだけでジェネリックではありません。</span><span class="sxs-lookup"><span data-stu-id="34d99-105">A procedure is not generic simply by virtue of being defined inside a generic class or a generic structure.</span></span> <span data-ttu-id="34d99-106">ジェネリックとは、プロシージャがかかる場合があります、通常のパラメーターだけでなく、少なくとも 1 つの型パラメーターを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="34d99-106">To be generic, the procedure must take at least one type parameter, in addition to any normal parameters it might take.</span></span> <span data-ttu-id="34d99-107">ジェネリック クラスまたは構造体は、非ジェネリック プロシージャは、および非ジェネリック クラス、構造体を含めることができます、またはモジュールには、ジェネリック プロシージャが含まれていることができます。</span><span class="sxs-lookup"><span data-stu-id="34d99-107">A generic class or structure can contain nongeneric procedures, and a nongeneric class, structure, or module can contain generic procedures.</span></span>  
  
 <span data-ttu-id="34d99-108">ジェネリック プロシージャでは、1 つ、およびそのプロシージャのコードがある場合、戻り値の型で、通常のパラメーター リストで、その型パラメーターを使用できます。</span><span class="sxs-lookup"><span data-stu-id="34d99-108">A generic procedure can use its type parameters in its normal parameter list, in its return type if it has one, and in its procedure code.</span></span>  
  
## <a name="type-inference"></a><span data-ttu-id="34d99-109">型推論</span><span class="sxs-lookup"><span data-stu-id="34d99-109">Type Inference</span></span>  
 <span data-ttu-id="34d99-110">型引数をまったく指定せず、ジェネリック プロシージャを呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="34d99-110">You can call a generic procedure without supplying any type arguments at all.</span></span> <span data-ttu-id="34d99-111">この方法で呼び出すことがある場合、コンパイラは適切なデータ型、プロシージャの型引数を渡すを判断するしようとします。</span><span class="sxs-lookup"><span data-stu-id="34d99-111">If you call it this way, the compiler attempts to determine the appropriate data types to pass to the procedure's type arguments.</span></span> <span data-ttu-id="34d99-112">これは呼び出されます*型推論*します。</span><span class="sxs-lookup"><span data-stu-id="34d99-112">This is called *type inference*.</span></span> <span data-ttu-id="34d99-113">次のコードの呼び出しを示しているコンパイラが推論型を渡すかで`String`型パラメーターに`t`します。</span><span class="sxs-lookup"><span data-stu-id="34d99-113">The following code shows a call in which the compiler infers that it should pass type `String` to the type parameter `t`.</span></span>  
  
 [!code-vb[VbVbalrDataTypes#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDataTypes/VB/Class1.vb#15)]  
  
 <span data-ttu-id="34d99-114">コンパイラが、呼び出しのコンテキストから型引数を推論されない場合、エラーを報告します。</span><span class="sxs-lookup"><span data-stu-id="34d99-114">If the compiler cannot infer the type arguments from the context of your call, it reports an error.</span></span> <span data-ttu-id="34d99-115">このようなエラーの考えられる原因の 1 つは、配列ランクが一致していません。</span><span class="sxs-lookup"><span data-stu-id="34d99-115">One possible cause of such an error is an array rank mismatch.</span></span> <span data-ttu-id="34d99-116">たとえば、型パラメーターの配列として通常のパラメーターを定義するとします。</span><span class="sxs-lookup"><span data-stu-id="34d99-116">For example, suppose you define a normal parameter as an array of a type parameter.</span></span> <span data-ttu-id="34d99-117">ジェネリック プロシージャを呼び出す場合の異なるランク (次元数)、配列を指定する、不一致が原因で型の推定が失敗します。</span><span class="sxs-lookup"><span data-stu-id="34d99-117">If you call the generic procedure supplying an array of a different rank (number of dimensions), the mismatch causes type inference to fail.</span></span> <span data-ttu-id="34d99-118">次のコードは呼び出しの 1 次元配列を受け取るプロシージャを 2 次元の配列が渡されます。</span><span class="sxs-lookup"><span data-stu-id="34d99-118">The following code shows a call in which a two-dimensional array is passed to a procedure that expects a one-dimensional array.</span></span>  
  
```vb  
Public Sub demoSub(Of t)(ByVal arg() As t)
End Sub

Public Sub callDemoSub()
    Dim twoDimensions(,) As Integer
    demoSub(twoDimensions)
End Sub
```
  
 <span data-ttu-id="34d99-119">型の推定は、すべての型引数を省略することによってのみ呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="34d99-119">You can invoke type inference only by omitting all the type arguments.</span></span> <span data-ttu-id="34d99-120">1 つの型引数を指定する場合に、それらすべてを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="34d99-120">If you supply one type argument, you must supply them all.</span></span>  
  
 <span data-ttu-id="34d99-121">型の推定は、ジェネリック プロシージャのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="34d99-121">Type inference is supported only for generic procedures.</span></span> <span data-ttu-id="34d99-122">ジェネリック クラス、構造体、インターフェイス、またはデリゲートの型の推定を呼び出すことはできません。</span><span class="sxs-lookup"><span data-stu-id="34d99-122">You cannot invoke type inference on generic classes, structures, interfaces, or delegates.</span></span>  
  
## <a name="example"></a><span data-ttu-id="34d99-123">例</span><span class="sxs-lookup"><span data-stu-id="34d99-123">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="34d99-124">説明</span><span class="sxs-lookup"><span data-stu-id="34d99-124">Description</span></span>  
 <span data-ttu-id="34d99-125">次の例では、ジェネリック`Function`配列で特定の要素を検索する手順。</span><span class="sxs-lookup"><span data-stu-id="34d99-125">The following example defines a generic `Function` procedure to find a particular element in an array.</span></span> <span data-ttu-id="34d99-126">1 つの型パラメーターを定義しを使用して、パラメーター リストの 2 つのパラメーターを作成します。</span><span class="sxs-lookup"><span data-stu-id="34d99-126">It defines one type parameter and uses it to construct the two parameters in the parameter list.</span></span>  
  
### <a name="code"></a><span data-ttu-id="34d99-127">コード</span><span class="sxs-lookup"><span data-stu-id="34d99-127">Code</span></span>  
 [!code-vb[VbVbalrDataTypes#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDataTypes/VB/Class1.vb#14)]  
  
### <a name="comments"></a><span data-ttu-id="34d99-128">コメント</span><span class="sxs-lookup"><span data-stu-id="34d99-128">Comments</span></span>  
 <span data-ttu-id="34d99-129">前の例を比較する機能を必要と`searchValue`の各要素に対して`searchArray`します。</span><span class="sxs-lookup"><span data-stu-id="34d99-129">The preceding example requires the ability to compare `searchValue` against each element of `searchArray`.</span></span> <span data-ttu-id="34d99-130">この機能を保証するために、型パラメーター制約`T`実装するために、<xref:System.IComparable%601>インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="34d99-130">To guarantee this ability, it constrains the type parameter `T` to implement the <xref:System.IComparable%601> interface.</span></span> <span data-ttu-id="34d99-131">コードを使用して、<xref:System.IComparable%601.CompareTo%2A>メソッドの代わりに、`=`演算子、型引数を指定するという保証がないため`T`サポート、`=`演算子。</span><span class="sxs-lookup"><span data-stu-id="34d99-131">The code uses the <xref:System.IComparable%601.CompareTo%2A> method instead of the `=` operator, because there is no guarantee that a type argument supplied for `T` supports the `=` operator.</span></span>  
  
 <span data-ttu-id="34d99-132">テストすることができます、`findElement`手順を次のコード。</span><span class="sxs-lookup"><span data-stu-id="34d99-132">You can test the `findElement` procedure with the following code.</span></span>  
  
 [!code-vb[VbVbalrDataTypes#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDataTypes/VB/Class1.vb#13)]  
  
 <span data-ttu-id="34d99-133">呼び出す前に、 `MsgBox` 「0」、「1」、「-1」をそれぞれ表示します。</span><span class="sxs-lookup"><span data-stu-id="34d99-133">The preceding calls to `MsgBox` display "0", "1", and "-1" respectively.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34d99-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="34d99-134">See also</span></span>

- [<span data-ttu-id="34d99-135">Visual Basic におけるジェネリック型</span><span class="sxs-lookup"><span data-stu-id="34d99-135">Generic Types in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [<span data-ttu-id="34d99-136">方法: 複数のデータ型に同一の機能を提供できるクラスを定義する</span><span class="sxs-lookup"><span data-stu-id="34d99-136">How to: Define a Class That Can Provide Identical Functionality on Different Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-define-a-class-that-can-provide-identical-functionality.md)
- [<span data-ttu-id="34d99-137">方法: ジェネリック クラスを使用する</span><span class="sxs-lookup"><span data-stu-id="34d99-137">How to: Use a Generic Class</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-use-a-generic-class.md)
- [<span data-ttu-id="34d99-138">プロシージャ</span><span class="sxs-lookup"><span data-stu-id="34d99-138">Procedures</span></span>](../../../../visual-basic/programming-guide/language-features/procedures/index.md)
- [<span data-ttu-id="34d99-139">プロシージャのパラメーターと引数</span><span class="sxs-lookup"><span data-stu-id="34d99-139">Procedure Parameters and Arguments</span></span>](../../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)
- [<span data-ttu-id="34d99-140">型リスト</span><span class="sxs-lookup"><span data-stu-id="34d99-140">Type List</span></span>](../../../../visual-basic/language-reference/statements/type-list.md)
- [<span data-ttu-id="34d99-141">パラメーター リスト</span><span class="sxs-lookup"><span data-stu-id="34d99-141">Parameter List</span></span>](../../../../visual-basic/language-reference/statements/parameter-list.md)
