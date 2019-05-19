---
title: '方法: IIS で WCF サービスをホストする'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b044b1c9-c1e5-4c9f-84d8-0f02f4537f8b
ms.openlocfilehash: e9ff82d58f08d8c040984b37422a7048b9d4361d
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2019
ms.locfileid: "65878635"
---
# <a name="how-to-host-a-wcf-service-in-iis"></a><span data-ttu-id="6f8b8-102">方法: IIS で WCF サービスをホストする</span><span class="sxs-lookup"><span data-stu-id="6f8b8-102">How to: Host a WCF Service in IIS</span></span>
<span data-ttu-id="6f8b8-103">このトピックでは、インターネット インフォメーション サービス (IIS) でホストされている Windows Communication Foundation (WCF) サービスを作成するために必要な基本的な手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="6f8b8-103">This topic outlines the basic steps required to create a Windows Communication Foundation (WCF) service that is hosted in Internet Information Services (IIS).</span></span> <span data-ttu-id="6f8b8-104">このトピックは、IIS に関する知識があり、IIS 管理ツールを使用して IIS アプリケーションを作成および管理する方法を理解していることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="6f8b8-104">This topic assumes you are familiar with IIS and understand how to use the IIS management tool to create and manage IIS applications.</span></span> <span data-ttu-id="6f8b8-105">IIS の詳細については、次を参照してください。[インターネット インフォメーション サービス](https://go.microsoft.com/fwlink/?LinkId=132449)します。</span><span class="sxs-lookup"><span data-stu-id="6f8b8-105">For more information about IIS see [Internet Information Services](https://go.microsoft.com/fwlink/?LinkId=132449).</span></span> <span data-ttu-id="6f8b8-106">IIS 環境での実行がプロセスのリサイクルなどの IIS 機能を最大限に活用する WCF サービスはアイドル シャット ダウン、処理状況の監視、およびメッセージ ベースのアクティブ化します。</span><span class="sxs-lookup"><span data-stu-id="6f8b8-106">A WCF service that runs in the IIS environment takes full advantage of IIS features, such as process recycling, idle shutdown, process health monitoring, and message-based activation.</span></span> <span data-ttu-id="6f8b8-107">このホスト オプションでは、IIS が正しく構成されている必要がありますが、アプリケーションの一部としてホスト コードを書く必要はありません。</span><span class="sxs-lookup"><span data-stu-id="6f8b8-107">This hosting option requires that IIS be properly configured, but it does not require that any hosting code be written as part of the application.</span></span> <span data-ttu-id="6f8b8-108">IIS ホストは、HTTP トランスポートでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="6f8b8-108">You can use IIS hosting only with an HTTP transport.</span></span>  
  
 <span data-ttu-id="6f8b8-109">WCF と ASP.NET の対話方法の詳細については、次を参照してください。 [WCF サービスと ASP.NET](../../../../docs/framework/wcf/feature-details/wcf-services-and-aspnet.md)します。</span><span class="sxs-lookup"><span data-stu-id="6f8b8-109">For more information about how WCF and ASP.NET interact, see [WCF Services and ASP.NET](../../../../docs/framework/wcf/feature-details/wcf-services-and-aspnet.md).</span></span> <span data-ttu-id="6f8b8-110">セキュリティの構成の詳細については、次を参照してください。[セキュリティ](../../../../docs/framework/wcf/feature-details/security.md)します。</span><span class="sxs-lookup"><span data-stu-id="6f8b8-110">For more information about configuring security, see [Security](../../../../docs/framework/wcf/feature-details/security.md).</span></span>  
  
 <span data-ttu-id="6f8b8-111">この例のソースのコピーを次を参照してください。 [IIS は、インラインのコードを使用してホスト](../../../../docs/framework/wcf/samples/iis-hosting-using-inline-code.md)します。</span><span class="sxs-lookup"><span data-stu-id="6f8b8-111">For the source copy of this example, see [IIS Hosting Using Inline Code](../../../../docs/framework/wcf/samples/iis-hosting-using-inline-code.md).</span></span>  
  
### <a name="to-create-a-service-hosted-by-iis"></a><span data-ttu-id="6f8b8-112">IIS でホストされるサービスを作成するには</span><span class="sxs-lookup"><span data-stu-id="6f8b8-112">To create a service hosted by IIS</span></span>  
  
1. <span data-ttu-id="6f8b8-113">コンピューターに IIS がインストールされ、実行されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="6f8b8-113">Confirm that IIS is installed and running on your computer.</span></span> <span data-ttu-id="6f8b8-114">インストールと IIS の構成の詳細については、次を参照してください[のインストールと IIS 7.0 の構成。](https://go.microsoft.com/fwlink/?LinkID=132128)</span><span class="sxs-lookup"><span data-stu-id="6f8b8-114">For more information about installing and configuring IIS see [Installing and Configuring IIS 7.0](https://go.microsoft.com/fwlink/?LinkID=132128)</span></span>  
  
2. <span data-ttu-id="6f8b8-115">"Iishostedcalcservice"アプリケーション ファイル用に新しいフォルダーを作成、ASP.NET には、フォルダーの内容にアクセスすることを確認および、IIS 管理ツールを使用して、このアプリケーション ディレクトリに物理的にある新しい IIS アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="6f8b8-115">Create a new folder for your application files called "IISHostedCalcService", ensure that ASP.NET has access to the contents of the folder, and use the IIS management tool to create a new IIS application that is physically located in this application directory.</span></span> <span data-ttu-id="6f8b8-116">アプリケーション ディレクトリのエイリアスを作成する場合は、"IISHostedCalc" を使用します。</span><span class="sxs-lookup"><span data-stu-id="6f8b8-116">When creating an alias for the application directory use "IISHostedCalc".</span></span>  
  
3. <span data-ttu-id="6f8b8-117">"service.svc" という新しいファイルをアプリケーション ディレクトリに作成します。</span><span class="sxs-lookup"><span data-stu-id="6f8b8-117">Create a new file named "service.svc" in the application directory.</span></span> <span data-ttu-id="6f8b8-118">次を追加してこのファイルを編集@ServiceHost要素。</span><span class="sxs-lookup"><span data-stu-id="6f8b8-118">Edit this file by adding the following @ServiceHost element.</span></span>  
  
    ```  
    <%@ServiceHost language=c# Debug="true" Service="Microsoft.ServiceModel.Samples.CalculatorService"%>  
    ```  
  
4. <span data-ttu-id="6f8b8-119">アプリケーション ディレクトリ内に App_Code サブディレクトリを作成します。</span><span class="sxs-lookup"><span data-stu-id="6f8b8-119">Create an App_Code subdirectory within the application directory.</span></span>  
  
5. <span data-ttu-id="6f8b8-120">App_Code サブディレクトリに Service.cs というコード ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="6f8b8-120">Create a code file named Service.cs in the App_Code subdirectory.</span></span>  
  
6. <span data-ttu-id="6f8b8-121">Service.cs ファイルの先頭に次の using ステートメントを追加します。</span><span class="sxs-lookup"><span data-stu-id="6f8b8-121">Add the following using statements to the top of the Service.cs file.</span></span>  
  
    ```csharp  
    using System;  
    using System.ServiceModel;  
    ```  
  
7. <span data-ttu-id="6f8b8-122">using ステートメントの後に、次の名前空間宣言を追加します。</span><span class="sxs-lookup"><span data-stu-id="6f8b8-122">Add the following namespace declaration after the using statements.</span></span>  
  
    ```csharp  
    namespace Microsoft.ServiceModel.Samples  
    {  
    }  
    ```  
  
8. <span data-ttu-id="6f8b8-123">次のコードに示すように、名前空間宣言内にサービス コントラクトを定義します。</span><span class="sxs-lookup"><span data-stu-id="6f8b8-123">Define the service contract inside the namespace declaration as shown in the following code.</span></span>  
  
     [!code-csharp[c_HowTo_HostInIIS#11](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostiniis/cs/source.cs#11)]
     [!code-vb[c_HowTo_HostInIIS#11](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostiniis/vb/source.vb#11)]  
  
9. <span data-ttu-id="6f8b8-124">次のコードに示すように、サービス コントラクト定義の後に、サービス コントラクトを実装します。</span><span class="sxs-lookup"><span data-stu-id="6f8b8-124">Implement the service contract after the service contract definition as shown in the following code.</span></span>  
  
     [!code-csharp[c_HowTo_HostInIIS#12](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostiniis/cs/source.cs#12)]
     [!code-vb[c_HowTo_HostInIIS#12](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostiniis/vb/source.vb#12)]  
  
10. <span data-ttu-id="6f8b8-125">アプリケーション ディレクトリ内に "Web.config" というファイルを作成し、次の構成コードをファイルに追加します。</span><span class="sxs-lookup"><span data-stu-id="6f8b8-125">Create a file named "Web.config" in the application directory and add the following configuration code into the file.</span></span> <span data-ttu-id="6f8b8-126">WCF インフラストラクチャは、実行時に情報を使用して、クライアント アプリケーションが通信できるエンドポイントを作成します。</span><span class="sxs-lookup"><span data-stu-id="6f8b8-126">At runtime, the WCF infrastructure uses the information to construct an endpoint that client applications can communicate with.</span></span>  
  
     [!code-xml[c_HowTo_HostInIIS#100](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostiniis/common/web.config#100)]      
  
     <span data-ttu-id="6f8b8-127">この例では、構成ファイルにエンドポイントを明示的に指定します。</span><span class="sxs-lookup"><span data-stu-id="6f8b8-127">This example explicitly specifies endpoints in the configuration file.</span></span> <span data-ttu-id="6f8b8-128">エンドポイントをサービスに追加しない場合、ランタイムによって既定のエンドポイントが追加されます。</span><span class="sxs-lookup"><span data-stu-id="6f8b8-128">If you do not add any endpoints to the service, the runtime adds default endpoints for you.</span></span> <span data-ttu-id="6f8b8-129">既定のエンドポイント、バインディング、および動作を参照の詳細については[Simplified Configuration](../../../../docs/framework/wcf/simplified-configuration.md)と[Simplified Configuration for WCF Services](../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md)します。</span><span class="sxs-lookup"><span data-stu-id="6f8b8-129">For more information about default endpoints, bindings, and behaviors see [Simplified Configuration](../../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>  
  
11. <span data-ttu-id="6f8b8-130">サービスが正確にホストされるようにするには、Internet Explorer のインスタンスを開き、サービスの URL: `http://localhost/IISHostedCalc/Service.svc` を参照します。</span><span class="sxs-lookup"><span data-stu-id="6f8b8-130">To make sure the service is hosted correctly, open an instance of Internet Explorer and browse to the service's URL: `http://localhost/IISHostedCalc/Service.svc`</span></span>  
  
## <a name="example"></a><span data-ttu-id="6f8b8-131">例</span><span class="sxs-lookup"><span data-stu-id="6f8b8-131">Example</span></span>  
 <span data-ttu-id="6f8b8-132">IIS がホストする電卓サービスのコードの完全な一覧を次に示します。</span><span class="sxs-lookup"><span data-stu-id="6f8b8-132">The following is a complete listing of the code for the IIS hosted calculator service.</span></span>  
  
 [!code-csharp[C_HowTo_HostInIIS#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostiniis/cs/source.cs#1)] 
 [!code-vb[C_HowTo_HostInIIS#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostiniis/vb/source.vb#1)] 
 [!code-xml[c_HowTo_HostInIIS#100](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostiniis/common/web.config#100)]  
  
## <a name="see-also"></a><span data-ttu-id="6f8b8-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="6f8b8-133">See also</span></span>

- [<span data-ttu-id="6f8b8-134">インターネット インフォメーション サービスでのホスティング</span><span class="sxs-lookup"><span data-stu-id="6f8b8-134">Hosting in Internet Information Services</span></span>](../../../../docs/framework/wcf/feature-details/hosting-in-internet-information-services.md)
- [<span data-ttu-id="6f8b8-135">ホスティング サービス</span><span class="sxs-lookup"><span data-stu-id="6f8b8-135">Hosting Services</span></span>](../../../../docs/framework/wcf/hosting-services.md)
- [<span data-ttu-id="6f8b8-136">WCF サービスと ASP.NET</span><span class="sxs-lookup"><span data-stu-id="6f8b8-136">WCF Services and ASP.NET</span></span>](../../../../docs/framework/wcf/feature-details/wcf-services-and-aspnet.md)
- [<span data-ttu-id="6f8b8-137">セキュリティ</span><span class="sxs-lookup"><span data-stu-id="6f8b8-137">Security</span></span>](../../../../docs/framework/wcf/feature-details/security.md)
- [<span data-ttu-id="6f8b8-138">AppFabric のホスティング機能</span><span class="sxs-lookup"><span data-stu-id="6f8b8-138">Windows Server App Fabric Hosting Features</span></span>](https://go.microsoft.com/fwlink/?LinkId=201276)
