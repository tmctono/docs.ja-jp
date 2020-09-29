---
title: デリゲートを宣言し、インスタンス化して使用する方法 - C# プログラミング ガイド
description: デリゲートを宣言し、インスタンス化して、使用する方法について説明します。 C# 1.0、2.0、および 3.0 以降に対応する例を参照してください。
ms.date: 07/20/2015
helpviewer_keywords:
- delegates [C#], declaring and instantiating
ms.assetid: 61c4895f-f785-48f8-8bfe-db73b411c4ae
ms.openlocfilehash: 83dbd2dc497fafaf1922f8ad53208d0ab14f14a9
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91185900"
---
# <a name="how-to-declare-instantiate-and-use-a-delegate-c-programming-guide"></a><span data-ttu-id="f02e8-104">デリゲートを宣言し、インスタンス化して使用する方法 (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="f02e8-104">How to declare, instantiate, and use a Delegate (C# Programming Guide)</span></span>

<span data-ttu-id="f02e8-105">C# 1.0 以降では、次の例に示すようにデリゲートを宣言できます。</span><span class="sxs-lookup"><span data-stu-id="f02e8-105">In C# 1.0 and later, delegates can be declared as shown in the following example.</span></span>  
  
 [!code-csharp[csProgGuideDelegates#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#13)]  
  
 [!code-csharp[csProgGuideDelegates#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#14)]  
  
 <span data-ttu-id="f02e8-106">C# 2.0 では、次の例に示すように、上記の宣言をより簡単に記述できます。</span><span class="sxs-lookup"><span data-stu-id="f02e8-106">C# 2.0 provides a simpler way to write the previous declaration, as shown in the following example.</span></span>  
  
 [!code-csharp[csProgGuideDelegates#32](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#32)]  
  
 <span data-ttu-id="f02e8-107">C# 2.0 以降では、次の例に示すように、匿名メソッドを使用して[デリゲート](../../language-reference/builtin-types/reference-types.md)の宣言と初期化を行うこともできます。</span><span class="sxs-lookup"><span data-stu-id="f02e8-107">In C# 2.0 and later, it is also possible to use an anonymous method to declare and initialize a [delegate](../../language-reference/builtin-types/reference-types.md), as shown in the following example.</span></span>  
  
 [!code-csharp[csProgGuideDelegates#15](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#15)]  
  
 <span data-ttu-id="f02e8-108">C# 3.0 以降では、次の例に示すように、ラムダ式を使用してデリゲートの宣言とインスタンス化を行うこともできます。</span><span class="sxs-lookup"><span data-stu-id="f02e8-108">In C# 3.0 and later, delegates can also be declared and instantiated by using a lambda expression, as shown in the following example.</span></span>  
  
 [!code-csharp[csProgGuideDelegates#31](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#31)]  
  
 <span data-ttu-id="f02e8-109">詳細については、「[ラムダ式](../../language-reference/operators/lambda-expressions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f02e8-109">For more information, see [Lambda Expressions](../../language-reference/operators/lambda-expressions.md).</span></span>  
  
 <span data-ttu-id="f02e8-110">次の例で、デリゲートの宣言、インスタンス化、および使用の方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="f02e8-110">The following example illustrates declaring, instantiating, and using a delegate.</span></span> <span data-ttu-id="f02e8-111">`BookDB` クラスにより、書籍のデータベースを保持する書店データベースをカプセル化します。</span><span class="sxs-lookup"><span data-stu-id="f02e8-111">The `BookDB` class encapsulates a bookstore database that maintains a database of books.</span></span> <span data-ttu-id="f02e8-112">これは、データベース内にあるすべてのペーパーバックを検索し、各ペーパーバックに対してデリゲートを呼び出す `ProcessPaperbackBooks` メソッドを公開します。</span><span class="sxs-lookup"><span data-stu-id="f02e8-112">It exposes a method, `ProcessPaperbackBooks`, which finds all paperback books in the database and calls a delegate for each one.</span></span> <span data-ttu-id="f02e8-113">使用する `delegate` 型には `ProcessBookDelegate` という名前を付けます。</span><span class="sxs-lookup"><span data-stu-id="f02e8-113">The `delegate` type that is used is named `ProcessBookDelegate`.</span></span> <span data-ttu-id="f02e8-114">`Test` クラスでは、このクラスを使用してペーパーバックのタイトルと平均価格を出力します。</span><span class="sxs-lookup"><span data-stu-id="f02e8-114">The `Test` class uses this class to print the titles and average price of the paperback books.</span></span>  
  
 <span data-ttu-id="f02e8-115">デリゲートを使用することで、書店データベースとクライアント コードの機能を適切に分離しやすくなります。</span><span class="sxs-lookup"><span data-stu-id="f02e8-115">The use of delegates promotes good separation of functionality between the bookstore database and the client code.</span></span> <span data-ttu-id="f02e8-116">クライアント コードからは、書籍の格納方法や書店コードでのペーパーバックの検索方法はわかりません。</span><span class="sxs-lookup"><span data-stu-id="f02e8-116">The client code has no knowledge of how the books are stored or how the bookstore code finds paperback books.</span></span> <span data-ttu-id="f02e8-117">書店コードからは、検索後にペーパーバックに対して行われる処理はわかりません。</span><span class="sxs-lookup"><span data-stu-id="f02e8-117">The bookstore code has no knowledge of what processing is performed on the paperback books after it finds them.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f02e8-118">例</span><span class="sxs-lookup"><span data-stu-id="f02e8-118">Example</span></span>  

 [!code-csharp[csProgGuideDelegates#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#12)]  
  
## <a name="robust-programming"></a><span data-ttu-id="f02e8-119">信頼性の高いプログラミング</span><span class="sxs-lookup"><span data-stu-id="f02e8-119">Robust Programming</span></span>  
  
- <span data-ttu-id="f02e8-120">デリゲートを宣言する。</span><span class="sxs-lookup"><span data-stu-id="f02e8-120">Declaring a delegate.</span></span>  
  
     <span data-ttu-id="f02e8-121">次のステートメントで、新しいデリゲート型を宣言します。</span><span class="sxs-lookup"><span data-stu-id="f02e8-121">The following statement declares a new delegate type.</span></span>  
  
     [!code-csharp[csProgGuideDelegates#16](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#16)]  
  
     <span data-ttu-id="f02e8-122">各デリゲート型は、引数の数と型、およびデリゲートでカプセル化可能なメソッドの戻り値の型を示します。</span><span class="sxs-lookup"><span data-stu-id="f02e8-122">Each delegate type describes the number and types of the arguments, and the type of the return value of methods that it can encapsulate.</span></span> <span data-ttu-id="f02e8-123">引数型または戻り値型のセットが新しく必要になった場合は、常に新しいデリゲート型を宣言する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f02e8-123">Whenever a new set of argument types or return value type is needed, a new delegate type must be declared.</span></span>  
  
- <span data-ttu-id="f02e8-124">デリゲートをインスタンス化する。</span><span class="sxs-lookup"><span data-stu-id="f02e8-124">Instantiating a delegate.</span></span>  
  
     <span data-ttu-id="f02e8-125">デリゲート型の宣言後、デリゲート オブジェクトを作成して特定のメソッドに関連付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="f02e8-125">After a delegate type has been declared, a delegate object must be created and associated with a particular method.</span></span> <span data-ttu-id="f02e8-126">先の例では、次の例に示すように `PrintTitle` メソッドを `ProcessPaperbackBooks` メソッドに渡すことでこの操作を行っています。</span><span class="sxs-lookup"><span data-stu-id="f02e8-126">In the previous example, you do this by passing the `PrintTitle` method to the `ProcessPaperbackBooks` method as in the following example:</span></span>  
  
     [!code-csharp[csProgGuideDelegates#17](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#17)]  
  
     <span data-ttu-id="f02e8-127">これにより、[静的](../../language-reference/keywords/static.md) メソッド `Test.PrintTitle` に関連付けられた新しいデリゲート オブジェクトが作成されます。</span><span class="sxs-lookup"><span data-stu-id="f02e8-127">This creates a new delegate object associated with the [static](../../language-reference/keywords/static.md) method `Test.PrintTitle`.</span></span> <span data-ttu-id="f02e8-128">同様に、次の例で示すようにオブジェクト `totaller` の非静的メソッド `AddBookToTotal` も渡しています。</span><span class="sxs-lookup"><span data-stu-id="f02e8-128">Similarly, the non-static method `AddBookToTotal` on the object `totaller` is passed as in the following example:</span></span>  
  
     [!code-csharp[csProgGuideDelegates#18](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#18)]  
  
     <span data-ttu-id="f02e8-129">どちらの場合でも、新しいデリゲート オブジェクトが `ProcessPaperbackBooks` メソッドに渡されます。</span><span class="sxs-lookup"><span data-stu-id="f02e8-129">In both cases a new delegate object is passed to the `ProcessPaperbackBooks` method.</span></span>  
  
     <span data-ttu-id="f02e8-130">デリゲート オブジェクトは不変であるため、関連付けられているメソッドを、デリゲートの作成後に変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="f02e8-130">After a delegate is created, the method it is associated with never changes; delegate objects are immutable.</span></span>  
  
- <span data-ttu-id="f02e8-131">デリゲートを呼び出す。</span><span class="sxs-lookup"><span data-stu-id="f02e8-131">Calling a delegate.</span></span>  
  
     <span data-ttu-id="f02e8-132">デリゲート オブジェクトを作成したら、通常は、そのデリゲートを呼び出す別のコードにデリゲート オブジェクトを渡します。</span><span class="sxs-lookup"><span data-stu-id="f02e8-132">After a delegate object is created, the delegate object is typically passed to other code that will call the delegate.</span></span> <span data-ttu-id="f02e8-133">デリゲート オブジェクトを呼び出すときには、デリゲートに渡す引数を、デリゲート オブジェクト名の後ろにかっこで囲んで付けます。</span><span class="sxs-lookup"><span data-stu-id="f02e8-133">A delegate object is called by using the name of the delegate object, followed by the parenthesized arguments to be passed to the delegate.</span></span> <span data-ttu-id="f02e8-134">デリゲートの呼び出しの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="f02e8-134">Following is an example of a delegate call:</span></span>  
  
     [!code-csharp[csProgGuideDelegates#19](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#19)]  
  
     <span data-ttu-id="f02e8-135">デリゲートは、この例に示すように同期的に呼び出すことも、`BeginInvoke` メソッドおよび `EndInvoke` メソッドを使用して非同期的に呼び出すこともできます。</span><span class="sxs-lookup"><span data-stu-id="f02e8-135">A delegate can be either called synchronously, as in this example, or asynchronously by using `BeginInvoke` and `EndInvoke` methods.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f02e8-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="f02e8-136">See also</span></span>

- [<span data-ttu-id="f02e8-137">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="f02e8-137">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="f02e8-138">イベント</span><span class="sxs-lookup"><span data-stu-id="f02e8-138">Events</span></span>](../events/index.md)
- [<span data-ttu-id="f02e8-139">デリゲート</span><span class="sxs-lookup"><span data-stu-id="f02e8-139">Delegates</span></span>](./index.md)
