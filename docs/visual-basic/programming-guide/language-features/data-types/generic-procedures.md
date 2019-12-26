---
title: ジェネリック プロシージャ
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
ms.openlocfilehash: 16a629e07cf711778b3d8d1863958ec7a6300649
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350085"
---
# <a name="generic-procedures-in-visual-basic"></a><span data-ttu-id="3d0c3-102">Visual Basic におけるジェネリック プロシージャ</span><span class="sxs-lookup"><span data-stu-id="3d0c3-102">Generic Procedures in Visual Basic</span></span>
<span data-ttu-id="3d0c3-103">ジェネリック*プロシージャ*(*ジェネリックメソッド*とも呼ばれます) は、少なくとも1つの型パラメーターで定義されたプロシージャです。</span><span class="sxs-lookup"><span data-stu-id="3d0c3-103">A *generic procedure*, also called a *generic method*, is a procedure defined with at least one type parameter.</span></span> <span data-ttu-id="3d0c3-104">これにより、呼び出し元のコードは、プロシージャを呼び出すたびに、データ型を要件に合わせて調整できます。</span><span class="sxs-lookup"><span data-stu-id="3d0c3-104">This allows the calling code to tailor the data types to its requirements each time it calls the procedure.</span></span>  
  
 <span data-ttu-id="3d0c3-105">ジェネリッククラスまたはジェネリック構造体内で定義されているので、プロシージャはジェネリックではありません。</span><span class="sxs-lookup"><span data-stu-id="3d0c3-105">A procedure is not generic simply by virtue of being defined inside a generic class or a generic structure.</span></span> <span data-ttu-id="3d0c3-106">ジェネリックにするには、プロシージャは、実行される可能性のある通常のパラメーターに加えて、少なくとも1つの型パラメーターを受け取る必要があります。</span><span class="sxs-lookup"><span data-stu-id="3d0c3-106">To be generic, the procedure must take at least one type parameter, in addition to any normal parameters it might take.</span></span> <span data-ttu-id="3d0c3-107">ジェネリッククラスまたは構造体には、非ジェネリックプロシージャを含めることができ、非ジェネリックのクラス、構造体、またはモジュールにジェネリックプロシージャを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="3d0c3-107">A generic class or structure can contain nongeneric procedures, and a nongeneric class, structure, or module can contain generic procedures.</span></span>  
  
 <span data-ttu-id="3d0c3-108">ジェネリックプロシージャは、通常のパラメーターリスト、戻り値の型 (存在する場合)、およびプロシージャコード内で、その型パラメーターを使用できます。</span><span class="sxs-lookup"><span data-stu-id="3d0c3-108">A generic procedure can use its type parameters in its normal parameter list, in its return type if it has one, and in its procedure code.</span></span>  
  
## <a name="type-inference"></a><span data-ttu-id="3d0c3-109">型の推定</span><span class="sxs-lookup"><span data-stu-id="3d0c3-109">Type Inference</span></span>  
 <span data-ttu-id="3d0c3-110">型引数をまったく指定せずにジェネリックプロシージャを呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="3d0c3-110">You can call a generic procedure without supplying any type arguments at all.</span></span> <span data-ttu-id="3d0c3-111">このように呼び出した場合、コンパイラは、プロシージャの型引数に渡す適切なデータ型を決定しようとします。</span><span class="sxs-lookup"><span data-stu-id="3d0c3-111">If you call it this way, the compiler attempts to determine the appropriate data types to pass to the procedure's type arguments.</span></span> <span data-ttu-id="3d0c3-112">これは、*型の推論*と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="3d0c3-112">This is called *type inference*.</span></span> <span data-ttu-id="3d0c3-113">次のコードは、型パラメーター `t`に型 `String` を渡す必要があることをコンパイラが推論する呼び出しを示しています。</span><span class="sxs-lookup"><span data-stu-id="3d0c3-113">The following code shows a call in which the compiler infers that it should pass type `String` to the type parameter `t`.</span></span>  
  
 [!code-vb[VbVbalrDataTypes#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDataTypes/VB/Class1.vb#15)]  
  
 <span data-ttu-id="3d0c3-114">コンパイラは、呼び出しのコンテキストから型引数を推論できない場合、エラーを報告します。</span><span class="sxs-lookup"><span data-stu-id="3d0c3-114">If the compiler cannot infer the type arguments from the context of your call, it reports an error.</span></span> <span data-ttu-id="3d0c3-115">このようなエラーの原因の1つとして、配列のランクの不一致が考えられます。</span><span class="sxs-lookup"><span data-stu-id="3d0c3-115">One possible cause of such an error is an array rank mismatch.</span></span> <span data-ttu-id="3d0c3-116">たとえば、通常のパラメーターを型パラメーターの配列として定義するとします。</span><span class="sxs-lookup"><span data-stu-id="3d0c3-116">For example, suppose you define a normal parameter as an array of a type parameter.</span></span> <span data-ttu-id="3d0c3-117">異なるランク (次元数) の配列を指定するジェネリックプロシージャを呼び出すと、不一致によって型の推定が失敗します。</span><span class="sxs-lookup"><span data-stu-id="3d0c3-117">If you call the generic procedure supplying an array of a different rank (number of dimensions), the mismatch causes type inference to fail.</span></span> <span data-ttu-id="3d0c3-118">次のコードは、1次元配列を必要とするプロシージャに2次元配列が渡される呼び出しを示しています。</span><span class="sxs-lookup"><span data-stu-id="3d0c3-118">The following code shows a call in which a two-dimensional array is passed to a procedure that expects a one-dimensional array.</span></span>  
  
```vb  
Public Sub demoSub(Of t)(ByVal arg() As t)
End Sub

Public Sub callDemoSub()
    Dim twoDimensions(,) As Integer
    demoSub(twoDimensions)
End Sub
```
  
 <span data-ttu-id="3d0c3-119">型の推定を呼び出すには、すべての型引数を省略する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3d0c3-119">You can invoke type inference only by omitting all the type arguments.</span></span> <span data-ttu-id="3d0c3-120">1つの型引数を指定する場合は、それらをすべて指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3d0c3-120">If you supply one type argument, you must supply them all.</span></span>  
  
 <span data-ttu-id="3d0c3-121">型の推定は、ジェネリックプロシージャでのみサポートされています。</span><span class="sxs-lookup"><span data-stu-id="3d0c3-121">Type inference is supported only for generic procedures.</span></span> <span data-ttu-id="3d0c3-122">ジェネリッククラス、構造体、インターフェイス、またはデリゲートの型の推定を呼び出すことはできません。</span><span class="sxs-lookup"><span data-stu-id="3d0c3-122">You cannot invoke type inference on generic classes, structures, interfaces, or delegates.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3d0c3-123">例</span><span class="sxs-lookup"><span data-stu-id="3d0c3-123">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="3d0c3-124">説明</span><span class="sxs-lookup"><span data-stu-id="3d0c3-124">Description</span></span>  
 <span data-ttu-id="3d0c3-125">次の例では、ジェネリック `Function` プロシージャを定義して、配列内の特定の要素を検索します。</span><span class="sxs-lookup"><span data-stu-id="3d0c3-125">The following example defines a generic `Function` procedure to find a particular element in an array.</span></span> <span data-ttu-id="3d0c3-126">1つの型パラメーターを定義し、それを使用してパラメーターリスト内の2つのパラメーターを構築します。</span><span class="sxs-lookup"><span data-stu-id="3d0c3-126">It defines one type parameter and uses it to construct the two parameters in the parameter list.</span></span>  
  
### <a name="code"></a><span data-ttu-id="3d0c3-127">コード</span><span class="sxs-lookup"><span data-stu-id="3d0c3-127">Code</span></span>  
 [!code-vb[VbVbalrDataTypes#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDataTypes/VB/Class1.vb#14)]  
  
### <a name="comments"></a><span data-ttu-id="3d0c3-128">コメント</span><span class="sxs-lookup"><span data-stu-id="3d0c3-128">Comments</span></span>  
 <span data-ttu-id="3d0c3-129">前の例では、`searchArray`の各要素に対して `searchValue` を比較する機能が必要です。</span><span class="sxs-lookup"><span data-stu-id="3d0c3-129">The preceding example requires the ability to compare `searchValue` against each element of `searchArray`.</span></span> <span data-ttu-id="3d0c3-130">この機能を保証するために、`T` 型パラメーターを制約して、<xref:System.IComparable%601> インターフェイスを実装します。</span><span class="sxs-lookup"><span data-stu-id="3d0c3-130">To guarantee this ability, it constrains the type parameter `T` to implement the <xref:System.IComparable%601> interface.</span></span> <span data-ttu-id="3d0c3-131">このコードでは、`=` 演算子ではなく、<xref:System.IComparable%601.CompareTo%2A> メソッドを使用しています。 `T` に指定された型引数が `=` 演算子をサポートしている保証はないためです。</span><span class="sxs-lookup"><span data-stu-id="3d0c3-131">The code uses the <xref:System.IComparable%601.CompareTo%2A> method instead of the `=` operator, because there is no guarantee that a type argument supplied for `T` supports the `=` operator.</span></span>  
  
 <span data-ttu-id="3d0c3-132">`findElement` プロシージャは、次のコードを使用してテストできます。</span><span class="sxs-lookup"><span data-stu-id="3d0c3-132">You can test the `findElement` procedure with the following code.</span></span>  
  
 [!code-vb[VbVbalrDataTypes#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDataTypes/VB/Class1.vb#13)]  
  
 <span data-ttu-id="3d0c3-133">上記の `MsgBox` を呼び出すと、それぞれ "0"、"1"、および "-1" が表示されます。</span><span class="sxs-lookup"><span data-stu-id="3d0c3-133">The preceding calls to `MsgBox` display "0", "1", and "-1" respectively.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d0c3-134">参照</span><span class="sxs-lookup"><span data-stu-id="3d0c3-134">See also</span></span>

- [<span data-ttu-id="3d0c3-135">Visual Basic におけるジェネリック型</span><span class="sxs-lookup"><span data-stu-id="3d0c3-135">Generic Types in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [<span data-ttu-id="3d0c3-136">方法 : 複数のデータ型に同一の機能を提供できるクラスを定義する</span><span class="sxs-lookup"><span data-stu-id="3d0c3-136">How to: Define a Class That Can Provide Identical Functionality on Different Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-define-a-class-that-can-provide-identical-functionality.md)
- [<span data-ttu-id="3d0c3-137">方法 : ジェネリック クラスを使用する</span><span class="sxs-lookup"><span data-stu-id="3d0c3-137">How to: Use a Generic Class</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-use-a-generic-class.md)
- [<span data-ttu-id="3d0c3-138">Visual Basic におけるプロシージャ</span><span class="sxs-lookup"><span data-stu-id="3d0c3-138">Procedures</span></span>](../../../../visual-basic/programming-guide/language-features/procedures/index.md)
- [<span data-ttu-id="3d0c3-139">プロシージャのパラメーターと引数</span><span class="sxs-lookup"><span data-stu-id="3d0c3-139">Procedure Parameters and Arguments</span></span>](../../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)
- [<span data-ttu-id="3d0c3-140">型リスト</span><span class="sxs-lookup"><span data-stu-id="3d0c3-140">Type List</span></span>](../../../../visual-basic/language-reference/statements/type-list.md)
- [<span data-ttu-id="3d0c3-141">パラメーター リスト</span><span class="sxs-lookup"><span data-stu-id="3d0c3-141">Parameter List</span></span>](../../../../visual-basic/language-reference/statements/parameter-list.md)
