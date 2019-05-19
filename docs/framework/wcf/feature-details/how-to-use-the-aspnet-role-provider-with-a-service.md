---
title: '方法: ASP.NET のロール プロバイダーとサービスを使用する'
ms.date: 03/30/2017
ms.assetid: 88d33a81-8ac7-48de-978c-5c5b1257951e
ms.openlocfilehash: f989252c7dd9b2ccdce8331e7cdd987042230ded
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2019
ms.locfileid: "65880242"
---
# <a name="how-to-use-the-aspnet-role-provider-with-a-service"></a><span data-ttu-id="68fb0-102">方法: ASP.NET のロール プロバイダーとサービスを使用する</span><span class="sxs-lookup"><span data-stu-id="68fb0-102">How to: Use the ASP.NET Role Provider with a Service</span></span>
<span data-ttu-id="68fb0-103">(ASP.NET メンバーシップ プロバイダーと組み合わせて) ASP.NET ロール プロバイダーは、ASP.NET 開発者サイトでアカウントを作成し、承認のためのロールを割り当てられるようにすることが Web サイトを作成することができる機能です。</span><span class="sxs-lookup"><span data-stu-id="68fb0-103">The ASP.NET role provider (in conjunction with the ASP.NET membership provider) is a feature that enables ASP.NET developers to create Web sites that allow users to create an account with a site and to be assigned roles for authorization purposes.</span></span> <span data-ttu-id="68fb0-104">この機能を使用すれば、ユーザーはだれでもサイトでアカウントを作成し、そのサイトにログインしてサービスに排他的にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="68fb0-104">With this feature, any user can establish an account with the site, and log in for exclusive access to the site and its services.</span></span> <span data-ttu-id="68fb0-105">これは、ユーザーが Windows ドメイン内にアカウントを持っていることが必要な Windows セキュリティとは対照的です。</span><span class="sxs-lookup"><span data-stu-id="68fb0-105">This is in contrast to Windows security, which requires users to have accounts in a Windows domain.</span></span> <span data-ttu-id="68fb0-106">自分の資格情報 (ユーザー名とパスワードの組み合わせ) を提示したユーザーは、だれでもサイトとそのサービスを使用できます。</span><span class="sxs-lookup"><span data-stu-id="68fb0-106">Instead, any user who supplies his or her credentials (the user name/password combination) can use the site and its services.</span></span>  
  
 <span data-ttu-id="68fb0-107">サンプル アプリケーションについては「[メンバーシップとロール プロバイダー](../../../../docs/framework/wcf/samples/membership-and-role-provider.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="68fb0-107">For a sample application, see [Membership and Role Provider](../../../../docs/framework/wcf/samples/membership-and-role-provider.md).</span></span> <span data-ttu-id="68fb0-108">ASP.NET メンバーシップ プロバイダー機能の詳細については、次を参照してください。[方法。ASP.NET メンバーシップ プロバイダーを使用して、](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-membership-provider.md)します。</span><span class="sxs-lookup"><span data-stu-id="68fb0-108">For more information about the ASP.NET membership provider feature, see [How to: Use the ASP.NET Membership Provider](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-membership-provider.md).</span></span>  
  
 <span data-ttu-id="68fb0-109">ロール プロバイダー機能では、SQL Server データベースを使用してユーザー情報を格納します。</span><span class="sxs-lookup"><span data-stu-id="68fb0-109">The role provider feature uses a SQL Server database to store user information.</span></span> <span data-ttu-id="68fb0-110">Windows Communication Foundation (WCF) 開発者は、これらの機能のセキュリティの目的で利用できます。</span><span class="sxs-lookup"><span data-stu-id="68fb0-110">Windows Communication Foundation (WCF) developers can take advantage of these features for security purposes.</span></span> <span data-ttu-id="68fb0-111">WCF アプリケーションに統合すると、ユーザーは、WCF クライアント アプリケーションにユーザー名/パスワードの組み合わせを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="68fb0-111">When integrated into a WCF application, users must supply a user name/password combination to the WCF client application.</span></span> <span data-ttu-id="68fb0-112">データベースを使用する WCF を有効にするには、インスタンスを作成する必要があります、<xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>クラス、設定、<xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.PrincipalPermissionMode%2A>プロパティを<xref:System.ServiceModel.Description.PrincipalPermissionMode.UseAspNetRoles>、に対する動作のコレクションにインスタンスを追加し、<xref:System.ServiceModel.ServiceHost>サービスをホストしています。</span><span class="sxs-lookup"><span data-stu-id="68fb0-112">To enable WCF to use the database, you must create an instance of the <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior> class, set its <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.PrincipalPermissionMode%2A> property to <xref:System.ServiceModel.Description.PrincipalPermissionMode.UseAspNetRoles>, and add the instance to the collection of behaviors to the <xref:System.ServiceModel.ServiceHost> that is hosting the service.</span></span>  
  
### <a name="to-configure-the-role-provider"></a><span data-ttu-id="68fb0-113">ロール プロバイダーを構成するには</span><span class="sxs-lookup"><span data-stu-id="68fb0-113">To configure the role provider</span></span>  
  
1. <span data-ttu-id="68fb0-114">Web.config ファイルでの下、<`system.web`> 要素を追加、<`roleManager`> 要素の`enabled`属性を`true`。</span><span class="sxs-lookup"><span data-stu-id="68fb0-114">In the Web.config file, under the <`system.web`> element, add a <`roleManager`> element and set its `enabled` attribute to `true`.</span></span>  
  
2. <span data-ttu-id="68fb0-115">`defaultProvider` 属性に `SqlRoleProvider` を設定</span><span class="sxs-lookup"><span data-stu-id="68fb0-115">Set the `defaultProvider` attribute to `SqlRoleProvider`.</span></span>  
  
3. <span data-ttu-id="68fb0-116">子として、<`roleManager`> 要素を追加する <`providers`> 要素。</span><span class="sxs-lookup"><span data-stu-id="68fb0-116">As a child to the <`roleManager`> element, add a <`providers`> element.</span></span>  
  
4. <span data-ttu-id="68fb0-117">子として、<`providers`> 要素を追加、<`add`> 次の属性を持つ要素が適切な値に設定: `name`、 `type`、`connectionStringName`と`applicationName`次の例のようにします。</span><span class="sxs-lookup"><span data-stu-id="68fb0-117">As a child to the <`providers`> element, add an <`add`> element with the following attributes set to appropriate values: `name`, `type`, `connectionStringName`, and `applicationName`, as shown in the following example.</span></span>  
  
    ```xml  
    <!-- Configure the Sql Role Provider. -->  
    <roleManager enabled ="true"   
     defaultProvider ="SqlRoleProvider" >  
       <providers>  
         <add name ="SqlRoleProvider"   
           type="System.Web.Security.SqlRoleProvider"   
           connectionStringName="SqlConn"   
           applicationName="MembershipAndRoleProviderSample"/>  
       </providers>  
    </roleManager>  
    ```  
  
### <a name="to-configure-the-service-to-use-the-role-provider"></a><span data-ttu-id="68fb0-118">ロール プロバイダーを使用するようにサービスを構成するには</span><span class="sxs-lookup"><span data-stu-id="68fb0-118">To configure the service to use the role provider</span></span>  
  
1. <span data-ttu-id="68fb0-119">Web.config ファイルで、追加、 [ \<system.serviceModel >](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)要素。</span><span class="sxs-lookup"><span data-stu-id="68fb0-119">In the Web.config file, add a [\<system.serviceModel>](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) element.</span></span>  
  
2. <span data-ttu-id="68fb0-120">追加、 [\<動作 >](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md)要素を <`system.ServiceModel`> 要素。</span><span class="sxs-lookup"><span data-stu-id="68fb0-120">Add a [\<behaviors>](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) element to the <`system.ServiceModel`> element.</span></span>  
  
3. <span data-ttu-id="68fb0-121">追加、 [ \<serviceBehaviors >](../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md)に、<`behaviors`> 要素。</span><span class="sxs-lookup"><span data-stu-id="68fb0-121">Add a [\<serviceBehaviors>](../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md) to the <`behaviors`> element.</span></span>  
  
4. <span data-ttu-id="68fb0-122">追加、 [\<動作 >](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)要素、`name`属性に適切な値。</span><span class="sxs-lookup"><span data-stu-id="68fb0-122">Add a [\<behavior>](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) element and set the `name` attribute to an appropriate value.</span></span>  
  
5. <span data-ttu-id="68fb0-123">追加、 [ \<serviceAuthorization >](../../../../docs/framework/configure-apps/file-schema/wcf/serviceauthorization-element.md)に、<`behavior`> 要素。</span><span class="sxs-lookup"><span data-stu-id="68fb0-123">Add a [\<serviceAuthorization>](../../../../docs/framework/configure-apps/file-schema/wcf/serviceauthorization-element.md) to the <`behavior`> element.</span></span>  
  
6. <span data-ttu-id="68fb0-124">`principalPermissionMode` 属性に `UseAspNetRoles` を設定</span><span class="sxs-lookup"><span data-stu-id="68fb0-124">Set the `principalPermissionMode` attribute to `UseAspNetRoles`.</span></span>  
  
7. <span data-ttu-id="68fb0-125">`roleProviderName` 属性に `SqlRoleProvider` を設定</span><span class="sxs-lookup"><span data-stu-id="68fb0-125">Set the `roleProviderName` attribute to `SqlRoleProvider`.</span></span> <span data-ttu-id="68fb0-126">この構成の一部を次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="68fb0-126">The following example shows a fragment of the configuration.</span></span>  
  
    ```xml  
    <behaviors>  
     <serviceBehaviors>  
      <behavior name="CalculatorServiceBehavior">  
       <serviceAuthorization principalPermissionMode ="UseAspNetRoles"  
                             roleProviderName ="SqlRoleProvider" />  
      </behavior>  
     </serviceBehaviors>  
    </behaviors>  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="68fb0-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="68fb0-127">See also</span></span>

- [<span data-ttu-id="68fb0-128">メンバーシップとロール プロバイダー</span><span class="sxs-lookup"><span data-stu-id="68fb0-128">Membership and Role Provider</span></span>](../../../../docs/framework/wcf/samples/membership-and-role-provider.md)
- [<span data-ttu-id="68fb0-129">方法: ASP.NET メンバーシップ プロバイダーを使用します。</span><span class="sxs-lookup"><span data-stu-id="68fb0-129">How to: Use the ASP.NET Membership Provider</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-membership-provider.md)
