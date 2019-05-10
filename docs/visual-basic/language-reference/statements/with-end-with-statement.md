---
title: With...End With ステートメント (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.With
helpviewer_keywords:
- With keyword [Visual Basic]
- loop structures [Visual Basic], and With...End With statements
- execution [Visual Basic], on object
- instructions, repeating
- With...End With statements [Visual Basic]
- With statement [Visual Basic]
- With statement [Visual Basic], nesting
- objects [Visual Basic], accessing
- With block
- End keyword [Visual Basic], With...End With statements
ms.assetid: 340d5fbb-4f43-48ec-a024-80843c137817
ms.openlocfilehash: 38a34a4662d969fd526963744b8bd493952d9cff
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64615070"
---
# <a name="withend-with-statement-visual-basic"></a><span data-ttu-id="6e855-102">With...End With ステートメント (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6e855-102">With...End With Statement (Visual Basic)</span></span>
<span data-ttu-id="6e855-103">オブジェクトまたは構造のメンバーにアクセスする場合にステートメントで簡単な構文を使用できるように、単一のオブジェクトまたは構造を繰り返し参照する一連のステートメントを実行します。</span><span class="sxs-lookup"><span data-stu-id="6e855-103">Executes a series of statements that repeatedly refer to a single object or structure so that the statements can use a simplified syntax when accessing members of the object or structure.</span></span>  <span data-ttu-id="6e855-104">構造体の使用時には、メンバー値の読み取りまたはメソッドの呼び出しのみを行うことができます。また、`With...End With` ステートメントで使用されている構造体のメンバーに値を割り当てようとすると、エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="6e855-104">When using a structure, you can only read the values of members or invoke methods, and you get an error if you try to assign values to members of a structure used in a `With...End With` statement.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6e855-105">構文</span><span class="sxs-lookup"><span data-stu-id="6e855-105">Syntax</span></span>  
  
```  
With objectExpression  
    [ statements ]  
End With  
```  
  
## <a name="parts"></a><span data-ttu-id="6e855-106">指定項目</span><span class="sxs-lookup"><span data-stu-id="6e855-106">Parts</span></span>  
  
|<span data-ttu-id="6e855-107">用語</span><span class="sxs-lookup"><span data-stu-id="6e855-107">Term</span></span>|<span data-ttu-id="6e855-108">定義</span><span class="sxs-lookup"><span data-stu-id="6e855-108">Definition</span></span>|  
|---|---|  
|`objectExpression`|<span data-ttu-id="6e855-109">必須。</span><span class="sxs-lookup"><span data-stu-id="6e855-109">Required.</span></span> <span data-ttu-id="6e855-110">オブジェクトとして評価される式。</span><span class="sxs-lookup"><span data-stu-id="6e855-110">An expression that evaluates to an object.</span></span> <span data-ttu-id="6e855-111">この式は、任意で複雑にできます。評価されるのは 1 回のみです。</span><span class="sxs-lookup"><span data-stu-id="6e855-111">The expression may be arbitrarily complex and is evaluated only once.</span></span> <span data-ttu-id="6e855-112">基本データ型だけでなく、どのデータ型として評価される式でも指定できます。</span><span class="sxs-lookup"><span data-stu-id="6e855-112">The expression can evaluate to any data type, including elementary types.</span></span>|  
|`statements`|<span data-ttu-id="6e855-113">省略可能です。</span><span class="sxs-lookup"><span data-stu-id="6e855-113">Optional.</span></span> <span data-ttu-id="6e855-114">`With` の評価によって生成されるオブジェクトのメンバーを参照できる、`End With` と `objectExpression` 間の 1 つ以上のステートメント。</span><span class="sxs-lookup"><span data-stu-id="6e855-114">One or more statements between `With` and `End With` that may refer to members of an object that's produced by the evaluation of `objectExpression`.</span></span>|  
|`End With`|<span data-ttu-id="6e855-115">必須。</span><span class="sxs-lookup"><span data-stu-id="6e855-115">Required.</span></span> <span data-ttu-id="6e855-116">`With` ブロックの定義を終了します。</span><span class="sxs-lookup"><span data-stu-id="6e855-116">Terminates the definition of the `With` block.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6e855-117">Remarks</span><span class="sxs-lookup"><span data-stu-id="6e855-117">Remarks</span></span>  
 <span data-ttu-id="6e855-118">`With...End With` を使用すると、特定のオブジェクトの名前を複数回指定することなく、そのオブジェクトに対して一連のステートメントを実行できます。</span><span class="sxs-lookup"><span data-stu-id="6e855-118">By using `With...End With`, you can perform a series of statements on a specified object without specifying the name of the object multiple times.</span></span> <span data-ttu-id="6e855-119">`With` ステートメント ブロック内では、先頭に `With` ステートメント オブジェクトを付ける場合と同様に、先頭にピリオドを付けてオブジェクトのメンバーを指定できます。</span><span class="sxs-lookup"><span data-stu-id="6e855-119">Within a `With` statement block, you can specify a member of the object starting with a period, as if the `With` statement object preceded it.</span></span>  
  
 <span data-ttu-id="6e855-120">たとえば、単一のオブジェクトに対して複数のプロパティを変更する場合、プロパティを割り当てるステートメントを `With...End With` ブロック内に指定すると、プロパティを割り当てるたびにオブジェクトを参照するのではなく、一度参照するだけで済みます。</span><span class="sxs-lookup"><span data-stu-id="6e855-120">For example, to change multiple properties on a single object, place the property assignment statements inside the `With...End With` block, referring to the object only once instead of once for each property assignment.</span></span>  
  
 <span data-ttu-id="6e855-121">コードの複数のステートメントで同じオブジェクトにアクセスする場合、`With` ステートメントを使用することにより次の利点が得られます。</span><span class="sxs-lookup"><span data-stu-id="6e855-121">If your code accesses the same object in multiple statements, you gain the following benefits by using the `With` statement:</span></span>  
  
- <span data-ttu-id="6e855-122">複雑な式を複数回評価したり、そのメンバーを複数回参照するために一時変数に結果を割り当てたりする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="6e855-122">You don't need to evaluate a complex expression multiple times or assign the result to a temporary variable to refer to its members multiple times.</span></span>  
  
- <span data-ttu-id="6e855-123">反復的な修飾式の使用を避けることにより、コードを読みやすくします。</span><span class="sxs-lookup"><span data-stu-id="6e855-123">You make your code more readable by eliminating repetitive qualifying expressions.</span></span>  
  
 <span data-ttu-id="6e855-124">`objectExpression` のデータ型には、任意のクラス型や構造体の型、または Visual Basic の基本型 (`Integer` など) も使用できます。</span><span class="sxs-lookup"><span data-stu-id="6e855-124">The data type of `objectExpression` can be any class or structure type or even a Visual Basic elementary type such as `Integer`.</span></span>  <span data-ttu-id="6e855-125">`objectExpression` の結果がオブジェクト以外になる場合、メンバー値の読み取りまたはメソッドの呼び出しのみを行うことができます。また、`With...End With` ステートメントで使用されている構造体のメンバーに値を割り当てようとすると、エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="6e855-125">If `objectExpression` results in anything other than an object, you can only read the values of its members or invoke methods, and you get an error if you try to assign values to members of a structure used in a `With...End With` statement.</span></span>  <span data-ttu-id="6e855-126">これは、構造体を返したメソッドを呼び出し、`GetAPoint().x = 1` など、関数の結果のメンバーにアクセスして直ちに値を割り当てた場合に発生するエラーと同じです。</span><span class="sxs-lookup"><span data-stu-id="6e855-126">This is the same error you would get if you invoked a method that returned a structure and immediately accessed and assigned a value to a member of the function’s result, such as `GetAPoint().x = 1`.</span></span>  <span data-ttu-id="6e855-127">いずれの場合も問題になるのは、構造体が呼び出し履歴にのみ存在することです。また、こうした状況で変更された構造体のメンバーが、プログラム内の他のコードが変更を確認できるような方法でいずれかの場所に書き込むことができません。</span><span class="sxs-lookup"><span data-stu-id="6e855-127">The problem in both cases is that the structure exists only on the call stack, and there is no way a modified structure member in these situations can write to  a location such that any other code in the program can observe the change.</span></span>  
  
 <span data-ttu-id="6e855-128">`objectExpression` は、ブロックへの入力時にのみ評価されます。</span><span class="sxs-lookup"><span data-stu-id="6e855-128">The `objectExpression` is evaluated once, upon entry into the block.</span></span> <span data-ttu-id="6e855-129">`objectExpression` ブロック内から `With` を再度割り当てることはできません。</span><span class="sxs-lookup"><span data-stu-id="6e855-129">You can't reassign the `objectExpression` from within the `With` block.</span></span>  
  
 <span data-ttu-id="6e855-130">`With` ブロック内で、修飾せずにアクセスできるのは、指定したオブジェクトのメソッドやプロパティだけです。</span><span class="sxs-lookup"><span data-stu-id="6e855-130">Within a `With` block, you can access the methods and properties of only the specified object without qualifying them.</span></span> <span data-ttu-id="6e855-131">他のオブジェクトのメソッドやプロパティを使用するには、オブジェクト名で修飾する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e855-131">You can use methods and properties of other objects, but you must qualify them with their object names.</span></span>  
  
 <span data-ttu-id="6e855-132">`With...End With` ステートメントは入れ子に配置できます。</span><span class="sxs-lookup"><span data-stu-id="6e855-132">You can place one `With...End With` statement within another.</span></span> <span data-ttu-id="6e855-133">入れ子の `With...End With` ステートメントは、参照されているオブジェクトがコンテキストから明確でない場合、混乱を招くことがあります。</span><span class="sxs-lookup"><span data-stu-id="6e855-133">Nested `With...End With` statements may be confusing if the objects that are being referred to aren't clear from context.</span></span> <span data-ttu-id="6e855-134">内側の `With` ブロックの内部からオブジェクトが参照された場合、外側の `With` ブロックにあるオブジェクトに対する完全修飾参照を提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e855-134">You must provide a fully qualified reference to an object that's in an outer `With` block when the object is referenced from within an inner `With` block.</span></span>  
  
 <span data-ttu-id="6e855-135">ブロック外から `With` ステートメント ブロックに分岐することはできません。</span><span class="sxs-lookup"><span data-stu-id="6e855-135">You can't branch into a `With` statement block from outside the block.</span></span>  
  
 <span data-ttu-id="6e855-136">ブロックの内部にループがなければ、ステートメントは一度だけ実行されます。</span><span class="sxs-lookup"><span data-stu-id="6e855-136">Unless the block contains a loop, the statements run only once.</span></span> <span data-ttu-id="6e855-137">さまざまな種類の制御構造を入れ子にできます。</span><span class="sxs-lookup"><span data-stu-id="6e855-137">You can nest different kinds of control structures.</span></span> <span data-ttu-id="6e855-138">詳細については、次を参照してください。[制御構造の入れ子になった](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)します。</span><span class="sxs-lookup"><span data-stu-id="6e855-138">For more information, see [Nested Control Structures](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6e855-139">また、オブジェクト初期化子で `With` キーワードを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="6e855-139">You can use the `With` keyword in object initializers also.</span></span> <span data-ttu-id="6e855-140">詳細と例については、次を参照してください。[オブジェクト初期化子。名前付きの匿名型](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)と[匿名型](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)します。</span><span class="sxs-lookup"><span data-stu-id="6e855-140">For more information and examples, see [Object Initializers: Named and Anonymous Types](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md) and [Anonymous Types](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).</span></span>  
>   
>  <span data-ttu-id="6e855-141">直前にインスタンス化したオブジェクトのプロパティまたはフィールドのみを `With` ブロックを使用して初期化する場合は、代わりにオブジェクト初期化子を使用することを考慮します。</span><span class="sxs-lookup"><span data-stu-id="6e855-141">If you're using a `With` block only to initialize the properties or fields of an object that you've just instantiated, consider using an object initializer instead.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6e855-142">例</span><span class="sxs-lookup"><span data-stu-id="6e855-142">Example</span></span>  
 <span data-ttu-id="6e855-143">次の例では、各 `With` ブロックが単一のオブジェクトに対して一連のステートメントを実行します。</span><span class="sxs-lookup"><span data-stu-id="6e855-143">In the following example, each `With` block executes a series of statements on a single object.</span></span>  
  
 [!code-vb[VbVbalrWithStatement#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrwithstatement/vb/mainwindow.xaml.vb#2)]  
  
## <a name="example"></a><span data-ttu-id="6e855-144">例</span><span class="sxs-lookup"><span data-stu-id="6e855-144">Example</span></span>  
 <span data-ttu-id="6e855-145">次の例では、`With…End With` ステートメントを入れ子にしています。</span><span class="sxs-lookup"><span data-stu-id="6e855-145">The following example nests `With…End With` statements.</span></span> <span data-ttu-id="6e855-146">入れ子にされた `With` ステートメント内の構文では、内側のオブジェクトを参照します。</span><span class="sxs-lookup"><span data-stu-id="6e855-146">Within the nested `With` statement, the syntax refers to the inner object.</span></span>  
  
 [!code-vb[VbVbalrWithStatement#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrwithstatement/vb/mainwindow.xaml.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="6e855-147">関連項目</span><span class="sxs-lookup"><span data-stu-id="6e855-147">See also</span></span>

- <xref:System.Collections.Generic.List%601>
- [<span data-ttu-id="6e855-148">入れ子になった制御構造</span><span class="sxs-lookup"><span data-stu-id="6e855-148">Nested Control Structures</span></span>](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)
- [<span data-ttu-id="6e855-149">オブジェクト初期化子:名前付きの匿名型</span><span class="sxs-lookup"><span data-stu-id="6e855-149">Object Initializers: Named and Anonymous Types</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)
- [<span data-ttu-id="6e855-150">匿名型</span><span class="sxs-lookup"><span data-stu-id="6e855-150">Anonymous Types</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)
