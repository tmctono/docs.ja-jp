---
title: 'Windows Communication Foundation の採用: 将来の移行の簡略化'
ms.date: 03/30/2017
ms.assetid: f49664d9-e9e0-425c-a259-93f0a569d01b
ms.openlocfilehash: 995bdaaaba96bf8697ea75c1f1a17fa8e51ec2d5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79185471"
---
# <a name="anticipating-adopting-the-windows-communication-foundation-easing-future-migration"></a><span data-ttu-id="307b5-102">Windows Communication Foundation の採用: 将来の移行の簡略化</span><span class="sxs-lookup"><span data-stu-id="307b5-102">Anticipating Adopting the Windows Communication Foundation: Easing Future Migration</span></span>
<span data-ttu-id="307b5-103">新しいASP.NET アプリケーションを WCF に移行しやすくするには、前述の推奨事項と次の推奨事項に従います。</span><span class="sxs-lookup"><span data-stu-id="307b5-103">To ensure an easier future migration of new ASP.NET applications to WCF, follow the preceding recommendations as well as the following recommendations.</span></span>  
  
## <a name="protocols"></a><span data-ttu-id="307b5-104">プロトコル</span><span class="sxs-lookup"><span data-stu-id="307b5-104">Protocols</span></span>  
 <span data-ttu-id="307b5-105">ASP.NET 2.0 の SOAP 1.2 サポートを無効にします。</span><span class="sxs-lookup"><span data-stu-id="307b5-105">Disable ASP.NET 2.0’s support for SOAP 1.2:</span></span>  
  
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
  
 <span data-ttu-id="307b5-106">WCF では、SOAP 1.1 や SOAP 1.2 などの異なるプロトコルに準拠したメッセージを別のエンドポイントを使用して実行する必要があるため、この方法をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="307b5-106">Doing so is advisable because WCF requires messages conforming to different protocols, like SOAP 1.1 and SOAP 1.2, to go by using different endpoints.</span></span> <span data-ttu-id="307b5-107">ASP.NET 2.0 Web サービスが SOAP 1.1 と SOAP 1.2 の両方をサポートするように構成されている場合 (デフォルトの構成) は、元 ASP.NETのアドレスにある単一の WCF エンドポイントに移行できません。サービスの既存のクライアント。</span><span class="sxs-lookup"><span data-stu-id="307b5-107">If an ASP.NET 2.0 Web service is configured to support both SOAP 1.1 and SOAP 1.2, which is the default configuration, then it cannot be migrated forward to a single WCF endpoint at the original address that would be certainly be compatible with all of the ASP.NET Web service’s existing clients.</span></span> <span data-ttu-id="307b5-108">また、SOAP 1.1 ではなく 1.2 を選択すると、サービスの利用者がさらに厳しく制限されます。</span><span class="sxs-lookup"><span data-stu-id="307b5-108">Also choosing SOAP 1.2 instead of 1.1 will more severely restrict the clientele of the service.</span></span>  
  
## <a name="service-development"></a><span data-ttu-id="307b5-109">サービスの開発</span><span class="sxs-lookup"><span data-stu-id="307b5-109">Service Development</span></span>  
 <span data-ttu-id="307b5-110">WCF では、インターフェイスまたはクラス<xref:System.ServiceModel.ServiceContractAttribute>のいずれかに適用してサービス コントラクトを定義できます。</span><span class="sxs-lookup"><span data-stu-id="307b5-110">WCF allows you to define service contracts by applying the <xref:System.ServiceModel.ServiceContractAttribute> either to interfaces or to classes.</span></span> <span data-ttu-id="307b5-111">この属性は、クラスではなくインターフェイスに適用することをお勧めします。これにより、任意の数のクラスでさまざまに実装できるコントラクト定義が作成されます。</span><span class="sxs-lookup"><span data-stu-id="307b5-111">It is recommended to apply the attribute to an interface rather than to a class, because doing so creates a definition of a contract that can be variously implemented by any number of classes.</span></span> <span data-ttu-id="307b5-112">ASP.NET 2.0 では、<xref:System.Web.Services.WebService> 属性をクラスだけでなくインターフェイスに適用することもできます。</span><span class="sxs-lookup"><span data-stu-id="307b5-112">ASP.NET 2.0 supports the option of applying the <xref:System.Web.Services.WebService> attribute to interfaces as well as classes.</span></span> <span data-ttu-id="307b5-113">ただし、既に説明したように ASP.NET 2.0 には不具合があり、<xref:System.Web.Services.WebService> 属性をクラスではなくインターフェイスに適用した場合、この属性の名前空間パラメーターが有効化されません。</span><span class="sxs-lookup"><span data-stu-id="307b5-113">However, as mentioned already, there is a defect in ASP.NET 2.0, by which the Namespace parameter of the <xref:System.Web.Services.WebService> attribute has no effect when that attribute is applied to an interface rather than a class.</span></span> <span data-ttu-id="307b5-114">通常は、属性の Namespace パラメーターを使用して、`http://tempuri.org`サービス ASP.NET<xref:System.Web.Services.WebService><xref:System.ServiceModel.ServiceContractAttribute>の名前空間を既定値から変更することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="307b5-114">Since it is generally advisable to modify the namespace of a service from the default value, `http://tempuri.org`, using the Namespace parameter of the <xref:System.Web.Services.WebService> attribute, one should continue defining ASP.NET Web Services by applying the <xref:System.ServiceModel.ServiceContractAttribute> attribute either to interfaces or to classes.</span></span>  
  
- <span data-ttu-id="307b5-115">これらのインターフェイスを定義するメソッドに含めるコードは、できるだけ少なくします。</span><span class="sxs-lookup"><span data-stu-id="307b5-115">Have as little code as possible in the methods by which those interfaces are defined.</span></span> <span data-ttu-id="307b5-116">これらのメソッドの作業を他のクラスに委任します。</span><span class="sxs-lookup"><span data-stu-id="307b5-116">Have them delegate their work to other classes.</span></span> <span data-ttu-id="307b5-117">新しい WCF サービスの種類は、これらのクラスにそれらの実質的な作業をデリゲートすることもできます。</span><span class="sxs-lookup"><span data-stu-id="307b5-117">New WCF service types could then also delegate their substantive work to those classes.</span></span>  
  
- <span data-ttu-id="307b5-118">`MessageName` の <xref:System.Web.Services.WebMethodAttribute> パラメーターを使用して、サービスの動作の明示的な名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="307b5-118">Provide explicit names for the operations of a service using the `MessageName` parameter of the <xref:System.Web.Services.WebMethodAttribute>.</span></span>  
  
    ```csharp  
    [WebMethod(MessageName="ExplicitName")]  
    string Echo(string input);  
    ```  
  
     <span data-ttu-id="307b5-119">この操作は重要です。なぜなら、ASP.NETの操作の既定の名前は WCF によって提供される既定の名前とは異なるためです。</span><span class="sxs-lookup"><span data-stu-id="307b5-119">Doing so is important, because the default names for operations in ASP.NET are different from the default names supplied by WCF.</span></span> <span data-ttu-id="307b5-120">明示的な名前を指定することで、既定の名前への依存を避けることができます。</span><span class="sxs-lookup"><span data-stu-id="307b5-120">By providing explicit names, you avoid relying on the default ones.</span></span>  
  
- <span data-ttu-id="307b5-121">WCF ではポリモーフィック メソッドを使用した操作の実装はサポートされていないため、ポリモーフィック メソッドを使用して ASP.NET Web サービス操作を実装しないでください。</span><span class="sxs-lookup"><span data-stu-id="307b5-121">Do not implement ASP.NET Web service operations with polymorphic methods, because WCF does not support implementing operations with polymorphic methods.</span></span>  
  
- <span data-ttu-id="307b5-122"><xref:System.Web.Services.Protocols.SoapDocumentMethodAttribute> を使用して、HTTP 要求をメソッドにルーティングする SOAPAction HTTP ヘッダーの明示的な値を指定します。</span><span class="sxs-lookup"><span data-stu-id="307b5-122">Use the <xref:System.Web.Services.Protocols.SoapDocumentMethodAttribute> to provide explicit values for the SOAPAction HTTP headers by which HTTP requests will be routed to methods.</span></span>  
  
    ```csharp  
    [WebMethod]  
    [SoapDocumentMethod(RequestElementName="ExplicitAction")]  
    string Echo(string input);  
    ```  
  
     <span data-ttu-id="307b5-123">この方法を使用すると、ASP.NETと WCF が同じで使用する既定の SOAPAction 値に依存する必要が回避されます。</span><span class="sxs-lookup"><span data-stu-id="307b5-123">Taking this approach will circumvent having to rely on the default SOAPAction values used by ASP.NET and WCF being the same.</span></span>  
  
- <span data-ttu-id="307b5-124">SOAP 拡張機能は使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="307b5-124">Avoid using SOAP extensions.</span></span> <span data-ttu-id="307b5-125">SOAP 拡張機能が必要な場合は、それらが検討される目的が、既に WCF によって提供されている機能であるかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="307b5-125">If SOAP extensions are required, then determine whether the purpose for which they are being considered is a feature that is already provided by WCF.</span></span> <span data-ttu-id="307b5-126">実際にそうである場合は、すぐに WCF を採用しないという選択を再検討してください。</span><span class="sxs-lookup"><span data-stu-id="307b5-126">If that is indeed the case, then reconsider the choice to not adopt WCF right away.</span></span>  
  
## <a name="state-management"></a><span data-ttu-id="307b5-127">状態管理</span><span class="sxs-lookup"><span data-stu-id="307b5-127">State Management</span></span>  
 <span data-ttu-id="307b5-128">サービスで状態を維持する必要がないようにします。</span><span class="sxs-lookup"><span data-stu-id="307b5-128">Avoid having to maintain state in services.</span></span> <span data-ttu-id="307b5-129">状態の維持はアプリケーションのスケーラビリティを損なう傾向があるだけでなく、wcf wcf では互換性モードでASP.NETメカニズムをサポートしていますが、ASP.NETと WCF の状態管理メカニズムは大 ASP.NETきく異なります。</span><span class="sxs-lookup"><span data-stu-id="307b5-129">Not only does maintaining state tend to compromise the scalability of an application, but the state management mechanisms of ASP.NET and WCF are very different, although WCF does support the ASP.NET mechanisms in ASP.NET compatibility mode.</span></span>  
  
## <a name="exception-handling"></a><span data-ttu-id="307b5-130">例外処理</span><span class="sxs-lookup"><span data-stu-id="307b5-130">Exception Handling</span></span>  
 <span data-ttu-id="307b5-131">サービスで送受信するデータ型の構造を設計するときは、クライアントに伝達する必要があり、サービス内で発生する可能性のあるさまざまな種類の例外を表現する構造も設計します。</span><span class="sxs-lookup"><span data-stu-id="307b5-131">In designing the structures of the data types to be sent and received by a service, also design structures to represent the various types of exceptions that might occur within a service that one might wish to convey to a client.</span></span>  
  
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
  
 <span data-ttu-id="307b5-132">これらのクラスには、自分自身を XML にシリアル化する機能を与えます。</span><span class="sxs-lookup"><span data-stu-id="307b5-132">Give such classes the ability to serialize themselves to XML:</span></span>  
  
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
  
 <span data-ttu-id="307b5-133">これでこのクラスを使用して、明示的にスローされた <xref:System.Web.Services.Protocols.SoapException> インスタンスの詳細を指定できます。</span><span class="sxs-lookup"><span data-stu-id="307b5-133">The classes can then be used to provide the details for explicitly thrown <xref:System.Web.Services.Protocols.SoapException> instances:</span></span>  
  
```csharp  
AnticipatedException exception = new AnticipatedException();  
exception.AnticipatedExceptionInformation = "…";  
throw new SoapException(  
     "Fault occurred",  
     SoapException.ClientFaultCode,  
     Context.Request.Url.AbsoluteUri,  
     exception.ToXML());  
```  
  
 <span data-ttu-id="307b5-134">これらの例外クラスは、WCF<xref:System.ServiceModel.FaultException%601>クラスを使用して簡単に再利用可能になり、新しい`FaultException<AnticipatedException>(anticipatedException);`</span><span class="sxs-lookup"><span data-stu-id="307b5-134">These exception classes will be readily reusable with the WCF <xref:System.ServiceModel.FaultException%601> class to throw a new `FaultException<AnticipatedException>(anticipatedException);`</span></span>  
  
## <a name="security"></a><span data-ttu-id="307b5-135">Security</span><span class="sxs-lookup"><span data-stu-id="307b5-135">Security</span></span>  
 <span data-ttu-id="307b5-136">セキュリティに関する推奨事項を次にいくつか示します。</span><span class="sxs-lookup"><span data-stu-id="307b5-136">The following are some security recommendations.</span></span>  
  
- <span data-ttu-id="307b5-137">サービスが WCF に移行された場合、ASP.NET統合モードの使用を制限するので、ASP.NET 2.0 プロファイルの使用を避けてください。</span><span class="sxs-lookup"><span data-stu-id="307b5-137">Avoid using ASP.NET 2.0 Profiles, as using them would restrict the use of ASP.NET Integration Mode if the service was migrated to WCF.</span></span>  
  
- <span data-ttu-id="307b5-138">Web サービスがインターネット インフォメーション サービス (IIS) を使用して ACL をサポートASP.NET、WCF ではホスト用の IIS ASP.NET に依存しているため、サービスへのアクセスを制御するために ACL を使用することは避けてください。</span><span class="sxs-lookup"><span data-stu-id="307b5-138">Avoid using ACLs to control access to services, as ASP.NET Web services supports ACLs using Internet Information Services (IIS), WCF does not—because ASP.NET Web services depend on IIS for hosting, and WCF does not necessarily have to be hosted in IIS.</span></span>  
  
- <span data-ttu-id="307b5-139">サービスのリソースへのアクセスを承認するには、ASP.NET 2.0 ロール プロバイダーの使用を検討してください。</span><span class="sxs-lookup"><span data-stu-id="307b5-139">Do consider using ASP.NET 2.0 Role Providers for authorizing access to the resources of a service.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="307b5-140">関連項目</span><span class="sxs-lookup"><span data-stu-id="307b5-140">See also</span></span>

- [<span data-ttu-id="307b5-141">Windows Communication Foundation 導入の準備 : 将来的な統合の容易化</span><span class="sxs-lookup"><span data-stu-id="307b5-141">Anticipating Adopting the Windows Communication Foundation: Easing Future Integration</span></span>](../../../../docs/framework/wcf/feature-details/anticipating-adopting-the-wcf-easing-future-integration.md)
