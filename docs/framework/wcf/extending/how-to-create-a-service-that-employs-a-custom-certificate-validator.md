---
title: '方法: カスタム証明書検証を使用するサービスを作成する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF, authentication
ms.assetid: bb0190ff-0738-4e54-8d22-c97d343708bf
ms.openlocfilehash: b2407c293de7f11b90586f5a55bd759a4ea734aa
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70795677"
---
# <a name="how-to-create-a-service-that-employs-a-custom-certificate-validator"></a><span data-ttu-id="5177d-102">方法: カスタム証明書検証を使用するサービスを作成する</span><span class="sxs-lookup"><span data-stu-id="5177d-102">How to: Create a Service that Employs a Custom Certificate Validator</span></span>
<span data-ttu-id="5177d-103">このトピックでは、カスタム証明書検証を実装する方法、クライアントまたはサービスの資格情報の設定により、既定の証明書検証機能を、カスタム証明書検証で置き換える方法について解説します。</span><span class="sxs-lookup"><span data-stu-id="5177d-103">This topic shows how to implement a custom certificate validator and how to configure client or service credentials to replace the default certificate validation logic with the custom certificate validator.</span></span>  
  
 <span data-ttu-id="5177d-104">X.509 証明書を使用してクライアントまたはサービスを認証する場合、Windows Communication Foundation (WCF) では、既定で Windows 証明書ストアと Crypto API を使用して証明書を検証し、証明書が信頼されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="5177d-104">If the X.509 certificate is used to authenticate a client or service, Windows Communication Foundation (WCF) by default uses the Windows certificate store and Crypto API to validate the certificate and to ensure that it is trusted.</span></span> <span data-ttu-id="5177d-105">ただし、組み込みの検証機能では不十分で、処理内容を変更する必要がある場合もあります。</span><span class="sxs-lookup"><span data-stu-id="5177d-105">Sometimes the built-in certificate validation functionality is not enough and must be changed.</span></span> <span data-ttu-id="5177d-106">WCF では、ユーザーがカスタム証明書検証機能を追加できるようにすることで、検証ロジックを簡単に変更できます。</span><span class="sxs-lookup"><span data-stu-id="5177d-106">WCF provides an easy way to change the validation logic by allowing users to add a custom certificate validator.</span></span> <span data-ttu-id="5177d-107">カスタム証明書検証コントロールが指定されている場合、WCF は組み込みの証明書検証ロジックを使用しませんが、代わりにカスタム検証機能に依存します。</span><span class="sxs-lookup"><span data-stu-id="5177d-107">If a custom certificate validator is specified, WCF does not use the built-in certificate validation logic but relies on the custom validator instead.</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="5177d-108">手順</span><span class="sxs-lookup"><span data-stu-id="5177d-108">Procedures</span></span>  
  
#### <a name="to-create-a-custom-certificate-validator"></a><span data-ttu-id="5177d-109">カスタムの証明書検証機能を作成するには</span><span class="sxs-lookup"><span data-stu-id="5177d-109">To create a custom certificate validator</span></span>  
  
1. <span data-ttu-id="5177d-110"><xref:System.IdentityModel.Selectors.X509CertificateValidator> から派生する新しいクラスを定義します。</span><span class="sxs-lookup"><span data-stu-id="5177d-110">Define a new class derived from <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span></span>  
  
2. <span data-ttu-id="5177d-111">抽象メソッドである <xref:System.IdentityModel.Selectors.X509CertificateValidator.Validate%2A> を実装します。</span><span class="sxs-lookup"><span data-stu-id="5177d-111">Implement the abstract <xref:System.IdentityModel.Selectors.X509CertificateValidator.Validate%2A> method.</span></span> <span data-ttu-id="5177d-112">検証対象の証明書が、引数としてこのメソッドに渡されます。</span><span class="sxs-lookup"><span data-stu-id="5177d-112">The certificate that must be validated is passed as an argument to the method.</span></span> <span data-ttu-id="5177d-113">検証処理の結果、証明書が無効であると判断されると、このメソッドは、<xref:System.IdentityModel.Tokens.SecurityTokenValidationException> という例外をスローします。</span><span class="sxs-lookup"><span data-stu-id="5177d-113">If the passed certificate is not valid according to the validation logic, this method throws a <xref:System.IdentityModel.Tokens.SecurityTokenValidationException>.</span></span> <span data-ttu-id="5177d-114">有効であればそのまま呼び出し元に制御を返します。</span><span class="sxs-lookup"><span data-stu-id="5177d-114">If the certificate is valid, the method returns to the caller.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="5177d-115">クライアントに認証エラーを返すには、<xref:System.ServiceModel.FaultException> メソッドで <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A> をスローします。</span><span class="sxs-lookup"><span data-stu-id="5177d-115">To return authentication errors back to the client, throw a <xref:System.ServiceModel.FaultException> in the <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A> method.</span></span>  
  
 [!code-csharp[c_CustomCertificateValidator#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customcertificatevalidator/cs/source.cs#2)]
 [!code-vb[c_CustomCertificateValidator#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customcertificatevalidator/vb/source.vb#2)]  
  
#### <a name="to-specify-a-custom-certificate-validator-in-service-configuration"></a><span data-ttu-id="5177d-116">サービス構成でカスタム検証処理を指定するには</span><span class="sxs-lookup"><span data-stu-id="5177d-116">To specify a custom certificate validator in service configuration</span></span>  
  
1. <span data-ttu-id="5177d-117">[ \<](../../configure-apps/file-schema/wcf/behaviors.md) [System.servicemodel >要素\<](../../configure-apps/file-schema/wcf/system-servicemodel.md)に > 要素と[ \<servicebehaviors >](../../configure-apps/file-schema/wcf/servicebehaviors.md)の動作を追加します。</span><span class="sxs-lookup"><span data-stu-id="5177d-117">Add a [\<behaviors>](../../configure-apps/file-schema/wcf/behaviors.md) element and a [\<serviceBehaviors>](../../configure-apps/file-schema/wcf/servicebehaviors.md) to the [\<system.serviceModel>](../../configure-apps/file-schema/wcf/system-servicemodel.md) element.</span></span>  
  
2. <span data-ttu-id="5177d-118">[\<behavior>](../../configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) を追加し、`name` 属性に適切な値を設定</span><span class="sxs-lookup"><span data-stu-id="5177d-118">Add a [\<behavior>](../../configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) and set the `name` attribute to an appropriate value.</span></span>  
  
3. <span data-ttu-id="5177d-119">要素に[ \<serviceCredentials](../../configure-apps/file-schema/wcf/servicecredentials.md) `<behavior>` > を追加します。</span><span class="sxs-lookup"><span data-stu-id="5177d-119">Add a [\<serviceCredentials>](../../configure-apps/file-schema/wcf/servicecredentials.md) to the `<behavior>` element.</span></span>  
  
4. <span data-ttu-id="5177d-120">`<clientCertificate>` 要素を `<serviceCredentials>` 要素に追加します。</span><span class="sxs-lookup"><span data-stu-id="5177d-120">Add a `<clientCertificate>` element to the `<serviceCredentials>` element.</span></span>  
  
5. <span data-ttu-id="5177d-121">認証 > を要素に追加します。`<clientCertificate>` [ \<](../../configure-apps/file-schema/wcf/authentication-of-clientcertificate-element.md)</span><span class="sxs-lookup"><span data-stu-id="5177d-121">Add an [\<authentication>](../../configure-apps/file-schema/wcf/authentication-of-clientcertificate-element.md) to the `<clientCertificate>` element.</span></span>  
  
6. <span data-ttu-id="5177d-122">`customCertificateValidatorType` 属性に検証処理の型を設定します。</span><span class="sxs-lookup"><span data-stu-id="5177d-122">Set the `customCertificateValidatorType` attribute to the validator type.</span></span> <span data-ttu-id="5177d-123">この属性に型の名前空間と名前を設定する例を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="5177d-123">The following example sets the attribute to the namespace and name of the type.</span></span>  
  
7. <span data-ttu-id="5177d-124">`certificateValidationMode` 属性に `Custom` を設定</span><span class="sxs-lookup"><span data-stu-id="5177d-124">Set the `certificateValidationMode` attribute to `Custom`.</span></span>  
  
    ```xml  
    <configuration>  
     <system.serviceModel>  
      <behaviors>  
       <serviceBehaviors>  
        <behavior name="ServiceBehavior">  
         <serviceCredentials>  
          <clientCertificate>  
          <authentication certificateValidationMode="Custom" customCertificateValidatorType="Samples.MyValidator, service" />  
          </clientCertificate>  
         </serviceCredentials>  
        </behavior>  
       </serviceBehaviors>  
      </behaviors>  
    </system.serviceModel>  
    </configuration>  
    ```  
  
#### <a name="to-specify-a-custom-certificate-validator-using-configuration-on-the-client"></a><span data-ttu-id="5177d-125">クライアント側の設定でカスタム証明書検証を指定するには</span><span class="sxs-lookup"><span data-stu-id="5177d-125">To specify a custom certificate validator using configuration on the client</span></span>  
  
1. <span data-ttu-id="5177d-126">[ \<](../../configure-apps/file-schema/wcf/behaviors.md) [System.servicemodel >要素\<](../../configure-apps/file-schema/wcf/system-servicemodel.md)に > 要素と[ \<servicebehaviors >](../../configure-apps/file-schema/wcf/servicebehaviors.md)の動作を追加します。</span><span class="sxs-lookup"><span data-stu-id="5177d-126">Add a [\<behaviors>](../../configure-apps/file-schema/wcf/behaviors.md) element and a [\<serviceBehaviors>](../../configure-apps/file-schema/wcf/servicebehaviors.md) to the [\<system.serviceModel>](../../configure-apps/file-schema/wcf/system-servicemodel.md) element.</span></span>  
  
2. <span data-ttu-id="5177d-127">[ \<Endpointbehaviors >](../../configure-apps/file-schema/wcf/endpointbehaviors.md)要素を追加します。</span><span class="sxs-lookup"><span data-stu-id="5177d-127">Add an [\<endpointBehaviors>](../../configure-apps/file-schema/wcf/endpointbehaviors.md) element.</span></span>  
  
3. <span data-ttu-id="5177d-128">`<behavior>` 要素を追加し、`name` 属性に適切な値を設定します。</span><span class="sxs-lookup"><span data-stu-id="5177d-128">Add a `<behavior>` element and set the `name` attribute to an appropriate value.</span></span>  
  
4. <span data-ttu-id="5177d-129">[ \<ClientCredentials >](../../configure-apps/file-schema/wcf/clientcredentials.md)要素を追加します。</span><span class="sxs-lookup"><span data-stu-id="5177d-129">Add a [\<clientCredentials>](../../configure-apps/file-schema/wcf/clientcredentials.md) element.</span></span>  
  
5. <span data-ttu-id="5177d-130">[ \<ServiceCertificate >](../../configure-apps/file-schema/wcf/servicecertificate-of-clientcredentials-element.md)を追加します。</span><span class="sxs-lookup"><span data-stu-id="5177d-130">Add a [\<serviceCertificate>](../../configure-apps/file-schema/wcf/servicecertificate-of-clientcredentials-element.md).</span></span>  
  
6. <span data-ttu-id="5177d-131">次の例に示すように、 [ \<認証 >](../../configure-apps/file-schema/wcf/authentication-of-servicecertificate-element.md)を追加します。</span><span class="sxs-lookup"><span data-stu-id="5177d-131">Add an [\<authentication>](../../configure-apps/file-schema/wcf/authentication-of-servicecertificate-element.md) as shown on the following example.</span></span>  
  
7. <span data-ttu-id="5177d-132">`customCertificateValidatorType` 属性に検証処理の型を設定します。</span><span class="sxs-lookup"><span data-stu-id="5177d-132">Set the `customCertificateValidatorType` attribute to the validator type.</span></span>  
  
8. <span data-ttu-id="5177d-133">`certificateValidationMode` 属性に `Custom` を設定</span><span class="sxs-lookup"><span data-stu-id="5177d-133">Set the `certificateValidationMode` attribute to `Custom`.</span></span> <span data-ttu-id="5177d-134">この属性に型の名前空間と名前を設定する例を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="5177d-134">The following example sets the attribute to the namespace and name of the type.</span></span>  
  
    ```xml  
    <configuration>  
     <system.serviceModel>  
      <behaviors>  
       <endpointBehaviors>  
        <behavior name="clientBehavior">  
         <clientCredentials>  
          <serviceCertificate>  
           <authentication certificateValidationMode="Custom"   
                  customCertificateValidatorType=  
             "Samples.CustomX509CertificateValidator, client"/>  
          </serviceCertificate>  
         </clientCredentials>  
        </behavior>  
       </endpointBehaviors>  
      </behaviors>  
     </system.serviceModel>  
    </configuration>  
    ```  
  
#### <a name="to-specify-a-custom-certificate-validator-using-code-on-the-service"></a><span data-ttu-id="5177d-135">サービス側のコードでカスタム証明書検証を指定するには</span><span class="sxs-lookup"><span data-stu-id="5177d-135">To specify a custom certificate validator using code on the service</span></span>  
  
1. <span data-ttu-id="5177d-136"><xref:System.ServiceModel.Description.ServiceCredentials.ClientCertificate%2A> プロパティの値としてカスタム証明書検証を指定します。</span><span class="sxs-lookup"><span data-stu-id="5177d-136">Specify the custom certificate validator on the <xref:System.ServiceModel.Description.ServiceCredentials.ClientCertificate%2A> property.</span></span> <span data-ttu-id="5177d-137">サービスの資格情報には、<xref:System.ServiceModel.ServiceHostBase.Credentials%2A> プロパティを使用してアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="5177d-137">You can access the service credentials using the <xref:System.ServiceModel.ServiceHostBase.Credentials%2A> property.</span></span>  
  
2. <span data-ttu-id="5177d-138"><xref:System.ServiceModel.Security.X509ClientCertificateAuthentication.CertificateValidationMode%2A> プロパティを <xref:System.ServiceModel.Security.X509CertificateValidationMode.Custom> に設定します。</span><span class="sxs-lookup"><span data-stu-id="5177d-138">Set the <xref:System.ServiceModel.Security.X509ClientCertificateAuthentication.CertificateValidationMode%2A> property to <xref:System.ServiceModel.Security.X509CertificateValidationMode.Custom>.</span></span>  
  
 [!code-csharp[c_CustomCertificateValidator#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customcertificatevalidator/cs/source.cs#1)]
 [!code-vb[c_CustomCertificateValidator#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customcertificatevalidator/vb/source.vb#1)]  
  
#### <a name="to-specify-a-custom-certificate-validator-using-code-on-the-client"></a><span data-ttu-id="5177d-139">クライアント側のコードでカスタム証明書検証を指定するには</span><span class="sxs-lookup"><span data-stu-id="5177d-139">To specify a custom certificate validator using code on the client</span></span>  
  
1. <span data-ttu-id="5177d-140">カスタム証明書検証を、<xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication.CustomCertificateValidator%2A> プロパティを使って指定します。</span><span class="sxs-lookup"><span data-stu-id="5177d-140">Specify the custom certificate validator using the <xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication.CustomCertificateValidator%2A> property.</span></span> <span data-ttu-id="5177d-141">クライアントの資格情報には、<xref:System.ServiceModel.ServiceHostBase.Credentials%2A> プロパティを使用してアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="5177d-141">You can access the client credentials using the <xref:System.ServiceModel.ServiceHostBase.Credentials%2A> property.</span></span> <span data-ttu-id="5177d-142">( [ServiceModel メタデータユーティリティツール (svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md)によって生成されるクライアントクラスは、 <xref:System.ServiceModel.ClientBase%601>常にクラスから派生します)。</span><span class="sxs-lookup"><span data-stu-id="5177d-142">(The client class generated by [ServiceModel Metadata Utility Tool (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) always derives from the <xref:System.ServiceModel.ClientBase%601> class.)</span></span>  
  
2. <span data-ttu-id="5177d-143"><xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication.CertificateValidationMode%2A> プロパティを <xref:System.ServiceModel.Security.X509CertificateValidationMode.Custom> に設定します。</span><span class="sxs-lookup"><span data-stu-id="5177d-143">Set the <xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication.CertificateValidationMode%2A> property to <xref:System.ServiceModel.Security.X509CertificateValidationMode.Custom>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5177d-144">例</span><span class="sxs-lookup"><span data-stu-id="5177d-144">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="5177d-145">説明</span><span class="sxs-lookup"><span data-stu-id="5177d-145">Description</span></span>  
 <span data-ttu-id="5177d-146">カスタム証明書検証を実装し、サービス側で使用する例を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="5177d-146">The following sample shows an implementation of a custom certificate validator and its usage on the service.</span></span>  
  
### <a name="code"></a><span data-ttu-id="5177d-147">コード</span><span class="sxs-lookup"><span data-stu-id="5177d-147">Code</span></span>  
 [!code-csharp[c_CustomCertificateValidator#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customcertificatevalidator/cs/source.cs#3)]
 [!code-vb[c_CustomCertificateValidator#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customcertificatevalidator/vb/source.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="5177d-148">関連項目</span><span class="sxs-lookup"><span data-stu-id="5177d-148">See also</span></span>

- <xref:System.IdentityModel.Selectors.X509CertificateValidator>
