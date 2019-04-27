---
title: <iriParsing> 要素 (Uri 設定)
ms.date: 03/30/2017
ms.assetid: 953d0b53-445e-41f9-b302-77c4030852ce
ms.openlocfilehash: 7033f4dcda7d2fe73310ae0d36d9b05c090d13d4
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61674520"
---
# <a name="iriparsing-element-uri-settings"></a><span data-ttu-id="01280-102">\<iriParsing > 要素 (Uri 設定)</span><span class="sxs-lookup"><span data-stu-id="01280-102">\<iriParsing> Element (Uri Settings)</span></span>
<span data-ttu-id="01280-103">International Resource Identifier (IRI) 解析が、<xref:System.Uri> に適用されるかどうか、および IRI の解析規則が適用されるどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="01280-103">Specifies if International Resource Identifier (IRI) parsing is applied to a <xref:System.Uri> and whether IRI parsing rules should be applied.</span></span>  
  
## <a name="schema-hierarchy"></a><span data-ttu-id="01280-104">スキーマの階層</span><span class="sxs-lookup"><span data-stu-id="01280-104">Schema Hierarchy</span></span>  
 [<span data-ttu-id="01280-105">\<configuration> 要素</span><span class="sxs-lookup"><span data-stu-id="01280-105">\<configuration> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)  
  
 [<span data-ttu-id="01280-106">\<Uri> 要素 (Uri 設定)</span><span class="sxs-lookup"><span data-stu-id="01280-106">\<Uri> Element (Uri Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/uri-element-uri-settings.md)  
  
 [<span data-ttu-id="01280-107">\<iriParsing ></span><span class="sxs-lookup"><span data-stu-id="01280-107">\<iriParsing></span></span>](../../../../../docs/framework/configure-apps/file-schema/network/iriparsing-element-uri-settings.md)  
  
## <a name="syntax"></a><span data-ttu-id="01280-108">構文</span><span class="sxs-lookup"><span data-stu-id="01280-108">Syntax</span></span>  
  
```xml  
<iriParsing  
  enabled="true|false"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="01280-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="01280-109">Attributes and Elements</span></span>  
 <span data-ttu-id="01280-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="01280-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="01280-111">属性</span><span class="sxs-lookup"><span data-stu-id="01280-111">Attributes</span></span>  
  
|<span data-ttu-id="01280-112">**要素**</span><span class="sxs-lookup"><span data-stu-id="01280-112">**Element**</span></span>|<span data-ttu-id="01280-113">**説明**</span><span class="sxs-lookup"><span data-stu-id="01280-113">**Description**</span></span>|  
|-----------------|---------------------|  
|`enabled`|<span data-ttu-id="01280-114">解析する IRI が有効になっているかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="01280-114">Specifies whether IRI parsing is enabled.</span></span> <span data-ttu-id="01280-115">既定値は `false` です。</span><span class="sxs-lookup"><span data-stu-id="01280-115">The default value is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="01280-116">子要素</span><span class="sxs-lookup"><span data-stu-id="01280-116">Child Elements</span></span>  
 <span data-ttu-id="01280-117">なし</span><span class="sxs-lookup"><span data-stu-id="01280-117">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="01280-118">親要素</span><span class="sxs-lookup"><span data-stu-id="01280-118">Parent Elements</span></span>  
  
|<span data-ttu-id="01280-119">**要素**</span><span class="sxs-lookup"><span data-stu-id="01280-119">**Element**</span></span>|<span data-ttu-id="01280-120">**説明**</span><span class="sxs-lookup"><span data-stu-id="01280-120">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="01280-121">Uri</span><span class="sxs-lookup"><span data-stu-id="01280-121">uri</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/uri-element-uri-settings.md)|<span data-ttu-id="01280-122">.NET Framework での uniform resource identifier (Uri) を使用して表現された web アドレスの処理方法を指定する設定が含まれています。</span><span class="sxs-lookup"><span data-stu-id="01280-122">Contains settings that specify how the .NET Framework handles web addresses expressed using uniform resource identifiers (URIs).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="01280-123">Remarks</span><span class="sxs-lookup"><span data-stu-id="01280-123">Remarks</span></span>  
 <span data-ttu-id="01280-124">既存の<xref:System.Uri>クラスは、.NET Framework 3.5 で拡張されています。</span><span class="sxs-lookup"><span data-stu-id="01280-124">The existing <xref:System.Uri> class has been extended in .NET Framework 3.5.</span></span> <span data-ttu-id="01280-125">3.0 SP1、および 2.0 SP1 国際リソース識別子 (IRI) および国際化ドメイン名 (IDN) のサポートを提供します。</span><span class="sxs-lookup"><span data-stu-id="01280-125">3.0 SP1, and 2.0 SP1 to provide support for International Resource Identifiers (IRI) and Internationalized Domain Names (IDN).</span></span> <span data-ttu-id="01280-126">IRI と IDN 明確には、現在のユーザーに、.NET Framework 2.0 の動作から変更は表示されないをサポートします。</span><span class="sxs-lookup"><span data-stu-id="01280-126">Current users will not see any change from the .NET Framework 2.0 behavior unless they specifically enable IRI and IDN support.</span></span> <span data-ttu-id="01280-127">これにより、.NET Framework の以前のバージョンとのアプリケーションの互換性を保証します。</span><span class="sxs-lookup"><span data-stu-id="01280-127">This ensures application compatibility with prior versions of the .NET Framework.</span></span>  
  
 <span data-ttu-id="01280-128">IRI のサポートを有効にするのには、次の 2 つの変更が必要です。</span><span class="sxs-lookup"><span data-stu-id="01280-128">To enable support for IRI, the following two changes are required:</span></span>  
  
1. <span data-ttu-id="01280-129">.NET Framework 2.0 のディレクトリの machine.config ファイルに次の行を追加します。</span><span class="sxs-lookup"><span data-stu-id="01280-129">Add the following line to the machine.config file under the .NET Framework 2.0 directory</span></span>  
  
    ```xml  
    <section name="uri" type="System.Configuration.UriSection, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
    ```  
  
2. <span data-ttu-id="01280-130">IRI 解析規則を適用する必要があるかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="01280-130">Specify whether IRI parsing rules should be applied.</span></span> <span data-ttu-id="01280-131">これは、machine.config ファイルまたは app.config ファイルで指定できます。</span><span class="sxs-lookup"><span data-stu-id="01280-131">This can be done in the machine.config or in the app.config file.</span></span>  
  
 <span data-ttu-id="01280-132">IRI 解析を有効にする (iriParsing を有効になっている = `true`) 正規化を行うし、RFC 3987 ルール文字に従って最新の IRI チェックします。</span><span class="sxs-lookup"><span data-stu-id="01280-132">Enabling IRI parsing (iriParsing enabled = `true`) will do normalization and character checking according to the latest IRI rules in RFC 3987.</span></span> <span data-ttu-id="01280-133">既定値は`false`とは正規化を実行し、チェックに従って RFC 2396 および RFC 3986 を (IPv6 のリテラル) の文字します。</span><span class="sxs-lookup"><span data-stu-id="01280-133">The default value is `false` and will do normalization and character checking according to RFC 2396 and RFC 3986 (for IPv6 literals).</span></span>  
  
### <a name="configuration-files"></a><span data-ttu-id="01280-134">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="01280-134">Configuration Files</span></span>  
 <span data-ttu-id="01280-135">この要素は、アプリケーション構成ファイルまたはマシン構成ファイル (Machine.config) で使用できます。</span><span class="sxs-lookup"><span data-stu-id="01280-135">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="01280-136">例</span><span class="sxs-lookup"><span data-stu-id="01280-136">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="01280-137">説明</span><span class="sxs-lookup"><span data-stu-id="01280-137">Description</span></span>  
 <span data-ttu-id="01280-138">次の例で使用する構成を示しています、<xref:System.Uri>解析する IRI と IDN 名をサポートするクラス。</span><span class="sxs-lookup"><span data-stu-id="01280-138">The following example shows a configuration used by the <xref:System.Uri> class to support IRI parsing and IDN names.</span></span>  
  
### <a name="code"></a><span data-ttu-id="01280-139">コード</span><span class="sxs-lookup"><span data-stu-id="01280-139">Code</span></span>  
  
```xml  
<configuration>  
  <uri>  
    <idn enabled="All" />  
    <iriParsing enabled="true" />  
  </uri>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="01280-140">関連項目</span><span class="sxs-lookup"><span data-stu-id="01280-140">See also</span></span>

- <xref:System.Configuration.IriParsingElement?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection?displayProperty=nameWithType>
- [<span data-ttu-id="01280-141">ネットワーク設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="01280-141">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
