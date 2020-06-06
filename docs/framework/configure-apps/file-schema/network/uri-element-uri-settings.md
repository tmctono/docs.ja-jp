---
title: <uri> 要素 (Uri 設定)
ms.date: 03/30/2017
ms.assetid: c22bab8b-477c-4ae4-8498-65ad409e0847
ms.openlocfilehash: a492baf9951466383ca0277a2927b8554e5bb332
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "71697438"
---
# <a name="uri-element-uri-settings"></a><span data-ttu-id="1d592-102">\<uri> 要素 (Uri 設定)</span><span class="sxs-lookup"><span data-stu-id="1d592-102">\<uri> Element (Uri Settings)</span></span>
<span data-ttu-id="1d592-103">.NET Framework が、uniform resource identifier (Uri) を使用して表された web アドレスを処理する方法を指定する設定が含まれます。</span><span class="sxs-lookup"><span data-stu-id="1d592-103">Contains settings that specify how the .NET Framework handles web addresses expressed using uniform resource identifiers (URIs).</span></span>  
  
[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;**\<uri>**  
  
## <a name="syntax"></a><span data-ttu-id="1d592-104">構文</span><span class="sxs-lookup"><span data-stu-id="1d592-104">Syntax</span></span>  
  
```xml  
<uri>  
</uri>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1d592-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="1d592-105">Attributes and Elements</span></span>  
 <span data-ttu-id="1d592-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="1d592-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1d592-107">属性</span><span class="sxs-lookup"><span data-stu-id="1d592-107">Attributes</span></span>  
 <span data-ttu-id="1d592-108">なし。</span><span class="sxs-lookup"><span data-stu-id="1d592-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="1d592-109">子要素</span><span class="sxs-lookup"><span data-stu-id="1d592-109">Child Elements</span></span>  
  
|<span data-ttu-id="1d592-110">**要素**</span><span class="sxs-lookup"><span data-stu-id="1d592-110">**Element**</span></span>|<span data-ttu-id="1d592-111">**説明**</span><span class="sxs-lookup"><span data-stu-id="1d592-111">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="1d592-112">idn</span><span class="sxs-lookup"><span data-stu-id="1d592-112">idn</span></span>](idn-element-uri-settings.md)|<span data-ttu-id="1d592-113">国際化ドメイン名 (IDN) の解析がドメイン名に適用されるかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="1d592-113">Specifies if Internationalized Domain Name (IDN) parsing is applied to domain names.</span></span>|  
|[<span data-ttu-id="1d592-114">Iriparsing></span><span class="sxs-lookup"><span data-stu-id="1d592-114">iriParsing</span></span>](iriparsing-element-uri-settings.md)|<span data-ttu-id="1d592-115">国際化リソース識別子 (IRI) の解析を適用する <xref:System.Uri> かどうか、および iri 解析規則を適用するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="1d592-115">Specifies if International Resource Identifier (IRI) parsing is applied to <xref:System.Uri> and whether IRI parsing rules should be applied.</span></span>|  
|[<span data-ttu-id="1d592-116">schemeSettings</span><span class="sxs-lookup"><span data-stu-id="1d592-116">schemeSettings</span></span>](schemesettings-element-uri-settings.md)|<span data-ttu-id="1d592-117"><xref:System.Uri> が特定のスキームに解析される方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="1d592-117">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="1d592-118">親要素</span><span class="sxs-lookup"><span data-stu-id="1d592-118">Parent Elements</span></span>  
  
|<span data-ttu-id="1d592-119">**要素**</span><span class="sxs-lookup"><span data-stu-id="1d592-119">**Element**</span></span>|<span data-ttu-id="1d592-120">**説明**</span><span class="sxs-lookup"><span data-stu-id="1d592-120">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="1d592-121">configuration</span><span class="sxs-lookup"><span data-stu-id="1d592-121">configuration</span></span>](../configuration-element.md)|<span data-ttu-id="1d592-122">すべての名前空間の設定が含まれます。</span><span class="sxs-lookup"><span data-stu-id="1d592-122">Contains settings for all namespaces.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1d592-123">解説</span><span class="sxs-lookup"><span data-stu-id="1d592-123">Remarks</span></span>  
 <span data-ttu-id="1d592-124">要素には、 `uri` <xref:System.Uri> 名前空間のクラスによって使用されるクラスのメンバーの設定が含まれ <xref:System.Net> ます。</span><span class="sxs-lookup"><span data-stu-id="1d592-124">The `uri` element contains settings for members of the <xref:System.Uri> class used by classes in the <xref:System.Net> namespace.</span></span> <span data-ttu-id="1d592-125">この設定により、IRI と IDN のサポートが構成されます。</span><span class="sxs-lookup"><span data-stu-id="1d592-125">The settings configure support for IRI and IDN.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1d592-126">例</span><span class="sxs-lookup"><span data-stu-id="1d592-126">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="1d592-127">説明</span><span class="sxs-lookup"><span data-stu-id="1d592-127">Description</span></span>  
 <span data-ttu-id="1d592-128">次の例は、 <xref:System.Uri> IRI 解析と IDN 名をサポートするためにクラスによって使用される構成を示しています。</span><span class="sxs-lookup"><span data-stu-id="1d592-128">The following example shows a configuration used by the <xref:System.Uri> class to support IRI parsing and IDN names.</span></span> <span data-ttu-id="1d592-129">また、この例では、すべてのスキーム設定をクリアした後、http スキームに対してパーセントでエンコードされたパス区切り記号をエスケープしないためのサポートを追加します。</span><span class="sxs-lookup"><span data-stu-id="1d592-129">The example also clears all scheme settings and then adds support for not escaping percent-encoded path delimiters for the http scheme.</span></span>  
  
### <a name="code"></a><span data-ttu-id="1d592-130">コード</span><span class="sxs-lookup"><span data-stu-id="1d592-130">Code</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="1d592-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="1d592-131">See also</span></span>

- [<span data-ttu-id="1d592-132">ネットワーク設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="1d592-132">Network Settings Schema</span></span>](index.md)
