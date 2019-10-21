---
title: コード内の特殊文字 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.)
- vb.(
- vb.colon
- vb.!
- vb..
- 'vb.:'
helpviewer_keywords:
- special characters [Visual Basic], in code
- parentheses [Visual Basic], using in code
- colons (:)
- period character in code
- dot operator (.)
- dictionary access operator [Visual Basic]
- concatenation operators [Visual Basic], special characters in code
- concatenation operators [Visual Basic], vs. addition operator
- '! operator'
- separators [Visual Basic], using in code
- operators [Visual Basic], dictionary access
- ': separator character'
- member access operator [Visual Basic]
- addition operator [Visual Basic]
- operators [Visual Basic], member access
- . operator
- exclamation points
- separators
- exclamation point operator (!)
- Visual Basic code, special characters
ms.assetid: 310dce0c-45b5-4e0d-83e9-32df258d2a3e
ms.openlocfilehash: 95bef937912e35cd828bf0090b4cf48ccb3290cc
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69962474"
---
# <a name="special-characters-in-code-visual-basic"></a><span data-ttu-id="0b20e-102">コード内の特殊文字 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0b20e-102">Special Characters in Code (Visual Basic)</span></span>
<span data-ttu-id="0b20e-103">場合によっては、コードで特殊文字を使用する必要があります。つまり、アルファベットまたは数字以外の文字を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0b20e-103">Sometimes you have to use special characters in your code, that is, characters that are not alphabetical or numeric.</span></span> <span data-ttu-id="0b20e-104">Visual Basic 文字セットの句読点と特殊文字には、プログラムテキストの整理から、コンパイラまたはコンパイル済みプログラムによって実行されるタスクの定義まで、さまざまな用途があります。</span><span class="sxs-lookup"><span data-stu-id="0b20e-104">The punctuation and special characters in the Visual Basic character set have various uses, from organizing program text to defining the tasks that the compiler or the compiled program performs.</span></span> <span data-ttu-id="0b20e-105">実行するオペレーションを指定するのには使用されません。</span><span class="sxs-lookup"><span data-stu-id="0b20e-105">They do not specify an operation to be performed.</span></span>  
  
## <a name="parentheses"></a><span data-ttu-id="0b20e-106">かっこ</span><span class="sxs-lookup"><span data-stu-id="0b20e-106">Parentheses</span></span>  
 <span data-ttu-id="0b20e-107">やなどの`Sub`プロシージャを定義するときは`Function`、かっこを使用します。</span><span class="sxs-lookup"><span data-stu-id="0b20e-107">Use parentheses when you define a procedure, such as a `Sub` or `Function`.</span></span> <span data-ttu-id="0b20e-108">すべてのプロシージャ引数リストをかっこで囲む必要があります。</span><span class="sxs-lookup"><span data-stu-id="0b20e-108">You must enclose all procedure argument lists in parentheses.</span></span> <span data-ttu-id="0b20e-109">また、変数または引数を論理グループに含めるためにかっこを使用します。特に、複合式での演算子の優先順位の既定の順序をオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="0b20e-109">You also use parentheses for putting variables or arguments into logical groups, especially to override the default order of operator precedence in a complex expression.</span></span> <span data-ttu-id="0b20e-110">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="0b20e-110">The following example illustrates this.</span></span>  
  
 [!code-vb[VbVbcnConventions#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#11)]  
  
 <span data-ttu-id="0b20e-111">前のコードの実行後、の`d`値は8.225 で、の`e`値は3です。</span><span class="sxs-lookup"><span data-stu-id="0b20e-111">Following execution of the previous code, the value of `d` is 8.225 and the value of `e` is 3.</span></span> <span data-ttu-id="0b20e-112">の`d`計算では、 `+`の既定の`/`優先順位が使用さ`d = b + (c / a)`れます。これはと同じです。</span><span class="sxs-lookup"><span data-stu-id="0b20e-112">The calculation for `d` uses the default precedence of `/` over `+` and is equivalent to `d = b + (c / a)`.</span></span> <span data-ttu-id="0b20e-113">の`e`計算のかっこは、既定の優先順位よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="0b20e-113">The parentheses in the calculation for `e` override the default precedence.</span></span>  
  
## <a name="separators"></a><span data-ttu-id="0b20e-114">区切り記号</span><span class="sxs-lookup"><span data-stu-id="0b20e-114">Separators</span></span>  
 <span data-ttu-id="0b20e-115">区切り記号は、コードのセクションを分離します。</span><span class="sxs-lookup"><span data-stu-id="0b20e-115">Separators do what their name suggests: they separate sections of code.</span></span> <span data-ttu-id="0b20e-116">Visual Basic では、区切り文字はコロン (`:`) です。</span><span class="sxs-lookup"><span data-stu-id="0b20e-116">In Visual Basic, the separator character is the colon (`:`).</span></span> <span data-ttu-id="0b20e-117">複数のステートメントを別々の行ではなく 1 行に含めたい場合は、区切り記号を使用します。</span><span class="sxs-lookup"><span data-stu-id="0b20e-117">Use separators when you want to include multiple statements on a single line instead of separate lines.</span></span> <span data-ttu-id="0b20e-118">これにより、領域が節約され、コードの読みやすさが向上します。</span><span class="sxs-lookup"><span data-stu-id="0b20e-118">This saves space and improves the readability of your code.</span></span> <span data-ttu-id="0b20e-119">次の例では、コロンで区切られた 3 つのステートメントを示します。</span><span class="sxs-lookup"><span data-stu-id="0b20e-119">The following example shows three statements separated by colons.</span></span>  
  
 [!code-vb[VbVbcnConventions#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#12)]  
  
 <span data-ttu-id="0b20e-120">詳細については、「[方法 :コード](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)内のステートメントを分割し、結合します。</span><span class="sxs-lookup"><span data-stu-id="0b20e-120">For more information, see [How to: Break and Combine Statements in Code](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md).</span></span>  
  
 <span data-ttu-id="0b20e-121">コロン (`:`) 文字は、ステートメントラベルを識別するためにも使用されます。</span><span class="sxs-lookup"><span data-stu-id="0b20e-121">The colon (`:`) character is also used to identify a statement label.</span></span> <span data-ttu-id="0b20e-122">詳細については、「[方法 :ラベルステートメント](../../../visual-basic/programming-guide/program-structure/how-to-label-statements.md)。</span><span class="sxs-lookup"><span data-stu-id="0b20e-122">For more information, see [How to: Label Statements](../../../visual-basic/programming-guide/program-structure/how-to-label-statements.md).</span></span>  
  
## <a name="concatenation"></a><span data-ttu-id="0b20e-123">連結</span><span class="sxs-lookup"><span data-stu-id="0b20e-123">Concatenation</span></span>  
 <span data-ttu-id="0b20e-124">*連結*、すなわち文字列を連結するには `&` 演算子を使用します。</span><span class="sxs-lookup"><span data-stu-id="0b20e-124">Use the `&` operator for *concatenation*, or linking strings together.</span></span> <span data-ttu-id="0b20e-125">数値を加算する `+` 演算子と混同しないようにしてください。</span><span class="sxs-lookup"><span data-stu-id="0b20e-125">Do not confuse it with the `+` operator, which adds together numeric values.</span></span> <span data-ttu-id="0b20e-126">数値を操作するときに `+` 演算子を使用して連結すると、不適切な結果を得ることがあります。</span><span class="sxs-lookup"><span data-stu-id="0b20e-126">If you use the `+` operator to concatenate when you operate on numeric values, you can obtain incorrect results.</span></span> <span data-ttu-id="0b20e-127">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="0b20e-127">The following example demonstrates this.</span></span>  
  
 [!code-vb[VbVbcnConventions#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#13)]  
  
 <span data-ttu-id="0b20e-128">前のコードの実行後、の`resultA`値は21.01 で、の`resultB`値は "10.0111" です。</span><span class="sxs-lookup"><span data-stu-id="0b20e-128">Following execution of the previous code, the value of `resultA` is 21.01 and the value of `resultB` is "10.0111".</span></span>  
  
## <a name="member-access-operators"></a><span data-ttu-id="0b20e-129">メンバーアクセス演算子</span><span class="sxs-lookup"><span data-stu-id="0b20e-129">Member Access Operators</span></span>  
 <span data-ttu-id="0b20e-130">型のメンバーにアクセスするには、型名とメンバー名の間にドット (`.`) または感嘆符 (`!`) 演算子を使用します。</span><span class="sxs-lookup"><span data-stu-id="0b20e-130">To access a member of a type, you use the dot (`.`) or exclamation point (`!`) operator between the type name and the member name.</span></span>  
  
### <a name="dot--operator"></a><span data-ttu-id="0b20e-131">ドット (.)演算子</span><span class="sxs-lookup"><span data-stu-id="0b20e-131">Dot (.) Operator</span></span>  
 <span data-ttu-id="0b20e-132">メンバーアクセス演算子として、クラス、構造体、インターフェイス、または列挙体に対して演算子を使用します。`.`</span><span class="sxs-lookup"><span data-stu-id="0b20e-132">Use the `.` operator on a class, structure, interface, or enumeration as a member access operator.</span></span> <span data-ttu-id="0b20e-133">メンバーには、フィールド、プロパティ、イベント、またはメソッドを指定できます。</span><span class="sxs-lookup"><span data-stu-id="0b20e-133">The member can be a field, property, event, or method.</span></span> <span data-ttu-id="0b20e-134">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="0b20e-134">The following example illustrates this.</span></span>  
  
 [!code-vb[VbVbcnConventions#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#14)]  
  
### <a name="exclamation-point--operator"></a><span data-ttu-id="0b20e-135">感嘆符 (!)演算子</span><span class="sxs-lookup"><span data-stu-id="0b20e-135">Exclamation Point (!) Operator</span></span>  
 <span data-ttu-id="0b20e-136">`!` 演算子は 、クラスまたはインターフェイスに対してのみ、ディクショナリアクセス演算子として使用します。</span><span class="sxs-lookup"><span data-stu-id="0b20e-136">Use the `!` operator only on a class or interface as a dictionary access operator.</span></span> <span data-ttu-id="0b20e-137">クラスまたはインターフェイスには、1 つの `String` 型の引数を受け取る既定のプロパティが必要です。</span><span class="sxs-lookup"><span data-stu-id="0b20e-137">The class or interface must have a default property that accepts a single `String` argument.</span></span> <span data-ttu-id="0b20e-138">`!` 演算子の直後にある識別子は、既定のプロパティに文字列として渡される引数の値になります。</span><span class="sxs-lookup"><span data-stu-id="0b20e-138">The identifier immediately following the `!` operator becomes the argument value passed to the default property as a string.</span></span> <span data-ttu-id="0b20e-139">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="0b20e-139">The following example demonstrates this.</span></span>  
  
 [!code-vb[VbVbcnConventions#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#15)]  
  
 <span data-ttu-id="0b20e-140">すべてのの3つ`MsgBox`の出力行に`32856`値が表示されます。</span><span class="sxs-lookup"><span data-stu-id="0b20e-140">The three output lines of `MsgBox` all display the value `32856`.</span></span> <span data-ttu-id="0b20e-141">最初の行では、プロパティ`index`への従来のアクセスを使用します。2番目の行では、クラス`hasDefault`の既定のプロパティである`index`ファクトを使用し、3番目の行ではクラスへのディクショナリアクセスを使用します。</span><span class="sxs-lookup"><span data-stu-id="0b20e-141">The first line uses the traditional access to property `index`, the second makes use of the fact that `index` is the default property of class `hasDefault`, and the third uses dictionary access to the class.</span></span>  
  
 <span data-ttu-id="0b20e-142">`!`演算子の2番目のオペランドは、二重引用符 (`" "`) で囲まれていない有効な Visual Basic 識別子である必要があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="0b20e-142">Note that the second operand of the `!` operator must be a valid Visual Basic identifier not enclosed in double quotation marks (`" "`).</span></span> <span data-ttu-id="0b20e-143">つまり、文字列リテラルまたは文字列変数を使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="0b20e-143">In other words, you cannot use a string literal or string variable.</span></span> <span data-ttu-id="0b20e-144">`MsgBox`呼び出しの最後の行に次の変更を行うと、は`"X"`囲まれた文字列リテラルであるため、エラーが生成されます。</span><span class="sxs-lookup"><span data-stu-id="0b20e-144">The following change to the last line of the `MsgBox` call generates an error because `"X"` is an enclosed string literal.</span></span>  
  
 `"Dictionary access returns " & hD!"X")`  
  
> [!NOTE]
> <span data-ttu-id="0b20e-145">既定のコレクションへの参照は明示的に指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0b20e-145">References to default collections must be explicit.</span></span> <span data-ttu-id="0b20e-146">特に、遅延バインディング変数に対して `!` 演算子を使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="0b20e-146">In particular, you cannot use the `!` operator on a late-bound variable.</span></span>  
  
 <span data-ttu-id="0b20e-147">文字は、 `Single`型文字としても使用されます。 `!`</span><span class="sxs-lookup"><span data-stu-id="0b20e-147">The `!` character is also used as the `Single` type character.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b20e-148">関連項目</span><span class="sxs-lookup"><span data-stu-id="0b20e-148">See also</span></span>

- [<span data-ttu-id="0b20e-149">プログラム構造とコード規則</span><span class="sxs-lookup"><span data-stu-id="0b20e-149">Program Structure and Code Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)
- [<span data-ttu-id="0b20e-150">型文字</span><span class="sxs-lookup"><span data-stu-id="0b20e-150">Type Characters</span></span>](../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)
