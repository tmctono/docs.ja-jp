---
title: '方法: ASP.NET メンバーシップ プロバイダーを使用する'
ms.date: 03/30/2017
helpviewer_keywords:
- WCF and ASP.NET
- WCF, authorization
- WCF, security
ms.assetid: 322c56e0-938f-4f19-a981-7b6530045b90
ms.openlocfilehash: 840e4a5d365f2adbaf335c1061a580665a39824d
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84595324"
---
# <a name="how-to-use-the-aspnet-membership-provider"></a><span data-ttu-id="a8c00-102">方法: ASP.NET メンバーシップ プロバイダーを使用する</span><span class="sxs-lookup"><span data-stu-id="a8c00-102">How to: Use the ASP.NET Membership Provider</span></span>

<span data-ttu-id="a8c00-103">ASP.NET メンバーシッププロバイダーは、ユーザーが一意のユーザー名とパスワードの組み合わせを作成できるようにする Web サイトを ASP.NET 開発者が作成できるようにする機能です。</span><span class="sxs-lookup"><span data-stu-id="a8c00-103">The ASP.NET membership provider is a feature that enables ASP.NET developers to create Web sites that allow users to create unique user name and password combinations.</span></span> <span data-ttu-id="a8c00-104">この機能を使用すれば、ユーザーはだれでもサイトでアカウントを作成し、そのサイトにサインインして、サービスに排他的にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="a8c00-104">With this facility, any user can establish an account with the site, and sign in for exclusive access to the site and its services.</span></span> <span data-ttu-id="a8c00-105">これは、ユーザーが Windows ドメイン内にアカウントを持っていることが必要な Windows セキュリティとは対照的です。</span><span class="sxs-lookup"><span data-stu-id="a8c00-105">This is in contrast to Windows security, which requires users to have accounts in a Windows domain.</span></span> <span data-ttu-id="a8c00-106">その代わりに、資格情報を提供するすべてのユーザー (ユーザー名とパスワードの組み合わせ) で、サイトとそのサービスを使用できます。</span><span class="sxs-lookup"><span data-stu-id="a8c00-106">Instead, any user that supplies their credentials (the user name/password combination) can use the site and its services.</span></span>

<span data-ttu-id="a8c00-107">サンプルアプリケーションについては、「[メンバーシップとロールプロバイダー](../samples/membership-and-role-provider.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a8c00-107">For a sample application, see [Membership and Role Provider](../samples/membership-and-role-provider.md).</span></span> <span data-ttu-id="a8c00-108">ASP.NET ロールプロバイダー機能の使用方法の詳細については、「 [How to: Use the ASP.NET Role provider with a Service](how-to-use-the-aspnet-role-provider-with-a-service.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a8c00-108">For information about using the ASP.NET role provider feature, see [How to: Use the ASP.NET Role Provider with a Service](how-to-use-the-aspnet-role-provider-with-a-service.md).</span></span>

<span data-ttu-id="a8c00-109">メンバーシップ機能では、SQL Server データベースを使用してユーザー情報を格納する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a8c00-109">The membership feature requires using a SQL Server database to store the user information.</span></span> <span data-ttu-id="a8c00-110">メンバーシップ機能には、パスワードを忘れたユーザーへの質問を行うためのメソッドも含まれています。</span><span class="sxs-lookup"><span data-stu-id="a8c00-110">The feature also includes methods for prompting with a question any users who have forgotten their password.</span></span>

<span data-ttu-id="a8c00-111">Windows Communication Foundation (WCF) 開発者は、これらの機能をセキュリティ上の目的で利用できます。</span><span class="sxs-lookup"><span data-stu-id="a8c00-111">Windows Communication Foundation (WCF) developers can take advantage of these features for security purposes.</span></span> <span data-ttu-id="a8c00-112">WCF アプリケーションに統合されている場合、ユーザーは、WCF クライアントアプリケーションに対してユーザー名とパスワードの組み合わせを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a8c00-112">When integrated into an WCF application, users must supply a user name/password combination to the WCF client application.</span></span> <span data-ttu-id="a8c00-113">WCF サービスにデータを転送するには、ユーザー名とパスワードの資格情報 (構成では) をサポートするバインディングを使用して、 <xref:System.ServiceModel.WSHttpBinding> [\<wsHttpBinding>](../../configure-apps/file-schema/wcf/wshttpbinding.md) クライアント資格情報の種類をに設定し `UserName` ます。</span><span class="sxs-lookup"><span data-stu-id="a8c00-113">To transfer the data to the WCF service, use a binding that supports user name/password credentials, such as the <xref:System.ServiceModel.WSHttpBinding> (in configuration, the [\<wsHttpBinding>](../../configure-apps/file-schema/wcf/wshttpbinding.md)) and set the client credential type to `UserName`.</span></span> <span data-ttu-id="a8c00-114">サービスでは、WCF セキュリティはユーザー名とパスワードに基づいてユーザーを認証し、ASP.NET ロールによって指定されたロールも割り当てます。</span><span class="sxs-lookup"><span data-stu-id="a8c00-114">On the service, WCF security authenticates the user based on the user name and password, and also assigns the role specified by the ASP.NET role.</span></span>

> [!NOTE]
> <span data-ttu-id="a8c00-115">WCF には、ユーザー名とパスワードの組み合わせ、またはその他のユーザー情報をデータベースに設定するメソッドは用意されていません。</span><span class="sxs-lookup"><span data-stu-id="a8c00-115">WCF does not provide methods to populate the database with user name/password combinations or other user information.</span></span>

### <a name="to-configure-the-membership-provider"></a><span data-ttu-id="a8c00-116">メンバーシップ プロバイダーを構成するには</span><span class="sxs-lookup"><span data-stu-id="a8c00-116">To configure the membership provider</span></span>

1. <span data-ttu-id="a8c00-117">Web.config ファイルの < > 要素の下に `system.web` < `membership` > 要素を作成します。</span><span class="sxs-lookup"><span data-stu-id="a8c00-117">In the Web.config file, under the <`system.web`> element, create a <`membership`> element.</span></span>

2. <span data-ttu-id="a8c00-118">`<membership>` 要素を作成します。</span><span class="sxs-lookup"><span data-stu-id="a8c00-118">Under the `<membership>` element, create a `<providers>` element.</span></span>

3. <span data-ttu-id="a8c00-119"><> 要素の子として `providers` 、 `<clear />` プロバイダーのコレクションをフラッシュする要素を追加します。</span><span class="sxs-lookup"><span data-stu-id="a8c00-119">As a child to the <`providers`> element, add a `<clear />` element to flush the collection of providers.</span></span>

4. <span data-ttu-id="a8c00-120">要素の下に、、、、、、、、、 `<clear />` `add` `name` `type` `connectionStringName` `applicationName` `enablePasswordRetrieval` `enablePasswordReset` `requiresQuestionAndAnswer` `requiresUniqueEmail` および `passwordFormat` の各属性を適切な値に設定して、<の> 要素を作成します。</span><span class="sxs-lookup"><span data-stu-id="a8c00-120">Under the `<clear />` element, create an <`add`> element with the following attributes set to appropriate values: `name`, `type`, `connectionStringName`, `applicationName`, `enablePasswordRetrieval`, `enablePasswordReset`, `requiresQuestionAndAnswer`, `requiresUniqueEmail`, and `passwordFormat`.</span></span> <span data-ttu-id="a8c00-121">`name` 属性は、構成ファイルの値として後で使用します。</span><span class="sxs-lookup"><span data-stu-id="a8c00-121">The `name` attribute is used later as a value in the configuration file.</span></span> <span data-ttu-id="a8c00-122">`SqlMembershipProvider` に設定する方法の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="a8c00-122">The following example sets it to `SqlMembershipProvider`.</span></span>

    <span data-ttu-id="a8c00-123">次の例は構成セクションを示します。</span><span class="sxs-lookup"><span data-stu-id="a8c00-123">The following example shows the configuration section.</span></span>

    ```xml
    <!-- Configure the Sql Membership Provider -->
    <membership defaultProvider="SqlMembershipProvider" userIsOnlineTimeWindow="15">
      <providers>
        <clear />
          <add
            name="SqlMembershipProvider"
            type="System.Web.Security.SqlMembershipProvider"
            connectionStringName="SqlConn"
            applicationName="MembershipAndRoleProviderSample"
            enablePasswordRetrieval="false"
            enablePasswordReset="false"
            requiresQuestionAndAnswer="false"
            requiresUniqueEmail="true"
            passwordFormat="Hashed" />
      </providers>
    </membership>
    ```

### <a name="to-configure-service-security-to-accept-the-user-namepassword-combination"></a><span data-ttu-id="a8c00-124">ユーザー名/パスワードの組み合わせを受け入れるようにサービス セキュリティを構成するには</span><span class="sxs-lookup"><span data-stu-id="a8c00-124">To configure service security to accept the user name/password combination</span></span>

1. <span data-ttu-id="a8c00-125">構成ファイルの要素の下に [\<system.serviceModel>](../../configure-apps/file-schema/wcf/system-servicemodel.md) 要素を追加 [\<bindings>](../../configure-apps/file-schema/wcf/bindings.md) します。</span><span class="sxs-lookup"><span data-stu-id="a8c00-125">In the configuration file, under the [\<system.serviceModel>](../../configure-apps/file-schema/wcf/system-servicemodel.md) element, add a [\<bindings>](../../configure-apps/file-schema/wcf/bindings.md) element.</span></span>

2. <span data-ttu-id="a8c00-126">[\<wsHttpBinding>](../../configure-apps/file-schema/wcf/wshttpbinding.md)バインドセクションにを追加します。</span><span class="sxs-lookup"><span data-stu-id="a8c00-126">Add a [\<wsHttpBinding>](../../configure-apps/file-schema/wcf/wshttpbinding.md) to the bindings section.</span></span> <span data-ttu-id="a8c00-127">WCF バインド要素の作成の詳細については、「[方法: 構成でサービスバインディングを指定](../how-to-specify-a-service-binding-in-configuration.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a8c00-127">For more information about creating an WCF binding element, see [How to: Specify a Service Binding in Configuration](../how-to-specify-a-service-binding-in-configuration.md).</span></span>

3. <span data-ttu-id="a8c00-128">`mode` 要素の `<security>` 属性を `Message` に設定します。</span><span class="sxs-lookup"><span data-stu-id="a8c00-128">Set the `mode` attribute of the `<security>` element to `Message`.</span></span>

4. <span data-ttu-id="a8c00-129">`clientCredentialType`<`message`> 要素の属性をに設定 `UserName` します。</span><span class="sxs-lookup"><span data-stu-id="a8c00-129">Set the `clientCredentialType` attribute of the <`message`> element to `UserName`.</span></span> <span data-ttu-id="a8c00-130">これにより、ユーザー名/パスワードの組み合わせがクライアントの資格情報として使用されるようになります。</span><span class="sxs-lookup"><span data-stu-id="a8c00-130">This specifies that a user name/password pair will be used as the client's credential.</span></span>

    <span data-ttu-id="a8c00-131">次のコード例は、バインディングの構成コードを示しています。</span><span class="sxs-lookup"><span data-stu-id="a8c00-131">The following example shows the configuration code for the binding.</span></span>

    ```xml
    <system.serviceModel>
    <bindings>
      <wsHttpBinding>
      <!-- Set up a binding that uses UserName as the client credential type -->
        <binding name="MembershipBinding">
          <security mode ="Message">
            <message clientCredentialType ="UserName"/>
          </security>
        </binding>
      </wsHttpBinding>
    </bindings>
    </system.serviceModel>
    ```

### <a name="to-configure-a-service-to-use-the-membership-provider"></a><span data-ttu-id="a8c00-132">メンバーシップ プロバイダーを使用するようにサービスを構成するには</span><span class="sxs-lookup"><span data-stu-id="a8c00-132">To configure a service to use the membership provider</span></span>

1. <span data-ttu-id="a8c00-133">要素の子として `<system.serviceModel>` 、要素を追加します。 [\<behaviors>](../../configure-apps/file-schema/wcf/behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="a8c00-133">As a child to the `<system.serviceModel>` element, add a [\<behaviors>](../../configure-apps/file-schema/wcf/behaviors.md) element</span></span>

2. <span data-ttu-id="a8c00-134">[\<serviceBehaviors>](../../configure-apps/file-schema/wcf/servicebehaviors.md)<> 要素にを追加 `behaviors` します。</span><span class="sxs-lookup"><span data-stu-id="a8c00-134">Add a [\<serviceBehaviors>](../../configure-apps/file-schema/wcf/servicebehaviors.md) to the <`behaviors`> element.</span></span>

3. <span data-ttu-id="a8c00-135">を追加 [\<behavior>](../../configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) し、 `name` 属性を適切な値に設定します。</span><span class="sxs-lookup"><span data-stu-id="a8c00-135">Add a [\<behavior>](../../configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) and set the `name` attribute to an appropriate value.</span></span>

4. <span data-ttu-id="a8c00-136">[\<serviceCredentials>](../../configure-apps/file-schema/wcf/servicecredentials.md)<> 要素にを追加 `behavior` します。</span><span class="sxs-lookup"><span data-stu-id="a8c00-136">Add a [\<serviceCredentials>](../../configure-apps/file-schema/wcf/servicecredentials.md) to the <`behavior`> element.</span></span>

5. <span data-ttu-id="a8c00-137">を [\<userNameAuthentication>](../../configure-apps/file-schema/wcf/usernameauthentication.md) 要素に追加し `<serviceCredentials>` ます。</span><span class="sxs-lookup"><span data-stu-id="a8c00-137">Add a [\<userNameAuthentication>](../../configure-apps/file-schema/wcf/usernameauthentication.md) to the `<serviceCredentials>` element.</span></span>

6. <span data-ttu-id="a8c00-138">`userNamePasswordValidationMode` 属性を `MembershipProvider` に設定します。</span><span class="sxs-lookup"><span data-stu-id="a8c00-138">Set the `userNamePasswordValidationMode` attribute to `MembershipProvider`.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="a8c00-139">`userNamePasswordValidationMode`値が設定されていない場合、WCF は ASP.NET メンバーシッププロバイダーの代わりに Windows 認証を使用します。</span><span class="sxs-lookup"><span data-stu-id="a8c00-139">If the `userNamePasswordValidationMode` value is not set, WCF uses Windows authentication instead of the ASP.NET membership provider.</span></span>

7. <span data-ttu-id="a8c00-140">`membershipProviderName` 属性をプロバイダーの名前 (このトピックの最初の手順でプロバイダーを追加したときに指定したもの) に設定します。</span><span class="sxs-lookup"><span data-stu-id="a8c00-140">Set the `membershipProviderName` attribute to the name of the provider (specified when adding the provider in the first procedure in this topic).</span></span> <span data-ttu-id="a8c00-141">次の例に、この時点での `<serviceCredentials>` のフラグメントを示します。</span><span class="sxs-lookup"><span data-stu-id="a8c00-141">The following example shows the `<serviceCredentials>` fragment to this point.</span></span>

    ```xml
    <behaviors>
       <serviceBehaviors>
          <behavior name="MyServiceBehavior">
             <serviceCredentials>
                <userNameAuthentication
                userNamePasswordValidationMode="MembershipProvider"
                membershipProviderName="SqlMembershipProvider" />
             </serviceCredentials>
          </behavior>
       </serviceBehaviors>
    </behaviors>
    ```

## <a name="example"></a><span data-ttu-id="a8c00-142">例</span><span class="sxs-lookup"><span data-stu-id="a8c00-142">Example</span></span>

<span data-ttu-id="a8c00-143">次のコードは、ASP メンバーシップ機能を使用するサービスの構成を示します。</span><span class="sxs-lookup"><span data-stu-id="a8c00-143">The following code shows the configuration for a service that uses the ASP membership feature.</span></span>

```xml
<?xml version="1.0" encoding="utf-8" ?>
<configuration>
  <system.serviceModel>
    <services>
      <service behaviorConfiguration="MyServiceBehavior" name="Microsoft.Samples.GettingStarted.CalculatorService">
        <endpoint address="http://microsoft.com/WCFservices/Calculator"
          binding="wsHttpBinding" bindingConfiguration="MembershipBinding"
          name="ASPmemberUserName" contract="Microsoft.Samples.GettingStarted.ICalculator" />
      </service>
    </services>
    <behaviors>
      <serviceBehaviors>
        <behavior name="MyServiceBehavior">
          <serviceCredentials>
            <userNameAuthentication
              userNamePasswordValidationMode="MembershipProvider"
              membershipProviderName="SqlMembershipProvider" />
          </serviceCredentials>
        </behavior>
          </serviceBehaviors>
    </behaviors>
    <bindings>
      <wsHttpBinding>
        <binding name="MembershipBinding">
          <security mode="Message">
            <message clientCredentialType="UserName" />
          </security>
        </binding>
      </wsHttpBinding>
    </bindings>
  </system.serviceModel>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="a8c00-144">関連項目</span><span class="sxs-lookup"><span data-stu-id="a8c00-144">See also</span></span>

- [<span data-ttu-id="a8c00-145">方法: ASP.NET のロール プロバイダーとサービスを使用する</span><span class="sxs-lookup"><span data-stu-id="a8c00-145">How to: Use the ASP.NET Role Provider with a Service</span></span>](how-to-use-the-aspnet-role-provider-with-a-service.md)
- [<span data-ttu-id="a8c00-146">メンバーシップとロール プロバイダー</span><span class="sxs-lookup"><span data-stu-id="a8c00-146">Membership and Role Provider</span></span>](../samples/membership-and-role-provider.md)
