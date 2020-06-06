---
title: <metadata>
ms.date: 03/30/2017
ms.assetid: d09653eb-e355-4c73-b87b-28f93d56480d
ms.openlocfilehash: 028e4d3fbe7bce06caa7497c8f95f3b293a4b068
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "70855230"
---
# \<metadata>
<span data-ttu-id="8786b-101">サービス メタデータを処理する方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="8786b-101">Specifies how service metadata can be processed.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<client>**](client.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<metadata>**  
  
## <a name="syntax"></a><span data-ttu-id="8786b-102">構文</span><span class="sxs-lookup"><span data-stu-id="8786b-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8786b-103">属性および要素</span><span class="sxs-lookup"><span data-stu-id="8786b-103">Attributes and Elements</span></span>  
 <span data-ttu-id="8786b-104">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="8786b-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8786b-105">属性</span><span class="sxs-lookup"><span data-stu-id="8786b-105">Attributes</span></span>  
 <span data-ttu-id="8786b-106">なし。</span><span class="sxs-lookup"><span data-stu-id="8786b-106">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="8786b-107">子要素</span><span class="sxs-lookup"><span data-stu-id="8786b-107">Child Elements</span></span>  
  
|<span data-ttu-id="8786b-108">要素</span><span class="sxs-lookup"><span data-stu-id="8786b-108">Element</span></span>|<span data-ttu-id="8786b-109">説明</span><span class="sxs-lookup"><span data-stu-id="8786b-109">Description</span></span>|  
|-------------|-----------------|  
|[\<policyImporters>](policyimporters.md)|<span data-ttu-id="8786b-110">バインディングに関するカスタム ポリシー アサーションのインポートを制御するすべてのポリシー インポーターを指定します。</span><span class="sxs-lookup"><span data-stu-id="8786b-110">Specifies all the policy importers that control the import of custom policy assertions about bindings.</span></span> <span data-ttu-id="8786b-111">ポリシー インポーターは、バインディング機能についてのカスタム ポリシー アサーションの検索、およびアサーションで必要となる機能を実装するカスタム バインド要素の結び付けに使用されます。</span><span class="sxs-lookup"><span data-stu-id="8786b-111">A policy importer is used to search custom policy assertions about binding features, as well as attach a custom binding element that implements the features the assertion requires.</span></span>|  
|[\<wsdlImporters>](wsdlimporters.md)|<span data-ttu-id="8786b-112">WS-Policy が添付された Web サービス記述言語 (WSDL) 1.1 メタデータをインポートするすべての WSDL インポーターを指定します。</span><span class="sxs-lookup"><span data-stu-id="8786b-112">Specifies all the WSDL importers that import Web Services Description Language (WSDL) 1.1 metadata with WS-Policy attachments.</span></span> <span data-ttu-id="8786b-113">WSDL インポーターは、メタデータのインポートに加えて、コントラクトおよびエンドポイント情報を表すさまざまなクラスにその情報を変換するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="8786b-113">A WSDL importer is used to import metadata as well as convert that information into various classes that represent contract and endpoint information.</span></span> <span data-ttu-id="8786b-114">コントラクトおよびエンドポイントの情報やプロパティを選択的にインポートできます。これらは、任意のインポート エラーを公開し、インポートおよび変換プロセスに関連する型情報を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="8786b-114">It can selectively import contract and endpoint information and properties that expose any import errors and accept type information relevant to the import and conversion process.</span></span> <span data-ttu-id="8786b-115">また、任意のポリシー ドキュメント、WSDL ドキュメント、WSDL 拡張、および XML スキーマ ドキュメントにアクセスするためのバインディング情報およびプロパティのインポートもサポートします。</span><span class="sxs-lookup"><span data-stu-id="8786b-115">It also supports importing binding information and properties that provide access to any policy documents, WSDL documents, WSDL extensions, and XML schema documents.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="8786b-116">親要素</span><span class="sxs-lookup"><span data-stu-id="8786b-116">Parent Elements</span></span>  
  
|<span data-ttu-id="8786b-117">要素</span><span class="sxs-lookup"><span data-stu-id="8786b-117">Element</span></span>|<span data-ttu-id="8786b-118">説明</span><span class="sxs-lookup"><span data-stu-id="8786b-118">Description</span></span>|  
|-------------|-----------------|  
|[\<client>](client.md)|<span data-ttu-id="8786b-119">クライアントが接続可能なエンドポイントの一覧を定義するクライアント セクション。</span><span class="sxs-lookup"><span data-stu-id="8786b-119">The client section defines a list of endpoints that a client can connect to.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8786b-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="8786b-120">See also</span></span>

- <xref:System.ServiceModel.Configuration.MetadataElement>
- <xref:System.ServiceModel.Configuration.PolicyImporterElementCollection>
- <xref:System.ServiceModel.Configuration.WsdlImporterElementCollection>
- <xref:System.ServiceModel.Description.MetadataImporter>
- <xref:System.ServiceModel.Description.WsdlImporter>
- [<span data-ttu-id="8786b-121">WCF クライアントの構成</span><span class="sxs-lookup"><span data-stu-id="8786b-121">WCF Client Configuration</span></span>](../../../wcf/feature-details/client-configuration.md)
- [<span data-ttu-id="8786b-122">クライアント</span><span class="sxs-lookup"><span data-stu-id="8786b-122">Clients</span></span>](../../../wcf/feature-details/clients.md)
