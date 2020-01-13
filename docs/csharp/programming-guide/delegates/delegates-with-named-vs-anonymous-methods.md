---
title: 名前付きメソッドを使用したデリゲートと匿名メソッド - C# プログラミング ガイド
ms.date: 07/20/2015
helpviewer_keywords:
- delegates [C#], with named vs. anonymous methods
- methods [C#], in delegates
ms.assetid: 98fa8c61-66b6-4146-986c-3236c4045733
ms.openlocfilehash: 1ec366999ca6457471b705fa83f06fcde4293f4e
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/07/2020
ms.locfileid: "75712378"
---
# <a name="delegates-with-named-vs-anonymous-methods-c-programming-guide"></a><span data-ttu-id="90c24-102">名前付きメソッドを使用したデリゲートと匿名メソッド (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="90c24-102">Delegates with Named vs. Anonymous Methods (C# Programming Guide)</span></span>
<span data-ttu-id="90c24-103">[デリゲート](../../language-reference/builtin-types/reference-types.md)は、名前付きメソッドに関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="90c24-103">A [delegate](../../language-reference/builtin-types/reference-types.md) can be associated with a named method.</span></span> <span data-ttu-id="90c24-104">名前付きメソッドを使用してデリゲートをインスタンス化するときは、次のように、そのメソッドをパラメーターとして渡します。</span><span class="sxs-lookup"><span data-stu-id="90c24-104">When you instantiate a delegate by using a named method, the method is passed as a parameter, for example:</span></span>  
  
 [!code-csharp[csProgGuideDelegates#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#1)]  
  
 <span data-ttu-id="90c24-105">これを名前付きメソッドの使用といいます。</span><span class="sxs-lookup"><span data-stu-id="90c24-105">This is called using a named method.</span></span> <span data-ttu-id="90c24-106">名前付きメソッドで作成されたデリゲートは、[静的](../../language-reference/keywords/static.md)メソッドまたはインスタンス メソッドのいずれかでカプセル化できます。</span><span class="sxs-lookup"><span data-stu-id="90c24-106">Delegates constructed with a named method can encapsulate either a [static](../../language-reference/keywords/static.md) method or an instance method.</span></span> <span data-ttu-id="90c24-107">旧バージョンの C# では、デリゲートをインスタンス化するには、名前付きメソッドを使用するしかありませんが、</span><span class="sxs-lookup"><span data-stu-id="90c24-107">Named methods are the only way to instantiate a delegate in earlier versions of C#.</span></span> <span data-ttu-id="90c24-108">新しいメソッドを作成するのが、オーバーヘッドの点で望ましくない場合は、C# でデリゲートをインスタンス化し、そのデリゲートが呼び出されたときに処理するコード ブロックを直接指定できます。</span><span class="sxs-lookup"><span data-stu-id="90c24-108">However, in a situation where creating a new method is unwanted overhead, C# enables you to instantiate a delegate and immediately specify a code block that the delegate will process when it is called.</span></span> <span data-ttu-id="90c24-109">ブロックには、ラムダ式または匿名メソッドのいずれかを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="90c24-109">The block can contain either a lambda expression or an anonymous method.</span></span> <span data-ttu-id="90c24-110">詳細については、[匿名関数](../statements-expressions-operators/anonymous-functions.md)に関するページをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="90c24-110">For more information, see [Anonymous Functions](../statements-expressions-operators/anonymous-functions.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="90c24-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="90c24-111">Remarks</span></span>  
 <span data-ttu-id="90c24-112">デリゲート パラメーターとして渡すメソッドには、デリゲート宣言と同じシグネチャが必要です。</span><span class="sxs-lookup"><span data-stu-id="90c24-112">The method that you pass as a delegate parameter must have the same signature as the delegate declaration.</span></span>  
  
 <span data-ttu-id="90c24-113">デリゲート インスタンスがカプセル化できるのは、静的メソッドまたはインスタンス メソッドのいずれかです。</span><span class="sxs-lookup"><span data-stu-id="90c24-113">A delegate instance may encapsulate either static or instance method.</span></span>  
  
 <span data-ttu-id="90c24-114">デリゲートは [out](../../language-reference/keywords/out-parameter-modifier.md) パラメーターを使用できますが、マルチキャスト イベント デリゲートでこのパラメーターを使用することはお勧めしません。どのデリゲートが呼び出されるかわからないためです。</span><span class="sxs-lookup"><span data-stu-id="90c24-114">Although the delegate can use an [out](../../language-reference/keywords/out-parameter-modifier.md) parameter, we do not recommend its use with multicast event delegates because you cannot know which delegate will be called.</span></span>  
  
## <a name="example-1"></a><span data-ttu-id="90c24-115">例 1</span><span class="sxs-lookup"><span data-stu-id="90c24-115">Example 1</span></span>  
 <span data-ttu-id="90c24-116">次のシンプルな例では、デリゲートを宣言して使用します。</span><span class="sxs-lookup"><span data-stu-id="90c24-116">The following is a simple example of declaring and using a delegate.</span></span> <span data-ttu-id="90c24-117">デリゲート `Del` とそれに関連付けられているメソッド `MultiplyNumbers` の両方に同じシグネチャが含まれることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="90c24-117">Notice that both the delegate, `Del`, and the associated method, `MultiplyNumbers`, have the same signature</span></span>  
  
 [!code-csharp[csProgGuideDelegates#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#2)]  
  
## <a name="example-2"></a><span data-ttu-id="90c24-118">例 2</span><span class="sxs-lookup"><span data-stu-id="90c24-118">Example 2</span></span>  
 <span data-ttu-id="90c24-119">次の例では、1 つのデリゲートを静的メソッドとインスタンス メソッドの両方に割り当て、各メソッドから特定の情報を戻します。</span><span class="sxs-lookup"><span data-stu-id="90c24-119">In the following example, one delegate is mapped to both static and instance methods and returns specific information from each.</span></span>  
  
 [!code-csharp[csProgGuideDelegates#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#3)]  
  
## <a name="see-also"></a><span data-ttu-id="90c24-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="90c24-120">See also</span></span>

- [<span data-ttu-id="90c24-121">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="90c24-121">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="90c24-122">デリゲート</span><span class="sxs-lookup"><span data-stu-id="90c24-122">Delegates</span></span>](./index.md)
- [<span data-ttu-id="90c24-123">デリゲートを結合する方法 (マルチキャスト デリゲート)</span><span class="sxs-lookup"><span data-stu-id="90c24-123">How to combine delegates (Multicast Delegates)</span></span>](./how-to-combine-delegates-multicast-delegates.md)
- [<span data-ttu-id="90c24-124">イベント</span><span class="sxs-lookup"><span data-stu-id="90c24-124">Events</span></span>](../events/index.md)
