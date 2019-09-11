---
title: ServiceHostFactory を使用したホストの拡張
ms.date: 03/30/2017
ms.assetid: bcc5ae1b-21ce-4e0e-a184-17fad74a441e
ms.openlocfilehash: de6a590b94285872dd77006eda7f86d5d629be9d
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2019
ms.locfileid: "70849905"
---
# <a name="extending-hosting-using-servicehostfactory"></a><span data-ttu-id="2f993-102">ServiceHostFactory を使用したホストの拡張</span><span class="sxs-lookup"><span data-stu-id="2f993-102">Extending Hosting Using ServiceHostFactory</span></span>
<span data-ttu-id="2f993-103">Windows Communication Foundation ( <xref:System.ServiceModel.ServiceHost> wcf) でサービスをホストするための標準 API は、wcf アーキテクチャの機能拡張ポイントです。</span><span class="sxs-lookup"><span data-stu-id="2f993-103">The standard <xref:System.ServiceModel.ServiceHost> API for hosting services in Windows Communication Foundation (WCF) is an extensibility point in the WCF architecture.</span></span> <span data-ttu-id="2f993-104">ユーザーは、この <xref:System.ServiceModel.ServiceHost> の派生型として独自のホスト クラスを定義できます。通常は、<xref:System.ServiceModel.Channels.CommunicationObject.OnOpening> を使用するために <xref:System.ServiceModel.Description.ServiceDescription> をオーバーライドして、これにより、サービスを開く前に、強制的に既定のエンドポイントを追加したり、動作を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="2f993-104">Users can derive their own host classes from <xref:System.ServiceModel.ServiceHost>, usually to override <xref:System.ServiceModel.Channels.CommunicationObject.OnOpening> to use <xref:System.ServiceModel.Description.ServiceDescription> to add default endpoints imperatively or modify behaviors, prior to opening the service.</span></span>  
  
 <span data-ttu-id="2f993-105">自己ホスト環境では、カスタムの <xref:System.ServiceModel.ServiceHost> を作成する必要はありません。ホストをインスタンス化し、インスタンス化の後で <xref:System.ServiceModel.ICommunicationObject.Open> を呼び出すコードを記述するので、</span><span class="sxs-lookup"><span data-stu-id="2f993-105">In the self-host environment, you do not have to create a custom <xref:System.ServiceModel.ServiceHost> because you write the code that instantiates the host and then call <xref:System.ServiceModel.ICommunicationObject.Open> on it after you instantiate it.</span></span> <span data-ttu-id="2f993-106">この 2 つのステップの間に任意の処理を記述できます。</span><span class="sxs-lookup"><span data-stu-id="2f993-106">Between those two steps you can do whatever you want.</span></span> <span data-ttu-id="2f993-107">たとえば、新しい <xref:System.ServiceModel.Description.IServiceBehavior> を次のように追加できます。</span><span class="sxs-lookup"><span data-stu-id="2f993-107">You could, for example, add a new <xref:System.ServiceModel.Description.IServiceBehavior>:</span></span>  
  
```csharp
public static void Main()  
{  
   ServiceHost host = new ServiceHost( typeof( MyService ) );  
   host.Description.Add( new MyServiceBehavior() );  
   host.Open();  
  
   ...  
}  
```  
  
 <span data-ttu-id="2f993-108">この方法は再利用できません。</span><span class="sxs-lookup"><span data-stu-id="2f993-108">This approach is not reusable.</span></span> <span data-ttu-id="2f993-109">説明を操作するコードはホスト プログラム (この場合は Main() 関数) に記述されているので、このロジックを別のコンテキストで使用するのは困難です。</span><span class="sxs-lookup"><span data-stu-id="2f993-109">The code that manipulates the description is coded into the host program (in this case, the Main() function), so it is difficult to reuse that logic in other contexts.</span></span> <span data-ttu-id="2f993-110">このような強制コードを記述することなく、<xref:System.ServiceModel.Description.IServiceBehavior> を追加する方法もあります。</span><span class="sxs-lookup"><span data-stu-id="2f993-110">There are also other ways of adding an <xref:System.ServiceModel.Description.IServiceBehavior> that do not require imperative code.</span></span> <span data-ttu-id="2f993-111"><xref:System.ServiceModel.ServiceBehaviorAttribute> から派生した属性をサービス実装型に組み込む方法や、カスタム動作の詳細を構成できるようにしておき、構成を使用して動的に組み込む方法が考えられます。</span><span class="sxs-lookup"><span data-stu-id="2f993-111">You can derive an attribute from <xref:System.ServiceModel.ServiceBehaviorAttribute> and put that on your service implementation type or you can make a custom behavior configurable and compose it dynamically using configuration.</span></span>  
  
 <span data-ttu-id="2f993-112">ただし、サンプル コードを少し修正して問題を解決することもできます。</span><span class="sxs-lookup"><span data-stu-id="2f993-112">However, a slight variation of the example can also be used to solve this problem.</span></span> <span data-ttu-id="2f993-113">1 つの方法として、ServiceBehavior を追加するコードを `Main()` 内に記述する代わりに、<xref:System.ServiceModel.Channels.CommunicationObject.OnOpening%2A> から派生した <xref:System.ServiceModel.ServiceHost> メソッドに記述することができます。</span><span class="sxs-lookup"><span data-stu-id="2f993-113">One approach is to move the code that adds the ServiceBehavior out of `Main()` and into the <xref:System.ServiceModel.Channels.CommunicationObject.OnOpening%2A> method of a custom derivative of <xref:System.ServiceModel.ServiceHost>:</span></span>  
  
```csharp
public class DerivedHost : ServiceHost  
{  
   public DerivedHost( Type t, params Uri baseAddresses ) :  
      base( t, baseAddresses ) {}  
  
   public override void OnOpening()  
   {  
  this.Description.Add( new MyServiceBehavior() );  
   }  
}  
```  
  
 <span data-ttu-id="2f993-114">`Main()` 内には、次のように記述できます。</span><span class="sxs-lookup"><span data-stu-id="2f993-114">Then, inside of `Main()` you can use:</span></span>  
  
```csharp
public static void Main()  
{  
   ServiceHost host = new DerivedHost( typeof( MyService ) );  
   host.Open();  
  
   ...  
}  
```  
  
 <span data-ttu-id="2f993-115">このようにカスタム ロジックをカプセル化、抽象化すると、さまざまなホスト アプリケーションで再利用できます。</span><span class="sxs-lookup"><span data-stu-id="2f993-115">Now you have encapsulated the custom logic into a clean abstraction that can be easily reused across many different host executables.</span></span>  
  
 <span data-ttu-id="2f993-116">カスタムの <xref:System.ServiceModel.ServiceHost> を Internet Information Services (IIS) や Windows Process Activation Service (WAS) で使用する方法は、それほど単純ではありません。</span><span class="sxs-lookup"><span data-stu-id="2f993-116">It is not immediately obvious how to use this custom <xref:System.ServiceModel.ServiceHost> from inside of Internet Information Services (IIS) or Windows Process Activation Service (WAS).</span></span> <span data-ttu-id="2f993-117">アプリケーションの代わりにホスティング環境が <xref:System.ServiceModel.ServiceHost> をインスタンス化するという点で、これらの環境は、自己ホスト環境と異なっています。</span><span class="sxs-lookup"><span data-stu-id="2f993-117">Those environments are different than the self-host environment, because the hosting environment is the one instantiating the <xref:System.ServiceModel.ServiceHost> on behalf of the application.</span></span> <span data-ttu-id="2f993-118">IIS および WAS ホスティング インフラストラクチャは、<xref:System.ServiceModel.ServiceHost> のカスタム派生物については何も認識しません。</span><span class="sxs-lookup"><span data-stu-id="2f993-118">The IIS and WAS hosting infrastructure does not know anything about your custom <xref:System.ServiceModel.ServiceHost> derivative.</span></span>  
  
 <span data-ttu-id="2f993-119"><xref:System.ServiceModel.Activation.ServiceHostFactory> は、独自に定義した <xref:System.ServiceModel.ServiceHost> の派生クラスに、IIS または WAS からアクセスする手段として設計されました。</span><span class="sxs-lookup"><span data-stu-id="2f993-119">The <xref:System.ServiceModel.Activation.ServiceHostFactory> was designed to solve this problem of accessing your custom <xref:System.ServiceModel.ServiceHost> from within IIS or WAS.</span></span> <span data-ttu-id="2f993-120"><xref:System.ServiceModel.ServiceHost> から派生したカスタム ホストは、動的に構成され、種類もさまざまであるため、ホスト環境でこれを直接インスタンス化することはありません。</span><span class="sxs-lookup"><span data-stu-id="2f993-120">Because a custom host that is derived from <xref:System.ServiceModel.ServiceHost> is dynamically configured and potentially of various types, the hosting environment never instantiates it directly.</span></span> <span data-ttu-id="2f993-121">代わりに、WCF はファクトリパターンを使用して、ホスト環境とサービスの具象型の間に間接レイヤーを提供します。</span><span class="sxs-lookup"><span data-stu-id="2f993-121">Instead, WCF uses a factory pattern to provide a layer of indirection between the hosting environment and the concrete type of the service.</span></span> <span data-ttu-id="2f993-122">特に指定しなければ、<xref:System.ServiceModel.Activation.ServiceHostFactory> のインスタンスを返す、<xref:System.ServiceModel.ServiceHost> の既定の実装が使用されます。</span><span class="sxs-lookup"><span data-stu-id="2f993-122">Unless you tell it otherwise, it uses a default implementation of <xref:System.ServiceModel.Activation.ServiceHostFactory> that returns an instance of <xref:System.ServiceModel.ServiceHost>.</span></span> <span data-ttu-id="2f993-123">ただし、 @ServiceHostディレクティブでファクトリ実装の CLR 型名を指定することによって、派生ホストを返す独自のファクトリを指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="2f993-123">But you can also provide your own factory that returns your derived host by specifying the CLR type name of your factory implementation in the @ServiceHost directive.</span></span>  
  
 <span data-ttu-id="2f993-124">基本的なケースでは、独自のファクトリは容易に実装できます。</span><span class="sxs-lookup"><span data-stu-id="2f993-124">The intent is that for basic cases, implementing your own factory should be a straight forward exercise.</span></span> <span data-ttu-id="2f993-125">派生 <xref:System.ServiceModel.Activation.ServiceHostFactory> を返す、カスタムの <xref:System.ServiceModel.ServiceHost> の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="2f993-125">For example, here is a custom <xref:System.ServiceModel.Activation.ServiceHostFactory> that returns a derived <xref:System.ServiceModel.ServiceHost>:</span></span>  
  
```csharp
public class DerivedFactory : ServiceHostFactory  
{  
   public override ServiceHost CreateServiceHost( Type t, Uri[] baseAddresses )  
   {  
      return new DerivedHost( t, baseAddresses )  
   }  
}  
```  
  
 <span data-ttu-id="2f993-126">既定のファクトリの代わりにこのファクトリを使用するには、次の@ServiceHostようにディレクティブに型名を指定します。</span><span class="sxs-lookup"><span data-stu-id="2f993-126">To use this factory instead of the default factory, provide the type name in the @ServiceHost directive as follows:</span></span>  
  
`<% @ServiceHost Factory="DerivedFactory" Service="MyService" %>`  
  
 <span data-ttu-id="2f993-127"><xref:System.ServiceModel.ServiceHost> から返す <xref:System.ServiceModel.Activation.ServiceHostFactory.CreateServiceHost%2A> で行う処理について、技術的には制限はありませんが、ファクトリ実装はできるだけ単純にしておくことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="2f993-127">While there is no technical limit on doing what you want to the <xref:System.ServiceModel.ServiceHost> you return from <xref:System.ServiceModel.Activation.ServiceHostFactory.CreateServiceHost%2A>, we suggest that you keep your factory implementations as simple as possible.</span></span> <span data-ttu-id="2f993-128">多くのカスタムロジックがある場合は、そのロジックをファクトリ内部ではなくホスト内に配置して、再利用できるようにすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="2f993-128">If you have lots of custom logic, it is better to put that logic inside of your host instead of inside the factory so that it can be reusable.</span></span>  
  
 <span data-ttu-id="2f993-129">ここで、ホスティング API にはもう 1 つのレイヤーがあることを知っておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="2f993-129">There is one more layer to the hosting API that should be mentioned here.</span></span> <span data-ttu-id="2f993-130">また、WCF <xref:System.ServiceModel.ServiceHostBase>に<xref:System.ServiceModel.Activation.ServiceHostFactoryBase>はとも<xref:System.ServiceModel.ServiceHost>あり<xref:System.ServiceModel.Activation.ServiceHostFactory>ます。このとは、それぞれとを派生させたものです。</span><span class="sxs-lookup"><span data-stu-id="2f993-130">WCF also has <xref:System.ServiceModel.ServiceHostBase> and <xref:System.ServiceModel.Activation.ServiceHostFactoryBase>, from which <xref:System.ServiceModel.ServiceHost> and <xref:System.ServiceModel.Activation.ServiceHostFactory> respectively derive.</span></span> <span data-ttu-id="2f993-131">これらは、メタデータ システムの大部分がカスタム コードに置き換わるような、高度なシナリオを想定して用意されています。</span><span class="sxs-lookup"><span data-stu-id="2f993-131">Those exist for more advanced scenarios where you must swap out large parts of the metadata system with your own customized creations.</span></span>
