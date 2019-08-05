---
title: 列挙型ではなく列挙型クラスを使用する
description: コンテナー化された .NET アプリケーションの .NET マイクロサービス アーキテクチャ | enum のいくつかの制限を解決する方法として、代わりに Enumeration クラスを使用する方法を説明します。
ms.date: 10/08/2018
ms.openlocfilehash: 10b4c2f7b9f079ed535111e65b8154791f6575cd
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/30/2019
ms.locfileid: "68674189"
---
# <a name="use-enumeration-classes-instead-of-enum-types"></a><span data-ttu-id="512ed-103">enum 型の代わりに Enumeration クラスを使用する</span><span class="sxs-lookup"><span data-stu-id="512ed-103">Use enumeration classes instead of enum types</span></span>

<span data-ttu-id="512ed-104">[列挙型](../../../../docs/csharp/language-reference/keywords/enum.md) (省略形も同じ *列挙型*) は、整数型を包む薄い言語ラッパーです。</span><span class="sxs-lookup"><span data-stu-id="512ed-104">[Enumerations](../../../../docs/csharp/language-reference/keywords/enum.md) (or *enum types* for short) are a thin language wrapper around an integral type.</span></span> <span data-ttu-id="512ed-105">閉じた値のセットから 1 つの値を格納するときに、列挙型の使用を制限することができます。</span><span class="sxs-lookup"><span data-stu-id="512ed-105">You might want to limit their use to when you are storing one value from a closed set of values.</span></span> <span data-ttu-id="512ed-106">サイズ (小、中、大) に基づく分類は良い一例です。</span><span class="sxs-lookup"><span data-stu-id="512ed-106">Classification based on sizes (small, medium, large) is a good example.</span></span> <span data-ttu-id="512ed-107">制御フローまたはより堅牢な抽象化のために列挙型を使用すると、[コードの臭い](https://deviq.com/code-smells/)になることがあります。</span><span class="sxs-lookup"><span data-stu-id="512ed-107">Using enums for control flow or more robust abstractions can be a [code smell](https://deviq.com/code-smells/).</span></span> <span data-ttu-id="512ed-108">このような用法は、列挙型の値を検査する多くの制御フロー ステートメントでは脆弱なコードにつながります。</span><span class="sxs-lookup"><span data-stu-id="512ed-108">This type of usage leads to fragile code with many control flow statements checking values of the enum.</span></span>

<span data-ttu-id="512ed-109">代わりに、オブジェクト指向言語の豊富な機能をすべて使用できる列挙型クラスを作成する方法があります。</span><span class="sxs-lookup"><span data-stu-id="512ed-109">Instead, you can create Enumeration classes that enable all the rich features of an object-oriented language.</span></span>

<span data-ttu-id="512ed-110">ただし、これは重要な話題ではなく、多くの場合は、好みに応じてわかりやすくするために通常の[列挙型](../../../csharp/language-reference/keywords/enum.md)を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="512ed-110">However, this isn't a critical topic and in many cases, for simplicity, you can still use regular [enum types](../../../csharp/language-reference/keywords/enum.md) if that's your preference.</span></span> <span data-ttu-id="512ed-111">いずれにしても、Enumeration クラスを使用するとビジネス関連の概念に対する関連性が強くなります。</span><span class="sxs-lookup"><span data-stu-id="512ed-111">Anyway, the use of enumeration classes is more related to business-related concepts.</span></span>

## <a name="implement-an-enumeration-base-class"></a><span data-ttu-id="512ed-112">Enumeration 基底クラスを実装する</span><span class="sxs-lookup"><span data-stu-id="512ed-112">Implement an Enumeration base class</span></span>

<span data-ttu-id="512ed-113">eShopOnContainers 内の注文マイクロサービスは、次の例のように、列挙型基底クラスの実装サンプルを提供しています。</span><span class="sxs-lookup"><span data-stu-id="512ed-113">The ordering microservice in eShopOnContainers provides a sample Enumeration base class implementation, as shown in the following example:</span></span>

```csharp
public abstract class Enumeration : IComparable
{
    public string Name { get; private set; }

    public int Id { get; private set; }

    protected Enumeration(int id, string name) 
    {
        Id = id; 
        Name = name; 
    }

    public override string ToString() => Name;

    public static IEnumerable<T> GetAll<T>() where T : Enumeration
    {
        var fields = typeof(T).GetFields(BindingFlags.Public | 
                                         BindingFlags.Static | 
                                         BindingFlags.DeclaredOnly); 

        return fields.Select(f => f.GetValue(null)).Cast<T>();
    }

    public override bool Equals(object obj) 
    {
        var otherValue = obj as Enumeration; 

        if (otherValue == null) 
            return false;

        var typeMatches = GetType().Equals(obj.GetType());
        var valueMatches = Id.Equals(otherValue.Id);

        return typeMatches && valueMatches;
    }

    public int CompareTo(object other) => Id.CompareTo(((Enumeration)other).Id); 

    // Other utility methods ... 
}
```

<span data-ttu-id="512ed-114">次の `CardType` : `Enumeration` クラスに関しては、このクラスを任意のエンティティまたは値オブジェクトの型として使用できます。</span><span class="sxs-lookup"><span data-stu-id="512ed-114">You can use this class as a type in any entity or value object, as for the following `CardType` : `Enumeration` class:</span></span>

```csharp
public class CardType : Enumeration
{
    public static CardType Amex = new CardType(1, "Amex");
    public static CardType Visa = new CardType(2, "Visa");
    public static CardType MasterCard = new CardType(3, "MasterCard");

    public CardType(int id, string name)
        : base(id, name)
    {
    }
}
```

## <a name="additional-resources"></a><span data-ttu-id="512ed-115">その他の技術情報</span><span class="sxs-lookup"><span data-stu-id="512ed-115">Additional resources</span></span>

- <span data-ttu-id="512ed-116">**列挙型は悪 — 更新** </span><span class="sxs-lookup"><span data-stu-id="512ed-116">**Enum’s are evil—update** </span></span>\
  <https://www.planetgeek.ch/2009/07/01/enums-are-evil/>

- <span data-ttu-id="512ed-117">**Daniel Hardman。列挙型で広がる病気 — そしてその治療方法** </span><span class="sxs-lookup"><span data-stu-id="512ed-117">**Daniel Hardman. How Enums Spread Disease — And How To Cure It** </span></span>\
  <https://codecraft.co/2012/10/29/how-enums-spread-disease-and-how-to-cure-it/>

- <span data-ttu-id="512ed-118">**Jimmy Bogard。列挙型クラス** </span><span class="sxs-lookup"><span data-stu-id="512ed-118">**Jimmy Bogard. Enumeration classes** </span></span>\
  <https://lostechies.com/jimmybogard/2008/08/12/enumeration-classes/>

- <span data-ttu-id="512ed-119">**Steve Smith。C# の列挙型の代替** </span><span class="sxs-lookup"><span data-stu-id="512ed-119">**Steve Smith. Enum Alternatives in C#** </span></span>\
  <https://ardalis.com/enum-alternatives-in-c>

- <span data-ttu-id="512ed-120">**Enumeration.cs。**</span><span class="sxs-lookup"><span data-stu-id="512ed-120">**Enumeration.cs.**</span></span> <span data-ttu-id="512ed-121">eShopOnContainers の基底列挙型クラス </span><span class="sxs-lookup"><span data-stu-id="512ed-121">Base Enumeration class in eShopOnContainers </span></span>\
  <https://github.com/dotnet-architecture/eShopOnContainers/blob/dev/src/Services/Ordering/Ordering.Domain/SeedWork/Enumeration.cs>

- <span data-ttu-id="512ed-122">**CardType.cs**。</span><span class="sxs-lookup"><span data-stu-id="512ed-122">**CardType.cs**.</span></span> <span data-ttu-id="512ed-123">eShopOnContainers のサンプル列挙型クラス。</span><span class="sxs-lookup"><span data-stu-id="512ed-123">Sample Enumeration class in eShopOnContainers.</span></span> \
  <https://github.com/dotnet-architecture/eShopOnContainers/blob/dev/src/Services/Ordering/Ordering.Domain/AggregatesModel/BuyerAggregate/CardType.cs>
    
- <span data-ttu-id="512ed-124">**SmartEnum**.</span><span class="sxs-lookup"><span data-stu-id="512ed-124">**SmartEnum**.</span></span> <span data-ttu-id="512ed-125">Ardalis - .NET で厳密に型指定されたスマートな列挙型を生成するためのクラス。</span><span class="sxs-lookup"><span data-stu-id="512ed-125">Ardalis - Classes to help produce strongly typed smarter enums in .NET.</span></span> \
  <https://www.nuget.org/packages/Ardalis.SmartEnum/>

>[!div class="step-by-step"]
><span data-ttu-id="512ed-126">[前へ](implement-value-objects.md)
>[次へ](domain-model-layer-validations.md)</span><span class="sxs-lookup"><span data-stu-id="512ed-126">[Previous](implement-value-objects.md)
[Next](domain-model-layer-validations.md)</span></span>
