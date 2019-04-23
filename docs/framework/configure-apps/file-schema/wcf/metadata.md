---
title: <metadata>
ms.date: 03/30/2017
ms.assetid: d09653eb-e355-4c73-b87b-28f93d56480d
ms.openlocfilehash: c0c9848d073c799e1f97dd79b375848dfab71e99
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59191485"
---
# <a name="metadata"></a><span data-ttu-id="1647f-101">\<matadata></span><span class="sxs-lookup"><span data-stu-id="1647f-101">\<metadata></span></span>
<span data-ttu-id="1647f-102">サービス メタデータを処理する方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="1647f-102">Specifies how service metadata can be processed.</span></span>  
  
 <span data-ttu-id="1647f-103">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="1647f-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="1647f-104">\<client></span><span class="sxs-lookup"><span data-stu-id="1647f-104">\<client></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1647f-105">構文</span><span class="sxs-lookup"><span data-stu-id="1647f-105">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <client>
    <metadata>
      <policyImporters>
        <policyImporter type="string" />
      </policyImporters>
      <wsdlImporters>
        <wsdlImporter type="string" />
      </wsdlImporters>
    </metadata>
  </client>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1647f-106">属性および要素</span><span class="sxs-lookup"><span data-stu-id="1647f-106">Attributes and Elements</span></span>  
 <span data-ttu-id="1647f-107">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="1647f-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1647f-108">属性</span><span class="sxs-lookup"><span data-stu-id="1647f-108">Attributes</span></span>  
 <span data-ttu-id="1647f-109">なし。</span><span class="sxs-lookup"><span data-stu-id="1647f-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="1647f-110">子要素</span><span class="sxs-lookup"><span data-stu-id="1647f-110">Child Elements</span></span>  
  
|<span data-ttu-id="1647f-111">要素</span><span class="sxs-lookup"><span data-stu-id="1647f-111">Element</span></span>|<span data-ttu-id="1647f-112">説明</span><span class="sxs-lookup"><span data-stu-id="1647f-112">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1647f-113">\<policyImporters></span><span class="sxs-lookup"><span data-stu-id="1647f-113">\<policyImporters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/policyimporters.md)|<span data-ttu-id="1647f-114">バインディングに関するカスタム ポリシー アサーションのインポートを制御するすべてのポリシー インポーターを指定します。</span><span class="sxs-lookup"><span data-stu-id="1647f-114">Specifies all the policy importers that control the import of custom policy assertions about bindings.</span></span> <span data-ttu-id="1647f-115">ポリシー インポーターは、バインディング機能についてのカスタム ポリシー アサーションの検索、およびアサーションで必要となる機能を実装するカスタム バインド要素の結び付けに使用されます。</span><span class="sxs-lookup"><span data-stu-id="1647f-115">A policy importer is used to search custom policy assertions about binding features, as well as attach a custom binding element that implements the features the assertion requires.</span></span>|  
|[<span data-ttu-id="1647f-116">\<wsdlImporters></span><span class="sxs-lookup"><span data-stu-id="1647f-116">\<wsdlImporters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsdlimporters.md)|<span data-ttu-id="1647f-117">WS-Policy が添付された Web サービス記述言語 (WSDL) 1.1 メタデータをインポートするすべての WSDL インポーターを指定します。</span><span class="sxs-lookup"><span data-stu-id="1647f-117">Specifies all the WSDL importers that import Web Services Description Language (WSDL) 1.1 metadata with WS-Policy attachments.</span></span> <span data-ttu-id="1647f-118">WSDL インポーターは、メタデータのインポートに加えて、コントラクトおよびエンドポイント情報を表すさまざまなクラスにその情報を変換するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="1647f-118">A WSDL importer is used to import metadata as well as convert that information into various classes that represent contract and endpoint information.</span></span> <span data-ttu-id="1647f-119">コントラクトおよびエンドポイントの情報やプロパティを選択的にインポートできます。これらは、任意のインポート エラーを公開し、インポートおよび変換プロセスに関連する型情報を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="1647f-119">It can selectively import contract and endpoint information and properties that expose any import errors and accept type information relevant to the import and conversion process.</span></span> <span data-ttu-id="1647f-120">また、任意のポリシー ドキュメント、WSDL ドキュメント、WSDL 拡張、および XML スキーマ ドキュメントにアクセスするためのバインディング情報およびプロパティのインポートもサポートします。</span><span class="sxs-lookup"><span data-stu-id="1647f-120">It also supports importing binding information and properties that provide access to any policy documents, WSDL documents, WSDL extensions, and XML schema documents.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="1647f-121">親要素</span><span class="sxs-lookup"><span data-stu-id="1647f-121">Parent Elements</span></span>  
  
|<span data-ttu-id="1647f-122">要素</span><span class="sxs-lookup"><span data-stu-id="1647f-122">Element</span></span>|<span data-ttu-id="1647f-123">説明</span><span class="sxs-lookup"><span data-stu-id="1647f-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1647f-124">\<client></span><span class="sxs-lookup"><span data-stu-id="1647f-124">\<client></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/client.md)|<span data-ttu-id="1647f-125">クライアントが接続可能なエンドポイントの一覧を定義するクライアント セクション。</span><span class="sxs-lookup"><span data-stu-id="1647f-125">The client section defines a list of endpoints that a client can connect to.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1647f-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="1647f-126">See also</span></span>

- <xref:System.ServiceModel.Configuration.MetadataElement>
- <xref:System.ServiceModel.Configuration.PolicyImporterElementCollection>
- <xref:System.ServiceModel.Configuration.WsdlImporterElementCollection>
- <xref:System.ServiceModel.Description.MetadataImporter>
- <xref:System.ServiceModel.Description.WsdlImporter>
- [<span data-ttu-id="1647f-127">WCF クライアントの構成</span><span class="sxs-lookup"><span data-stu-id="1647f-127">WCF Client Configuration</span></span>](../../../../../docs/framework/wcf/feature-details/client-configuration.md)
- [<span data-ttu-id="1647f-128">クライアント</span><span class="sxs-lookup"><span data-stu-id="1647f-128">Clients</span></span>](../../../../../docs/framework/wcf/feature-details/clients.md)
