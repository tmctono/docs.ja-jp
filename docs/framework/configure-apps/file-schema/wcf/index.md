---
title: WCF 構成スキーマ
ms.date: 03/30/2017
ms.assetid: c282aeb5-91f0-4522-8e2f-704c1ef3651f
ms.openlocfilehash: baea1e49bce10054530afa5b6f282023d5ceb981
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61755816"
---
# <a name="wcf-configuration-schema"></a><span data-ttu-id="8e3d6-102">WCF 構成スキーマ</span><span class="sxs-lookup"><span data-stu-id="8e3d6-102">WCF Configuration Schema</span></span>
<span data-ttu-id="8e3d6-103">Windows Communication Foundation (WCF) 構成要素を使用すると、WCF サービスとクライアント アプリケーションを構成できます。</span><span class="sxs-lookup"><span data-stu-id="8e3d6-103">Windows Communication Foundation (WCF) configuration elements enable you to configure WCF service and client applications.</span></span> <span data-ttu-id="8e3d6-104">[ 構成エディター ツール (SvcConfigEditor.exe)](../../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md) を使用して、クライアントとサービスの構成ファイルを作成および変更できます。</span><span class="sxs-lookup"><span data-stu-id="8e3d6-104">You can use the [Configuration Editor Tool (SvcConfigEditor.exe)](../../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md) to create and modify configuration files for clients and services.</span></span> <span data-ttu-id="8e3d6-105">構成ファイルは XML として書式設定されているので、テキスト エディターを使用して手動で編集する場合は、XML について理解している必要があります。</span><span class="sxs-lookup"><span data-stu-id="8e3d6-105">Since the configuration files are formatted as XML, you must be familiar with XML if you want to manually edit them using a text editor.</span></span> <span data-ttu-id="8e3d6-106">理解しないで編集すると、XML 要素タグや属性が見つからないなどの問題が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="8e3d6-106">Otherwise, you may run into issues such as an unfound XML element tag or attribute.</span></span> <span data-ttu-id="8e3d6-107">問題の原因は、XML 要素タグと属性が大文字と小文字を区別することによります。</span><span class="sxs-lookup"><span data-stu-id="8e3d6-107">This is because XML element tags and attributes are case-sensitive.</span></span>  
  
 <span data-ttu-id="8e3d6-108">WCF 構成システムがに基づいて、<xref:System.Configuration>名前空間。</span><span class="sxs-lookup"><span data-stu-id="8e3d6-108">The WCF configuration system is based on the <xref:System.Configuration> namespace.</span></span> <span data-ttu-id="8e3d6-109">したがって、<xref:System.Configuration> 名前空間によって提供される、構成ロック、暗号化、マージなどのすべての標準機能を使用して、アプリケーションとその構成のセキュリティを強化できます。</span><span class="sxs-lookup"><span data-stu-id="8e3d6-109">Therefore, you can use all the standard features provided by the <xref:System.Configuration> namespace, such as configuration locking, encryption and merging to increase the security of your application and its configuration.</span></span> <span data-ttu-id="8e3d6-110">これらの概念の詳細については、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8e3d6-110">For more information on these concepts, see the following topics.</span></span>  
  
 [<span data-ttu-id="8e3d6-111">保護された構成を使用した構成情報の暗号化</span><span class="sxs-lookup"><span data-stu-id="8e3d6-111">Encrypting Configuration Information</span></span>](https://go.microsoft.com/fwlink/?LinkId=95337)  
  
 [<span data-ttu-id="8e3d6-112">構成設定のロック</span><span class="sxs-lookup"><span data-stu-id="8e3d6-112">Locking Configuration Settings</span></span>](https://go.microsoft.com/fwlink/?LinkId=95338)  
  
 <span data-ttu-id="8e3d6-113">このセクションでは、各構成項目のすべての可能な値についてと各構成項目が他の WCF 構成要素とやり取りする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="8e3d6-113">This section describes all possible values of each configuration item, and how it interacts with other WCF configuration elements.</span></span> <span data-ttu-id="8e3d6-114">次のマップは、WCF 構成スキーマを示しています。</span><span class="sxs-lookup"><span data-stu-id="8e3d6-114">The following map illustrates the WCF configuration schema:</span></span>  
  
 ![WCF 構成スキーマを示す図。](./media/index/windows-communication-foundation-configuration-schema.gif)  
  
> [!CAUTION]
>  <span data-ttu-id="8e3d6-116">アプリケーション構成ファイル (app.config) で適切なアクセス制御リスト (ACL) の潜在的なセキュリティ脅威を防止する WCF の構成セクションを保護する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8e3d6-116">You should protect WCF configuration sections in your application configuration files (app.config) with appropriate Access Control Lists (ACL) to prevent any potential security threats.</span></span>  <span data-ttu-id="8e3d6-117">たとえば、適切なユーザーだけが、アプリケーション バインドのセキュリティ設定、またはサービスの構成ファイルのサービス モデル セクションにアクセスまたは変更できるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="8e3d6-117">For example, you should make sure that only the appropriate people can access or modify the security settings on application bindings, or the service model section of the configuration file for a service.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8e3d6-118">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="8e3d6-118">In This Section</span></span>  
 [<span data-ttu-id="8e3d6-119">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="8e3d6-119">\<system.serviceModel></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)  
 <span data-ttu-id="8e3d6-120">`ServiceModel` 要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="8e3d6-120">Describes the `ServiceModel` element.</span></span>  
  
 [<span data-ttu-id="8e3d6-121">\<system.serviceModel.activation ></span><span class="sxs-lookup"><span data-stu-id="8e3d6-121">\<system.serviceModel.activation></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel-activation.md)  
 <span data-ttu-id="8e3d6-122">SMSvcHost.exe ツールを構成します。</span><span class="sxs-lookup"><span data-stu-id="8e3d6-122">Configures the SMSvcHost.exe tool.</span></span>  
  
 [<span data-ttu-id="8e3d6-123">\<system.runtime.serialization ></span><span class="sxs-lookup"><span data-stu-id="8e3d6-123">\<system.runtime.serialization></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-runtime-serialization.md)  
 <span data-ttu-id="8e3d6-124"><xref:System.Runtime.Serialization.DataContractSerializer> などのシリアライザーの使用時にオプションを設定するための最上位の要素。</span><span class="sxs-lookup"><span data-stu-id="8e3d6-124">The top-level element for setting options when using serializers such as the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="8e3d6-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="8e3d6-125">Related Sections</span></span>  
 [<span data-ttu-id="8e3d6-126">Windows Communication Foundation アプリケーションの構成</span><span class="sxs-lookup"><span data-stu-id="8e3d6-126">Configuring Windows Communication Foundation Applications</span></span>](../../../wcf/configuring-services.md)  
 <span data-ttu-id="8e3d6-127">WCF サービスとクライアントを構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="8e3d6-127">Describes how to configure WCF services and clients.</span></span>
