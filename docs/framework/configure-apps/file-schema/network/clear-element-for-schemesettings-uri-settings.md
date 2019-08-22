---
title: schemeSettings の <clear> 要素 (Uri 設定)
ms.date: 03/30/2017
ms.assetid: 65098332-ce61-4542-ab8d-e7dc0257d31f
ms.openlocfilehash: 51c669aff767948523172aa075677ad3fb6478a2
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/21/2019
ms.locfileid: "69664175"
---
# <a name="clear-element-for-schemesettings-uri-settings"></a><span data-ttu-id="7d0b0-102">\<schemeSettings の > 要素のクリア (Uri 設定)</span><span class="sxs-lookup"><span data-stu-id="7d0b0-102">\<clear> Element for schemeSettings (Uri Settings)</span></span>
<span data-ttu-id="7d0b0-103">既存のスキーム設定をすべてクリアします。</span><span class="sxs-lookup"><span data-stu-id="7d0b0-103">Clears all existing scheme settings.</span></span>  
  
 <span data-ttu-id="7d0b0-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="7d0b0-104">\<configuration></span></span>  
<span data-ttu-id="7d0b0-105">\<uri></span><span class="sxs-lookup"><span data-stu-id="7d0b0-105">\<uri></span></span>  
<span data-ttu-id="7d0b0-106">\<schemeSettings></span><span class="sxs-lookup"><span data-stu-id="7d0b0-106">\<schemeSettings></span></span>  
<span data-ttu-id="7d0b0-107">\<clear></span><span class="sxs-lookup"><span data-stu-id="7d0b0-107">\<clear></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7d0b0-108">構文</span><span class="sxs-lookup"><span data-stu-id="7d0b0-108">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7d0b0-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="7d0b0-109">Attributes and Elements</span></span>  
 <span data-ttu-id="7d0b0-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="7d0b0-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7d0b0-111">属性</span><span class="sxs-lookup"><span data-stu-id="7d0b0-111">Attributes</span></span>  
 <span data-ttu-id="7d0b0-112">なし。</span><span class="sxs-lookup"><span data-stu-id="7d0b0-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="7d0b0-113">子要素</span><span class="sxs-lookup"><span data-stu-id="7d0b0-113">Child Elements</span></span>  
 <span data-ttu-id="7d0b0-114">なし。</span><span class="sxs-lookup"><span data-stu-id="7d0b0-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7d0b0-115">親要素</span><span class="sxs-lookup"><span data-stu-id="7d0b0-115">Parent Elements</span></span>  
  
|<span data-ttu-id="7d0b0-116">要素</span><span class="sxs-lookup"><span data-stu-id="7d0b0-116">Element</span></span>|<span data-ttu-id="7d0b0-117">説明</span><span class="sxs-lookup"><span data-stu-id="7d0b0-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7d0b0-118">\<schemeSettings> 要素 (Uri 設定)</span><span class="sxs-lookup"><span data-stu-id="7d0b0-118">\<schemeSettings> Element (Uri Settings)</span></span>](schemesettings-element-uri-settings.md)|<span data-ttu-id="7d0b0-119"><xref:System.Uri> が特定のスキームに解析される方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="7d0b0-119">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7d0b0-120">Remarks</span><span class="sxs-lookup"><span data-stu-id="7d0b0-120">Remarks</span></span>  
 <span data-ttu-id="7d0b0-121">既定では、 <xref:System.Uri?displayProperty=nameWithType>クラスは、パスの圧縮を実行する前に、エンコードされたパス区切り記号のエスケープを解除します。</span><span class="sxs-lookup"><span data-stu-id="7d0b0-121">By default, the <xref:System.Uri?displayProperty=nameWithType> class un-escapes percent encoded path delimiters before executing path compression.</span></span> <span data-ttu-id="7d0b0-122">これは、次のような攻撃に対するセキュリティメカニズムとして実装されています。</span><span class="sxs-lookup"><span data-stu-id="7d0b0-122">This was implemented as a security mechanism against attacks like the following:</span></span>  
  
 `http://www.contoso.com/..%2F..%2F/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="7d0b0-123">% Encoded 文字を正しく処理しないモジュールにこの URI が渡された場合、サーバーによって次のコマンドが実行される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="7d0b0-123">If this URI gets passed down to modules not handling percent encoded characters correctly, it could result in the following command being executed by the server:</span></span>  
  
 `c:\Windows\System32\cmd.exe /c dir c:\`  
  
 <span data-ttu-id="7d0b0-124">このため、クラス<xref:System.Uri?displayProperty=nameWithType>はまずパスの区切り記号をエスケープ解除し、次にパスの圧縮を適用します。</span><span class="sxs-lookup"><span data-stu-id="7d0b0-124">For this reason, <xref:System.Uri?displayProperty=nameWithType> class first un-escapes path delimiters and then applies path compression.</span></span> <span data-ttu-id="7d0b0-125">上の悪意のある URL をクラスコンストラクター <xref:System.Uri?displayProperty=nameWithType>に渡すと、次の URI が生成されます。</span><span class="sxs-lookup"><span data-stu-id="7d0b0-125">The result of passing the malicious URL above to <xref:System.Uri?displayProperty=nameWithType> class constructor results in the following URI:</span></span>  
  
 `http://www.microsoft.com/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="7d0b0-126">この既定の動作は、特定のスキームの schemeSettings 構成オプションを使用して、パーセントエンコードされたパス区切り記号のエスケープを解除しないように変更できます。</span><span class="sxs-lookup"><span data-stu-id="7d0b0-126">This default behavior can be modified to not un-escape percent encoded path delimiters using the schemeSettings configuration option for a specific scheme.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="7d0b0-127">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="7d0b0-127">Configuration Files</span></span>  
 <span data-ttu-id="7d0b0-128">この要素は、アプリケーション構成ファイルまたはマシン構成ファイル (Machine.config) で使用できます。</span><span class="sxs-lookup"><span data-stu-id="7d0b0-128">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="7d0b0-129">例</span><span class="sxs-lookup"><span data-stu-id="7d0b0-129">Example</span></span>  
 <span data-ttu-id="7d0b0-130">次の例は、すべてのスキーム設定<xref:System.Uri>をクリアするクラスによって使用される構成を示しています。その後、http スキームに対してパーセントでエンコードされたパス区切り記号をエスケープしないためのサポートを追加します。</span><span class="sxs-lookup"><span data-stu-id="7d0b0-130">The following example shows a configuration used by the <xref:System.Uri> class that clears all scheme settings and then adds support for not escaping percent-encoded path delimiters for the http scheme.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="7d0b0-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="7d0b0-131">See also</span></span>

- <xref:System.Configuration.SchemeSettingElement?displayProperty=nameWithType>
- <xref:System.Configuration.SchemeSettingElementCollection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection.SchemeSettings%2A?displayProperty=nameWithType>
- <xref:System.GenericUriParserOptions?displayProperty=nameWithType>
- <xref:System.Uri?displayProperty=nameWithType>
- [<span data-ttu-id="7d0b0-132">ネットワーク設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="7d0b0-132">Network Settings Schema</span></span>](index.md)
