---
title: Visual Basic でのタプル
ms.date: 04/23/2017
helpviewer_keywords:
- tuples [Visual Basic]
ms.assetid: 3e66cd1b-3432-4e1d-8c37-5ebacae8f53f
ms.openlocfilehash: 146e9c2360cea153d2f487769d5b983516861e8d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61663298"
---
# <a name="tuples-visual-basic"></a><span data-ttu-id="729c2-102">タプル (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="729c2-102">Tuples (Visual Basic)</span></span>

<span data-ttu-id="729c2-103">Visual Basic 2017 以降、Visual Basic 言語ではタプルのための組み込みサポートが提供され、タプルの作成や、タプルの要素へのアクセスが簡略化されます。</span><span class="sxs-lookup"><span data-stu-id="729c2-103">Starting with Visual Basic 2017, the Visual Basic language offers built-in support for tuples that makes creating tuples and accessing the elements of tuples easier.</span></span> <span data-ttu-id="729c2-104">タプルとは、値の特定の数とシーケンスを持つ軽量のデータ構造です。</span><span class="sxs-lookup"><span data-stu-id="729c2-104">A tuple is a light-weight data structure that has a specific number and sequence of values.</span></span> <span data-ttu-id="729c2-105">タプルをインスタンス化する場合は、数とそれぞれの値 (または要素) のデータ型を定義します。</span><span class="sxs-lookup"><span data-stu-id="729c2-105">When you instantiate the tuple, you define the number and the data type of each value (or element).</span></span> <span data-ttu-id="729c2-106">たとえば、2 タプル (またはペア) には、2 つの要素があります。</span><span class="sxs-lookup"><span data-stu-id="729c2-106">For example, a 2-tuple (or pair) has two elements.</span></span> <span data-ttu-id="729c2-107">最初の要素は `Boolean` 値で、2 つ目の要素は `String`となる場合があります。</span><span class="sxs-lookup"><span data-stu-id="729c2-107">The first might be a `Boolean` value, while the second is a `String`.</span></span> <span data-ttu-id="729c2-108">タプルを使用すると 1 つのオブジェクトに複数の値を格納するのが簡単になるため、メソッドから複数の値を返すための気軽な方法としてよく使用されます。</span><span class="sxs-lookup"><span data-stu-id="729c2-108">Because tuples make it easy to store multiple values in a single object, they are often used as a lightweight way to return multiple values from a method.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="729c2-109">タプルのサポートが必要です、<xref:System.ValueTuple>型。</span><span class="sxs-lookup"><span data-stu-id="729c2-109">Tuple support requires the <xref:System.ValueTuple> type.</span></span> <span data-ttu-id="729c2-110">.NET Framework 4.7 がインストールされていない場合は、NuGet パッケージを追加する必要があります`System.ValueTuple`、これは、NuGet ギャラリーで使用できます。</span><span class="sxs-lookup"><span data-stu-id="729c2-110">If the .NET Framework 4.7 is not installed, you must add the NuGet package `System.ValueTuple`, which is available on the NuGet Gallery.</span></span> <span data-ttu-id="729c2-111">このパッケージは、せず可能性がありますエラーが発生したコンパイル"定義済みの型 'ValueTuple(Of,,,)' は定義されている、またはインポートされていません"に似ています</span><span class="sxs-lookup"><span data-stu-id="729c2-111">Without this package, you may get a compilation error similar to, "Predefined type 'ValueTuple(Of,,,)' is not defined or imported."</span></span>

## <a name="instantiating-and-using-a-tuple"></a><span data-ttu-id="729c2-112">タプルのインスタンス化と使用</span><span class="sxs-lookup"><span data-stu-id="729c2-112">Instantiating and using a tuple</span></span>

<span data-ttu-id="729c2-113">タプルをインスタンス化するには、外側の値のコンマ区切りの im かっこ。</span><span class="sxs-lookup"><span data-stu-id="729c2-113">You instantiate a tuple by enclosing its comma-delimited values im parentheses.</span></span> <span data-ttu-id="729c2-114">これらの値の各し、タプルのフィールドになります。</span><span class="sxs-lookup"><span data-stu-id="729c2-114">Each of those values then becomes a field of the tuple.</span></span> <span data-ttu-id="729c2-115">次のコードが 3 回 (または 3 タプル) を定義するなど、`Date`その最初の値として、 `String` 、2 番目のオペランドとして、 `Boolean` 3 つ目として。</span><span class="sxs-lookup"><span data-stu-id="729c2-115">For example, the following code defines a triple (or 3-tuple) with a `Date` as its first value, a `String` as its second, and a `Boolean` as its third.</span></span>

[!code-vb[Instantiate](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple1.vb#1)]

<span data-ttu-id="729c2-116">既定では、タプル内の各フィールドの名前から成る文字列`Item`と共に、タプルのフィールドの 1 から始まる位置。</span><span class="sxs-lookup"><span data-stu-id="729c2-116">By default, the name of each field in a tuple consists of the string `Item` along with the field's one-based position in the tuple.</span></span> <span data-ttu-id="729c2-117">この 3 タプルの`Date`フィールドは`Item1`、`String`フィールドは`Item2`、および`Boolean`フィールドは`Item3`します。</span><span class="sxs-lookup"><span data-stu-id="729c2-117">For this 3-tuple, the `Date` field is `Item1`, the `String` field is `Item2`, and the `Boolean` field is `Item3`.</span></span> <span data-ttu-id="729c2-118">次の例は、前のコード行でインスタンス化するタプルのフィールドの値を表示します。</span><span class="sxs-lookup"><span data-stu-id="729c2-118">The following example displays the values of fields of the tuple instantiated in the previous line of code</span></span>

[!code-vb[Instantiate](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple1.vb#2)]

<span data-ttu-id="729c2-119">Visual Basic のタプルのフィールドは読み取り/書き込みです。タプルをインスタンス化した後は、その値を変更できます。</span><span class="sxs-lookup"><span data-stu-id="729c2-119">The fields of a Visual Basic tuple are read-write; after you've instantiated a tuple, you can modify its values.</span></span> <span data-ttu-id="729c2-120">次の例では、前の例で作成されたタプルの 3 つのフィールドのうち 2 つを変更し、結果を表示します。</span><span class="sxs-lookup"><span data-stu-id="729c2-120">The following example modifies two of the three fields of the tuple created in the previous example and displays the result.</span></span>

[!code-vb[Instantiate](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple1.vb#3)]

## <a name="instantiating-and-using-a-named-tuple"></a><span data-ttu-id="729c2-121">インスタンス化し、名前付きタプルを使用します。</span><span class="sxs-lookup"><span data-stu-id="729c2-121">Instantiating and using a named tuple</span></span>

<span data-ttu-id="729c2-122">インスタンス化、タプルのフィールドの既定の名前を使用してではなく、*名前付きタプル*タプルの要素を独自の名前を割り当てることで。</span><span class="sxs-lookup"><span data-stu-id="729c2-122">Rather than using default names for a tuple's fields, you can instantiate a *named tuple* by assigning your own names to the tuple's elements.</span></span> <span data-ttu-id="729c2-123">タプルのフィールドは割り当てられている名前でアクセスできます*または*によって既定の名前。</span><span class="sxs-lookup"><span data-stu-id="729c2-123">The tuple's fields can then be accessed by their assigned names *or* by their default names.</span></span> <span data-ttu-id="729c2-124">次の例では、最初のフィールドを明示的に指定する点を除いて前と同じ 3 つのタプルをインスタンス化`EventDate`、2 番目の`Name`、3 番目の`IsHoliday`します。</span><span class="sxs-lookup"><span data-stu-id="729c2-124">The following example instantiates the same 3-tuple as previously, except that it explicitly names the first field `EventDate`, the second `Name`, and the third `IsHoliday`.</span></span> <span data-ttu-id="729c2-125">フィールドの値が表示されます、それらを変更し、フィールドの値が再び表示されます。</span><span class="sxs-lookup"><span data-stu-id="729c2-125">It then displays the field values, modifies them, and displays the field values again.</span></span>

[!code-vb[Instantiate](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple1.vb#4)]

## <a name="inferred-tuple-element-names"></a><span data-ttu-id="729c2-126">推論されたタプル要素の名前</span><span class="sxs-lookup"><span data-stu-id="729c2-126">Inferred tuple element names</span></span>

<span data-ttu-id="729c2-127">Visual Basic 15.3 以降、Visual Basic はタプルの要素の名前を推測できます。明示的に割り当てる必要はありません。</span><span class="sxs-lookup"><span data-stu-id="729c2-127">Starting with Visual Basic 15.3, Visual Basic can infer the names of tuple elements; you do not have to assign them explicitly.</span></span> <span data-ttu-id="729c2-128">推論されたタプル名は、変数のセットから組を初期化して、同じ変数名であるタプル要素名を使用する場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="729c2-128">Inferred tuple names are useful when you initialize a tuple from a set of variables, and you want the tuple element name to be the same as the variable name.</span></span> 

<span data-ttu-id="729c2-129">次の例では、作成、`stateInfo`という名前の要素を明示的に 3 つを含むタプルが`state`、 `stateName`、および`capital`します。</span><span class="sxs-lookup"><span data-stu-id="729c2-129">The following example creates a `stateInfo` tuple that contains three explicitly named elements, `state`, `stateName`, and `capital`.</span></span> <span data-ttu-id="729c2-130">要素の名前付けに注意してください、タプルの初期化ステートメントが同じ名前の変数の値だけの名前付き要素に割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="729c2-130">Note that, in naming the elements, the tuple initialization statement simply assigns the named elements the values of the identically named variables.</span></span>

[!code-vb[ExplicitlyNamed](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/named-tuples/program.vb#1)]
 
<span data-ttu-id="729c2-131">要素と変数の名前が同じであるため、Visual Basic コンパイラは、次の例として、フィールドの名前を推測できます。</span><span class="sxs-lookup"><span data-stu-id="729c2-131">Because elements and variables have the same name, the Visual Basic compiler can infer the names of the fields, as the following example shows.</span></span>

[!code-vb[ExplicitlyNamed](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/named-tuples/program.vb#2)]

<span data-ttu-id="729c2-132">推論されたタプル要素名を有効にするには、Visual Basic プロジェクトで使用する Visual Basic コンパイラのバージョンを定義する必要があります (\*.vbproj) ファイル。</span><span class="sxs-lookup"><span data-stu-id="729c2-132">To enable inferred tuple element names, you must define the version of the Visual Basic compiler to use in your Visual Basic project (\*.vbproj) file:</span></span> 

```xml 
<PropertyGroup> 
  <LangVersion>15.3</LangVersion> 
</PropertyGroup> 
```

<span data-ttu-id="729c2-133">バージョン番号は 15.3 以降、Visual Basic コンパイラの任意のバージョンを指定できます。</span><span class="sxs-lookup"><span data-stu-id="729c2-133">The version number can be any version of the Visual Basic compiler starting with 15.3.</span></span> <span data-ttu-id="729c2-134">特定のコンパイラ バージョンをハードコーディングするのではなく指定することも"Latest"の値として`LangVersion`システムにインストールされている Visual Basic コンパイラの最新バージョンでコンパイルします。</span><span class="sxs-lookup"><span data-stu-id="729c2-134">Rather than hard-coding a specific compiler version, you can also specify "Latest" as the value of `LangVersion` to compile with the most recent version of the Visual Basic compiler installed on your system.</span></span>

<span data-ttu-id="729c2-135">詳細については、次を参照してください。 [Visual Basic の言語バージョンを設定](../../../language-reference/configure-language-version.md)します。</span><span class="sxs-lookup"><span data-stu-id="729c2-135">For more information, see [setting the Visual Basic language version](../../../language-reference/configure-language-version.md).</span></span>

<span data-ttu-id="729c2-136">場合によっては、Visual Basic コンパイラが、候補名からタプル要素名を推論できませんなどを使用して、既定の名前は、タプルのフィールドを参照のみ`Item1`、`Item2`など。不足している機能には次が含まれます。</span><span class="sxs-lookup"><span data-stu-id="729c2-136">In some cases, the Visual Basic compiler cannot infer the tuple element name from the candidate name, and the tuple field can only be referenced using its default name, such as `Item1`, `Item2`, etc. These include:</span></span>

- <span data-ttu-id="729c2-137">候補名は、`Item3`、`Rest`、`ToString` などのように、タプルのメンバーの名前と同じです。</span><span class="sxs-lookup"><span data-stu-id="729c2-137">The candidate name is the same as the name of a tuple member, such as `Item3`, `Rest`, or `ToString`.</span></span>

- <span data-ttu-id="729c2-138">候補名がタプルで重複しています。</span><span class="sxs-lookup"><span data-stu-id="729c2-138">The candidate name is duplicated in the tuple.</span></span>
 
<span data-ttu-id="729c2-139">フィールドの名前の推論が失敗すると、Visual Basic は、コンパイラ エラーを生成しませんもは実行時にスローされる例外です。</span><span class="sxs-lookup"><span data-stu-id="729c2-139">When field name inference fails, Visual Basic does not generate a compiler error, nor is an exception thrown at runtime.</span></span> <span data-ttu-id="729c2-140">代わりに、タプルのフィールド参照する必要が、定義済みの名前でなど`Item1`と`Item2`します。</span><span class="sxs-lookup"><span data-stu-id="729c2-140">Instead, tuple fields must be referenced by their predefined names, such as `Item1` and `Item2`.</span></span> 
  
## <a name="tuples-versus-structures"></a><span data-ttu-id="729c2-141">構造体とタプル</span><span class="sxs-lookup"><span data-stu-id="729c2-141">Tuples versus structures</span></span>

<span data-ttu-id="729c2-142">Visual Basic のタプルは、**System.ValueTuple** ジェネリック型の 1 つのインスタンスであるタイプ型です。</span><span class="sxs-lookup"><span data-stu-id="729c2-142">A Visual Basic tuple is a value type that is an instance of one of the a **System.ValueTuple** generic types.</span></span> <span data-ttu-id="729c2-143">たとえば、前の例で定義された `holiday`のタプルは <xref:System.ValueTuple%603> 構造体のインスタンスです。</span><span class="sxs-lookup"><span data-stu-id="729c2-143">For example, the `holiday` tuple defined in the previous example is an instance of the <xref:System.ValueTuple%603> structure.</span></span> <span data-ttu-id="729c2-144">データ用の軽量コンテナーとなるように設計されています。</span><span class="sxs-lookup"><span data-stu-id="729c2-144">It is designed to be a lightweight container for data.</span></span> <span data-ttu-id="729c2-145">タプルは簡単に複数のデータ項目を含むオブジェクトを作成することを目的としているため、カスタム構造の持ついくつかの機能が不足している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="729c2-145">Since the tuple aims to make it easy to create an object with multiple data items, it lacks some of the features that a custom structure might have.</span></span> <span data-ttu-id="729c2-146">不足している機能には次が含まれます。</span><span class="sxs-lookup"><span data-stu-id="729c2-146">These include:</span></span>

- <span data-ttu-id="729c2-147">カスタム メンバー。</span><span class="sxs-lookup"><span data-stu-id="729c2-147">Custom members.</span></span> <span data-ttu-id="729c2-148">タプルの独自のプロパティ、メソッド、またはイベントを定義することはできません。</span><span class="sxs-lookup"><span data-stu-id="729c2-148">You cannot define your own properties, methods, or events for a tuple.</span></span>

- <span data-ttu-id="729c2-149">検証します。</span><span class="sxs-lookup"><span data-stu-id="729c2-149">Validation.</span></span> <span data-ttu-id="729c2-150">フィールドに割り当てられているデータを検証することはできません。</span><span class="sxs-lookup"><span data-stu-id="729c2-150">You cannot validate the data assigned to fields.</span></span>

- <span data-ttu-id="729c2-151">不変性。</span><span class="sxs-lookup"><span data-stu-id="729c2-151">Immutability.</span></span> <span data-ttu-id="729c2-152">Visual Basic のタプルは変更可能です。</span><span class="sxs-lookup"><span data-stu-id="729c2-152">Visual Basic tuples are mutable.</span></span> <span data-ttu-id="729c2-153">これに対し、カスタム構造ではインスタンスを変更できるようにするかどうかを制御できます。</span><span class="sxs-lookup"><span data-stu-id="729c2-153">In contrast, a custom structure allows you to control whether an instance is mutable or immutable.</span></span>

<span data-ttu-id="729c2-154">カスタム メンバー、プロパティやフィールドの検証、不変性が重要な場合は、Visual Basic を使用する必要があります[構造](../../../language-reference/statements/structure-statement.md)カスタム値の型を定義するステートメント。</span><span class="sxs-lookup"><span data-stu-id="729c2-154">If custom members, property and field validation, or immutability are important, you should use the Visual Basic [Structure](../../../language-reference/statements/structure-statement.md) statement to define a custom value type.</span></span>

<span data-ttu-id="729c2-155">Visual Basic のタプルのメンバーを継承してその**ValueTuple**型。</span><span class="sxs-lookup"><span data-stu-id="729c2-155">A Visual Basic tuple does inherit the members of its **ValueTuple** type.</span></span> <span data-ttu-id="729c2-156">フィールドだけでなく、次のメソッドが含まれます。</span><span class="sxs-lookup"><span data-stu-id="729c2-156">In addition to its fields, these include the following methods:</span></span>

| <span data-ttu-id="729c2-157">メンバー</span><span class="sxs-lookup"><span data-stu-id="729c2-157">Member</span></span> | <span data-ttu-id="729c2-158">説明</span><span class="sxs-lookup"><span data-stu-id="729c2-158">Description</span></span> |
| ---|---|
| <span data-ttu-id="729c2-159">CompareTo</span><span class="sxs-lookup"><span data-stu-id="729c2-159">CompareTo</span></span> | <span data-ttu-id="729c2-160">現在のタプルを同じ数の要素を持つ別のタプルと比較します。</span><span class="sxs-lookup"><span data-stu-id="729c2-160">Compares the current tuple to another tuple with the same number of elements.</span></span> |
| <span data-ttu-id="729c2-161">Equals</span><span class="sxs-lookup"><span data-stu-id="729c2-161">Equals</span></span> | <span data-ttu-id="729c2-162">現在のタプルが別のタプルまたはオブジェクトと等しいかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="729c2-162">Determines whether the current tuple is equal to another tuple or object.</span></span> |
| <span data-ttu-id="729c2-163">GetHashCode</span><span class="sxs-lookup"><span data-stu-id="729c2-163">GetHashCode</span></span> | <span data-ttu-id="729c2-164">現在のインスタンスのハッシュ コードを計算します。</span><span class="sxs-lookup"><span data-stu-id="729c2-164">Calculates the hash code for the current instance.</span></span> |
| <span data-ttu-id="729c2-165">ToString</span><span class="sxs-lookup"><span data-stu-id="729c2-165">ToString</span></span> | <span data-ttu-id="729c2-166">このタプルでは、形式の文字列表現を返します`(Item1, Item2...)`ここで、`Item1`と`Item2`タプルのフィールドの値を表します。</span><span class="sxs-lookup"><span data-stu-id="729c2-166">Returns the string representation of this tuple, which takes the form `(Item1, Item2...)`, where `Item1` and `Item2` represent the values of the tuple's fields.</span></span> |

<span data-ttu-id="729c2-167">さらに、 **ValueTuple**型実装<xref:System.Collections.IStructuralComparable>と<xref:System.Collections.IStructuralEquatable>インターフェイスで、使用する顧客の比較子を定義できます。</span><span class="sxs-lookup"><span data-stu-id="729c2-167">In addition, the **ValueTuple** types implement <xref:System.Collections.IStructuralComparable> and <xref:System.Collections.IStructuralEquatable> interfaces, which allow you to define customer comparers.</span></span>

## <a name="assignment-and-tuples"></a><span data-ttu-id="729c2-168">割り当てとタプル</span><span class="sxs-lookup"><span data-stu-id="729c2-168">Assignment and tuples</span></span>

<span data-ttu-id="729c2-169">Visual Basic では、同じ数のフィールドがあるタプル型間での割り当てをサポートします。</span><span class="sxs-lookup"><span data-stu-id="729c2-169">Visual Basic supports assignment between tuple types that have the same number of fields.</span></span> <span data-ttu-id="729c2-170">次のいずれかが true の場合、フィールドの型を変換できます。</span><span class="sxs-lookup"><span data-stu-id="729c2-170">The field types can be converted if one of the following is true:</span></span>

- <span data-ttu-id="729c2-171">ソースとターゲットのフィールドは、同じ型です。</span><span class="sxs-lookup"><span data-stu-id="729c2-171">The source and target field are of the same type.</span></span>

- <span data-ttu-id="729c2-172">ターゲットの型に、ソースの種類の拡大 (または暗黙的な) 変換が定義されます。</span><span class="sxs-lookup"><span data-stu-id="729c2-172">A widening (or implicit) conversion of the source type to the target type is defined.</span></span> 

- <span data-ttu-id="729c2-173">`Option Strict` `On`対象の型に、元の型の縮小 (または明示的な) 変換が定義されているとします。</span><span class="sxs-lookup"><span data-stu-id="729c2-173">`Option Strict` is `On`, and a narrowing (or explicit) conversion of the source type to the target type is defined.</span></span> <span data-ttu-id="729c2-174">この変換は、元の値が対象の型の範囲外の場合、例外をスローできます。</span><span class="sxs-lookup"><span data-stu-id="729c2-174">This conversion can throw an exception if the source value is outside the range of the target type.</span></span>

<span data-ttu-id="729c2-175">他の変換は、割り当てでは考慮されません。</span><span class="sxs-lookup"><span data-stu-id="729c2-175">Other conversions are not considered for assignments.</span></span> <span data-ttu-id="729c2-176">タプル型間で許可されている割り当ての種類を見てみましょう。</span><span class="sxs-lookup"><span data-stu-id="729c2-176">Let's look at the kinds of assignments that are allowed between tuple types.</span></span>

<span data-ttu-id="729c2-177">以降の例で使用されている変数について考えます。</span><span class="sxs-lookup"><span data-stu-id="729c2-177">Consider these variables used in the following examples:</span></span>

[!code-vb[Assign](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple3.vb#1)]

<span data-ttu-id="729c2-178">最初の 2 つの変数では、`unnamed`と`anonymous`、セマンティック名が、フィールドはありません。</span><span class="sxs-lookup"><span data-stu-id="729c2-178">The first two variables, `unnamed` and `anonymous`, do not have semantic names provided for the fields.</span></span> <span data-ttu-id="729c2-179">フィールド名は、既定`Item1`と`Item2`します。</span><span class="sxs-lookup"><span data-stu-id="729c2-179">Their field names are the default `Item1` and `Item2`.</span></span> <span data-ttu-id="729c2-180">最後の 2 つの変数では、`named`と`differentName`セマンティック フィールドの名前します。</span><span class="sxs-lookup"><span data-stu-id="729c2-180">The last two variables, `named` and `differentName` have semantic field names.</span></span> <span data-ttu-id="729c2-181">この 2 つのタプルでは、フィールド名が異なっていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="729c2-181">Note that these two tuples have different names for the fields.</span></span>

<span data-ttu-id="729c2-182">すべての 4 つのタプルは同じ呼ばれるフィールド (「アリティ」)、数を持ち、これらのフィールドの型は同じです。</span><span class="sxs-lookup"><span data-stu-id="729c2-182">All four of these tuples have the same number of fields (referred to as 'arity'), and the types of those fields are identical.</span></span> <span data-ttu-id="729c2-183">このため、これらの割り当てはすべて機能します。</span><span class="sxs-lookup"><span data-stu-id="729c2-183">Therefore, all of these assignments work:</span></span>

[!code-vb[Assign](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple3.vb#2)]

<span data-ttu-id="729c2-184">タプルの名前が割り当てられていないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="729c2-184">Notice that the names of the tuples are not assigned.</span></span> <span data-ttu-id="729c2-185">フィールドの値は、タプルのフィールドの順序に従って割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="729c2-185">The values of the fields are assigned following the order of the fields in the tuple.</span></span>

<span data-ttu-id="729c2-186">最後に、割り当てることができることに注意してください、`named`するタプル、`conversion`タプル、にもかかわらずの最初のフィールド`named`は、`Integer`の最初のフィールドと`conversion`は、 `Long`。</span><span class="sxs-lookup"><span data-stu-id="729c2-186">Finally, notice that we can assign the `named` tuple to the `conversion` tuple, even though the first field of `named` is an `Integer`, and the first field of `conversion` is a `Long`.</span></span> <span data-ttu-id="729c2-187">変換するために、この割り当てが成功、`Integer`を`Long`は拡大変換です。</span><span class="sxs-lookup"><span data-stu-id="729c2-187">This assignment succeeds because converting an `Integer` to a `Long` is a widening conversion.</span></span>

[!code-vb[Assign](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple3.vb#3)]

<span data-ttu-id="729c2-188">異なる数のフィールドを持つタプルを割り当てることはできません。</span><span class="sxs-lookup"><span data-stu-id="729c2-188">Tuples with different numbers of fields are not assignable:</span></span>

```vb
' Does not compile.
' VB30311: Value of type '(Integer, Integer, Integer)' cannot be converted
'          to '(Answer As Integer, Message As String)'
var differentShape = (1, 2, 3)
named = differentShape
```

## <a name="tuples-as-method-return-values"></a><span data-ttu-id="729c2-189">メソッドの戻り値としてのタプル</span><span class="sxs-lookup"><span data-stu-id="729c2-189">Tuples as method return values</span></span>

<span data-ttu-id="729c2-190">メソッドは、値は 1 つだけを返すことができます。</span><span class="sxs-lookup"><span data-stu-id="729c2-190">A method can return only a single value.</span></span> <span data-ttu-id="729c2-191">多くの場合、ただしたいメソッドの呼び出しを複数の値を返します。</span><span class="sxs-lookup"><span data-stu-id="729c2-191">Frequently, though, you'd like a method call to return multiple values.</span></span> <span data-ttu-id="729c2-192">この制限を回避するいくつかの方法はあります。</span><span class="sxs-lookup"><span data-stu-id="729c2-192">There are several ways to work around this limitation:</span></span>

- <span data-ttu-id="729c2-193">できるプロパティを作成するカスタム クラスまたは構造体がまたはのフィールドは、メソッドによって返される値。</span><span class="sxs-lookup"><span data-stu-id="729c2-193">You can create a custom class or structure whose properties or fields represent values returned by the method.</span></span> <span data-ttu-id="729c2-194">つまり、重量級のソリューションです。メソッドの呼び出しから値を取得するが唯一の目的は、カスタム型を定義することが必要です。</span><span class="sxs-lookup"><span data-stu-id="729c2-194">Thus is a heavyweight solution; it requires that you define a custom type whose only purpose is to retrieve values from a method call.</span></span>

- <span data-ttu-id="729c2-195">メソッドから 1 つの値を返すし、メソッドへの参照で渡すことによって、残りの値を返すことができます。</span><span class="sxs-lookup"><span data-stu-id="729c2-195">You can return a single value from the method, and return the remaining values by passing them by reference to the method.</span></span> <span data-ttu-id="729c2-196">これには、変数と参照渡しで渡す変数の値を上書きしてしまうリスクをインスタンス化のオーバーヘッドが含まれます。</span><span class="sxs-lookup"><span data-stu-id="729c2-196">This involves the overhead of instantiating a variable and risks inadvertently overwriting the value of the variable that you pass by reference.</span></span>

- <span data-ttu-id="729c2-197">複数の戻り値を取得するライトウェイト ソリューションを提供するタプルを使用できます。</span><span class="sxs-lookup"><span data-stu-id="729c2-197">You can use a tuple, which provides a lightweight solution to retrieving multiple return values.</span></span>

<span data-ttu-id="729c2-198">たとえば、 **TryParse** .NET の戻り値でメソッドを`Boolean`解析操作が成功したかどうかを示す値です。</span><span class="sxs-lookup"><span data-stu-id="729c2-198">For example, the **TryParse** methods in .NET return a `Boolean` value that indicates whether the parsing operation succeeded.</span></span> <span data-ttu-id="729c2-199">メソッドへの参照によって渡された変数では、解析操作の結果が返されます。</span><span class="sxs-lookup"><span data-stu-id="729c2-199">The result of the parsing operation is returned in a variable passed by reference to the method.</span></span> <span data-ttu-id="729c2-200">呼び出しでは通常などの解析メソッド<xref:System.Int32.TryParse%2A?displayProperty=nameWithType>次のようになります。</span><span class="sxs-lookup"><span data-stu-id="729c2-200">Normally, a call to the a parsing method such as <xref:System.Int32.TryParse%2A?displayProperty=nameWithType> looks like the following:</span></span>

[!code-vb[Return](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple-returns.vb#1)]

<span data-ttu-id="729c2-201">呼び出しのラップがある場合、解析操作からタプルを返しますことができます、<xref:System.Int32.TryParse%2A?displayProperty=nameWithType>方法では、独自のメソッド。</span><span class="sxs-lookup"><span data-stu-id="729c2-201">We can return a tuple from the parsing operation if we wrap the call to the <xref:System.Int32.TryParse%2A?displayProperty=nameWithType> method in our own method.</span></span> <span data-ttu-id="729c2-202">次の例では、`NumericLibrary.ParseInteger`呼び出し、<xref:System.Int32.TryParse%2A?displayProperty=nameWithType>メソッドを 2 つの要素で名前付きタプルを返します。</span><span class="sxs-lookup"><span data-stu-id="729c2-202">In the following example, `NumericLibrary.ParseInteger` calls the <xref:System.Int32.TryParse%2A?displayProperty=nameWithType> method and returns a named tuple with two elements.</span></span> 

[!code-vb[Return](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple-returns.vb#2)]

<span data-ttu-id="729c2-203">次のようなコードでメソッドを呼び出してことができます。</span><span class="sxs-lookup"><span data-stu-id="729c2-203">You can then call the method with code like the following:</span></span>

[!code-vb[Return](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple-returns.vb#3)]

## <a name="visual-basic-tuples-and-tuples-in-the-net-framework"></a><span data-ttu-id="729c2-204">Visual Basic のタプルと、.NET Framework 内のタプル</span><span class="sxs-lookup"><span data-stu-id="729c2-204">Visual Basic tuples and tuples in the .NET Framework</span></span>

<span data-ttu-id="729c2-205">Visual Basic のタプルは、.NET Framework 4.7 で導入された **System.ValueTuple** ジェネリック型の 1 つのインスタンスです。</span><span class="sxs-lookup"><span data-stu-id="729c2-205">A Visual Basic tuple is an instance of one of the **System.ValueTuple** generic types, which were introduced in the .NET Framework 4.7.</span></span> <span data-ttu-id="729c2-206">.NET Framework には、汎用の **System.Tuple** クラスのセットも含まれます。</span><span class="sxs-lookup"><span data-stu-id="729c2-206">The .NET Framework also includes a set of generic **System.Tuple** classes.</span></span> <span data-ttu-id="729c2-207">ただし、これらのクラスは Visual Basic のタプルおよび **System.ValueTuple** とは次のいくつかの面で異なります。</span><span class="sxs-lookup"><span data-stu-id="729c2-207">These classes, however, differ from Visual Basic tuples and the **System.ValueTuple** generic types in a number of ways:</span></span>

- <span data-ttu-id="729c2-208">**タプル** クラスの要素は、`Item1`、`Item2`などの名前を持つプロパティです。</span><span class="sxs-lookup"><span data-stu-id="729c2-208">The elements of the **Tuple** classes are properties named `Item1`, `Item2`, and so on.</span></span> <span data-ttu-id="729c2-209">Visual Basic のタプルおよび **ValueTuple** においてタプル要素はフィールドです。</span><span class="sxs-lookup"><span data-stu-id="729c2-209">In Visual Basic tuples and the **ValueTuple** types, tuple elements are fields.</span></span>

- <span data-ttu-id="729c2-210">要素にわかりやすい名前を割り当てることはできません、**タプル**インスタンスまたはを**ValueTuple**インスタンス。</span><span class="sxs-lookup"><span data-stu-id="729c2-210">You cannot assign meaningful names to the elements of a **Tuple** instance or of a **ValueTuple** instance.</span></span> <span data-ttu-id="729c2-211">Visual Basic を使用すると、フィールドの意味を伝える名前を割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="729c2-211">Visual Basic allows you to assign names that communicate the meaning of the fields.</span></span>

- <span data-ttu-id="729c2-212">**タプル** インスタンスのプロパティは読み取り専用で、タプルは変更できません。</span><span class="sxs-lookup"><span data-stu-id="729c2-212">The properties of a **Tuple** instance are read-only; the tuples are immutable.</span></span> <span data-ttu-id="729c2-213">Visual Basic のタプルおよび **ValueTuple** 型では、タプルのフィールドは読み取り/書き込み可能で、タプルは変更できます。</span><span class="sxs-lookup"><span data-stu-id="729c2-213">In Visual Basic tuples and the **ValueTuple** types, tuple fields are read-write; the tuples are mutable.</span></span>

- <span data-ttu-id="729c2-214">汎用の**タプル**型は参照型です。</span><span class="sxs-lookup"><span data-stu-id="729c2-214">The generic **Tuple** types are reference types.</span></span> <span data-ttu-id="729c2-215">これらの**タプル**型を使用することはオブジェクトの割り当てを意味します。</span><span class="sxs-lookup"><span data-stu-id="729c2-215">Using these **Tuple** types means allocating objects.</span></span> <span data-ttu-id="729c2-216">ホット パスでは、これがアプリケーションのパフォーマンスに大きな影響を与えることがあります。</span><span class="sxs-lookup"><span data-stu-id="729c2-216">On hot paths, this can have a measurable impact on your application's performance.</span></span> <span data-ttu-id="729c2-217">Visual Basic のタプルと **ValueTuple** 型は値型です。</span><span class="sxs-lookup"><span data-stu-id="729c2-217">Visual Basic tuples and the **ValueTuple** types are value types.</span></span>

<span data-ttu-id="729c2-218"><xref:System.TupleExtensions> クラスの拡張メソッドによって、簡単に Visual Basic のタプルと .NET **タプル** オブジェクト間の変換がしやすくなります。</span><span class="sxs-lookup"><span data-stu-id="729c2-218">Extension methods in the <xref:System.TupleExtensions> class make it easy to convert between Visual Basic tuples and .NET **Tuple** objects.</span></span> <span data-ttu-id="729c2-219">**ToTuple** メソッドは、Visual Basic のタプルを .NET **タプル** オブジェクトに変換し、**ToValueTuple** メソッドは .NET **タプル** オブジェクトを Visual Basic のタプルに変換します。</span><span class="sxs-lookup"><span data-stu-id="729c2-219">The **ToTuple** method converts a Visual Basic tuple to a .NET **Tuple** object, and the **ToValueTuple** method converts a .NET **Tuple** object to a Visual Basic tuple.</span></span>

<span data-ttu-id="729c2-220">次の例ではタプルを作成し、.NET **タプル** オブジェクトを変換し、Visual Basic のタプルに変換し直します。</span><span class="sxs-lookup"><span data-stu-id="729c2-220">The following example creates a tuple, converts it to a .NET **Tuple** object, and converts it back to a Visual Basic tuple.</span></span> <span data-ttu-id="729c2-221">この例では、このタプルを元のタプルと比較して、それらが等しいことを確認します。</span><span class="sxs-lookup"><span data-stu-id="729c2-221">The example then compares this tuple with the original one to ensure that they are equal.</span></span>

[!code-vb[Convert](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple2.vb#1)]

## <a name="see-also"></a><span data-ttu-id="729c2-222">関連項目</span><span class="sxs-lookup"><span data-stu-id="729c2-222">See also</span></span>

- [<span data-ttu-id="729c2-223">Visual Basic の言語リファレンス</span><span class="sxs-lookup"><span data-stu-id="729c2-223">Visual Basic Language Reference</span></span>](index.md)
