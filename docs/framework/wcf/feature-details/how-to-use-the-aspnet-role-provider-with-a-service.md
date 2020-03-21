---
title: '方法 : ASP.NET のロール プロバイダーとサービスを使用する'
ms.date: 03/30/2017
ms.assetid: 88d33a81-8ac7-48de-978c-5c5b1257951e
ms.openlocfilehash: ddfedeb2491998f64ab241ceba303d50d0714351
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184770"
---
# <a name="how-to-use-the-aspnet-role-provider-with-a-service"></a><span data-ttu-id="5c36f-102">方法 : ASP.NET のロール プロバイダーとサービスを使用する</span><span class="sxs-lookup"><span data-stu-id="5c36f-102">How to: Use the ASP.NET Role Provider with a Service</span></span>

<span data-ttu-id="5c36f-103">ASP.NET ロール プロバイダ (ASP.NET メンバーシップ プロバイダーと組み合わせた) は、ASP.NET開発者が、ユーザーがサイトを持つアカウントを作成したり、承認用にロールを割り当てたりできる Web サイトを作成できるようにする機能です。</span><span class="sxs-lookup"><span data-stu-id="5c36f-103">The ASP.NET role provider (in conjunction with the ASP.NET membership provider) is a feature that enables ASP.NET developers to create Web sites that allow users to create an account with a site and to be assigned roles for authorization purposes.</span></span> <span data-ttu-id="5c36f-104">この機能を使用すれば、ユーザーはだれでもサイトでアカウントを作成し、そのサイトにログインしてサービスに排他的にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="5c36f-104">With this feature, any user can establish an account with the site, and log in for exclusive access to the site and its services.</span></span> <span data-ttu-id="5c36f-105">これは、ユーザーが Windows ドメイン内にアカウントを持っていることが必要な Windows セキュリティとは対照的です。</span><span class="sxs-lookup"><span data-stu-id="5c36f-105">This is in contrast to Windows security, which requires users to have accounts in a Windows domain.</span></span> <span data-ttu-id="5c36f-106">代わりに、資格情報 (ユーザー名とパスワードの組み合わせ) を提供するすべてのユーザーが、サイトとそのサービスを使用できます。</span><span class="sxs-lookup"><span data-stu-id="5c36f-106">Instead, any user who supplies their credentials (the user name/password combination) can use the site and its services.</span></span>  
  
<span data-ttu-id="5c36f-107">サンプル アプリケーションについては、「[メンバーシップとロール プロバイダ](../../../../docs/framework/wcf/samples/membership-and-role-provider.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5c36f-107">For a sample application, see [Membership and Role Provider](../../../../docs/framework/wcf/samples/membership-and-role-provider.md).</span></span> <span data-ttu-id="5c36f-108">ASP.NET メンバーシップ プロバイダ機能の詳細については、「[方法 : ASP.NET メンバーシップ プロバイダを使用する](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-membership-provider.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5c36f-108">For more information about the ASP.NET membership provider feature, see [How to: Use the ASP.NET Membership Provider](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-membership-provider.md).</span></span>  
  
<span data-ttu-id="5c36f-109">ロール プロバイダー機能では、SQL Server データベースを使用してユーザー情報を格納します。</span><span class="sxs-lookup"><span data-stu-id="5c36f-109">The role provider feature uses a SQL Server database to store user information.</span></span> <span data-ttu-id="5c36f-110">Windows 通信基盤 (WCF) の開発者は、セキュリティ上の目的でこれらの機能を利用できます。</span><span class="sxs-lookup"><span data-stu-id="5c36f-110">Windows Communication Foundation (WCF) developers can take advantage of these features for security purposes.</span></span> <span data-ttu-id="5c36f-111">WCF アプリケーションに統合する場合、ユーザーは、WCF クライアント アプリケーションにユーザー名とパスワードの組み合わせを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5c36f-111">When integrated into a WCF application, users must supply a user name/password combination to the WCF client application.</span></span> <span data-ttu-id="5c36f-112">WCF<xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>でデータベースを使用できるようにするには、クラスのインスタンスを作成し、その<xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.PrincipalPermissionMode%2A>プロパティを に<xref:System.ServiceModel.Description.PrincipalPermissionMode.UseAspNetRoles>設定し、サービスをホスト<xref:System.ServiceModel.ServiceHost>している動作のコレクションにインスタンスを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5c36f-112">To enable WCF to use the database, you must create an instance of the <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior> class, set its <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.PrincipalPermissionMode%2A> property to <xref:System.ServiceModel.Description.PrincipalPermissionMode.UseAspNetRoles>, and add the instance to the collection of behaviors to the <xref:System.ServiceModel.ServiceHost> that is hosting the service.</span></span>  
  
## <a name="configure-the-role-provider"></a><span data-ttu-id="5c36f-113">ロール プロバイダーを構成する</span><span class="sxs-lookup"><span data-stu-id="5c36f-113">Configure the role provider</span></span>  
  
1. <span data-ttu-id="5c36f-114">Web.config ファイルの`system.web`<>要素の下に、<>`roleManager`要素を追加し、`enabled`その属性`true`を に設定します。</span><span class="sxs-lookup"><span data-stu-id="5c36f-114">In the Web.config file, under the <`system.web`> element, add a <`roleManager`> element and set its `enabled` attribute to `true`.</span></span>  
  
2. <span data-ttu-id="5c36f-115">`defaultProvider` 属性を `SqlRoleProvider` に設定します。</span><span class="sxs-lookup"><span data-stu-id="5c36f-115">Set the `defaultProvider` attribute to `SqlRoleProvider`.</span></span>  
  
3. <span data-ttu-id="5c36f-116"><`roleManager`>要素の子として、<>`providers`要素を追加します。</span><span class="sxs-lookup"><span data-stu-id="5c36f-116">As a child to the <`roleManager`> element, add a <`providers`> element.</span></span>  
  
4. <span data-ttu-id="5c36f-117">`providers` <>要素の子として、次の例に示`add`すように、次の属性を適切な値`name` `type`、、、、`connectionStringName`および`applicationName`に設定した<>要素を追加します。</span><span class="sxs-lookup"><span data-stu-id="5c36f-117">As a child to the <`providers`> element, add an <`add`> element with the following attributes set to appropriate values: `name`, `type`, `connectionStringName`, and `applicationName`, as shown in the following example.</span></span>  
  
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
  
## <a name="configure-the-service-to-use-the-role-provider"></a><span data-ttu-id="5c36f-118">ロール プロバイダーを使用するようにサービスを構成する</span><span class="sxs-lookup"><span data-stu-id="5c36f-118">Configure the service to use the role provider</span></span>  
  
1. <span data-ttu-id="5c36f-119">Web.config ファイルに[\<、システム.サービスモデル>要素を](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)追加します。</span><span class="sxs-lookup"><span data-stu-id="5c36f-119">In the Web.config file, add a [\<system.serviceModel>](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) element.</span></span>  
  
2. <span data-ttu-id="5c36f-120">`system.ServiceModel` <>[\<要素に、動作>](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md)要素を追加します。</span><span class="sxs-lookup"><span data-stu-id="5c36f-120">Add a [\<behaviors>](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) element to the <`system.ServiceModel`> element.</span></span>  
  
3. <span data-ttu-id="5c36f-121">[\<サービス](../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md)`behaviors`を追加する><>要素にします。</span><span class="sxs-lookup"><span data-stu-id="5c36f-121">Add a [\<serviceBehaviors>](../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md) to the <`behaviors`> element.</span></span>  
  
4. <span data-ttu-id="5c36f-122">要素[\<>動作を](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)追加し、属性`name`を適切な値に設定します。</span><span class="sxs-lookup"><span data-stu-id="5c36f-122">Add a [\<behavior>](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) element and set the `name` attribute to an appropriate value.</span></span>  
  
5. <span data-ttu-id="5c36f-123">サービス認証>を<>`behavior`要素に追加します。 [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/serviceauthorization-element.md)</span><span class="sxs-lookup"><span data-stu-id="5c36f-123">Add a [\<serviceAuthorization>](../../../../docs/framework/configure-apps/file-schema/wcf/serviceauthorization-element.md) to the <`behavior`> element.</span></span>  
  
6. <span data-ttu-id="5c36f-124">`principalPermissionMode` 属性を `UseAspNetRoles` に設定します。</span><span class="sxs-lookup"><span data-stu-id="5c36f-124">Set the `principalPermissionMode` attribute to `UseAspNetRoles`.</span></span>  
  
7. <span data-ttu-id="5c36f-125">`roleProviderName` 属性を `SqlRoleProvider` に設定します。</span><span class="sxs-lookup"><span data-stu-id="5c36f-125">Set the `roleProviderName` attribute to `SqlRoleProvider`.</span></span> <span data-ttu-id="5c36f-126">この構成の一部を次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="5c36f-126">The following example shows a fragment of the configuration.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="5c36f-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="5c36f-127">See also</span></span>

- [<span data-ttu-id="5c36f-128">メンバーシップとロール プロバイダー</span><span class="sxs-lookup"><span data-stu-id="5c36f-128">Membership and Role Provider</span></span>](../../../../docs/framework/wcf/samples/membership-and-role-provider.md)
- [<span data-ttu-id="5c36f-129">方法 : ASP.NET メンバーシップ プロバイダーを使用する</span><span class="sxs-lookup"><span data-stu-id="5c36f-129">How to: Use the ASP.NET Membership Provider</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-membership-provider.md)
