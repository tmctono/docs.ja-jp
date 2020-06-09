---
title: '方法: カスタム ユーザー名およびパスワード検証を使用する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF, username and password
ms.assetid: 8e08b74b-fa44-4018-b63d-0d0805f85e3f
ms.openlocfilehash: 5ada34ca2d0d757ea333fed60aef179d6578356c
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84601180"
---
# <a name="how-to-use-a-custom-user-name-and-password-validator"></a><span data-ttu-id="191cb-102">方法: カスタム ユーザー名およびパスワード検証を使用する</span><span class="sxs-lookup"><span data-stu-id="191cb-102">How to: Use a Custom User Name and Password Validator</span></span>

<span data-ttu-id="191cb-103">既定では、ユーザー名とパスワードが認証に使用されると、Windows Communication Foundation (WCF) は Windows を使用してユーザー名とパスワードを検証します。</span><span class="sxs-lookup"><span data-stu-id="191cb-103">By default, when a user name and password is used for authentication, Windows Communication Foundation (WCF) uses Windows to validate the user name and password.</span></span> <span data-ttu-id="191cb-104">ただし、WCF では、カスタムのユーザー名とパスワードの認証方式 (*検証コントロール*とも呼ばれます) を使用できます。</span><span class="sxs-lookup"><span data-stu-id="191cb-104">However, WCF allows for custom user name and password authentication schemes, also known as *validators*.</span></span> <span data-ttu-id="191cb-105">ユーザー名およびパスワードのカスタム検証を組み込むには、<xref:System.IdentityModel.Selectors.UserNamePasswordValidator> から派生するクラスを作成して構成します。</span><span class="sxs-lookup"><span data-stu-id="191cb-105">To incorporate a custom user name and password validator, create a class that derives from <xref:System.IdentityModel.Selectors.UserNamePasswordValidator> and then configure it.</span></span>

<span data-ttu-id="191cb-106">サンプルアプリケーションについては、「[ユーザー名パスワード検証コントロール](../samples/user-name-password-validator.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="191cb-106">For a sample application, see [User Name Password Validator](../samples/user-name-password-validator.md).</span></span>

### <a name="to-create-a-custom-user-name-and-password-validator"></a><span data-ttu-id="191cb-107">カスタムのユーザー名/パスワード検証コントロールを作成するには</span><span class="sxs-lookup"><span data-stu-id="191cb-107">To create a custom user name and password validator</span></span>

1. <span data-ttu-id="191cb-108"><xref:System.IdentityModel.Selectors.UserNamePasswordValidator> から派生するクラスを作成します。</span><span class="sxs-lookup"><span data-stu-id="191cb-108">Create a class that derives from <xref:System.IdentityModel.Selectors.UserNamePasswordValidator>.</span></span>

    [!code-csharp[C_CustomUsernameAndPasswordValidator#3](~/samples/snippets/csharp/VS_Snippets_CFX/c_customusernameandpasswordvalidator/cs/service.cs#3)]
    [!code-vb[C_CustomUsernameAndPasswordValidator#3](~/samples/snippets/visualbasic/VS_Snippets_CFX/c_customusernameandpasswordvalidator/vb/service.vb#3)]

2. <span data-ttu-id="191cb-109"><xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A> メソッドをオーバーライドして、カスタム認証方式を実装します。</span><span class="sxs-lookup"><span data-stu-id="191cb-109">Implement the custom authentication scheme by overriding the <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A> method.</span></span>

    <span data-ttu-id="191cb-110">次の例のコードは、<xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A> メソッドをオーバーライドします。稼働環境では、このようなコードを使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="191cb-110">Do not use the code in the following example that overrides the <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A> method in a production environment.</span></span> <span data-ttu-id="191cb-111">このコードをカスタムのユーザー名/パスワード検証方式に置き換えます。この場合、ユーザー名とパスワードの組み合わせをデータベースから取得する必要があります。</span><span class="sxs-lookup"><span data-stu-id="191cb-111">Replace the code with your custom user name and password validation scheme, which might involve retrieving user name and password pairs from a database.</span></span>

    <span data-ttu-id="191cb-112">クライアントに認証エラーを返すには、<xref:System.ServiceModel.FaultException> メソッドで <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A> をスローします。</span><span class="sxs-lookup"><span data-stu-id="191cb-112">To return authentication errors back to the client, throw a <xref:System.ServiceModel.FaultException> in the <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A> method.</span></span>

    [!code-csharp[C_CustomUsernameAndPasswordValidator#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customusernameandpasswordvalidator/cs/service.cs#4)]
    [!code-vb[C_CustomUsernameAndPasswordValidator#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customusernameandpasswordvalidator/vb/service.vb#4)]

### <a name="to-configure-a-service-to-use-a-custom-user-name-and-password-validator"></a><span data-ttu-id="191cb-113">カスタムのユーザー名/パスワード検証コントロールを使用するようにサービスを構成するには</span><span class="sxs-lookup"><span data-stu-id="191cb-113">To configure a service to use a custom user name and password validator</span></span>

1. <span data-ttu-id="191cb-114">任意のトランスポート上のメッセージ セキュリティ、または HTTP(S) 上のトランスポート レベル セキュリティを使用するバインディングを構成します。</span><span class="sxs-lookup"><span data-stu-id="191cb-114">Configure a binding that uses message security over any transport or transport-level security over HTTP(S).</span></span>

    <span data-ttu-id="191cb-115">メッセージセキュリティを使用する場合は、などのシステム指定のバインディング、 [\<wsHttpBinding>](../../configure-apps/file-schema/wcf/wshttpbinding.md) または [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md) メッセージセキュリティと資格情報の種類をサポートするのいずれかを追加し `UserName` ます。</span><span class="sxs-lookup"><span data-stu-id="191cb-115">When using message security, add one of the system-provided bindings, such as a  [\<wsHttpBinding>](../../configure-apps/file-schema/wcf/wshttpbinding.md), or a [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md) that supports message security and the `UserName` credential type.</span></span>

    <span data-ttu-id="191cb-116">HTTP (S) でトランスポートレベルのセキュリティを使用する場合は、 [\<wsHttpBinding>](../../configure-apps/file-schema/wcf/wshttpbinding.md) [\<basicHttpBinding>](../../configure-apps/file-schema/wcf/basichttpbinding.md) [\<netTcpBinding>](../../configure-apps/file-schema/wcf/nettcpbinding.md) [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md) http (s) と認証スキームを使用するまたはを追加し `Basic` ます。</span><span class="sxs-lookup"><span data-stu-id="191cb-116">When using transport-level security over HTTP(S), add either the [\<wsHttpBinding>](../../configure-apps/file-schema/wcf/wshttpbinding.md) or [\<basicHttpBinding>](../../configure-apps/file-schema/wcf/basichttpbinding.md), a [\<netTcpBinding>](../../configure-apps/file-schema/wcf/nettcpbinding.md) or a [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md) that uses HTTP(S) and the `Basic` authentication scheme.</span></span>

    > [!NOTE]
    > <span data-ttu-id="191cb-117">.NET Framework 3.5 以降のバージョンを使用する場合は、メッセージおよびトランスポートセキュリティと共にカスタムのユーザー名とパスワード検証を使用できます。</span><span class="sxs-lookup"><span data-stu-id="191cb-117">When using .NET Framework 3.5 or later versions, you can use a custom username and password validator with message and transport security.</span></span> <span data-ttu-id="191cb-118">WinFX では、カスタムのユーザー名とパスワード検証コントロールは、メッセージセキュリティでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="191cb-118">With WinFX, a custom username and password validator can only be used with message security.</span></span>

    > [!TIP]
    > <span data-ttu-id="191cb-119">このコンテキストでを使用する方法の詳細につい \<netTcpBinding> ては、「」を参照してください [\<security>](../../configure-apps/file-schema/wcf/security-of-nettcpbinding.md) 。</span><span class="sxs-lookup"><span data-stu-id="191cb-119">For more information on using \<netTcpBinding> in this context, see [\<security>](../../configure-apps/file-schema/wcf/security-of-nettcpbinding.md).</span></span>

    1. <span data-ttu-id="191cb-120">構成ファイルの要素の下に [\<system.serviceModel>](../../configure-apps/file-schema/wcf/system-servicemodel.md) 要素を追加 [\<bindings>](../../configure-apps/file-schema/wcf/bindings.md) します。</span><span class="sxs-lookup"><span data-stu-id="191cb-120">In the configuration file, under the [\<system.serviceModel>](../../configure-apps/file-schema/wcf/system-servicemodel.md) element, add a [\<bindings>](../../configure-apps/file-schema/wcf/bindings.md) element.</span></span>

    2. <span data-ttu-id="191cb-121">[\<wsHttpBinding>](../../configure-apps/file-schema/wcf/wshttpbinding.md)バインドセクションにまたは要素を追加し [\<basicHttpBinding>](../../configure-apps/file-schema/wcf/basichttpbinding.md) ます。</span><span class="sxs-lookup"><span data-stu-id="191cb-121">Add a [\<wsHttpBinding>](../../configure-apps/file-schema/wcf/wshttpbinding.md) or [\<basicHttpBinding>](../../configure-apps/file-schema/wcf/basichttpbinding.md) element to the bindings section.</span></span> <span data-ttu-id="191cb-122">WCF バインド要素の作成の詳細については、「[方法: 構成でサービスバインディングを指定](../how-to-specify-a-service-binding-in-configuration.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="191cb-122">For more information about creating an WCF binding element, see [How to: Specify a Service Binding in Configuration](../how-to-specify-a-service-binding-in-configuration.md).</span></span>

    3. <span data-ttu-id="191cb-123">`mode`またはの属性を [\<security>](../../configure-apps/file-schema/wcf/security-of-wshttpbinding.md) 、、、 [\<security>](../../configure-apps/file-schema/wcf/security-of-basichttpbinding.md) `Message` またはに設定 `Transport` `TransportWithMessageCredential` します。</span><span class="sxs-lookup"><span data-stu-id="191cb-123">Set the `mode` attribute of the [\<security>](../../configure-apps/file-schema/wcf/security-of-wshttpbinding.md) or [\<security>](../../configure-apps/file-schema/wcf/security-of-basichttpbinding.md) to `Message`, `Transport`, or `TransportWithMessageCredential`.</span></span>

    4. <span data-ttu-id="191cb-124">`clientCredentialType`またはの属性を設定し [\<message>](../../configure-apps/file-schema/wcf/message-of-wshttpbinding.md) [\<transport>](../../configure-apps/file-schema/wcf/transport-of-wshttpbinding.md) ます。</span><span class="sxs-lookup"><span data-stu-id="191cb-124">Set the `clientCredentialType` attribute of the [\<message>](../../configure-apps/file-schema/wcf/message-of-wshttpbinding.md) or [\<transport>](../../configure-apps/file-schema/wcf/transport-of-wshttpbinding.md).</span></span>

        <span data-ttu-id="191cb-125">メッセージセキュリティを使用する場合は、 `clientCredentialType` の属性を [\<message>](../../configure-apps/file-schema/wcf/message-of-wshttpbinding.md) に設定 `UserName` します。</span><span class="sxs-lookup"><span data-stu-id="191cb-125">When using message security, set the `clientCredentialType` attribute of the [\<message>](../../configure-apps/file-schema/wcf/message-of-wshttpbinding.md) to `UserName`.</span></span>

        <span data-ttu-id="191cb-126">HTTP (S) でトランスポートレベルのセキュリティを使用する場合 `clientCredentialType` は、またはの属性を [\<transport>](../../configure-apps/file-schema/wcf/transport-of-wshttpbinding.md) に設定 [\<transport>](../../configure-apps/file-schema/wcf/transport-of-basichttpbinding.md) `Basic` します。</span><span class="sxs-lookup"><span data-stu-id="191cb-126">When using transport-level security over HTTP(S), set the `clientCredentialType` attribute of the [\<transport>](../../configure-apps/file-schema/wcf/transport-of-wshttpbinding.md) or [\<transport>](../../configure-apps/file-schema/wcf/transport-of-basichttpbinding.md) to `Basic`.</span></span>

        > [!NOTE]
        > <span data-ttu-id="191cb-127">WCF サービスがトランスポートレベルのセキュリティを使用してインターネットインフォメーションサービス (IIS) でホストされていて、 <xref:System.ServiceModel.Security.UserNamePasswordServiceCredential.UserNamePasswordValidationMode%2A> プロパティがに設定されている場合 <xref:System.ServiceModel.Security.UserNamePasswordValidationMode.Custom> 、カスタム認証スキームは Windows 認証のサブセットを使用します。</span><span class="sxs-lookup"><span data-stu-id="191cb-127">When a WCF service is hosted in Internet Information Services (IIS) using transport-level security and the <xref:System.ServiceModel.Security.UserNamePasswordServiceCredential.UserNamePasswordValidationMode%2A> property is set to <xref:System.ServiceModel.Security.UserNamePasswordValidationMode.Custom>, the custom authentication scheme uses a subset of Windows authentication.</span></span> <span data-ttu-id="191cb-128">このシナリオでは、WCF がカスタム認証システムを呼び出す前に、IIS が Windows 認証を実行します。</span><span class="sxs-lookup"><span data-stu-id="191cb-128">That is because in this scenario, IIS performs Windows authentication prior to WCF invoking the custom authenticator.</span></span>

    <span data-ttu-id="191cb-129">WCF バインド要素の作成の詳細については、「[方法: 構成でサービスバインディングを指定](../how-to-specify-a-service-binding-in-configuration.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="191cb-129">For more information about creating an WCF binding element, see [How to: Specify a Service Binding in Configuration](../how-to-specify-a-service-binding-in-configuration.md).</span></span>

    <span data-ttu-id="191cb-130">次の例は、バインディングの構成コードを示しています。</span><span class="sxs-lookup"><span data-stu-id="191cb-130">The following example shows the configuration code for the binding:</span></span>

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

2. <span data-ttu-id="191cb-131">受信 <xref:System.IdentityModel.Tokens.UserNameSecurityToken> セキュリティ トークンのユーザー名とパスワードの組み合わせを検証する際に、カスタムのユーザー名/パスワード検証コントロールを使用することを指定する動作を構成します。</span><span class="sxs-lookup"><span data-stu-id="191cb-131">Configure a behavior that specifies that a custom user name and password validator is used to validate user name and password pairs for incoming <xref:System.IdentityModel.Tokens.UserNameSecurityToken> security tokens.</span></span>

    1. <span data-ttu-id="191cb-132">要素の子として [\<system.serviceModel>](../../configure-apps/file-schema/wcf/system-servicemodel.md) 、要素を追加し [\<behaviors>](../../configure-apps/file-schema/wcf/behaviors.md) ます。</span><span class="sxs-lookup"><span data-stu-id="191cb-132">As a child to the [\<system.serviceModel>](../../configure-apps/file-schema/wcf/system-servicemodel.md) element, add a [\<behaviors>](../../configure-apps/file-schema/wcf/behaviors.md) element.</span></span>

    2. <span data-ttu-id="191cb-133">を [\<serviceBehaviors>](../../configure-apps/file-schema/wcf/servicebehaviors.md) 要素に追加し [\<behaviors>](../../configure-apps/file-schema/wcf/behaviors.md) ます。</span><span class="sxs-lookup"><span data-stu-id="191cb-133">Add a [\<serviceBehaviors>](../../configure-apps/file-schema/wcf/servicebehaviors.md) to the [\<behaviors>](../../configure-apps/file-schema/wcf/behaviors.md) element.</span></span>

    3. <span data-ttu-id="191cb-134">要素を追加 [\<behavior>](../../configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md) し、 `name` 属性を適切な値に設定します。</span><span class="sxs-lookup"><span data-stu-id="191cb-134">Add a [\<behavior>](../../configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md) element and set the `name` attribute to an appropriate value.</span></span>

    4. <span data-ttu-id="191cb-135">を [\<serviceCredentials>](../../configure-apps/file-schema/wcf/servicecredentials.md) 要素に追加し [\<behavior>](../../configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md) ます。</span><span class="sxs-lookup"><span data-stu-id="191cb-135">Add a [\<serviceCredentials>](../../configure-apps/file-schema/wcf/servicecredentials.md) to the [\<behavior>](../../configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md) element.</span></span>

    5. <span data-ttu-id="191cb-136">を [\<userNameAuthentication>](../../configure-apps/file-schema/wcf/usernameauthentication.md) に追加し [\<serviceCredentials>](../../configure-apps/file-schema/wcf/servicecredentials.md) ます。</span><span class="sxs-lookup"><span data-stu-id="191cb-136">Add a [\<userNameAuthentication>](../../configure-apps/file-schema/wcf/usernameauthentication.md) to the [\<serviceCredentials>](../../configure-apps/file-schema/wcf/servicecredentials.md).</span></span>

    6. <span data-ttu-id="191cb-137">`userNamePasswordValidationMode` を `Custom` に設定します。</span><span class="sxs-lookup"><span data-stu-id="191cb-137">Set the `userNamePasswordValidationMode` to `Custom`.</span></span>

        > [!IMPORTANT]
        > <span data-ttu-id="191cb-138">`userNamePasswordValidationMode`値が設定されていない場合、WCF はカスタムユーザー名とパスワード検証コントロールではなく Windows 認証を使用します。</span><span class="sxs-lookup"><span data-stu-id="191cb-138">If the `userNamePasswordValidationMode` value is not set, WCF uses Windows authentication instead of the custom user name and password validator.</span></span>

    7. <span data-ttu-id="191cb-139">`customUserNamePasswordValidatorType` を、カスタムのユーザー名/パスワード検証コントロールを表す型に設定します。</span><span class="sxs-lookup"><span data-stu-id="191cb-139">Set the `customUserNamePasswordValidatorType` to the type that represents your custom user name and password validator.</span></span>

    <span data-ttu-id="191cb-140">次の例は、 `<serviceCredentials>` この点を示すフラグメントを示しています。</span><span class="sxs-lookup"><span data-stu-id="191cb-140">The following example shows the `<serviceCredentials>` fragment to this point:</span></span>

    ```xml
    <serviceCredentials>
      <userNameAuthentication userNamePasswordValidationMode="Custom" customUserNamePasswordValidatorType="Microsoft.ServiceModel.Samples.CalculatorService.CustomUserNameValidator, service" />
    </serviceCredentials>
    ```

## <a name="example"></a><span data-ttu-id="191cb-141">例</span><span class="sxs-lookup"><span data-stu-id="191cb-141">Example</span></span>

<span data-ttu-id="191cb-142">カスタムのユーザー名/パスワード検証コントロールを作成する方法を次のコード例に示します。</span><span class="sxs-lookup"><span data-stu-id="191cb-142">The following code example demonstrates how to create a custom user name and password validator.</span></span> <span data-ttu-id="191cb-143">稼働環境では、<xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A> メソッドをオーバーライドするコードを使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="191cb-143">Do not use the code that overrides the <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A> method in a production environment.</span></span> <span data-ttu-id="191cb-144">このコードをカスタムのユーザー名/パスワード検証方式に置き換えます。この場合、ユーザー名とパスワードの組み合わせをデータベースから取得する必要があります。</span><span class="sxs-lookup"><span data-stu-id="191cb-144">Replace the code with your custom user name and password validation scheme, which might involve retrieving user name and password pairs from a database.</span></span>

[!code-csharp[C_CustomUsernameAndPasswordValidator#1](~/samples/snippets/csharp/VS_Snippets_CFX/c_customusernameandpasswordvalidator/cs/service.cs#1)]
[!code-vb[C_CustomUsernameAndPasswordValidator#1](~/samples/snippets/visualbasic/VS_Snippets_CFX/c_customusernameandpasswordvalidator/vb/service.vb#1)]
[!code-csharp[C_CustomUsernameAndPasswordValidator#2](~/samples/snippets/csharp/VS_Snippets_CFX/c_customusernameandpasswordvalidator/cs/service.cs#2)]
[!code-vb[C_CustomUsernameAndPasswordValidator#2](~/samples/snippets/visualbasic/VS_Snippets_CFX/c_customusernameandpasswordvalidator/vb/service.vb#2)]

## <a name="see-also"></a><span data-ttu-id="191cb-145">関連項目</span><span class="sxs-lookup"><span data-stu-id="191cb-145">See also</span></span>

- <xref:System.IdentityModel.Selectors.UserNamePasswordValidator>
- [<span data-ttu-id="191cb-146">方法: ASP.NET メンバーシップ プロバイダーを使用する</span><span class="sxs-lookup"><span data-stu-id="191cb-146">How to: Use the ASP.NET Membership Provider</span></span>](how-to-use-the-aspnet-membership-provider.md)
- [<span data-ttu-id="191cb-147">認証</span><span class="sxs-lookup"><span data-stu-id="191cb-147">Authentication</span></span>](authentication-in-wcf.md)
