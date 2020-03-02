---
title: 列挙型ではなく列挙型クラスを使用する
description: コンテナー化された .NET アプリケーションの .NET マイクロサービス アーキテクチャ | enum のいくつかの制限を解決する方法として、代わりに Enumeration クラスを使用する方法を説明します。
ms.date: 10/08/2018
ms.openlocfilehash: 82bd80d19b3b73eb2f45ede8cc7ad4593c688277
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/26/2020
ms.locfileid: "77628463"
---
# <a name="use-enumeration-classes-instead-of-enum-types"></a><span data-ttu-id="7c44a-103">enum 型の代わりに Enumeration クラスを使用する</span><span class="sxs-lookup"><span data-stu-id="7c44a-103">Use enumeration classes instead of enum types</span></span>

<span data-ttu-id="7c44a-104">[列挙型](../../../csharp/language-reference/builtin-types/enum.md) (省略形も同じ *列挙型*) は、整数型を包む薄い言語ラッパーです。</span><span class="sxs-lookup"><span data-stu-id="7c44a-104">[Enumerations](../../../csharp/language-reference/builtin-types/enum.md) (or *enum types* for short) are a thin language wrapper around an integral type.</span></span> <span data-ttu-id="7c44a-105">閉じた値のセットから 1 つの値を格納するときに、列挙型の使用を制限することができます。</span><span class="sxs-lookup"><span data-stu-id="7c44a-105">You might want to limit their use to when you are storing one value from a closed set of values.</span></span> <span data-ttu-id="7c44a-106">サイズ (小、中、大) に基づく分類は良い一例です。</span><span class="sxs-lookup"><span data-stu-id="7c44a-106">Classification based on sizes (small, medium, large) is a good example.</span></span> <span data-ttu-id="7c44a-107">制御フローまたはより堅牢な抽象化のために列挙型を使用すると、[コードの臭い](https://deviq.com/code-smells/)になることがあります。</span><span class="sxs-lookup"><span data-stu-id="7c44a-107">Using enums for control flow or more robust abstractions can be a [code smell](https://deviq.com/code-smells/).</span></span> <span data-ttu-id="7c44a-108">このような用法は、列挙型の値を検査する多くの制御フロー ステートメントでは脆弱なコードにつながります。</span><span class="sxs-lookup"><span data-stu-id="7c44a-108">This type of usage leads to fragile code with many control flow statements checking values of the enum.</span></span>

<span data-ttu-id="7c44a-109">代わりに、オブジェクト指向言語の豊富な機能をすべて使用できる列挙型クラスを作成する方法があります。</span><span class="sxs-lookup"><span data-stu-id="7c44a-109">Instead, you can create Enumeration classes that enable all the rich features of an object-oriented language.</span></span>

<span data-ttu-id="7c44a-110">ただし、これは重要な話題ではなく、多くの場合は、好みに応じてわかりやすくするために通常の[列挙型](../../../csharp/language-reference/builtin-types/enum.md)を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="7c44a-110">However, this isn't a critical topic and in many cases, for simplicity, you can still use regular [enum types](../../../csharp/language-reference/builtin-types/enum.md) if that's your preference.</span></span> <span data-ttu-id="7c44a-111">いずれにしても、Enumeration クラスを使用するとビジネス関連の概念に対する関連性が強くなります。</span><span class="sxs-lookup"><span data-stu-id="7c44a-111">Anyway, the use of enumeration classes is more related to business-related concepts.</span></span>

## <a name="implement-an-enumeration-base-class"></a><span data-ttu-id="7c44a-112">Enumeration 基底クラスを実装する</span><span class="sxs-lookup"><span data-stu-id="7c44a-112">Implement an Enumeration base class</span></span>

<span data-ttu-id="7c44a-113">eShopOnContainers 内の注文マイクロサービスは、次の例のように、列挙型基底クラスの実装サンプルを提供しています。</span><span class="sxs-lookup"><span data-stu-id="7c44a-113">The ordering microservice in eShopOnContainers provides a sample Enumeration base class implementation, as shown in the following example:</span></span>

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

<span data-ttu-id="7c44a-114">次の `CardType` : `Enumeration` クラスに関しては、このクラスを任意のエンティティまたは値オブジェクトの型として使用できます。</span><span class="sxs-lookup"><span data-stu-id="7c44a-114">You can use this class as a type in any entity or value object, as for the following `CardType` : `Enumeration` class:</span></span>

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

## <a name="additional-resources"></a><span data-ttu-id="7c44a-115">その他の技術情報</span><span class="sxs-lookup"><span data-stu-id="7c44a-115">Additional resources</span></span>

- <span data-ttu-id="7c44a-116">**Jimmy Bogard。列挙型クラス** </span><span class="sxs-lookup"><span data-stu-id="7c44a-116">**Jimmy Bogard. Enumeration classes** </span></span>\
  <https://lostechies.com/jimmybogard/2008/08/12/enumeration-classes/>

- <span data-ttu-id="7c44a-117">**Steve Smith。C# の列挙型の代替** </span><span class="sxs-lookup"><span data-stu-id="7c44a-117">**Steve Smith. Enum Alternatives in C#** </span></span>\
  <https://ardalis.com/enum-alternatives-in-c>

- <span data-ttu-id="7c44a-118">**Enumeration.cs。**</span><span class="sxs-lookup"><span data-stu-id="7c44a-118">**Enumeration.cs.**</span></span> <span data-ttu-id="7c44a-119">eShopOnContainers の基底列挙型クラス </span><span class="sxs-lookup"><span data-stu-id="7c44a-119">Base Enumeration class in eShopOnContainers </span></span>\
  <https://github.com/dotnet-architecture/eShopOnContainers/blob/dev/src/Services/Ordering/Ordering.Domain/SeedWork/Enumeration.cs>

- <span data-ttu-id="7c44a-120">**CardType.cs**。</span><span class="sxs-lookup"><span data-stu-id="7c44a-120">**CardType.cs**.</span></span> <span data-ttu-id="7c44a-121">eShopOnContainers のサンプル列挙型クラス。</span><span class="sxs-lookup"><span data-stu-id="7c44a-121">Sample Enumeration class in eShopOnContainers.</span></span> \
  <https://github.com/dotnet-architecture/eShopOnContainers/blob/dev/src/Services/Ordering/Ordering.Domain/AggregatesModel/BuyerAggregate/CardType.cs>

- <span data-ttu-id="7c44a-122">**SmartEnum**.</span><span class="sxs-lookup"><span data-stu-id="7c44a-122">**SmartEnum**.</span></span> <span data-ttu-id="7c44a-123">Ardalis - .NET で厳密に型指定されたスマートな列挙型を生成するためのクラス。</span><span class="sxs-lookup"><span data-stu-id="7c44a-123">Ardalis - Classes to help produce strongly typed smarter enums in .NET.</span></span> \
  <https://www.nuget.org/packages/Ardalis.SmartEnum/>

>[!div class="step-by-step"]
><span data-ttu-id="7c44a-124">[前へ](implement-value-objects.md)
>[次へ](domain-model-layer-validations.md)</span><span class="sxs-lookup"><span data-stu-id="7c44a-124">[Previous](implement-value-objects.md)
[Next](domain-model-layer-validations.md)</span></span>
