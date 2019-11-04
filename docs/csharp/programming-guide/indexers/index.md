---
title: インデクサー - C# プログラミング ガイド
ms.custom: seodec18
ms.date: 03/10/2017
f1_keywords:
- cs.indexers
helpviewer_keywords:
- indexers [C#]
- C# language, indexers
ms.assetid: 022cd27d-d5e0-4cfe-8b97-dc018cc3355d
ms.openlocfilehash: 02dc8c21b86438c801fb151d9f02a223b60d6197
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/01/2019
ms.locfileid: "73423228"
---
# <a name="indexers-c-programming-guide"></a><span data-ttu-id="5e14b-102">インデクサー (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="5e14b-102">Indexers (C# Programming Guide)</span></span>

<span data-ttu-id="5e14b-103">インデクサーを使用すると、配列と同じようにクラスまたは構造体のインスタンスにインデックスを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="5e14b-103">Indexers allow instances of a class or struct to be indexed just like arrays.</span></span> <span data-ttu-id="5e14b-104">インデックス値は、型またはインスタンス メンバーの明示的な指定なしで設定または取得できます。</span><span class="sxs-lookup"><span data-stu-id="5e14b-104">The indexed value can be set or retrieved without explicitly specifying a type or instance member.</span></span> <span data-ttu-id="5e14b-105">インデクサーは[プロパティ](../classes-and-structs/properties.md)と似ていますが、そのアクセサーがパラメーターを取る点が異なります。</span><span class="sxs-lookup"><span data-stu-id="5e14b-105">Indexers resemble [properties](../classes-and-structs/properties.md) except that their accessors take parameters.</span></span>  

 <span data-ttu-id="5e14b-106">次の例は、値の割り当てと取得を行う単純な [get](../../language-reference/keywords/get.md) アクセサー メソッドと [set](../../language-reference/keywords/set.md) アクセサー メソッドを持つジェネリック クラスを定義します。</span><span class="sxs-lookup"><span data-stu-id="5e14b-106">The following example defines a generic class with simple [get](../../language-reference/keywords/get.md) and [set](../../language-reference/keywords/set.md) accessor methods to assign and retrieve values.</span></span> <span data-ttu-id="5e14b-107">`Program` クラスは、文字列の格納用にこのクラスのインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="5e14b-107">The `Program` class creates an instance of this class for storing strings.</span></span>  
  
 [!code-csharp[indexers#1](../../../../samples/snippets/csharp/programming-guide/indexers/indexer-1.cs)]  
  
> [!NOTE]
> <span data-ttu-id="5e14b-108">その他の例については、「[関連セクション](./index.md#BKMK_RelatedSections)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5e14b-108">For more examples, see [Related Sections](./index.md#BKMK_RelatedSections).</span></span>  
  
## <a name="expression-body-definitions"></a><span data-ttu-id="5e14b-109">式の本文の定義</span><span class="sxs-lookup"><span data-stu-id="5e14b-109">Expression Body Definitions</span></span>  
 
<span data-ttu-id="5e14b-110">通常は、インデクサーの get または set アクセサーは、値を返すか値を設定する単一のステートメントで構成します。</span><span class="sxs-lookup"><span data-stu-id="5e14b-110">It is common for an indexer's get or set accessor to consist of a single statement that either returns or sets a value.</span></span> <span data-ttu-id="5e14b-111">式の本文のメンバーは、このシナリオをサポートする簡略化された構文を提供します。</span><span class="sxs-lookup"><span data-stu-id="5e14b-111">Expression-bodied members provide a simplified syntax to support this scenario.</span></span> <span data-ttu-id="5e14b-112">C# 6 以降、読み取り専用インデクサーは、次の例のように、式の本文のメンバーとして実装することができます。</span><span class="sxs-lookup"><span data-stu-id="5e14b-112">Starting with C# 6, a read-only indexer can be implemented as an expression-bodied member, as the following example shows.</span></span>

[!code-csharp[indexers#2](../../../../samples/snippets/csharp/programming-guide/indexers/indexer-2.cs)]  

<span data-ttu-id="5e14b-113">式の本文は `=>` で導入され、`get` キーワードは使用されないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="5e14b-113">Note that `=>` introduces the expression body, and that the `get` keyword is not used.</span></span> 

<span data-ttu-id="5e14b-114">C# 7.0 以降、get アクセサーと set アクセサーのどちらも、式の本文のメンバーとして実装できます。</span><span class="sxs-lookup"><span data-stu-id="5e14b-114">Starting with C# 7.0, both the get and set accessor can be an implemented as expression-bodied members.</span></span> <span data-ttu-id="5e14b-115">この場合、`get` キーワードと `set` キーワードの両方を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5e14b-115">In this case, both `get` and `set` keywords must be used.</span></span> <span data-ttu-id="5e14b-116">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="5e14b-116">For example:</span></span>

[!code-csharp[indexers#3](../../../../samples/snippets/csharp/programming-guide/indexers/indexer-3.cs)]  
  
## <a name="indexers-overview"></a><span data-ttu-id="5e14b-117">インデクサーの概要</span><span class="sxs-lookup"><span data-stu-id="5e14b-117">Indexers Overview</span></span>  
  
- <span data-ttu-id="5e14b-118">インデクサーを使用すると、配列と同じようにオブジェクトにインデックスを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="5e14b-118">Indexers enable objects to be indexed in a similar manner to arrays.</span></span>  
  
- <span data-ttu-id="5e14b-119">`get` アクセサーは値を返します。</span><span class="sxs-lookup"><span data-stu-id="5e14b-119">A `get` accessor returns a value.</span></span> <span data-ttu-id="5e14b-120">`set` アクセサーは値を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="5e14b-120">A `set` accessor assigns a value.</span></span>  
  
- <span data-ttu-id="5e14b-121">[this](../../language-reference/keywords/this.md) キーワードは、インデクサーの定義に使用されます。</span><span class="sxs-lookup"><span data-stu-id="5e14b-121">The [this](../../language-reference/keywords/this.md) keyword is used to define the indexer.</span></span>  
  
- <span data-ttu-id="5e14b-122">[value](../../language-reference/keywords/value.md) キーワードは、`set` インデクサーによって割り当てられる値の定義に使用されます。</span><span class="sxs-lookup"><span data-stu-id="5e14b-122">The [value](../../language-reference/keywords/value.md) keyword is used to define the value being assigned by the `set` indexer.</span></span>  
  
- <span data-ttu-id="5e14b-123">インデクサーは、整数値でインデックスを指定する必要はありません。個々の検索メカニズムの定義方法によります。</span><span class="sxs-lookup"><span data-stu-id="5e14b-123">Indexers do not have to be indexed by an integer value; it is up to you how to define the specific look-up mechanism.</span></span>  
  
- <span data-ttu-id="5e14b-124">インデクサーはオーバーロードすることができます。</span><span class="sxs-lookup"><span data-stu-id="5e14b-124">Indexers can be overloaded.</span></span>  
  
- <span data-ttu-id="5e14b-125">インデクサーには、2 次元配列にアクセスする場合など、複数の仮パラメーターを指定できます。</span><span class="sxs-lookup"><span data-stu-id="5e14b-125">Indexers can have more than one formal parameter, for example, when accessing a two-dimensional array.</span></span>  
  
## <a name="BKMK_RelatedSections"></a> <span data-ttu-id="5e14b-126">関連セクション</span><span class="sxs-lookup"><span data-stu-id="5e14b-126">Related Sections</span></span>  
  
- [<span data-ttu-id="5e14b-127">インデクサーの使用</span><span class="sxs-lookup"><span data-stu-id="5e14b-127">Using Indexers</span></span>](./using-indexers.md)  
  
- [<span data-ttu-id="5e14b-128">インターフェイスのインデクサー</span><span class="sxs-lookup"><span data-stu-id="5e14b-128">Indexers in Interfaces</span></span>](./indexers-in-interfaces.md)  
  
- [<span data-ttu-id="5e14b-129">プロパティとインデクサーの比較</span><span class="sxs-lookup"><span data-stu-id="5e14b-129">Comparison Between Properties and Indexers</span></span>](./comparison-between-properties-and-indexers.md)  
  
- [<span data-ttu-id="5e14b-130">アクセサーのアクセシビリティの制限</span><span class="sxs-lookup"><span data-stu-id="5e14b-130">Restricting Accessor Accessibility</span></span>](../classes-and-structs/restricting-accessor-accessibility.md)  
  
## <a name="c-language-specification"></a><span data-ttu-id="5e14b-131">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="5e14b-131">C# Language Specification</span></span>  

<span data-ttu-id="5e14b-132">詳細については、「[C# 言語の仕様](/dotnet/csharp/language-reference/language-specification/introduction)」の「[インデクサー](~/_csharplang/spec/classes.md#indexers)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5e14b-132">For more information, see [Indexers](~/_csharplang/spec/classes.md#indexers) in the [C# Language Specification](/dotnet/csharp/language-reference/language-specification/introduction).</span></span> <span data-ttu-id="5e14b-133">言語仕様は、C# の構文と使用法に関する信頼性のある情報源です。</span><span class="sxs-lookup"><span data-stu-id="5e14b-133">The language specification is the definitive source for C# syntax and usage.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="5e14b-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="5e14b-134">See also</span></span>

- [<span data-ttu-id="5e14b-135">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="5e14b-135">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="5e14b-136">プロパティ</span><span class="sxs-lookup"><span data-stu-id="5e14b-136">Properties</span></span>](../classes-and-structs/properties.md)
