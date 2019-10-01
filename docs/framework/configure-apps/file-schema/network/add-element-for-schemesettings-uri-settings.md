---
title: schemeSettings の <add> 要素 (Uri 設定)
ms.date: 03/30/2017
ms.assetid: 594a7b3b-af23-4cfa-b616-0b2dddb1a705
ms.openlocfilehash: efd52557ea8b617a39e685ff8ad69bab01322a7a
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2019
ms.locfileid: "71699591"
---
# <a name="add-element-for-schemesettings-uri-settings"></a><span data-ttu-id="9a4ae-102">schemeSettings の @no__t 0add > 要素 (Uri 設定)</span><span class="sxs-lookup"><span data-stu-id="9a4ae-102">\<add> Element for schemeSettings (Uri Settings)</span></span>
<span data-ttu-id="9a4ae-103">スキーム名のスキーム設定を追加します。</span><span class="sxs-lookup"><span data-stu-id="9a4ae-103">Adds a scheme setting for a scheme name.</span></span>  
  
[<span data-ttu-id="9a4ae-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="9a4ae-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="9a4ae-105">&nbsp; @ no__t-1[ **\< uri >** ](uri-element-uri-settings.md)</span><span class="sxs-lookup"><span data-stu-id="9a4ae-105">&nbsp;&nbsp;[**\<uri>**](uri-element-uri-settings.md)</span></span>  
<span data-ttu-id="9a4ae-106">&nbsp; @ no__t-1 @ no__t @ no__t-3[ **\<schemeSettings >** ](schemesettings-element-uri-settings.md)</span><span class="sxs-lookup"><span data-stu-id="9a4ae-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<schemeSettings>**](schemesettings-element-uri-settings.md)</span></span>  
<span data-ttu-id="9a4ae-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> の追加**</span><span class="sxs-lookup"><span data-stu-id="9a4ae-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9a4ae-108">構文</span><span class="sxs-lookup"><span data-stu-id="9a4ae-108">Syntax</span></span>  
  
```xml  
<add
  name="http|https"
  genericUriParserOptions="DontUnescapePathDotsAndSlashes"
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9a4ae-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="9a4ae-109">Attributes and Elements</span></span>  
 <span data-ttu-id="9a4ae-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="9a4ae-110">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9a4ae-111">属性</span><span class="sxs-lookup"><span data-stu-id="9a4ae-111">Attributes</span></span>  
  
|<span data-ttu-id="9a4ae-112">属性</span><span class="sxs-lookup"><span data-stu-id="9a4ae-112">Attribute</span></span>|<span data-ttu-id="9a4ae-113">説明</span><span class="sxs-lookup"><span data-stu-id="9a4ae-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9a4ae-114">NAME</span><span class="sxs-lookup"><span data-stu-id="9a4ae-114">name</span></span>|<span data-ttu-id="9a4ae-115">この設定を適用するスキーム名。</span><span class="sxs-lookup"><span data-stu-id="9a4ae-115">The scheme name for which this setting applies.</span></span> <span data-ttu-id="9a4ae-116">サポートされている値は、name = "http" と name = "https" だけです。</span><span class="sxs-lookup"><span data-stu-id="9a4ae-116">The only supported values are name="http" and name="https".</span></span>|  
  
## <a name="attribute-name-attribute"></a><span data-ttu-id="9a4ae-117">{属性名}属性</span><span class="sxs-lookup"><span data-stu-id="9a4ae-117">{Attribute name} Attribute</span></span>  
  
|<span data-ttu-id="9a4ae-118">値</span><span class="sxs-lookup"><span data-stu-id="9a4ae-118">Value</span></span>|<span data-ttu-id="9a4ae-119">説明</span><span class="sxs-lookup"><span data-stu-id="9a4ae-119">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="9a4ae-120">genericUriParserOptions</span><span class="sxs-lookup"><span data-stu-id="9a4ae-120">genericUriParserOptions</span></span>|<span data-ttu-id="9a4ae-121">このスキームのパーサーオプション。</span><span class="sxs-lookup"><span data-stu-id="9a4ae-121">The parser options for this scheme.</span></span> <span data-ttu-id="9a4ae-122">サポートされている値は、genericUriParserOptions = "DontUnescapePathDotsAndSlashes" だけです。</span><span class="sxs-lookup"><span data-stu-id="9a4ae-122">The only supported value is genericUriParserOptions= "DontUnescapePathDotsAndSlashes".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9a4ae-123">子要素</span><span class="sxs-lookup"><span data-stu-id="9a4ae-123">Child Elements</span></span>  
 <span data-ttu-id="9a4ae-124">なし</span><span class="sxs-lookup"><span data-stu-id="9a4ae-124">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9a4ae-125">親要素</span><span class="sxs-lookup"><span data-stu-id="9a4ae-125">Parent Elements</span></span>  
  
|<span data-ttu-id="9a4ae-126">要素</span><span class="sxs-lookup"><span data-stu-id="9a4ae-126">Element</span></span>|<span data-ttu-id="9a4ae-127">説明</span><span class="sxs-lookup"><span data-stu-id="9a4ae-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9a4ae-128">\<schemeSettings> 要素 (Uri 設定)</span><span class="sxs-lookup"><span data-stu-id="9a4ae-128">\<schemeSettings> Element (Uri Settings)</span></span>](schemesettings-element-uri-settings.md)|<span data-ttu-id="9a4ae-129"><xref:System.Uri> が特定のスキームに解析される方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="9a4ae-129">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9a4ae-130">コメント</span><span class="sxs-lookup"><span data-stu-id="9a4ae-130">Remarks</span></span>  
 <span data-ttu-id="9a4ae-131">既定では、<xref:System.Uri?displayProperty=nameWithType> クラスは、パスの圧縮を実行する前に、エンコードされたパス区切り記号のエスケープを解除します。</span><span class="sxs-lookup"><span data-stu-id="9a4ae-131">By default, the <xref:System.Uri?displayProperty=nameWithType> class un-escapes percent encoded path delimiters before executing path compression.</span></span> <span data-ttu-id="9a4ae-132">これは、次のような攻撃に対するセキュリティメカニズムとして実装されています。</span><span class="sxs-lookup"><span data-stu-id="9a4ae-132">This was implemented as a security mechanism against attacks like the following:</span></span>  
  
 `http://www.contoso.com/..%2F..%2F/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="9a4ae-133">% Encoded 文字を正しく処理しないモジュールにこの URI が渡された場合、サーバーによって次のコマンドが実行される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="9a4ae-133">If this URI gets passed down to modules not handling percent encoded characters correctly, it could result in the following command being executed by the server:</span></span>  
  
 `c:\Windows\System32\cmd.exe /c dir c:\`  
  
 <span data-ttu-id="9a4ae-134">このため、<xref:System.Uri?displayProperty=nameWithType> クラスはまずパスの区切り記号をエスケープ解除し、次にパスの圧縮を適用します。</span><span class="sxs-lookup"><span data-stu-id="9a4ae-134">For this reason, <xref:System.Uri?displayProperty=nameWithType> class first un-escapes path delimiters and then applies path compression.</span></span> <span data-ttu-id="9a4ae-135">上記の悪意のある URL を <xref:System.Uri?displayProperty=nameWithType> クラスコンストラクターに渡すと、次の URI になります。</span><span class="sxs-lookup"><span data-stu-id="9a4ae-135">The result of passing the malicious URL above to <xref:System.Uri?displayProperty=nameWithType> class constructor results in the following URI:</span></span>  
  
 `http://www.microsoft.com/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="9a4ae-136">この既定の動作は、特定のスキームの schemeSettings 構成オプションを使用して、パーセントエンコードされたパス区切り記号のエスケープを解除しないように変更できます。</span><span class="sxs-lookup"><span data-stu-id="9a4ae-136">This default behavior can be modified to not un-escape percent encoded path delimiters using the schemeSettings configuration option for a specific scheme.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="9a4ae-137">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="9a4ae-137">Configuration Files</span></span>  
 <span data-ttu-id="9a4ae-138">この要素は、アプリケーション構成ファイルまたはマシン構成ファイル (Machine.config) で使用できます。</span><span class="sxs-lookup"><span data-stu-id="9a4ae-138">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="9a4ae-139">例</span><span class="sxs-lookup"><span data-stu-id="9a4ae-139">Example</span></span>  
 <span data-ttu-id="9a4ae-140">次の例は、http スキームでパーセントでエンコードされたパス区切り記号をエスケープしないようにするために <xref:System.Uri> クラスによって使用される構成を示しています。</span><span class="sxs-lookup"><span data-stu-id="9a4ae-140">The following example shows a configuration used by the <xref:System.Uri> class to support not escaping percent-encoded path delimiters for the http scheme.</span></span>  
  
```xml  
<configuration>  
  <uri>  
    <schemeSettings>  
      <add name="http" genericUriParserOptions="DontUnescapePathDotsAndSlashes"/>  
    </schemeSettings>  
  </uri>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="9a4ae-141">関連項目</span><span class="sxs-lookup"><span data-stu-id="9a4ae-141">See also</span></span>

- <xref:System.Configuration.SchemeSettingElement?displayProperty=nameWithType>
- <xref:System.Configuration.SchemeSettingElementCollection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection.SchemeSettings%2A?displayProperty=nameWithType>
- <xref:System.GenericUriParserOptions?displayProperty=nameWithType>
- <xref:System.Uri?displayProperty=nameWithType>
- [<span data-ttu-id="9a4ae-142">ネットワーク設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="9a4ae-142">Network Settings Schema</span></span>](index.md)
