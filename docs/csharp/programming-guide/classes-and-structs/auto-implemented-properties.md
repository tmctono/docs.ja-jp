---
title: 自動実装するプロパティ - C# プログラミング ガイド
ms.date: 01/31/2020
helpviewer_keywords:
- auto-implemented properties [C#]
- properties [C#], auto-implemented
ms.assetid: aa55fa97-ccec-431f-b5e9-5ac789fd32b7
ms.openlocfilehash: 791455c1eaef752da2b551e20187d390ca6c65e6
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2020
ms.locfileid: "79170326"
---
# <a name="auto-implemented-properties-c-programming-guide"></a><span data-ttu-id="07455-102">自動実装するプロパティ (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="07455-102">Auto-Implemented Properties (C# Programming Guide)</span></span>

<span data-ttu-id="07455-103">C# 3.0 以降では、自動実装プロパティを使用することで、プロパティ アクセサーに追加のロジックが必要ない場合は、プロパティをより簡潔に宣言できます。</span><span class="sxs-lookup"><span data-stu-id="07455-103">In C# 3.0 and later, auto-implemented properties make property-declaration more concise when no additional logic is required in the property accessors.</span></span> <span data-ttu-id="07455-104">これにより、クライアント コードでオブジェクトを作成することも可能になります。</span><span class="sxs-lookup"><span data-stu-id="07455-104">They also enable client code to create objects.</span></span> <span data-ttu-id="07455-105">次の例に示すようにプロパティを宣言する場合、コンパイラによって、プロパティの `get` および `set` アクセサーを介してのみアクセスできる、プライベートの匿名バッキング フィールドが作成されます。</span><span class="sxs-lookup"><span data-stu-id="07455-105">When you declare a property as shown in the following example, the compiler creates a private, anonymous backing field that can only be accessed through the property's `get` and `set` accessors.</span></span>
  
## <a name="example"></a><span data-ttu-id="07455-106">例</span><span class="sxs-lookup"><span data-stu-id="07455-106">Example</span></span>

<span data-ttu-id="07455-107">次の例に、自動実装プロパティを持つ簡単なクラスを示します。</span><span class="sxs-lookup"><span data-stu-id="07455-107">The following example shows a simple class that has some auto-implemented properties:</span></span>  

[!code-csharp[csProgGuideLINQ#28](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideLINQ/CS/csRef30LangFeatures_2.cs#28)]  

<span data-ttu-id="07455-108">インターフェイスで自動実装プロパティを宣言することはできません。</span><span class="sxs-lookup"><span data-stu-id="07455-108">You can't declare auto-implemented properties in interfaces.</span></span> <span data-ttu-id="07455-109">自動実装プロパティでは、プライベートのインスタンス バッキング フィールドが宣言されます。インターフェイスでは、インスタンス フィールドを宣言できません。</span><span class="sxs-lookup"><span data-stu-id="07455-109">Auto-implemented properties declare a private instance backing field, and interfaces may not declare instance fields.</span></span> <span data-ttu-id="07455-110">本文を定義せずにインターフェイスでプロパティを宣言すると、アクセサーを利用してプロパティが宣言されますが、そのアクセサーは、そのインターフェイスを実装する型ごとに実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="07455-110">Declaring a property in an interface without defining a body declares a property with accessors that must be implemented by each type that implements that interface.</span></span>

<span data-ttu-id="07455-111">C# 6 以降では、フィールドと同様に自動実装プロパティを初期化することができます。</span><span class="sxs-lookup"><span data-stu-id="07455-111">In C# 6 and later, you can initialize auto-implemented properties similarly to fields:</span></span>  

```csharp  
public string FirstName { get; set; } = "Jane";  
```  

<span data-ttu-id="07455-112">前の例に示したクラスは、変更可能です。</span><span class="sxs-lookup"><span data-stu-id="07455-112">The class that is shown in the previous example is mutable.</span></span> <span data-ttu-id="07455-113">クライアント コードでは、作成後、オブジェクト内の値を変更できます。</span><span class="sxs-lookup"><span data-stu-id="07455-113">Client code can change the values in objects after creation.</span></span> <span data-ttu-id="07455-114">データだけでなく、重要な動作 (メソッド) も含まれる複雑なクラスでは、多くの場合、パブリック プロパティが必要です。</span><span class="sxs-lookup"><span data-stu-id="07455-114">In complex classes that contain significant behavior (methods) as well as data, it's often necessary to have public properties.</span></span> <span data-ttu-id="07455-115">ただし、値 (データ) のセットをカプセル化しているだけで、動作をほとんど、またはまったく含まない小さなクラスや構造体の場合は、set アクセサーを [private](../../language-reference/keywords/private.md) (コンシューマーからは変更できない) として宣言するか、または get アクセサー (コンストラクターを除くすべての場所で変更できない) のみを宣言することで、オブジェクトを変更不可能にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="07455-115">However, for small classes or structs that just encapsulate a set of values (data) and have little or no behaviors, you should either make the objects immutable by declaring the set accessor as [private](../../language-reference/keywords/private.md) (immutable to consumers) or by declaring only a get accessor (immutable everywhere except the constructor).</span></span>  <span data-ttu-id="07455-116">詳細については、「[自動実装するプロパティを使用して簡易クラスを実装する方法](./how-to-implement-a-lightweight-class-with-auto-implemented-properties.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="07455-116">For more information, see [How to implement a lightweight class with auto-implemented properties](./how-to-implement-a-lightweight-class-with-auto-implemented-properties.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="07455-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="07455-117">See also</span></span>

- [<span data-ttu-id="07455-118">プロパティ</span><span class="sxs-lookup"><span data-stu-id="07455-118">Properties</span></span>](./properties.md)
- [<span data-ttu-id="07455-119">修飾子</span><span class="sxs-lookup"><span data-stu-id="07455-119">Modifiers</span></span>](/dotnet/csharp/language-reference/keywords)
