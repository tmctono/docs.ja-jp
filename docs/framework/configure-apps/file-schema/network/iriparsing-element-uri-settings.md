---
title: <iriParsing> 要素 (Uri 設定)
ms.date: 03/30/2017
ms.assetid: 953d0b53-445e-41f9-b302-77c4030852ce
ms.openlocfilehash: 2c99edf2f1a03e0e510858c106cad43b0eaa27b4
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/21/2019
ms.locfileid: "69664088"
---
# <a name="iriparsing-element-uri-settings"></a><span data-ttu-id="dfe0b-102">\<iriParsing 要素 (Uri 設定)</span><span class="sxs-lookup"><span data-stu-id="dfe0b-102">\<iriParsing> Element (Uri Settings)</span></span>
<span data-ttu-id="dfe0b-103">International Resource Identifier (IRI) 解析が、<xref:System.Uri> に適用されるかどうか、および IRI の解析規則が適用されるどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="dfe0b-103">Specifies if International Resource Identifier (IRI) parsing is applied to a <xref:System.Uri> and whether IRI parsing rules should be applied.</span></span>  
  
## <a name="schema-hierarchy"></a><span data-ttu-id="dfe0b-104">スキーマの階層</span><span class="sxs-lookup"><span data-stu-id="dfe0b-104">Schema Hierarchy</span></span>  
 [<span data-ttu-id="dfe0b-105">\<configuration> 要素</span><span class="sxs-lookup"><span data-stu-id="dfe0b-105">\<configuration> Element</span></span>](../configuration-element.md)  
  
 [<span data-ttu-id="dfe0b-106">\<Uri> 要素 (Uri 設定)</span><span class="sxs-lookup"><span data-stu-id="dfe0b-106">\<Uri> Element (Uri Settings)</span></span>](uri-element-uri-settings.md)  
  
 [<span data-ttu-id="dfe0b-107">\<iriParsing ></span><span class="sxs-lookup"><span data-stu-id="dfe0b-107">\<iriParsing></span></span>](iriparsing-element-uri-settings.md)  
  
## <a name="syntax"></a><span data-ttu-id="dfe0b-108">構文</span><span class="sxs-lookup"><span data-stu-id="dfe0b-108">Syntax</span></span>  
  
```xml  
<iriParsing  
  enabled="true|false"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="dfe0b-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="dfe0b-109">Attributes and Elements</span></span>  
 <span data-ttu-id="dfe0b-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="dfe0b-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="dfe0b-111">属性</span><span class="sxs-lookup"><span data-stu-id="dfe0b-111">Attributes</span></span>  
  
|<span data-ttu-id="dfe0b-112">**要素**</span><span class="sxs-lookup"><span data-stu-id="dfe0b-112">**Element**</span></span>|<span data-ttu-id="dfe0b-113">**説明**</span><span class="sxs-lookup"><span data-stu-id="dfe0b-113">**Description**</span></span>|  
|-----------------|---------------------|  
|`enabled`|<span data-ttu-id="dfe0b-114">IRI 解析を有効にするかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="dfe0b-114">Specifies whether IRI parsing is enabled.</span></span> <span data-ttu-id="dfe0b-115">既定値は `false` です。</span><span class="sxs-lookup"><span data-stu-id="dfe0b-115">The default value is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="dfe0b-116">子要素</span><span class="sxs-lookup"><span data-stu-id="dfe0b-116">Child Elements</span></span>  
 <span data-ttu-id="dfe0b-117">なし</span><span class="sxs-lookup"><span data-stu-id="dfe0b-117">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="dfe0b-118">親要素</span><span class="sxs-lookup"><span data-stu-id="dfe0b-118">Parent Elements</span></span>  
  
|<span data-ttu-id="dfe0b-119">**要素**</span><span class="sxs-lookup"><span data-stu-id="dfe0b-119">**Element**</span></span>|<span data-ttu-id="dfe0b-120">**説明**</span><span class="sxs-lookup"><span data-stu-id="dfe0b-120">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="dfe0b-121">uri</span><span class="sxs-lookup"><span data-stu-id="dfe0b-121">uri</span></span>](uri-element-uri-settings.md)|<span data-ttu-id="dfe0b-122">.NET Framework が、uniform resource identifier (Uri) を使用して表された web アドレスを処理する方法を指定する設定が含まれます。</span><span class="sxs-lookup"><span data-stu-id="dfe0b-122">Contains settings that specify how the .NET Framework handles web addresses expressed using uniform resource identifiers (URIs).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dfe0b-123">Remarks</span><span class="sxs-lookup"><span data-stu-id="dfe0b-123">Remarks</span></span>  
 <span data-ttu-id="dfe0b-124">既存<xref:System.Uri>のクラスは .NET Framework 3.5 で拡張されています。</span><span class="sxs-lookup"><span data-stu-id="dfe0b-124">The existing <xref:System.Uri> class has been extended in .NET Framework 3.5.</span></span> <span data-ttu-id="dfe0b-125">3.0 SP1 および 2.0 SP1 では、International Resource Identifier (IRI) と国際化ドメイン名 (IDN) のサポートが提供されます。</span><span class="sxs-lookup"><span data-stu-id="dfe0b-125">3.0 SP1, and 2.0 SP1 to provide support for International Resource Identifiers (IRI) and Internationalized Domain Names (IDN).</span></span> <span data-ttu-id="dfe0b-126">現在のユーザーには、IRI と IDN のサポートを明示的に有効にしない限り、.NET Framework 2.0 の動作からの変更は表示されません。</span><span class="sxs-lookup"><span data-stu-id="dfe0b-126">Current users will not see any change from the .NET Framework 2.0 behavior unless they specifically enable IRI and IDN support.</span></span> <span data-ttu-id="dfe0b-127">これにより、.NET Framework の以前のバージョンとのアプリケーションの互換性を保証します。</span><span class="sxs-lookup"><span data-stu-id="dfe0b-127">This ensures application compatibility with prior versions of the .NET Framework.</span></span>  
  
 <span data-ttu-id="dfe0b-128">IRI のサポートを有効にするには、次の2つの変更が必要です。</span><span class="sxs-lookup"><span data-stu-id="dfe0b-128">To enable support for IRI, the following two changes are required:</span></span>  
  
1. <span data-ttu-id="dfe0b-129">Machine.config ファイルの .NET Framework 2.0 ディレクトリの下に次の行を追加します。</span><span class="sxs-lookup"><span data-stu-id="dfe0b-129">Add the following line to the machine.config file under the .NET Framework 2.0 directory</span></span>  
  
    ```xml  
    <section name="uri" type="System.Configuration.UriSection, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
    ```  
  
2. <span data-ttu-id="dfe0b-130">IRI 解析規則を適用するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="dfe0b-130">Specify whether IRI parsing rules should be applied.</span></span> <span data-ttu-id="dfe0b-131">これは、machine.config ファイルまたは app.config ファイルで指定できます。</span><span class="sxs-lookup"><span data-stu-id="dfe0b-131">This can be done in the machine.config or in the app.config file.</span></span>  
  
 <span data-ttu-id="dfe0b-132">Iri 解析を有効にすると (iriparsing 有効 = `true`)、RFC 3987 の最新の IRI 規則に従って、正規化と文字チェックが実行されます。</span><span class="sxs-lookup"><span data-stu-id="dfe0b-132">Enabling IRI parsing (iriParsing enabled = `true`) will do normalization and character checking according to the latest IRI rules in RFC 3987.</span></span> <span data-ttu-id="dfe0b-133">既定値は`false`で、rfc 2396 および rfc 3986 (IPv6 リテラルの場合) に従って、正規化と文字チェックが実行されます。</span><span class="sxs-lookup"><span data-stu-id="dfe0b-133">The default value is `false` and will do normalization and character checking according to RFC 2396 and RFC 3986 (for IPv6 literals).</span></span>  
  
### <a name="configuration-files"></a><span data-ttu-id="dfe0b-134">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="dfe0b-134">Configuration Files</span></span>  
 <span data-ttu-id="dfe0b-135">この要素は、アプリケーション構成ファイルまたはマシン構成ファイル (Machine.config) で使用できます。</span><span class="sxs-lookup"><span data-stu-id="dfe0b-135">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="dfe0b-136">例</span><span class="sxs-lookup"><span data-stu-id="dfe0b-136">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="dfe0b-137">説明</span><span class="sxs-lookup"><span data-stu-id="dfe0b-137">Description</span></span>  
 <span data-ttu-id="dfe0b-138">次の例は、IRI 解析と IDN <xref:System.Uri>名をサポートするためにクラスによって使用される構成を示しています。</span><span class="sxs-lookup"><span data-stu-id="dfe0b-138">The following example shows a configuration used by the <xref:System.Uri> class to support IRI parsing and IDN names.</span></span>  
  
### <a name="code"></a><span data-ttu-id="dfe0b-139">コード</span><span class="sxs-lookup"><span data-stu-id="dfe0b-139">Code</span></span>  
  
```xml  
<configuration>  
  <uri>  
    <idn enabled="All" />  
    <iriParsing enabled="true" />  
  </uri>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="dfe0b-140">関連項目</span><span class="sxs-lookup"><span data-stu-id="dfe0b-140">See also</span></span>

- <xref:System.Configuration.IriParsingElement?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection?displayProperty=nameWithType>
- [<span data-ttu-id="dfe0b-141">ネットワーク設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="dfe0b-141">Network Settings Schema</span></span>](index.md)
