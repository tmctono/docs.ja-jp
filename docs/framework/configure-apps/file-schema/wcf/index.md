---
title: WCF 構成スキーマ
ms.date: 03/30/2017
ms.assetid: c282aeb5-91f0-4522-8e2f-704c1ef3651f
ms.openlocfilehash: 160be2ea43d1530cdb2ccd3de1f9e6a2e4d0aca3
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/15/2020
ms.locfileid: "90536393"
---
# <a name="wcf-configuration-schema"></a><span data-ttu-id="f7ef7-102">WCF 構成スキーマ</span><span class="sxs-lookup"><span data-stu-id="f7ef7-102">WCF Configuration Schema</span></span>
<span data-ttu-id="f7ef7-103">Windows Communication Foundation (WCF) 構成要素を使用すると、WCF サービスとクライアントアプリケーションを構成できます。</span><span class="sxs-lookup"><span data-stu-id="f7ef7-103">Windows Communication Foundation (WCF) configuration elements enable you to configure WCF service and client applications.</span></span> <span data-ttu-id="f7ef7-104">[ 構成エディター ツール (SvcConfigEditor.exe)](../../../wcf/configuration-editor-tool-svcconfigeditor-exe.md) を使用して、クライアントとサービスの構成ファイルを作成および変更できます。</span><span class="sxs-lookup"><span data-stu-id="f7ef7-104">You can use the [Configuration Editor Tool (SvcConfigEditor.exe)](../../../wcf/configuration-editor-tool-svcconfigeditor-exe.md) to create and modify configuration files for clients and services.</span></span> <span data-ttu-id="f7ef7-105">構成ファイルは XML として書式設定されているので、テキスト エディターを使用して手動で編集する場合は、XML について理解している必要があります。</span><span class="sxs-lookup"><span data-stu-id="f7ef7-105">Since the configuration files are formatted as XML, you must be familiar with XML if you want to manually edit them using a text editor.</span></span> <span data-ttu-id="f7ef7-106">理解しないで編集すると、XML 要素タグや属性が見つからないなどの問題が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f7ef7-106">Otherwise, you may run into issues such as an unfound XML element tag or attribute.</span></span> <span data-ttu-id="f7ef7-107">問題の原因は、XML 要素タグと属性が大文字と小文字を区別することによります。</span><span class="sxs-lookup"><span data-stu-id="f7ef7-107">This is because XML element tags and attributes are case-sensitive.</span></span>  
  
 <span data-ttu-id="f7ef7-108">WCF 構成システムは、名前空間に基づいてい <xref:System.Configuration> ます。</span><span class="sxs-lookup"><span data-stu-id="f7ef7-108">The WCF configuration system is based on the <xref:System.Configuration> namespace.</span></span> <span data-ttu-id="f7ef7-109">したがって、<xref:System.Configuration> 名前空間によって提供される、構成ロック、暗号化、マージなどのすべての標準機能を使用して、アプリケーションとその構成のセキュリティを強化できます。</span><span class="sxs-lookup"><span data-stu-id="f7ef7-109">Therefore, you can use all the standard features provided by the <xref:System.Configuration> namespace, such as configuration locking, encryption and merging to increase the security of your application and its configuration.</span></span> <span data-ttu-id="f7ef7-110">これらの概念の詳細については、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f7ef7-110">For more information on these concepts, see the following topics.</span></span>  
  
 <span data-ttu-id="f7ef7-111">[保護された構成を使用した構成情報の暗号化](/previous-versions/aspnet/53tyfkaw(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="f7ef7-111">[Encrypting Configuration Information](/previous-versions/aspnet/53tyfkaw(v=vs.100))</span></span>  
  
 <span data-ttu-id="f7ef7-112">[構成設定のロック](/previous-versions/aspnet/55th21y4(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="f7ef7-112">[Locking Configuration Settings](/previous-versions/aspnet/55th21y4(v=vs.100))</span></span>  
  
 <span data-ttu-id="f7ef7-113">このセクションでは、各構成項目のすべての可能な値についてと各構成項目が他の WCF 構成要素とやり取りする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="f7ef7-113">This section describes all possible values of each configuration item, and how it interacts with other WCF configuration elements.</span></span> <span data-ttu-id="f7ef7-114">次のマップは、WCF 構成スキーマを示しています。</span><span class="sxs-lookup"><span data-stu-id="f7ef7-114">The following map illustrates the WCF configuration schema:</span></span>  
  
 ![WCF 構成スキーマを示す図。](./media/index/windows-communication-foundation-configuration-schema.gif)  
  
> [!CAUTION]
> <span data-ttu-id="f7ef7-116">アプリケーション構成ファイル (app.config) の WCF 構成セクションは、適切な Access Control リスト (ACL) を使用して保護し、潜在的なセキュリティ上の脅威を防ぐ必要があります。</span><span class="sxs-lookup"><span data-stu-id="f7ef7-116">You should protect WCF configuration sections in your application configuration files (app.config) with appropriate Access Control Lists (ACL) to prevent any potential security threats.</span></span>  <span data-ttu-id="f7ef7-117">たとえば、適切なユーザーだけが、アプリケーション バインドのセキュリティ設定、またはサービスの構成ファイルのサービス モデル セクションにアクセスまたは変更できるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f7ef7-117">For example, you should make sure that only the appropriate people can access or modify the security settings on application bindings, or the service model section of the configuration file for a service.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f7ef7-118">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="f7ef7-118">In This Section</span></span>  
 [\<system.serviceModel>](system-servicemodel.md)  
 <span data-ttu-id="f7ef7-119">`ServiceModel` 要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="f7ef7-119">Describes the `ServiceModel` element.</span></span>  
  
 [\<system.serviceModel.activation>](system-servicemodel-activation.md)  
 <span data-ttu-id="f7ef7-120">SMSvcHost.exe ツールを構成します。</span><span class="sxs-lookup"><span data-stu-id="f7ef7-120">Configures the SMSvcHost.exe tool.</span></span>  
  
 [\<system.runtime.serialization>](system-runtime-serialization.md)  
 <span data-ttu-id="f7ef7-121"><xref:System.Runtime.Serialization.DataContractSerializer> などのシリアライザーの使用時にオプションを設定するための最上位の要素。</span><span class="sxs-lookup"><span data-stu-id="f7ef7-121">The top-level element for setting options when using serializers such as the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="f7ef7-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="f7ef7-122">Related Sections</span></span>  
 [<span data-ttu-id="f7ef7-123">Configuring Windows Communication Foundation Applications</span><span class="sxs-lookup"><span data-stu-id="f7ef7-123">Configuring Windows Communication Foundation Applications</span></span>](../../../wcf/configuring-services.md)  
 <span data-ttu-id="f7ef7-124">WCF サービスとクライアントを構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="f7ef7-124">Describes how to configure WCF services and clients.</span></span>
