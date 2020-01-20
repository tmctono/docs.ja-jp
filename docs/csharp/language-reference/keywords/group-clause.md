---
title: group 句 - C# リファレンス
ms.date: 07/20/2015
f1_keywords:
- group
- group_CSharpKeyword
helpviewer_keywords:
- group keyword [C#]
- group clause [C#]
ms.assetid: c817242e-b12c-4baa-a57e-73ee138f34d1
ms.openlocfilehash: 75a366ec24e4e48af7e87d3372950aad8d76435b
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/07/2020
ms.locfileid: "75713469"
---
# <a name="group-clause-c-reference"></a><span data-ttu-id="72c7b-102">group 句 (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="72c7b-102">group clause (C# Reference)</span></span>

<span data-ttu-id="72c7b-103">`group` 句は、グループのキー値に一致する 0 個以上の項目を含む <xref:System.Linq.IGrouping%602> オブジェクトのシーケンスを返します。</span><span class="sxs-lookup"><span data-stu-id="72c7b-103">The `group` clause returns a sequence of <xref:System.Linq.IGrouping%602> objects that contain zero or more items that match the key value for the group.</span></span> <span data-ttu-id="72c7b-104">たとえば、各文字列の最初の文字に基づいて文字列のシーケンスをグループ化することができます。</span><span class="sxs-lookup"><span data-stu-id="72c7b-104">For example, you can group a sequence of strings according to the first letter in each string.</span></span> <span data-ttu-id="72c7b-105">この場合、最初の文字がキーで、型は [char](../builtin-types/char.md) であり、各 <xref:System.Linq.IGrouping%602> オブジェクトの `Key` プロパティに格納されています。</span><span class="sxs-lookup"><span data-stu-id="72c7b-105">In this case, the first letter is the key and has a type [char](../builtin-types/char.md), and is stored in the `Key` property of each <xref:System.Linq.IGrouping%602> object.</span></span> <span data-ttu-id="72c7b-106">コンパイラは、キーの型を推論します。</span><span class="sxs-lookup"><span data-stu-id="72c7b-106">The compiler infers the type of the key.</span></span>

<span data-ttu-id="72c7b-107">次の例で示すように、クエリ式は `group` 句で終了できます。</span><span class="sxs-lookup"><span data-stu-id="72c7b-107">You can end a query expression with a `group` clause, as shown in the following example:</span></span>

[!code-csharp[cscsrefQueryKeywords#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Group.cs#10)]

<span data-ttu-id="72c7b-108">各グループで追加のクエリ操作を実行する場合、[into](into.md) コンテキスト キーワードを使用して一時的な識別子を指定できます。</span><span class="sxs-lookup"><span data-stu-id="72c7b-108">If you want to perform additional query operations on each group, you can specify a temporary identifier by using the [into](into.md) contextual keyword.</span></span> <span data-ttu-id="72c7b-109">`into` を使用する場合、次の抜粋に示すように、クエリを続行し、最終的には `select` ステートメントまたは別の `group` 句でそれを終了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="72c7b-109">When you use `into`, you must continue with the query, and eventually end it with either a `select` statement or another `group` clause, as shown in the following excerpt:</span></span>

[!code-csharp[cscsrefQueryKeywords#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Group.cs#11)]

<span data-ttu-id="72c7b-110">この記事の「例」のセクションでは、`into` を含む場合と含まない場合の `group` の使用方法の完全な例があります。</span><span class="sxs-lookup"><span data-stu-id="72c7b-110">More complete examples of the use of `group` with and without `into` are provided in the Example section of this article.</span></span>

## <a name="enumerating-the-results-of-a-group-query"></a><span data-ttu-id="72c7b-111">グループ クエリの結果を列挙する</span><span class="sxs-lookup"><span data-stu-id="72c7b-111">Enumerating the results of a group query</span></span>

<span data-ttu-id="72c7b-112">`group` クエリによって生成される <xref:System.Linq.IGrouping%602> オブジェクトは基本的には、リストのリストであるため、各グループのアイテムにアクセスするには、入れ子になった [foreach](foreach-in.md) ループを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="72c7b-112">Because the <xref:System.Linq.IGrouping%602> objects produced by a `group` query are essentially a list of lists, you must use a nested [foreach](foreach-in.md) loop to access the items in each group.</span></span> <span data-ttu-id="72c7b-113">外側のループがグループ キーを反復処理し、内側のループがグループ自体の各項目を反復処理します。</span><span class="sxs-lookup"><span data-stu-id="72c7b-113">The outer loop iterates over the group keys, and the inner loop iterates over each item in the group itself.</span></span> <span data-ttu-id="72c7b-114">グループには、キーがある場合はありますが、要素はありません。</span><span class="sxs-lookup"><span data-stu-id="72c7b-114">A group may have a key but no elements.</span></span> <span data-ttu-id="72c7b-115">次に、前のコード例でクエリを実行する `foreach` ループを示します。</span><span class="sxs-lookup"><span data-stu-id="72c7b-115">The following is the `foreach` loop that executes the query in the previous code examples:</span></span>

[!code-csharp[cscsrefQueryKeywords#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Group.cs#12)]

## <a name="key-types"></a><span data-ttu-id="72c7b-116">キーの種類</span><span class="sxs-lookup"><span data-stu-id="72c7b-116">Key types</span></span>

<span data-ttu-id="72c7b-117">グループ キーは、文字列、組み込みの数値型、またはユーザー定義の名前付きの型または匿名型など、任意の型にすることができます。</span><span class="sxs-lookup"><span data-stu-id="72c7b-117">Group keys can be any type, such as a string, a built-in numeric type, or a user-defined named type or anonymous type.</span></span>

### <a name="grouping-by-string"></a><span data-ttu-id="72c7b-118">文字列でグループ化する</span><span class="sxs-lookup"><span data-stu-id="72c7b-118">Grouping by string</span></span>

<span data-ttu-id="72c7b-119">前のコード例では、`char` を使用していました。</span><span class="sxs-lookup"><span data-stu-id="72c7b-119">The previous code examples used a `char`.</span></span> <span data-ttu-id="72c7b-120">姓を完全に指定するなど、簡単に代わりに文字列のキーを指定できます。</span><span class="sxs-lookup"><span data-stu-id="72c7b-120">A string key could easily have been specified instead, for example the complete last name:</span></span>

[!code-csharp[cscsrefQueryKeywords#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Group.cs#13)]

### <a name="grouping-by-bool"></a><span data-ttu-id="72c7b-121">ブールでグループ化する</span><span class="sxs-lookup"><span data-stu-id="72c7b-121">Grouping by bool</span></span>

<span data-ttu-id="72c7b-122">次の例では、結果を 2 つのグループに分割するためのキー用のブール値の用途を示します。</span><span class="sxs-lookup"><span data-stu-id="72c7b-122">The following example shows the use of a bool value for a key to divide the results into two groups.</span></span> <span data-ttu-id="72c7b-123">値は `group` 句のサブ式で生成されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="72c7b-123">Note that the value is produced by a sub-expression in the `group` clause.</span></span>

[!code-csharp[cscsrefQueryKeywords#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Group.cs#14)]

### <a name="grouping-by-numeric-range"></a><span data-ttu-id="72c7b-124">数値の範囲でグループ化する</span><span class="sxs-lookup"><span data-stu-id="72c7b-124">Grouping by numeric range</span></span>

<span data-ttu-id="72c7b-125">次の例では、パーセンタイルの範囲を示す数値のグループ キーを作成する式を使用しています。</span><span class="sxs-lookup"><span data-stu-id="72c7b-125">The next example uses an expression to create numeric group keys that represent a percentile range.</span></span> <span data-ttu-id="72c7b-126">`group` 句でメソッドを 2 度呼び出さなくて済むように、メソッド呼び出しの結果を格納する便利な場所として [let](let-clause.md) を使用できます。</span><span class="sxs-lookup"><span data-stu-id="72c7b-126">Note the use of [let](let-clause.md) as a convenient location to store a method call result, so that you don't have to call the method two times in the `group` clause.</span></span> <span data-ttu-id="72c7b-127">クエリ式でメソッドを安全に使用する方法の詳細については、「[クエリ式の例外の処理](../../linq/handle-exceptions-in-query-expressions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="72c7b-127">For more information about how to safely use methods in query expressions, see [Handle exceptions in query expressions](../../linq/handle-exceptions-in-query-expressions.md).</span></span>

[!code-csharp[cscsrefQueryKeywords#15](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Group.cs#15)]

### <a name="grouping-by-composite-keys"></a><span data-ttu-id="72c7b-128">複合キーでグループ化する</span><span class="sxs-lookup"><span data-stu-id="72c7b-128">Grouping by composite keys</span></span>

<span data-ttu-id="72c7b-129">1 つ以上のキーを使用して要素をグループ化するには、複合キーを使用します。</span><span class="sxs-lookup"><span data-stu-id="72c7b-129">Use a composite key when you want to group elements according to more than one key.</span></span> <span data-ttu-id="72c7b-130">複合キーは、キー要素を保持する、匿名型または名前付きの型を使用して作成できます。</span><span class="sxs-lookup"><span data-stu-id="72c7b-130">You create a composite key by using an anonymous type or a named type to hold the key element.</span></span> <span data-ttu-id="72c7b-131">次の例では、クラス `Person` が、`surname` と `city` という名前のメンバーで宣言されていると想定しています。</span><span class="sxs-lookup"><span data-stu-id="72c7b-131">In the following example, assume that a class `Person` has been declared with members named `surname` and `city`.</span></span> <span data-ttu-id="72c7b-132">`group` 句により、同じ名前と同じ市の人物のセットごとに、別のグループが作成されます。</span><span class="sxs-lookup"><span data-stu-id="72c7b-132">The `group` clause causes a separate group to be created for each set of persons with the same last name and the same city.</span></span>

```csharp
group person by new {name = person.surname, city = person.city};
```

<span data-ttu-id="72c7b-133">クエリ変数を別のメソッドに渡す場合には、名前付きの型を使用します。</span><span class="sxs-lookup"><span data-stu-id="72c7b-133">Use a named type if you must pass the query variable to another method.</span></span> <span data-ttu-id="72c7b-134">キーの自動実装プロパティを使用して特殊クラスを作成し、<xref:System.Object.Equals%2A> メソッドと <xref:System.Object.GetHashCode%2A> メソッドをオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="72c7b-134">Create a special class using auto-implemented properties for the keys, and then override the <xref:System.Object.Equals%2A> and <xref:System.Object.GetHashCode%2A> methods.</span></span> <span data-ttu-id="72c7b-135">これらのメソッドを厳密にオーバーライドする必要がない構造体を使用することも可能です。</span><span class="sxs-lookup"><span data-stu-id="72c7b-135">You can also use a struct, in which case you do not strictly have to override those methods.</span></span> <span data-ttu-id="72c7b-136">詳細については、「[自動実装するプロパティを使用して簡易クラスを実装する方法](../../programming-guide/classes-and-structs/how-to-implement-a-lightweight-class-with-auto-implemented-properties.md)」と「[ディレクトリ ツリーで重複するファイルを照会する方法](../../programming-guide/concepts/linq/how-to-query-for-duplicate-files-in-a-directory-tree-linq.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="72c7b-136">For more information see [How to implement a lightweight class with auto-implemented properties](../../programming-guide/classes-and-structs/how-to-implement-a-lightweight-class-with-auto-implemented-properties.md) and [How to query for duplicate files in a directory tree](../../programming-guide/concepts/linq/how-to-query-for-duplicate-files-in-a-directory-tree-linq.md).</span></span> <span data-ttu-id="72c7b-137">後述の記事には、名前付きの型を複合キーで使用する方法のコード例があります。</span><span class="sxs-lookup"><span data-stu-id="72c7b-137">The latter article has a code example that demonstrates how to use a composite key with a named type.</span></span>

## <a name="example"></a><span data-ttu-id="72c7b-138">例</span><span class="sxs-lookup"><span data-stu-id="72c7b-138">Example</span></span>

<span data-ttu-id="72c7b-139">次の例では、グループにその他のクエリ ロジックが適用されていない場合、ソース データをグループに並べる標準的なパターンを示します。</span><span class="sxs-lookup"><span data-stu-id="72c7b-139">The following example shows the standard pattern for ordering source data into groups when no additional query logic is applied to the groups.</span></span> <span data-ttu-id="72c7b-140">これは連結なしのグループ化と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="72c7b-140">This is called a grouping without a continuation.</span></span> <span data-ttu-id="72c7b-141">文字列の配列の要素は、最初の文字でグループ化されます。</span><span class="sxs-lookup"><span data-stu-id="72c7b-141">The elements in an array of strings are grouped according to their first letter.</span></span> <span data-ttu-id="72c7b-142">クエリの結果は、型 `char` のパブリック `Key` プロパティを含む <xref:System.Linq.IGrouping%602> 型とグループに各項目を含む <xref:System.Collections.Generic.IEnumerable%601> コレクションです。</span><span class="sxs-lookup"><span data-stu-id="72c7b-142">The result of the query is an <xref:System.Linq.IGrouping%602> type that contains a public `Key` property of type `char` and an <xref:System.Collections.Generic.IEnumerable%601> collection that contains each item in the grouping.</span></span>

<span data-ttu-id="72c7b-143">`group` 句の結果は、シーケンスのシーケンスです。</span><span class="sxs-lookup"><span data-stu-id="72c7b-143">The result of a `group` clause is a sequence of sequences.</span></span> <span data-ttu-id="72c7b-144">そのため、返される各グループ内の各要素にアクセスするには、次の例のように、グループ キーを反復処理するループ内で入れ子になった `foreach` ループを使用します。</span><span class="sxs-lookup"><span data-stu-id="72c7b-144">Therefore, to access the individual elements within each returned group, use a nested `foreach` loop inside the loop that iterates the group keys, as shown in the following example.</span></span>

[!code-csharp[cscsrefQueryKeywords#16](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Group.cs#16)]

## <a name="example"></a><span data-ttu-id="72c7b-145">例</span><span class="sxs-lookup"><span data-stu-id="72c7b-145">Example</span></span>

<span data-ttu-id="72c7b-146">この例では、作成後に、`into` と共に *continuation* を使用し、グループに追加のロジックを実行する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="72c7b-146">This example shows how to perform additional logic on the groups after you have created them, by using a *continuation* with `into`.</span></span> <span data-ttu-id="72c7b-147">詳しくは、「[into](into.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="72c7b-147">For more information, see [into](into.md).</span></span> <span data-ttu-id="72c7b-148">次の例では、キー値が母音であるものだけを選択するために各グループに問い合せを行います。</span><span class="sxs-lookup"><span data-stu-id="72c7b-148">The following example queries each group to select only those whose key value is a vowel.</span></span>

[!code-csharp[cscsrefQueryKeywords#17](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Group.cs#17)]

## <a name="remarks"></a><span data-ttu-id="72c7b-149">Remarks</span><span class="sxs-lookup"><span data-stu-id="72c7b-149">Remarks</span></span>

<span data-ttu-id="72c7b-150">コンパイル時に `group` 句が <xref:System.Linq.Enumerable.GroupBy%2A> メソッドの呼び出しに変換されます。</span><span class="sxs-lookup"><span data-stu-id="72c7b-150">At compile time, `group` clauses are translated into calls to the <xref:System.Linq.Enumerable.GroupBy%2A> method.</span></span>

## <a name="see-also"></a><span data-ttu-id="72c7b-151">関連項目</span><span class="sxs-lookup"><span data-stu-id="72c7b-151">See also</span></span>

- <xref:System.Linq.IGrouping%602>
- <xref:System.Linq.Enumerable.GroupBy%2A>
- <xref:System.Linq.Enumerable.ThenBy%2A>
- <xref:System.Linq.Enumerable.ThenByDescending%2A>
- [<span data-ttu-id="72c7b-152">クエリ キーワード</span><span class="sxs-lookup"><span data-stu-id="72c7b-152">Query Keywords</span></span>](query-keywords.md)
- [<span data-ttu-id="72c7b-153">統合言語クエリ (LINQ)</span><span class="sxs-lookup"><span data-stu-id="72c7b-153">Language Integrated Query (LINQ)</span></span>](../../linq/index.md)
- [<span data-ttu-id="72c7b-154">入れ子になったグループの作成</span><span class="sxs-lookup"><span data-stu-id="72c7b-154">Create a nested group</span></span>](../../linq/create-a-nested-group.md)
- [<span data-ttu-id="72c7b-155">クエリ結果のグループ化</span><span class="sxs-lookup"><span data-stu-id="72c7b-155">Group query results</span></span>](../../linq/group-query-results.md)
- [<span data-ttu-id="72c7b-156">グループ化操作でのサブクエリの実行</span><span class="sxs-lookup"><span data-stu-id="72c7b-156">Perform a subquery on a grouping operation</span></span>](../../linq/perform-a-subquery-on-a-grouping-operation.md)
