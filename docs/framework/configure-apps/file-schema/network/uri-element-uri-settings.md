---
title: <uri> 要素 (Uri 設定)
ms.date: 03/30/2017
ms.assetid: c22bab8b-477c-4ae4-8498-65ad409e0847
ms.openlocfilehash: a492baf9951466383ca0277a2927b8554e5bb332
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2019
ms.locfileid: "71697438"
---
# <a name="uri-element-uri-settings"></a><span data-ttu-id="d92a1-102">\<uri > 要素 (Uri 設定)</span><span class="sxs-lookup"><span data-stu-id="d92a1-102">\<uri> Element (Uri Settings)</span></span>
<span data-ttu-id="d92a1-103">.NET Framework が、uniform resource identifier (Uri) を使用して表された web アドレスを処理する方法を指定する設定が含まれます。</span><span class="sxs-lookup"><span data-stu-id="d92a1-103">Contains settings that specify how the .NET Framework handles web addresses expressed using uniform resource identifiers (URIs).</span></span>  
  
[<span data-ttu-id="d92a1-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="d92a1-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="d92a1-105">&nbsp;&nbsp; **\<uri >**</span><span class="sxs-lookup"><span data-stu-id="d92a1-105">&nbsp;&nbsp;**\<uri>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d92a1-106">構文</span><span class="sxs-lookup"><span data-stu-id="d92a1-106">Syntax</span></span>  
  
```xml  
<uri>  
</uri>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d92a1-107">属性と要素</span><span class="sxs-lookup"><span data-stu-id="d92a1-107">Attributes and Elements</span></span>  
 <span data-ttu-id="d92a1-108">次のセクションでは、属性、子要素、親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="d92a1-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d92a1-109">属性</span><span class="sxs-lookup"><span data-stu-id="d92a1-109">Attributes</span></span>  
 <span data-ttu-id="d92a1-110">[なし]。</span><span class="sxs-lookup"><span data-stu-id="d92a1-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="d92a1-111">子要素</span><span class="sxs-lookup"><span data-stu-id="d92a1-111">Child Elements</span></span>  
  
|<span data-ttu-id="d92a1-112">**要素**</span><span class="sxs-lookup"><span data-stu-id="d92a1-112">**Element**</span></span>|<span data-ttu-id="d92a1-113">**説明**</span><span class="sxs-lookup"><span data-stu-id="d92a1-113">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="d92a1-114">idn</span><span class="sxs-lookup"><span data-stu-id="d92a1-114">idn</span></span>](idn-element-uri-settings.md)|<span data-ttu-id="d92a1-115">国際化ドメイン名 (IDN) の解析がドメイン名に適用されるかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="d92a1-115">Specifies if Internationalized Domain Name (IDN) parsing is applied to domain names.</span></span>|  
|[<span data-ttu-id="d92a1-116">Iriparsing></span><span class="sxs-lookup"><span data-stu-id="d92a1-116">iriParsing</span></span>](iriparsing-element-uri-settings.md)|<span data-ttu-id="d92a1-117">国際化リソース識別子 (IRI) の解析を <xref:System.Uri> に適用するかどうか、および IRI 解析規則を適用するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="d92a1-117">Specifies if International Resource Identifier (IRI) parsing is applied to <xref:System.Uri> and whether IRI parsing rules should be applied.</span></span>|  
|[<span data-ttu-id="d92a1-118">schemeSettings</span><span class="sxs-lookup"><span data-stu-id="d92a1-118">schemeSettings</span></span>](schemesettings-element-uri-settings.md)|<span data-ttu-id="d92a1-119"><xref:System.Uri> が特定のスキームに解析される方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="d92a1-119">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d92a1-120">親要素</span><span class="sxs-lookup"><span data-stu-id="d92a1-120">Parent Elements</span></span>  
  
|<span data-ttu-id="d92a1-121">**要素**</span><span class="sxs-lookup"><span data-stu-id="d92a1-121">**Element**</span></span>|<span data-ttu-id="d92a1-122">**説明**</span><span class="sxs-lookup"><span data-stu-id="d92a1-122">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="d92a1-123">configuration</span><span class="sxs-lookup"><span data-stu-id="d92a1-123">configuration</span></span>](../configuration-element.md)|<span data-ttu-id="d92a1-124">すべての名前空間の設定が含まれます。</span><span class="sxs-lookup"><span data-stu-id="d92a1-124">Contains settings for all namespaces.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d92a1-125">コメント</span><span class="sxs-lookup"><span data-stu-id="d92a1-125">Remarks</span></span>  
 <span data-ttu-id="d92a1-126">`uri` 要素には、<xref:System.Net> 名前空間のクラスによって使用される <xref:System.Uri> クラスのメンバーの設定が含まれています。</span><span class="sxs-lookup"><span data-stu-id="d92a1-126">The `uri` element contains settings for members of the <xref:System.Uri> class used by classes in the <xref:System.Net> namespace.</span></span> <span data-ttu-id="d92a1-127">この設定により、IRI と IDN のサポートが構成されます。</span><span class="sxs-lookup"><span data-stu-id="d92a1-127">The settings configure support for IRI and IDN.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d92a1-128">例</span><span class="sxs-lookup"><span data-stu-id="d92a1-128">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="d92a1-129">説明</span><span class="sxs-lookup"><span data-stu-id="d92a1-129">Description</span></span>  
 <span data-ttu-id="d92a1-130">次の例は、IRI 解析と IDN 名をサポートするために <xref:System.Uri> クラスによって使用される構成を示しています。</span><span class="sxs-lookup"><span data-stu-id="d92a1-130">The following example shows a configuration used by the <xref:System.Uri> class to support IRI parsing and IDN names.</span></span> <span data-ttu-id="d92a1-131">また、この例では、すべてのスキーム設定をクリアした後、http スキームに対してパーセントでエンコードされたパス区切り記号をエスケープしないためのサポートを追加します。</span><span class="sxs-lookup"><span data-stu-id="d92a1-131">The example also clears all scheme settings and then adds support for not escaping percent-encoded path delimiters for the http scheme.</span></span>  
  
### <a name="code"></a><span data-ttu-id="d92a1-132">コード</span><span class="sxs-lookup"><span data-stu-id="d92a1-132">Code</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="d92a1-133">参照</span><span class="sxs-lookup"><span data-stu-id="d92a1-133">See also</span></span>

- [<span data-ttu-id="d92a1-134">ネットワーク設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="d92a1-134">Network Settings Schema</span></span>](index.md)
