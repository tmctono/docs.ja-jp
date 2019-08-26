---
title: インデクサーの使用 - C# プログラミング ガイド
ms.custom: seodec18
ms.date: 10/03/2018
helpviewer_keywords:
- indexers [C#], about indexers
ms.assetid: df70e1a2-3ce3-4aba-ad80-4b2f3538699f
ms.openlocfilehash: 4411fe0ffe7dc136b4e74adeba3e5596af3aa1db
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/19/2019
ms.locfileid: "69589429"
---
# <a name="using-indexers-c-programming-guide"></a><span data-ttu-id="b2bea-102">インデクサーの使用 (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="b2bea-102">Using indexers (C# Programming Guide)</span></span>

<span data-ttu-id="b2bea-103">インデクサーは構文を簡略化します。これを使用すると、[クラス](../../language-reference/keywords/class.md)、[構造体](../../language-reference/keywords/struct.md)、または[インターフェイス](../../language-reference/keywords/interface.md)を作成でき、クライアント アプリケーションは配列と同じようにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="b2bea-103">Indexers are a syntactic convenience that enable you to create a [class](../../language-reference/keywords/class.md), [struct](../../language-reference/keywords/struct.md), or [interface](../../language-reference/keywords/interface.md) that client applications can access just as an array.</span></span> <span data-ttu-id="b2bea-104">インデクサーは、内部コレクションまたは配列をカプセル化することが主な目的である型で最も多く実装されます。</span><span class="sxs-lookup"><span data-stu-id="b2bea-104">Indexers are most frequently implemented in types whose primary purpose is to encapsulate an internal collection or array.</span></span> <span data-ttu-id="b2bea-105">たとえば、24 時間のうちの異なる 10 回の時刻で記録した温度を華氏で表す `TempRecord` クラスがあるとします。</span><span class="sxs-lookup"><span data-stu-id="b2bea-105">For example, suppose you have a class `TempRecord` that represents the temperature in Fahrenheit as recorded at 10 different times during a 24 hour period.</span></span> <span data-ttu-id="b2bea-106">このクラスには、温度値を格納する `float[]` 型の配列 `temps` が含まれています。</span><span class="sxs-lookup"><span data-stu-id="b2bea-106">The class contains an array `temps` of type `float[]` to store the temperature values.</span></span> <span data-ttu-id="b2bea-107">このクラスにインデクサーを実装することで、クライアントは、`float temp = tr.temps[4]` ではなく `float temp = tr[4]` として `TempRecord` インスタンスの温度にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="b2bea-107">By implementing an indexer in this class, clients can access the temperatures in a `TempRecord` instance as `float temp = tr[4]` instead of as `float temp = tr.temps[4]`.</span></span> <span data-ttu-id="b2bea-108">インデクサーはクライアント アプリケーションの構文を簡略化するだけでなく、クラスとその目的を、他の開発者たちにとってわかりやすい、より直感的なものにします。</span><span class="sxs-lookup"><span data-stu-id="b2bea-108">The indexer notation not only simplifies the syntax for client applications; it also makes the class and its purpose more intuitive for other developers to understand.</span></span>  
  
<span data-ttu-id="b2bea-109">クラスまたは構造体でインデクサーを宣言するには、次の例のように [this](../../language-reference/keywords/this.md) キーワードを使用します。</span><span class="sxs-lookup"><span data-stu-id="b2bea-109">To declare an indexer on a class or struct, use the [this](../../language-reference/keywords/this.md) keyword, as the following example shows:</span></span>

```csharp
public int this[int index]    // Indexer declaration  
{  
    // get and set accessors  
}  
```

## <a name="remarks"></a><span data-ttu-id="b2bea-110">解説</span><span class="sxs-lookup"><span data-stu-id="b2bea-110">Remarks</span></span>

<span data-ttu-id="b2bea-111">インデクサーの型とそのパラメーターの型は、少なくとも、インデクサー自体と同程度にアクセス可能である必要があります。</span><span class="sxs-lookup"><span data-stu-id="b2bea-111">The type of an indexer and the type of its parameters must be at least as accessible as the indexer itself.</span></span> <span data-ttu-id="b2bea-112">アクセシビリティ レベルの詳細については、「[アクセス修飾子 (C# リファレンス)](../../language-reference/keywords/access-modifiers.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b2bea-112">For more information about accessibility levels, see [Access Modifiers](../../language-reference/keywords/access-modifiers.md).</span></span>  
  
 <span data-ttu-id="b2bea-113">インターフェイスでインデクサーを使用する方法の詳細については、「[インターフェイスのインデクサー (C# プログラミング ガイド)](./indexers-in-interfaces.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b2bea-113">For more information about how to use indexers with an interface, see [Interface Indexers](./indexers-in-interfaces.md).</span></span>  
  
 <span data-ttu-id="b2bea-114">インデクサーのシグネチャは、その仮パラメーターの数と型で構成されます。</span><span class="sxs-lookup"><span data-stu-id="b2bea-114">The signature of an indexer consists of the number and types of its formal parameters.</span></span> <span data-ttu-id="b2bea-115">これには、インデクサーの型や仮パラメーターの名前は含まれません。</span><span class="sxs-lookup"><span data-stu-id="b2bea-115">It doesn't include the indexer type or the names of the formal parameters.</span></span> <span data-ttu-id="b2bea-116">同じクラス内に複数のインデクサーを宣言する場合は、異なるシグネチャが必要です。</span><span class="sxs-lookup"><span data-stu-id="b2bea-116">If you declare more than one indexer in the same class, they must have different signatures.</span></span>  
  
 <span data-ttu-id="b2bea-117">インデクサーの値は変数として分類されないため、インデクサーの値を [ref](../../language-reference/keywords/ref.md) や [out](../../language-reference/keywords/out-parameter-modifier.md) パラメーターとして渡すことはできません。</span><span class="sxs-lookup"><span data-stu-id="b2bea-117">An indexer value is not classified as a variable; therefore, you cannot pass an indexer value as a [ref](../../language-reference/keywords/ref.md) or [out](../../language-reference/keywords/out-parameter-modifier.md) parameter.</span></span>  
  
 <span data-ttu-id="b2bea-118">他の言語が使用できる名前をインデクサーに指定するには、次の例のように <xref:System.Runtime.CompilerServices.IndexerNameAttribute?displayProperty=nameWithType> を使用します。</span><span class="sxs-lookup"><span data-stu-id="b2bea-118">To provide the indexer with a name that other languages can use, use <xref:System.Runtime.CompilerServices.IndexerNameAttribute?displayProperty=nameWithType>, as the following example shows:</span></span>  

```csharp
[System.Runtime.CompilerServices.IndexerName("TheItem")]  
public int this[int index]   // Indexer declaration  
{
    // get and set accessors  
}  
```

<span data-ttu-id="b2bea-119">このインデクサーの名前は `TheItem` になります。</span><span class="sxs-lookup"><span data-stu-id="b2bea-119">This indexer will have the name `TheItem`.</span></span> <span data-ttu-id="b2bea-120">name 属性を指定しないと、`Item` が既定の名前になります。</span><span class="sxs-lookup"><span data-stu-id="b2bea-120">Not providing the name attribute would make `Item` the default name.</span></span>  
  
## <a name="example-1"></a><span data-ttu-id="b2bea-121">例 1</span><span class="sxs-lookup"><span data-stu-id="b2bea-121">Example 1</span></span>  
  
<span data-ttu-id="b2bea-122">次の例は、プライベートな配列フィールド `temps` とインデクサーの宣言方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="b2bea-122">The following example shows how to declare a private array field, `temps`, and an indexer.</span></span> <span data-ttu-id="b2bea-123">インデクサーを使用すれば、インスタンス `tempRecord[i]` に直接アクセスできます。</span><span class="sxs-lookup"><span data-stu-id="b2bea-123">The indexer enables direct access to the instance `tempRecord[i]`.</span></span> <span data-ttu-id="b2bea-124">インデクサーを使用しない場合は、配列を [public](../../language-reference/keywords/public.md) メンバーとして宣言し、そのメンバー `tempRecord.temps[i]` に直接アクセスします。</span><span class="sxs-lookup"><span data-stu-id="b2bea-124">The alternative to using the indexer is to declare the array as a [public](../../language-reference/keywords/public.md) member and access its members, `tempRecord.temps[i]`, directly.</span></span>  
  
 <span data-ttu-id="b2bea-125">`Console.Write` ステートメントなどでインデクサーのアクセスが評価されると、[get](../../language-reference/keywords/get.md) アクセサーが呼び出されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="b2bea-125">Notice that when an indexer's access is evaluated, for example, in a `Console.Write` statement, the [get](../../language-reference/keywords/get.md) accessor is invoked.</span></span> <span data-ttu-id="b2bea-126">したがって、`get` アクセサーが存在しない場合は、コンパイル時エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="b2bea-126">Therefore, if no `get` accessor exists, a compile-time error occurs.</span></span>  
  
 [!code-csharp[csProgGuideIndexers#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideIndexers/CS/Indexers.cs#1)]  
  
## <a name="indexing-using-other-values"></a><span data-ttu-id="b2bea-127">他の値を使用したインデックス作成</span><span class="sxs-lookup"><span data-stu-id="b2bea-127">Indexing using other values</span></span>

<span data-ttu-id="b2bea-128">C# では、インデクサー パラメーター型は整数に制限されません。</span><span class="sxs-lookup"><span data-stu-id="b2bea-128">C# doesn't limit the indexer parameter type to integer.</span></span> <span data-ttu-id="b2bea-129">たとえば、文字列をインデクサーで使用すると有効な場合があります。</span><span class="sxs-lookup"><span data-stu-id="b2bea-129">For example, it may be useful to use a string with an indexer.</span></span> <span data-ttu-id="b2bea-130">このようなインデクサーは、コレクション内の文字列を検索し、適切な値を返すことによって実装される場合があります。</span><span class="sxs-lookup"><span data-stu-id="b2bea-130">Such an indexer might be implemented by searching for the string in the collection, and returning the appropriate value.</span></span> <span data-ttu-id="b2bea-131">アクセサーはオーバーロードできるため、文字列と整数のバージョンは共存できます。</span><span class="sxs-lookup"><span data-stu-id="b2bea-131">As accessors can be overloaded, the string and integer versions can co-exist.</span></span>  
  
## <a name="example-2"></a><span data-ttu-id="b2bea-132">例 2</span><span class="sxs-lookup"><span data-stu-id="b2bea-132">Example 2</span></span>  
  
<span data-ttu-id="b2bea-133">次の例では、曜日を格納するクラスを宣言しています。</span><span class="sxs-lookup"><span data-stu-id="b2bea-133">The following example declares a class that stores the days of the week.</span></span> <span data-ttu-id="b2bea-134">`get` アクセサーは、曜日を示す文字列を受け取り、対応する整数を返します。</span><span class="sxs-lookup"><span data-stu-id="b2bea-134">A `get` accessor takes a string, the name of a day, and returns the corresponding integer.</span></span> <span data-ttu-id="b2bea-135">たとえば、"Sunday" は 0、"Monday" は 1 などと値を返します。</span><span class="sxs-lookup"><span data-stu-id="b2bea-135">For example, "Sunday" returns 0, "Monday" returns 1, and so on.</span></span>  
  
 [!code-csharp[csProgGuideIndexers#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideIndexers/CS/Indexers.cs#2)]  
  
## <a name="robust-programming"></a><span data-ttu-id="b2bea-136">信頼性の高いプログラミング</span><span class="sxs-lookup"><span data-stu-id="b2bea-136">Robust programming</span></span>

 <span data-ttu-id="b2bea-137">インデクサーのセキュリティと信頼性を改善するには、主に次の 2 つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="b2bea-137">There are two main ways in which the security and reliability of indexers can be improved:</span></span>  
  
- <span data-ttu-id="b2bea-138">クライアント コードが無効なインデックス値を渡しても、それを処理できるように必ずエラー処理戦略を組み込んでください。</span><span class="sxs-lookup"><span data-stu-id="b2bea-138">Be sure to incorporate some type of error-handling strategy to handle the chance of client code passing in an invalid index value.</span></span> <span data-ttu-id="b2bea-139">このトピックの最初の例の TempRecord クラスには Length プロパティが用意されており、入力がインデクサーに渡される前にクライアント コードで検証できるようになっています。</span><span class="sxs-lookup"><span data-stu-id="b2bea-139">In the first example earlier in this topic, the TempRecord class provides a Length property that enables the client code to verify the input before passing it to the indexer.</span></span> <span data-ttu-id="b2bea-140">インデクサー自体にエラー処理コードを配置することもできます。</span><span class="sxs-lookup"><span data-stu-id="b2bea-140">You can also put the error handling code inside the indexer itself.</span></span> <span data-ttu-id="b2bea-141">インデクサーのアクセサー内部でスローされる例外はすべて、ユーザーのために文書化してください。</span><span class="sxs-lookup"><span data-stu-id="b2bea-141">Be sure to document for users any exceptions that you throw inside an indexer accessor.</span></span>  
  
- <span data-ttu-id="b2bea-142">[get](../../language-reference/keywords/get.md) および [set](../../language-reference/keywords/set.md) アクセサーのアクセシビリティを設定し、適切な制限を指定します。</span><span class="sxs-lookup"><span data-stu-id="b2bea-142">Set the accessibility of the [get](../../language-reference/keywords/get.md) and [set](../../language-reference/keywords/set.md) accessors to be as restrictive as is reasonable.</span></span> <span data-ttu-id="b2bea-143">これは、`set` アクセサーの場合、特に重要です。</span><span class="sxs-lookup"><span data-stu-id="b2bea-143">This is important for the `set` accessor in particular.</span></span> <span data-ttu-id="b2bea-144">詳細については、「[アクセサーのアクセシビリティの制限](../classes-and-structs/restricting-accessor-accessibility.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b2bea-144">For more information, see [Restricting Accessor Accessibility](../classes-and-structs/restricting-accessor-accessibility.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2bea-145">関連項目</span><span class="sxs-lookup"><span data-stu-id="b2bea-145">See also</span></span>

- [<span data-ttu-id="b2bea-146">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="b2bea-146">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="b2bea-147">インデクサー</span><span class="sxs-lookup"><span data-stu-id="b2bea-147">Indexers</span></span>](./index.md)
- [<span data-ttu-id="b2bea-148">プロパティ</span><span class="sxs-lookup"><span data-stu-id="b2bea-148">Properties</span></span>](../classes-and-structs/properties.md)
