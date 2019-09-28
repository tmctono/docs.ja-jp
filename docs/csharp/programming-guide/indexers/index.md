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
ms.openlocfilehash: f0df3170289d780852ee14232e92c3b71412c548
ms.sourcegitcommit: da2dd2772fcf32b44eb18b1cbe8affd17b1753c9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/27/2019
ms.locfileid: "71392382"
---
# <a name="indexers-c-programming-guide"></a><span data-ttu-id="fa372-102">インデクサー (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="fa372-102">Indexers (C# Programming Guide)</span></span>

<span data-ttu-id="fa372-103">インデクサーを使用すると、配列と同じようにクラスまたは構造体のインスタンスにインデックスを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="fa372-103">Indexers allow instances of a class or struct to be indexed just like arrays.</span></span> <span data-ttu-id="fa372-104">インデックス値は、型またはインスタンス メンバーの明示的な指定なしで設定または取得できます。</span><span class="sxs-lookup"><span data-stu-id="fa372-104">The indexed value can be set or retrieved without explicitly specifying a type or instance member.</span></span> <span data-ttu-id="fa372-105">インデクサーは[プロパティ](../classes-and-structs/properties.md)と似ていますが、そのアクセサーがパラメーターを取る点が異なります。</span><span class="sxs-lookup"><span data-stu-id="fa372-105">Indexers resemble [properties](../classes-and-structs/properties.md) except that their accessors take parameters.</span></span>  

 <span data-ttu-id="fa372-106">次の例は、値の割り当てと取得を行う単純な [get](../../language-reference/keywords/get.md) アクセサー メソッドと [set](../../language-reference/keywords/set.md) アクセサー メソッドを持つジェネリック クラスを定義します。</span><span class="sxs-lookup"><span data-stu-id="fa372-106">The following example defines a generic class with simple [get](../../language-reference/keywords/get.md) and [set](../../language-reference/keywords/set.md) accessor methods to assign and retrieve values.</span></span> <span data-ttu-id="fa372-107">`Program` クラスは、文字列の格納用にこのクラスのインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="fa372-107">The `Program` class creates an instance of this class for storing strings.</span></span>  
  
 [!code-csharp[indexers#1](../../../../samples/snippets/csharp/programming-guide/indexers/indexer-1.cs)]  
  
> [!NOTE]
> <span data-ttu-id="fa372-108">その他の例については、「[関連セクション](./index.md#BKMK_RelatedSections)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fa372-108">For more examples, see [Related Sections](./index.md#BKMK_RelatedSections).</span></span>  
  
## <a name="expression-body-definitions"></a><span data-ttu-id="fa372-109">式の本文の定義</span><span class="sxs-lookup"><span data-stu-id="fa372-109">Expression Body Definitions</span></span>  
 
<span data-ttu-id="fa372-110">通常は、インデクサーの get または set アクセサーは、値を返すか値を設定する単一のステートメントで構成します。</span><span class="sxs-lookup"><span data-stu-id="fa372-110">It is common for an indexer's get or set accessor to consist of a single statement that either returns or sets a value.</span></span> <span data-ttu-id="fa372-111">式の本文のメンバーは、このシナリオをサポートする簡略化された構文を提供します。</span><span class="sxs-lookup"><span data-stu-id="fa372-111">Expression-bodied members provide a simplified syntax to support this scenario.</span></span> <span data-ttu-id="fa372-112">C# 6 以降、読み取り専用インデクサーは、次の例のように、式の本文のメンバーとして実装することができます。</span><span class="sxs-lookup"><span data-stu-id="fa372-112">Starting with C# 6, a read-only indexer can be implemented as an expression-bodied member, as the following example shows.</span></span>

[!code-csharp[indexers#2](../../../../samples/snippets/csharp/programming-guide/indexers/indexer-2.cs)]  

<span data-ttu-id="fa372-113">式の本文は `=>` で導入され、`get` キーワードは使用されないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="fa372-113">Note that `=>` introduces the expression body, and that the `get` keyword is not used.</span></span> 

<span data-ttu-id="fa372-114">C# 7.0 以降、get アクセサーと set アクセサーのどちらも、式の本文のメンバーとして実装できます。</span><span class="sxs-lookup"><span data-stu-id="fa372-114">Starting with C# 7.0, both the get and set accessor can be an implemented as expression-bodied members.</span></span> <span data-ttu-id="fa372-115">この場合、`get` キーワードと `set` キーワードの両方を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fa372-115">In this case, both `get` and `set` keywords must be used.</span></span> <span data-ttu-id="fa372-116">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="fa372-116">For example:</span></span>

[!code-csharp[indexers#3](../../../../samples/snippets/csharp/programming-guide/indexers/indexer-3.cs)]  
  
## <a name="indexers-overview"></a><span data-ttu-id="fa372-117">インデクサーの概要</span><span class="sxs-lookup"><span data-stu-id="fa372-117">Indexers Overview</span></span>  
  
- <span data-ttu-id="fa372-118">インデクサーを使用すると、配列と同じようにオブジェクトにインデックスを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="fa372-118">Indexers enable objects to be indexed in a similar manner to arrays.</span></span>  
  
- <span data-ttu-id="fa372-119">`get` アクセサーは値を返します。</span><span class="sxs-lookup"><span data-stu-id="fa372-119">A `get` accessor returns a value.</span></span> <span data-ttu-id="fa372-120">`set` アクセサーは値を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="fa372-120">A `set` accessor assigns a value.</span></span>  
  
- <span data-ttu-id="fa372-121">[this](../../language-reference/keywords/this.md) キーワードは、インデクサーの定義に使用されます。</span><span class="sxs-lookup"><span data-stu-id="fa372-121">The [this](../../language-reference/keywords/this.md) keyword is used to define the indexer.</span></span>  
  
- <span data-ttu-id="fa372-122">[value](../../language-reference/keywords/value.md) キーワードは、`set` インデクサーによって割り当てられる値の定義に使用されます。</span><span class="sxs-lookup"><span data-stu-id="fa372-122">The [value](../../language-reference/keywords/value.md) keyword is used to define the value being assigned by the `set` indexer.</span></span>  
  
- <span data-ttu-id="fa372-123">インデクサーは、整数値でインデックスを指定する必要はありません。個々の検索メカニズムの定義方法によります。</span><span class="sxs-lookup"><span data-stu-id="fa372-123">Indexers do not have to be indexed by an integer value; it is up to you how to define the specific look-up mechanism.</span></span>  
  
- <span data-ttu-id="fa372-124">インデクサーはオーバーロードすることができます。</span><span class="sxs-lookup"><span data-stu-id="fa372-124">Indexers can be overloaded.</span></span>  
  
- <span data-ttu-id="fa372-125">インデクサーには、2 次元配列にアクセスする場合など、複数の仮パラメーターを指定できます。</span><span class="sxs-lookup"><span data-stu-id="fa372-125">Indexers can have more than one formal parameter, for example, when accessing a two-dimensional array.</span></span>  
  
## <a name="BKMK_RelatedSections"></a> <span data-ttu-id="fa372-126">関連セクション</span><span class="sxs-lookup"><span data-stu-id="fa372-126">Related Sections</span></span>  
  
- [<span data-ttu-id="fa372-127">インデクサーの使用</span><span class="sxs-lookup"><span data-stu-id="fa372-127">Using Indexers</span></span>](./using-indexers.md)  
  
- [<span data-ttu-id="fa372-128">インターフェイスのインデクサー</span><span class="sxs-lookup"><span data-stu-id="fa372-128">Indexers in Interfaces</span></span>](./indexers-in-interfaces.md)  
  
- [<span data-ttu-id="fa372-129">プロパティとインデクサーの比較</span><span class="sxs-lookup"><span data-stu-id="fa372-129">Comparison Between Properties and Indexers</span></span>](./comparison-between-properties-and-indexers.md)  
  
- [<span data-ttu-id="fa372-130">アクセサーのアクセシビリティの制限</span><span class="sxs-lookup"><span data-stu-id="fa372-130">Restricting Accessor Accessibility</span></span>](../classes-and-structs/restricting-accessor-accessibility.md)  
  
## <a name="c-language-specification"></a><span data-ttu-id="fa372-131">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="fa372-131">C# Language Specification</span></span>  

<span data-ttu-id="fa372-132">詳細については、「[C# 言語の仕様](../../language-reference/language-specification/index.md)」の「[インデクサー](~/_csharplang/spec/classes.md#indexers)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fa372-132">For more information, see [Indexers](~/_csharplang/spec/classes.md#indexers) in the [C# Language Specification](../../language-reference/language-specification/index.md).</span></span> <span data-ttu-id="fa372-133">言語仕様は、C# の構文と使用法に関する信頼性のある情報源です。</span><span class="sxs-lookup"><span data-stu-id="fa372-133">The language specification is the definitive source for C# syntax and usage.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="fa372-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="fa372-134">See also</span></span>

- [<span data-ttu-id="fa372-135">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="fa372-135">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="fa372-136">プロパティ</span><span class="sxs-lookup"><span data-stu-id="fa372-136">Properties</span></span>](../classes-and-structs/properties.md)
