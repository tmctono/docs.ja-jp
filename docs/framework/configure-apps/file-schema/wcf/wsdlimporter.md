---
title: <wsdlImporter>
ms.date: 03/30/2017
ms.assetid: 986b2165-8430-4dba-b1b8-00396841bb96
ms.openlocfilehash: 317921a66fa3b8d1f0026d676ea674b67732b3df
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "70854759"
---
# \<wsdlImporter>
<span data-ttu-id="699d1-101">WS-Policy が添付された Web サービス記述言語 (WSDL) 1.1 メタデータをインポートするすべての WSDL インポーターを指定します。</span><span class="sxs-lookup"><span data-stu-id="699d1-101">Specifies all the WSDL importers that imports Web Services Description Language (WSDL) 1.1 metadata with WS-Policy attachments.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<client>**](client.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<metadata>**](metadata.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsdlImporters>**](wsdlimporters.md)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<wsdlImporter>**  
  
## <a name="syntax"></a><span data-ttu-id="699d1-102">構文</span><span class="sxs-lookup"><span data-stu-id="699d1-102">Syntax</span></span>  
  
```xml  
<metadata>
  <wsdlImporters>
    <wsdlImporter type="string" />
  </wsdlImporters>
</metadata>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="699d1-103">属性および要素</span><span class="sxs-lookup"><span data-stu-id="699d1-103">Attributes and Elements</span></span>  
 <span data-ttu-id="699d1-104">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="699d1-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="699d1-105">属性</span><span class="sxs-lookup"><span data-stu-id="699d1-105">Attributes</span></span>  
  
|<span data-ttu-id="699d1-106">属性</span><span class="sxs-lookup"><span data-stu-id="699d1-106">Attribute</span></span>|<span data-ttu-id="699d1-107">説明</span><span class="sxs-lookup"><span data-stu-id="699d1-107">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="699d1-108">この要素の型です。</span><span class="sxs-lookup"><span data-stu-id="699d1-108">The type of this element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="699d1-109">子要素</span><span class="sxs-lookup"><span data-stu-id="699d1-109">Child Elements</span></span>  
 <span data-ttu-id="699d1-110">なし。</span><span class="sxs-lookup"><span data-stu-id="699d1-110">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="699d1-111">親要素</span><span class="sxs-lookup"><span data-stu-id="699d1-111">Parent Elements</span></span>  
  
|<span data-ttu-id="699d1-112">要素</span><span class="sxs-lookup"><span data-stu-id="699d1-112">Element</span></span>|<span data-ttu-id="699d1-113">Description</span><span class="sxs-lookup"><span data-stu-id="699d1-113">Description</span></span>|  
|-------------|-----------------|  
|[\<wsdlImporters>](wsdlimporters.md)|<span data-ttu-id="699d1-114">WS-Policy が添付された Web サービス記述言語 (WSDL) 1.1 メタデータをインポートするすべての WSDL インポーターを指定します。</span><span class="sxs-lookup"><span data-stu-id="699d1-114">Specifies all the WSDL importers that imports Web Services Description Language (WSDL) 1.1 metadata with WS-Policy attachments.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="699d1-115">解説</span><span class="sxs-lookup"><span data-stu-id="699d1-115">Remarks</span></span>  
 <span data-ttu-id="699d1-116">WSDL インポーターは、メタデータのインポートに加えて、コントラクトおよびエンドポイント情報を表すさまざまなクラスにその情報を変換するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="699d1-116">A WSDL importer is used to import metadata as well as convert that information into various classes that represent contract and endpoint information.</span></span> <span data-ttu-id="699d1-117">コントラクトおよびエンドポイントの情報やプロパティを選択的にインポートできます。これらは、任意のインポート エラーを公開し、インポートおよび変換プロセスに関連する型情報を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="699d1-117">It can selectively import contract and endpoint information and properties that expose any import errors and accept type information relevant to the import and conversion process.</span></span> <span data-ttu-id="699d1-118">また、任意のポリシー ドキュメント、WSDL ドキュメント、WSDL 拡張、および XML スキーマ ドキュメントにアクセスするためのバインディング情報およびプロパティのインポートもサポートします。</span><span class="sxs-lookup"><span data-stu-id="699d1-118">It also supports importing binding information and properties that provide access to any policy documents, WSDL documents, WSDL extensions, and XML schema documents.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="699d1-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="699d1-119">See also</span></span>

- <xref:System.ServiceModel.Configuration.WsdlImporterElement>
- <xref:System.ServiceModel.Configuration.MetadataElement>
- <xref:System.ServiceModel.Configuration.WsdlImporterElementCollection>
- <xref:System.ServiceModel.Description.MetadataImporter>
- <xref:System.ServiceModel.Description.WsdlImporter>
- [<span data-ttu-id="699d1-120">WCF クライアントの構成</span><span class="sxs-lookup"><span data-stu-id="699d1-120">WCF Client Configuration</span></span>](../../../wcf/feature-details/client-configuration.md)
- [<span data-ttu-id="699d1-121">クライアント</span><span class="sxs-lookup"><span data-stu-id="699d1-121">Clients</span></span>](../../../wcf/feature-details/clients.md)
