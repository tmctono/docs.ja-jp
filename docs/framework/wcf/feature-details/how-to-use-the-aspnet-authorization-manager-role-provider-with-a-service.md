---
title: '方法 : ASP.NET の承認マネージャー ロール プロバイダーとサービスを使用する'
ms.date: 03/30/2017
ms.assetid: f21deb81-91ef-49ef-94d6-494785143271
ms.openlocfilehash: 009b96defdf27591ddb98afaa684745b5fcbe0d4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184812"
---
# <a name="how-to-use-the-aspnet-authorization-manager-role-provider-with-a-service"></a><span data-ttu-id="8387b-102">方法 : ASP.NET の承認マネージャー ロール プロバイダーとサービスを使用する</span><span class="sxs-lookup"><span data-stu-id="8387b-102">How to: Use the ASP.NET Authorization Manager Role Provider with a Service</span></span>
<span data-ttu-id="8387b-103">ASP.NET Web サービスをホストする場合、承認マネージャをアプリケーションに統合して、サービスに承認を提供できます。</span><span class="sxs-lookup"><span data-stu-id="8387b-103">When ASP.NET hosts a Web service, you can integrate Authorization Manager into the application to provide authorization to the service.</span></span> <span data-ttu-id="8387b-104">承認マネージャーを使用して、アプリケーション開発者は個々の操作を定義できます。また、個々の操作をグループ化してタスクを形成できます。</span><span class="sxs-lookup"><span data-stu-id="8387b-104">Authorization Manager enables an application developer to define individual operations, which can be grouped together to form tasks.</span></span> <span data-ttu-id="8387b-105">次に管理者は、ロールを承認して特定のタスクまたは個々の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="8387b-105">An administrator can then authorize roles to perform specific tasks or individual operations.</span></span> <span data-ttu-id="8387b-106">承認マネージャーでは、ロール、タスク、操作、ユーザーを管理する管理ツールとして Microsoft 管理コンソール (MMC) スナップインが提供されます。</span><span class="sxs-lookup"><span data-stu-id="8387b-106">Authorization Manager provides an administration tool as a Microsoft Management Console (MMC) snap-in to manage roles, tasks, operations, and users.</span></span> <span data-ttu-id="8387b-107">管理者は、承認マネージャーのポリシー ストアを XML ファイル、Active Directory、または Active Directory アプリケーション モード (ADAM) ストアに構成します。</span><span class="sxs-lookup"><span data-stu-id="8387b-107">Administrators configure an Authorization Manager policy store in an XML file, Active Directory, or in an Active Directory Application Mode (ADAM) store.</span></span>  
  
 <span data-ttu-id="8387b-108">承認マネージャは、Web サービスをホストしているASP.NET アプリケーションの承認マネージャASP.NETロール プロバイダを構成することによって、アプリケーションに統合されます。</span><span class="sxs-lookup"><span data-stu-id="8387b-108">Authorization Manager is Integrated into the application by configuring the Authorization Manager ASP.NET role provider for the ASP.NET application that is hosting the Web service.</span></span> <span data-ttu-id="8387b-109">他のASP.NET ロール プロバイダーと同様に、承認マネージャーASP.NETロール プロバイダーは`providers`、<>要素を使用して構成されます。</span><span class="sxs-lookup"><span data-stu-id="8387b-109">Like other ASP.NET role providers, the Authorization Manager ASP.NET role provider is configured using the <`providers`> element.</span></span>  
  
 <span data-ttu-id="8387b-110">承認マネージャーをアプリケーションに統合する Web サービスの構成ファイルの一部を示すコード例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="8387b-110">The following code example is a portion of a configuration file for a Web service that is integrating Authorization Manager into the application.</span></span>  
  
```xml  
<system.web>  
    <roleManager enabled="true" defaultProvider="AzManRoleProvider">  
      <providers>  
        <add name="AzManRoleProvider"  
             type="System.Web.Security.AuthorizationStoreRoleProvider, System.Web, Version=2.0.0.0, Culture=neutral, publicKeyToken=b03f5f7f11d50a3a"  
             connectionStringName="AzManPolicyStoreConnectionString"
             applicationName="SecureService"/>  
      </providers>  
    </roleManager>  
</system.web>  
```  
  
 <span data-ttu-id="8387b-111">WCF アプリケーションとASP.NET ロール プロバイダーを統合する方法の詳細については、「[方法 : サービスでASP.NET ロール プロバイダーを使用](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md)する 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8387b-111">For more information about integrating an ASP.NET role provider with a WCF application, see [How to: Use the ASP.NET Role Provider with a Service](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md).</span></span> <span data-ttu-id="8387b-112">ASP.NETで承認マネージャを使用する方法の詳細については、「[方法 : ASP.NET 2.0 で承認マネージャ (AzMan) を使用](https://docs.microsoft.com/previous-versions/msp-n-p/ff649313(v=pandp.10))する方法」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8387b-112">For more information about using Authorization Manager with ASP.NET, see [How to: Use Authorization Manager (AzMan) with ASP.NET 2.0](https://docs.microsoft.com/previous-versions/msp-n-p/ff649313(v=pandp.10)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8387b-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="8387b-113">See also</span></span>

- [<span data-ttu-id="8387b-114">方法 : ASP.NET のロール プロバイダーとサービスを使用する</span><span class="sxs-lookup"><span data-stu-id="8387b-114">How to: Use the ASP.NET Role Provider with a Service</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md)
