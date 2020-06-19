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
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350085"
---
# <a name="generic-procedures-in-visual-basic"></a><span data-ttu-id="88707-102">Visual Basic におけるジェネリック プロシージャ</span><span class="sxs-lookup"><span data-stu-id="88707-102">Generic Procedures in Visual Basic</span></span>
<span data-ttu-id="88707-103">"*ジェネリック プロシージャ*" は、"*ジェネリック メソッド*" とも呼ばれる、少なくとも 1 つの型パラメーターを含むように定義されたプロシージャです。</span><span class="sxs-lookup"><span data-stu-id="88707-103">A *generic procedure*, also called a *generic method*, is a procedure defined with at least one type parameter.</span></span> <span data-ttu-id="88707-104">これによって、呼び出し元のコードが、プロシージャを呼び出すたびに、要件に合わせてデータ型を調整できるようになります。</span><span class="sxs-lookup"><span data-stu-id="88707-104">This allows the calling code to tailor the data types to its requirements each time it calls the procedure.</span></span>  
  
 <span data-ttu-id="88707-105">プロシージャは、ジェネリック クラスまたはジェネリック構造体内で定義されているというだけの理由ではジェネリックになりません。</span><span class="sxs-lookup"><span data-stu-id="88707-105">A procedure is not generic simply by virtue of being defined inside a generic class or a generic structure.</span></span> <span data-ttu-id="88707-106">プロシージャがジェネリックになるためには、通常のパラメーター以外に、少なくとも 1 つの型パラメーターを受け取る必要があります。</span><span class="sxs-lookup"><span data-stu-id="88707-106">To be generic, the procedure must take at least one type parameter, in addition to any normal parameters it might take.</span></span> <span data-ttu-id="88707-107">ジェネリックのクラスまたは構造体に非ジェネリック プロシージャを含めることができます。また、非ジェネリックのクラス、構造体、またはモジュールにジェネリック プロシージャを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="88707-107">A generic class or structure can contain nongeneric procedures, and a nongeneric class, structure, or module can contain generic procedures.</span></span>  
  
 <span data-ttu-id="88707-108">ジェネリック プロシージャは、通常のパラメーター リスト、戻り値の型 (存在する場合)、およびプロシージャ コード内で、その型パラメーターを使用できます。</span><span class="sxs-lookup"><span data-stu-id="88707-108">A generic procedure can use its type parameters in its normal parameter list, in its return type if it has one, and in its procedure code.</span></span>  
  
## <a name="type-inference"></a><span data-ttu-id="88707-109">型推論</span><span class="sxs-lookup"><span data-stu-id="88707-109">Type Inference</span></span>  
 <span data-ttu-id="88707-110">型引数をまったく指定せずにジェネリック プロシージャを呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="88707-110">You can call a generic procedure without supplying any type arguments at all.</span></span> <span data-ttu-id="88707-111">このように呼び出した場合、コンパイラが、プロシージャの型引数に渡す適切なデータ型を決定しようとします。</span><span class="sxs-lookup"><span data-stu-id="88707-111">If you call it this way, the compiler attempts to determine the appropriate data types to pass to the procedure's type arguments.</span></span> <span data-ttu-id="88707-112">これは "*型の推定*" と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="88707-112">This is called *type inference*.</span></span> <span data-ttu-id="88707-113">次のコードに示す呼び出しでは、型 `String` を型パラメーター `t` に渡す必要があるとコンパイラによって推定されます。</span><span class="sxs-lookup"><span data-stu-id="88707-113">The following code shows a call in which the compiler infers that it should pass type `String` to the type parameter `t`.</span></span>  
  
 [!code-vb[VbVbalrDataTypes#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDataTypes/VB/Class1.vb#15)]  
  
 <span data-ttu-id="88707-114">コンパイラが、呼び出しのコンテキストから型引数を推定できない場合、エラーを報告します。</span><span class="sxs-lookup"><span data-stu-id="88707-114">If the compiler cannot infer the type arguments from the context of your call, it reports an error.</span></span> <span data-ttu-id="88707-115">このようなエラーの原因の 1 つとして、配列のランクの不一致が考えられます。</span><span class="sxs-lookup"><span data-stu-id="88707-115">One possible cause of such an error is an array rank mismatch.</span></span> <span data-ttu-id="88707-116">たとえば、通常のパラメーターを型パラメーターの配列として定義するとします。</span><span class="sxs-lookup"><span data-stu-id="88707-116">For example, suppose you define a normal parameter as an array of a type parameter.</span></span> <span data-ttu-id="88707-117">呼び出すジェネリック プロシージャによって異なるランク (次元数) の配列が提供されると、不一致のために型の推定が失敗します。</span><span class="sxs-lookup"><span data-stu-id="88707-117">If you call the generic procedure supplying an array of a different rank (number of dimensions), the mismatch causes type inference to fail.</span></span> <span data-ttu-id="88707-118">次のコードに示す呼び出しでは、1 次元配列を予期しているプロシージャに 2 次元配列が渡されます。</span><span class="sxs-lookup"><span data-stu-id="88707-118">The following code shows a call in which a two-dimensional array is passed to a procedure that expects a one-dimensional array.</span></span>  
  
```vb  
Public Sub demoSub(Of t)(ByVal arg() As t)
End Sub

Public Sub callDemoSub()
    Dim twoDimensions(,) As Integer
    demoSub(twoDimensions)
End Sub
```
  
 <span data-ttu-id="88707-119">型の推定を呼び出すことができるのは、すべての型引数を省略した場合のみです。</span><span class="sxs-lookup"><span data-stu-id="88707-119">You can invoke type inference only by omitting all the type arguments.</span></span> <span data-ttu-id="88707-120">型引数を 1 つ指定する場合は、すべて指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="88707-120">If you supply one type argument, you must supply them all.</span></span>  
  
 <span data-ttu-id="88707-121">型の推定は、ジェネリック プロシージャでのみサポートされています。</span><span class="sxs-lookup"><span data-stu-id="88707-121">Type inference is supported only for generic procedures.</span></span> <span data-ttu-id="88707-122">ジェネリック クラス、構造体、インターフェイス、またはデリゲートに対して、型の推定を呼び出すことはできません。</span><span class="sxs-lookup"><span data-stu-id="88707-122">You cannot invoke type inference on generic classes, structures, interfaces, or delegates.</span></span>  
  
## <a name="example"></a><span data-ttu-id="88707-123">例</span><span class="sxs-lookup"><span data-stu-id="88707-123">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="88707-124">説明</span><span class="sxs-lookup"><span data-stu-id="88707-124">Description</span></span>  
 <span data-ttu-id="88707-125">次の例では、配列内の特定の要素を探す、ジェネリック `Function` プロシージャを定義しています。</span><span class="sxs-lookup"><span data-stu-id="88707-125">The following example defines a generic `Function` procedure to find a particular element in an array.</span></span> <span data-ttu-id="88707-126">1 つの型パラメーターを定義し、それを使用してパラメーター リスト内の 2 つのパラメーターを構築します。</span><span class="sxs-lookup"><span data-stu-id="88707-126">It defines one type parameter and uses it to construct the two parameters in the parameter list.</span></span>  
  
### <a name="code"></a><span data-ttu-id="88707-127">コード</span><span class="sxs-lookup"><span data-stu-id="88707-127">Code</span></span>  
 [!code-vb[VbVbalrDataTypes#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDataTypes/VB/Class1.vb#14)]  
  
### <a name="comments"></a><span data-ttu-id="88707-128">コメント</span><span class="sxs-lookup"><span data-stu-id="88707-128">Comments</span></span>  
 <span data-ttu-id="88707-129">前の例は、`searchArray` の各要素に対して `searchValue` を比較する必要があります。</span><span class="sxs-lookup"><span data-stu-id="88707-129">The preceding example requires the ability to compare `searchValue` against each element of `searchArray`.</span></span> <span data-ttu-id="88707-130">この動作を保証するために、型パラメーター `T` が <xref:System.IComparable%601> インターフェイスを実装するように制約します。</span><span class="sxs-lookup"><span data-stu-id="88707-130">To guarantee this ability, it constrains the type parameter `T` to implement the <xref:System.IComparable%601> interface.</span></span> <span data-ttu-id="88707-131">コードは、<xref:System.IComparable%601.CompareTo%2A> メソッドを `=` 演算子の代わりに使用します。`T` に提供される型引数で `=` 演算子がサポートされる保証がないためです。</span><span class="sxs-lookup"><span data-stu-id="88707-131">The code uses the <xref:System.IComparable%601.CompareTo%2A> method instead of the `=` operator, because there is no guarantee that a type argument supplied for `T` supports the `=` operator.</span></span>  
  
 <span data-ttu-id="88707-132">次のコードを使用して `findElement` プロシージャをテストできます。</span><span class="sxs-lookup"><span data-stu-id="88707-132">You can test the `findElement` procedure with the following code.</span></span>  
  
 [!code-vb[VbVbalrDataTypes#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDataTypes/VB/Class1.vb#13)]  
  
 <span data-ttu-id="88707-133">上記の `MsgBox` の呼び出しで、それぞれ "0"、"1"、および "-1" が表示されます。</span><span class="sxs-lookup"><span data-stu-id="88707-133">The preceding calls to `MsgBox` display "0", "1", and "-1" respectively.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="88707-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="88707-134">See also</span></span>

- [<span data-ttu-id="88707-135">Generic Types in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="88707-135">Generic Types in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [<span data-ttu-id="88707-136">方法: 複数のデータ型に同一の機能を提供できるクラスを定義する</span><span class="sxs-lookup"><span data-stu-id="88707-136">How to: Define a Class That Can Provide Identical Functionality on Different Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-define-a-class-that-can-provide-identical-functionality.md)
- [<span data-ttu-id="88707-137">方法: ジェネリック クラスを使用する</span><span class="sxs-lookup"><span data-stu-id="88707-137">How to: Use a Generic Class</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-use-a-generic-class.md)
- [<span data-ttu-id="88707-138">手順</span><span class="sxs-lookup"><span data-stu-id="88707-138">Procedures</span></span>](../../../../visual-basic/programming-guide/language-features/procedures/index.md)
- [<span data-ttu-id="88707-139">プロシージャのパラメーターと引数</span><span class="sxs-lookup"><span data-stu-id="88707-139">Procedure Parameters and Arguments</span></span>](../../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)
- [<span data-ttu-id="88707-140">型リスト</span><span class="sxs-lookup"><span data-stu-id="88707-140">Type List</span></span>](../../../../visual-basic/language-reference/statements/type-list.md)
- [<span data-ttu-id="88707-141">パラメーター リスト</span><span class="sxs-lookup"><span data-stu-id="88707-141">Parameter List</span></span>](../../../../visual-basic/language-reference/statements/parameter-list.md)
