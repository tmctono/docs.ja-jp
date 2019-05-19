---
title: '方法: ASP.NET メンバーシップ プロバイダーを使用する'
ms.date: 03/30/2017
helpviewer_keywords:
- WCF and ASP.NET
- WCF, authorization
- WCF, security
ms.assetid: 322c56e0-938f-4f19-a981-7b6530045b90
ms.openlocfilehash: 61324bbc5ea07dd19e23589bfc90f9ea44a6b331
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2019
ms.locfileid: "65880185"
---
# <a name="how-to-use-the-aspnet-membership-provider"></a><span data-ttu-id="911d1-102">方法: ASP.NET メンバーシップ プロバイダーを使用する</span><span class="sxs-lookup"><span data-stu-id="911d1-102">How to: Use the ASP.NET Membership Provider</span></span>
<span data-ttu-id="911d1-103">ASP.NET メンバーシップ プロバイダーは、ASP.NET 開発者ユーザー名とパスワードの組み合わせを作成するには、一意のユーザーに許可する Web サイトを作成することができる機能です。</span><span class="sxs-lookup"><span data-stu-id="911d1-103">The ASP.NET membership provider is a feature that enables ASP.NET developers to create Web sites that allow users to create unique user name and password combinations.</span></span> <span data-ttu-id="911d1-104">この機能を使用すれば、ユーザーはだれでもサイトでアカウントを作成し、そのサイトにサインインして、サービスに排他的にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="911d1-104">With this facility, any user can establish an account with the site, and sign in for exclusive access to the site and its services.</span></span> <span data-ttu-id="911d1-105">これは、ユーザーが Windows ドメイン内にアカウントを持っていることが必要な Windows セキュリティとは対照的です。</span><span class="sxs-lookup"><span data-stu-id="911d1-105">This is in contrast to Windows security, which requires users to have accounts in a Windows domain.</span></span> <span data-ttu-id="911d1-106">自分の資格情報 (ユーザー名とパスワードの組み合わせ) を提示したユーザーは、だれでもサイトとそのサービスを使用できるからです。</span><span class="sxs-lookup"><span data-stu-id="911d1-106">Instead, any user that supplies his or her credentials (the user name/password combination) can use the site and its services.</span></span>  
  
 <span data-ttu-id="911d1-107">サンプル アプリケーションについては「[メンバーシップとロール プロバイダー](../../../../docs/framework/wcf/samples/membership-and-role-provider.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="911d1-107">For a sample application, see [Membership and Role Provider](../../../../docs/framework/wcf/samples/membership-and-role-provider.md).</span></span> <span data-ttu-id="911d1-108">ASP.NET ロール プロバイダー機能の使用方法の詳細については、次を参照してください。[方法。ASP.NET ロール プロバイダーを使用して、サービスと](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md)します。</span><span class="sxs-lookup"><span data-stu-id="911d1-108">For information about using the ASP.NET role provider feature, see [How to: Use the ASP.NET Role Provider with a Service](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md).</span></span>  
  
 <span data-ttu-id="911d1-109">メンバーシップ機能では、SQL Server データベースを使用してユーザー情報を格納する必要があります。</span><span class="sxs-lookup"><span data-stu-id="911d1-109">The membership feature requires using a SQL Server database to store the user information.</span></span> <span data-ttu-id="911d1-110">メンバーシップ機能には、パスワードを忘れたユーザーへの質問を行うためのメソッドも含まれています。</span><span class="sxs-lookup"><span data-stu-id="911d1-110">The feature also includes methods for prompting with a question any users who have forgotten their password.</span></span>  
  
 <span data-ttu-id="911d1-111">Windows Communication Foundation (WCF) 開発者は、これらの機能のセキュリティの目的で利用できます。</span><span class="sxs-lookup"><span data-stu-id="911d1-111">Windows Communication Foundation (WCF) developers can take advantage of these features for security purposes.</span></span> <span data-ttu-id="911d1-112">WCF アプリケーションに統合すると、ユーザーは、WCF クライアント アプリケーションにユーザー名/パスワードの組み合わせを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="911d1-112">When integrated into an WCF application, users must supply a user name/password combination to the WCF client application.</span></span> <span data-ttu-id="911d1-113">WCF サービスにデータを転送するには、ユーザー名/パスワードの資格情報をサポートするバインディングを <xref:System.ServiceModel.WSHttpBinding> (構成では、 [\<wsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)) として使用して、クライアントの資格情報の種類を `UserName` に設定します。</span><span class="sxs-lookup"><span data-stu-id="911d1-113">To transfer the data to the WCF service, use a binding that supports user name/password credentials, such as the <xref:System.ServiceModel.WSHttpBinding> (in configuration, the [\<wsHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)) and set the client credential type to `UserName`.</span></span> <span data-ttu-id="911d1-114">サービスでは、WCF のセキュリティは、ユーザー名とパスワードに基づいてユーザーを認証し、ASP.NET のロールで指定されたロールを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="911d1-114">On the service, WCF security authenticates the user based on the user name and password, and also assigns the role specified by the ASP.NET role.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="911d1-115">WCF では、ユーザー名/パスワードの組み合わせを使用してデータベースまたは他のユーザー情報を格納するメソッドは提供されません。</span><span class="sxs-lookup"><span data-stu-id="911d1-115">WCF does not provide methods to populate the database with user name/password combinations or other user information.</span></span>  
  
### <a name="to-configure-the-membership-provider"></a><span data-ttu-id="911d1-116">メンバーシップ プロバイダーを構成するには</span><span class="sxs-lookup"><span data-stu-id="911d1-116">To configure the membership provider</span></span>  
  
1. <span data-ttu-id="911d1-117">Web.config ファイルで、<`system.web`> 要素の下に、<`membership`> 要素を作成します。</span><span class="sxs-lookup"><span data-stu-id="911d1-117">In the Web.config file, under the <`system.web`> element, create a <`membership`> element.</span></span>  
  
2. <span data-ttu-id="911d1-118">`<membership>` 要素の下に、`<providers>` 要素を作成します。</span><span class="sxs-lookup"><span data-stu-id="911d1-118">Under the `<membership>` element, create a `<providers>` element.</span></span>  
  
3. <span data-ttu-id="911d1-119">子として、<`providers`> 要素を追加、`<clear />`プロバイダーのコレクションをフラッシュする要素。</span><span class="sxs-lookup"><span data-stu-id="911d1-119">As a child to the <`providers`> element, add a `<clear />` element to flush the collection of providers.</span></span>  
  
4. <span data-ttu-id="911d1-120">下、`<clear />`要素を作成、<`add`> 次の属性を持つ要素が適切な値に設定: `name`、 `type`、 `connectionStringName`、 `applicationName`、 `enablePasswordRetrieval`、 `enablePasswordReset`、 `requiresQuestionAndAnswer`、 `requiresUniqueEmail`、および`passwordFormat`します。</span><span class="sxs-lookup"><span data-stu-id="911d1-120">Under the `<clear />` element, create an <`add`> element with the following attributes set to appropriate values: `name`, `type`, `connectionStringName`, `applicationName`, `enablePasswordRetrieval`, `enablePasswordReset`, `requiresQuestionAndAnswer`, `requiresUniqueEmail`, and `passwordFormat`.</span></span> <span data-ttu-id="911d1-121">`name` 属性は、構成ファイルの値として後で使用します。</span><span class="sxs-lookup"><span data-stu-id="911d1-121">The `name` attribute is used later as a value in the configuration file.</span></span> <span data-ttu-id="911d1-122">`SqlMembershipProvider` に設定する方法の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="911d1-122">The following example sets it to `SqlMembershipProvider`.</span></span>  
  
     <span data-ttu-id="911d1-123">次の例は構成セクションを示します。</span><span class="sxs-lookup"><span data-stu-id="911d1-123">The following example shows the configuration section.</span></span>  
  
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
  
### <a name="to-configure-service-security-to-accept-the-user-namepassword-combination"></a><span data-ttu-id="911d1-124">ユーザー名/パスワードの組み合わせを受け入れるようにサービス セキュリティを構成するには</span><span class="sxs-lookup"><span data-stu-id="911d1-124">To configure service security to accept the user name/password combination</span></span>  
  
1. <span data-ttu-id="911d1-125">構成ファイルでの下、 [ \<system.serviceModel >](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)要素を追加、 [\<バインド >](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)要素。</span><span class="sxs-lookup"><span data-stu-id="911d1-125">In the configuration file, under the [\<system.serviceModel>](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) element, add a [\<bindings>](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) element.</span></span>  
  
2. <span data-ttu-id="911d1-126">追加、 [ \<wsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)をバインディング セクション。</span><span class="sxs-lookup"><span data-stu-id="911d1-126">Add a [\<wsHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) to the bindings section.</span></span> <span data-ttu-id="911d1-127">WCF のバインド要素を作成する方法の詳細については、次を参照してください。[方法。構成でサービス バインディング指定](../../../../docs/framework/wcf/how-to-specify-a-service-binding-in-configuration.md)します。</span><span class="sxs-lookup"><span data-stu-id="911d1-127">For more information about creating an WCF binding element, see [How to: Specify a Service Binding in Configuration](../../../../docs/framework/wcf/how-to-specify-a-service-binding-in-configuration.md).</span></span>  
  
3. <span data-ttu-id="911d1-128">`mode` 要素の `<security>` 属性を `Message` に設定します。</span><span class="sxs-lookup"><span data-stu-id="911d1-128">Set the `mode` attribute of the `<security>` element to `Message`.</span></span>  
  
4. <span data-ttu-id="911d1-129">設定、`clientCredentialType`の属性、<`message`> 要素を`UserName`します。</span><span class="sxs-lookup"><span data-stu-id="911d1-129">Set the `clientCredentialType` attribute of the <`message`> element to `UserName`.</span></span> <span data-ttu-id="911d1-130">これにより、ユーザー名/パスワードの組み合わせがクライアントの資格情報として使用されるようになります。</span><span class="sxs-lookup"><span data-stu-id="911d1-130">This specifies that a user name/password pair will be used as the client's credential.</span></span>  
  
     <span data-ttu-id="911d1-131">次のコード例は、バインディングの構成コードを示しています。</span><span class="sxs-lookup"><span data-stu-id="911d1-131">The following example shows the configuration code for the binding.</span></span>  
  
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
  
### <a name="to-configure-a-service-to-use-the-membership-provider"></a><span data-ttu-id="911d1-132">メンバーシップ プロバイダーを使用するようにサービスを構成するには</span><span class="sxs-lookup"><span data-stu-id="911d1-132">To configure a service to use the membership provider</span></span>  
  
1. <span data-ttu-id="911d1-133">`<system.serviceModel>`要素の子として [\<behaviors>](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) 要素を追加</span><span class="sxs-lookup"><span data-stu-id="911d1-133">As a child to the `<system.serviceModel>` element, add a [\<behaviors>](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) element</span></span>  
  
2. <span data-ttu-id="911d1-134">追加、 [ \<serviceBehaviors >](../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md)に、<`behaviors`> 要素。</span><span class="sxs-lookup"><span data-stu-id="911d1-134">Add a [\<serviceBehaviors>](../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md) to the <`behaviors`> element.</span></span>  
  
3. <span data-ttu-id="911d1-135">[\<behavior>](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) を追加し、`name` 属性に適切な値を設定</span><span class="sxs-lookup"><span data-stu-id="911d1-135">Add a [\<behavior>](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) and set the `name` attribute to an appropriate value.</span></span>  
  
4. <span data-ttu-id="911d1-136">``behavior`` 要素に [\<serviceCredentials>](../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md) を追加</span><span class="sxs-lookup"><span data-stu-id="911d1-136">Add a [\<serviceCredentials>](../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md) to the <`behavior`> element.</span></span>  
  
5. <span data-ttu-id="911d1-137">``<serviceCredentials>`` 要素に [\<userNameAuthentication>](../../../../docs/framework/configure-apps/file-schema/wcf/usernameauthentication.md) を追加</span><span class="sxs-lookup"><span data-stu-id="911d1-137">Add a [\<userNameAuthentication>](../../../../docs/framework/configure-apps/file-schema/wcf/usernameauthentication.md) to the `<serviceCredentials>` element.</span></span>  
  
6. <span data-ttu-id="911d1-138">`userNamePasswordValidationMode` 属性に `MembershipProvider` を設定</span><span class="sxs-lookup"><span data-stu-id="911d1-138">Set the `userNamePasswordValidationMode` attribute to `MembershipProvider`.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="911d1-139">場合、`userNamePasswordValidationMode`値が設定されていない、WCF、ASP.NET メンバーシップ プロバイダーではなく Windows 認証を使用します。</span><span class="sxs-lookup"><span data-stu-id="911d1-139">If the `userNamePasswordValidationMode` value is not set, WCF uses Windows authentication instead of the ASP.NET membership provider.</span></span>  
  
7. <span data-ttu-id="911d1-140">`membershipProviderName` 属性をプロバイダーの名前 (このトピックの最初の手順でプロバイダーを追加したときに指定したもの) に設定します。</span><span class="sxs-lookup"><span data-stu-id="911d1-140">Set the `membershipProviderName` attribute to the name of the provider (specified when adding the provider in the first procedure in this topic).</span></span> <span data-ttu-id="911d1-141">次の例に、この時点での `<serviceCredentials>` のフラグメントを示します。</span><span class="sxs-lookup"><span data-stu-id="911d1-141">The following example shows the `<serviceCredentials>` fragment to this point.</span></span>  
  
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
  
## <a name="example"></a><span data-ttu-id="911d1-142">例</span><span class="sxs-lookup"><span data-stu-id="911d1-142">Example</span></span>  
 <span data-ttu-id="911d1-143">次のコードは、ASP メンバーシップ機能を使用するサービスの構成を示します。</span><span class="sxs-lookup"><span data-stu-id="911d1-143">The following code shows the configuration for a service that uses the ASP membership feature.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="911d1-144">関連項目</span><span class="sxs-lookup"><span data-stu-id="911d1-144">See also</span></span>

- [<span data-ttu-id="911d1-145">方法: サービスで ASP.NET ロール プロバイダーを使用します。</span><span class="sxs-lookup"><span data-stu-id="911d1-145">How to: Use the ASP.NET Role Provider with a Service</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md)
- [<span data-ttu-id="911d1-146">メンバーシップとロール プロバイダー</span><span class="sxs-lookup"><span data-stu-id="911d1-146">Membership and Role Provider</span></span>](../../../../docs/framework/wcf/samples/membership-and-role-provider.md)
