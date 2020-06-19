---
title: コード内の特殊文字
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
ms.openlocfilehash: c9b170ed812474cdeee100f1dc388d5c7e85f2cc
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400592"
---
# <a name="special-characters-in-code-visual-basic"></a><span data-ttu-id="f0687-102">コード内の特殊文字 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f0687-102">Special Characters in Code (Visual Basic)</span></span>
<span data-ttu-id="f0687-103">コードで特殊文字 (アルファベットまたは数字以外の文字) を使用することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="f0687-103">Sometimes you have to use special characters in your code, that is, characters that are not alphabetical or numeric.</span></span> <span data-ttu-id="f0687-104">Visual Basic の文字セットに含まれる区切り文字と特殊文字には、プログラム テキストの整理から、コンパイラやコンパイル済みプログラムが実行するタスクの定義まで、さまざまな用途があります。</span><span class="sxs-lookup"><span data-stu-id="f0687-104">The punctuation and special characters in the Visual Basic character set have various uses, from organizing program text to defining the tasks that the compiler or the compiled program performs.</span></span> <span data-ttu-id="f0687-105">実行するオペレーションを指定するのには使用されません。</span><span class="sxs-lookup"><span data-stu-id="f0687-105">They do not specify an operation to be performed.</span></span>  
  
## <a name="parentheses"></a><span data-ttu-id="f0687-106">かっこ</span><span class="sxs-lookup"><span data-stu-id="f0687-106">Parentheses</span></span>  
 <span data-ttu-id="f0687-107">かっこは、`Sub` や `Function` などのプロシージャを定義するときに使用します。</span><span class="sxs-lookup"><span data-stu-id="f0687-107">Use parentheses when you define a procedure, such as a `Sub` or `Function`.</span></span> <span data-ttu-id="f0687-108">プロシージャのすべての引数リストをかっこで囲む必要があります。</span><span class="sxs-lookup"><span data-stu-id="f0687-108">You must enclose all procedure argument lists in parentheses.</span></span> <span data-ttu-id="f0687-109">特に、複雑な式で演算子の既定の優先順位をオーバーライドするために、変数や引数を論理グループに配置する際にもかっこを使用します。</span><span class="sxs-lookup"><span data-stu-id="f0687-109">You also use parentheses for putting variables or arguments into logical groups, especially to override the default order of operator precedence in a complex expression.</span></span> <span data-ttu-id="f0687-110">次の例を使って説明します。</span><span class="sxs-lookup"><span data-stu-id="f0687-110">The following example illustrates this.</span></span>  
  
 [!code-vb[VbVbcnConventions#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#11)]  
  
 <span data-ttu-id="f0687-111">上記のコードの実行後、`d` の値は 8.225、`e` の値は 3 になります。</span><span class="sxs-lookup"><span data-stu-id="f0687-111">Following execution of the previous code, the value of `d` is 8.225 and the value of `e` is 3.</span></span> <span data-ttu-id="f0687-112">`d` の計算では、`+` よりも `/` が優先される既定の優先順位が使用されます。これは、`d = b + (c / a)` と同じです。</span><span class="sxs-lookup"><span data-stu-id="f0687-112">The calculation for `d` uses the default precedence of `/` over `+` and is equivalent to `d = b + (c / a)`.</span></span> <span data-ttu-id="f0687-113">`e` の計算のかっこは、既定の優先順位をオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="f0687-113">The parentheses in the calculation for `e` override the default precedence.</span></span>  
  
## <a name="separators"></a><span data-ttu-id="f0687-114">[区切り記号]</span><span class="sxs-lookup"><span data-stu-id="f0687-114">Separators</span></span>  
 <span data-ttu-id="f0687-115">区切り文字は、その名前が示すとおり、コードのセクションを区切ります。</span><span class="sxs-lookup"><span data-stu-id="f0687-115">Separators do what their name suggests: they separate sections of code.</span></span> <span data-ttu-id="f0687-116">Visual Basic では、区切り文字はコロン (`:`) です。</span><span class="sxs-lookup"><span data-stu-id="f0687-116">In Visual Basic, the separator character is the colon (`:`).</span></span> <span data-ttu-id="f0687-117">別々の行ではなく、1 つの行に複数のステートメントを含める場合は、区切り文字を使用します。</span><span class="sxs-lookup"><span data-stu-id="f0687-117">Use separators when you want to include multiple statements on a single line instead of separate lines.</span></span> <span data-ttu-id="f0687-118">これにより、スペースが節約され、コードが読みやすくなります。</span><span class="sxs-lookup"><span data-stu-id="f0687-118">This saves space and improves the readability of your code.</span></span> <span data-ttu-id="f0687-119">次の例は、コロンで区切られた 3 つのステートメントを示しています。</span><span class="sxs-lookup"><span data-stu-id="f0687-119">The following example shows three statements separated by colons.</span></span>  
  
 [!code-vb[VbVbcnConventions#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#12)]  
  
 <span data-ttu-id="f0687-120">詳細については、「[方法:コード内でステートメントを分割および連結する](how-to-break-and-combine-statements-in-code.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="f0687-120">For more information, see [How to: Break and Combine Statements in Code](how-to-break-and-combine-statements-in-code.md).</span></span>  
  
 <span data-ttu-id="f0687-121">コロン (`:`) 文字は、ステートメント ラベルの識別にも使用されます。</span><span class="sxs-lookup"><span data-stu-id="f0687-121">The colon (`:`) character is also used to identify a statement label.</span></span> <span data-ttu-id="f0687-122">詳細については、「[方法:ステートメントにラベルを付ける](how-to-label-statements.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="f0687-122">For more information, see [How to: Label Statements](how-to-label-statements.md).</span></span>  
  
## <a name="concatenation"></a><span data-ttu-id="f0687-123">連結</span><span class="sxs-lookup"><span data-stu-id="f0687-123">Concatenation</span></span>  
 <span data-ttu-id="f0687-124">`&` 演算子は、"*連結*" (文字列の結合) に使用します。</span><span class="sxs-lookup"><span data-stu-id="f0687-124">Use the `&` operator for *concatenation*, or linking strings together.</span></span> <span data-ttu-id="f0687-125">数値を加算する `+` 演算子と混同しないでください。</span><span class="sxs-lookup"><span data-stu-id="f0687-125">Do not confuse it with the `+` operator, which adds together numeric values.</span></span> <span data-ttu-id="f0687-126">数値を操作するときに `+` 演算子を使用して連結すると、間違った結果を得る可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f0687-126">If you use the `+` operator to concatenate when you operate on numeric values, you can obtain incorrect results.</span></span> <span data-ttu-id="f0687-127">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="f0687-127">The following example demonstrates this.</span></span>  
  
 [!code-vb[VbVbcnConventions#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#13)]  
  
 <span data-ttu-id="f0687-128">上記のコードの実行後、`resultA` の値は 21.01、`resultB` の値は "10.0111" になります。</span><span class="sxs-lookup"><span data-stu-id="f0687-128">Following execution of the previous code, the value of `resultA` is 21.01 and the value of `resultB` is "10.0111".</span></span>  
  
## <a name="member-access-operators"></a><span data-ttu-id="f0687-129">メンバー アクセス演算子</span><span class="sxs-lookup"><span data-stu-id="f0687-129">Member Access Operators</span></span>  
 <span data-ttu-id="f0687-130">型のメンバーにアクセスするには、型名とメンバー名の間にドット (`.`) または感嘆符 (`!`) 演算子を使用します。</span><span class="sxs-lookup"><span data-stu-id="f0687-130">To access a member of a type, you use the dot (`.`) or exclamation point (`!`) operator between the type name and the member name.</span></span>  
  
### <a name="dot--operator"></a><span data-ttu-id="f0687-131">ドット (.) 演算子</span><span class="sxs-lookup"><span data-stu-id="f0687-131">Dot (.) Operator</span></span>  
 <span data-ttu-id="f0687-132">`.` 演算子は、クラス、構造体、インターフェイス、または列挙型でメンバー アクセス演算子として使用します。</span><span class="sxs-lookup"><span data-stu-id="f0687-132">Use the `.` operator on a class, structure, interface, or enumeration as a member access operator.</span></span> <span data-ttu-id="f0687-133">メンバーには、フィールド、プロパティ、イベント、またはメソッドを指定できます。</span><span class="sxs-lookup"><span data-stu-id="f0687-133">The member can be a field, property, event, or method.</span></span> <span data-ttu-id="f0687-134">次の例を使って説明します。</span><span class="sxs-lookup"><span data-stu-id="f0687-134">The following example illustrates this.</span></span>  
  
 [!code-vb[VbVbcnConventions#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#14)]  
  
### <a name="exclamation-point--operator"></a><span data-ttu-id="f0687-135">感嘆符 (!) 演算子</span><span class="sxs-lookup"><span data-stu-id="f0687-135">Exclamation Point (!) Operator</span></span>  
 <span data-ttu-id="f0687-136">`!` 演算子は、ディクショナリ アクセス演算子としてクラスまたはインターフェイスでのみ使用します。</span><span class="sxs-lookup"><span data-stu-id="f0687-136">Use the `!` operator only on a class or interface as a dictionary access operator.</span></span> <span data-ttu-id="f0687-137">クラスまたはインターフェイスには、単一の `String` 引数を受け入れる既定のプロパティが必要です。</span><span class="sxs-lookup"><span data-stu-id="f0687-137">The class or interface must have a default property that accepts a single `String` argument.</span></span> <span data-ttu-id="f0687-138">`!` 演算子の直後の識別子は、既定のプロパティに文字列として渡される引数値になります。</span><span class="sxs-lookup"><span data-stu-id="f0687-138">The identifier immediately following the `!` operator becomes the argument value passed to the default property as a string.</span></span> <span data-ttu-id="f0687-139">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="f0687-139">The following example demonstrates this.</span></span>  
  
 [!code-vb[VbVbcnConventions#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#15)]  
  
 <span data-ttu-id="f0687-140">`MsgBox` の 3 つの出力行では、いずれも値 `32856` が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f0687-140">The three output lines of `MsgBox` all display the value `32856`.</span></span> <span data-ttu-id="f0687-141">1 行目では、`index` プロパティへの従来のアクセスを使用し、2 行目では、`index` が `hasDefault` クラスの既定のプロパティであることを利用しています。3 行目では、クラスへのディクショナリ アクセスを使用しています。</span><span class="sxs-lookup"><span data-stu-id="f0687-141">The first line uses the traditional access to property `index`, the second makes use of the fact that `index` is the default property of class `hasDefault`, and the third uses dictionary access to the class.</span></span>  
  
 <span data-ttu-id="f0687-142">`!` 演算子の 2 番目のオペランドは、二重引用符 (`" "`) で囲まれていない有効な Visual Basic 識別子である必要があります。</span><span class="sxs-lookup"><span data-stu-id="f0687-142">Note that the second operand of the `!` operator must be a valid Visual Basic identifier not enclosed in double quotation marks (`" "`).</span></span> <span data-ttu-id="f0687-143">つまり、文字列リテラルや文字列変数は使用できません。</span><span class="sxs-lookup"><span data-stu-id="f0687-143">In other words, you cannot use a string literal or string variable.</span></span> <span data-ttu-id="f0687-144">`"X"` は囲まれた文字列リテラルであるため、`MsgBox` 呼び出しの最後の行を次のように変更すると、エラーが生成されます。</span><span class="sxs-lookup"><span data-stu-id="f0687-144">The following change to the last line of the `MsgBox` call generates an error because `"X"` is an enclosed string literal.</span></span>  
  
 `"Dictionary access returns " & hD!"X")`  
  
> [!NOTE]
> <span data-ttu-id="f0687-145">既定のコレクションへの参照は明示的である必要があります。</span><span class="sxs-lookup"><span data-stu-id="f0687-145">References to default collections must be explicit.</span></span> <span data-ttu-id="f0687-146">特に、遅延バインディング変数で `!` 演算子を使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="f0687-146">In particular, you cannot use the `!` operator on a late-bound variable.</span></span>  
  
 <span data-ttu-id="f0687-147">`!` 文字は、`Single` 型の文字としても使用されます。</span><span class="sxs-lookup"><span data-stu-id="f0687-147">The `!` character is also used as the `Single` type character.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0687-148">関連項目</span><span class="sxs-lookup"><span data-stu-id="f0687-148">See also</span></span>

- [<span data-ttu-id="f0687-149">プログラム構造とコード規則</span><span class="sxs-lookup"><span data-stu-id="f0687-149">Program Structure and Code Conventions</span></span>](program-structure-and-code-conventions.md)
- [<span data-ttu-id="f0687-150">型文字</span><span class="sxs-lookup"><span data-stu-id="f0687-150">Type Characters</span></span>](../language-features/data-types/type-characters.md)
