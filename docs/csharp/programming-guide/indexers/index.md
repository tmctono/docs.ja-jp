---
title: インデクサー - C# プログラミング ガイド
description: C# のインデクサーにより、クラスまたは構造体のインスタンスを配列のようにインデックス付けできます。 インデックス付きの値は、型またはインスタンスのメンバーを指定せずに、設定または取得できます。
ms.date: 03/10/2017
f1_keywords:
- cs.indexers
helpviewer_keywords:
- indexers [C#]
- C# language, indexers
ms.assetid: 022cd27d-d5e0-4cfe-8b97-dc018cc3355d
ms.openlocfilehash: ea95eef7bb9ba232e4d59e3f833b82e98398fc33
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2020
ms.locfileid: "89495305"
---
# <a name="indexers-c-programming-guide"></a><span data-ttu-id="d7437-104">インデクサー (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="d7437-104">Indexers (C# Programming Guide)</span></span>

<span data-ttu-id="d7437-105">インデクサーを使用すると、配列と同じようにクラスまたは構造体のインスタンスにインデックスを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="d7437-105">Indexers allow instances of a class or struct to be indexed just like arrays.</span></span> <span data-ttu-id="d7437-106">インデックス値は、型またはインスタンス メンバーの明示的な指定なしで設定または取得できます。</span><span class="sxs-lookup"><span data-stu-id="d7437-106">The indexed value can be set or retrieved without explicitly specifying a type or instance member.</span></span> <span data-ttu-id="d7437-107">インデクサーは[プロパティ](../classes-and-structs/properties.md)と似ていますが、そのアクセサーがパラメーターを取る点が異なります。</span><span class="sxs-lookup"><span data-stu-id="d7437-107">Indexers resemble [properties](../classes-and-structs/properties.md) except that their accessors take parameters.</span></span>  

 <span data-ttu-id="d7437-108">次の例は、値の割り当てと取得を行う単純な [get](../../language-reference/keywords/get.md) アクセサー メソッドと [set](../../language-reference/keywords/set.md) アクセサー メソッドを持つジェネリック クラスを定義します。</span><span class="sxs-lookup"><span data-stu-id="d7437-108">The following example defines a generic class with simple [get](../../language-reference/keywords/get.md) and [set](../../language-reference/keywords/set.md) accessor methods to assign and retrieve values.</span></span> <span data-ttu-id="d7437-109">`Program` クラスは、文字列の格納用にこのクラスのインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="d7437-109">The `Program` class creates an instance of this class for storing strings.</span></span>  
  
 [!code-csharp[indexers#1](../../../../samples/snippets/csharp/programming-guide/indexers/indexer-1.cs)]  
  
> [!NOTE]
> <span data-ttu-id="d7437-110">その他の例については、「[関連セクション](./index.md#BKMK_RelatedSections)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d7437-110">For more examples, see [Related Sections](./index.md#BKMK_RelatedSections).</span></span>  
  
## <a name="expression-body-definitions"></a><span data-ttu-id="d7437-111">式の本文の定義</span><span class="sxs-lookup"><span data-stu-id="d7437-111">Expression Body Definitions</span></span>  

<span data-ttu-id="d7437-112">通常は、インデクサーの get または set アクセサーは、値を返すか値を設定する単一のステートメントで構成します。</span><span class="sxs-lookup"><span data-stu-id="d7437-112">It is common for an indexer's get or set accessor to consist of a single statement that either returns or sets a value.</span></span> <span data-ttu-id="d7437-113">式の本文のメンバーは、このシナリオをサポートする簡略化された構文を提供します。</span><span class="sxs-lookup"><span data-stu-id="d7437-113">Expression-bodied members provide a simplified syntax to support this scenario.</span></span> <span data-ttu-id="d7437-114">C# 6 以降、読み取り専用インデクサーは、次の例のように、式の本文のメンバーとして実装することができます。</span><span class="sxs-lookup"><span data-stu-id="d7437-114">Starting with C# 6, a read-only indexer can be implemented as an expression-bodied member, as the following example shows.</span></span>

[!code-csharp[indexers#2](../../../../samples/snippets/csharp/programming-guide/indexers/indexer-2.cs)]  

<span data-ttu-id="d7437-115">式の本文は `=>` で導入され、`get` キーワードは使用されないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="d7437-115">Note that `=>` introduces the expression body, and that the `get` keyword is not used.</span></span>

<span data-ttu-id="d7437-116">C# 7.0 以降、get アクセサーと set アクセサーのどちらも、式の本文のメンバーとして実装できます。</span><span class="sxs-lookup"><span data-stu-id="d7437-116">Starting with C# 7.0, both the get and set accessor can be an implemented as expression-bodied members.</span></span> <span data-ttu-id="d7437-117">この場合、`get` キーワードと `set` キーワードの両方を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d7437-117">In this case, both `get` and `set` keywords must be used.</span></span> <span data-ttu-id="d7437-118">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="d7437-118">For example:</span></span>

[!code-csharp[indexers#3](../../../../samples/snippets/csharp/programming-guide/indexers/indexer-3.cs)]  
  
## <a name="indexers-overview"></a><span data-ttu-id="d7437-119">インデクサーの概要</span><span class="sxs-lookup"><span data-stu-id="d7437-119">Indexers Overview</span></span>  
  
- <span data-ttu-id="d7437-120">インデクサーを使用すると、配列と同じようにオブジェクトにインデックスを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="d7437-120">Indexers enable objects to be indexed in a similar manner to arrays.</span></span>  
  
- <span data-ttu-id="d7437-121">`get` アクセサーは値を返します。</span><span class="sxs-lookup"><span data-stu-id="d7437-121">A `get` accessor returns a value.</span></span> <span data-ttu-id="d7437-122">`set` アクセサーは値を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="d7437-122">A `set` accessor assigns a value.</span></span>  
  
- <span data-ttu-id="d7437-123">[this](../../language-reference/keywords/this.md) キーワードは、インデクサーの定義に使用されます。</span><span class="sxs-lookup"><span data-stu-id="d7437-123">The [this](../../language-reference/keywords/this.md) keyword is used to define the indexer.</span></span>  
  
- <span data-ttu-id="d7437-124">`set` アクセサーで割り当てる値は [value](../../language-reference/keywords/value.md) キーワードを使用して定義します。</span><span class="sxs-lookup"><span data-stu-id="d7437-124">The [value](../../language-reference/keywords/value.md) keyword is used to define the value being assigned by the `set` accessor.</span></span>  
  
- <span data-ttu-id="d7437-125">インデクサーは、整数値でインデックスを指定する必要はありません。個々の検索メカニズムの定義方法によります。</span><span class="sxs-lookup"><span data-stu-id="d7437-125">Indexers do not have to be indexed by an integer value; it is up to you how to define the specific look-up mechanism.</span></span>  
  
- <span data-ttu-id="d7437-126">インデクサーはオーバーロードすることができます。</span><span class="sxs-lookup"><span data-stu-id="d7437-126">Indexers can be overloaded.</span></span>  
  
- <span data-ttu-id="d7437-127">インデクサーには、2 次元配列にアクセスする場合など、複数の仮パラメーターを指定できます。</span><span class="sxs-lookup"><span data-stu-id="d7437-127">Indexers can have more than one formal parameter, for example, when accessing a two-dimensional array.</span></span>  
  
## <a name="related-sections"></a><a name="BKMK_RelatedSections"></a> <span data-ttu-id="d7437-128">関連セクション</span><span class="sxs-lookup"><span data-stu-id="d7437-128">Related Sections</span></span>  
  
- [<span data-ttu-id="d7437-129">インデクサーの使用</span><span class="sxs-lookup"><span data-stu-id="d7437-129">Using Indexers</span></span>](./using-indexers.md)  
  
- [<span data-ttu-id="d7437-130">インターフェイスのインデクサー</span><span class="sxs-lookup"><span data-stu-id="d7437-130">Indexers in Interfaces</span></span>](./indexers-in-interfaces.md)  
  
- [<span data-ttu-id="d7437-131">プロパティとインデクサーの比較</span><span class="sxs-lookup"><span data-stu-id="d7437-131">Comparison Between Properties and Indexers</span></span>](./comparison-between-properties-and-indexers.md)  
  
- [<span data-ttu-id="d7437-132">アクセサーのアクセシビリティの制限</span><span class="sxs-lookup"><span data-stu-id="d7437-132">Restricting Accessor Accessibility</span></span>](../classes-and-structs/restricting-accessor-accessibility.md)  
  
## <a name="c-language-specification"></a><span data-ttu-id="d7437-133">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="d7437-133">C# Language Specification</span></span>  

<span data-ttu-id="d7437-134">詳細については、「[C# 言語の仕様](/dotnet/csharp/language-reference/language-specification/introduction)」の「[インデクサー](~/_csharplang/spec/classes.md#indexers)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d7437-134">For more information, see [Indexers](~/_csharplang/spec/classes.md#indexers) in the [C# Language Specification](/dotnet/csharp/language-reference/language-specification/introduction).</span></span> <span data-ttu-id="d7437-135">言語仕様は、C# の構文と使用法に関する信頼性のある情報源です。</span><span class="sxs-lookup"><span data-stu-id="d7437-135">The language specification is the definitive source for C# syntax and usage.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="d7437-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="d7437-136">See also</span></span>

- [<span data-ttu-id="d7437-137">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="d7437-137">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="d7437-138">プロパティ</span><span class="sxs-lookup"><span data-stu-id="d7437-138">Properties</span></span>](../classes-and-structs/properties.md)
