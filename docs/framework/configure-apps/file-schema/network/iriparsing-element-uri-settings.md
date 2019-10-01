---
title: <iriParsing> 要素 (Uri 設定)
ms.date: 03/30/2017
ms.assetid: 953d0b53-445e-41f9-b302-77c4030852ce
ms.openlocfilehash: fd617d1b4ac8e532c6f9aeaa01465e9866b059e9
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2019
ms.locfileid: "71698089"
---
# <a name="iriparsing-element-uri-settings"></a><span data-ttu-id="36590-102">@no__t 0iriParsing > 要素 (Uri 設定)</span><span class="sxs-lookup"><span data-stu-id="36590-102">\<iriParsing> Element (Uri Settings)</span></span>
<span data-ttu-id="36590-103">International Resource Identifier (IRI) 解析が、<xref:System.Uri> に適用されるかどうか、および IRI の解析規則が適用されるどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="36590-103">Specifies if International Resource Identifier (IRI) parsing is applied to a <xref:System.Uri> and whether IRI parsing rules should be applied.</span></span>  
  
[<span data-ttu-id="36590-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="36590-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="36590-105">&nbsp; @ no__t-1[ **\< uri >** ](uri-element-uri-settings.md)</span><span class="sxs-lookup"><span data-stu-id="36590-105">&nbsp;&nbsp;[**\<uri>**](uri-element-uri-settings.md)</span></span>  
<span data-ttu-id="36590-106">&nbsp; @ no__t @ no__t-2 @ no__t-3 **\<iriParsing >**</span><span class="sxs-lookup"><span data-stu-id="36590-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<iriParsing>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="36590-107">構文</span><span class="sxs-lookup"><span data-stu-id="36590-107">Syntax</span></span>  
  
```xml  
<iriParsing  
  enabled="true|false"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="36590-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="36590-108">Attributes and Elements</span></span>  
 <span data-ttu-id="36590-109">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="36590-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="36590-110">属性</span><span class="sxs-lookup"><span data-stu-id="36590-110">Attributes</span></span>  
  
|<span data-ttu-id="36590-111">**要素**</span><span class="sxs-lookup"><span data-stu-id="36590-111">**Element**</span></span>|<span data-ttu-id="36590-112">**[説明]**</span><span class="sxs-lookup"><span data-stu-id="36590-112">**Description**</span></span>|  
|-----------------|---------------------|  
|`enabled`|<span data-ttu-id="36590-113">IRI 解析を有効にするかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="36590-113">Specifies whether IRI parsing is enabled.</span></span> <span data-ttu-id="36590-114">既定値は `false` です。</span><span class="sxs-lookup"><span data-stu-id="36590-114">The default value is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="36590-115">子要素</span><span class="sxs-lookup"><span data-stu-id="36590-115">Child Elements</span></span>  
 <span data-ttu-id="36590-116">なし</span><span class="sxs-lookup"><span data-stu-id="36590-116">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="36590-117">親要素</span><span class="sxs-lookup"><span data-stu-id="36590-117">Parent Elements</span></span>  
  
|<span data-ttu-id="36590-118">**要素**</span><span class="sxs-lookup"><span data-stu-id="36590-118">**Element**</span></span>|<span data-ttu-id="36590-119">**[説明]**</span><span class="sxs-lookup"><span data-stu-id="36590-119">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="36590-120">uri</span><span class="sxs-lookup"><span data-stu-id="36590-120">uri</span></span>](uri-element-uri-settings.md)|<span data-ttu-id="36590-121">.NET Framework が、uniform resource identifier (Uri) を使用して表された web アドレスを処理する方法を指定する設定が含まれます。</span><span class="sxs-lookup"><span data-stu-id="36590-121">Contains settings that specify how the .NET Framework handles web addresses expressed using uniform resource identifiers (URIs).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="36590-122">コメント</span><span class="sxs-lookup"><span data-stu-id="36590-122">Remarks</span></span>  
 <span data-ttu-id="36590-123">既存の <xref:System.Uri> クラスは .NET Framework 3.5 で拡張されています。</span><span class="sxs-lookup"><span data-stu-id="36590-123">The existing <xref:System.Uri> class has been extended in .NET Framework 3.5.</span></span> <span data-ttu-id="36590-124">3.0 SP1 および 2.0 SP1 では、International Resource Identifier (IRI) と国際化ドメイン名 (IDN) のサポートが提供されます。</span><span class="sxs-lookup"><span data-stu-id="36590-124">3.0 SP1, and 2.0 SP1 to provide support for International Resource Identifiers (IRI) and Internationalized Domain Names (IDN).</span></span> <span data-ttu-id="36590-125">現在のユーザーには、IRI と IDN のサポートを明示的に有効にしない限り、.NET Framework 2.0 の動作からの変更は表示されません。</span><span class="sxs-lookup"><span data-stu-id="36590-125">Current users will not see any change from the .NET Framework 2.0 behavior unless they specifically enable IRI and IDN support.</span></span> <span data-ttu-id="36590-126">これにより、.NET Framework の以前のバージョンとのアプリケーションの互換性を保証します。</span><span class="sxs-lookup"><span data-stu-id="36590-126">This ensures application compatibility with prior versions of the .NET Framework.</span></span>  
  
 <span data-ttu-id="36590-127">IRI のサポートを有効にするには、次の2つの変更が必要です。</span><span class="sxs-lookup"><span data-stu-id="36590-127">To enable support for IRI, the following two changes are required:</span></span>  
  
1. <span data-ttu-id="36590-128">Machine.config ファイルの .NET Framework 2.0 ディレクトリの下に次の行を追加します。</span><span class="sxs-lookup"><span data-stu-id="36590-128">Add the following line to the machine.config file under the .NET Framework 2.0 directory</span></span>  
  
    ```xml  
    <section name="uri" type="System.Configuration.UriSection, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
    ```  
  
2. <span data-ttu-id="36590-129">IRI 解析規則を適用するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="36590-129">Specify whether IRI parsing rules should be applied.</span></span> <span data-ttu-id="36590-130">これは、machine.config ファイルまたは app.config ファイルで指定できます。</span><span class="sxs-lookup"><span data-stu-id="36590-130">This can be done in the machine.config or in the app.config file.</span></span>  
  
 <span data-ttu-id="36590-131">Iri 解析を有効にすると (iriparsing 有効 = `true`)、RFC 3987 の最新の IRI 規則に従って、正規化と文字チェックが実行されます。</span><span class="sxs-lookup"><span data-stu-id="36590-131">Enabling IRI parsing (iriParsing enabled = `true`) will do normalization and character checking according to the latest IRI rules in RFC 3987.</span></span> <span data-ttu-id="36590-132">既定値は 0 @no__t であり、RFC 2396 および RFC 3986 (IPv6 リテラルの場合) に従って、正規化と文字チェックが実行されます。</span><span class="sxs-lookup"><span data-stu-id="36590-132">The default value is `false` and will do normalization and character checking according to RFC 2396 and RFC 3986 (for IPv6 literals).</span></span>  
  
### <a name="configuration-files"></a><span data-ttu-id="36590-133">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="36590-133">Configuration Files</span></span>  
 <span data-ttu-id="36590-134">この要素は、アプリケーション構成ファイルまたはマシン構成ファイル (Machine.config) で使用できます。</span><span class="sxs-lookup"><span data-stu-id="36590-134">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="36590-135">例</span><span class="sxs-lookup"><span data-stu-id="36590-135">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="36590-136">説明</span><span class="sxs-lookup"><span data-stu-id="36590-136">Description</span></span>  
 <span data-ttu-id="36590-137">次の例は、IRI 解析と IDN 名をサポートするために <xref:System.Uri> クラスによって使用される構成を示しています。</span><span class="sxs-lookup"><span data-stu-id="36590-137">The following example shows a configuration used by the <xref:System.Uri> class to support IRI parsing and IDN names.</span></span>  
  
### <a name="code"></a><span data-ttu-id="36590-138">コード</span><span class="sxs-lookup"><span data-stu-id="36590-138">Code</span></span>  
  
```xml  
<configuration>  
  <uri>  
    <idn enabled="All" />  
    <iriParsing enabled="true" />  
  </uri>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="36590-139">関連項目</span><span class="sxs-lookup"><span data-stu-id="36590-139">See also</span></span>

- <xref:System.Configuration.IriParsingElement?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection?displayProperty=nameWithType>
- [<span data-ttu-id="36590-140">ネットワーク設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="36590-140">Network Settings Schema</span></span>](index.md)
