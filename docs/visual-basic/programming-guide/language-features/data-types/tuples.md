---
title: Tuples
ms.date: 04/23/2017
helpviewer_keywords:
- tuples [Visual Basic]
ms.assetid: 3e66cd1b-3432-4e1d-8c37-5ebacae8f53f
ms.openlocfilehash: e0310f31d7becb1f79bb023a277bd565421b44fb
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350495"
---
# <a name="tuples-visual-basic"></a><span data-ttu-id="78d1e-102">タプル (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="78d1e-102">Tuples (Visual Basic)</span></span>

<span data-ttu-id="78d1e-103">Visual Basic 2017 以降、Visual Basic 言語ではタプルのための組み込みサポートが提供され、タプルの作成や、タプルの要素へのアクセスが簡略化されます。</span><span class="sxs-lookup"><span data-stu-id="78d1e-103">Starting with Visual Basic 2017, the Visual Basic language offers built-in support for tuples that makes creating tuples and accessing the elements of tuples easier.</span></span> <span data-ttu-id="78d1e-104">タプルは、特定の数と値のシーケンスを持つ軽量なデータ構造です。</span><span class="sxs-lookup"><span data-stu-id="78d1e-104">A tuple is a lightweight data structure that has a specific number and sequence of values.</span></span> <span data-ttu-id="78d1e-105">タプルをインスタンス化する場合は、数とそれぞれの値 (または要素) のデータ型を定義します。</span><span class="sxs-lookup"><span data-stu-id="78d1e-105">When you instantiate the tuple, you define the number and the data type of each value (or element).</span></span> <span data-ttu-id="78d1e-106">たとえば、2 タプル (またはペア) には 2 つの要素があります。</span><span class="sxs-lookup"><span data-stu-id="78d1e-106">For example, a 2-tuple (or pair) has two elements.</span></span> <span data-ttu-id="78d1e-107">1 つ目は `Boolean` 値、2 番目のは `String`です。</span><span class="sxs-lookup"><span data-stu-id="78d1e-107">The first might be a `Boolean` value, while the second is a `String`.</span></span> <span data-ttu-id="78d1e-108">タプルを使用すると 1 つのオブジェクトに複数の値を格納するのが簡単になるため、メソッドから複数の値を返すための気軽な方法としてよく使用されます。</span><span class="sxs-lookup"><span data-stu-id="78d1e-108">Because tuples make it easy to store multiple values in a single object, they are often used as a lightweight way to return multiple values from a method.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="78d1e-109">組のサポートには <xref:System.ValueTuple> 型が必要です。</span><span class="sxs-lookup"><span data-stu-id="78d1e-109">Tuple support requires the <xref:System.ValueTuple> type.</span></span> <span data-ttu-id="78d1e-110">.NET Framework 4.7 がインストールされていない場合は、nuget ギャラリーから入手できる NuGet パッケージ `System.ValueTuple`を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="78d1e-110">If the .NET Framework 4.7 is not installed, you must add the NuGet package `System.ValueTuple`, which is available on the NuGet Gallery.</span></span> <span data-ttu-id="78d1e-111">このパッケージがないと、"定義済みの型 ' ValueTuple (,,,) ' が定義またはインポートされていません" のようなコンパイルエラーが発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="78d1e-111">Without this package, you may get a compilation error similar to, "Predefined type 'ValueTuple(Of,,,)' is not defined or imported."</span></span>

## <a name="instantiating-and-using-a-tuple"></a><span data-ttu-id="78d1e-112">タプルのインスタンス化と使用</span><span class="sxs-lookup"><span data-stu-id="78d1e-112">Instantiating and using a tuple</span></span>

<span data-ttu-id="78d1e-113">タプルをインスタンス化するには、コンマ区切り値の im かっこを囲みます。</span><span class="sxs-lookup"><span data-stu-id="78d1e-113">You instantiate a tuple by enclosing its comma-delimited values im parentheses.</span></span> <span data-ttu-id="78d1e-114">これらの値はそれぞれ、タプルのフィールドになります。</span><span class="sxs-lookup"><span data-stu-id="78d1e-114">Each of those values then becomes a field of the tuple.</span></span> <span data-ttu-id="78d1e-115">たとえば、次のコードでは、`Date` が最初の値、`String` が2 番目の値、3 番目の値が `Boolean` であるトリプル (または 3 タプル) を定義しています。</span><span class="sxs-lookup"><span data-stu-id="78d1e-115">For example, the following code defines a triple (or 3-tuple) with a `Date` as its first value, a `String` as its second, and a `Boolean` as its third.</span></span>

[!code-vb[Instantiate](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple1.vb#1)]

<span data-ttu-id="78d1e-116">タプルをインスタンス化するには、コンマ区切り値の im かっこを囲みます。</span><span class="sxs-lookup"><span data-stu-id="78d1e-116">By default, the name of each field in a tuple consists of the string `Item` along with the field's one-based position in the tuple.</span></span> <span data-ttu-id="78d1e-117">これらの値はそれぞれ、タプルのフィールドになります。</span><span class="sxs-lookup"><span data-stu-id="78d1e-117">For this 3-tuple, the `Date` field is `Item1`, the `String` field is `Item2`, and the `Boolean` field is `Item3`.</span></span> <span data-ttu-id="78d1e-118">たとえば、次のコードでは、`Date` が最初の値、`String` が2 番目の値、3 番目の値が `Boolean` であるトリプル (または 3 タプル) を定義しています。</span><span class="sxs-lookup"><span data-stu-id="78d1e-118">The following example displays the values of fields of the tuple instantiated in the previous line of code</span></span>

[!code-vb[Instantiate](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple1.vb#2)]

<span data-ttu-id="78d1e-119">Visual Basic タプルのフィールドは読み取り/書き込み可能です。タプルをインスタンス化した後は、その値を変更できます。</span><span class="sxs-lookup"><span data-stu-id="78d1e-119">The fields of a Visual Basic tuple are read-write; after you've instantiated a tuple, you can modify its values.</span></span> <span data-ttu-id="78d1e-120">次の例では、前の例で作成されたタプルの 3 つのフィールドのうち 2 つを変更し、結果を表示します。</span><span class="sxs-lookup"><span data-stu-id="78d1e-120">The following example modifies two of the three fields of the tuple created in the previous example and displays the result.</span></span>

[!code-vb[Instantiate](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple1.vb#3)]

## <a name="instantiating-and-using-a-named-tuple"></a><span data-ttu-id="78d1e-121">名前付きタプルのインスタンス化と使用</span><span class="sxs-lookup"><span data-stu-id="78d1e-121">Instantiating and using a named tuple</span></span>

<span data-ttu-id="78d1e-122">タプルのフィールドに既定の名前を使用するのではなく、独自の名前をタプルの要素に割り当てることで、*名前付きタプル*をインスタンス化できます。</span><span class="sxs-lookup"><span data-stu-id="78d1e-122">Rather than using default names for a tuple's fields, you can instantiate a *named tuple* by assigning your own names to the tuple's elements.</span></span> <span data-ttu-id="78d1e-123">タプルのフィールドには、割り当てられた名前*または*既定の名前を使用してアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="78d1e-123">The tuple's fields can then be accessed by their assigned names *or* by their default names.</span></span> <span data-ttu-id="78d1e-124">次の例では、前と同じ 3 つのタプルをインスタンス化しますが、最初のフィールド `EventDate`、2 番目の `Name`、3 番目の `IsHoliday`を明示的に指定する点が異なります。</span><span class="sxs-lookup"><span data-stu-id="78d1e-124">The following example instantiates the same 3-tuple as previously, except that it explicitly names the first field `EventDate`, the second `Name`, and the third `IsHoliday`.</span></span> <span data-ttu-id="78d1e-125">次に、フィールドの値を表示して変更し、フィールドの値を再度表示します。</span><span class="sxs-lookup"><span data-stu-id="78d1e-125">It then displays the field values, modifies them, and displays the field values again.</span></span>

[!code-vb[Instantiate](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple1.vb#4)]

## <a name="inferred-tuple-element-names"></a><span data-ttu-id="78d1e-126">推論されたタプル要素の名前</span><span class="sxs-lookup"><span data-stu-id="78d1e-126">Inferred tuple element names</span></span>

<span data-ttu-id="78d1e-127">Visual Basic 15.3 以降では、Visual Basic タプル要素の名前を推論できます。明示的に割り当てる必要はありません。</span><span class="sxs-lookup"><span data-stu-id="78d1e-127">Starting with Visual Basic 15.3, Visual Basic can infer the names of tuple elements; you do not have to assign them explicitly.</span></span> <span data-ttu-id="78d1e-128">推論されたタプル名は、一連の変数からタプルを初期化するときに、タプル要素名を変数名と同じにする場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="78d1e-128">Inferred tuple names are useful when you initialize a tuple from a set of variables, and you want the tuple element name to be the same as the variable name.</span></span>

<span data-ttu-id="78d1e-129">次の例では、明示的に指定された3つの要素、`state`、`stateName`、および `capital`を含む `stateInfo` 組を作成します。</span><span class="sxs-lookup"><span data-stu-id="78d1e-129">The following example creates a `stateInfo` tuple that contains three explicitly named elements, `state`, `stateName`, and `capital`.</span></span> <span data-ttu-id="78d1e-130">要素の名前付けでは、タプルの初期化ステートメントによって、名前付きの要素が同じ名前の変数の値に割り当てられることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="78d1e-130">Note that, in naming the elements, the tuple initialization statement simply assigns the named elements the values of the identically named variables.</span></span>

[!code-vb[ExplicitlyNamed](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/named-tuples/program.vb#1)]

<span data-ttu-id="78d1e-131">要素と変数の名前が同じであるため、次の例に示すように、Visual Basic コンパイラはフィールドの名前を推論できます。</span><span class="sxs-lookup"><span data-stu-id="78d1e-131">Because elements and variables have the same name, the Visual Basic compiler can infer the names of the fields, as the following example shows.</span></span>

[!code-vb[ExplicitlyNamed](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/named-tuples/program.vb#2)]

<span data-ttu-id="78d1e-132">推論されたタプル要素名を有効にするには、Visual Basic プロジェクト (\*.vbproj) ファイルで使用する Visual Basic コンパイラのバージョンを定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="78d1e-132">To enable inferred tuple element names, you must define the version of the Visual Basic compiler to use in your Visual Basic project (\*.vbproj) file:</span></span>

```xml
<PropertyGroup>
  <LangVersion>15.3</LangVersion>
</PropertyGroup>
```

<span data-ttu-id="78d1e-133">バージョン番号は、15.3 以降の任意のバージョンの Visual Basic コンパイラにすることができます。</span><span class="sxs-lookup"><span data-stu-id="78d1e-133">The version number can be any version of the Visual Basic compiler starting with 15.3.</span></span> <span data-ttu-id="78d1e-134">特定のコンパイラのバージョンをハードコーディングするのではなく、`LangVersion` の値として "Latest" を指定して、システムにインストールされている最新バージョンの Visual Basic コンパイラでコンパイルすることもできます。</span><span class="sxs-lookup"><span data-stu-id="78d1e-134">Rather than hard-coding a specific compiler version, you can also specify "Latest" as the value of `LangVersion` to compile with the most recent version of the Visual Basic compiler installed on your system.</span></span>

<span data-ttu-id="78d1e-135">詳細については、「 [Visual Basic 言語バージョンの設定](../../../language-reference/configure-language-version.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="78d1e-135">For more information, see [setting the Visual Basic language version](../../../language-reference/configure-language-version.md).</span></span>

<span data-ttu-id="78d1e-136">場合によっては、Visual Basic コンパイラが候補名からタプル要素名を推測できず、タプルフィールドは、`Item1`、`Item2`などの既定の名前を使用してのみ参照できます。次のようなものがあります。</span><span class="sxs-lookup"><span data-stu-id="78d1e-136">In some cases, the Visual Basic compiler cannot infer the tuple element name from the candidate name, and the tuple field can only be referenced using its default name, such as `Item1`, `Item2`, etc. These include:</span></span>

- <span data-ttu-id="78d1e-137">候補名は、`Item3`、`Rest`、`ToString`などのタプルメンバーの名前と同じです。</span><span class="sxs-lookup"><span data-stu-id="78d1e-137">The candidate name is the same as the name of a tuple member, such as `Item3`, `Rest`, or `ToString`.</span></span>

- <span data-ttu-id="78d1e-138">候補名がタプルで重複しています。</span><span class="sxs-lookup"><span data-stu-id="78d1e-138">The candidate name is duplicated in the tuple.</span></span>

<span data-ttu-id="78d1e-139">フィールド名の推定に失敗した場合、Visual Basic はコンパイラエラーを生成せず、実行時にスローされる例外も生成しません。</span><span class="sxs-lookup"><span data-stu-id="78d1e-139">When field name inference fails, Visual Basic does not generate a compiler error, nor is an exception thrown at runtime.</span></span> <span data-ttu-id="78d1e-140">代わりに、`Item1` や `Item2`など、定義済みの名前でタプルフィールドを参照する必要があります。</span><span class="sxs-lookup"><span data-stu-id="78d1e-140">Instead, tuple fields must be referenced by their predefined names, such as `Item1` and `Item2`.</span></span>

## <a name="tuples-versus-structures"></a><span data-ttu-id="78d1e-141">タプルと構造体</span><span class="sxs-lookup"><span data-stu-id="78d1e-141">Tuples versus structures</span></span>

<span data-ttu-id="78d1e-142">Visual Basic タプルは、値型であり、いずれかの種類の **ValueTuple** ジェネリック型のインスタンスです。</span><span class="sxs-lookup"><span data-stu-id="78d1e-142">A Visual Basic tuple is a value type that is an instance of one of the a **System.ValueTuple** generic types.</span></span> <span data-ttu-id="78d1e-143">たとえば、前の例で定義されている `holiday` タプルは、<xref:System.ValueTuple%603> 構造のインスタンスです。</span><span class="sxs-lookup"><span data-stu-id="78d1e-143">For example, the `holiday` tuple defined in the previous example is an instance of the <xref:System.ValueTuple%603> structure.</span></span> <span data-ttu-id="78d1e-144">データ用の軽量コンテナーとなるように設計されています。</span><span class="sxs-lookup"><span data-stu-id="78d1e-144">It is designed to be a lightweight container for data.</span></span> <span data-ttu-id="78d1e-145">タプルは簡単に複数のデータ項目を含むオブジェクトを作成することを目的としているため、カスタム構造の持ついくつかの機能が不足している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="78d1e-145">Since the tuple aims to make it easy to create an object with multiple data items, it lacks some of the features that a custom structure might have.</span></span> <span data-ttu-id="78d1e-146">これには次が含まれます。</span><span class="sxs-lookup"><span data-stu-id="78d1e-146">These include:</span></span>

- <span data-ttu-id="78d1e-147">カスタムメンバー。</span><span class="sxs-lookup"><span data-stu-id="78d1e-147">Custom members.</span></span> <span data-ttu-id="78d1e-148">タプルの独自のプロパティ、メソッド、またはイベントを定義することはできません。</span><span class="sxs-lookup"><span data-stu-id="78d1e-148">You cannot define your own properties, methods, or events for a tuple.</span></span>

- <span data-ttu-id="78d1e-149">検証:</span><span class="sxs-lookup"><span data-stu-id="78d1e-149">Validation.</span></span> <span data-ttu-id="78d1e-150">フィールドに割り当てられたデータを検証することはできません。</span><span class="sxs-lookup"><span data-stu-id="78d1e-150">You cannot validate the data assigned to fields.</span></span>

- <span data-ttu-id="78d1e-151">不変性.</span><span class="sxs-lookup"><span data-stu-id="78d1e-151">Immutability.</span></span> <span data-ttu-id="78d1e-152">Visual Basic のタプルは変更可能です。</span><span class="sxs-lookup"><span data-stu-id="78d1e-152">Visual Basic tuples are mutable.</span></span> <span data-ttu-id="78d1e-153">これに対し、カスタム構造ではインスタンスを変更できるようにするかどうかを制御できます。</span><span class="sxs-lookup"><span data-stu-id="78d1e-153">In contrast, a custom structure allows you to control whether an instance is mutable or immutable.</span></span>

<span data-ttu-id="78d1e-154">カスタムメンバー、プロパティとフィールドの検証、または不変性が重要な場合は、Visual Basic [Structure](../../../language-reference/statements/structure-statement.md)ステートメントを使用してカスタム値型を定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="78d1e-154">If custom members, property and field validation, or immutability are important, you should use the Visual Basic [Structure](../../../language-reference/statements/structure-statement.md) statement to define a custom value type.</span></span>

<span data-ttu-id="78d1e-155">Visual Basic タプルは、その **valuetuple** 型のメンバーを継承します。</span><span class="sxs-lookup"><span data-stu-id="78d1e-155">A Visual Basic tuple does inherit the members of its **ValueTuple** type.</span></span> <span data-ttu-id="78d1e-156">フィールドに加えて、次のメソッドがあります。</span><span class="sxs-lookup"><span data-stu-id="78d1e-156">In addition to its fields, these include the following methods:</span></span>

| <span data-ttu-id="78d1e-157">メンバー</span><span class="sxs-lookup"><span data-stu-id="78d1e-157">Member</span></span> | <span data-ttu-id="78d1e-158">説明</span><span class="sxs-lookup"><span data-stu-id="78d1e-158">Description</span></span> |
| ---|---|
| <span data-ttu-id="78d1e-159">CompareTo</span><span class="sxs-lookup"><span data-stu-id="78d1e-159">CompareTo</span></span> | <span data-ttu-id="78d1e-160">現在のタプルを同じ数の要素を持つ別のタプルと比較します。</span><span class="sxs-lookup"><span data-stu-id="78d1e-160">Compares the current tuple to another tuple with the same number of elements.</span></span> |
| <span data-ttu-id="78d1e-161">Equals</span><span class="sxs-lookup"><span data-stu-id="78d1e-161">Equals</span></span> | <span data-ttu-id="78d1e-162">現在のタプルが別のタプルまたはオブジェクトと等しいかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="78d1e-162">Determines whether the current tuple is equal to another tuple or object.</span></span> |
| <span data-ttu-id="78d1e-163">GetHashCode</span><span class="sxs-lookup"><span data-stu-id="78d1e-163">GetHashCode</span></span> | <span data-ttu-id="78d1e-164">現在のインスタンスのハッシュコードを計算します。</span><span class="sxs-lookup"><span data-stu-id="78d1e-164">Calculates the hash code for the current instance.</span></span> |
| <span data-ttu-id="78d1e-165">ToString</span><span class="sxs-lookup"><span data-stu-id="78d1e-165">ToString</span></span> | <span data-ttu-id="78d1e-166">このタプルの文字列表現を返します。このタプルは `(Item1, Item2...)`の形式をとります。`Item1` と `Item2` はタプルのフィールドの値を表します。</span><span class="sxs-lookup"><span data-stu-id="78d1e-166">Returns the string representation of this tuple, which takes the form `(Item1, Item2...)`, where `Item1` and `Item2` represent the values of the tuple's fields.</span></span> |

<span data-ttu-id="78d1e-167">さらに、 **Valuetuple**型は <xref:System.Collections.IStructuralComparable> および <xref:System.Collections.IStructuralEquatable> インターフェイスを実装します。これにより、顧客比較子を定義できます。</span><span class="sxs-lookup"><span data-stu-id="78d1e-167">In addition, the **ValueTuple** types implement <xref:System.Collections.IStructuralComparable> and <xref:System.Collections.IStructuralEquatable> interfaces, which allow you to define customer comparers.</span></span>

## <a name="assignment-and-tuples"></a><span data-ttu-id="78d1e-168">割り当てとタプル</span><span class="sxs-lookup"><span data-stu-id="78d1e-168">Assignment and tuples</span></span>

<span data-ttu-id="78d1e-169">Visual Basic は、同じ数のフィールドを持つタプル型間の割り当てをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="78d1e-169">Visual Basic supports assignment between tuple types that have the same number of fields.</span></span> <span data-ttu-id="78d1e-170">次のいずれかに該当する場合は、フィールドの種類を変換できます。</span><span class="sxs-lookup"><span data-stu-id="78d1e-170">The field types can be converted if one of the following is true:</span></span>

- <span data-ttu-id="78d1e-171">ソースとターゲットのフィールドの型は同じです。</span><span class="sxs-lookup"><span data-stu-id="78d1e-171">The source and target field are of the same type.</span></span>

- <span data-ttu-id="78d1e-172">ソース型からターゲット型への拡大 (または暗黙的) の変換が定義されています。</span><span class="sxs-lookup"><span data-stu-id="78d1e-172">A widening (or implicit) conversion of the source type to the target type is defined.</span></span>

- <span data-ttu-id="78d1e-173">`Option Strict` が `On`、変換元の型から変換先の型への縮小 (または明示的) 変換が定義されています。</span><span class="sxs-lookup"><span data-stu-id="78d1e-173">`Option Strict` is `On`, and a narrowing (or explicit) conversion of the source type to the target type is defined.</span></span> <span data-ttu-id="78d1e-174">ソース値が対象の型の範囲外の場合、この変換によって例外がスローされる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="78d1e-174">This conversion can throw an exception if the source value is outside the range of the target type.</span></span>

<span data-ttu-id="78d1e-175">他の変換は、割り当てでは考慮されません。</span><span class="sxs-lookup"><span data-stu-id="78d1e-175">Other conversions are not considered for assignments.</span></span> <span data-ttu-id="78d1e-176">タプル型間で許可されている割り当ての種類を見てみましょう。</span><span class="sxs-lookup"><span data-stu-id="78d1e-176">Let's look at the kinds of assignments that are allowed between tuple types.</span></span>

<span data-ttu-id="78d1e-177">以降の例で使用されている変数について考えます。</span><span class="sxs-lookup"><span data-stu-id="78d1e-177">Consider these variables used in the following examples:</span></span>

[!code-vb[Assign](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple3.vb#1)]

<span data-ttu-id="78d1e-178">最初の2つの変数 `unnamed` と `anonymous`には、フィールドにセマンティック名が指定されていません。</span><span class="sxs-lookup"><span data-stu-id="78d1e-178">The first two variables, `unnamed` and `anonymous`, do not have semantic names provided for the fields.</span></span> <span data-ttu-id="78d1e-179">フィールド名は、既定の `Item1` と `Item2`です。</span><span class="sxs-lookup"><span data-stu-id="78d1e-179">Their field names are the default `Item1` and `Item2`.</span></span> <span data-ttu-id="78d1e-180">最後の2つの変数 `named` と `differentName` には、セマンティックフィールド名があります。</span><span class="sxs-lookup"><span data-stu-id="78d1e-180">The last two variables, `named` and `differentName` have semantic field names.</span></span> <span data-ttu-id="78d1e-181">この 2 つのタプルでは、フィールド名が異なっていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="78d1e-181">Note that these two tuples have different names for the fields.</span></span>

<span data-ttu-id="78d1e-182">これらの 4 つのタプルのフィールドの数（"アリティ" と呼ばれる）は同じであり、それらのフィールドの型は同じです。</span><span class="sxs-lookup"><span data-stu-id="78d1e-182">All four of these tuples have the same number of fields (referred to as 'arity'), and the types of those fields are identical.</span></span> <span data-ttu-id="78d1e-183">このため、これらの割り当てはすべて機能します。</span><span class="sxs-lookup"><span data-stu-id="78d1e-183">Therefore, all of these assignments work:</span></span>

[!code-vb[Assign](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple3.vb#2)]

<span data-ttu-id="78d1e-184">タプルの名前が割り当てられていないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="78d1e-184">Notice that the names of the tuples are not assigned.</span></span> <span data-ttu-id="78d1e-185">フィールドの値は、タプルのフィールドの順序に従って割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="78d1e-185">The values of the fields are assigned following the order of the fields in the tuple.</span></span>

<span data-ttu-id="78d1e-186">最後に、`named` の最初のフィールドが `Integer`である場合でも、`named` タプルを `conversion` タプルに割り当てることができることに注意してください。`conversion` の最初のフィールドは `Long`です。</span><span class="sxs-lookup"><span data-stu-id="78d1e-186">Finally, notice that we can assign the `named` tuple to the `conversion` tuple, even though the first field of `named` is an `Integer`, and the first field of `conversion` is a `Long`.</span></span> <span data-ttu-id="78d1e-187">`Integer` を `Long` に変換することは、拡大変換であるため、この割り当ては成功します。</span><span class="sxs-lookup"><span data-stu-id="78d1e-187">This assignment succeeds because converting an `Integer` to a `Long` is a widening conversion.</span></span>

[!code-vb[Assign](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple3.vb#3)]

<span data-ttu-id="78d1e-188">フィールドの数が異なるタプルを割り当てることはできません。</span><span class="sxs-lookup"><span data-stu-id="78d1e-188">Tuples with different numbers of fields are not assignable:</span></span>

```vb
' Does not compile.
' VB30311: Value of type '(Integer, Integer, Integer)' cannot be converted
'          to '(Answer As Integer, Message As String)'
var differentShape = (1, 2, 3)
named = differentShape
```

## <a name="tuples-as-method-return-values"></a><span data-ttu-id="78d1e-189">メソッドの戻り値としてのタプル</span><span class="sxs-lookup"><span data-stu-id="78d1e-189">Tuples as method return values</span></span>

<span data-ttu-id="78d1e-190">メソッドは、1つの値のみを返すことができます。</span><span class="sxs-lookup"><span data-stu-id="78d1e-190">A method can return only a single value.</span></span> <span data-ttu-id="78d1e-191">しかし、多くの場合、メソッド呼び出しを使用して複数の値を返す必要があります。</span><span class="sxs-lookup"><span data-stu-id="78d1e-191">Frequently, though, you'd like a method call to return multiple values.</span></span> <span data-ttu-id="78d1e-192">この制限を回避するには、いくつかの方法があります。</span><span class="sxs-lookup"><span data-stu-id="78d1e-192">There are several ways to work around this limitation:</span></span>

- <span data-ttu-id="78d1e-193">メソッドによって返される値を表すプロパティまたはフィールドを持つカスタムクラスまたは構造体を作成できます。</span><span class="sxs-lookup"><span data-stu-id="78d1e-193">You can create a custom class or structure whose properties or fields represent values returned by the method.</span></span> <span data-ttu-id="78d1e-194">そのため、重いソリューションです。このためには、メソッド呼び出しから値を取得するだけの目的を持つカスタム型を定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="78d1e-194">Thus is a heavyweight solution; it requires that you define a custom type whose only purpose is to retrieve values from a method call.</span></span>

- <span data-ttu-id="78d1e-195">メソッドから1つの値を返すことができ、残りの値は、メソッドへの参照で渡すことによって返されます。</span><span class="sxs-lookup"><span data-stu-id="78d1e-195">You can return a single value from the method, and return the remaining values by passing them by reference to the method.</span></span> <span data-ttu-id="78d1e-196">これには、変数をインスタンス化する際のオーバーヘッドが含まれ、参照渡しで渡す変数の値が誤って上書きされるリスクがあります。</span><span class="sxs-lookup"><span data-stu-id="78d1e-196">This involves the overhead of instantiating a variable and risks inadvertently overwriting the value of the variable that you pass by reference.</span></span>

- <span data-ttu-id="78d1e-197">複数の戻り値を取得するためのライトウェイトソリューションを提供するタプルを使用できます。</span><span class="sxs-lookup"><span data-stu-id="78d1e-197">You can use a tuple, which provides a lightweight solution to retrieving multiple return values.</span></span>

<span data-ttu-id="78d1e-198">たとえば、.NET の**TryParse**メソッドは、解析操作が成功したかどうかを示す `Boolean` 値を返します。</span><span class="sxs-lookup"><span data-stu-id="78d1e-198">For example, the **TryParse** methods in .NET return a `Boolean` value that indicates whether the parsing operation succeeded.</span></span> <span data-ttu-id="78d1e-199">解析操作の結果は、メソッドへの参照によって渡される変数に返されます。</span><span class="sxs-lookup"><span data-stu-id="78d1e-199">The result of the parsing operation is returned in a variable passed by reference to the method.</span></span> <span data-ttu-id="78d1e-200">通常、<xref:System.Int32.TryParse%2A?displayProperty=nameWithType> などの解析メソッドを呼び出すと、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="78d1e-200">Normally, a call to the a parsing method such as <xref:System.Int32.TryParse%2A?displayProperty=nameWithType> looks like the following:</span></span>

[!code-vb[Return](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple-returns.vb#1)]

<span data-ttu-id="78d1e-201">独自のメソッドで <xref:System.Int32.TryParse%2A?displayProperty=nameWithType> メソッドへの呼び出しをラップすると、解析操作からタプルを返すことができます。</span><span class="sxs-lookup"><span data-stu-id="78d1e-201">We can return a tuple from the parsing operation if we wrap the call to the <xref:System.Int32.TryParse%2A?displayProperty=nameWithType> method in our own method.</span></span> <span data-ttu-id="78d1e-202">次の例では、`NumericLibrary.ParseInteger` によって <xref:System.Int32.TryParse%2A?displayProperty=nameWithType> メソッドが呼び出され、2つの要素を持つ名前付きタプルが返されます。</span><span class="sxs-lookup"><span data-stu-id="78d1e-202">In the following example, `NumericLibrary.ParseInteger` calls the <xref:System.Int32.TryParse%2A?displayProperty=nameWithType> method and returns a named tuple with two elements.</span></span>

[!code-vb[Return](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple-returns.vb#2)]

<span data-ttu-id="78d1e-203">その後、次のようなコードを使用してメソッドを呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="78d1e-203">You can then call the method with code like the following:</span></span>

[!code-vb[Return](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple-returns.vb#3)]

## <a name="visual-basic-tuples-and-tuples-in-the-net-framework"></a><span data-ttu-id="78d1e-204">Visual Basic のタプルと、.NET Framework 内のタプル</span><span class="sxs-lookup"><span data-stu-id="78d1e-204">Visual Basic tuples and tuples in the .NET Framework</span></span>

<span data-ttu-id="78d1e-205">Visual Basic タプルは、.NET Framework 4.7 で導入された、**ValueTuple**ジェネリック型の 1 つのインスタンスです。</span><span class="sxs-lookup"><span data-stu-id="78d1e-205">A Visual Basic tuple is an instance of one of the **System.ValueTuple** generic types, which were introduced in the .NET Framework 4.7.</span></span> <span data-ttu-id="78d1e-206">.NET Framework には、一連の汎用的な **Tuple** クラスも含まれています。</span><span class="sxs-lookup"><span data-stu-id="78d1e-206">The .NET Framework also includes a set of generic **System.Tuple** classes.</span></span> <span data-ttu-id="78d1e-207">ただし、これらのクラスは、Visual Basic タプルと、次のようなさまざまな方法での **ValueTuple** ジェネリック型とは異なります。</span><span class="sxs-lookup"><span data-stu-id="78d1e-207">These classes, however, differ from Visual Basic tuples and the **System.ValueTuple** generic types in a number of ways:</span></span>

- <span data-ttu-id="78d1e-208">**タプル**クラスの要素は、`Item1`、`Item2`などという名前のプロパティです。</span><span class="sxs-lookup"><span data-stu-id="78d1e-208">The elements of the **Tuple** classes are properties named `Item1`, `Item2`, and so on.</span></span> <span data-ttu-id="78d1e-209">Visual Basic タプルと **valuetuple** 型では、tuple 要素はフィールドです。</span><span class="sxs-lookup"><span data-stu-id="78d1e-209">In Visual Basic tuples and the **ValueTuple** types, tuple elements are fields.</span></span>

- <span data-ttu-id="78d1e-210">**タプル** のインスタンスまたは **valuetuple** インスタンスの要素にわかりやすい名前を割り当てることはできません。</span><span class="sxs-lookup"><span data-stu-id="78d1e-210">You cannot assign meaningful names to the elements of a **Tuple** instance or of a **ValueTuple** instance.</span></span> <span data-ttu-id="78d1e-211">Visual Basic を使用すると、フィールドの意味を伝える名前を割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="78d1e-211">Visual Basic allows you to assign names that communicate the meaning of the fields.</span></span>

- <span data-ttu-id="78d1e-212">**タプル** インスタンスのプロパティは読み取り専用です。タプルは変更できません。</span><span class="sxs-lookup"><span data-stu-id="78d1e-212">The properties of a **Tuple** instance are read-only; the tuples are immutable.</span></span> <span data-ttu-id="78d1e-213">Visual Basic タプルと **valuetuple** 型では、タプルフィールドは読み取り/書き込み可能です。タプルは変更可能です。</span><span class="sxs-lookup"><span data-stu-id="78d1e-213">In Visual Basic tuples and the **ValueTuple** types, tuple fields are read-write; the tuples are mutable.</span></span>

- <span data-ttu-id="78d1e-214">ジェネリック**タプル** 型は参照型です。</span><span class="sxs-lookup"><span data-stu-id="78d1e-214">The generic **Tuple** types are reference types.</span></span> <span data-ttu-id="78d1e-215">これらの **タプル** 型を使用することは、オブジェクトを割り当てることを意味します。</span><span class="sxs-lookup"><span data-stu-id="78d1e-215">Using these **Tuple** types means allocating objects.</span></span> <span data-ttu-id="78d1e-216">ホット パスでは、これがアプリケーションのパフォーマンスに大きな影響を与えることがあります。</span><span class="sxs-lookup"><span data-stu-id="78d1e-216">On hot paths, this can have a measurable impact on your application's performance.</span></span> <span data-ttu-id="78d1e-217">Visual Basic タプルと **Valuetuple** 型は値型です。</span><span class="sxs-lookup"><span data-stu-id="78d1e-217">Visual Basic tuples and the **ValueTuple** types are value types.</span></span>

<span data-ttu-id="78d1e-218"><xref:System.TupleExtensions> クラスの拡張メソッドを使用すると、Visual Basic タプルと .NET **Tuple** オブジェクト間で簡単に変換できます。</span><span class="sxs-lookup"><span data-stu-id="78d1e-218">Extension methods in the <xref:System.TupleExtensions> class make it easy to convert between Visual Basic tuples and .NET **Tuple** objects.</span></span> <span data-ttu-id="78d1e-219">**Totuple** メソッドは、Visual Basic タプルを .net **tuple** オブジェクトに変換し、 **tovaluetuple** メソッドは .net **タプル** オブジェクトを Visual Basic タプルに変換します。</span><span class="sxs-lookup"><span data-stu-id="78d1e-219">The **ToTuple** method converts a Visual Basic tuple to a .NET **Tuple** object, and the **ToValueTuple** method converts a .NET **Tuple** object to a Visual Basic tuple.</span></span>

<span data-ttu-id="78d1e-220">次の例では、タプルを作成し、それを .NET **tuple** オブジェクトに変換して、Visual Basic タプルに変換して戻します。</span><span class="sxs-lookup"><span data-stu-id="78d1e-220">The following example creates a tuple, converts it to a .NET **Tuple** object, and converts it back to a Visual Basic tuple.</span></span> <span data-ttu-id="78d1e-221">この例では、このタプルを元のタプルと比較して、それらが等しいことを確認します。</span><span class="sxs-lookup"><span data-stu-id="78d1e-221">The example then compares this tuple with the original one to ensure that they are equal.</span></span>

[!code-vb[Convert](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple2.vb#1)]

## <a name="see-also"></a><span data-ttu-id="78d1e-222">関連項目</span><span class="sxs-lookup"><span data-stu-id="78d1e-222">See also</span></span>

- [<span data-ttu-id="78d1e-223">Visual Basic の言語リファレンス</span><span class="sxs-lookup"><span data-stu-id="78d1e-223">Visual Basic Language Reference</span></span>](index.md)
