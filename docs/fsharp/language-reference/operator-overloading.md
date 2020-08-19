---
title: 演算子のオーバーロード
description: 'クラス、レコード型、および F # のグローバルレベルで算術演算子をオーバーロードする方法について説明します。'
ms.date: 08/15/2020
ms.openlocfilehash: fb86ceb95101fcc1f157ec9ba17a9d8145b11a91
ms.sourcegitcommit: 8bfeb5930ca48b2ee6053f16082dcaf24d46d221
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/18/2020
ms.locfileid: "88557582"
---
# <a name="operator-overloading"></a><span data-ttu-id="dcac0-103">演算子のオーバーロード</span><span class="sxs-lookup"><span data-stu-id="dcac0-103">Operator Overloading</span></span>

<span data-ttu-id="dcac0-104">このトピックでは、クラス型またはレコード型の算術演算子をオーバーロードする方法と、グローバル レベルで算術演算子をオーバーロードする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="dcac0-104">This topic describes how to overload arithmetic operators in a class or record type, and at the global level.</span></span>

## <a name="syntax"></a><span data-ttu-id="dcac0-105">構文</span><span class="sxs-lookup"><span data-stu-id="dcac0-105">Syntax</span></span>

```fsharp
// Overloading an operator as a class or record member.
static member (operator-symbols) (parameter-list) =
    method-body
// Overloading an operator at the global level
let [inline] (operator-symbols) parameter-list = function-body
```

## <a name="remarks"></a><span data-ttu-id="dcac0-106">解説</span><span class="sxs-lookup"><span data-stu-id="dcac0-106">Remarks</span></span>

<span data-ttu-id="dcac0-107">前の構文では、 *演算子記号* は、、、、、などの1つです `+` `-` `*` `/` `=` 。</span><span class="sxs-lookup"><span data-stu-id="dcac0-107">In the previous syntax, the *operator-symbol* is one of `+`, `-`, `*`, `/`, `=`, and so on.</span></span> <span data-ttu-id="dcac0-108">*パラメーターリスト*は、その演算子の通常の構文で表示される順序でオペランドを指定します。</span><span class="sxs-lookup"><span data-stu-id="dcac0-108">The *parameter-list* specifies the operands in the order they appear in the usual syntax for that operator.</span></span> <span data-ttu-id="dcac0-109">*メソッド本体*は、結果として得られる値を構築します。</span><span class="sxs-lookup"><span data-stu-id="dcac0-109">The *method-body* constructs the resulting value.</span></span>

<span data-ttu-id="dcac0-110">演算子のオーバーロードには、static を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dcac0-110">Operator overloads for operators must be static.</span></span> <span data-ttu-id="dcac0-111">やなどの単項演算子のオーバーロードでは、演算子が `+` `-` 単項演算子であり、次の `~` 宣言に示すように、二項演算子ではないことを示すために、演算子 *記号* でチルダ () を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dcac0-111">Operator overloads for unary operators, such as `+` and `-`, must use a tilde (`~`) in the *operator-symbol* to indicate that the operator is a unary operator and not a binary operator, as shown in the following declaration.</span></span>

```fsharp
static member (~-) (v : Vector)
```

<span data-ttu-id="dcac0-112">次のコードは、演算子を 2 つだけ含むベクター クラスを示しています。その 1 つは単項マイナス演算子で、もう 1 つはスカラーによる乗算演算子です。</span><span class="sxs-lookup"><span data-stu-id="dcac0-112">The following code illustrates a vector class that has just two operators, one for unary minus and one for multiplication by a scalar.</span></span> <span data-ttu-id="dcac0-113">この例では、ベクターとスカラーの記述順序とは無関係に演算子が機能する必要があるため、必要となるスカラー乗算のオーバーロードは 2 つです。</span><span class="sxs-lookup"><span data-stu-id="dcac0-113">In the example, two overloads for scalar multiplication are needed because the operator must work regardless of the order in which the vector and scalar appear.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4001.fs)]

## <a name="creating-new-operators"></a><span data-ttu-id="dcac0-114">新しい演算子の作成</span><span class="sxs-lookup"><span data-stu-id="dcac0-114">Creating New Operators</span></span>

<span data-ttu-id="dcac0-115">標準演算子はすべてオーバーロードすることができますが、特定の文字を並べて新しい演算子を作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="dcac0-115">You can overload all the standard operators, but you can also create new operators out of sequences of certain characters.</span></span> <span data-ttu-id="dcac0-116">使用できる演算子の文字は、、、、、、、、、、、、、、、、 `!` `%` `&` `*` `+` `-` `.` `/` `<` `=` `>` `?` `@` `^` `|` および `~` です。</span><span class="sxs-lookup"><span data-stu-id="dcac0-116">Allowed operator characters are `!`, `%`, `&`, `*`, `+`, `-`, `.`, `/`, `<`, `=`, `>`, `?`, `@`, `^`, `|`, and `~`.</span></span> <span data-ttu-id="dcac0-117">`~` には、演算子を単項演算子にするという特別な意味があるため、演算子の文字シーケンスに含めることはできません。</span><span class="sxs-lookup"><span data-stu-id="dcac0-117">The `~` character has the special meaning of making an operator unary, and is not part of the operator character sequence.</span></span> <span data-ttu-id="dcac0-118">すべての演算子を単項にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="dcac0-118">Not all operators can be made unary.</span></span>

<span data-ttu-id="dcac0-119">作成した演算子は、使用した厳密な文字シーケンスに従って、特定の優先順位と結合規則を持つようになります。</span><span class="sxs-lookup"><span data-stu-id="dcac0-119">Depending on the exact character sequence you use, your operator will have a certain precedence and associativity.</span></span> <span data-ttu-id="dcac0-120">結合規則を使用する方向は、左から右にすることも、右から左にすることもできます。シーケンスの中で同じレベルの優先順位を持つ演算子を、かっこを使用せずに記述する場合は、必ず結合規則を使用します。</span><span class="sxs-lookup"><span data-stu-id="dcac0-120">Associativity can be either left to right or right to left and is used whenever operators of the same level of precedence appear in sequence without parentheses.</span></span>

<span data-ttu-id="dcac0-121">演算子文字の `.` は、優先順位に影響しません。そのため、通常の乗算演算子と同じ優先順位と結合規則を持つ独自の形式の乗算演算子を定義する場合などに、`.*` のような演算子を作成できます。</span><span class="sxs-lookup"><span data-stu-id="dcac0-121">The operator character `.` does not affect precedence, so that, for example, if you want to define your own version of multiplication that has the same precedence and associativity as ordinary multiplication, you could create operators such as `.*`.</span></span>

<span data-ttu-id="dcac0-122">とで始まるのは演算子だけ `?` `?<-` `?` です。</span><span class="sxs-lookup"><span data-stu-id="dcac0-122">Only the operators `?` and `?<-` may start with `?`.</span></span>

<span data-ttu-id="dcac0-123">F # のすべての演算子の優先順位を示す表は、「 [シンボルと演算子のリファレンス](./symbol-and-operator-reference/index.md)」で確認できます。</span><span class="sxs-lookup"><span data-stu-id="dcac0-123">A table that shows the precedence of all operators in F# can be found in [Symbol and Operator Reference](./symbol-and-operator-reference/index.md).</span></span>

## <a name="overloaded-operator-names"></a><span data-ttu-id="dcac0-124">オーバーロードされた演算子の名前</span><span class="sxs-lookup"><span data-stu-id="dcac0-124">Overloaded Operator Names</span></span>

<span data-ttu-id="dcac0-125">F# コンパイラが演算子の式をコンパイルするときに、その演算子のメソッドが生成されます。このメソッドには、コンパイラにより生成された名前が付けられます。</span><span class="sxs-lookup"><span data-stu-id="dcac0-125">When the F# compiler compiles an operator expression, it generates a method that has a compiler-generated name for that operator.</span></span> <span data-ttu-id="dcac0-126">これは、このメソッドの Microsoft Intermediate Language (MSIL) で使用される名前です。また、リフレクションと IntelliSense でも使用されます。</span><span class="sxs-lookup"><span data-stu-id="dcac0-126">This is the name that appears in the Microsoft intermediate language (MSIL) for the method, and also in reflection and IntelliSense.</span></span> <span data-ttu-id="dcac0-127">通常、この名前を F# コードで使用する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="dcac0-127">You do not normally need to use these names in F# code.</span></span>

<span data-ttu-id="dcac0-128">次の表に、標準演算子と生成される名前を示します。</span><span class="sxs-lookup"><span data-stu-id="dcac0-128">The following table shows the standard operators and their corresponding generated names.</span></span>

|<span data-ttu-id="dcac0-129">演算子</span><span class="sxs-lookup"><span data-stu-id="dcac0-129">Operator</span></span>|<span data-ttu-id="dcac0-130">生成された名前</span><span class="sxs-lookup"><span data-stu-id="dcac0-130">Generated name</span></span>|
|--------|--------------|
|`[]`|`op_Nil`|
|`::`|`op_Cons`|
|`+`|`op_Addition`|
|`-`|`op_Subtraction`|
|`*`|`op_Multiply`|
|`/`|`op_Division`|
|`@`|`op_Append`|
|`^`|`op_Concatenate`|
|`%`|`op_Modulus`|
|`&&&`|`op_BitwiseAnd`|
|<code>&#124;&#124;&#124;</code>|`op_BitwiseOr`|
|`^^^`|`op_ExclusiveOr`|
|`<<<`|`op_LeftShift`|
|`~~~`|`op_LogicalNot`|
|`>>>`|`op_RightShift`|
|`~+`|`op_UnaryPlus`|
|`~-`|`op_UnaryNegation`|
|`=`|`op_Equality`|
|`<=`|`op_LessThanOrEqual`|
|`>=`|`op_GreaterThanOrEqual`|
|`<`|`op_LessThan`|
|`>`|`op_GreaterThan`|
|`?`|`op_Dynamic`|
|`?<-`|`op_DynamicAssignment`|
|<code>&#124;></code>|`op_PipeRight`|
|<code><&#124;</code>|`op_PipeLeft`|
|`!`|`op_Dereference`|
|`>>`|`op_ComposeRight`|
|`<<`|`op_ComposeLeft`|
|`<@ @>`|`op_Quotation`|
|`<@@ @@>`|`op_QuotationUntyped`|
|`+=`|`op_AdditionAssignment`|
|`-=`|`op_SubtractionAssignment`|
|`*=`|`op_MultiplyAssignment`|
|`/=`|`op_DivisionAssignment`|
|`..`|`op_Range`|
|`.. ..`|`op_RangeStep`|

<span data-ttu-id="dcac0-131">`not`F # の演算子は、 `op_Inequality` シンボリック演算子ではないため、生成されないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="dcac0-131">Note that the `not` operator in F# does not emit `op_Inequality` because it is not a symbolic operator.</span></span> <span data-ttu-id="dcac0-132">これは、ブール式を否定する IL を生成する関数です。</span><span class="sxs-lookup"><span data-stu-id="dcac0-132">It is a function that emits IL that negates a boolean expression.</span></span>

<span data-ttu-id="dcac0-133">ここに記載されていないその他の演算子文字の組み合わせも演算子として使用できます。その場合の名前は、次の表の各文字の名前を連結して生成されます。</span><span class="sxs-lookup"><span data-stu-id="dcac0-133">Other combinations of operator characters that are not listed here can be used as operators and have names that are made up by concatenating names for the individual characters from the following table.</span></span> <span data-ttu-id="dcac0-134">たとえば、+!</span><span class="sxs-lookup"><span data-stu-id="dcac0-134">For example, +!</span></span> <span data-ttu-id="dcac0-135"> は `op_PlusBang` になります。</span><span class="sxs-lookup"><span data-stu-id="dcac0-135">becomes `op_PlusBang`.</span></span>

|<span data-ttu-id="dcac0-136">演算子文字</span><span class="sxs-lookup"><span data-stu-id="dcac0-136">Operator character</span></span>|<span data-ttu-id="dcac0-137">Name</span><span class="sxs-lookup"><span data-stu-id="dcac0-137">Name</span></span>|
|------------------|----|
|`>`|`Greater`|
|`<`|`Less`|
|`+`|`Plus`|
|`-`|`Minus`|
|`*`|`Multiply`|
|`/`|`Divide`|
|`=`|`Equals`|
|`~`|`Twiddle`|
|`%`|`Percent`|
|`.`|`Dot`|
|`&`|`Amp`|
|<code>&#124;</code>|`Bar`|
|`@`|`At`|
|`^`|`Hat`|
|`!`|`Bang`|
|`?`|`Qmark`|
|`(`|`LParen`|
|`,`|`Comma`|
|`)`|`RParen`|
|`[`|`LBrack`|
|`]`|`RBrack`|

## <a name="prefix-and-infix-operators"></a><span data-ttu-id="dcac0-138">前置演算子と挿入演算子</span><span class="sxs-lookup"><span data-stu-id="dcac0-138">Prefix and Infix Operators</span></span>

<span data-ttu-id="dcac0-139">*前置* 演算子は、関数と同じように、オペランドまたはオペランドの前に配置する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dcac0-139">*Prefix* operators are expected to be placed in front of an operand or operands, much like a function.</span></span> <span data-ttu-id="dcac0-140">*挿入* 演算子は、2つのオペランドの間に配置されることが想定されています。</span><span class="sxs-lookup"><span data-stu-id="dcac0-140">*Infix* operators are expected to be placed between the two operands.</span></span>

<span data-ttu-id="dcac0-141">前置演算子として使用できるのは特定の演算子だけです。</span><span class="sxs-lookup"><span data-stu-id="dcac0-141">Only certain operators can be used as prefix operators.</span></span> <span data-ttu-id="dcac0-142">演算子は、常に前置演算子であるもの、挿入演算子にも前置演算子にもなるもの、および常に挿入演算子であるものに分けられます。</span><span class="sxs-lookup"><span data-stu-id="dcac0-142">Some operators are always prefix operators, others can be infix or prefix, and the rest are always infix operators.</span></span> <span data-ttu-id="dcac0-143">`!` で始まる演算子 (`!=` を除く) と `~` 演算子、または `~` の繰り返しシーケンスは、常に前置演算子です。</span><span class="sxs-lookup"><span data-stu-id="dcac0-143">Operators that begin with `!`, except `!=`, and the operator `~`, or repeated sequences of`~`, are always prefix operators.</span></span> <span data-ttu-id="dcac0-144">演算子 `+`、`-`、`+.`、`-.`、`&`、`&&`、`%`、および `%%` は、前置演算子にも挿入演算子にもなります。</span><span class="sxs-lookup"><span data-stu-id="dcac0-144">The operators `+`, `-`, `+.`, `-.`, `&`, `&&`, `%`, and `%%` can be prefix operators or infix operators.</span></span> <span data-ttu-id="dcac0-145">これらの演算子の前置バージョンを挿入バージョンと区別するには、定義時に前置演算子の先頭に `~` を追加します。</span><span class="sxs-lookup"><span data-stu-id="dcac0-145">You distinguish the prefix version of these operators from the infix version by adding a `~` at the beginning of a prefix operator when it is defined.</span></span> <span data-ttu-id="dcac0-146">`~` は、演算子の使用時には使用されず、定義時にのみ使用されます。</span><span class="sxs-lookup"><span data-stu-id="dcac0-146">The `~` is not used when you use the operator, only when it is defined.</span></span>

## <a name="example"></a><span data-ttu-id="dcac0-147">例</span><span class="sxs-lookup"><span data-stu-id="dcac0-147">Example</span></span>

<span data-ttu-id="dcac0-148">次のコードは、分数型を実装する際の演算子のオーバーロードの使用例です。</span><span class="sxs-lookup"><span data-stu-id="dcac0-148">The following code illustrates the use of operator overloading to implement a fraction type.</span></span> <span data-ttu-id="dcac0-149">分数は、分子と分母で表されます。</span><span class="sxs-lookup"><span data-stu-id="dcac0-149">A fraction is represented by a numerator and a denominator.</span></span> <span data-ttu-id="dcac0-150">`hcf` 関数を使用して最大公約数を求め、その公約数を使用して約分します。</span><span class="sxs-lookup"><span data-stu-id="dcac0-150">The function `hcf` is used to determine the highest common factor, which is used to reduce fractions.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4002.fs)]

<span data-ttu-id="dcac0-151">**出力:**</span><span class="sxs-lookup"><span data-stu-id="dcac0-151">**Output:**</span></span>

```console
3/4 + 1/2 = 5/4
3/4 - 1/2 = 1/4
3/4 * 1/2 = 3/8
3/4 / 1/2 = 3/2
3/4 + 1 = 7/4
```

## <a name="operators-at-the-global-level"></a><span data-ttu-id="dcac0-152">グローバル レベルの演算子</span><span class="sxs-lookup"><span data-stu-id="dcac0-152">Operators at the Global Level</span></span>

<span data-ttu-id="dcac0-153">演算子は、グローバル レベルで定義することもできます。</span><span class="sxs-lookup"><span data-stu-id="dcac0-153">You can also define operators at the global level.</span></span> <span data-ttu-id="dcac0-154">次のコードでは、演算子を定義して `+?` います。</span><span class="sxs-lookup"><span data-stu-id="dcac0-154">The following code defines an operator `+?`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4003.fs)]

<span data-ttu-id="dcac0-155">上記のコードの出力は `12` になります。</span><span class="sxs-lookup"><span data-stu-id="dcac0-155">The output of the above code is `12`.</span></span>

<span data-ttu-id="dcac0-156">F# のスコープ規則では、新しく定義された演算子が組み込み演算子よりも優先されるため、このようにして、通常の算術演算子を再定義できます。</span><span class="sxs-lookup"><span data-stu-id="dcac0-156">You can redefine the regular arithmetic operators in this manner because the scoping rules for F# dictate that newly defined operators take precedence over the built-in operators.</span></span>

<span data-ttu-id="dcac0-157">キーワード `inline` は、グローバル演算子と共に使用されることがよくあります。グローバル演算子は、通常、呼び出し元のコードに適宜組み込まれる小規模関数にします。</span><span class="sxs-lookup"><span data-stu-id="dcac0-157">The keyword `inline` is often used with global operators, which are often small functions that are best integrated into the calling code.</span></span> <span data-ttu-id="dcac0-158">演算子関数をインライン化することにより、その関数を静的に解決された型パラメーターと共に使用して、静的に解決されたジェネリック コードを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="dcac0-158">Making operator functions inline also enables them to work with statically resolved type parameters to produce statically resolved generic code.</span></span> <span data-ttu-id="dcac0-159">詳細については、「 [インライン関数](./functions/inline-functions.md) 」と「 [静的に解決される型パラメーター](./generics/statically-resolved-type-parameters.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dcac0-159">For more information, see [Inline Functions](./functions/inline-functions.md) and [Statically Resolved Type Parameters](./generics/statically-resolved-type-parameters.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="dcac0-160">関連項目</span><span class="sxs-lookup"><span data-stu-id="dcac0-160">See also</span></span>

- <span data-ttu-id="dcac0-161">[[メンバー]](./members/index.md)</span><span class="sxs-lookup"><span data-stu-id="dcac0-161">[Members](./members/index.md)</span></span>
