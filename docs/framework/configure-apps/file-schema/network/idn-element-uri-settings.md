---
title: <idn> 要素 (Uri 設定)
ms.date: 03/30/2017
ms.assetid: 16c8e869-1791-4cf5-9244-3d3c738f60ec
ms.openlocfilehash: 5fe2eafee702be96bfdca80a06af4a040d9ef0f6
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/21/2019
ms.locfileid: "69664118"
---
# <a name="idn-element-uri-settings"></a><span data-ttu-id="c478b-102">\<idn> 要素 (Uri 設定)</span><span class="sxs-lookup"><span data-stu-id="c478b-102">\<idn> Element (Uri Settings)</span></span>
<span data-ttu-id="c478b-103">国際化ドメイン名 (IDN) の解析がドメイン名に適用されるかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="c478b-103">Specifies if Internationalized Domain Name (IDN) parsing is applied to a domain name.</span></span>  
  
## <a name="schema-hierarchy"></a><span data-ttu-id="c478b-104">スキーマの階層</span><span class="sxs-lookup"><span data-stu-id="c478b-104">Schema Hierarchy</span></span>  
 [<span data-ttu-id="c478b-105">\<configuration> 要素</span><span class="sxs-lookup"><span data-stu-id="c478b-105">\<configuration> Element</span></span>](../configuration-element.md)  
  
 [<span data-ttu-id="c478b-106">\<Uri> 要素 (Uri 設定)</span><span class="sxs-lookup"><span data-stu-id="c478b-106">\<Uri> Element (Uri Settings)</span></span>](uri-element-uri-settings.md)  
  
 [<span data-ttu-id="c478b-107">\<idn></span><span class="sxs-lookup"><span data-stu-id="c478b-107">\<idn></span></span>](idn-element-uri-settings.md)  
  
## <a name="syntax"></a><span data-ttu-id="c478b-108">構文</span><span class="sxs-lookup"><span data-stu-id="c478b-108">Syntax</span></span>  
  
```xml  
<idn  
  enabled="All|AllExceptIntranet|None"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c478b-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="c478b-109">Attributes and Elements</span></span>  
 <span data-ttu-id="c478b-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="c478b-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c478b-111">属性</span><span class="sxs-lookup"><span data-stu-id="c478b-111">Attributes</span></span>  
  
|<span data-ttu-id="c478b-112">**要素**</span><span class="sxs-lookup"><span data-stu-id="c478b-112">**Element**</span></span>|<span data-ttu-id="c478b-113">**説明**</span><span class="sxs-lookup"><span data-stu-id="c478b-113">**Description**</span></span>|  
|-----------------|---------------------|  
|`enabled`|<span data-ttu-id="c478b-114">国際化ドメイン名 (IDN) の解析がドメイン名に適用されるかどうかを指定します。既定値は none です。</span><span class="sxs-lookup"><span data-stu-id="c478b-114">Specifies if Internationalized Domain Name (IDN) parsing is applied to a domain name The default value is none.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c478b-115">子要素</span><span class="sxs-lookup"><span data-stu-id="c478b-115">Child Elements</span></span>  
 <span data-ttu-id="c478b-116">なし</span><span class="sxs-lookup"><span data-stu-id="c478b-116">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c478b-117">親要素</span><span class="sxs-lookup"><span data-stu-id="c478b-117">Parent Elements</span></span>  
  
|<span data-ttu-id="c478b-118">**要素**</span><span class="sxs-lookup"><span data-stu-id="c478b-118">**Element**</span></span>|<span data-ttu-id="c478b-119">**説明**</span><span class="sxs-lookup"><span data-stu-id="c478b-119">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="c478b-120">uri</span><span class="sxs-lookup"><span data-stu-id="c478b-120">uri</span></span>](uri-element-uri-settings.md)|<span data-ttu-id="c478b-121">.NET Framework が、uniform resource identifier (Uri) を使用して表された web アドレスを処理する方法を指定する設定が含まれます。</span><span class="sxs-lookup"><span data-stu-id="c478b-121">Contains settings that specify how the .NET Framework handles web addresses expressed using uniform resource identifiers (URIs).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c478b-122">Remarks</span><span class="sxs-lookup"><span data-stu-id="c478b-122">Remarks</span></span>  
 <span data-ttu-id="c478b-123">既存<xref:System.Uri>のクラスは .NET Framework 3.5 で拡張されています。</span><span class="sxs-lookup"><span data-stu-id="c478b-123">The existing <xref:System.Uri> class has been extended in .NET Framework 3.5.</span></span> <span data-ttu-id="c478b-124">3.0 SP1 および 2.0 SP1 (国際リソース識別子 (IRI) と国際化ドメイン名 (IDN) をサポート)。</span><span class="sxs-lookup"><span data-stu-id="c478b-124">3.0 SP1, and 2.0 SP1 with support for International Resource Identifiers (IRI) and Internationalized Domain Names (IDN).</span></span> <span data-ttu-id="c478b-125">現在のユーザーには、IRI と IDN のサポートを明示的に有効にしない限り、.NET Framework 2.0 の動作からの変更は表示されません。</span><span class="sxs-lookup"><span data-stu-id="c478b-125">Current users will not see any change from the .NET Framework 2.0 behavior unless they specifically enable IRI and IDN support.</span></span> <span data-ttu-id="c478b-126">これにより、.NET Framework の以前のバージョンとのアプリケーションの互換性を保証します。</span><span class="sxs-lookup"><span data-stu-id="c478b-126">This ensures application compatibility with prior versions of the .NET Framework.</span></span>  
  
 <span data-ttu-id="c478b-127">IRI のサポートを有効にするには、次の2つの変更が必要です。</span><span class="sxs-lookup"><span data-stu-id="c478b-127">To enable support for IRI, the following two changes are required:</span></span>  
  
1. <span data-ttu-id="c478b-128">Machine.config ファイルの .NET Framework 2.0 ディレクトリの下に次の行を追加します。</span><span class="sxs-lookup"><span data-stu-id="c478b-128">Add the following line to the machine.config file under the .NET Framework 2.0 directory</span></span>  
  
    ```xml  
    <section name="uri" type="System.Configuration.UriSection, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
    ```  
  
2. <span data-ttu-id="c478b-129">国際化ドメイン名 (IDN) の解析をドメイン名に適用するかどうか、および IRI 解析規則を適用するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="c478b-129">Specify whether you want Internationalized Domain Name (IDN) parsing applied to the domain name and whether IRI parsing rules should be applied.</span></span> <span data-ttu-id="c478b-130">これは、machine.config ファイルまたは app.config ファイルで指定できます。</span><span class="sxs-lookup"><span data-stu-id="c478b-130">This can be done in the machine.config or in the app.config file.</span></span>  
  
 <span data-ttu-id="c478b-131">IDN には、使用する DNS サーバーに応じて、次の3つの値を指定できます。</span><span class="sxs-lookup"><span data-stu-id="c478b-131">There are three possible values for IDN depending on the DNS servers that are used:</span></span>  
  
- <span data-ttu-id="c478b-132">idn enabled = すべて</span><span class="sxs-lookup"><span data-stu-id="c478b-132">idn enabled = All</span></span>  
  
     <span data-ttu-id="c478b-133">この値により、すべての Unicode ドメイン名が Punycode に相当する (IDN 名) に変換されます。</span><span class="sxs-lookup"><span data-stu-id="c478b-133">This value will convert any Unicode domain names to their Punycode equivalents (IDN names).</span></span>  
  
- <span data-ttu-id="c478b-134">idn enabled = AllExceptIntranet</span><span class="sxs-lookup"><span data-stu-id="c478b-134">idn enabled = AllExceptIntranet</span></span>  
  
     <span data-ttu-id="c478b-135">この値を指定すると、ローカルイントラネット上にないすべての Unicode ドメイン名が、Punycode に相当する (IDN 名) を使用するように変換されます。</span><span class="sxs-lookup"><span data-stu-id="c478b-135">This value will convert all Unicode domain names not on the local Intranet to use the Punycode equivalents (IDN names).</span></span> <span data-ttu-id="c478b-136">この場合は、イントラネットで使用される DNS サーバーが Unicode 名前解決をサポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c478b-136">In this case to handle international names on the local Intranet, the DNS servers that are used for the Intranet should support Unicode name resolution.</span></span>  
  
- <span data-ttu-id="c478b-137">idn enabled = なし</span><span class="sxs-lookup"><span data-stu-id="c478b-137">idn enabled = None</span></span>  
  
     <span data-ttu-id="c478b-138">この値では、Unicode ドメイン名を変換して Punycode を使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="c478b-138">This value will not convert any Unicode domain names to use Punycode.</span></span> <span data-ttu-id="c478b-139">これは、.NET Framework 2.0 の動作と一貫性のある既定値です。</span><span class="sxs-lookup"><span data-stu-id="c478b-139">This is the default value which is consistent with the .NET Framework 2.0 behaviour.</span></span>  
  
 <span data-ttu-id="c478b-140">IDN を有効にすると、ドメイン名に含まれるすべての Unicode のラベルが Punycode のラベルに変換されます。</span><span class="sxs-lookup"><span data-stu-id="c478b-140">Enabling IDN will convert all Unicode labels in a domain name to their Punycode equivalents.</span></span> <span data-ttu-id="c478b-141">Punycode 名には ASCII 文字のみが含まれ、常に xn-- プレフィックスで始まります。</span><span class="sxs-lookup"><span data-stu-id="c478b-141">Punycode names contain only ASCII characters and always start with the xn-- prefix.</span></span> <span data-ttu-id="c478b-142">この理由は、ほとんどの DNS サーバーは ASCII 文字しかサポートしていないため、インターネットで既存の DNS サーバーをサポートするためです (RFC 3940 を参照)。</span><span class="sxs-lookup"><span data-stu-id="c478b-142">The reason for this is to support existing DNS servers on the Internet, since most DNS servers only support ASCII characters (see RFC 3940).</span></span>  
  
### <a name="configuration-files"></a><span data-ttu-id="c478b-143">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="c478b-143">Configuration Files</span></span>  
 <span data-ttu-id="c478b-144">この要素は、アプリケーション構成ファイルまたはマシン構成ファイル (Machine.config) で使用できます。</span><span class="sxs-lookup"><span data-stu-id="c478b-144">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="c478b-145">例</span><span class="sxs-lookup"><span data-stu-id="c478b-145">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="c478b-146">説明</span><span class="sxs-lookup"><span data-stu-id="c478b-146">Description</span></span>  
 <span data-ttu-id="c478b-147">次の例は、IRI 解析と IDN <xref:System.Uri>名をサポートするためにクラスによって使用される構成を示しています。</span><span class="sxs-lookup"><span data-stu-id="c478b-147">The following example shows a configuration used by the <xref:System.Uri> class to support IRI parsing and IDN names.</span></span>  
  
### <a name="code"></a><span data-ttu-id="c478b-148">コード</span><span class="sxs-lookup"><span data-stu-id="c478b-148">Code</span></span>  
  
```xml  
<configuration>  
  <uri>  
    <idn enabled="All" />  
    <iriParsing enabled="true" />  
  </uri>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="c478b-149">関連項目</span><span class="sxs-lookup"><span data-stu-id="c478b-149">See also</span></span>

- <xref:System.Configuration.IdnElement?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection?displayProperty=nameWithType>
- [<span data-ttu-id="c478b-150">ネットワーク設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="c478b-150">Network Settings Schema</span></span>](index.md)
