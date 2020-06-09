---
title: '方法: ASP.NET のロール プロバイダーとサービスを使用する'
ms.date: 03/30/2017
ms.assetid: 88d33a81-8ac7-48de-978c-5c5b1257951e
ms.openlocfilehash: 45eeda046e877b4379d7d0e5edd90fac305f5e44
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84595298"
---
# <a name="how-to-use-the-aspnet-role-provider-with-a-service"></a><span data-ttu-id="5c8de-102">方法: ASP.NET のロール プロバイダーとサービスを使用する</span><span class="sxs-lookup"><span data-stu-id="5c8de-102">How to: Use the ASP.NET Role Provider with a Service</span></span>

<span data-ttu-id="5c8de-103">ASP.NET ロールプロバイダー (ASP.NET メンバーシッププロバイダーと共に) は、ASP.NET 開発者がサイトを使用してアカウントを作成し、承認のためにロールを割り当てることができる Web サイトを作成できるようにする機能です。</span><span class="sxs-lookup"><span data-stu-id="5c8de-103">The ASP.NET role provider (in conjunction with the ASP.NET membership provider) is a feature that enables ASP.NET developers to create Web sites that allow users to create an account with a site and to be assigned roles for authorization purposes.</span></span> <span data-ttu-id="5c8de-104">この機能を使用すれば、ユーザーはだれでもサイトでアカウントを作成し、そのサイトにログインしてサービスに排他的にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="5c8de-104">With this feature, any user can establish an account with the site, and log in for exclusive access to the site and its services.</span></span> <span data-ttu-id="5c8de-105">これは、ユーザーが Windows ドメイン内にアカウントを持っていることが必要な Windows セキュリティとは対照的です。</span><span class="sxs-lookup"><span data-stu-id="5c8de-105">This is in contrast to Windows security, which requires users to have accounts in a Windows domain.</span></span> <span data-ttu-id="5c8de-106">代わりに、資格情報 (ユーザー名とパスワードの組み合わせ) を指定するすべてのユーザーが、サイトとそのサービスを使用できます。</span><span class="sxs-lookup"><span data-stu-id="5c8de-106">Instead, any user who supplies their credentials (the user name/password combination) can use the site and its services.</span></span>  
  
<span data-ttu-id="5c8de-107">サンプルアプリケーションについては、「[メンバーシップとロールプロバイダー](../samples/membership-and-role-provider.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5c8de-107">For a sample application, see [Membership and Role Provider](../samples/membership-and-role-provider.md).</span></span> <span data-ttu-id="5c8de-108">メンバーシッププロバイダーの ASP.NET 機能の詳細については、「[方法: ASP.NET メンバーシッププロバイダーを使用](how-to-use-the-aspnet-membership-provider.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5c8de-108">For more information about the ASP.NET membership provider feature, see [How to: Use the ASP.NET Membership Provider](how-to-use-the-aspnet-membership-provider.md).</span></span>  
  
<span data-ttu-id="5c8de-109">ロール プロバイダー機能では、SQL Server データベースを使用してユーザー情報を格納します。</span><span class="sxs-lookup"><span data-stu-id="5c8de-109">The role provider feature uses a SQL Server database to store user information.</span></span> <span data-ttu-id="5c8de-110">Windows Communication Foundation (WCF) 開発者は、これらの機能をセキュリティ上の目的で利用できます。</span><span class="sxs-lookup"><span data-stu-id="5c8de-110">Windows Communication Foundation (WCF) developers can take advantage of these features for security purposes.</span></span> <span data-ttu-id="5c8de-111">WCF アプリケーションに統合されている場合、ユーザーは、WCF クライアントアプリケーションに対してユーザー名とパスワードの組み合わせを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5c8de-111">When integrated into a WCF application, users must supply a user name/password combination to the WCF client application.</span></span> <span data-ttu-id="5c8de-112">WCF でデータベースを使用できるようにするには、クラスのインスタンスを作成し、 <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior> その <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.PrincipalPermissionMode%2A> プロパティをに設定 <xref:System.ServiceModel.Description.PrincipalPermissionMode.UseAspNetRoles> して、サービスをホストしているへの動作のコレクションにインスタンスを追加する必要があり <xref:System.ServiceModel.ServiceHost> ます。</span><span class="sxs-lookup"><span data-stu-id="5c8de-112">To enable WCF to use the database, you must create an instance of the <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior> class, set its <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.PrincipalPermissionMode%2A> property to <xref:System.ServiceModel.Description.PrincipalPermissionMode.UseAspNetRoles>, and add the instance to the collection of behaviors to the <xref:System.ServiceModel.ServiceHost> that is hosting the service.</span></span>  
  
## <a name="configure-the-role-provider"></a><span data-ttu-id="5c8de-113">ロールプロバイダーを構成する</span><span class="sxs-lookup"><span data-stu-id="5c8de-113">Configure the role provider</span></span>  
  
1. <span data-ttu-id="5c8de-114">Web.config ファイルの < > 要素の下に `system.web` < > 要素を追加し、 `roleManager` その `enabled` 属性をに設定し `true` ます。</span><span class="sxs-lookup"><span data-stu-id="5c8de-114">In the Web.config file, under the <`system.web`> element, add a <`roleManager`> element and set its `enabled` attribute to `true`.</span></span>  
  
2. <span data-ttu-id="5c8de-115">`defaultProvider` 属性を `SqlRoleProvider` に設定します。</span><span class="sxs-lookup"><span data-stu-id="5c8de-115">Set the `defaultProvider` attribute to `SqlRoleProvider`.</span></span>  
  
3. <span data-ttu-id="5c8de-116"><> 要素の子として `roleManager` 、<> 要素を追加し `providers` ます。</span><span class="sxs-lookup"><span data-stu-id="5c8de-116">As a child to the <`roleManager`> element, add a <`providers`> element.</span></span>  
  
4. <span data-ttu-id="5c8de-117"><> 要素の子として、次の `providers` `add` `name` `type` `connectionStringName` `applicationName` 例に示すように、、、、およびの各属性を適切な値に設定して、<> 要素を追加します。</span><span class="sxs-lookup"><span data-stu-id="5c8de-117">As a child to the <`providers`> element, add an <`add`> element with the following attributes set to appropriate values: `name`, `type`, `connectionStringName`, and `applicationName`, as shown in the following example.</span></span>  
  
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
  
## <a name="configure-the-service-to-use-the-role-provider"></a><span data-ttu-id="5c8de-118">ロールプロバイダーを使用するようにサービスを構成する</span><span class="sxs-lookup"><span data-stu-id="5c8de-118">Configure the service to use the role provider</span></span>  
  
1. <span data-ttu-id="5c8de-119">Web.config ファイルで、要素を追加し [\<system.serviceModel>](../../configure-apps/file-schema/wcf/system-servicemodel.md) ます。</span><span class="sxs-lookup"><span data-stu-id="5c8de-119">In the Web.config file, add a [\<system.serviceModel>](../../configure-apps/file-schema/wcf/system-servicemodel.md) element.</span></span>  
  
2. <span data-ttu-id="5c8de-120">要素を [\<behaviors>](../../configure-apps/file-schema/wcf/behaviors.md) <`system.ServiceModel`> 要素に追加します。</span><span class="sxs-lookup"><span data-stu-id="5c8de-120">Add a [\<behaviors>](../../configure-apps/file-schema/wcf/behaviors.md) element to the <`system.ServiceModel`> element.</span></span>  
  
3. <span data-ttu-id="5c8de-121">[\<serviceBehaviors>](../../configure-apps/file-schema/wcf/servicebehaviors.md)<> 要素にを追加 `behaviors` します。</span><span class="sxs-lookup"><span data-stu-id="5c8de-121">Add a [\<serviceBehaviors>](../../configure-apps/file-schema/wcf/servicebehaviors.md) to the <`behaviors`> element.</span></span>  
  
4. <span data-ttu-id="5c8de-122">要素を追加 [\<behavior>](../../configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) し、 `name` 属性を適切な値に設定します。</span><span class="sxs-lookup"><span data-stu-id="5c8de-122">Add a [\<behavior>](../../configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) element and set the `name` attribute to an appropriate value.</span></span>  
  
5. <span data-ttu-id="5c8de-123">[\<serviceAuthorization>](../../configure-apps/file-schema/wcf/serviceauthorization-element.md)<> 要素にを追加 `behavior` します。</span><span class="sxs-lookup"><span data-stu-id="5c8de-123">Add a [\<serviceAuthorization>](../../configure-apps/file-schema/wcf/serviceauthorization-element.md) to the <`behavior`> element.</span></span>  
  
6. <span data-ttu-id="5c8de-124">`principalPermissionMode` 属性を `UseAspNetRoles` に設定します。</span><span class="sxs-lookup"><span data-stu-id="5c8de-124">Set the `principalPermissionMode` attribute to `UseAspNetRoles`.</span></span>  
  
7. <span data-ttu-id="5c8de-125">`roleProviderName` 属性を `SqlRoleProvider` に設定します。</span><span class="sxs-lookup"><span data-stu-id="5c8de-125">Set the `roleProviderName` attribute to `SqlRoleProvider`.</span></span> <span data-ttu-id="5c8de-126">この構成の一部を次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="5c8de-126">The following example shows a fragment of the configuration.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="5c8de-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="5c8de-127">See also</span></span>

- [<span data-ttu-id="5c8de-128">メンバーシップとロール プロバイダー</span><span class="sxs-lookup"><span data-stu-id="5c8de-128">Membership and Role Provider</span></span>](../samples/membership-and-role-provider.md)
- [<span data-ttu-id="5c8de-129">方法: ASP.NET メンバーシップ プロバイダーを使用する</span><span class="sxs-lookup"><span data-stu-id="5c8de-129">How to: Use the ASP.NET Membership Provider</span></span>](how-to-use-the-aspnet-membership-provider.md)
