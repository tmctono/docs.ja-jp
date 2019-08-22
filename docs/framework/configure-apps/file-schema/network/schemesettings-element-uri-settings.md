---
title: <schemeSettings> 要素 (Uri 設定)
ms.date: 03/30/2017
ms.assetid: 0ae45c6e-8c4c-4c0d-8b9f-a93824648890
ms.openlocfilehash: 46012b15d41422fb3357e57438e320136809ef41
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/21/2019
ms.locfileid: "69664006"
---
# <a name="schemesettings-element-uri-settings"></a><span data-ttu-id="05eed-102">\<schemeSettings > 要素 (Uri 設定)</span><span class="sxs-lookup"><span data-stu-id="05eed-102">\<schemeSettings> Element (Uri Settings)</span></span>
<span data-ttu-id="05eed-103"><xref:System.Uri> が特定のスキームに解析される方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="05eed-103">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>  
  
 <span data-ttu-id="05eed-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="05eed-104">\<configuration></span></span>  
<span data-ttu-id="05eed-105">\<uri></span><span class="sxs-lookup"><span data-stu-id="05eed-105">\<uri></span></span>  
<span data-ttu-id="05eed-106">\<schemeSettings></span><span class="sxs-lookup"><span data-stu-id="05eed-106">\<schemeSettings></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="05eed-107">構文</span><span class="sxs-lookup"><span data-stu-id="05eed-107">Syntax</span></span>  
  
```xml  
<schemeSettings>   
</schemeSettings>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="05eed-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="05eed-108">Attributes and Elements</span></span>  
 <span data-ttu-id="05eed-109">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="05eed-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="05eed-110">属性</span><span class="sxs-lookup"><span data-stu-id="05eed-110">Attributes</span></span>  
 <span data-ttu-id="05eed-111">なし</span><span class="sxs-lookup"><span data-stu-id="05eed-111">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="05eed-112">子要素</span><span class="sxs-lookup"><span data-stu-id="05eed-112">Child Elements</span></span>  
  
|<span data-ttu-id="05eed-113">**要素**</span><span class="sxs-lookup"><span data-stu-id="05eed-113">**Element**</span></span>|<span data-ttu-id="05eed-114">**説明**</span><span class="sxs-lookup"><span data-stu-id="05eed-114">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="05eed-115">add</span><span class="sxs-lookup"><span data-stu-id="05eed-115">add</span></span>](add-element-for-schemesettings-uri-settings.md)|<span data-ttu-id="05eed-116">スキーム名のスキーム設定を追加します。</span><span class="sxs-lookup"><span data-stu-id="05eed-116">Adds a scheme setting for a scheme name.</span></span>|  
|[<span data-ttu-id="05eed-117">clear</span><span class="sxs-lookup"><span data-stu-id="05eed-117">clear</span></span>](clear-element-for-schemesettings-uri-settings.md)|<span data-ttu-id="05eed-118">既存のスキーム設定をすべてクリアします。</span><span class="sxs-lookup"><span data-stu-id="05eed-118">Clears all existing scheme settings.</span></span>|  
|[<span data-ttu-id="05eed-119">remove</span><span class="sxs-lookup"><span data-stu-id="05eed-119">remove</span></span>](remove-element-for-schemesettings-uri-settings.md)|<span data-ttu-id="05eed-120">スキーム名のスキーム設定を削除します。</span><span class="sxs-lookup"><span data-stu-id="05eed-120">Removes a scheme setting for a scheme name.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="05eed-121">親要素</span><span class="sxs-lookup"><span data-stu-id="05eed-121">Parent Elements</span></span>  
  
|<span data-ttu-id="05eed-122">**要素**</span><span class="sxs-lookup"><span data-stu-id="05eed-122">**Element**</span></span>|<span data-ttu-id="05eed-123">**説明**</span><span class="sxs-lookup"><span data-stu-id="05eed-123">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="05eed-124">uri</span><span class="sxs-lookup"><span data-stu-id="05eed-124">uri</span></span>](uri-element-uri-settings.md)|<span data-ttu-id="05eed-125">.NET Framework が、uniform resource identifier (Uri) を使用して表された web アドレスを処理する方法を指定する設定が含まれます。</span><span class="sxs-lookup"><span data-stu-id="05eed-125">Contains settings that specify how the .NET Framework handles web addresses expressed using uniform resource identifiers (URIs).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="05eed-126">Remarks</span><span class="sxs-lookup"><span data-stu-id="05eed-126">Remarks</span></span>  
 <span data-ttu-id="05eed-127">既定では、 <xref:System.Uri?displayProperty=nameWithType>クラスは、パスの圧縮を実行する前に、エンコードされたパス区切り記号のエスケープを解除します。</span><span class="sxs-lookup"><span data-stu-id="05eed-127">By default, the <xref:System.Uri?displayProperty=nameWithType> class un-escapes percent encoded path delimiters before executing path compression.</span></span> <span data-ttu-id="05eed-128">これは、次のような攻撃に対するセキュリティメカニズムとして実装されています。</span><span class="sxs-lookup"><span data-stu-id="05eed-128">This was implemented as a security mechanism against attacks like the following:</span></span>  
  
 `http://www.contoso.com/..%2F..%2F/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="05eed-129">% Encoded 文字を正しく処理しないモジュールにこの URI が渡された場合、サーバーによって次のコマンドが実行される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="05eed-129">If this URI gets passed down to modules not handling percent encoded characters correctly, it could result in the following command being executed by the server:</span></span>  
  
 `c:\Windows\System32\cmd.exe /c dir c:\`  
  
 <span data-ttu-id="05eed-130">このため、クラス<xref:System.Uri?displayProperty=nameWithType>はまずパスの区切り記号をエスケープ解除し、次にパスの圧縮を適用します。</span><span class="sxs-lookup"><span data-stu-id="05eed-130">For this reason, <xref:System.Uri?displayProperty=nameWithType> class first un-escapes path delimiters and then applies path compression.</span></span> <span data-ttu-id="05eed-131">上の悪意のある URL をクラスコンストラクター <xref:System.Uri?displayProperty=nameWithType>に渡すと、次の URI が生成されます。</span><span class="sxs-lookup"><span data-stu-id="05eed-131">The result of passing the malicious URL above to <xref:System.Uri?displayProperty=nameWithType> class constructor results in the following URI:</span></span>  
  
 `http://www.microsoft.com/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="05eed-132">この既定の動作は、特定のスキームの schemeSettings 構成オプションを使用して、パーセントエンコードされたパス区切り記号のエスケープを解除しないように変更できます。</span><span class="sxs-lookup"><span data-stu-id="05eed-132">This default behavior can be modified to not un-escape percent encoded path delimiters using the schemeSettings configuration option for a specific scheme.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="05eed-133">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="05eed-133">Configuration Files</span></span>  
 <span data-ttu-id="05eed-134">この要素は、アプリケーション構成ファイルまたはマシン構成ファイル (Machine.config) で使用できます。</span><span class="sxs-lookup"><span data-stu-id="05eed-134">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="05eed-135">例</span><span class="sxs-lookup"><span data-stu-id="05eed-135">Example</span></span>  
 <span data-ttu-id="05eed-136">次の例は、http スキームに対し<xref:System.Uri>てパーセントでエンコードされたパス区切り記号をエスケープしないようにするために、クラスによって使用される構成を示しています。</span><span class="sxs-lookup"><span data-stu-id="05eed-136">The following example shows a configuration used by the <xref:System.Uri> class to support not escaping percent-encoded path delimiters for the http scheme.</span></span>  
  
```xml  
<configuration>  
  <uri>  
    <schemeSettings>  
      <add name="http" genericUriParserOptions="DontUnescapePathDotsAndSlashes"/>  
    </schemeSettings>  
  </uri>  
</configuration>  
```  
  
## <a name="element-information"></a><span data-ttu-id="05eed-137">要素情報</span><span class="sxs-lookup"><span data-stu-id="05eed-137">Element Information</span></span>  
  
|||
|-|-|  
|<span data-ttu-id="05eed-138">名前空間</span><span class="sxs-lookup"><span data-stu-id="05eed-138">Namespace</span></span>|<span data-ttu-id="05eed-139">システム</span><span class="sxs-lookup"><span data-stu-id="05eed-139">System</span></span>|  
|<span data-ttu-id="05eed-140">スキーマ名</span><span class="sxs-lookup"><span data-stu-id="05eed-140">Schema Name</span></span>||  
|<span data-ttu-id="05eed-141">検証ファイル</span><span class="sxs-lookup"><span data-stu-id="05eed-141">Validation File</span></span>||  
|<span data-ttu-id="05eed-142">空にすることができます</span><span class="sxs-lookup"><span data-stu-id="05eed-142">Can be Empty</span></span>||  
  
## <a name="see-also"></a><span data-ttu-id="05eed-143">関連項目</span><span class="sxs-lookup"><span data-stu-id="05eed-143">See also</span></span>

- <xref:System.Configuration.SchemeSettingElement?displayProperty=nameWithType>
- <xref:System.Configuration.SchemeSettingElementCollection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection.SchemeSettings%2A?displayProperty=nameWithType>
- <xref:System.GenericUriParserOptions?displayProperty=nameWithType>
- <xref:System.Uri?displayProperty=nameWithType>
- [<span data-ttu-id="05eed-144">ネットワーク設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="05eed-144">Network Settings Schema</span></span>](index.md)
