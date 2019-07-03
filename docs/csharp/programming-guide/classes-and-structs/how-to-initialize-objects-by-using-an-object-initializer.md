---
title: '方法: オブジェクト初期化子を使用してオブジェクトを初期化する - C# プログラミング ガイド'
ms.custom: seodec18
ms.date: 12/20/2018
helpviewer_keywords:
- object initializers [C#], how to use
- objects [C#], initializing
ms.assetid: 4b75ebb2-2e29-43de-929c-d736a8f27ce6
ms.openlocfilehash: 7b31e28c23a70e9f0794c82feb2a984c40ee9d0f
ms.sourcegitcommit: 4c41ec195caf03d98b7900007c3c8e24eba20d34
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/20/2019
ms.locfileid: "67267585"
---
# <a name="how-to-initialize-objects-by-using-an-object-initializer-c-programming-guide"></a><span data-ttu-id="4cd24-102">方法: オブジェクト初期化子を使用してオブジェクトを初期化する (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="4cd24-102">How to: Initialize Objects by Using an Object Initializer (C# Programming Guide)</span></span>

<span data-ttu-id="4cd24-103">オブジェクト初期化子を使用すると、型のコンストラクターを明示的に呼び出さずに、宣言的な方法で型オブジェクトを初期化できます。</span><span class="sxs-lookup"><span data-stu-id="4cd24-103">You can use object initializers to initialize type objects in a declarative manner without explicitly invoking a constructor for the type.</span></span>  
  
<span data-ttu-id="4cd24-104">次の例は、指定したオブジェクトでオブジェクト初期化子を使用する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="4cd24-104">The following examples show how to use object initializers with named objects.</span></span> <span data-ttu-id="4cd24-105">コンパイラは、最初に既定のインスタンス コンストラクターにアクセスし、メンバーの初期化を処理することで、オブジェクト初期化子を処理します。</span><span class="sxs-lookup"><span data-stu-id="4cd24-105">The compiler processes object initializers by first accessing the default instance constructor and then processing the member initializations.</span></span> <span data-ttu-id="4cd24-106">そのため、クラスでパラメーターなしのコンストラクターが `private` として宣言されている場合、パブリック アクセスを必要とするオブジェクト初期化子は失敗します。</span><span class="sxs-lookup"><span data-stu-id="4cd24-106">Therefore, if the parameterless constructor is declared as `private` in the class, object initializers that require public access will fail.</span></span>
  
<span data-ttu-id="4cd24-107">匿名型を定義する場合は、オブジェクト初期化子を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4cd24-107">You must use an object initializer if you're defining an anonymous type.</span></span> <span data-ttu-id="4cd24-108">詳細については、「[方法 :クエリで要素のプロパティのサブセットを返す](how-to-return-subsets-of-element-properties-in-a-query.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="4cd24-108">For more information, see [How to: Return Subsets of Element Properties in a Query](how-to-return-subsets-of-element-properties-in-a-query.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="4cd24-109">例</span><span class="sxs-lookup"><span data-stu-id="4cd24-109">Example</span></span>  

<span data-ttu-id="4cd24-110">次の例は、オブジェクト初期化子を使用して、新しい `StudentName` 型を初期化する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="4cd24-110">The following example shows how to initialize a new `StudentName` type by using object initializers.</span></span> <span data-ttu-id="4cd24-111">この例では `StudentName` 型でプロパティが設定されます。</span><span class="sxs-lookup"><span data-stu-id="4cd24-111">This example sets properties in the `StudentName` type:</span></span>
  
[!code-csharp[InitializerObjectExample](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/object-collection-initializers/HowToObjectInitializers.cs#HowToObjectInitializers)]  

<span data-ttu-id="4cd24-112">オブジェクト初期化子を使用し、オブジェクトにインデクサーを設定できます。</span><span class="sxs-lookup"><span data-stu-id="4cd24-112">Object initializers can be used to set indexers in an object.</span></span> <span data-ttu-id="4cd24-113">次の例では、インデクサーを使用する `BaseballTeam` クラスを定義し、選手を取得し、さまざまなポジションに据えます。</span><span class="sxs-lookup"><span data-stu-id="4cd24-113">The following example defines a `BaseballTeam` class that uses an indexer to get and set players at different positions.</span></span> <span data-ttu-id="4cd24-114">初期化子によって、ポジションの省略形 (野球のスコアカードに使用される各ポジションの番号) に基づき、選手を割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="4cd24-114">The initializer can assign players, based on the abbreviation for the position, or the number used for each position baseball scorecards:</span></span>

[!code-csharp[InitializerIndexerExample](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/object-collection-initializers/HowToIndexInitializer.cs#HowToIndexInitializer)]  

## <a name="see-also"></a><span data-ttu-id="4cd24-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="4cd24-115">See also</span></span>

- [<span data-ttu-id="4cd24-116">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="4cd24-116">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="4cd24-117">オブジェクト初期化子とコレクション初期化子</span><span class="sxs-lookup"><span data-stu-id="4cd24-117">Object and Collection Initializers</span></span>](object-and-collection-initializers.md)
