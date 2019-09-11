---
title: <wsdlImporter>
ms.date: 03/30/2017
ms.assetid: 986b2165-8430-4dba-b1b8-00396841bb96
ms.openlocfilehash: 317921a66fa3b8d1f0026d676ea674b67732b3df
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2019
ms.locfileid: "70854759"
---
# <a name="wsdlimporter"></a><span data-ttu-id="b3bad-101">\<wsdlImporter ></span><span class="sxs-lookup"><span data-stu-id="b3bad-101">\<wsdlImporter></span></span>
<span data-ttu-id="b3bad-102">WS-Policy が添付された Web サービス記述言語 (WSDL) 1.1 メタデータをインポートするすべての WSDL インポーターを指定します。</span><span class="sxs-lookup"><span data-stu-id="b3bad-102">Specifies all the WSDL importers that imports Web Services Description Language (WSDL) 1.1 metadata with WS-Policy attachments.</span></span>  
  
<span data-ttu-id="b3bad-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="b3bad-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="b3bad-104">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="b3bad-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="b3bad-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<クライアント >** ](client.md)</span><span class="sxs-lookup"><span data-stu-id="b3bad-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<client>**](client.md)</span></span>\
<span data-ttu-id="b3bad-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<メタデータ >** ](metadata.md)</span><span class="sxs-lookup"><span data-stu-id="b3bad-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<metadata>**](metadata.md)</span></span>\
<span data-ttu-id="b3bad-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<wsdlImporters >** ](wsdlimporters.md)</span><span class="sxs-lookup"><span data-stu-id="b3bad-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsdlImporters>**](wsdlimporters.md)</span></span>  
<span data-ttu-id="b3bad-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<wsdlImporter >**</span><span class="sxs-lookup"><span data-stu-id="b3bad-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<wsdlImporter>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b3bad-109">構文</span><span class="sxs-lookup"><span data-stu-id="b3bad-109">Syntax</span></span>  
  
```xml  
<metadata>
  <wsdlImporters>
    <wsdlImporter type="string" />
  </wsdlImporters>
</metadata>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b3bad-110">属性および要素</span><span class="sxs-lookup"><span data-stu-id="b3bad-110">Attributes and Elements</span></span>  
 <span data-ttu-id="b3bad-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="b3bad-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b3bad-112">属性</span><span class="sxs-lookup"><span data-stu-id="b3bad-112">Attributes</span></span>  
  
|<span data-ttu-id="b3bad-113">属性</span><span class="sxs-lookup"><span data-stu-id="b3bad-113">Attribute</span></span>|<span data-ttu-id="b3bad-114">説明</span><span class="sxs-lookup"><span data-stu-id="b3bad-114">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="b3bad-115">この要素の型です。</span><span class="sxs-lookup"><span data-stu-id="b3bad-115">The type of this element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b3bad-116">子要素</span><span class="sxs-lookup"><span data-stu-id="b3bad-116">Child Elements</span></span>  
 <span data-ttu-id="b3bad-117">なし。</span><span class="sxs-lookup"><span data-stu-id="b3bad-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b3bad-118">親要素</span><span class="sxs-lookup"><span data-stu-id="b3bad-118">Parent Elements</span></span>  
  
|<span data-ttu-id="b3bad-119">要素</span><span class="sxs-lookup"><span data-stu-id="b3bad-119">Element</span></span>|<span data-ttu-id="b3bad-120">説明</span><span class="sxs-lookup"><span data-stu-id="b3bad-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b3bad-121">\<wsdlImporters ></span><span class="sxs-lookup"><span data-stu-id="b3bad-121">\<wsdlImporters></span></span>](wsdlimporters.md)|<span data-ttu-id="b3bad-122">WS-Policy が添付された Web サービス記述言語 (WSDL) 1.1 メタデータをインポートするすべての WSDL インポーターを指定します。</span><span class="sxs-lookup"><span data-stu-id="b3bad-122">Specifies all the WSDL importers that imports Web Services Description Language (WSDL) 1.1 metadata with WS-Policy attachments.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b3bad-123">Remarks</span><span class="sxs-lookup"><span data-stu-id="b3bad-123">Remarks</span></span>  
 <span data-ttu-id="b3bad-124">WSDL インポーターは、メタデータのインポートに加えて、コントラクトおよびエンドポイント情報を表すさまざまなクラスにその情報を変換するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="b3bad-124">A WSDL importer is used to import metadata as well as convert that information into various classes that represent contract and endpoint information.</span></span> <span data-ttu-id="b3bad-125">コントラクトおよびエンドポイントの情報やプロパティを選択的にインポートできます。これらは、任意のインポート エラーを公開し、インポートおよび変換プロセスに関連する型情報を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="b3bad-125">It can selectively import contract and endpoint information and properties that expose any import errors and accept type information relevant to the import and conversion process.</span></span> <span data-ttu-id="b3bad-126">また、任意のポリシー ドキュメント、WSDL ドキュメント、WSDL 拡張、および XML スキーマ ドキュメントにアクセスするためのバインディング情報およびプロパティのインポートもサポートします。</span><span class="sxs-lookup"><span data-stu-id="b3bad-126">It also supports importing binding information and properties that provide access to any policy documents, WSDL documents, WSDL extensions, and XML schema documents.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3bad-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="b3bad-127">See also</span></span>

- <xref:System.ServiceModel.Configuration.WsdlImporterElement>
- <xref:System.ServiceModel.Configuration.MetadataElement>
- <xref:System.ServiceModel.Configuration.WsdlImporterElementCollection>
- <xref:System.ServiceModel.Description.MetadataImporter>
- <xref:System.ServiceModel.Description.WsdlImporter>
- [<span data-ttu-id="b3bad-128">WCF クライアントの構成</span><span class="sxs-lookup"><span data-stu-id="b3bad-128">WCF Client Configuration</span></span>](../../../wcf/feature-details/client-configuration.md)
- [<span data-ttu-id="b3bad-129">クライアント</span><span class="sxs-lookup"><span data-stu-id="b3bad-129">Clients</span></span>](../../../wcf/feature-details/clients.md)
