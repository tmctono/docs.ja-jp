---
title: Seedwork (ドメイン モデルの再利用可能な基底クラスとインターフェイス)
description: '.NET マイクロサービス: コンテナー化された .NET アプリケーションのアーキテクチャ | Seedwork 概念を開始点として使用し、DDD 指向ドメイン モデルの実装を開始する。'
ms.date: 10/08/2018
ms.openlocfilehash: f53988b92a05fb54f3f05d9f463450d1a11a0843
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2019
ms.locfileid: "73737220"
---
# <a name="seedwork-reusable-base-classes-and-interfaces-for-your-domain-model"></a><span data-ttu-id="80ec2-103">Seedwork (ドメイン モデルの再利用可能な基底クラスとインターフェイス)</span><span class="sxs-lookup"><span data-stu-id="80ec2-103">Seedwork (reusable base classes and interfaces for your domain model)</span></span>

<span data-ttu-id="80ec2-104">ソリューション フォルダーには、*SeedWork* フォルダーが含まれています。</span><span class="sxs-lookup"><span data-stu-id="80ec2-104">The solution folder contains a *SeedWork* folder.</span></span> <span data-ttu-id="80ec2-105">このフォルダー内にあるカスタム基底クラスは、ドメイン エンティティおよび値オブジェクトの基礎として使用できます。</span><span class="sxs-lookup"><span data-stu-id="80ec2-105">This folder contains custom base classes that you can use as a base for your domain entities and value objects.</span></span> <span data-ttu-id="80ec2-106">これらの基底クラスを使用すると、各ドメインのオブジェクト クラスで冗長なコードがなくなります。</span><span class="sxs-lookup"><span data-stu-id="80ec2-106">Use these base classes so you do not have redundant code in each domain’s object class.</span></span> <span data-ttu-id="80ec2-107">これらのタイプのクラス用のフォルダーは、*Framework* のような名前ではなく、*SeedWork* という名前になっています。</span><span class="sxs-lookup"><span data-stu-id="80ec2-107">The folder for these types of classes is called *SeedWork* and not something like *Framework*.</span></span> <span data-ttu-id="80ec2-108">*SeedWork* という名前になっているのは、このフォルダーには再利用可能なクラスのほんの一部しか含まれておらず、実際にはフレームワークと見なすことができないためです。</span><span class="sxs-lookup"><span data-stu-id="80ec2-108">It's called *SeedWork* because the folder contains just a small subset of reusable classes which cannot really be considered a framework.</span></span> <span data-ttu-id="80ec2-109">*Seedwork* は、[Michael Feathers](https://www.artima.com/forums/flat.jsp?forum=106&thread=8826) が発表し、[Martin Fowler](https://martinfowler.com/bliki/Seedwork.html) が普及させた用語ですが、Common や SharedKernel といった名前で呼ばれる場合もあります。</span><span class="sxs-lookup"><span data-stu-id="80ec2-109">*Seedwork* is a term introduced by [Michael Feathers](https://www.artima.com/forums/flat.jsp?forum=106&thread=8826) and popularized by [Martin Fowler](https://martinfowler.com/bliki/Seedwork.html) but you could also name that folder Common, SharedKernel, or similar.</span></span>

<span data-ttu-id="80ec2-110">図 7-12 は、注文マイクロサービスのドメイン モデルの SeedWork を構成するクラスを示しています。</span><span class="sxs-lookup"><span data-stu-id="80ec2-110">Figure 7-12 shows the classes that form the seedwork of the domain model in the ordering microservice.</span></span> <span data-ttu-id="80ec2-111">カスタム基底クラス (Entity、ValueObject、Enumeration など) とインターフェイスがいくつか含まれています。</span><span class="sxs-lookup"><span data-stu-id="80ec2-111">It has a few custom base classes like Entity, ValueObject, and Enumeration, plus a few interfaces.</span></span> <span data-ttu-id="80ec2-112">これらのインターフェイス (IRepository と IUnitOfWork) は、実装する必要があるものをインフラストラクチャ レイヤーに通知します。</span><span class="sxs-lookup"><span data-stu-id="80ec2-112">These interfaces (IRepository and IUnitOfWork) inform the infrastructure layer about what needs to be implemented.</span></span> <span data-ttu-id="80ec2-113">また、これらのインターフェイスは、アプリケーション レイヤーから依存関係の挿入を通じて使用されます。</span><span class="sxs-lookup"><span data-stu-id="80ec2-113">Those interfaces are also used through Dependency Injection from the application layer.</span></span>

<span data-ttu-id="80ec2-114">:::image type="complex" source="./media/seedwork-domain-model-base-classes-interfaces/vs-solution-seedwork-classes.png" alt-text="SeedWork フォルダーに含まれているクラスのスクリーンショット。":::</span><span class="sxs-lookup"><span data-stu-id="80ec2-114">:::image type="complex" source="./media/seedwork-domain-model-base-classes-interfaces/vs-solution-seedwork-classes.png" alt-text="Screenshot of the classes contained in the SeedWork folder.":::</span></span>
<span data-ttu-id="80ec2-115">基底クラスとインターフェイスを含む、SeedWork フォルダーの詳細な内容: Entity.cs、Enumeration.cs、IAggregateRoot.cs、IRepository.cs、IUnitOfWork.cs、ValueObject.cs。</span><span class="sxs-lookup"><span data-stu-id="80ec2-115">The detailed contents of the SeedWork folder, containing base classes and interfaces: Entity.cs, Enumeration.cs, IAggregateRoot.cs, IRepository.cs, IUnitOfWork.cs, and ValueObject.cs.</span></span>
:::image-end:::

<span data-ttu-id="80ec2-116">**図 7-12**。</span><span class="sxs-lookup"><span data-stu-id="80ec2-116">**Figure 7-12**.</span></span> <span data-ttu-id="80ec2-117">ドメイン モデル "SeedWork" の基底クラスとインターフェイスのサンプル セット</span><span class="sxs-lookup"><span data-stu-id="80ec2-117">A sample set of domain model “seedwork" base classes and interfaces</span></span>

<span data-ttu-id="80ec2-118">これは、コピーと貼り付けによって再利用するタイプのもので、多くの開発者によってプロジェクト間で共有されます。正式なフレームワークではありません。</span><span class="sxs-lookup"><span data-stu-id="80ec2-118">This is the type of copy and paste reuse that many developers share between projects, not a formal framework.</span></span> <span data-ttu-id="80ec2-119">SeedWork は、どのレイヤーやライブラリでも使用できます。</span><span class="sxs-lookup"><span data-stu-id="80ec2-119">You can have seedworks in any layer or library.</span></span> <span data-ttu-id="80ec2-120">ただし、クラスとインターフェイスのセットが十分に大きくなったら、単一のクラス ライブラリを作成するのがよいでしょう。</span><span class="sxs-lookup"><span data-stu-id="80ec2-120">However, if the set of classes and interfaces gets big enough, you might want to create a single class library.</span></span>

## <a name="the-custom-entity-base-class"></a><span data-ttu-id="80ec2-121">カスタム Entity 基底クラス</span><span class="sxs-lookup"><span data-stu-id="80ec2-121">The custom Entity base class</span></span>

<span data-ttu-id="80ec2-122">次のコードは、Entity 基底クラスの例です。このクラスでは、任意のドメイン エンティティ (エンティティ ID、[等値演算子](../../../csharp/language-reference/operators/equality-operators.md)、エンティティごとのドメイン イベント リストなど) が同様の方法で使用できるコードを配置できます。</span><span class="sxs-lookup"><span data-stu-id="80ec2-122">The following code is an example of an Entity base class where you can place code that can be used the same way by any domain entity, such as the entity ID, [equality operators](../../../csharp/language-reference/operators/equality-operators.md), a domain event list per entity, etc.</span></span>

```csharp
// COMPATIBLE WITH ENTITY FRAMEWORK CORE (1.1 and later)
public abstract class Entity
{
    int? _requestedHashCode;
    int _Id;
    private List<INotification> _domainEvents;
    public virtual int Id
    {
        get
        {
            return _Id;
        }
        protected set
        {
            _Id = value;
        }
    }

    public List<INotification> DomainEvents => _domainEvents;
    public void AddDomainEvent(INotification eventItem)
    {
        _domainEvents = _domainEvents ?? new List<INotification>();
        _domainEvents.Add(eventItem);
    }
    public void RemoveDomainEvent(INotification eventItem)
    {
        if (_domainEvents is null) return;
        _domainEvents.Remove(eventItem);
    }

    public bool IsTransient()
    {
        return this.Id == default(Int32);
    }

    public override bool Equals(object obj)
    {
        if (obj == null || !(obj is Entity))
            return false;
        if (Object.ReferenceEquals(this, obj))
            return true;
        if (this.GetType() != obj.GetType())
            return false;
        Entity item = (Entity)obj;
        if (item.IsTransient() || this.IsTransient())
            return false;
        else
            return item.Id == this.Id;
    }

    public override int GetHashCode()
    {
        if (!IsTransient())
        {
            if (!_requestedHashCode.HasValue)
                _requestedHashCode = this.Id.GetHashCode() ^ 31;
            // XOR for random distribution. See:
            // https://blogs.msdn.microsoft.com/ericlippert/2011/02/28/guidelines-and-rules-for-gethashcode/
            return _requestedHashCode.Value;
        }
        else
            return base.GetHashCode();
    }
    public static bool operator ==(Entity left, Entity right)
    {
        if (Object.Equals(left, null))
            return (Object.Equals(right, null));
        else
            return left.Equals(right);
    }
    public static bool operator !=(Entity left, Entity right)
    {
        return !(left == right);
    }
}
```

<span data-ttu-id="80ec2-123">エンティティごとのドメイン イベント リストを使用する以前のコードについては、次のセクションでドメイン イベントを取り上げるときに説明します。</span><span class="sxs-lookup"><span data-stu-id="80ec2-123">The previous code using a domain event list per entity will be explained in the next sections when focusing on domain events.</span></span>

## <a name="repository-contracts-interfaces-in-the-domain-model-layer"></a><span data-ttu-id="80ec2-124">ドメイン モデル レイヤーのリポジトリ コントラクト (インターフェイス)</span><span class="sxs-lookup"><span data-stu-id="80ec2-124">Repository contracts (interfaces) in the domain model layer</span></span>

<span data-ttu-id="80ec2-125">リポジトリ コントラクトは、各集計に使用されるリポジトリのコントラクト要件を示すシンプルな .NET インターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="80ec2-125">Repository contracts are simply .NET interfaces that express the contract requirements of the repositories to be used for each aggregate.</span></span>

<span data-ttu-id="80ec2-126">リポジトリ自体と EF コア コード、または他の任意のインフラストラクチャの依存関係やコード (Linq や SQL など) は、ドメイン モデル内に実装してはなりません。リポジトリは、ドメイン モデルでユーザーが定義するインターフェイスのみを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="80ec2-126">The repositories themselves, with EF Core code or any other infrastructure dependencies and code (Linq, SQL, etc.), must not be implemented within the domain model; the repositories should only implement the interfaces you define in the domain model.</span></span>

<span data-ttu-id="80ec2-127">この手法 (リポジトリ インターフェイスをドメイン モデル レイヤーに配置する手法) に関連するパターンが、インターフェイスの分離 パターンです。</span><span class="sxs-lookup"><span data-stu-id="80ec2-127">A pattern related to this practice (placing the repository interfaces in the domain model layer) is the Separated Interface pattern.</span></span> <span data-ttu-id="80ec2-128">Martin Fowler は、次のように[説明](https://www.martinfowler.com/eaaCatalog/separatedInterface.html)しています。"インターフェイスの分離を使用して、あるインターフェイスをあるパッケージに定義します。ただし、その実装は、別のパッケージで行います。</span><span class="sxs-lookup"><span data-stu-id="80ec2-128">As [explained](https://www.martinfowler.com/eaaCatalog/separatedInterface.html) by Martin Fowler, “Use Separated Interface to define an interface in one package but implement it in another.</span></span> <span data-ttu-id="80ec2-129">これにより、このインターフェイスへの依存関係が必要なクライアントは、実装を全く意識せずにすむようになります。"</span><span class="sxs-lookup"><span data-stu-id="80ec2-129">This way a client that needs the dependency to the interface can be completely unaware of the implementation.”</span></span>

<span data-ttu-id="80ec2-130">インターフェイスの分離パターンに従うと、アプリケーション レイヤー (この場合はマイクロサービスの Web API プロジェクト) は、ドメイン モデルで定義された要件に対する依存関係を持つことができます。ただし、インフラストラクチャ/ 永続化レイヤーに対する直接の依存関係を持つことはできません。</span><span class="sxs-lookup"><span data-stu-id="80ec2-130">Following the Separated Interface pattern enables the application layer (in this case, the Web API project for the microservice) to have a dependency on the requirements defined in the domain model, but not a direct dependency to the infrastructure/persistence layer.</span></span> <span data-ttu-id="80ec2-131">また、依存関係の挿入を使用すると、リポジトリを使用してインフラストラクチャ/永続化レイヤーに実装された実装を分離できます。</span><span class="sxs-lookup"><span data-stu-id="80ec2-131">In addition, you can use Dependency Injection to isolate the implementation, which is implemented in the infrastructure/ persistence layer using repositories.</span></span>

<span data-ttu-id="80ec2-132">たとえば、IOrderRepository インターフェイスを使用する次の例では、OrderRepository クラスがインフラストラクチャ レイヤーで実装する必要のある操作が定義されています。</span><span class="sxs-lookup"><span data-stu-id="80ec2-132">For example, the following example with the IOrderRepository interface defines what operations the OrderRepository class will need to implement at the infrastructure layer.</span></span> <span data-ttu-id="80ec2-133">アプリケーションの現在の実装では、簡略化された CQRS アプローチに従ってクエリが分割されているため、コードは、データベースに注文を追加するか、またはデータベースの注文を更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="80ec2-133">In the current implementation of the application, the code just needs to add or update orders to the database, since queries are split following the simplified CQRS approach.</span></span>

```csharp
// Defined at IOrderRepository.cs
public interface IOrderRepository : IRepository<Order>
{
    Order Add(Order order);

    void Update(Order order);

    Task<Order> GetAsync(int orderId);
}

// Defined at IRepository.cs (Part of the Domain Seedwork)
public interface IRepository<T> where T : IAggregateRoot
{
    IUnitOfWork UnitOfWork { get; }
}
```

## <a name="additional-resources"></a><span data-ttu-id="80ec2-134">その他の技術情報</span><span class="sxs-lookup"><span data-stu-id="80ec2-134">Additional resources</span></span>

- <span data-ttu-id="80ec2-135">**Martin Fowler。インターフェイスの分離。**</span><span class="sxs-lookup"><span data-stu-id="80ec2-135">**Martin Fowler. Separated Interface.**</span></span> \
  <https://www.martinfowler.com/eaaCatalog/separatedInterface.html>

>[!div class="step-by-step"]
><span data-ttu-id="80ec2-136">[前へ](net-core-microservice-domain-model.md)
>[次へ](implement-value-objects.md)</span><span class="sxs-lookup"><span data-stu-id="80ec2-136">[Previous](net-core-microservice-domain-model.md)
[Next](implement-value-objects.md)</span></span>
