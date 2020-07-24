---
title: インデクサーの使用 - C# プログラミング ガイド
ms.date: 07/15/2020
helpviewer_keywords:
- indexers [C#], about indexers
ms.assetid: df70e1a2-3ce3-4aba-ad80-4b2f3538699f
ms.openlocfilehash: e742e4dd5ea92ec3baf37c915e024e713022b7b6
ms.sourcegitcommit: 3492dafceb5d4183b6b0d2f3bdf4a1abc4d5ed8c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/16/2020
ms.locfileid: "86416238"
---
# <a name="using-indexers-c-programming-guide"></a><span data-ttu-id="38787-102">インデクサーの使用 (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="38787-102">Using indexers (C# Programming Guide)</span></span>

<span data-ttu-id="38787-103">インデクサーによって構文上の利便性がもたらされます。これを使用すると、[クラス](../../language-reference/keywords/class.md)、[構造体](../../language-reference/builtin-types/struct.md)、または[インターフェイス](../../language-reference/keywords/interface.md)を作成でき、クライアント アプリケーションから配列と同じようにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="38787-103">Indexers are a syntactic convenience that enable you to create a [class](../../language-reference/keywords/class.md), [struct](../../language-reference/builtin-types/struct.md), or [interface](../../language-reference/keywords/interface.md) that client applications can access as an array.</span></span> <span data-ttu-id="38787-104">コンパイラによって、`Item` プロパティ (または、<xref:System.Runtime.CompilerServices.IndexerNameAttribute> が存在する場合は別の名前が付けられたプロパティ) と、適切なアクセサー メソッドが生成されます。</span><span class="sxs-lookup"><span data-stu-id="38787-104">The compiler will generate an `Item` property (or an alternatively named property if <xref:System.Runtime.CompilerServices.IndexerNameAttribute> is present), and the appropriate accessor methods.</span></span> <span data-ttu-id="38787-105">インデクサーは、内部コレクションまたは配列をカプセル化することが主な目的である型で最も多く実装されます。</span><span class="sxs-lookup"><span data-stu-id="38787-105">Indexers are most frequently implemented in types whose primary purpose is to encapsulate an internal collection or array.</span></span> <span data-ttu-id="38787-106">たとえば、24 時間のうちの異なる 10 回の時刻で記録した温度を華氏で表す `TempRecord` クラスがあるとします。</span><span class="sxs-lookup"><span data-stu-id="38787-106">For example, suppose you have a class `TempRecord` that represents the temperature in Fahrenheit as recorded at 10 different times during a 24-hour period.</span></span> <span data-ttu-id="38787-107">このクラスには、温度値を格納する `float[]` 型の配列 `temps` が含まれています。</span><span class="sxs-lookup"><span data-stu-id="38787-107">The class contains a `temps` array of type `float[]` to store the temperature values.</span></span> <span data-ttu-id="38787-108">このクラスにインデクサーを実装することで、クライアントは、`float temp = tempRecord.temps[4]` ではなく `float temp = tempRecord[4]` として `TempRecord` インスタンスの温度にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="38787-108">By implementing an indexer in this class, clients can access the temperatures in a `TempRecord` instance as `float temp = tempRecord[4]` instead of as `float temp = tempRecord.temps[4]`.</span></span> <span data-ttu-id="38787-109">インデクサー表記を使用すると、クライアント アプリケーションの構文が簡略化されるだけでなく、クラスとその目的が、他の開発者たちにとってわかりやすい、より直感的なものとなります。</span><span class="sxs-lookup"><span data-stu-id="38787-109">The indexer notation not only simplifies the syntax for client applications; it also makes the class, and its purpose more intuitive for other developers to understand.</span></span>

<span data-ttu-id="38787-110">クラスまたは構造体でインデクサーを宣言するには、次の例のように [this](../../language-reference/keywords/this.md) キーワードを使用します。</span><span class="sxs-lookup"><span data-stu-id="38787-110">To declare an indexer on a class or struct, use the [this](../../language-reference/keywords/this.md) keyword, as the following example shows:</span></span>

```csharp
// Indexer declaration
public int this[int index]
{
    // get and set accessors
}
```

> [!IMPORTANT]
> <span data-ttu-id="38787-111">インデクサーを宣言すると、オブジェクト上に `Item` という名前のプロパティが自動的に生成されます。</span><span class="sxs-lookup"><span data-stu-id="38787-111">Declaring an indexer will automatically generate a property named `Item` on the object.</span></span> <span data-ttu-id="38787-112">`Item` プロパティは、インスタンスの[メンバー アクセス式](../../language-reference/operators/member-access-operators.md#member-access-expression-)から直接アクセスすることはできません。</span><span class="sxs-lookup"><span data-stu-id="38787-112">The `Item` property is not directly accessible from the instance [member access expression](../../language-reference/operators/member-access-operators.md#member-access-expression-).</span></span> <span data-ttu-id="38787-113">また、インデクサーを使用して独自の `Item` プロパティをオブジェクトに追加すると、[CS0102 コンパイラエラー](../../misc/cs0102.md)が発生します。</span><span class="sxs-lookup"><span data-stu-id="38787-113">Additionally, if you add your own `Item` property to an object with an indexer, you'll get a [CS0102 compiler error](../../misc/cs0102.md).</span></span> <span data-ttu-id="38787-114">このエラーを回避するには、以下で説明するように、<xref:System.Runtime.CompilerServices.IndexerNameAttribute> を使用してインデクサーの名前を変更します。</span><span class="sxs-lookup"><span data-stu-id="38787-114">To avoid this error, use the <xref:System.Runtime.CompilerServices.IndexerNameAttribute> rename the indexer as detailed below.</span></span>

## <a name="remarks"></a><span data-ttu-id="38787-115">Remarks</span><span class="sxs-lookup"><span data-stu-id="38787-115">Remarks</span></span>

<span data-ttu-id="38787-116">インデクサーの型とそのパラメーターの型は、少なくとも、インデクサー自体と同程度にアクセス可能である必要があります。</span><span class="sxs-lookup"><span data-stu-id="38787-116">The type of an indexer and the type of its parameters must be at least as accessible as the indexer itself.</span></span> <span data-ttu-id="38787-117">アクセシビリティ レベルの詳細については、「[アクセス修飾子 (C# リファレンス)](../../language-reference/keywords/access-modifiers.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="38787-117">For more information about accessibility levels, see [Access Modifiers](../../language-reference/keywords/access-modifiers.md).</span></span>

<span data-ttu-id="38787-118">インターフェイスでインデクサーを使用する方法の詳細については、「[インターフェイスのインデクサー (C# プログラミング ガイド)](./indexers-in-interfaces.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="38787-118">For more information about how to use indexers with an interface, see [Interface Indexers](./indexers-in-interfaces.md).</span></span>

<span data-ttu-id="38787-119">インデクサーのシグネチャは、その仮パラメーターの数と型で構成されます。</span><span class="sxs-lookup"><span data-stu-id="38787-119">The signature of an indexer consists of the number and types of its formal parameters.</span></span> <span data-ttu-id="38787-120">これには、インデクサーの型や仮パラメーターの名前は含まれません。</span><span class="sxs-lookup"><span data-stu-id="38787-120">It doesn't include the indexer type or the names of the formal parameters.</span></span> <span data-ttu-id="38787-121">同じクラス内に複数のインデクサーを宣言する場合は、異なるシグネチャが必要です。</span><span class="sxs-lookup"><span data-stu-id="38787-121">If you declare more than one indexer in the same class, they must have different signatures.</span></span>

<span data-ttu-id="38787-122">インデクサーの値は変数として分類されないため、インデクサーの値を [ref](../../language-reference/keywords/ref.md) や [out](../../language-reference/keywords/out-parameter-modifier.md) パラメーターとして渡すことはできません。</span><span class="sxs-lookup"><span data-stu-id="38787-122">An indexer value is not classified as a variable; therefore, you cannot pass an indexer value as a [ref](../../language-reference/keywords/ref.md) or [out](../../language-reference/keywords/out-parameter-modifier.md) parameter.</span></span>

<span data-ttu-id="38787-123">他の言語が使用できる名前をインデクサーに指定するには、次の例のように <xref:System.Runtime.CompilerServices.IndexerNameAttribute?displayProperty=nameWithType> を使用します。</span><span class="sxs-lookup"><span data-stu-id="38787-123">To provide the indexer with a name that other languages can use, use <xref:System.Runtime.CompilerServices.IndexerNameAttribute?displayProperty=nameWithType>, as the following example shows:</span></span>

```csharp
// Indexer declaration
[System.Runtime.CompilerServices.IndexerName("TheItem")]
public int this[int index]
{
    // get and set accessors
}
```

<span data-ttu-id="38787-124">インデクサー名属性によってオーバーライドされるため、このインデクサーの名前は `TheItem` になります。</span><span class="sxs-lookup"><span data-stu-id="38787-124">This indexer will have the name `TheItem`, as it is overridden by the indexer name attribute.</span></span> <span data-ttu-id="38787-125">既定では、インデクサーの名前は `Item` です。</span><span class="sxs-lookup"><span data-stu-id="38787-125">By default, the indexer name is `Item`.</span></span>

## <a name="example-1"></a><span data-ttu-id="38787-126">例 1</span><span class="sxs-lookup"><span data-stu-id="38787-126">Example 1</span></span>

<span data-ttu-id="38787-127">次の例は、プライベートな配列フィールド `temps` とインデクサーの宣言方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="38787-127">The following example shows how to declare a private array field, `temps`, and an indexer.</span></span> <span data-ttu-id="38787-128">インデクサーを使用すれば、インスタンス `tempRecord[i]` に直接アクセスできます。</span><span class="sxs-lookup"><span data-stu-id="38787-128">The indexer enables direct access to the instance `tempRecord[i]`.</span></span> <span data-ttu-id="38787-129">インデクサーを使用しない場合は、配列を [public](../../language-reference/keywords/public.md) メンバーとして宣言し、そのメンバー `tempRecord.temps[i]` に直接アクセスします。</span><span class="sxs-lookup"><span data-stu-id="38787-129">The alternative to using the indexer is to declare the array as a [public](../../language-reference/keywords/public.md) member and access its members, `tempRecord.temps[i]`, directly.</span></span>

:::code language="csharp" source="snippets/Temperatures/TempRecord.cs":::

<span data-ttu-id="38787-130">`Console.Write` ステートメントなどでインデクサーのアクセスが評価されると、[get](../../language-reference/keywords/get.md) アクセサーが呼び出されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="38787-130">Notice that when an indexer's access is evaluated, for example, in a `Console.Write` statement, the [get](../../language-reference/keywords/get.md) accessor is invoked.</span></span> <span data-ttu-id="38787-131">したがって、`get` アクセサーが存在しない場合は、コンパイル時エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="38787-131">Therefore, if no `get` accessor exists, a compile-time error occurs.</span></span>

:::code language="csharp" source="snippets/Temperatures/Program.cs":::

## <a name="indexing-using-other-values"></a><span data-ttu-id="38787-132">他の値を使用したインデックス作成</span><span class="sxs-lookup"><span data-stu-id="38787-132">Indexing using other values</span></span>

<span data-ttu-id="38787-133">C# では、インデクサー パラメーター型は整数に制限されません。</span><span class="sxs-lookup"><span data-stu-id="38787-133">C# doesn't limit the indexer parameter type to integer.</span></span> <span data-ttu-id="38787-134">たとえば、文字列をインデクサーで使用すると有効な場合があります。</span><span class="sxs-lookup"><span data-stu-id="38787-134">For example, it may be useful to use a string with an indexer.</span></span> <span data-ttu-id="38787-135">このようなインデクサーは、コレクション内の文字列を検索し、適切な値を返すことによって実装される場合があります。</span><span class="sxs-lookup"><span data-stu-id="38787-135">Such an indexer might be implemented by searching for the string in the collection, and returning the appropriate value.</span></span> <span data-ttu-id="38787-136">アクセサーはオーバーロードできるため、文字列と整数のバージョンは共存できます。</span><span class="sxs-lookup"><span data-stu-id="38787-136">As accessors can be overloaded, the string and integer versions can coexist.</span></span>

## <a name="example-2"></a><span data-ttu-id="38787-137">例 2</span><span class="sxs-lookup"><span data-stu-id="38787-137">Example 2</span></span>

<span data-ttu-id="38787-138">次の例では、曜日を格納するクラスを宣言しています。</span><span class="sxs-lookup"><span data-stu-id="38787-138">The following example declares a class that stores the days of the week.</span></span> <span data-ttu-id="38787-139">`get` アクセサーは、曜日を示す文字列を受け取り、対応する整数を返します。</span><span class="sxs-lookup"><span data-stu-id="38787-139">A `get` accessor takes a string, the name of a day, and returns the corresponding integer.</span></span> <span data-ttu-id="38787-140">たとえば、"Sunday" は 0、"Monday" は 1 などと値を返します。</span><span class="sxs-lookup"><span data-stu-id="38787-140">For example, "Sunday" returns 0, "Monday" returns 1, and so on.</span></span>

:::code language="csharp" source="snippets/StringIndexers/DayCollection.cs":::

### <a name="consuming-example-2"></a><span data-ttu-id="38787-141">使用例 2</span><span class="sxs-lookup"><span data-stu-id="38787-141">Consuming example 2</span></span>

:::code language="csharp" source="snippets/StringIndexers/Program.cs":::

## <a name="example-3"></a><span data-ttu-id="38787-142">例 3</span><span class="sxs-lookup"><span data-stu-id="38787-142">Example 3</span></span>

<span data-ttu-id="38787-143">次の例では、<xref:System.DayOfWeek?displayProperty=fullName> 列挙型の使用により、曜日を格納するクラスが宣言されています。</span><span class="sxs-lookup"><span data-stu-id="38787-143">The following example declares a class that stores the days of the week using the <xref:System.DayOfWeek?displayProperty=fullName> enum.</span></span> <span data-ttu-id="38787-144">曜日を示す `DayOfWeek` が`get` アクセサーにより受け取られ、対応する整数が返されます。</span><span class="sxs-lookup"><span data-stu-id="38787-144">A `get` accessor takes a `DayOfWeek`, the value of a day, and returns the corresponding integer.</span></span> <span data-ttu-id="38787-145">たとえば、`DayOfWeek.Sunday` の場合は 0 が返される、`DayOfWeek.Monday` の場合は 1 が返されるなどです。</span><span class="sxs-lookup"><span data-stu-id="38787-145">For example, `DayOfWeek.Sunday` returns 0, `DayOfWeek.Monday` returns 1, and so on.</span></span>

:::code language="csharp" source="snippets/DayOfWeekIndexers/DayOfWeekCollection.cs":::

### <a name="consuming-example-3"></a><span data-ttu-id="38787-146">使用例 3</span><span class="sxs-lookup"><span data-stu-id="38787-146">Consuming example 3</span></span>

:::code language="csharp" source="snippets/DayOfWeekIndexers/Program.cs":::

## <a name="robust-programming"></a><span data-ttu-id="38787-147">信頼性の高いプログラミング</span><span class="sxs-lookup"><span data-stu-id="38787-147">Robust programming</span></span>

<span data-ttu-id="38787-148">インデクサーのセキュリティと信頼性を改善するには、主に次の 2 つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="38787-148">There are two main ways in which the security and reliability of indexers can be improved:</span></span>

- <span data-ttu-id="38787-149">クライアント コードが無効なインデックス値を渡しても、それを処理できるように必ずエラー処理戦略を組み込んでください。</span><span class="sxs-lookup"><span data-stu-id="38787-149">Be sure to incorporate some type of error-handling strategy to handle the chance of client code passing in an invalid index value.</span></span> <span data-ttu-id="38787-150">このトピックの最初の例の TempRecord クラスには Length プロパティが用意されており、入力がインデクサーに渡される前にクライアント コードで検証できるようになっています。</span><span class="sxs-lookup"><span data-stu-id="38787-150">In the first example earlier in this topic, the TempRecord class provides a Length property that enables the client code to verify the input before passing it to the indexer.</span></span> <span data-ttu-id="38787-151">インデクサー自体にエラー処理コードを配置することもできます。</span><span class="sxs-lookup"><span data-stu-id="38787-151">You can also put the error handling code inside the indexer itself.</span></span> <span data-ttu-id="38787-152">インデクサーのアクセサー内部でスローされる例外はすべて、ユーザーのために文書化してください。</span><span class="sxs-lookup"><span data-stu-id="38787-152">Be sure to document for users any exceptions that you throw inside an indexer accessor.</span></span>

- <span data-ttu-id="38787-153">[get](../../language-reference/keywords/get.md) および [set](../../language-reference/keywords/set.md) アクセサーのアクセシビリティを設定し、適切な制限を指定します。</span><span class="sxs-lookup"><span data-stu-id="38787-153">Set the accessibility of the [get](../../language-reference/keywords/get.md) and [set](../../language-reference/keywords/set.md) accessors to be as restrictive as is reasonable.</span></span> <span data-ttu-id="38787-154">これは、`set` アクセサーの場合、特に重要です。</span><span class="sxs-lookup"><span data-stu-id="38787-154">This is important for the `set` accessor in particular.</span></span> <span data-ttu-id="38787-155">詳細については、「[アクセサーのアクセシビリティの制限](../classes-and-structs/restricting-accessor-accessibility.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="38787-155">For more information, see [Restricting Accessor Accessibility](../classes-and-structs/restricting-accessor-accessibility.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="38787-156">関連項目</span><span class="sxs-lookup"><span data-stu-id="38787-156">See also</span></span>

- [<span data-ttu-id="38787-157">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="38787-157">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="38787-158">インデクサー</span><span class="sxs-lookup"><span data-stu-id="38787-158">Indexers</span></span>](./index.md)
- [<span data-ttu-id="38787-159">プロパティ</span><span class="sxs-lookup"><span data-stu-id="38787-159">Properties</span></span>](../classes-and-structs/properties.md)
