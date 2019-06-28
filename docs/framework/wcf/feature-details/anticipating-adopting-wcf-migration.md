---
title: Windows Communication Foundation 導入の準備:将来の移行の簡略化
ms.date: 03/30/2017
ms.assetid: f49664d9-e9e0-425c-a259-93f0a569d01b
ms.openlocfilehash: 09bbb11c58992f0fabcb822f5f3d88fef273bea9
ms.sourcegitcommit: 9b1ac36b6c80176fd4e20eb5bfcbd9d56c3264cf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/28/2019
ms.locfileid: "67425284"
---
# <a name="anticipating-adopting-the-windows-communication-foundation-easing-future-migration"></a><span data-ttu-id="27caf-102">Windows Communication Foundation 導入の準備:将来の移行の簡略化</span><span class="sxs-lookup"><span data-stu-id="27caf-102">Anticipating Adopting the Windows Communication Foundation: Easing Future Migration</span></span>
<span data-ttu-id="27caf-103">新しい ASP.NET アプリケーションの WCF への簡単に将来の移行のために、次の推奨事項と同様に、前の推奨事項に従います。</span><span class="sxs-lookup"><span data-stu-id="27caf-103">To ensure an easier future migration of new ASP.NET applications to WCF, follow the preceding recommendations as well as the following recommendations.</span></span>  
  
## <a name="protocols"></a><span data-ttu-id="27caf-104">プロトコル</span><span class="sxs-lookup"><span data-stu-id="27caf-104">Protocols</span></span>  
 <span data-ttu-id="27caf-105">ASP.NET 2.0 の SOAP 1.2 サポートを無効にします。</span><span class="sxs-lookup"><span data-stu-id="27caf-105">Disable ASP.NET 2.0’s support for SOAP 1.2:</span></span>  
  
```xml  
<configuration>  
     <system.web>  
      <webServices >  
          <protocols>  
           <remove name="HttpSoap12"/>  
          </protocols>    
      </webServices>  
     </system.web>   
</configuration>  
```  
  
 <span data-ttu-id="27caf-106">WCF メッセージは SOAP 1.1 と SOAP 1.2 などのさまざまなプロトコルに準拠している、さまざまなエンドポイントを使用して、移動を必要とするため、これはお勧めします。</span><span class="sxs-lookup"><span data-stu-id="27caf-106">Doing so is advisable because WCF requires messages conforming to different protocols, like SOAP 1.1 and SOAP 1.2, to go by using different endpoints.</span></span> <span data-ttu-id="27caf-107">サービスが SOAP 1.1 と SOAP 1.2 では、することはできませんが、既定の構成の両方をサポートするために構成されている ASP.NET 2.0 Web 前方参照を確実になる元のアドレスにある単一の WCF エンドポイントに移行する場合はすべて、ASP.NET Web の互換性があります。サービスの既存のクライアント。</span><span class="sxs-lookup"><span data-stu-id="27caf-107">If an ASP.NET 2.0 Web service is configured to support both SOAP 1.1 and SOAP 1.2, which is the default configuration, then it cannot be migrated forward to a single WCF endpoint at the original address that would be certainly be compatible with all of the ASP.NET Web service’s existing clients.</span></span> <span data-ttu-id="27caf-108">また、SOAP 1.1 ではなく 1.2 を選択すると、サービスの利用者がさらに厳しく制限されます。</span><span class="sxs-lookup"><span data-stu-id="27caf-108">Also choosing SOAP 1.2 instead of 1.1 will more severely restrict the clientele of the service.</span></span>  
  
## <a name="service-development"></a><span data-ttu-id="27caf-109">サービスの開発</span><span class="sxs-lookup"><span data-stu-id="27caf-109">Service Development</span></span>  
 <span data-ttu-id="27caf-110">WCF では、適用することでサービス コントラクトを定義することにより、<xref:System.ServiceModel.ServiceContractAttribute>インターフェイスまたはクラスのいずれか。</span><span class="sxs-lookup"><span data-stu-id="27caf-110">WCF allows you to define service contracts by applying the <xref:System.ServiceModel.ServiceContractAttribute> either to interfaces or to classes.</span></span> <span data-ttu-id="27caf-111">この属性は、クラスではなくインターフェイスに適用することをお勧めします。これにより、任意の数のクラスでさまざまに実装できるコントラクト定義が作成されます。</span><span class="sxs-lookup"><span data-stu-id="27caf-111">It is recommended to apply the attribute to an interface rather than to a class, because doing so creates a definition of a contract that can be variously implemented by any number of classes.</span></span> <span data-ttu-id="27caf-112">ASP.NET 2.0 では、<xref:System.Web.Services.WebService> 属性をクラスだけでなくインターフェイスに適用することもできます。</span><span class="sxs-lookup"><span data-stu-id="27caf-112">ASP.NET 2.0 supports the option of applying the <xref:System.Web.Services.WebService> attribute to interfaces as well as classes.</span></span> <span data-ttu-id="27caf-113">ただし、既に説明したように ASP.NET 2.0 には不具合があり、<xref:System.Web.Services.WebService> 属性をクラスではなくインターフェイスに適用した場合、この属性の名前空間パラメーターが有効化されません。</span><span class="sxs-lookup"><span data-stu-id="27caf-113">However, as mentioned already, there is a defect in ASP.NET 2.0, by which the Namespace parameter of the <xref:System.Web.Services.WebService> attribute has no effect when that attribute is applied to an interface rather than a class.</span></span> <span data-ttu-id="27caf-114">一般に、既定値からのサービスの名前空間を変更することをお勧めであるため`http://tempuri.org`の Namespace パラメーターを使用して、<xref:System.Web.Services.WebService>を適用して ASP.NET Web サービスを定義する 1 つ続行、属性、 <xref:System.ServiceModel.ServiceContractAttribute>インターフェイスまたはクラスのいずれかの属性です。</span><span class="sxs-lookup"><span data-stu-id="27caf-114">Since it is generally advisable to modify the namespace of a service from the default value, `http://tempuri.org`, using the Namespace parameter of the <xref:System.Web.Services.WebService> attribute, one should continue defining ASP.NET Web Services by applying the <xref:System.ServiceModel.ServiceContractAttribute> attribute either to interfaces or to classes.</span></span>  
  
- <span data-ttu-id="27caf-115">これらのインターフェイスを定義するメソッドに含めるコードは、できるだけ少なくします。</span><span class="sxs-lookup"><span data-stu-id="27caf-115">Have as little code as possible in the methods by which those interfaces are defined.</span></span> <span data-ttu-id="27caf-116">これらのメソッドの作業を他のクラスに委任します。</span><span class="sxs-lookup"><span data-stu-id="27caf-116">Have them delegate their work to other classes.</span></span> <span data-ttu-id="27caf-117">新しい WCF サービスの種類にし、それらのクラスには、次の実質的な仕事委任も可能性があります。</span><span class="sxs-lookup"><span data-stu-id="27caf-117">New WCF service types could then also delegate their substantive work to those classes.</span></span>  
  
- <span data-ttu-id="27caf-118">`MessageName` の <xref:System.Web.Services.WebMethodAttribute> パラメーターを使用して、サービスの動作の明示的な名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="27caf-118">Provide explicit names for the operations of a service using the `MessageName` parameter of the <xref:System.Web.Services.WebMethodAttribute>.</span></span>  
  
    ```csharp  
    [WebMethod(MessageName="ExplicitName")]  
    string Echo(string input);  
    ```  
  
     <span data-ttu-id="27caf-119">これは、ASP.NET での操作の既定の名前は、WCF によって提供される既定の名前と異なるため、重要です。</span><span class="sxs-lookup"><span data-stu-id="27caf-119">Doing so is important, because the default names for operations in ASP.NET are different from the default names supplied by WCF.</span></span> <span data-ttu-id="27caf-120">明示的な名前を指定することで、既定の名前への依存を避けることができます。</span><span class="sxs-lookup"><span data-stu-id="27caf-120">By providing explicit names, you avoid relying on the default ones.</span></span>  
  
- <span data-ttu-id="27caf-121">WCF がポリモーフィックなメソッドを実装する操作をサポートしていないためを多様メソッドは、ASP.NET Web サービスの操作を実装してください。</span><span class="sxs-lookup"><span data-stu-id="27caf-121">Do not implement ASP.NET Web service operations with polymorphic methods, because WCF does not support implementing operations with polymorphic methods.</span></span>  
  
- <span data-ttu-id="27caf-122"><xref:System.Web.Services.Protocols.SoapDocumentMethodAttribute> を使用して、HTTP 要求をメソッドにルーティングする SOAPAction HTTP ヘッダーの明示的な値を指定します。</span><span class="sxs-lookup"><span data-stu-id="27caf-122">Use the <xref:System.Web.Services.Protocols.SoapDocumentMethodAttribute> to provide explicit values for the SOAPAction HTTP headers by which HTTP requests will be routed to methods.</span></span>  
  
    ```csharp  
    [WebMethod]  
    [SoapDocumentMethod(RequestElementName="ExplicitAction")]  
    string Echo(string input);  
    ```  
  
     <span data-ttu-id="27caf-123">このアプローチには、ASP.NET および WCF が同じで使用する SOAPAction 値を既定値に依存することは回避します。</span><span class="sxs-lookup"><span data-stu-id="27caf-123">Taking this approach will circumvent having to rely on the default SOAPAction values used by ASP.NET and WCF being the same.</span></span>  
  
- <span data-ttu-id="27caf-124">SOAP 拡張機能は使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="27caf-124">Avoid using SOAP extensions.</span></span> <span data-ttu-id="27caf-125">SOAP 拡張機能が必要な場合、検討している対象の目的は、WCF によって既に提供されている機能であるかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="27caf-125">If SOAP extensions are required, then determine whether the purpose for which they are being considered is a feature that is already provided by WCF.</span></span> <span data-ttu-id="27caf-126">そのような場合は実際に場合、WCF を導入しないすぐを再確認します。</span><span class="sxs-lookup"><span data-stu-id="27caf-126">If that is indeed the case, then reconsider the choice to not adopt WCF right away.</span></span>  
  
## <a name="state-management"></a><span data-ttu-id="27caf-127">状態管理</span><span class="sxs-lookup"><span data-stu-id="27caf-127">State Management</span></span>  
 <span data-ttu-id="27caf-128">サービスで状態を維持する必要がないようにします。</span><span class="sxs-lookup"><span data-stu-id="27caf-128">Avoid having to maintain state in services.</span></span> <span data-ttu-id="27caf-129">だけでなく、アプリケーションのスケーラビリティを侵害する傾向がある状態を維持するが、WCF は、ASP.NET 互換モードで ASP.NET のメカニズムをサポートして、ASP.NET および WCF の状態管理メカニズムは非常に異なる。</span><span class="sxs-lookup"><span data-stu-id="27caf-129">Not only does maintaining state tend to compromise the scalability of an application, but the state management mechanisms of ASP.NET and WCF are very different, although WCF does support the ASP.NET mechanisms in ASP.NET compatibility mode.</span></span>  
  
## <a name="exception-handling"></a><span data-ttu-id="27caf-130">例外処理</span><span class="sxs-lookup"><span data-stu-id="27caf-130">Exception Handling</span></span>  
 <span data-ttu-id="27caf-131">サービスで送受信するデータ型の構造を設計するときは、クライアントに伝達する必要があり、サービス内で発生する可能性のあるさまざまな種類の例外を表現する構造も設計します。</span><span class="sxs-lookup"><span data-stu-id="27caf-131">In designing the structures of the data types to be sent and received by a service, also design structures to represent the various types of exceptions that might occur within a service that one might wish to convey to a client.</span></span>  
  
```csharp  
[Serializable]  
[XmlRoot(Namespace="ExplicitNamespace", IsNullable=true)]  
public partial class AnticipatedException 
{ 
    private string anticipatedExceptionInformationField;  

    public string AnticipatedExceptionInformation 
    {  
        get {   
            return this.anticipatedExceptionInformationField;  
        }  
        set {  
            this.anticipatedExceptionInformationField = value;  
        }  
    }  
}  
```  
  
 <span data-ttu-id="27caf-132">これらのクラスには、自分自身を XML にシリアル化する機能を与えます。</span><span class="sxs-lookup"><span data-stu-id="27caf-132">Give such classes the ability to serialize themselves to XML:</span></span>  
  
```csharp  
public XmlNode ToXML()  
{  
     XmlSerializer serializer = new XmlSerializer(  
      typeof(AnticipatedException));  
     MemoryStream memoryStream = new MemoryStream();  
     XmlTextWriter writer = new XmlTextWriter(  
     memoryStream, UnicodeEncoding.UTF8);  
     serializer.Serialize(writer, this);  
     XmlDocument document = new XmlDocument();  
     document.LoadXml(new string(  
     UnicodeEncoding.UTF8.GetChars(  
     memoryStream.GetBuffer())).Trim());  
    return document.DocumentElement;  
}  
```  
  
 <span data-ttu-id="27caf-133">これでこのクラスを使用して、明示的にスローされた <xref:System.Web.Services.Protocols.SoapException> インスタンスの詳細を指定できます。</span><span class="sxs-lookup"><span data-stu-id="27caf-133">The classes can then be used to provide the details for explicitly thrown <xref:System.Web.Services.Protocols.SoapException> instances:</span></span>  
  
```csharp  
AnticipatedException exception = new AnticipatedException();  
exception.AnticipatedExceptionInformation = "…";  
throw new SoapException(  
     "Fault occurred",  
     SoapException.ClientFaultCode,  
     Context.Request.Url.AbsoluteUri,  
     exception.ToXML());  
```  
  
 <span data-ttu-id="27caf-134">これらの例外クラスが、WCF で簡単に再利用が可能<xref:System.ServiceModel.FaultException%601>新しいをスローするクラス `FaultException<AnticipatedException>(anticipatedException);`</span><span class="sxs-lookup"><span data-stu-id="27caf-134">These exception classes will be readily reusable with the WCF <xref:System.ServiceModel.FaultException%601> class to throw a new `FaultException<AnticipatedException>(anticipatedException);`</span></span>  
  
## <a name="security"></a><span data-ttu-id="27caf-135">セキュリティ</span><span class="sxs-lookup"><span data-stu-id="27caf-135">Security</span></span>  
 <span data-ttu-id="27caf-136">セキュリティに関する推奨事項を次にいくつか示します。</span><span class="sxs-lookup"><span data-stu-id="27caf-136">The following are some security recommendations.</span></span>  
  
- <span data-ttu-id="27caf-137">回避としてそれらを使用して ASP.NET 2.0 のプロファイルを使用して使用が制限 ASP.NET 統合モードの場合は、サービスが WCF に移行されました。</span><span class="sxs-lookup"><span data-stu-id="27caf-137">Avoid using ASP.NET 2.0 Profiles, as using them would restrict the use of ASP.NET Integration Mode if the service was migrated to WCF.</span></span>  
  
- <span data-ttu-id="27caf-138">インターネット インフォメーション サービス (IIS) を使用して Acl をサポートする ASP.NET Web サービスとしてのサービスへのアクセスを制御する Acl を使用しないように、WCF はありません — をホストするため、ASP.NET Web サービスが IIS に依存し、WCF とは限りませんが、IIS でホストするためです。</span><span class="sxs-lookup"><span data-stu-id="27caf-138">Avoid using ACLs to control access to services, as ASP.NET Web services supports ACLs using Internet Information Services (IIS), WCF does not—because ASP.NET Web services depend on IIS for hosting, and WCF does not necessarily have to be hosted in IIS.</span></span>  
  
- <span data-ttu-id="27caf-139">サービスのリソースへのアクセスを承認するには、ASP.NET 2.0 ロール プロバイダーの使用を検討してください。</span><span class="sxs-lookup"><span data-stu-id="27caf-139">Do consider using ASP.NET 2.0 Role Providers for authorizing access to the resources of a service.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27caf-140">関連項目</span><span class="sxs-lookup"><span data-stu-id="27caf-140">See also</span></span>

- [<span data-ttu-id="27caf-141">Windows Communication Foundation の採用を予測します。将来的な統合を簡略化</span><span class="sxs-lookup"><span data-stu-id="27caf-141">Anticipating Adopting the Windows Communication Foundation: Easing Future Integration</span></span>](../../../../docs/framework/wcf/feature-details/anticipating-adopting-the-wcf-easing-future-integration.md)
