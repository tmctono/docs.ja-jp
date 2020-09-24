---
title: schemeSettings の <add> 要素 (Uri 設定)
ms.date: 03/30/2017
ms.assetid: 594a7b3b-af23-4cfa-b616-0b2dddb1a705
ms.openlocfilehash: 55fcba41d4dabf8937ebaa11235e9309bcb57952
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91149462"
---
# <a name="add-element-for-schemesettings-uri-settings"></a><span data-ttu-id="3f47d-102">schemeSettings の \<add> 要素 (Uri 設定)</span><span class="sxs-lookup"><span data-stu-id="3f47d-102">\<add> Element for schemeSettings (Uri Settings)</span></span>

<span data-ttu-id="3f47d-103">スキーム名のスキーム設定を追加します。</span><span class="sxs-lookup"><span data-stu-id="3f47d-103">Adds a scheme setting for a scheme name.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<uri>**](uri-element-uri-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<schemeSettings>**](schemesettings-element-uri-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**

## <a name="syntax"></a><span data-ttu-id="3f47d-104">構文</span><span class="sxs-lookup"><span data-stu-id="3f47d-104">Syntax</span></span>  
  
```xml  
<add
  name="http|https"
  genericUriParserOptions="DontUnescapePathDotsAndSlashes"
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3f47d-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="3f47d-105">Attributes and Elements</span></span>  

 <span data-ttu-id="3f47d-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="3f47d-106">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3f47d-107">属性</span><span class="sxs-lookup"><span data-stu-id="3f47d-107">Attributes</span></span>  
  
|<span data-ttu-id="3f47d-108">属性</span><span class="sxs-lookup"><span data-stu-id="3f47d-108">Attribute</span></span>|<span data-ttu-id="3f47d-109">説明</span><span class="sxs-lookup"><span data-stu-id="3f47d-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3f47d-110">name</span><span class="sxs-lookup"><span data-stu-id="3f47d-110">name</span></span>|<span data-ttu-id="3f47d-111">この設定を適用するスキーム名。</span><span class="sxs-lookup"><span data-stu-id="3f47d-111">The scheme name for which this setting applies.</span></span> <span data-ttu-id="3f47d-112">サポートされている値は、name = "http" と name = "https" だけです。</span><span class="sxs-lookup"><span data-stu-id="3f47d-112">The only supported values are name="http" and name="https".</span></span>|  
  
## <a name="attribute-name-attribute"></a><span data-ttu-id="3f47d-113">{属性名}属性</span><span class="sxs-lookup"><span data-stu-id="3f47d-113">{Attribute name} Attribute</span></span>  
  
|<span data-ttu-id="3f47d-114">値</span><span class="sxs-lookup"><span data-stu-id="3f47d-114">Value</span></span>|<span data-ttu-id="3f47d-115">[説明]</span><span class="sxs-lookup"><span data-stu-id="3f47d-115">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="3f47d-116">genericUriParserOptions</span><span class="sxs-lookup"><span data-stu-id="3f47d-116">genericUriParserOptions</span></span>|<span data-ttu-id="3f47d-117">このスキームのパーサーオプション。</span><span class="sxs-lookup"><span data-stu-id="3f47d-117">The parser options for this scheme.</span></span> <span data-ttu-id="3f47d-118">サポートされている値は、genericUriParserOptions = "DontUnescapePathDotsAndSlashes" だけです。</span><span class="sxs-lookup"><span data-stu-id="3f47d-118">The only supported value is genericUriParserOptions= "DontUnescapePathDotsAndSlashes".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3f47d-119">子要素</span><span class="sxs-lookup"><span data-stu-id="3f47d-119">Child Elements</span></span>  

 <span data-ttu-id="3f47d-120">None</span><span class="sxs-lookup"><span data-stu-id="3f47d-120">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3f47d-121">親要素</span><span class="sxs-lookup"><span data-stu-id="3f47d-121">Parent Elements</span></span>  
  
|<span data-ttu-id="3f47d-122">要素</span><span class="sxs-lookup"><span data-stu-id="3f47d-122">Element</span></span>|<span data-ttu-id="3f47d-123">説明</span><span class="sxs-lookup"><span data-stu-id="3f47d-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3f47d-124">\<schemeSettings> 要素 (Uri 設定)</span><span class="sxs-lookup"><span data-stu-id="3f47d-124">\<schemeSettings> Element (Uri Settings)</span></span>](schemesettings-element-uri-settings.md)|<span data-ttu-id="3f47d-125"><xref:System.Uri> が特定のスキームに解析される方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="3f47d-125">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3f47d-126">解説</span><span class="sxs-lookup"><span data-stu-id="3f47d-126">Remarks</span></span>  

 <span data-ttu-id="3f47d-127">既定では、 <xref:System.Uri?displayProperty=nameWithType> クラスは、パスの圧縮を実行する前に、エンコードされたパス区切り記号のエスケープを解除します。</span><span class="sxs-lookup"><span data-stu-id="3f47d-127">By default, the <xref:System.Uri?displayProperty=nameWithType> class un-escapes percent encoded path delimiters before executing path compression.</span></span> <span data-ttu-id="3f47d-128">これは、次のような攻撃に対するセキュリティメカニズムとして実装されています。</span><span class="sxs-lookup"><span data-stu-id="3f47d-128">This was implemented as a security mechanism against attacks like the following:</span></span>  
  
 `http://www.contoso.com/..%2F..%2F/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="3f47d-129">% Encoded 文字を正しく処理しないモジュールにこの URI が渡された場合、サーバーによって次のコマンドが実行される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="3f47d-129">If this URI gets passed down to modules not handling percent encoded characters correctly, it could result in the following command being executed by the server:</span></span>  
  
 `c:\Windows\System32\cmd.exe /c dir c:\`  
  
 <span data-ttu-id="3f47d-130">このため、 <xref:System.Uri?displayProperty=nameWithType> クラスはまずパスの区切り記号をエスケープ解除し、次にパスの圧縮を適用します。</span><span class="sxs-lookup"><span data-stu-id="3f47d-130">For this reason, <xref:System.Uri?displayProperty=nameWithType> class first un-escapes path delimiters and then applies path compression.</span></span> <span data-ttu-id="3f47d-131">上の悪意のある URL をクラスコンストラクターに渡すと、次の URI が生成され <xref:System.Uri?displayProperty=nameWithType> ます。</span><span class="sxs-lookup"><span data-stu-id="3f47d-131">The result of passing the malicious URL above to <xref:System.Uri?displayProperty=nameWithType> class constructor results in the following URI:</span></span>  
  
 `http://www.microsoft.com/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="3f47d-132">この既定の動作は、特定のスキームの schemeSettings 構成オプションを使用して、パーセントエンコードされたパス区切り記号のエスケープを解除しないように変更できます。</span><span class="sxs-lookup"><span data-stu-id="3f47d-132">This default behavior can be modified to not un-escape percent encoded path delimiters using the schemeSettings configuration option for a specific scheme.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="3f47d-133">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="3f47d-133">Configuration Files</span></span>  

 <span data-ttu-id="3f47d-134">この要素は、アプリケーション構成ファイルまたはマシン構成ファイル (Machine.config) で使用できます。</span><span class="sxs-lookup"><span data-stu-id="3f47d-134">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="3f47d-135">例</span><span class="sxs-lookup"><span data-stu-id="3f47d-135">Example</span></span>  

 <span data-ttu-id="3f47d-136">次の例は、 <xref:System.Uri> http スキームに対してパーセントでエンコードされたパス区切り記号をエスケープしないようにするために、クラスによって使用される構成を示しています。</span><span class="sxs-lookup"><span data-stu-id="3f47d-136">The following example shows a configuration used by the <xref:System.Uri> class to support not escaping percent-encoded path delimiters for the http scheme.</span></span>  
  
```xml  
<configuration>  
  <uri>  
    <schemeSettings>  
      <add name="http" genericUriParserOptions="DontUnescapePathDotsAndSlashes"/>  
    </schemeSettings>  
  </uri>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="3f47d-137">関連項目</span><span class="sxs-lookup"><span data-stu-id="3f47d-137">See also</span></span>

- <xref:System.Configuration.SchemeSettingElement?displayProperty=nameWithType>
- <xref:System.Configuration.SchemeSettingElementCollection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection.SchemeSettings%2A?displayProperty=nameWithType>
- <xref:System.GenericUriParserOptions?displayProperty=nameWithType>
- <xref:System.Uri?displayProperty=nameWithType>
- [<span data-ttu-id="3f47d-138">ネットワーク設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="3f47d-138">Network Settings Schema</span></span>](index.md)
