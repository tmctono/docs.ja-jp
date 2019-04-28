---
title: WCF での複数の認証方式の使用
ms.date: 03/30/2017
ms.assetid: f32a56a0-e2b2-46bf-a302-29e1275917f9
ms.openlocfilehash: b0f5da9a4c6fdfede9a86434f49f9e9821778176
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61932681"
---
# <a name="using-multiple-authentication-schemes-with-wcf"></a><span data-ttu-id="b68d5-102">WCF での複数の認証方式の使用</span><span class="sxs-lookup"><span data-stu-id="b68d5-102">Using Multiple Authentication Schemes with WCF</span></span>
<span data-ttu-id="b68d5-103">WCF では、単一のエンドポイントに複数の認証方式を指定できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="b68d5-103">WCF now allows you to specify multiple authentication schemes on a single endpoint.</span></span> <span data-ttu-id="b68d5-104">さらに、Web ホスト サービスは、認証設定を IIS から直接継承できます。</span><span class="sxs-lookup"><span data-stu-id="b68d5-104">Furthermore web hosted services can inherit their authentication settings directly from IIS.</span></span> <span data-ttu-id="b68d5-105">自己ホスト型サービスは、使用可能な認証方式を指定できます。</span><span class="sxs-lookup"><span data-stu-id="b68d5-105">Self-hosted services can specify what authentication schemes can be used.</span></span> <span data-ttu-id="b68d5-106">IIS での認証設定の詳細については、次を参照してください[IIS 認証。](https://go.microsoft.com/fwlink/?LinkId=232458)</span><span class="sxs-lookup"><span data-stu-id="b68d5-106">For more information about setting authentication settings in IIS, see [IIS Authentication](https://go.microsoft.com/fwlink/?LinkId=232458)</span></span>  
  
## <a name="iis-hosted-services"></a><span data-ttu-id="b68d5-107">IIS でホストされるサービス</span><span class="sxs-lookup"><span data-stu-id="b68d5-107">IIS-Hosted Services</span></span>  
 <span data-ttu-id="b68d5-108">IIS でホストされるサービスでは、IIS で使用する認証方式を設定します。</span><span class="sxs-lookup"><span data-stu-id="b68d5-108">For IIS-hosted services, set the authentication schemes you wish to use in IIS.</span></span> <span data-ttu-id="b68d5-109">サービスの web.config ファイルでバインド構成で型を指定 clientCredential"InheritedFromHost"として次の XML スニペットに示すようにします。</span><span class="sxs-lookup"><span data-stu-id="b68d5-109">Then in your service’s web.config file, in your binding configuration specify clientCredential type as "InheritedFromHost" as shown in the following XML snippet:</span></span>  
  
```xml  
<bindings>  
      <basicHttpBinding>  
        <binding name="secureBinding">  
          <security mode="Transport">  
            <transport clientCredentialType="InheritedFromHost" />  
          </security>  
        </binding>  
      </basicHttpBinding>  
    </bindings>  
```  
  
 <span data-ttu-id="b68d5-110">ServiceAuthenticationBehavior を使用して、サービスで使用する認証方式のサブセットのみをすることを指定する、または\<serviceAuthenticationManager > 要素。</span><span class="sxs-lookup"><span data-stu-id="b68d5-110">You can specify that you only want a subset of authentication schemes to be used with your service using the ServiceAuthenticationBehavior or the \<serviceAuthenticationManager> element.</span></span> <span data-ttu-id="b68d5-111">これをコードで構成する場合は、次のコード スニペットに示すように ServiceAuthenticationBehavior を使用します。</span><span class="sxs-lookup"><span data-stu-id="b68d5-111">When configuring this in code use the ServiceAuthenticationBehavior as shown in the following code snippet.</span></span>  
  
```csharp  
// ...  
ServiceAuthenticationBehavior sab = null;  
sab = serviceHost.Description.Behaviors.Find<ServiceAuthenticationBehavior>();  
  
if (sab == null)  
{  
    sab = new ServiceAuthenticationBehavior();  
    sab.AuthenticationSchemes = AuthenticationSchemes.Basic | AuthenticationSchemes.Negotiate | AuthenticationSchemes.Digest;  
    serviceHost.Description.Behaviors.Add(sab);  
}  
else  
{  
     sab.AuthenticationSchemes = AuthenticationSchemes.Basic | AuthenticationSchemes.Negotiate | AuthenticationSchemes.Digest;  
}  
// ...  
```  
  
 <span data-ttu-id="b68d5-112">構成ファイル内に構成を使用して、 \<serviceAuthenticationManager > 要素の次の XML スニペットに示すようにします。</span><span class="sxs-lookup"><span data-stu-id="b68d5-112">When configuring this in a config file, use the \<serviceAuthenticationManager> element as shown in the following XML snippet.</span></span>  
  
```xml  
<behaviors>  
      <serviceBehaviors>  
        <behavior name="limitedAuthBehavior">  
          <serviceAuthenticationManager authenticationSchemes="Negotiate, Digest, Basic"/>  
          <!-- ... -->  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
```  
  
 <span data-ttu-id="b68d5-113">この結果、IIS で選択した内容に応じて、ここに示されている認証方式のサブセットに限り、サービス エンドポイントへの適用が検討されます。</span><span class="sxs-lookup"><span data-stu-id="b68d5-113">This will ensure that only a subset of the authentication schemes listed here will be considered for applying on the service endpoint, depending on what is selected in the IIS.</span></span> <span data-ttu-id="b68d5-114">つまり、開発者は serviceAuthenticationManager の一覧から基本認証を省略することによって、リストから基本認証を除外することができます。IIS で有効になっている場合でも、サービス エンドポイントには適用されません。</span><span class="sxs-lookup"><span data-stu-id="b68d5-114">This means that a developer can exclude say Basic auth from the list by omitting it from the serviceAuthenticationManager listing and even if it is enabled in IIS, it will not be applied on the service endpoint</span></span>  
  
## <a name="self-hosted-services"></a><span data-ttu-id="b68d5-115">自己ホスト型サービス</span><span class="sxs-lookup"><span data-stu-id="b68d5-115">Self-Hosted Services</span></span>  
 <span data-ttu-id="b68d5-116">自己ホスト型サービスは、設定を継承する IIS がないため、構成方法が少し異なります。</span><span class="sxs-lookup"><span data-stu-id="b68d5-116">Self-hosted services are configured a bit differently since there is no IIS to inherit settings from.</span></span> <span data-ttu-id="b68d5-117">ここで使用して、 \<serviceAuthenticationManager > 要素または ServiceAuthenticationBehavior を継承される認証設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="b68d5-117">Here you use the \<serviceAuthenticationManager> element or ServiceAuthenticationBehavior to specify the authentication settings that will be inherited.</span></span> <span data-ttu-id="b68d5-118">コード例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="b68d5-118">In code it looks like this:</span></span>  
  
```csharp  
// ...  
ServiceAuthenticationBehavior sab = null;  
sab = serviceHost.Description.Behaviors.Find<ServiceAuthenticationBehavior>();  
  
if (sab == null)  
{  
    sab = new ServiceAuthenticationBehavior();  
    sab.AuthenticationSchemes = AuthenticationSchemes.Basic | AuthenticationSchemes.Negotiate | AuthenticationSchemes.Digest;  
    serviceHost.Description.Behaviors.Add(sab);  
}  
else  
{  
     sab.AuthenticationSchemes = AuthenticationSchemes.Basic | AuthenticationSchemes.Negotiate | AuthenticationSchemes.Digest;  
}  
// ...  
```  
  
 <span data-ttu-id="b68d5-119">config では、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="b68d5-119">In config, it looks like this:</span></span>  
  
```xml  
<behaviors>  
      <serviceBehaviors>  
        <behavior name="limitedAuthBehavior">  
          <serviceAuthenticationManager authenticationSchemes="Negotiate, Digest, Basic"/>  
          <!-- ... -->  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
```  
  
 <span data-ttu-id="b68d5-120">その後、次の XML スニペットに示すように、バインディング設定で InheritFromHost を指定できます。</span><span class="sxs-lookup"><span data-stu-id="b68d5-120">And then you can specify InheritFromHost in your binding settings as shown in the following XML snippet.</span></span>  
  
```xml  
<bindings>  
      <basicHttpBinding>  
        <binding name="secureBinding">  
          <security mode="Transport">  
            <transport clientCredentialType="InheritedFromHost" />  
          </security>  
        </binding>  
      </basicHttpBinding>  
    </bindings>  
```  
  
 <span data-ttu-id="b68d5-121">または、次の構成スニペットに示すように、HTTP トランスポート バインド要素で認証方式を設定することにより、カスタム バインドで認証方式を指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="b68d5-121">Alternatively, you can specify the authentication schemes in a custom binding, by setting the authentication schemes on the HTTP transport binding element, as shown in the following config snippet.</span></span>  
  
```xml  
<binding name="multipleBinding">  
      <textMessageEncoding/>  
      <httpTransport authenticationScheme="Negotiate, Ntlm, Digest, Basic" />  
    </binding>  
```  
  
## <a name="see-also"></a><span data-ttu-id="b68d5-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="b68d5-122">See also</span></span>

- [<span data-ttu-id="b68d5-123">バインディングとセキュリティ</span><span class="sxs-lookup"><span data-stu-id="b68d5-123">Bindings and Security</span></span>](../../../../docs/framework/wcf/feature-details/bindings-and-security.md)
- [<span data-ttu-id="b68d5-124">エンドポイント:アドレス、バインディング、およびコントラクト</span><span class="sxs-lookup"><span data-stu-id="b68d5-124">Endpoints: Addresses, Bindings, and Contracts</span></span>](../../../../docs/framework/wcf/feature-details/endpoints-addresses-bindings-and-contracts.md)
- [<span data-ttu-id="b68d5-125">システムが提供するバインディングの構成</span><span class="sxs-lookup"><span data-stu-id="b68d5-125">Configuring System-Provided Bindings</span></span>](../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="b68d5-126">カスタム バインドを使用したセキュリティ機能</span><span class="sxs-lookup"><span data-stu-id="b68d5-126">Security Capabilities with Custom Bindings</span></span>](../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="b68d5-127">バインディング</span><span class="sxs-lookup"><span data-stu-id="b68d5-127">Bindings</span></span>](../../../../docs/framework/wcf/feature-details/bindings.md)
- [<span data-ttu-id="b68d5-128">カスタム バインディング</span><span class="sxs-lookup"><span data-stu-id="b68d5-128">Custom Bindings</span></span>](../../../../docs/framework/wcf/extending/custom-bindings.md)
