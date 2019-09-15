---
title: '方法: ASP.NET AJAX エンドポイントのために HTTP POST または HTTP GET を選択する'
ms.date: 03/30/2017
ms.assetid: b47de82a-4c92-4af6-bceb-a5cb8bb8ede9
ms.openlocfilehash: 6de32c798e7d0db5ad2d8f6666d6c5d1714250d5
ms.sourcegitcommit: 005980b14629dfc193ff6cdc040800bc75e0a5a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/14/2019
ms.locfileid: "70991576"
---
# <a name="how-to-choose-between-http-post-and-http-get-requests-for-aspnet-ajax-endpoints"></a><span data-ttu-id="6d202-102">方法: ASP.NET AJAX エンドポイントのために HTTP POST または HTTP GET を選択する</span><span class="sxs-lookup"><span data-stu-id="6d202-102">How to: Choose between HTTP POST and HTTP GET requests for ASP.NET AJAX Endpoints</span></span>

<span data-ttu-id="6d202-103">Windows Communication Foundation (WCF) を使用すると、クライアント Web サイトの JavaScript から呼び出すことができる ASP.NET AJAX 対応エンドポイントを公開するサービスを作成できます。</span><span class="sxs-lookup"><span data-stu-id="6d202-103">Windows Communication Foundation (WCF) allows you to create a service that exposes an ASP.NET AJAX-enabled endpoint that can be called from JavaScript on a client Web site.</span></span> <span data-ttu-id="6d202-104">このようなサービスを構築するための基本的[な手順については、「方法:構成を使用して ASP.NET AJAX エンド](../../../../docs/framework/wcf/feature-details/how-to-use-configuration-to-add-an-aspnet-ajax-endpoint.md)ポイント[を追加し、次の操作を行います。構成](../../../../docs/framework/wcf/feature-details/how-to-add-an-aspnet-ajax-endpoint-without-using-configuration.md)を使用せずに ASP.NET AJAX エンドポイントを追加します。</span><span class="sxs-lookup"><span data-stu-id="6d202-104">The basic procedures for building such services is discussed in [How to: Use Configuration to Add an ASP.NET AJAX Endpoint](../../../../docs/framework/wcf/feature-details/how-to-use-configuration-to-add-an-aspnet-ajax-endpoint.md) and [How to: Add an ASP.NET AJAX Endpoint Without Using Configuration](../../../../docs/framework/wcf/feature-details/how-to-add-an-aspnet-ajax-endpoint-without-using-configuration.md).</span></span>  
  
 <span data-ttu-id="6d202-105">ASP.NET AJAX では、HTTP POST 動詞および HTTP GET 動詞を使用する操作をサポートしており、HTTP POST が既定となっています。</span><span class="sxs-lookup"><span data-stu-id="6d202-105">ASP.NET AJAX supports operations that use the HTTP POST and HTTP GET verbs, with HTTP POST being the default.</span></span> <span data-ttu-id="6d202-106">副作用がなく、返されるデータがほとんど、またはまったく変更されない操作を作成する場合は、代わりに HTTP GET を使用します。</span><span class="sxs-lookup"><span data-stu-id="6d202-106">When creating an operation that has no side effects and returns data that rarely or never changes, use HTTP GET instead.</span></span> <span data-ttu-id="6d202-107">GET 操作の結果はキャッシュされます。つまり、同じ操作についての複数の呼び出し結果がサービスに対する 1 回だけの要求で済むことになります。</span><span class="sxs-lookup"><span data-stu-id="6d202-107">Results of GET operations can be cached, which means that multiple calls to the same operation may result in only one request to your service.</span></span> <span data-ttu-id="6d202-108">キャッシュは WCF では実行されませんが、任意のレベル (ユーザーのブラウザー、プロキシサーバー、およびその他のレベル) で実行できます。キャッシュはサービス パフォーマンスの向上が望まれる場合には有効ですが、データの変更が頻繁であったり、操作によって何かのアクションが実行される場合は適していません。</span><span class="sxs-lookup"><span data-stu-id="6d202-108">The caching is not done by WCF but can take place at any level (in a user's browser, on a proxy server, and other levels.) Caching is advantageous if you want to increase service performance, but may not be acceptable if data changes frequently or if the operation performs some action.</span></span>  
  
 <span data-ttu-id="6d202-109">たとえば、ユーザーの音楽ライブラリを管理するサービスをデザインする場合、アルバムのタイトルに基づいてアーティストを検索する操作では GET の使用は役に立ちますが、ユーザーの個人コレクションにアルバムを追加する操作では POST を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6d202-109">For example, if you are designing service to manage a user's music library, an operation that looks up the artist based on an album's title benefits from using GET, but an operation that adds an album to the user's personal collection must use POST.</span></span>  
  
 <span data-ttu-id="6d202-110">キャッシュの有効期間を制御するには、<xref:System.ServiceModel.Web.OutgoingWebResponseContext> 型を使用します。</span><span class="sxs-lookup"><span data-stu-id="6d202-110">To control the lifetime of the cache, use the <xref:System.ServiceModel.Web.OutgoingWebResponseContext> type.</span></span> <span data-ttu-id="6d202-111">たとえば、1 時間ごとに更新される天気予報を返すサービスをデザインする場合、GET を使用することが考えられますが、サービスを使用するユーザーが古いデータにアクセスすることを防止するために、キャッシュの有効期間を 1 時間以内に制限します。</span><span class="sxs-lookup"><span data-stu-id="6d202-111">For example, when designing a service that returns weather forecasts updated hourly, you would use GET but limit the cache duration to an hour or less to prevent the users of the service from accessing stale data.</span></span>  
  
 <span data-ttu-id="6d202-112">Script Manager コントロールを使用する ASP.NET AJAX ページからサービスを使用する場合は、Script Manager のメカニズムにより適切な要求の種類が発行されることが保証されているため、操作で GET と POST のどちらを使用しても違いはありません。</span><span class="sxs-lookup"><span data-stu-id="6d202-112">When using services from an ASP.NET AJAX page that use the Script Manager control, it makes no difference whether the operation uses GET or POST - the script manager mechanism ensures that the correct request type is issued.</span></span>  
  
 <span data-ttu-id="6d202-113">HTTP GET 操作では、複合型データ コントラクト型も含めて、POST 操作でサポートされるすべての入力パラメーターを使用できます。</span><span class="sxs-lookup"><span data-stu-id="6d202-113">HTTP GET operations use any input parameters supported by POST operations, including complex data contract types.</span></span> <span data-ttu-id="6d202-114">ただし、多くの場合、キャッシュの効率が低下するため、多数のパラメーター、または複雑すぎるパラメーターを GET 操作で使用しないことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="6d202-114">However, in most cases it is recommended to avoid too many parameters or parameters that are too complex in GET operations because it reduces caching efficiency.</span></span>  
  
 <span data-ttu-id="6d202-115">このトピックでは、<xref:System.ServiceModel.Web.WebGetAttribute> または <xref:System.ServiceModel.Web.WebInvokeAttribute> 属性を追加することで、サービス コントラクトに適切な操作を GET と POST から選択する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="6d202-115">This topic demonstrates how to select between GET and POST by adding the <xref:System.ServiceModel.Web.WebGetAttribute> or <xref:System.ServiceModel.Web.WebInvokeAttribute> attributes to the relevant operations in the service contract.</span></span> <span data-ttu-id="6d202-116">サービスを実行するために必要な他の手順 (サービスを実装、構成、およびホストする) は、WCF の ASP.NET AJAX サービスで使用される手順と似ています。</span><span class="sxs-lookup"><span data-stu-id="6d202-116">The other steps (to implement, configure and host the service) that are required to get the service running are similar to those used by any ASP.NET AJAX service in WCF.</span></span>  
  
 <span data-ttu-id="6d202-117"><xref:System.ServiceModel.Web.WebGetAttribute> でマークされた操作では、常に GET 要求が使用されます。</span><span class="sxs-lookup"><span data-stu-id="6d202-117">An operation marked with the <xref:System.ServiceModel.Web.WebGetAttribute> always uses a GET request.</span></span> <span data-ttu-id="6d202-118"><xref:System.ServiceModel.Web.WebInvokeAttribute> でマークされた操作と、これらの 2 つの属性のどちらでもマークされていない操作では、POST 要求が使用されます。</span><span class="sxs-lookup"><span data-stu-id="6d202-118">An operation marked with the <xref:System.ServiceModel.Web.WebInvokeAttribute>, or not marked with any of the two attributes, uses a POST request.</span></span> <span data-ttu-id="6d202-119"><xref:System.ServiceModel.Web.WebInvokeAttribute> は、<xref:System.ServiceModel.Web.WebInvokeAttribute.Method%2A> プロパティを介して、GET と POST 以外の HTTP 動詞 (PUT や DELETE など) の使用を許可します。</span><span class="sxs-lookup"><span data-stu-id="6d202-119">The <xref:System.ServiceModel.Web.WebInvokeAttribute> allows the use of other HTTP verbs, other than GET and POST (such as PUT and DELETE) through the <xref:System.ServiceModel.Web.WebInvokeAttribute.Method%2A> property.</span></span> <span data-ttu-id="6d202-120">ただし、これらの動詞は ASP.NET AJAX ではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="6d202-120">However, these verbs are not supported by ASP.NET AJAX.</span></span> <span data-ttu-id="6d202-121">Script Manager コントロールを使用して ASP.NET ページからサービスを使用する場合は、<xref:System.ServiceModel.Web.WebInvokeAttribute.Method%2A> プロパティは使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="6d202-121">If you intend to use the service from ASP.NET pages using the Script Manager control, do not use the <xref:System.ServiceModel.Web.WebInvokeAttribute.Method%2A> property.</span></span>  
  
 <span data-ttu-id="6d202-122">GET に切り替える実際の例については、 [AJAX サービスの基本的な](../../../../docs/framework/wcf/samples/basic-ajax-service.md)サンプルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6d202-122">For a working example of switching to GET, see the [Basic AJAX Service](../../../../docs/framework/wcf/samples/basic-ajax-service.md) sample.</span></span>  
  
 <span data-ttu-id="6d202-123">POST を使用するサンプルについては、「 [HTTP post サンプルを使用した AJAX サービス](../../../../docs/framework/wcf/samples/ajax-service-using-http-post.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6d202-123">For a sample that uses POST, see the [AJAX Service Using HTTP POST](../../../../docs/framework/wcf/samples/ajax-service-using-http-post.md) sample.</span></span>  
  
## <a name="to-create-a-wcf-service-that-responds-to-http-get-or-http-post-requests"></a><span data-ttu-id="6d202-124">HTTP GET または HTTP POST 要求に応答する WCF サービスを作成するには</span><span class="sxs-lookup"><span data-stu-id="6d202-124">To create a WCF service that responds to HTTP GET or HTTP POST requests</span></span>
  
1. <span data-ttu-id="6d202-125"><xref:System.ServiceModel.ServiceContractAttribute>属性でマークされたインターフェイスを使用して、基本的な WCF サービスコントラクトを定義します。</span><span class="sxs-lookup"><span data-stu-id="6d202-125">Define a basic WCF service contract with an interface marked with the <xref:System.ServiceModel.ServiceContractAttribute> attribute.</span></span> <span data-ttu-id="6d202-126">各操作を <xref:System.ServiceModel.OperationContractAttribute> でマークします。</span><span class="sxs-lookup"><span data-stu-id="6d202-126">Mark each operation with the <xref:System.ServiceModel.OperationContractAttribute>.</span></span> <span data-ttu-id="6d202-127"><xref:System.ServiceModel.Web.WebGetAttribute> 属性を追加して、操作が HTTP GET 要求に応答するように指定します。</span><span class="sxs-lookup"><span data-stu-id="6d202-127">Add the <xref:System.ServiceModel.Web.WebGetAttribute> attribute to stipulate that an operation should respond to HTTP GET requests.</span></span> <span data-ttu-id="6d202-128">HTTP POST を明示的に指定するために <xref:System.ServiceModel.Web.WebInvokeAttribute> 属性を追加することもできます。また、属性を指定しなければ、既定で HTTP POST となります。</span><span class="sxs-lookup"><span data-stu-id="6d202-128">You can also add the <xref:System.ServiceModel.Web.WebInvokeAttribute> attribute to explicitly specify HTTP POST, or not specify an attribute, which defaults to HTTP POST.</span></span>
  
    ```csharp
    [ServiceContract]  
    public interface IMusicService  
    {  
        //This operation uses a GET method.  
        [OperationContract]  
        [WebGet]  
        string LookUpArtist(string album);  
  
        //This operation will use a POST method.  
        [OperationContract]  
        [WebInvoke]  
        void AddAlbum(string user, string album);  
  
        //This operation will use POST method by default  
        //since nothing else is explicitly specified.  
        [OperationContract]  
        string[] GetAlbums(string user);  
  
        //Other operations omitted…  
  
    }  
    ```  
  
2. <span data-ttu-id="6d202-129">`IMusicService` を使用して、`MusicService` サービス コントラクトを実装します。</span><span class="sxs-lookup"><span data-stu-id="6d202-129">Implement the `IMusicService` service contract with a `MusicService`.</span></span>
  
    ```csharp
    public class MusicService : IMusicService  
    {  
        public void AddAlbum(string user, string album)  
        {  
            //Add implementation here.  
        }  
  
         //Other operations omitted…  
    }  
    ```  
  
3. <span data-ttu-id="6d202-130">アプリケーションで、.svc という拡張子を付けて新しい service ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="6d202-130">Create a new file named service with a .svc extension in the application.</span></span> <span data-ttu-id="6d202-131">このファイルを編集するには、サービスに適切な[ \@ServiceHost](../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md)ディレクティブ情報を追加します。</span><span class="sxs-lookup"><span data-stu-id="6d202-131">Edit this file by adding the appropriate [\@ServiceHost](../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) directive information for the service.</span></span> <span data-ttu-id="6d202-132">ASP.NET AJAX エンド<xref:System.ServiceModel.Activation.WebScriptServiceHostFactory>ポイントを自動的に構成するために、 [ \@ServiceHost](../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md)ディレクティブでを使用することを指定します。</span><span class="sxs-lookup"><span data-stu-id="6d202-132">Specify that the <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> is to be used in the [\@ServiceHost](../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) directive to automatically configure an ASP.NET AJAX endpoint.</span></span>  
  
    ```
    <%@ServiceHost   
        language=c#   
        Debug="true"   
        Service="Microsoft.Ajax.Samples.MusicService"  
        Factory=System.ServiceModel.Activation.WebScriptServiceHostFactory  
    %>  
    ```  
  
## <a name="to-call-the-service"></a><span data-ttu-id="6d202-133">サービスを呼び出すには</span><span class="sxs-lookup"><span data-stu-id="6d202-133">To call the service</span></span>  
  
1. <span data-ttu-id="6d202-134">ブラウザーを使用すると、クライアントのコードなしでサービスの GET 操作をテストできます。</span><span class="sxs-lookup"><span data-stu-id="6d202-134">You can test your service's GET operations without any client code, by using the browser.</span></span> <span data-ttu-id="6d202-135">たとえば、サービスが`http://example.com/service.svc`アドレスで構成されている場合、ブラウザーのアドレスバーに「」と入力`http://example.com/service.svc/LookUpArtist?album=SomeAlbum`すると、サービスが呼び出され、応答がダウンロードまたは表示されます。</span><span class="sxs-lookup"><span data-stu-id="6d202-135">For example, if your service is configured at the `http://example.com/service.svc` address, then typing `http://example.com/service.svc/LookUpArtist?album=SomeAlbum` into the browser address bar invokes the service and causes the response to be downloaded or displayed.</span></span>
  
2. <span data-ttu-id="6d202-136">GET 操作によるサービスは、他の ASP.NET AJAX サービスと同様に、サービス URL を ASP.NET AJAX Script Manager コントロールのスクリプト コレクションに入力することで使用できます。</span><span class="sxs-lookup"><span data-stu-id="6d202-136">You can use services with GET operations in the same way as any other ASP.NET AJAX services - by entering the service URL into the Scripts collection of the ASP.NET AJAX Script Manager control.</span></span> <span data-ttu-id="6d202-137">例については、「[基本的な AJAX サービス](../../../../docs/framework/wcf/samples/basic-ajax-service.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6d202-137">For an example, see the [Basic AJAX Service](../../../../docs/framework/wcf/samples/basic-ajax-service.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="6d202-138">関連項目</span><span class="sxs-lookup"><span data-stu-id="6d202-138">See also</span></span>

- [<span data-ttu-id="6d202-139">ASP.NET AJAX 用の WCF サービスの作成</span><span class="sxs-lookup"><span data-stu-id="6d202-139">Creating WCF Services for ASP.NET AJAX</span></span>](../../../../docs/framework/wcf/feature-details/creating-wcf-services-for-aspnet-ajax.md)
- [<span data-ttu-id="6d202-140">方法: AJAX 対応の ASP.NET Web サービスを WCF に移行する</span><span class="sxs-lookup"><span data-stu-id="6d202-140">How to: Migrate AJAX-Enabled ASP.NET Web Services to WCF</span></span>](../../../../docs/framework/wcf/feature-details/how-to-migrate-ajax-enabled-aspnet-web-services-to-wcf.md)
