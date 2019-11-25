---
title: schemeSettings の <add> 要素 (Uri 設定)
ms.date: 03/30/2017
ms.assetid: 594a7b3b-af23-4cfa-b616-0b2dddb1a705
ms.openlocfilehash: ed40098e8d4c2d1298771e67a618b8d04f59c912
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/14/2019
ms.locfileid: "74087714"
---
# <a name="add-element-for-schemesettings-uri-settings"></a><span data-ttu-id="f4f86-102">schemeSettings の > 要素を追加 \<(Uri 設定)</span><span class="sxs-lookup"><span data-stu-id="f4f86-102">\<add> Element for schemeSettings (Uri Settings)</span></span>
<span data-ttu-id="f4f86-103">スキーム名のスキーム設定を追加します。</span><span class="sxs-lookup"><span data-stu-id="f4f86-103">Adds a scheme setting for a scheme name.</span></span>  

<span data-ttu-id="f4f86-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="f4f86-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="f4f86-105">&nbsp;&nbsp;[ **\<uri >** ](uri-element-uri-settings.md)</span><span class="sxs-lookup"><span data-stu-id="f4f86-105">&nbsp;&nbsp;[**\<uri>**](uri-element-uri-settings.md)</span></span>\
<span data-ttu-id="f4f86-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<schemeSettings >** ](schemesettings-element-uri-settings.md)</span><span class="sxs-lookup"><span data-stu-id="f4f86-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<schemeSettings>**](schemesettings-element-uri-settings.md)</span></span>\
<span data-ttu-id="f4f86-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**追加 >**</span><span class="sxs-lookup"><span data-stu-id="f4f86-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>

## <a name="syntax"></a><span data-ttu-id="f4f86-108">構文</span><span class="sxs-lookup"><span data-stu-id="f4f86-108">Syntax</span></span>  
  
```xml  
<add
  name="http|https"
  genericUriParserOptions="DontUnescapePathDotsAndSlashes"
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f4f86-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="f4f86-109">Attributes and Elements</span></span>  
 <span data-ttu-id="f4f86-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="f4f86-110">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f4f86-111">属性</span><span class="sxs-lookup"><span data-stu-id="f4f86-111">Attributes</span></span>  
  
|<span data-ttu-id="f4f86-112">属性</span><span class="sxs-lookup"><span data-stu-id="f4f86-112">Attribute</span></span>|<span data-ttu-id="f4f86-113">説明</span><span class="sxs-lookup"><span data-stu-id="f4f86-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f4f86-114">name</span><span class="sxs-lookup"><span data-stu-id="f4f86-114">name</span></span>|<span data-ttu-id="f4f86-115">この設定を適用するスキーム名。</span><span class="sxs-lookup"><span data-stu-id="f4f86-115">The scheme name for which this setting applies.</span></span> <span data-ttu-id="f4f86-116">サポートされている値は、name = "http" と name = "https" だけです。</span><span class="sxs-lookup"><span data-stu-id="f4f86-116">The only supported values are name="http" and name="https".</span></span>|  
  
## <a name="attribute-name-attribute"></a><span data-ttu-id="f4f86-117">{属性名}属性</span><span class="sxs-lookup"><span data-stu-id="f4f86-117">{Attribute name} Attribute</span></span>  
  
|<span data-ttu-id="f4f86-118">[値]</span><span class="sxs-lookup"><span data-stu-id="f4f86-118">Value</span></span>|<span data-ttu-id="f4f86-119">説明</span><span class="sxs-lookup"><span data-stu-id="f4f86-119">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="f4f86-120">genericUriParserOptions</span><span class="sxs-lookup"><span data-stu-id="f4f86-120">genericUriParserOptions</span></span>|<span data-ttu-id="f4f86-121">このスキームのパーサーオプション。</span><span class="sxs-lookup"><span data-stu-id="f4f86-121">The parser options for this scheme.</span></span> <span data-ttu-id="f4f86-122">サポートされている値は、genericUriParserOptions = "DontUnescapePathDotsAndSlashes" だけです。</span><span class="sxs-lookup"><span data-stu-id="f4f86-122">The only supported value is genericUriParserOptions= "DontUnescapePathDotsAndSlashes".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f4f86-123">子要素</span><span class="sxs-lookup"><span data-stu-id="f4f86-123">Child Elements</span></span>  
 <span data-ttu-id="f4f86-124">None</span><span class="sxs-lookup"><span data-stu-id="f4f86-124">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f4f86-125">親要素</span><span class="sxs-lookup"><span data-stu-id="f4f86-125">Parent Elements</span></span>  
  
|<span data-ttu-id="f4f86-126">要素</span><span class="sxs-lookup"><span data-stu-id="f4f86-126">Element</span></span>|<span data-ttu-id="f4f86-127">説明</span><span class="sxs-lookup"><span data-stu-id="f4f86-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f4f86-128">\<schemeSettings> 要素 (Uri 設定)</span><span class="sxs-lookup"><span data-stu-id="f4f86-128">\<schemeSettings> Element (Uri Settings)</span></span>](schemesettings-element-uri-settings.md)|<span data-ttu-id="f4f86-129"><xref:System.Uri> が特定のスキームに解析される方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="f4f86-129">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f4f86-130">Remarks</span><span class="sxs-lookup"><span data-stu-id="f4f86-130">Remarks</span></span>  
 <span data-ttu-id="f4f86-131">既定では、<xref:System.Uri?displayProperty=nameWithType> クラスは、パスの圧縮を実行する前に、エンコードされたパス区切り記号のエスケープを解除します。</span><span class="sxs-lookup"><span data-stu-id="f4f86-131">By default, the <xref:System.Uri?displayProperty=nameWithType> class un-escapes percent encoded path delimiters before executing path compression.</span></span> <span data-ttu-id="f4f86-132">これは、次のような攻撃に対するセキュリティメカニズムとして実装されています。</span><span class="sxs-lookup"><span data-stu-id="f4f86-132">This was implemented as a security mechanism against attacks like the following:</span></span>  
  
 `http://www.contoso.com/..%2F..%2F/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="f4f86-133">% Encoded 文字を正しく処理しないモジュールにこの URI が渡された場合、サーバーによって次のコマンドが実行される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f4f86-133">If this URI gets passed down to modules not handling percent encoded characters correctly, it could result in the following command being executed by the server:</span></span>  
  
 `c:\Windows\System32\cmd.exe /c dir c:\`  
  
 <span data-ttu-id="f4f86-134">このため、<xref:System.Uri?displayProperty=nameWithType> クラスはまずパスの区切り記号をエスケープ解除し、次にパスの圧縮を適用します。</span><span class="sxs-lookup"><span data-stu-id="f4f86-134">For this reason, <xref:System.Uri?displayProperty=nameWithType> class first un-escapes path delimiters and then applies path compression.</span></span> <span data-ttu-id="f4f86-135">上の悪意のある URL を <xref:System.Uri?displayProperty=nameWithType> クラスコンストラクターに渡すと、次の URI になります。</span><span class="sxs-lookup"><span data-stu-id="f4f86-135">The result of passing the malicious URL above to <xref:System.Uri?displayProperty=nameWithType> class constructor results in the following URI:</span></span>  
  
 `http://www.microsoft.com/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="f4f86-136">この既定の動作は、特定のスキームの schemeSettings 構成オプションを使用して、パーセントエンコードされたパス区切り記号のエスケープを解除しないように変更できます。</span><span class="sxs-lookup"><span data-stu-id="f4f86-136">This default behavior can be modified to not un-escape percent encoded path delimiters using the schemeSettings configuration option for a specific scheme.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="f4f86-137">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="f4f86-137">Configuration Files</span></span>  
 <span data-ttu-id="f4f86-138">この要素は、アプリケーション構成ファイルまたはマシン構成ファイル (Machine.config) で使用できます。</span><span class="sxs-lookup"><span data-stu-id="f4f86-138">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f4f86-139">例</span><span class="sxs-lookup"><span data-stu-id="f4f86-139">Example</span></span>  
 <span data-ttu-id="f4f86-140">次の例は、http スキームに対してパーセントでエンコードされたパス区切り記号をエスケープしないようにするために <xref:System.Uri> クラスによって使用される構成を示しています。</span><span class="sxs-lookup"><span data-stu-id="f4f86-140">The following example shows a configuration used by the <xref:System.Uri> class to support not escaping percent-encoded path delimiters for the http scheme.</span></span>  
  
```xml  
<configuration>  
  <uri>  
    <schemeSettings>  
      <add name="http" genericUriParserOptions="DontUnescapePathDotsAndSlashes"/>  
    </schemeSettings>  
  </uri>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="f4f86-141">関連項目</span><span class="sxs-lookup"><span data-stu-id="f4f86-141">See also</span></span>

- <xref:System.Configuration.SchemeSettingElement?displayProperty=nameWithType>
- <xref:System.Configuration.SchemeSettingElementCollection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection.SchemeSettings%2A?displayProperty=nameWithType>
- <xref:System.GenericUriParserOptions?displayProperty=nameWithType>
- <xref:System.Uri?displayProperty=nameWithType>
- [<span data-ttu-id="f4f86-142">ネットワーク設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="f4f86-142">Network Settings Schema</span></span>](index.md)
