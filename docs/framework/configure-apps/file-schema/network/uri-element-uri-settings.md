---
title: <Uri> 要素 (Uri 設定)
ms.date: 03/30/2017
ms.assetid: c22bab8b-477c-4ae4-8498-65ad409e0847
ms.openlocfilehash: 80d71da5ca680872e4948fa8ff135fbbdf08cffe
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/21/2019
ms.locfileid: "69663967"
---
# <a name="uri-element-uri-settings"></a><span data-ttu-id="2c1e6-102">\<Uri > 要素 (Uri 設定)</span><span class="sxs-lookup"><span data-stu-id="2c1e6-102">\<Uri> Element (Uri Settings)</span></span>
<span data-ttu-id="2c1e6-103">.NET Framework が、uniform resource identifier (Uri) を使用して表された web アドレスを処理する方法を指定する設定が含まれます。</span><span class="sxs-lookup"><span data-stu-id="2c1e6-103">Contains settings that specify how the .NET Framework handles web addresses expressed using uniform resource identifiers (URIs).</span></span>  
  
## <a name="schema-hierarchy"></a><span data-ttu-id="2c1e6-104">スキーマの階層</span><span class="sxs-lookup"><span data-stu-id="2c1e6-104">Schema Hierarchy</span></span>  
 [<span data-ttu-id="2c1e6-105">\<configuration> 要素</span><span class="sxs-lookup"><span data-stu-id="2c1e6-105">\<configuration> Element</span></span>](../configuration-element.md)  
  
 [<span data-ttu-id="2c1e6-106">\<uri></span><span class="sxs-lookup"><span data-stu-id="2c1e6-106">\<uri></span></span>](uri-element-uri-settings.md)  
  
## <a name="syntax"></a><span data-ttu-id="2c1e6-107">構文</span><span class="sxs-lookup"><span data-stu-id="2c1e6-107">Syntax</span></span>  
  
```xml  
<uri>  
</uri>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2c1e6-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="2c1e6-108">Attributes and Elements</span></span>  
 <span data-ttu-id="2c1e6-109">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="2c1e6-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2c1e6-110">属性</span><span class="sxs-lookup"><span data-stu-id="2c1e6-110">Attributes</span></span>  
 <span data-ttu-id="2c1e6-111">なし。</span><span class="sxs-lookup"><span data-stu-id="2c1e6-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="2c1e6-112">子要素</span><span class="sxs-lookup"><span data-stu-id="2c1e6-112">Child Elements</span></span>  
  
|<span data-ttu-id="2c1e6-113">**要素**</span><span class="sxs-lookup"><span data-stu-id="2c1e6-113">**Element**</span></span>|<span data-ttu-id="2c1e6-114">**説明**</span><span class="sxs-lookup"><span data-stu-id="2c1e6-114">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="2c1e6-115">idn</span><span class="sxs-lookup"><span data-stu-id="2c1e6-115">idn</span></span>](idn-element-uri-settings.md)|<span data-ttu-id="2c1e6-116">国際化ドメイン名 (IDN) の解析がドメイン名に適用されるかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="2c1e6-116">Specifies if Internationalized Domain Name (IDN) parsing is applied to domain names.</span></span>|  
|[<span data-ttu-id="2c1e6-117">Iriparsing></span><span class="sxs-lookup"><span data-stu-id="2c1e6-117">iriParsing</span></span>](iriparsing-element-uri-settings.md)|<span data-ttu-id="2c1e6-118">国際化リソース識別子 (iri) の解析を適用するか<xref:System.Uri>どうか、および iri 解析規則を適用するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="2c1e6-118">Specifies if International Resource Identifier (IRI) parsing is applied to <xref:System.Uri> and whether IRI parsing rules should be applied.</span></span>|  
|[<span data-ttu-id="2c1e6-119">schemeSettings</span><span class="sxs-lookup"><span data-stu-id="2c1e6-119">schemeSettings</span></span>](schemesettings-element-uri-settings.md)|<span data-ttu-id="2c1e6-120"><xref:System.Uri> が特定のスキームに解析される方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="2c1e6-120">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="2c1e6-121">親要素</span><span class="sxs-lookup"><span data-stu-id="2c1e6-121">Parent Elements</span></span>  
  
|<span data-ttu-id="2c1e6-122">**要素**</span><span class="sxs-lookup"><span data-stu-id="2c1e6-122">**Element**</span></span>|<span data-ttu-id="2c1e6-123">**説明**</span><span class="sxs-lookup"><span data-stu-id="2c1e6-123">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="2c1e6-124">configuration</span><span class="sxs-lookup"><span data-stu-id="2c1e6-124">configuration</span></span>](../configuration-element.md)|<span data-ttu-id="2c1e6-125">すべての名前空間の設定が含まれます。</span><span class="sxs-lookup"><span data-stu-id="2c1e6-125">Contains settings for all namespaces.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2c1e6-126">Remarks</span><span class="sxs-lookup"><span data-stu-id="2c1e6-126">Remarks</span></span>  
 <span data-ttu-id="2c1e6-127">要素には、 <xref:System.Net>名前空間のクラス<xref:System.Uri>によって使用されるクラスのメンバーの設定が含まれます。 `uri`</span><span class="sxs-lookup"><span data-stu-id="2c1e6-127">The `uri` element contains settings for members of the <xref:System.Uri> class used by classes in the <xref:System.Net> namespace.</span></span> <span data-ttu-id="2c1e6-128">この設定により、IRI と IDN のサポートが構成されます。</span><span class="sxs-lookup"><span data-stu-id="2c1e6-128">The settings configure support for IRI and IDN.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2c1e6-129">例</span><span class="sxs-lookup"><span data-stu-id="2c1e6-129">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="2c1e6-130">説明</span><span class="sxs-lookup"><span data-stu-id="2c1e6-130">Description</span></span>  
 <span data-ttu-id="2c1e6-131">次の例は、IRI 解析と IDN <xref:System.Uri>名をサポートするためにクラスによって使用される構成を示しています。</span><span class="sxs-lookup"><span data-stu-id="2c1e6-131">The following example shows a configuration used by the <xref:System.Uri> class to support IRI parsing and IDN names.</span></span> <span data-ttu-id="2c1e6-132">また、この例では、すべてのスキーム設定をクリアした後、http スキームに対してパーセントでエンコードされたパス区切り記号をエスケープしないためのサポートを追加します。</span><span class="sxs-lookup"><span data-stu-id="2c1e6-132">The example also clears all scheme settings and then adds support for not escaping percent-encoded path delimiters for the http scheme.</span></span>  
  
### <a name="code"></a><span data-ttu-id="2c1e6-133">コード</span><span class="sxs-lookup"><span data-stu-id="2c1e6-133">Code</span></span>  
  
```xml  
<configuration>  
  <uri>  
    <idn enabled="All" />  
    <iriParsing enabled="true" />  
    <schemeSettings>  
      <clear/>  
      <add name="http" genericUriParserOptions="DontUnescapePathDotsAndSlashes"/>  
    </schemeSettings>  
  </uri>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="2c1e6-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="2c1e6-134">See also</span></span>

- [<span data-ttu-id="2c1e6-135">ネットワーク設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="2c1e6-135">Network Settings Schema</span></span>](index.md)
