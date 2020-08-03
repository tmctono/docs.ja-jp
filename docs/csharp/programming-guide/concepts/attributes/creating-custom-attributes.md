---
title: カスタム属性の作成 (C#)
description: 属性クラスから派生する属性クラスを定義することで、C# でカスタム属性を作成する方法について説明します。
ms.date: 07/20/2015
ms.assetid: 500e1977-c6de-462d-abce-78a0eb1eda22
ms.openlocfilehash: 7d6f98620388af8715652dcbcfe78366952b853d
ms.sourcegitcommit: 40de8df14289e1e05b40d6e5c1daabd3c286d70c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/22/2020
ms.locfileid: "86925086"
---
# <a name="creating-custom-attributes-c"></a><span data-ttu-id="ff66a-103">カスタム属性の作成 (C#)</span><span class="sxs-lookup"><span data-stu-id="ff66a-103">Creating Custom Attributes (C#)</span></span>
<span data-ttu-id="ff66a-104">属性クラスを定義することで、独自のカスタム属性を作成できます。属性クラスは、<xref:System.Attribute> の直接的または間接的な派生クラスです。これにより、メタデータの中で属性の定義をすばやく簡単に特定できます。</span><span class="sxs-lookup"><span data-stu-id="ff66a-104">You can create your own custom attributes by defining an attribute class, a class that derives directly or indirectly from <xref:System.Attribute>, which makes identifying attribute definitions in metadata fast and easy.</span></span> <span data-ttu-id="ff66a-105">型にそれを記述したプログラマーの名前でタグを付けるとします。</span><span class="sxs-lookup"><span data-stu-id="ff66a-105">Suppose you want to tag types with the name of the programmer who wrote the type.</span></span> <span data-ttu-id="ff66a-106">`Author` というカスタム属性クラスを定義します。</span><span class="sxs-lookup"><span data-stu-id="ff66a-106">You might define a custom `Author` attribute class:</span></span>  
  
```csharp  
[System.AttributeUsage(System.AttributeTargets.Class |  
                       System.AttributeTargets.Struct)  
]  
public class AuthorAttribute : System.Attribute  
{  
    private string name;  
    public double version;  
  
    public AuthorAttribute(string name)  
    {  
        this.name = name;  
        version = 1.0;  
    }  
}  
```  
  
 <span data-ttu-id="ff66a-107">クラス名 `AuthorAttribute` は属性の名前 `Author` であり、サフィックス `Attribute` が付きます。</span><span class="sxs-lookup"><span data-stu-id="ff66a-107">The class name `AuthorAttribute` is the attribute's name, `Author`, plus the `Attribute` suffix.</span></span> <span data-ttu-id="ff66a-108">このクラスは `System.Attribute` から派生しているので、カスタム属性クラスです。</span><span class="sxs-lookup"><span data-stu-id="ff66a-108">It is derived from `System.Attribute`, so it is a custom attribute class.</span></span> <span data-ttu-id="ff66a-109">コンストラクターのパラメーターはカスタム属性の位置指定パラメーターです。</span><span class="sxs-lookup"><span data-stu-id="ff66a-109">The constructor's parameters are the custom attribute's positional parameters.</span></span> <span data-ttu-id="ff66a-110">この例では、`name` が位置指定パラメーターになります。</span><span class="sxs-lookup"><span data-stu-id="ff66a-110">In this example, `name` is a positional parameter.</span></span> <span data-ttu-id="ff66a-111">パブリックな読み取り/書き込みフィールドまたはプロパティは名前付きパラメーターです。</span><span class="sxs-lookup"><span data-stu-id="ff66a-111">Any public read-write fields or properties are named parameters.</span></span> <span data-ttu-id="ff66a-112">この場合は、`version` が唯一の名前付きパラメーターです。</span><span class="sxs-lookup"><span data-stu-id="ff66a-112">In this case, `version` is the only named parameter.</span></span> <span data-ttu-id="ff66a-113">`AttributeUsage` 属性を使用して、クラスと `struct` の宣言に対してのみ `Author` 属性を有効にしていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="ff66a-113">Note the use of the `AttributeUsage` attribute to make the `Author` attribute valid only on class and `struct` declarations.</span></span>  
  
 <span data-ttu-id="ff66a-114">この新しい属性の使用方法は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="ff66a-114">You could use this new attribute as follows:</span></span>  
  
```csharp  
[Author("P. Ackerman", version = 1.1)]  
class SampleClass  
{  
    // P. Ackerman's code goes here...  
}  
```  
  
 <span data-ttu-id="ff66a-115">`AttributeUsage` には名前付きパラメーター `AllowMultiple` があります。これを使用すると、カスタム属性が 1 回しか指定できない属性か、または複数回指定できる属性かを設定できます。</span><span class="sxs-lookup"><span data-stu-id="ff66a-115">`AttributeUsage` has a named parameter, `AllowMultiple`, with which you can make a custom attribute single-use or multiuse.</span></span> <span data-ttu-id="ff66a-116">次のコード例では、複数回指定できる属性が作成されます。</span><span class="sxs-lookup"><span data-stu-id="ff66a-116">In the following code example, a multiuse attribute is created.</span></span>  
  
```csharp  
[System.AttributeUsage(System.AttributeTargets.Class |  
                       System.AttributeTargets.Struct,  
                       AllowMultiple = true)  // multiuse attribute  
]  
public class AuthorAttribute : System.Attribute  
```  
  
 <span data-ttu-id="ff66a-117">次のコード例では、同じ型の複数の属性が 1 つのクラスに適用されます。</span><span class="sxs-lookup"><span data-stu-id="ff66a-117">In the following code example, multiple attributes of the same type are applied to a class.</span></span>  
  
```csharp  
[Author("P. Ackerman", version = 1.1)]  
[Author("R. Koch", version = 1.2)]  
class SampleClass  
{  
    // P. Ackerman's code goes here...  
    // R. Koch's code goes here...  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="ff66a-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="ff66a-118">See also</span></span>

- <xref:System.Reflection>
- [<span data-ttu-id="ff66a-119">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="ff66a-119">C# Programming Guide</span></span>](../../index.md)
- [<span data-ttu-id="ff66a-120">カスタム属性の記述</span><span class="sxs-lookup"><span data-stu-id="ff66a-120">Writing Custom Attributes</span></span>](../../../../standard/attributes/writing-custom-attributes.md)
- [<span data-ttu-id="ff66a-121">リフレクション (C#)</span><span class="sxs-lookup"><span data-stu-id="ff66a-121">Reflection (C#)</span></span>](../reflection.md)
- [<span data-ttu-id="ff66a-122">属性 (C#)</span><span class="sxs-lookup"><span data-stu-id="ff66a-122">Attributes (C#)</span></span>](./index.md)
- [<span data-ttu-id="ff66a-123">リフレクションを使用した属性へのアクセス (C#)</span><span class="sxs-lookup"><span data-stu-id="ff66a-123">Accessing Attributes by Using Reflection (C#)</span></span>](./accessing-attributes-by-using-reflection.md)
- [<span data-ttu-id="ff66a-124">AttributeUsage (C#)</span><span class="sxs-lookup"><span data-stu-id="ff66a-124">AttributeUsage (C#)</span></span>](../../../language-reference/attributes/general.md)
