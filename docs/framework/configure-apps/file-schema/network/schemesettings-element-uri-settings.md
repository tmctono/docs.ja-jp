---
title: <schemeSettings> 要素 (Uri 設定)
ms.date: 03/30/2017
ms.assetid: 0ae45c6e-8c4c-4c0d-8b9f-a93824648890
ms.openlocfilehash: c745c90bb61b9ee393687d7f6db4fd11565c7dc7
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "79154648"
---
# <a name="schemesettings-element-uri-settings"></a><span data-ttu-id="12384-102">\<schemeSettings> 要素 (Uri 設定)</span><span class="sxs-lookup"><span data-stu-id="12384-102">\<schemeSettings> Element (Uri Settings)</span></span>
<span data-ttu-id="12384-103"><xref:System.Uri> が特定のスキームに解析される方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="12384-103">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>  
  
[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;[**\<uri>**](uri-element-uri-settings.md)  
&nbsp;&nbsp;&nbsp;&nbsp;**\<schemeSettings>**  
  
## <a name="syntax"></a><span data-ttu-id="12384-104">構文</span><span class="sxs-lookup"><span data-stu-id="12384-104">Syntax</span></span>  
  
```xml  
<schemeSettings>
</schemeSettings>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="12384-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="12384-105">Attributes and Elements</span></span>  
 <span data-ttu-id="12384-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="12384-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="12384-107">属性</span><span class="sxs-lookup"><span data-stu-id="12384-107">Attributes</span></span>  
 <span data-ttu-id="12384-108">なし</span><span class="sxs-lookup"><span data-stu-id="12384-108">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="12384-109">子要素</span><span class="sxs-lookup"><span data-stu-id="12384-109">Child Elements</span></span>  
  
|<span data-ttu-id="12384-110">**要素**</span><span class="sxs-lookup"><span data-stu-id="12384-110">**Element**</span></span>|<span data-ttu-id="12384-111">**説明**</span><span class="sxs-lookup"><span data-stu-id="12384-111">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="12384-112">add</span><span class="sxs-lookup"><span data-stu-id="12384-112">add</span></span>](add-element-for-schemesettings-uri-settings.md)|<span data-ttu-id="12384-113">スキーム名のスキーム設定を追加します。</span><span class="sxs-lookup"><span data-stu-id="12384-113">Adds a scheme setting for a scheme name.</span></span>|  
|[<span data-ttu-id="12384-114">オフ</span><span class="sxs-lookup"><span data-stu-id="12384-114">clear</span></span>](clear-element-for-schemesettings-uri-settings.md)|<span data-ttu-id="12384-115">既存のスキーム設定をすべてクリアします。</span><span class="sxs-lookup"><span data-stu-id="12384-115">Clears all existing scheme settings.</span></span>|  
|[<span data-ttu-id="12384-116">remove</span><span class="sxs-lookup"><span data-stu-id="12384-116">remove</span></span>](remove-element-for-schemesettings-uri-settings.md)|<span data-ttu-id="12384-117">スキーム名のスキーム設定を削除します。</span><span class="sxs-lookup"><span data-stu-id="12384-117">Removes a scheme setting for a scheme name.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="12384-118">親要素</span><span class="sxs-lookup"><span data-stu-id="12384-118">Parent Elements</span></span>  
  
|<span data-ttu-id="12384-119">**要素**</span><span class="sxs-lookup"><span data-stu-id="12384-119">**Element**</span></span>|<span data-ttu-id="12384-120">**説明**</span><span class="sxs-lookup"><span data-stu-id="12384-120">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="12384-121">uri</span><span class="sxs-lookup"><span data-stu-id="12384-121">uri</span></span>](uri-element-uri-settings.md)|<span data-ttu-id="12384-122">.NET Framework が、uniform resource identifier (Uri) を使用して表された web アドレスを処理する方法を指定する設定が含まれます。</span><span class="sxs-lookup"><span data-stu-id="12384-122">Contains settings that specify how the .NET Framework handles web addresses expressed using uniform resource identifiers (URIs).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="12384-123">解説</span><span class="sxs-lookup"><span data-stu-id="12384-123">Remarks</span></span>  
 <span data-ttu-id="12384-124">既定では、 <xref:System.Uri?displayProperty=nameWithType> クラスは、パスの圧縮を実行する前に、エンコードされたパス区切り記号のエスケープを解除します。</span><span class="sxs-lookup"><span data-stu-id="12384-124">By default, the <xref:System.Uri?displayProperty=nameWithType> class un-escapes percent encoded path delimiters before executing path compression.</span></span> <span data-ttu-id="12384-125">これは、次のような攻撃に対するセキュリティメカニズムとして実装されています。</span><span class="sxs-lookup"><span data-stu-id="12384-125">This was implemented as a security mechanism against attacks like the following:</span></span>  
  
 `http://www.contoso.com/..%2F..%2F/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="12384-126">% Encoded 文字を正しく処理しないモジュールにこの URI が渡された場合、サーバーによって次のコマンドが実行される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="12384-126">If this URI gets passed down to modules not handling percent encoded characters correctly, it could result in the following command being executed by the server:</span></span>  
  
 `c:\Windows\System32\cmd.exe /c dir c:\`  
  
 <span data-ttu-id="12384-127">このため、 <xref:System.Uri?displayProperty=nameWithType> クラスはまずパスの区切り記号をエスケープ解除し、次にパスの圧縮を適用します。</span><span class="sxs-lookup"><span data-stu-id="12384-127">For this reason, <xref:System.Uri?displayProperty=nameWithType> class first un-escapes path delimiters and then applies path compression.</span></span> <span data-ttu-id="12384-128">上の悪意のある URL をクラスコンストラクターに渡すと、次の URI が生成され <xref:System.Uri?displayProperty=nameWithType> ます。</span><span class="sxs-lookup"><span data-stu-id="12384-128">The result of passing the malicious URL above to <xref:System.Uri?displayProperty=nameWithType> class constructor results in the following URI:</span></span>  
  
 `http://www.microsoft.com/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="12384-129">この既定の動作は、特定のスキームの schemeSettings 構成オプションを使用して、パーセントエンコードされたパス区切り記号のエスケープを解除しないように変更できます。</span><span class="sxs-lookup"><span data-stu-id="12384-129">This default behavior can be modified to not un-escape percent encoded path delimiters using the schemeSettings configuration option for a specific scheme.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="12384-130">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="12384-130">Configuration Files</span></span>  
 <span data-ttu-id="12384-131">この要素は、アプリケーション構成ファイルまたはマシン構成ファイル (Machine.config) で使用できます。</span><span class="sxs-lookup"><span data-stu-id="12384-131">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="12384-132">例</span><span class="sxs-lookup"><span data-stu-id="12384-132">Example</span></span>  
 <span data-ttu-id="12384-133">次の例は、 <xref:System.Uri> http スキームに対してパーセントでエンコードされたパス区切り記号をエスケープしないようにするために、クラスによって使用される構成を示しています。</span><span class="sxs-lookup"><span data-stu-id="12384-133">The following example shows a configuration used by the <xref:System.Uri> class to support not escaping percent-encoded path delimiters for the http scheme.</span></span>  
  
```xml  
<configuration>  
  <uri>  
    <schemeSettings>  
      <add name="http" genericUriParserOptions="DontUnescapePathDotsAndSlashes"/>  
    </schemeSettings>  
  </uri>  
</configuration>  
```  
  
## <a name="element-information"></a><span data-ttu-id="12384-134">要素情報</span><span class="sxs-lookup"><span data-stu-id="12384-134">Element Information</span></span>  
  
|||
|-|-|  
|<span data-ttu-id="12384-135">名前空間</span><span class="sxs-lookup"><span data-stu-id="12384-135">Namespace</span></span>|<span data-ttu-id="12384-136">System</span><span class="sxs-lookup"><span data-stu-id="12384-136">System</span></span>|  
|<span data-ttu-id="12384-137">スキーマ名</span><span class="sxs-lookup"><span data-stu-id="12384-137">Schema Name</span></span>||  
|<span data-ttu-id="12384-138">検証ファイル</span><span class="sxs-lookup"><span data-stu-id="12384-138">Validation File</span></span>||  
|<span data-ttu-id="12384-139">空にすることができます</span><span class="sxs-lookup"><span data-stu-id="12384-139">Can be Empty</span></span>||  
  
## <a name="see-also"></a><span data-ttu-id="12384-140">関連項目</span><span class="sxs-lookup"><span data-stu-id="12384-140">See also</span></span>

- <xref:System.Configuration.SchemeSettingElement?displayProperty=nameWithType>
- <xref:System.Configuration.SchemeSettingElementCollection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection.SchemeSettings%2A?displayProperty=nameWithType>
- <xref:System.GenericUriParserOptions?displayProperty=nameWithType>
- <xref:System.Uri?displayProperty=nameWithType>
- [<span data-ttu-id="12384-141">ネットワーク設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="12384-141">Network Settings Schema</span></span>](index.md)
