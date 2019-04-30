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
ms.openlocfilehash: 65fcd10521742e287c7934080b3352a06668df7a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61967982"
---
# <a name="special-characters-in-code-visual-basic"></a><span data-ttu-id="0bcdd-102">コード内の特殊文字 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0bcdd-102">Special Characters in Code (Visual Basic)</span></span>
<span data-ttu-id="0bcdd-103">アルファベットまたは数字ではない文字をコードでは、特殊文字を使用するがある場合があります。</span><span class="sxs-lookup"><span data-stu-id="0bcdd-103">Sometimes you have to use special characters in your code, that is, characters that are not alphabetical or numeric.</span></span> <span data-ttu-id="0bcdd-104">区切り記号および Visual Basic の文字セット内の特殊文字は、コンパイラやコンパイル済みプログラムを実行するタスクの定義をプログラム テキストの整理から、さまざまな用途があります。</span><span class="sxs-lookup"><span data-stu-id="0bcdd-104">The punctuation and special characters in the Visual Basic character set have various uses, from organizing program text to defining the tasks that the compiler or the compiled program performs.</span></span> <span data-ttu-id="0bcdd-105">実行するオペレーションを指定するのには使用されません。</span><span class="sxs-lookup"><span data-stu-id="0bcdd-105">They do not specify an operation to be performed.</span></span>  
  
## <a name="parentheses"></a><span data-ttu-id="0bcdd-106">かっこ</span><span class="sxs-lookup"><span data-stu-id="0bcdd-106">Parentheses</span></span>  
 <span data-ttu-id="0bcdd-107">など、プロシージャを定義するときに、かっこを使用して、`Sub`または`Function`します。</span><span class="sxs-lookup"><span data-stu-id="0bcdd-107">Use parentheses when you define a procedure, such as a `Sub` or `Function`.</span></span> <span data-ttu-id="0bcdd-108">すべてのプロシージャの引数リストをかっこで囲んでください。</span><span class="sxs-lookup"><span data-stu-id="0bcdd-108">You must enclose all procedure argument lists in parentheses.</span></span> <span data-ttu-id="0bcdd-109">複雑な式で演算子の優先順位の既定の順序を上書きするには、特に論理グループは、変数または引数を配置するかっこを使用します。</span><span class="sxs-lookup"><span data-stu-id="0bcdd-109">You also use parentheses for putting variables or arguments into logical groups, especially to override the default order of operator precedence in a complex expression.</span></span> <span data-ttu-id="0bcdd-110">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="0bcdd-110">The following example illustrates this.</span></span>  
  
 [!code-vb[VbVbcnConventions#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#11)]  
  
 <span data-ttu-id="0bcdd-111">次のコードでは、値の実行`d`8.225 しの値は、`e`は 3 です。</span><span class="sxs-lookup"><span data-stu-id="0bcdd-111">Following execution of the previous code, the value of `d` is 8.225 and the value of `e` is 3.</span></span> <span data-ttu-id="0bcdd-112">計算`d`の既定の優先順位を使用して`/`経由で`+`と等価`d = b + (c / a)`します。</span><span class="sxs-lookup"><span data-stu-id="0bcdd-112">The calculation for `d` uses the default precedence of `/` over `+` and is equivalent to `d = b + (c / a)`.</span></span> <span data-ttu-id="0bcdd-113">計算にかっこ`e`既定の優先順位をオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="0bcdd-113">The parentheses in the calculation for `e` override the default precedence.</span></span>  
  
## <a name="separators"></a><span data-ttu-id="0bcdd-114">[区切り記号]</span><span class="sxs-lookup"><span data-stu-id="0bcdd-114">Separators</span></span>  
 <span data-ttu-id="0bcdd-115">区切り記号はその名前が示す: コードのセクションを区切ります。</span><span class="sxs-lookup"><span data-stu-id="0bcdd-115">Separators do what their name suggests: they separate sections of code.</span></span> <span data-ttu-id="0bcdd-116">Visual basic での区切り記号はコロン (`:`)。</span><span class="sxs-lookup"><span data-stu-id="0bcdd-116">In Visual Basic, the separator character is the colon (`:`).</span></span> <span data-ttu-id="0bcdd-117">別の行ではなく 1 つの行に複数のステートメントを追加する場合は、区切り記号を使用します。</span><span class="sxs-lookup"><span data-stu-id="0bcdd-117">Use separators when you want to include multiple statements on a single line instead of separate lines.</span></span> <span data-ttu-id="0bcdd-118">これは、領域を節約し、コードの読みやすさが向上します。</span><span class="sxs-lookup"><span data-stu-id="0bcdd-118">This saves space and improves the readability of your code.</span></span> <span data-ttu-id="0bcdd-119">次の例では、コロンで区切られた 3 つのステートメントを示します。</span><span class="sxs-lookup"><span data-stu-id="0bcdd-119">The following example shows three statements separated by colons.</span></span>  
  
 [!code-vb[VbVbcnConventions#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#12)]  
  
 <span data-ttu-id="0bcdd-120">詳細については、「[方法 :分割および連結コード内でステートメント](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)します。</span><span class="sxs-lookup"><span data-stu-id="0bcdd-120">For more information, see [How to: Break and Combine Statements in Code](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md).</span></span>  
  
 <span data-ttu-id="0bcdd-121">コロン (`:`) 文字は、ステートメント ラベルを識別するためにも使用します。</span><span class="sxs-lookup"><span data-stu-id="0bcdd-121">The colon (`:`) character is also used to identify a statement label.</span></span> <span data-ttu-id="0bcdd-122">詳細については、「[方法 :ステートメントにラベル付け](../../../visual-basic/programming-guide/program-structure/how-to-label-statements.md)します。</span><span class="sxs-lookup"><span data-stu-id="0bcdd-122">For more information, see [How to: Label Statements](../../../visual-basic/programming-guide/program-structure/how-to-label-statements.md).</span></span>  
  
## <a name="concatenation"></a><span data-ttu-id="0bcdd-123">連結</span><span class="sxs-lookup"><span data-stu-id="0bcdd-123">Concatenation</span></span>  
 <span data-ttu-id="0bcdd-124">使用して、`&`演算子*連結*、または文字列を一緒にリンクします。</span><span class="sxs-lookup"><span data-stu-id="0bcdd-124">Use the `&` operator for *concatenation*, or linking strings together.</span></span> <span data-ttu-id="0bcdd-125">混同しないでください、`+`演算子で、数値を加算します。</span><span class="sxs-lookup"><span data-stu-id="0bcdd-125">Do not confuse it with the `+` operator, which adds together numeric values.</span></span> <span data-ttu-id="0bcdd-126">使用する場合、`+`数値の値を操作するときに連結する演算子が正しくない結果を取得することができます。</span><span class="sxs-lookup"><span data-stu-id="0bcdd-126">If you use the `+` operator to concatenate when you operate on numeric values, you can obtain incorrect results.</span></span> <span data-ttu-id="0bcdd-127">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="0bcdd-127">The following example demonstrates this.</span></span>  
  
 [!code-vb[VbVbcnConventions#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#13)]  
  
 <span data-ttu-id="0bcdd-128">次のコードでは、値の実行`resultA`21.01 しの値は、 `resultB` 「10.0111」です。</span><span class="sxs-lookup"><span data-stu-id="0bcdd-128">Following execution of the previous code, the value of `resultA` is 21.01 and the value of `resultB` is "10.0111".</span></span>  
  
## <a name="member-access-operators"></a><span data-ttu-id="0bcdd-129">メンバー アクセス演算子</span><span class="sxs-lookup"><span data-stu-id="0bcdd-129">Member Access Operators</span></span>  
 <span data-ttu-id="0bcdd-130">型のメンバーにアクセスするには、ドットを使用 (`.`)、または感嘆符 (`!`)、型名とメンバー名の間の演算子。</span><span class="sxs-lookup"><span data-stu-id="0bcdd-130">To access a member of a type, you use the dot (`.`) or exclamation point (`!`) operator between the type name and the member name.</span></span>  
  
### <a name="dot--operator"></a><span data-ttu-id="0bcdd-131">ドット (.)演算子</span><span class="sxs-lookup"><span data-stu-id="0bcdd-131">Dot (.) Operator</span></span>  
 <span data-ttu-id="0bcdd-132">使用して、`.`クラス、構造体、インターフェイス、または列挙体のメンバー アクセス演算子としての演算子。</span><span class="sxs-lookup"><span data-stu-id="0bcdd-132">Use the `.` operator on a class, structure, interface, or enumeration as a member access operator.</span></span> <span data-ttu-id="0bcdd-133">メンバーは、フィールド、プロパティ、イベント、またはメソッドにできます。</span><span class="sxs-lookup"><span data-stu-id="0bcdd-133">The member can be a field, property, event, or method.</span></span> <span data-ttu-id="0bcdd-134">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="0bcdd-134">The following example illustrates this.</span></span>  
  
 [!code-vb[VbVbcnConventions#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#14)]  
  
### <a name="exclamation-point--operator"></a><span data-ttu-id="0bcdd-135">感嘆符 (!)演算子</span><span class="sxs-lookup"><span data-stu-id="0bcdd-135">Exclamation Point (!) Operator</span></span>  
 <span data-ttu-id="0bcdd-136">使用して、`!`ディクショナリ アクセス演算子としてクラスまたはインターフェイスでのみ演算子。</span><span class="sxs-lookup"><span data-stu-id="0bcdd-136">Use the `!` operator only on a class or interface as a dictionary access operator.</span></span> <span data-ttu-id="0bcdd-137">クラスまたはインターフェイスが既定のプロパティを 1 つを受け入れる必要`String`引数。</span><span class="sxs-lookup"><span data-stu-id="0bcdd-137">The class or interface must have a default property that accepts a single `String` argument.</span></span> <span data-ttu-id="0bcdd-138">直後に続く識別子、`!`演算子に既定のプロパティを文字列として渡される引数値になります。</span><span class="sxs-lookup"><span data-stu-id="0bcdd-138">The identifier immediately following the `!` operator becomes the argument value passed to the default property as a string.</span></span> <span data-ttu-id="0bcdd-139">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="0bcdd-139">The following example demonstrates this.</span></span>  
  
 [!code-vb[VbVbcnConventions#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#15)]  
  
 <span data-ttu-id="0bcdd-140">3 つの出力行の`MsgBox`値を表示すべて`32856`します。</span><span class="sxs-lookup"><span data-stu-id="0bcdd-140">The three output lines of `MsgBox` all display the value `32856`.</span></span> <span data-ttu-id="0bcdd-141">最初の行がプロパティには、従来のアクセスを使用して`index`、2 番目のという事実を利用する`index`クラスの既定のプロパティは、 `hasDefault`、し、3 番目のクラスへのディクショナリを使用して。</span><span class="sxs-lookup"><span data-stu-id="0bcdd-141">The first line uses the traditional access to property `index`, the second makes use of the fact that `index` is the default property of class `hasDefault`, and the third uses dictionary access to the class.</span></span>  
  
 <span data-ttu-id="0bcdd-142">なお、2 番目のオペランドの`!`演算子は二重引用符で囲まれていない有効な Visual Basic 識別子である必要があります (`" "`)。</span><span class="sxs-lookup"><span data-stu-id="0bcdd-142">Note that the second operand of the `!` operator must be a valid Visual Basic identifier not enclosed in double quotation marks (`" "`).</span></span> <span data-ttu-id="0bcdd-143">つまり、リテラル文字列または文字列変数を使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="0bcdd-143">In other words, you cannot use a string literal or string variable.</span></span> <span data-ttu-id="0bcdd-144">次の行を最後の変更、`MsgBox`ための呼び出しにエラーが生成されます`"X"`は、囲まれた文字列リテラル。</span><span class="sxs-lookup"><span data-stu-id="0bcdd-144">The following change to the last line of the `MsgBox` call generates an error because `"X"` is an enclosed string literal.</span></span>  
  
 `"Dictionary access returns " & hD!"X")`  
  
> [!NOTE]
>  <span data-ttu-id="0bcdd-145">既定のコレクションへの参照を明示的にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="0bcdd-145">References to default collections must be explicit.</span></span> <span data-ttu-id="0bcdd-146">具体的には、使用することはできません、`!`演算子に対して遅延バインディングされた変数。</span><span class="sxs-lookup"><span data-stu-id="0bcdd-146">In particular, you cannot use the `!` operator on a late-bound variable.</span></span>  
  
 <span data-ttu-id="0bcdd-147">`!`としても使用される文字、`Single`文字を入力します。</span><span class="sxs-lookup"><span data-stu-id="0bcdd-147">The `!` character is also used as the `Single` type character.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0bcdd-148">関連項目</span><span class="sxs-lookup"><span data-stu-id="0bcdd-148">See also</span></span>

- [<span data-ttu-id="0bcdd-149">プログラム構造とコード規則</span><span class="sxs-lookup"><span data-stu-id="0bcdd-149">Program Structure and Code Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)
- [<span data-ttu-id="0bcdd-150">型文字</span><span class="sxs-lookup"><span data-stu-id="0bcdd-150">Type Characters</span></span>](../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)
