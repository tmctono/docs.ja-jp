---
title: 自動実装するプロパティ - C# プログラミング ガイド
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- auto-implemented properties [C#]
- properties [C#], auto-implemented
ms.assetid: aa55fa97-ccec-431f-b5e9-5ac789fd32b7
ms.openlocfilehash: 212fdde3a5ecc8b0a43e33bec3537bd57b1387e9
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/01/2019
ms.locfileid: "73419412"
---
# <a name="auto-implemented-properties-c-programming-guide"></a><span data-ttu-id="9a603-102">自動実装するプロパティ (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="9a603-102">Auto-Implemented Properties (C# Programming Guide)</span></span>
<span data-ttu-id="9a603-103">C# 3.0 以降では、自動実装プロパティを使用することで、プロパティ アクセサーに追加のロジックが必要ない場合は、プロパティをより簡潔に宣言できます。</span><span class="sxs-lookup"><span data-stu-id="9a603-103">In C# 3.0 and later, auto-implemented properties make property-declaration more concise when no additional logic is required in the property accessors.</span></span> <span data-ttu-id="9a603-104">これにより、クライアント コードでオブジェクトを作成することも可能になります。</span><span class="sxs-lookup"><span data-stu-id="9a603-104">They also enable client code to create objects.</span></span> <span data-ttu-id="9a603-105">次の例に示すようにプロパティを宣言する場合、コンパイラによって、プロパティの `get` および `set` アクセサーを介してのみアクセスできる、プライベートの匿名バッキング フィールドが作成されます。</span><span class="sxs-lookup"><span data-stu-id="9a603-105">When you declare a property as shown in the following example, the compiler creates a private, anonymous backing field that can only be accessed through the property's `get` and `set` accessors.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9a603-106">例</span><span class="sxs-lookup"><span data-stu-id="9a603-106">Example</span></span>  
 <span data-ttu-id="9a603-107">次の例に、自動実装プロパティを持つ簡単なクラスを示します。</span><span class="sxs-lookup"><span data-stu-id="9a603-107">The following example shows a simple class that has some auto-implemented properties:</span></span>  
  
 [!code-csharp[csProgGuideLINQ#28](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideLINQ/CS/csRef30LangFeatures_2.cs#28)]  
  
 <span data-ttu-id="9a603-108">C# 6 以降では、フィールドと同様に自動実装プロパティを初期化することができます。</span><span class="sxs-lookup"><span data-stu-id="9a603-108">In C# 6 and later, you can initialize auto-implemented properties similarly to fields:</span></span>  
  
```csharp  
public string FirstName { get; set; } = "Jane";  
```  
  
 <span data-ttu-id="9a603-109">前の例に示したクラスは、変更可能です。</span><span class="sxs-lookup"><span data-stu-id="9a603-109">The class that is shown in the previous example is mutable.</span></span> <span data-ttu-id="9a603-110">クライアント コードは、オブジェクト内の値を作成後に変更できます。</span><span class="sxs-lookup"><span data-stu-id="9a603-110">Client code can change the values in objects after they are created.</span></span> <span data-ttu-id="9a603-111">データだけでなく、重要な動作 (メソッド) も含まれる複雑なクラスでは、多くの場合、パブリック プロパティが必要です。</span><span class="sxs-lookup"><span data-stu-id="9a603-111">In complex classes that contain significant behavior (methods) as well as data, it is often necessary to have public properties.</span></span> <span data-ttu-id="9a603-112">ただし、値 (データ) のセットをカプセル化しているだけで、動作をほとんど、またはまったく含まない小さなクラスや構造体の場合は、set アクセサーを [private](../../language-reference/keywords/private.md) (コンシューマーからは変更できない) として宣言するか、または get アクセサー (コンストラクターを除くすべての場所で変更できない) のみを宣言することで、オブジェクトを変更不可能にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="9a603-112">However, for small classes or structs that just encapsulate a set of values (data) and have little or no behaviors, you should either make the objects immutable by declaring the set accessor as [private](../../language-reference/keywords/private.md) (immutable to consumers) or by declaring only a get accessor (immutable everywhere except the constructor).</span></span>  <span data-ttu-id="9a603-113">詳細については、[自動実装するプロパティを使用して簡易クラスを実装する](./how-to-implement-a-lightweight-class-with-auto-implemented-properties.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="9a603-113">For more information, see [How to: Implement a Lightweight Class with Auto-Implemented Properties](./how-to-implement-a-lightweight-class-with-auto-implemented-properties.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a603-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="9a603-114">See also</span></span>

- [<span data-ttu-id="9a603-115">プロパティ</span><span class="sxs-lookup"><span data-stu-id="9a603-115">Properties</span></span>](./properties.md)
- [<span data-ttu-id="9a603-116">修飾子</span><span class="sxs-lookup"><span data-stu-id="9a603-116">Modifiers</span></span>](/dotnet/csharp/language-reference/keywords)
