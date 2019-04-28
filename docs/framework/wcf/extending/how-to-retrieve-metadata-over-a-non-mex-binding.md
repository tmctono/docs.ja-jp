---
title: '方法: MEX 以外のバインディングを介してメタデータを取得する'
ms.date: 03/30/2017
ms.assetid: 2292e124-81b2-4317-b881-ce9c1ec66ecb
ms.openlocfilehash: 4a127e3e2283050018705c85606bd7c03c36de8b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61766780"
---
# <a name="how-to-retrieve-metadata-over-a-non-mex-binding"></a><span data-ttu-id="cfeb7-102">方法: MEX 以外のバインディングを介してメタデータを取得する</span><span class="sxs-lookup"><span data-stu-id="cfeb7-102">How to: Retrieve Metadata Over a non-MEX Binding</span></span>
<span data-ttu-id="cfeb7-103">ここでは、MEX 以外のバインディングを介して MEX エンドポイントからメタデータを取得する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="cfeb7-103">This topic describes how to retrieve metadata from a MEX endpoint over a non-MEX binding.</span></span> <span data-ttu-id="cfeb7-104">このサンプルでコードがに基づいて、[メタデータ エンドポイントのセキュリティで保護されたカスタム](../../../../docs/framework/wcf/samples/custom-secure-metadata-endpoint.md)サンプル。</span><span class="sxs-lookup"><span data-stu-id="cfeb7-104">The code in this sample is based on the [Custom Secure Metadata Endpoint](../../../../docs/framework/wcf/samples/custom-secure-metadata-endpoint.md) sample.</span></span>  
  
### <a name="to-retrieve-metadata-over-a-non-mex-binding"></a><span data-ttu-id="cfeb7-105">MEX 以外のバインディングを介してメタデータを取得するには</span><span class="sxs-lookup"><span data-stu-id="cfeb7-105">To retrieve metadata over a non-MEX binding</span></span>  
  
1. <span data-ttu-id="cfeb7-106">MEX エンドポイントで使用されているバインディングを特定します。</span><span class="sxs-lookup"><span data-stu-id="cfeb7-106">Determine the binding used by the MEX endpoint.</span></span> <span data-ttu-id="cfeb7-107">Windows Communication Foundation (WCF) サービスの場合に、サービスの構成ファイルにアクセスすることで MEX バインディングを指定できます。</span><span class="sxs-lookup"><span data-stu-id="cfeb7-107">For Windows Communication Foundation (WCF) services, you can determine the MEX binding by accessing the service's configuration file.</span></span> <span data-ttu-id="cfeb7-108">この場合、MEX バインディングは、次のサービス構成で定義されています。</span><span class="sxs-lookup"><span data-stu-id="cfeb7-108">In this case, the MEX binding is defined in the following service configuration.</span></span>  
  
    ```xml  
    <services>  
        <service name="Microsoft.ServiceModel.Samples.CalculatorService"  
                behaviorConfiguration="CalculatorServiceBehavior">  
         <!-- Use the base address provided by the host. -->  
         <endpoint address=""  
           binding="wsHttpBinding"  
           bindingConfiguration="Binding2"  
           contract="Microsoft.ServiceModel.Samples.ICalculator" />  
         <endpoint address="mex"  
           binding="wsHttpBinding"  
           bindingConfiguration="Binding1"  
           contract="IMetadataExchange" />  
         </service>  
     </services>  
     <bindings>  
       <wsHttpBinding>  
         <binding name="Binding1">  
           <security mode="Message">  
             <message clientCredentialType="Certificate" />  
           </security>  
         </binding>  
         <binding name="Binding2">  
           <reliableSession inactivityTimeout="00:01:00" enabled="true" />  
           <security mode="Message">  
             <message clientCredentialType="Certificate" />  
           </security>  
         </binding>  
       </wsHttpBinding>  
     </bindings>  
    ```  
  
2. <span data-ttu-id="cfeb7-109">クライアント構成ファイルで、同じカスタム バインドを構成します。</span><span class="sxs-lookup"><span data-stu-id="cfeb7-109">In the client configuration file, configure the same custom binding.</span></span> <span data-ttu-id="cfeb7-110">ここでクライアントは `clientCredentials` 動作も定義して、MEX エンドポイントからメタデータを要求するときに、サービスに対する認証で使用する証明書を指定します。</span><span class="sxs-lookup"><span data-stu-id="cfeb7-110">Here the client also defines a `clientCredentials` behavior to provide a certificate to use to authenticate to the service when requesting metadata from the MEX endpoint.</span></span> <span data-ttu-id="cfeb7-111">カスタム バインドを介してメタデータを要求するときに Svcutil.exe を使用する場合は、Svcutil.exe の構成ファイル (Svcutil.exe.config) に MEX エンドポイント構成を追加する必要があります。また、エンドポイント構成の名前が、次のコードに示すように、MEX エンドポイントのアドレスの URI スキームと一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cfeb7-111">When using Svcutil.exe to request metadata over a custom binding, you should add the MEX endpoint configuration to the configuration file for Svcutil.exe (Svcutil.exe.config), and the name of the endpoint configuration should match the URI scheme of the address of the MEX endpoint, as shown in the following code.</span></span>  
  
    ```xml  
    <system.serviceModel>  
      <client>  
        <endpoint name="http"  
                  binding="wsHttpBinding"  
                  bindingConfiguration="Binding1"  
                  behaviorConfiguration="ClientCertificateBehavior"  
                  contract="IMetadataExchange" />  
      </client>  
      <bindings>  
        <wsHttpBinding>  
          <binding name="Binding1">  
            <security mode="Message">  
              <message clientCredentialType="Certificate"/>  
            </security>  
          </binding>  
        </wsHttpBinding>  
      </bindings>  
      <behaviors>  
        <endpointBehaviors>  
          <behavior name="ClientCertificateBehavior">  
            <clientCredentials>  
              <clientCertificate findValue="client.com" storeLocation="CurrentUser" storeName="My" x509FindType="FindBySubjectName" />  
              <serviceCertificate>  
                <authentication certificateValidationMode="PeerOrChainTrust" />  
              </serviceCertificate>  
            </clientCredentials>  
          </behavior>  
        </endpointBehaviors>  
      </behaviors>    
    </system.serviceModel>  
    ```  
  
3. <span data-ttu-id="cfeb7-112">`MetadataExchangeClient` を作成して `GetMetadata` を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="cfeb7-112">Create a `MetadataExchangeClient` and call `GetMetadata`.</span></span> <span data-ttu-id="cfeb7-113">これを行うには、次の例に示すように、構成でカスタム バインドを指定する方法と、コードでカスタム バインドを指定する方法の 2 つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="cfeb7-113">There are two ways to do this: you can specify the custom binding in configuration, or you can specify the custom binding in code, as shown in the following example.</span></span>  
  
    ```  
    // The custom binding is specified in configuration.  
    EndpointAddress mexAddress = new EndpointAddress("http://localhost:8000/ServiceModelSamples/Service/mex");  
  
    MetadataExchangeClient mexClient = new MetadataExchangeClient("http");  
    mexClient.ResolveMetadataReferences = true;  
    MetadataSet mexSet = mexClient.GetMetadata(mexAddress);  
  
    // The custom binding is specified in code.  
    // Specify the Metadata Exchange binding and its security mode.  
    WSHttpBinding mexBinding = new WSHttpBinding(SecurityMode.Message);  
    mexBinding.Security.Message.ClientCredentialType = MessageCredentialType.Certificate;  
  
    // Create a MetadataExchangeClient and set the certificate details.  
    MetadataExchangeClient mexClient = new MetadataExchangeClient(mexBinding);  
    mexClient.SoapCredentials.ClientCertificate.SetCertificate(  
        StoreLocation.CurrentUser, StoreName.My,  
        X509FindType.FindBySubjectName, "client.com");  
    mexClient.SoapCredentials.ServiceCertificate.Authentication.  
        CertificateValidationMode =  
        X509CertificateValidationMode.PeerOrChainTrust;  
    mexClient.SoapCredentials.ServiceCertificate.SetDefaultCertificate(  
        StoreLocation.CurrentUser, StoreName.TrustedPeople,  
        X509FindType.FindBySubjectName, "localhost");  
    MetadataExchangeClient mexClient2 = new MetadataExchangeClient(customBinding);  
    mexClient2.ResolveMetadataReferences = true;  
    MetadataSet mexSet2 = mexClient2.GetMetadata(mexAddress);  
    ```  
  
4. <span data-ttu-id="cfeb7-114">次のコードに示すように、`WsdlImporter` を作成して `ImportAllEndpoints` を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="cfeb7-114">Create a `WsdlImporter` and call `ImportAllEndpoints`, as shown in the following code.</span></span>  
  
    ```  
    WsdlImporter importer = new WsdlImporter(mexSet);  
    ServiceEndpointCollection endpoints = importer.ImportAllEndpoints();  
    ```  
  
5. <span data-ttu-id="cfeb7-115">この時点で、サービス エンドポイントのコレクションが取得されます。</span><span class="sxs-lookup"><span data-stu-id="cfeb7-115">At this point, you have a collection of service endpoints.</span></span> <span data-ttu-id="cfeb7-116">メタデータのインポートに関する詳細については、次を参照してください。[方法。サービス エンドポイントにメタデータをインポート](../../../../docs/framework/wcf/feature-details/how-to-import-metadata-into-service-endpoints.md)します。</span><span class="sxs-lookup"><span data-stu-id="cfeb7-116">For more information about importing metadata, see [How to: Import Metadata into Service Endpoints](../../../../docs/framework/wcf/feature-details/how-to-import-metadata-into-service-endpoints.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cfeb7-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="cfeb7-117">See also</span></span>

- [<span data-ttu-id="cfeb7-118">メタデータ</span><span class="sxs-lookup"><span data-stu-id="cfeb7-118">Metadata</span></span>](../../../../docs/framework/wcf/feature-details/metadata.md)
