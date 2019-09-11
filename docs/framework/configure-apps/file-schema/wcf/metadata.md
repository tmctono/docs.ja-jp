---
title: <metadata>
ms.date: 03/30/2017
ms.assetid: d09653eb-e355-4c73-b87b-28f93d56480d
ms.openlocfilehash: 028e4d3fbe7bce06caa7497c8f95f3b293a4b068
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855230"
---
# <a name="metadata"></a><span data-ttu-id="ff87d-101">\<matadata></span><span class="sxs-lookup"><span data-stu-id="ff87d-101">\<metadata></span></span>
<span data-ttu-id="ff87d-102">サービス メタデータを処理する方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="ff87d-102">Specifies how service metadata can be processed.</span></span>  
  
<span data-ttu-id="ff87d-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="ff87d-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="ff87d-104">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="ff87d-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="ff87d-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<クライアント >** ](client.md)</span><span class="sxs-lookup"><span data-stu-id="ff87d-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<client>**](client.md)</span></span>\
<span data-ttu-id="ff87d-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<メタデータ >**</span><span class="sxs-lookup"><span data-stu-id="ff87d-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<metadata>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ff87d-107">構文</span><span class="sxs-lookup"><span data-stu-id="ff87d-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ff87d-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="ff87d-108">Attributes and Elements</span></span>  
 <span data-ttu-id="ff87d-109">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="ff87d-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ff87d-110">属性</span><span class="sxs-lookup"><span data-stu-id="ff87d-110">Attributes</span></span>  
 <span data-ttu-id="ff87d-111">なし。</span><span class="sxs-lookup"><span data-stu-id="ff87d-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="ff87d-112">子要素</span><span class="sxs-lookup"><span data-stu-id="ff87d-112">Child Elements</span></span>  
  
|<span data-ttu-id="ff87d-113">要素</span><span class="sxs-lookup"><span data-stu-id="ff87d-113">Element</span></span>|<span data-ttu-id="ff87d-114">説明</span><span class="sxs-lookup"><span data-stu-id="ff87d-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ff87d-115">\<policyImporters></span><span class="sxs-lookup"><span data-stu-id="ff87d-115">\<policyImporters></span></span>](policyimporters.md)|<span data-ttu-id="ff87d-116">バインディングに関するカスタム ポリシー アサーションのインポートを制御するすべてのポリシー インポーターを指定します。</span><span class="sxs-lookup"><span data-stu-id="ff87d-116">Specifies all the policy importers that control the import of custom policy assertions about bindings.</span></span> <span data-ttu-id="ff87d-117">ポリシー インポーターは、バインディング機能についてのカスタム ポリシー アサーションの検索、およびアサーションで必要となる機能を実装するカスタム バインド要素の結び付けに使用されます。</span><span class="sxs-lookup"><span data-stu-id="ff87d-117">A policy importer is used to search custom policy assertions about binding features, as well as attach a custom binding element that implements the features the assertion requires.</span></span>|  
|[<span data-ttu-id="ff87d-118">\<wsdlImporters ></span><span class="sxs-lookup"><span data-stu-id="ff87d-118">\<wsdlImporters></span></span>](wsdlimporters.md)|<span data-ttu-id="ff87d-119">WS-Policy が添付された Web サービス記述言語 (WSDL) 1.1 メタデータをインポートするすべての WSDL インポーターを指定します。</span><span class="sxs-lookup"><span data-stu-id="ff87d-119">Specifies all the WSDL importers that import Web Services Description Language (WSDL) 1.1 metadata with WS-Policy attachments.</span></span> <span data-ttu-id="ff87d-120">WSDL インポーターは、メタデータのインポートに加えて、コントラクトおよびエンドポイント情報を表すさまざまなクラスにその情報を変換するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="ff87d-120">A WSDL importer is used to import metadata as well as convert that information into various classes that represent contract and endpoint information.</span></span> <span data-ttu-id="ff87d-121">コントラクトおよびエンドポイントの情報やプロパティを選択的にインポートできます。これらは、任意のインポート エラーを公開し、インポートおよび変換プロセスに関連する型情報を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="ff87d-121">It can selectively import contract and endpoint information and properties that expose any import errors and accept type information relevant to the import and conversion process.</span></span> <span data-ttu-id="ff87d-122">また、任意のポリシー ドキュメント、WSDL ドキュメント、WSDL 拡張、および XML スキーマ ドキュメントにアクセスするためのバインディング情報およびプロパティのインポートもサポートします。</span><span class="sxs-lookup"><span data-stu-id="ff87d-122">It also supports importing binding information and properties that provide access to any policy documents, WSDL documents, WSDL extensions, and XML schema documents.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ff87d-123">親要素</span><span class="sxs-lookup"><span data-stu-id="ff87d-123">Parent Elements</span></span>  
  
|<span data-ttu-id="ff87d-124">要素</span><span class="sxs-lookup"><span data-stu-id="ff87d-124">Element</span></span>|<span data-ttu-id="ff87d-125">説明</span><span class="sxs-lookup"><span data-stu-id="ff87d-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ff87d-126">\<クライアント ></span><span class="sxs-lookup"><span data-stu-id="ff87d-126">\<client></span></span>](client.md)|<span data-ttu-id="ff87d-127">クライアントが接続可能なエンドポイントの一覧を定義するクライアント セクション。</span><span class="sxs-lookup"><span data-stu-id="ff87d-127">The client section defines a list of endpoints that a client can connect to.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ff87d-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="ff87d-128">See also</span></span>

- <xref:System.ServiceModel.Configuration.MetadataElement>
- <xref:System.ServiceModel.Configuration.PolicyImporterElementCollection>
- <xref:System.ServiceModel.Configuration.WsdlImporterElementCollection>
- <xref:System.ServiceModel.Description.MetadataImporter>
- <xref:System.ServiceModel.Description.WsdlImporter>
- [<span data-ttu-id="ff87d-129">WCF クライアントの構成</span><span class="sxs-lookup"><span data-stu-id="ff87d-129">WCF Client Configuration</span></span>](../../../wcf/feature-details/client-configuration.md)
- [<span data-ttu-id="ff87d-130">クライアント</span><span class="sxs-lookup"><span data-stu-id="ff87d-130">Clients</span></span>](../../../wcf/feature-details/clients.md)
