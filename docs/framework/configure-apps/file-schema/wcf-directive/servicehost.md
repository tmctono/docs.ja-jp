---
title: '@ServiceHost'
ms.date: 03/30/2017
ms.assetid: 96ba6967-00f2-422f-9aa7-15de4d33ebf3
ms.openlocfilehash: 3c7da8d5a473b801da8c48d1cb1504b95cc6c769
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/25/2019
ms.locfileid: "75342128"
---
# <a name="servicehost"></a><span data-ttu-id="56351-101">\@ServiceHost</span><span class="sxs-lookup"><span data-stu-id="56351-101">\@ServiceHost</span></span>
<span data-ttu-id="56351-102">サービス ホストの生成に使用されるファクトリを、ホストされるサービスと、.svc ファイルで提供されるホスティング コードのアクセスとコンパイルに必要なその他のプログラミング部分に関連付けます。</span><span class="sxs-lookup"><span data-stu-id="56351-102">Associates the factory used to produce the service host with the service to be hosted and other programming aspects required to access or compile the hosting code provided in the .svc file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="56351-103">構文</span><span class="sxs-lookup"><span data-stu-id="56351-103">Syntax</span></span>  
  
```xml  
<% @ServiceHost
Service = "Service, ServiceNamespace"
Factory = "Factory, FactoryNamespace"
Debug = "Debug"
Language = "Language"
CodeBehind = "CodeBehind"
%>
```  
  
## <a name="attributes"></a><span data-ttu-id="56351-104">属性</span><span class="sxs-lookup"><span data-stu-id="56351-104">Attributes</span></span>  
  
#### <a name="service"></a><span data-ttu-id="56351-105">サービス</span><span class="sxs-lookup"><span data-stu-id="56351-105">Service</span></span>  
 <span data-ttu-id="56351-106">ホストされるサービスの CLR 型名。</span><span class="sxs-lookup"><span data-stu-id="56351-106">The CLR type name of the service hosted.</span></span> <span data-ttu-id="56351-107">これは、1 つ以上のサービス コンタクトを実装する型の修飾名にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="56351-107">This should be a qualified name of a type that implements one or more of the service contacts.</span></span>  
  
#### <a name="factory"></a><span data-ttu-id="56351-108">ファクトリ</span><span class="sxs-lookup"><span data-stu-id="56351-108">Factory</span></span>  
 <span data-ttu-id="56351-109">サービス ホストのインスタンス化に使用されるサービス ホスト ファクトリの CLR 型名。</span><span class="sxs-lookup"><span data-stu-id="56351-109">The CLR type name of the service host factory used to instantiate the service host.</span></span> <span data-ttu-id="56351-110">この属性は省略できます。</span><span class="sxs-lookup"><span data-stu-id="56351-110">This attribute is optional.</span></span> <span data-ttu-id="56351-111">未指定の場合は、<xref:System.ServiceModel.Activation.ServiceHostFactory> のインスタンスを返す既定の <xref:System.ServiceModel.ServiceHost> が使用されます。</span><span class="sxs-lookup"><span data-stu-id="56351-111">If unspecified, the default <xref:System.ServiceModel.Activation.ServiceHostFactory> is used, which returns an instance of <xref:System.ServiceModel.ServiceHost>.</span></span>  
  
#### <a name="debug"></a><span data-ttu-id="56351-112">デバッグ</span><span class="sxs-lookup"><span data-stu-id="56351-112">Debug</span></span>  
 <span data-ttu-id="56351-113">デバッグシンボルを使用して Windows Communication Foundation (WCF) サービスをコンパイルする必要があるかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="56351-113">Indicates whether the Windows Communication Foundation (WCF) service should be compiled with debug symbols.</span></span> <span data-ttu-id="56351-114">WCF サービスをデバッグシンボルを使用してコンパイルする必要があるかどうかを `true` します。それ以外の場合は、`false`ます。</span><span class="sxs-lookup"><span data-stu-id="56351-114">`true` if the WCF service should be compiled with debug symbols; otherwise, `false`.</span></span>  
  
#### <a name="language"></a><span data-ttu-id="56351-115">言語</span><span class="sxs-lookup"><span data-stu-id="56351-115">Language</span></span>  
 <span data-ttu-id="56351-116">ファイル (.svc) 内のすべてのインライン コードをコンパイルするときに使用する言語を指定します。</span><span class="sxs-lookup"><span data-stu-id="56351-116">Specifies the language used when compiling all the inline code within file (.svc).</span></span> <span data-ttu-id="56351-117">値は任意のを表すことができます。`C#`、`VB`、および `JS`を含む、NET でサポートされているC#言語。それぞれ、、Visual Basic、および JScript .net を参照します。</span><span class="sxs-lookup"><span data-stu-id="56351-117">The values can represent any .NET-supported language, including `C#`, `VB`, and `JS`, which refer to C#, Visual Basic, and JScript .NET, respectively.</span></span> <span data-ttu-id="56351-118">この属性は省略できます。</span><span class="sxs-lookup"><span data-stu-id="56351-118">This attribute is optional.</span></span>  
  
#### <a name="codebehind"></a><span data-ttu-id="56351-119">CodeBehind</span><span class="sxs-lookup"><span data-stu-id="56351-119">CodeBehind</span></span>  
 <span data-ttu-id="56351-120">XML Web サービスを実装するクラスが同じファイル内に存在せず、アセンブリとしてコンパイルされずに \Bin ディレクトリに置かれているとき、XML Web サービスを実装するソース ファイルを指定します。</span><span class="sxs-lookup"><span data-stu-id="56351-120">Specifies the source file that implements the XML Web service, when the class that implements the XML Web service does not reside in the same file and has not been compiled into an assembly and placed in the \Bin directory.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="56351-121">コメント</span><span class="sxs-lookup"><span data-stu-id="56351-121">Remarks</span></span>  
 <span data-ttu-id="56351-122">サービスをホストするために使用される <xref:System.ServiceModel.ServiceHost> は、Windows Communication Foundation (WCF) プログラミングモデル内の機能拡張ポイントです。</span><span class="sxs-lookup"><span data-stu-id="56351-122">The <xref:System.ServiceModel.ServiceHost> used to host the service is a point of extensibility within the Windows Communication Foundation (WCF) programming model.</span></span> <span data-ttu-id="56351-123">ファクトリ パターンは、ホスティング環境が直接インスタンス化できないポリモーフィック型の可能性があるため、<xref:System.ServiceModel.ServiceHost> のインスタンス化に使用されます。</span><span class="sxs-lookup"><span data-stu-id="56351-123">A factory pattern is used to instantiate the <xref:System.ServiceModel.ServiceHost> because it is, potentially, a polymorphic type that the hosting environment should not instantiate directly.</span></span>  
  
 <span data-ttu-id="56351-124">既定の実装では <xref:System.ServiceModel.Activation.ServiceHostFactory> を使用して、<xref:System.ServiceModel.ServiceHost> のインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="56351-124">The default implementation uses <xref:System.ServiceModel.Activation.ServiceHostFactory> to create an instance of <xref:System.ServiceModel.ServiceHost>.</span></span> <span data-ttu-id="56351-125">ただし、 [\@ServiceHost](servicehost.md)ディレクティブでファクトリ実装の CLR 型名を指定することで、独自のファクトリ (派生ホストを返すもの) を指定できます。</span><span class="sxs-lookup"><span data-stu-id="56351-125">But you can provide your own factory (one that returns your derived host) by specifying the CLR type name of your factory implementation in the [\@ServiceHost](servicehost.md) directive.</span></span>  
  
 <span data-ttu-id="56351-126">既定のファクトリの代わりにカスタムサービスホストファクトリを使用するには、次のように[@ServiceHost](servicehost.md)ディレクティブで型名を指定するだけです。</span><span class="sxs-lookup"><span data-stu-id="56351-126">To use you own custom service host factory instead of the default factory, just provide the type name in the [@ServiceHost](servicehost.md) directive as follows:</span></span>  
  
```xml  
<% @ServiceHost Factory="DerivedFactory" Service="MyService" %>  
```  
  
 <span data-ttu-id="56351-127">ファクトリ実装はできるだけ軽量に保持してください。</span><span class="sxs-lookup"><span data-stu-id="56351-127">Keep the factory implementations as light as possible.</span></span> <span data-ttu-id="56351-128">多くのカスタム ロジックがある場合は、それらのロジックをファクトリ内部ではなくホスト内部に置くとコードがさらに再利用可能になります。</span><span class="sxs-lookup"><span data-stu-id="56351-128">If you have lots of custom logic, your code is more reusable if you put that logic inside your host instead of inside the factory.</span></span>  
  
 <span data-ttu-id="56351-129">たとえば、`MyService`に対して AJAX 対応のエンドポイントを有効にするには、次の例に示すように、 [@ServiceHost](servicehost.md)ディレクティブで、既定の <xref:System.ServiceModel.Activation.ServiceHostFactory>ではなく、`Factory` 属性の値に <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> を指定します。</span><span class="sxs-lookup"><span data-stu-id="56351-129">For example, to enable an AJAX-enabled endpoint for `MyService`, specify the <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> for the value of the `Factory` attribute, instead of the default <xref:System.ServiceModel.Activation.ServiceHostFactory>, in the [@ServiceHost](servicehost.md) directive as shown in the following example.</span></span>  
  
## <a name="example"></a><span data-ttu-id="56351-130">使用例</span><span class="sxs-lookup"><span data-stu-id="56351-130">Example</span></span>  
  
```xml  
<% @ServiceHost
Service="MyService"  
Language="C#"  
Debug="true"  
Factory="WebScriptServiceHostFactory"  
%>  
```  
  
## <a name="see-also"></a><span data-ttu-id="56351-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="56351-131">See also</span></span>

- [<span data-ttu-id="56351-132">カスタム サービス ホスト</span><span class="sxs-lookup"><span data-stu-id="56351-132">Custom Service Host</span></span>](../../../wcf/samples/custom-service-host.md)
