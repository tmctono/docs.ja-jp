---
title: コレクション初期化子を使用してディクショナリを初期化する方法 - C# プログラミング ガイド
ms.custom: seodec18
ms.date: 12/20/2018
helpviewer_keywords:
- collection initializers [C#], with Dictionary
ms.assetid: 25283922-f8ee-40dc-a639-fac30804ec71
ms.openlocfilehash: bab2c4c996f7780cec572d58eb572a90aeea592a
ms.sourcegitcommit: 4c41ec195caf03d98b7900007c3c8e24eba20d34
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/20/2019
ms.locfileid: "67267670"
---
# <a name="how-to-initialize-a-dictionary-with-a-collection-initializer-c-programming-guide"></a><span data-ttu-id="7f4b8-102">コレクション初期化子を使用してディクショナリを初期化する方法 (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="7f4b8-102">How to initialize a dictionary with a collection initializer (C# Programming Guide)</span></span>

<span data-ttu-id="7f4b8-103"><xref:System.Collections.Generic.Dictionary%602> にはキーと値のペアのコレクションが含まれています。</span><span class="sxs-lookup"><span data-stu-id="7f4b8-103">A <xref:System.Collections.Generic.Dictionary%602> contains a collection of key/value pairs.</span></span> <span data-ttu-id="7f4b8-104">その <xref:System.Collections.Generic.Dictionary%602.Add*> メソッドは、それぞれキーと値に対する 2 つのパラメーターを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="7f4b8-104">Its <xref:System.Collections.Generic.Dictionary%602.Add*> method takes two parameters, one for the key and one for the value.</span></span> <span data-ttu-id="7f4b8-105">`Add` メソッドが複数のパラメーターを受け取る <xref:System.Collections.Generic.Dictionary%602> またはコレクションを初期化する 1 つの方法は、次の例に示すように、各パラメーターのセットを中かっこで囲むことです。</span><span class="sxs-lookup"><span data-stu-id="7f4b8-105">One way to initialize a <xref:System.Collections.Generic.Dictionary%602>, or any collection whose `Add` method takes multiple parameters, is to enclose each set of parameters in braces as shown in the following example.</span></span> <span data-ttu-id="7f4b8-106">もう 1 つのオプションは、インデックス初期化子を使用することです。これも次の例に示されています。</span><span class="sxs-lookup"><span data-stu-id="7f4b8-106">Another option is to use an index initializer, also shown in the following example.</span></span>

## <a name="example"></a><span data-ttu-id="7f4b8-107">例</span><span class="sxs-lookup"><span data-stu-id="7f4b8-107">Example</span></span>

<span data-ttu-id="7f4b8-108">次のコード例では、<xref:System.Collections.Generic.Dictionary%602> が型 `StudentName` のインスタンスで初期化されています。</span><span class="sxs-lookup"><span data-stu-id="7f4b8-108">In the following code example, a <xref:System.Collections.Generic.Dictionary%602> is initialized with instances of type `StudentName`.</span></span>  <span data-ttu-id="7f4b8-109">最初の初期化では、`Add` メソッドを 2 つの引数と共に使用します。</span><span class="sxs-lookup"><span data-stu-id="7f4b8-109">The first initialization uses the `Add` method with two arguments.</span></span> <span data-ttu-id="7f4b8-110">コンパイラにより、`int` キーと `StudentName` 値の各ペアに対して、`Add` への呼び出しが生成されます。</span><span class="sxs-lookup"><span data-stu-id="7f4b8-110">The compiler generates a call to `Add` for each of the pairs of `int` keys and `StudentName` values.</span></span> <span data-ttu-id="7f4b8-111">2 回目の初期化では、`Dictionary` クラスのパブリック読み取り/書き込みインデクサー メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="7f4b8-111">The second uses a public read / write indexer method of the `Dictionary` class:</span></span>

[!code-csharp[InitializerExample](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/object-collection-initializers/HowToDictionaryInitializer.cs#HowToDictionaryInitializer)]  

<span data-ttu-id="7f4b8-112">最初の宣言のコレクションの各要素の中かっこの 2 つのペアに注目してください。</span><span class="sxs-lookup"><span data-stu-id="7f4b8-112">Note the two pairs of braces in each element of the collection in the first declaration.</span></span> <span data-ttu-id="7f4b8-113">最も内側の中かっこは `StudentName` のオブジェクト初期化子を囲み、最も外側の中かっこは、`students` <xref:System.Collections.Generic.Dictionary%602> に追加されるキーと値のペアの初期化子を囲んでいます。</span><span class="sxs-lookup"><span data-stu-id="7f4b8-113">The innermost braces enclose the object initializer for the `StudentName`, and the outermost braces enclose the initializer for the key/value pair that will be added to the `students` <xref:System.Collections.Generic.Dictionary%602>.</span></span> <span data-ttu-id="7f4b8-114">最後に、ディクショナリのコレクション初期化子全体が中かっこで囲まれています。</span><span class="sxs-lookup"><span data-stu-id="7f4b8-114">Finally, the whole collection initializer for the dictionary is enclosed in braces.</span></span> <span data-ttu-id="7f4b8-115">2 回目の初期化では、代入の左辺はキーで、右辺は `StudentName` のオブジェクトの初期化子を使用する値です。</span><span class="sxs-lookup"><span data-stu-id="7f4b8-115">In the second initialization, the left side of the assignment is the key and the right side is the value, using an object initializer for `StudentName`.</span></span>

## <a name="see-also"></a><span data-ttu-id="7f4b8-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="7f4b8-116">See also</span></span>

- [<span data-ttu-id="7f4b8-117">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="7f4b8-117">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="7f4b8-118">オブジェクト初期化子とコレクション初期化子</span><span class="sxs-lookup"><span data-stu-id="7f4b8-118">Object and Collection Initializers</span></span>](../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md)
