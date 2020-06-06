---
title: schemeSettings の <clear> 要素 (Uri 設定)
ms.date: 03/30/2017
ms.assetid: 65098332-ce61-4542-ab8d-e7dc0257d31f
ms.openlocfilehash: 90035c1c9ccdb8ac888aec84e506ccde41748c9f
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "74087440"
---
# <a name="clear-element-for-schemesettings-uri-settings"></a><span data-ttu-id="a99fa-102">schemeSettings の \<clear> 要素 (Uri 設定)</span><span class="sxs-lookup"><span data-stu-id="a99fa-102">\<clear> Element for schemeSettings (Uri Settings)</span></span>
<span data-ttu-id="a99fa-103">既存のスキーム設定をすべてクリアします。</span><span class="sxs-lookup"><span data-stu-id="a99fa-103">Clears all existing scheme settings.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<uri>**](uri-element-uri-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<schemeSettings>**](schemesettings-element-uri-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**

## <a name="syntax"></a><span data-ttu-id="a99fa-104">構文</span><span class="sxs-lookup"><span data-stu-id="a99fa-104">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a99fa-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="a99fa-105">Attributes and Elements</span></span>  
 <span data-ttu-id="a99fa-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="a99fa-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a99fa-107">属性</span><span class="sxs-lookup"><span data-stu-id="a99fa-107">Attributes</span></span>  
 <span data-ttu-id="a99fa-108">なし。</span><span class="sxs-lookup"><span data-stu-id="a99fa-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="a99fa-109">子要素</span><span class="sxs-lookup"><span data-stu-id="a99fa-109">Child Elements</span></span>  
 <span data-ttu-id="a99fa-110">[なし] :</span><span class="sxs-lookup"><span data-stu-id="a99fa-110">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a99fa-111">親要素</span><span class="sxs-lookup"><span data-stu-id="a99fa-111">Parent Elements</span></span>  
  
|<span data-ttu-id="a99fa-112">要素</span><span class="sxs-lookup"><span data-stu-id="a99fa-112">Element</span></span>|<span data-ttu-id="a99fa-113">説明</span><span class="sxs-lookup"><span data-stu-id="a99fa-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a99fa-114">\<schemeSettings>要素 (Uri 設定)</span><span class="sxs-lookup"><span data-stu-id="a99fa-114">\<schemeSettings> Element (Uri Settings)</span></span>](schemesettings-element-uri-settings.md)|<span data-ttu-id="a99fa-115"><xref:System.Uri> が特定のスキームに解析される方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="a99fa-115">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a99fa-116">解説</span><span class="sxs-lookup"><span data-stu-id="a99fa-116">Remarks</span></span>  
 <span data-ttu-id="a99fa-117">既定では、 <xref:System.Uri?displayProperty=nameWithType> クラスは、パスの圧縮を実行する前に、エンコードされたパス区切り記号のエスケープを解除します。</span><span class="sxs-lookup"><span data-stu-id="a99fa-117">By default, the <xref:System.Uri?displayProperty=nameWithType> class un-escapes percent encoded path delimiters before executing path compression.</span></span> <span data-ttu-id="a99fa-118">これは、次のような攻撃に対するセキュリティメカニズムとして実装されています。</span><span class="sxs-lookup"><span data-stu-id="a99fa-118">This was implemented as a security mechanism against attacks like the following:</span></span>  
  
 `http://www.contoso.com/..%2F..%2F/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="a99fa-119">% Encoded 文字を正しく処理しないモジュールにこの URI が渡された場合、サーバーによって次のコマンドが実行される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a99fa-119">If this URI gets passed down to modules not handling percent encoded characters correctly, it could result in the following command being executed by the server:</span></span>  
  
 `c:\Windows\System32\cmd.exe /c dir c:\`  
  
 <span data-ttu-id="a99fa-120">このため、 <xref:System.Uri?displayProperty=nameWithType> クラスはまずパスの区切り記号をエスケープ解除し、次にパスの圧縮を適用します。</span><span class="sxs-lookup"><span data-stu-id="a99fa-120">For this reason, <xref:System.Uri?displayProperty=nameWithType> class first un-escapes path delimiters and then applies path compression.</span></span> <span data-ttu-id="a99fa-121">上の悪意のある URL をクラスコンストラクターに渡すと、次の URI が生成され <xref:System.Uri?displayProperty=nameWithType> ます。</span><span class="sxs-lookup"><span data-stu-id="a99fa-121">The result of passing the malicious URL above to <xref:System.Uri?displayProperty=nameWithType> class constructor results in the following URI:</span></span>  
  
 `http://www.microsoft.com/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="a99fa-122">この既定の動作は、特定のスキームの schemeSettings 構成オプションを使用して、パーセントエンコードされたパス区切り記号のエスケープを解除しないように変更できます。</span><span class="sxs-lookup"><span data-stu-id="a99fa-122">This default behavior can be modified to not un-escape percent encoded path delimiters using the schemeSettings configuration option for a specific scheme.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="a99fa-123">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="a99fa-123">Configuration Files</span></span>  
 <span data-ttu-id="a99fa-124">この要素は、アプリケーション構成ファイルまたはマシン構成ファイル (Machine.config) で使用できます。</span><span class="sxs-lookup"><span data-stu-id="a99fa-124">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a99fa-125">例</span><span class="sxs-lookup"><span data-stu-id="a99fa-125">Example</span></span>  
 <span data-ttu-id="a99fa-126">次の例は、すべてのスキーム設定をクリアするクラスによって使用される構成を示して <xref:System.Uri> います。その後、http スキームに対してパーセントでエンコードされたパス区切り記号をエスケープしないためのサポートを追加します。</span><span class="sxs-lookup"><span data-stu-id="a99fa-126">The following example shows a configuration used by the <xref:System.Uri> class that clears all scheme settings and then adds support for not escaping percent-encoded path delimiters for the http scheme.</span></span>  
  
```xml  
<configuration>  
  <uri>  
    <schemeSettings>  
      <clear/>  
      <add name="http" genericUriParserOptions="DontUnescapePathDotsAndSlashes"/>  
    </schemeSettings>  
  </uri>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="a99fa-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="a99fa-127">See also</span></span>

- <xref:System.Configuration.SchemeSettingElement?displayProperty=nameWithType>
- <xref:System.Configuration.SchemeSettingElementCollection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection.SchemeSettings%2A?displayProperty=nameWithType>
- <xref:System.GenericUriParserOptions?displayProperty=nameWithType>
- <xref:System.Uri?displayProperty=nameWithType>
- [<span data-ttu-id="a99fa-128">ネットワーク設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="a99fa-128">Network Settings Schema</span></span>](index.md)
