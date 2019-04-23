---
title: '方法: クライアントの資格情報の種類を指定する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- security credentials, adding to SOAP messages
- WCF, security
ms.assetid: 10f51bee-5f92-4c1a-9126-fa5418535d8f
ms.openlocfilehash: 775c6a297047c7a0e16db091f9a22686fdb01efb
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59339399"
---
# <a name="how-to-specify-the-client-credential-type"></a><span data-ttu-id="baede-102">方法: クライアントの資格情報の種類を指定する</span><span class="sxs-lookup"><span data-stu-id="baede-102">How to: Specify the Client Credential Type</span></span>
<span data-ttu-id="baede-103">セキュリティ モード (トランスポートまたはメッセージ) を設定してから、クライアント資格情報の種類を指定することができます。</span><span class="sxs-lookup"><span data-stu-id="baede-103">After setting a security mode (either transport or message), you have the option of setting the client credential type.</span></span> <span data-ttu-id="baede-104">このプロパティでは、クライアントが認証時にサービスに提供する必要のある資格情報の種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="baede-104">This property specifies what type of credential the client must provide to the service for authentication.</span></span> <span data-ttu-id="baede-105">セキュリティ モード (クライアントの資格情報の種類を設定する前に必要な手順) を設定する方法についての詳細については、次を参照してください。[方法。セキュリティ モードを設定](../../../docs/framework/wcf/how-to-set-the-security-mode.md)します。</span><span class="sxs-lookup"><span data-stu-id="baede-105">For more information about setting the security mode (a necessary step before setting the client credential type), see [How to: Set the Security Mode](../../../docs/framework/wcf/how-to-set-the-security-mode.md).</span></span>  
  
### <a name="to-set-the-client-credential-type-in-code"></a><span data-ttu-id="baede-106">コードでクライアント資格情報の種類を設定するには</span><span class="sxs-lookup"><span data-stu-id="baede-106">To set the client credential type in code</span></span>  
  
1. <span data-ttu-id="baede-107">サービスで使用されるバインドのインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="baede-107">Create an instance of the binding that the service will use.</span></span> <span data-ttu-id="baede-108">この例では、<xref:System.ServiceModel.WSHttpBinding> バインドを使用します。</span><span class="sxs-lookup"><span data-stu-id="baede-108">This example uses the <xref:System.ServiceModel.WSHttpBinding> binding.</span></span>  
  
2. <span data-ttu-id="baede-109"><xref:System.ServiceModel.WSHttpSecurity.Mode%2A> プロパティに適切な値を設定します。</span><span class="sxs-lookup"><span data-stu-id="baede-109">Set the <xref:System.ServiceModel.WSHttpSecurity.Mode%2A> property to an appropriate value.</span></span> <span data-ttu-id="baede-110">この例では、メッセージ モードを使用します。</span><span class="sxs-lookup"><span data-stu-id="baede-110">This example uses the Message mode.</span></span>  
  
3. <span data-ttu-id="baede-111"><xref:System.ServiceModel.MessageSecurityOverHttp.ClientCredentialType%2A> プロパティに適切な値を設定します。</span><span class="sxs-lookup"><span data-stu-id="baede-111">Set the <xref:System.ServiceModel.MessageSecurityOverHttp.ClientCredentialType%2A> property to an appropriate value.</span></span> <span data-ttu-id="baede-112">この例では、Windows 認証 (<xref:System.ServiceModel.MessageCredentialType.Windows>) を使用するように設定します。</span><span class="sxs-lookup"><span data-stu-id="baede-112">This example sets it to use Windows authentication (<xref:System.ServiceModel.MessageCredentialType.Windows>).</span></span>  
  
     [!code-csharp[c_ProgrammingSecurity#14](../../../samples/snippets/csharp/VS_Snippets_CFX/c_programmingsecurity/cs/source.cs#14)]
     [!code-vb[c_ProgrammingSecurity#14](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_programmingsecurity/vb/source.vb#14)]  
  
### <a name="to-set-the-client-credential-type-in-configuration"></a><span data-ttu-id="baede-113">構成でクライアント資格情報の種類を設定するには</span><span class="sxs-lookup"><span data-stu-id="baede-113">To set the client credential type in configuration</span></span>  
  
1. <span data-ttu-id="baede-114">追加、 [ \<system.serviceModel >](../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)要素を構成ファイル。</span><span class="sxs-lookup"><span data-stu-id="baede-114">Add a [\<system.serviceModel>](../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) element to the configuration file.</span></span>  
  
2. <span data-ttu-id="baede-115">子要素として追加する[\<バインド >](../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)要素。</span><span class="sxs-lookup"><span data-stu-id="baede-115">As a child element, add a [\<bindings>](../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) element.</span></span>  
  
3. <span data-ttu-id="baede-116">適切なバインドを追加します。</span><span class="sxs-lookup"><span data-stu-id="baede-116">Add an appropriate binding.</span></span> <span data-ttu-id="baede-117">この例では、 [ \<wsHttpBinding >](../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)要素。</span><span class="sxs-lookup"><span data-stu-id="baede-117">This example uses the [\<wsHttpBinding>](../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) element.</span></span>  
  
4. <span data-ttu-id="baede-118">追加、 [\<バインド >](../../../docs/framework/misc/binding.md)要素、`name`属性に適切な値。</span><span class="sxs-lookup"><span data-stu-id="baede-118">Add a [\<binding>](../../../docs/framework/misc/binding.md) element and set the `name` attribute to an appropriate value.</span></span> <span data-ttu-id="baede-119">この例では、"SecureBinding" という名前を使用します。</span><span class="sxs-lookup"><span data-stu-id="baede-119">This example uses the name "SecureBinding".</span></span>  
  
5. <span data-ttu-id="baede-120">`<security>` バインドを追加します。</span><span class="sxs-lookup"><span data-stu-id="baede-120">Add a `<security>` binding.</span></span> <span data-ttu-id="baede-121">`mode` 属性を適切な値に設定します。</span><span class="sxs-lookup"><span data-stu-id="baede-121">Set the `mode` attribute to an appropriate value.</span></span> <span data-ttu-id="baede-122">この例では、`"Message"` に設定します。</span><span class="sxs-lookup"><span data-stu-id="baede-122">This example sets it to `"Message"`.</span></span>  
  
6. <span data-ttu-id="baede-123">セキュリティ モードによって、`<message>` 要素と `<transport>` 要素のどちらかを追加します。</span><span class="sxs-lookup"><span data-stu-id="baede-123">Add either a `<message>` or `<transport>` element, as determined by the security mode.</span></span> <span data-ttu-id="baede-124">`clientCredentialType` 属性を適切な値に設定します。</span><span class="sxs-lookup"><span data-stu-id="baede-124">Set the `clientCredentialType` attribute to an appropriate value.</span></span> <span data-ttu-id="baede-125">この例では `"Windows"` を使用します。</span><span class="sxs-lookup"><span data-stu-id="baede-125">This example uses `"Windows"`.</span></span>  
  
    ```xml  
    <system.serviceModel>  
      <bindings>  
        <wsHttpBinding>  
          <binding name="SecureBinding">  
            <security mode="Message">  
                 <message clientCredentialType="Windows" />  
             </security>  
          </binding>  
        </wsHttpBinding>  
      </bindings>  
    </system.serviceModel>  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="baede-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="baede-126">See also</span></span>

- [<span data-ttu-id="baede-127">サービスのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="baede-127">Securing Services</span></span>](../../../docs/framework/wcf/securing-services.md)
- [<span data-ttu-id="baede-128">方法: セキュリティ モードを設定します。</span><span class="sxs-lookup"><span data-stu-id="baede-128">How to: Set the Security Mode</span></span>](../../../docs/framework/wcf/how-to-set-the-security-mode.md)
