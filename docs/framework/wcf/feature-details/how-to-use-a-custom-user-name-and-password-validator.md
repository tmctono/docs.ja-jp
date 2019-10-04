---
title: '方法: カスタム ユーザー名およびパスワード検証を使用する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF, username and password
ms.assetid: 8e08b74b-fa44-4018-b63d-0d0805f85e3f
ms.openlocfilehash: 98ffad7e717aac949509fa701c77d8ba2b80a695
ms.sourcegitcommit: 8a0fe8a2227af612f8b8941bdb8b19d6268748e7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/03/2019
ms.locfileid: "71834693"
---
# <a name="how-to-use-a-custom-user-name-and-password-validator"></a><span data-ttu-id="b3ab9-102">方法: カスタム ユーザー名およびパスワード検証を使用する</span><span class="sxs-lookup"><span data-stu-id="b3ab9-102">How to: Use a Custom User Name and Password Validator</span></span>

<span data-ttu-id="b3ab9-103">既定では、ユーザー名とパスワードが認証に使用されると、Windows Communication Foundation (WCF) は Windows を使用してユーザー名とパスワードを検証します。</span><span class="sxs-lookup"><span data-stu-id="b3ab9-103">By default, when a user name and password is used for authentication, Windows Communication Foundation (WCF) uses Windows to validate the user name and password.</span></span> <span data-ttu-id="b3ab9-104">ただし、WCF では、カスタムのユーザー名とパスワードの認証方式 (*検証コントロール*とも呼ばれます) を使用できます。</span><span class="sxs-lookup"><span data-stu-id="b3ab9-104">However, WCF allows for custom user name and password authentication schemes, also known as *validators*.</span></span> <span data-ttu-id="b3ab9-105">ユーザー名およびパスワードのカスタム検証を組み込むには、<xref:System.IdentityModel.Selectors.UserNamePasswordValidator> から派生するクラスを作成して構成します。</span><span class="sxs-lookup"><span data-stu-id="b3ab9-105">To incorporate a custom user name and password validator, create a class that derives from <xref:System.IdentityModel.Selectors.UserNamePasswordValidator> and then configure it.</span></span>

<span data-ttu-id="b3ab9-106">サンプルアプリケーションについては、「[ユーザー名パスワード検証コントロール](../samples/user-name-password-validator.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b3ab9-106">For a sample application, see [User Name Password Validator](../samples/user-name-password-validator.md).</span></span>

### <a name="to-create-a-custom-user-name-and-password-validator"></a><span data-ttu-id="b3ab9-107">カスタムのユーザー名/パスワード検証コントロールを作成するには</span><span class="sxs-lookup"><span data-stu-id="b3ab9-107">To create a custom user name and password validator</span></span>

1. <span data-ttu-id="b3ab9-108"><xref:System.IdentityModel.Selectors.UserNamePasswordValidator> から派生するクラスを作成します。</span><span class="sxs-lookup"><span data-stu-id="b3ab9-108">Create a class that derives from <xref:System.IdentityModel.Selectors.UserNamePasswordValidator>.</span></span>

    [!code-csharp[C_CustomUsernameAndPasswordValidator#3](~/samples/snippets/csharp/VS_Snippets_CFX/c_customusernameandpasswordvalidator/cs/service.cs#3)]
    [!code-vb[C_CustomUsernameAndPasswordValidator#3](~/samples/snippets/visualbasic/VS_Snippets_CFX/c_customusernameandpasswordvalidator/vb/service.vb#3)]

2. <span data-ttu-id="b3ab9-109"><xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A> メソッドをオーバーライドして、カスタム認証方式を実装します。</span><span class="sxs-lookup"><span data-stu-id="b3ab9-109">Implement the custom authentication scheme by overriding the <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A> method.</span></span>

    <span data-ttu-id="b3ab9-110">次の例のコードは、<xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A> メソッドをオーバーライドします。稼働環境では、このようなコードを使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="b3ab9-110">Do not use the code in the following example that overrides the <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A> method in a production environment.</span></span> <span data-ttu-id="b3ab9-111">このコードをカスタムのユーザー名/パスワード検証方式に置き換えます。この場合、ユーザー名とパスワードの組み合わせをデータベースから取得する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b3ab9-111">Replace the code with your custom user name and password validation scheme, which might involve retrieving user name and password pairs from a database.</span></span>

    <span data-ttu-id="b3ab9-112">クライアントに認証エラーを返すには、<xref:System.ServiceModel.FaultException> メソッドで <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A> をスローします。</span><span class="sxs-lookup"><span data-stu-id="b3ab9-112">To return authentication errors back to the client, throw a <xref:System.ServiceModel.FaultException> in the <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A> method.</span></span>

    [!code-csharp[C_CustomUsernameAndPasswordValidator#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customusernameandpasswordvalidator/cs/service.cs#4)]
    [!code-vb[C_CustomUsernameAndPasswordValidator#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customusernameandpasswordvalidator/vb/service.vb#4)]

### <a name="to-configure-a-service-to-use-a-custom-user-name-and-password-validator"></a><span data-ttu-id="b3ab9-113">カスタムのユーザー名/パスワード検証コントロールを使用するようにサービスを構成するには</span><span class="sxs-lookup"><span data-stu-id="b3ab9-113">To configure a service to use a custom user name and password validator</span></span>

1. <span data-ttu-id="b3ab9-114">任意のトランスポート上のメッセージ セキュリティ、または HTTP(S) 上のトランスポート レベル セキュリティを使用するバインディングを構成します。</span><span class="sxs-lookup"><span data-stu-id="b3ab9-114">Configure a binding that uses message security over any transport or transport-level security over HTTP(S).</span></span>

    <span data-ttu-id="b3ab9-115">メッセージセキュリティを使用する場合は、システム指定のバインディングの1つを追加します。たとえば、 [\<wsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)のように、またはメッセージセキュリティと @no__t 4 の資格情報の種類をサポートする[\<custombinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)を追加します。</span><span class="sxs-lookup"><span data-stu-id="b3ab9-115">When using message security, add one of the system-provided bindings, such as a  [\<wsHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md), or a [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) that supports message security and the `UserName` credential type.</span></span>

    <span data-ttu-id="b3ab9-116">HTTP (S) を介してトランスポートレベルのセキュリティを使用する場合は、 [\<wsHttpBinding >](../../configure-apps/file-schema/wcf/wshttpbinding.md)または[\<basichttpbinding >](../../configure-apps/file-schema/wcf/basichttpbinding.md)、 [@no__t 5NETTCPBINDING >](../../configure-apps/file-schema/wcf/nettcpbinding.md) 、または http (s) とを使用する[@no__t 7custombinding >](../../configure-apps/file-schema/wcf/custombinding.md)を追加します。`Basic` 認証スキーム。</span><span class="sxs-lookup"><span data-stu-id="b3ab9-116">When using transport-level security over HTTP(S), add either the [\<wsHttpBinding>](../../configure-apps/file-schema/wcf/wshttpbinding.md) or [\<basicHttpBinding>](../../configure-apps/file-schema/wcf/basichttpbinding.md), a [\<netTcpBinding>](../../configure-apps/file-schema/wcf/nettcpbinding.md) or a [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md) that uses HTTP(S) and the `Basic` authentication scheme.</span></span>

    > [!NOTE]
    > <span data-ttu-id="b3ab9-117">[!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)] 以降を使用する場合は、メッセージおよびトランスポート セキュリティでカスタムのユーザー名/パスワード検証コントロールを使用できます。</span><span class="sxs-lookup"><span data-stu-id="b3ab9-117">When [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)] or later is used, you can use a custom username and password validator with message and transport security.</span></span> <span data-ttu-id="b3ab9-118">WinFX では、カスタムのユーザー名とパスワード検証コントロールは、メッセージセキュリティでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="b3ab9-118">With WinFX, a custom username and password validator can only be used with message security.</span></span>

    > [!TIP]
    > <span data-ttu-id="b3ab9-119">このコンテキストでの \<netTcpBinding > の使用の詳細については、「 [\<security >](../../configure-apps/file-schema/wcf/security-of-nettcpbinding.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b3ab9-119">For more information on using \<netTcpBinding> in this context, see [\<security>](../../configure-apps/file-schema/wcf/security-of-nettcpbinding.md).</span></span>

    1. <span data-ttu-id="b3ab9-120">構成ファイルの[\<System >](../../configure-apps/file-schema/wcf/system-servicemodel.md)要素の下に[\<bindings >](../../configure-apps/file-schema/wcf/bindings.md)要素を追加します。</span><span class="sxs-lookup"><span data-stu-id="b3ab9-120">In the configuration file, under the [\<system.serviceModel>](../../configure-apps/file-schema/wcf/system-servicemodel.md) element, add a [\<bindings>](../../configure-apps/file-schema/wcf/bindings.md) element.</span></span>

    2. <span data-ttu-id="b3ab9-121">[\<wsHttpBinding >](../../configure-apps/file-schema/wcf/wshttpbinding.md) または [\<basicHttpBinding >](../../configure-apps/file-schema/wcf/basichttpbinding.md) 要素をバインディング セクションに追加します。</span><span class="sxs-lookup"><span data-stu-id="b3ab9-121">Add a [\<wsHttpBinding>](../../configure-apps/file-schema/wcf/wshttpbinding.md) or [\<basicHttpBinding>](../../configure-apps/file-schema/wcf/basichttpbinding.md) element to the bindings section.</span></span> <span data-ttu-id="b3ab9-122">WCF バインド要素の作成の詳細については、@no__t を参照してください。構成](../how-to-specify-a-service-binding-in-configuration.md)でサービスバインドを指定します。</span><span class="sxs-lookup"><span data-stu-id="b3ab9-122">For more information about creating an WCF binding element, see [How to: Specify a Service Binding in Configuration](../how-to-specify-a-service-binding-in-configuration.md).</span></span>

    3. <span data-ttu-id="b3ab9-123">[@No__t-2security >](../../configure-apps/file-schema/wcf/security-of-wshttpbinding.md)または[\<security >](../../configure-apps/file-schema/wcf/security-of-basichttpbinding.md)の `mode` 属性を `Message`、`Transport`、または @no__t に設定します。</span><span class="sxs-lookup"><span data-stu-id="b3ab9-123">Set the `mode` attribute of the [\<security>](../../configure-apps/file-schema/wcf/security-of-wshttpbinding.md) or [\<security>](../../configure-apps/file-schema/wcf/security-of-basichttpbinding.md) to `Message`, `Transport`, or `TransportWithMessageCredential`.</span></span>

    4. <span data-ttu-id="b3ab9-124">[\<message>](../../../../docs/framework/configure-apps/file-schema/wcf/message-of-wshttpbinding.md) または　[\<transport>](../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-wshttpbinding.md) の　`clientCredentialType` 属性を設定します。</span><span class="sxs-lookup"><span data-stu-id="b3ab9-124">Set the `clientCredentialType` attribute of the [\<message>](../../../../docs/framework/configure-apps/file-schema/wcf/message-of-wshttpbinding.md) or [\<transport>](../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-wshttpbinding.md).</span></span>

        <span data-ttu-id="b3ab9-125">メッセージセキュリティを使用する場合は、 [\<message >](../../../../docs/framework/configure-apps/file-schema/wcf/message-of-wshttpbinding.md)の `clientCredentialType` 属性を `UserName` に設定します。</span><span class="sxs-lookup"><span data-stu-id="b3ab9-125">When using message security, set the `clientCredentialType` attribute of the [\<message>](../../../../docs/framework/configure-apps/file-schema/wcf/message-of-wshttpbinding.md) to `UserName`.</span></span>

        <span data-ttu-id="b3ab9-126">HTTP (S) でトランスポートレベルのセキュリティを使用する場合は、 [\<transport >](../../configure-apps/file-schema/wcf/transport-of-wshttpbinding.md)または[\<transport >](../../configure-apps/file-schema/wcf/transport-of-basichttpbinding.md)の `clientCredentialType` 属性を `Basic` に設定します。</span><span class="sxs-lookup"><span data-stu-id="b3ab9-126">When using transport-level security over HTTP(S), set the `clientCredentialType` attribute of the [\<transport>](../../configure-apps/file-schema/wcf/transport-of-wshttpbinding.md) or [\<transport>](../../configure-apps/file-schema/wcf/transport-of-basichttpbinding.md) to `Basic`.</span></span>

        > [!NOTE]
        > <span data-ttu-id="b3ab9-127">WCF サービスがトランスポートレベルのセキュリティを使用してインターネットインフォメーションサービス (IIS) でホストされ、<xref:System.ServiceModel.Security.UserNamePasswordServiceCredential.UserNamePasswordValidationMode%2A> プロパティが <xref:System.ServiceModel.Security.UserNamePasswordValidationMode.Custom> に設定されている場合、カスタム認証スキームは Windows 認証のサブセットを使用します。</span><span class="sxs-lookup"><span data-stu-id="b3ab9-127">When a WCF service is hosted in Internet Information Services (IIS) using transport-level security and the <xref:System.ServiceModel.Security.UserNamePasswordServiceCredential.UserNamePasswordValidationMode%2A> property is set to <xref:System.ServiceModel.Security.UserNamePasswordValidationMode.Custom>, the custom authentication scheme uses a subset of Windows authentication.</span></span> <span data-ttu-id="b3ab9-128">このシナリオでは、WCF がカスタム認証システムを呼び出す前に、IIS が Windows 認証を実行します。</span><span class="sxs-lookup"><span data-stu-id="b3ab9-128">That is because in this scenario, IIS performs Windows authentication prior to WCF invoking the custom authenticator.</span></span>

    <span data-ttu-id="b3ab9-129">WCF バインド要素の作成の詳細については、@no__t を参照してください。構成](../how-to-specify-a-service-binding-in-configuration.md)でサービスバインドを指定します。</span><span class="sxs-lookup"><span data-stu-id="b3ab9-129">For more information about creating an WCF binding element, see [How to: Specify a Service Binding in Configuration](../how-to-specify-a-service-binding-in-configuration.md).</span></span>

    <span data-ttu-id="b3ab9-130">次の例は、バインディングの構成コードを示しています。</span><span class="sxs-lookup"><span data-stu-id="b3ab9-130">The following example shows the configuration code for the binding:</span></span>

    ```xml
    <system.serviceModel>
      <bindings>
      <wsHttpBinding>
          <binding name="Binding1">
            <security mode="Message">
              <message clientCredentialType="UserName" />
            </security>
          </binding>
        </wsHttpBinding>
      </bindings>
    </system.serviceModel>
    ```

2. <span data-ttu-id="b3ab9-131">受信 <xref:System.IdentityModel.Tokens.UserNameSecurityToken> セキュリティ トークンのユーザー名とパスワードの組み合わせを検証する際に、カスタムのユーザー名/パスワード検証コントロールを使用することを指定する動作を構成します。</span><span class="sxs-lookup"><span data-stu-id="b3ab9-131">Configure a behavior that specifies that a custom user name and password validator is used to validate user name and password pairs for incoming <xref:System.IdentityModel.Tokens.UserNameSecurityToken> security tokens.</span></span>

    1. <span data-ttu-id="b3ab9-132">[@No__t-1System >](../../configure-apps/file-schema/wcf/system-servicemodel.md)要素の子として、 [\<behaviors >](../../configure-apps/file-schema/wcf/behaviors.md)要素を追加します。</span><span class="sxs-lookup"><span data-stu-id="b3ab9-132">As a child to the [\<system.serviceModel>](../../configure-apps/file-schema/wcf/system-servicemodel.md) element, add a [\<behaviors>](../../configure-apps/file-schema/wcf/behaviors.md) element.</span></span>

    2. <span data-ttu-id="b3ab9-133">[@No__t-3behaviors >](../../configure-apps/file-schema/wcf/behaviors.md)要素に[\< servicebehaviors >](../../configure-apps/file-schema/wcf/servicebehaviors.md)を追加します。</span><span class="sxs-lookup"><span data-stu-id="b3ab9-133">Add a [\<serviceBehaviors>](../../configure-apps/file-schema/wcf/servicebehaviors.md) to the [\<behaviors>](../../configure-apps/file-schema/wcf/behaviors.md) element.</span></span>

    3. <span data-ttu-id="b3ab9-134">[@No__t-1behavior >](../../configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md)要素を追加し、`name` 属性を適切な値に設定します。</span><span class="sxs-lookup"><span data-stu-id="b3ab9-134">Add a [\<behavior>](../../configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md) element and set the `name` attribute to an appropriate value.</span></span>

    4. <span data-ttu-id="b3ab9-135">[@No__t-3behavior >](../../configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md)要素に[\<serviceCredentials >](../../configure-apps/file-schema/wcf/servicecredentials.md)を追加します。</span><span class="sxs-lookup"><span data-stu-id="b3ab9-135">Add a [\<serviceCredentials>](../../configure-apps/file-schema/wcf/servicecredentials.md) to the [\<behavior>](../../configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md) element.</span></span>

    5. <span data-ttu-id="b3ab9-136">[@No__t-3serviceCredentials >](../../configure-apps/file-schema/wcf/servicecredentials.md)に[@no__t 1userNameAuthentication >](../../configure-apps/file-schema/wcf/usernameauthentication.md)を追加します。</span><span class="sxs-lookup"><span data-stu-id="b3ab9-136">Add a [\<userNameAuthentication>](../../configure-apps/file-schema/wcf/usernameauthentication.md) to the [\<serviceCredentials>](../../configure-apps/file-schema/wcf/servicecredentials.md).</span></span>

    6. <span data-ttu-id="b3ab9-137">`userNamePasswordValidationMode` を `Custom` に設定します。</span><span class="sxs-lookup"><span data-stu-id="b3ab9-137">Set the `userNamePasswordValidationMode` to `Custom`.</span></span>

        > [!IMPORTANT]
        > <span data-ttu-id="b3ab9-138">@No__t 0 の値が設定されていない場合、WCF ではカスタムユーザー名とパスワード検証コントロールではなく Windows 認証が使用されます。</span><span class="sxs-lookup"><span data-stu-id="b3ab9-138">If the `userNamePasswordValidationMode` value is not set, WCF uses Windows authentication instead of the custom user name and password validator.</span></span>

    7. <span data-ttu-id="b3ab9-139">`customUserNamePasswordValidatorType` を、カスタムのユーザー名/パスワード検証コントロールを表す型に設定します。</span><span class="sxs-lookup"><span data-stu-id="b3ab9-139">Set the `customUserNamePasswordValidatorType` to the type that represents your custom user name and password validator.</span></span>

    <span data-ttu-id="b3ab9-140">次の例は、このポイントまでの @no__t 0 のフラグメントを示しています。</span><span class="sxs-lookup"><span data-stu-id="b3ab9-140">The following example shows the `<serviceCredentials>` fragment to this point:</span></span>

    ```xml
    <serviceCredentials>
      <userNameAuthentication userNamePasswordValidationMode="Custom" customUserNamePasswordValidatorType="Microsoft.ServiceModel.Samples.CalculatorService.CustomUserNameValidator, service" />
    </serviceCredentials>
    ```

## <a name="example"></a><span data-ttu-id="b3ab9-141">例</span><span class="sxs-lookup"><span data-stu-id="b3ab9-141">Example</span></span>

<span data-ttu-id="b3ab9-142">カスタムのユーザー名/パスワード検証コントロールを作成する方法を次のコード例に示します。</span><span class="sxs-lookup"><span data-stu-id="b3ab9-142">The following code example demonstrates how to create a custom user name and password validator.</span></span> <span data-ttu-id="b3ab9-143">稼働環境では、<xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A> メソッドをオーバーライドするコードを使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="b3ab9-143">Do not use the code that overrides the <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A> method in a production environment.</span></span> <span data-ttu-id="b3ab9-144">このコードをカスタムのユーザー名/パスワード検証方式に置き換えます。この場合、ユーザー名とパスワードの組み合わせをデータベースから取得する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b3ab9-144">Replace the code with your custom user name and password validation scheme, which might involve retrieving user name and password pairs from a database.</span></span>

[!code-csharp[C_CustomUsernameAndPasswordValidator#1](~/samples/snippets/csharp/VS_Snippets_CFX/c_customusernameandpasswordvalidator/cs/service.cs#1)]
[!code-vb[C_CustomUsernameAndPasswordValidator#1](~/samples/snippets/visualbasic/VS_Snippets_CFX/c_customusernameandpasswordvalidator/vb/service.vb#1)]
[!code-csharp[C_CustomUsernameAndPasswordValidator#2](~/samples/snippets/csharp/VS_Snippets_CFX/c_customusernameandpasswordvalidator/cs/service.cs#2)]
[!code-vb[C_CustomUsernameAndPasswordValidator#2](~/samples/snippets/visualbasic/VS_Snippets_CFX/c_customusernameandpasswordvalidator/vb/service.vb#2)]

## <a name="see-also"></a><span data-ttu-id="b3ab9-145">関連項目</span><span class="sxs-lookup"><span data-stu-id="b3ab9-145">See also</span></span>

- <xref:System.IdentityModel.Selectors.UserNamePasswordValidator>
- <span data-ttu-id="b3ab9-146">[2 つのオブジェクトが等しいかどうかをテストする方法ASP.NET メンバーシッププロバイダーを使用する @ no__t-0</span><span class="sxs-lookup"><span data-stu-id="b3ab9-146">[How to: Use the ASP.NET Membership Provider](how-to-use-the-aspnet-membership-provider.md)</span></span>
- <span data-ttu-id="b3ab9-147">[\[認証]](authentication-in-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="b3ab9-147">[Authentication](authentication-in-wcf.md)</span></span>
