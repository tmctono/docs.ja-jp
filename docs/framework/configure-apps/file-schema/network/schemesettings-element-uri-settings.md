---
title: <schemeSettings> 要素 (Uri 設定)
ms.date: 03/30/2017
ms.assetid: 0ae45c6e-8c4c-4c0d-8b9f-a93824648890
ms.openlocfilehash: c745c90bb61b9ee393687d7f6db4fd11565c7dc7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154648"
---
# <a name="schemesettings-element-uri-settings"></a><span data-ttu-id="30335-102">\<schemeSettings> 要素 (Uri 設定)</span><span class="sxs-lookup"><span data-stu-id="30335-102">\<schemeSettings> Element (Uri Settings)</span></span>
<span data-ttu-id="30335-103"><xref:System.Uri> が特定のスキームに解析される方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="30335-103">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>  
  
[<span data-ttu-id="30335-104">**\<構成>**</span><span class="sxs-lookup"><span data-stu-id="30335-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="30335-105">&nbsp;&nbsp;[**\<uri>**](uri-element-uri-settings.md)</span><span class="sxs-lookup"><span data-stu-id="30335-105">&nbsp;&nbsp;[**\<uri>**](uri-element-uri-settings.md)</span></span>  
<span data-ttu-id="30335-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<スキーム設定>**</span><span class="sxs-lookup"><span data-stu-id="30335-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<schemeSettings>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="30335-107">構文</span><span class="sxs-lookup"><span data-stu-id="30335-107">Syntax</span></span>  
  
```xml  
<schemeSettings>
</schemeSettings>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="30335-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="30335-108">Attributes and Elements</span></span>  
 <span data-ttu-id="30335-109">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="30335-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="30335-110">属性</span><span class="sxs-lookup"><span data-stu-id="30335-110">Attributes</span></span>  
 <span data-ttu-id="30335-111">なし</span><span class="sxs-lookup"><span data-stu-id="30335-111">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="30335-112">子要素</span><span class="sxs-lookup"><span data-stu-id="30335-112">Child Elements</span></span>  
  
|<span data-ttu-id="30335-113">**Element**</span><span class="sxs-lookup"><span data-stu-id="30335-113">**Element**</span></span>|<span data-ttu-id="30335-114">**説明**</span><span class="sxs-lookup"><span data-stu-id="30335-114">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="30335-115">追加</span><span class="sxs-lookup"><span data-stu-id="30335-115">add</span></span>](add-element-for-schemesettings-uri-settings.md)|<span data-ttu-id="30335-116">スキーム名のスキーム設定を追加します。</span><span class="sxs-lookup"><span data-stu-id="30335-116">Adds a scheme setting for a scheme name.</span></span>|  
|[<span data-ttu-id="30335-117">クリア</span><span class="sxs-lookup"><span data-stu-id="30335-117">clear</span></span>](clear-element-for-schemesettings-uri-settings.md)|<span data-ttu-id="30335-118">既存のスキーム設定をすべてクリアします。</span><span class="sxs-lookup"><span data-stu-id="30335-118">Clears all existing scheme settings.</span></span>|  
|[<span data-ttu-id="30335-119">削除</span><span class="sxs-lookup"><span data-stu-id="30335-119">remove</span></span>](remove-element-for-schemesettings-uri-settings.md)|<span data-ttu-id="30335-120">スキーム名のスキーム設定を削除します。</span><span class="sxs-lookup"><span data-stu-id="30335-120">Removes a scheme setting for a scheme name.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="30335-121">親要素</span><span class="sxs-lookup"><span data-stu-id="30335-121">Parent Elements</span></span>  
  
|<span data-ttu-id="30335-122">**Element**</span><span class="sxs-lookup"><span data-stu-id="30335-122">**Element**</span></span>|<span data-ttu-id="30335-123">**説明**</span><span class="sxs-lookup"><span data-stu-id="30335-123">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="30335-124">Uri</span><span class="sxs-lookup"><span data-stu-id="30335-124">uri</span></span>](uri-element-uri-settings.md)|<span data-ttu-id="30335-125">統一リソース識別子 (URI) を使用して表される Web アドレスを .NET Framework が処理する方法を指定する設定が含まれています。</span><span class="sxs-lookup"><span data-stu-id="30335-125">Contains settings that specify how the .NET Framework handles web addresses expressed using uniform resource identifiers (URIs).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="30335-126">解説</span><span class="sxs-lookup"><span data-stu-id="30335-126">Remarks</span></span>  
 <span data-ttu-id="30335-127">既定では、クラス<xref:System.Uri?displayProperty=nameWithType>はパス圧縮を実行する前に、エンコードされたパスの区切り記号をパーセントでエスケープ解除します。</span><span class="sxs-lookup"><span data-stu-id="30335-127">By default, the <xref:System.Uri?displayProperty=nameWithType> class un-escapes percent encoded path delimiters before executing path compression.</span></span> <span data-ttu-id="30335-128">これは、次のような攻撃に対するセキュリティ メカニズムとして実装されました。</span><span class="sxs-lookup"><span data-stu-id="30335-128">This was implemented as a security mechanism against attacks like the following:</span></span>  
  
 `http://www.contoso.com/..%2F..%2F/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="30335-129">この URI がモジュールに渡されてパーセントエンコード文字が正しく処理されない場合、サーバーが実行するコマンドは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="30335-129">If this URI gets passed down to modules not handling percent encoded characters correctly, it could result in the following command being executed by the server:</span></span>  
  
 `c:\Windows\System32\cmd.exe /c dir c:\`  
  
 <span data-ttu-id="30335-130">このため、class<xref:System.Uri?displayProperty=nameWithType>はまずパス区切り文字をアンエスケープし、次にパス圧縮を適用します。</span><span class="sxs-lookup"><span data-stu-id="30335-130">For this reason, <xref:System.Uri?displayProperty=nameWithType> class first un-escapes path delimiters and then applies path compression.</span></span> <span data-ttu-id="30335-131">上記の悪意のある URL をクラス<xref:System.Uri?displayProperty=nameWithType>コンストラクターに渡した結果、次の URI が生成されます。</span><span class="sxs-lookup"><span data-stu-id="30335-131">The result of passing the malicious URL above to <xref:System.Uri?displayProperty=nameWithType> class constructor results in the following URI:</span></span>  
  
 `http://www.microsoft.com/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="30335-132">この既定の動作は、特定のスキームの schemeSettings 構成オプションを使用して、エンコードされたパス区切り記号をエスケープ解除しないように変更できます。</span><span class="sxs-lookup"><span data-stu-id="30335-132">This default behavior can be modified to not un-escape percent encoded path delimiters using the schemeSettings configuration option for a specific scheme.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="30335-133">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="30335-133">Configuration Files</span></span>  
 <span data-ttu-id="30335-134">この要素は、アプリケーション構成ファイルまたはマシン構成ファイル (Machine.config) で使用できます。</span><span class="sxs-lookup"><span data-stu-id="30335-134">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="30335-135">例</span><span class="sxs-lookup"><span data-stu-id="30335-135">Example</span></span>  
 <span data-ttu-id="30335-136">次の例は、http スキームの<xref:System.Uri>パーセントエンコードパス区切り記号をエスケープしないようにクラスで使用される構成を示しています。</span><span class="sxs-lookup"><span data-stu-id="30335-136">The following example shows a configuration used by the <xref:System.Uri> class to support not escaping percent-encoded path delimiters for the http scheme.</span></span>  
  
```xml  
<configuration>  
  <uri>  
    <schemeSettings>  
      <add name="http" genericUriParserOptions="DontUnescapePathDotsAndSlashes"/>  
    </schemeSettings>  
  </uri>  
</configuration>  
```  
  
## <a name="element-information"></a><span data-ttu-id="30335-137">要素情報</span><span class="sxs-lookup"><span data-stu-id="30335-137">Element Information</span></span>  
  
|||
|-|-|  
|<span data-ttu-id="30335-138">名前空間</span><span class="sxs-lookup"><span data-stu-id="30335-138">Namespace</span></span>|<span data-ttu-id="30335-139">システム</span><span class="sxs-lookup"><span data-stu-id="30335-139">System</span></span>|  
|<span data-ttu-id="30335-140">スキーマ名</span><span class="sxs-lookup"><span data-stu-id="30335-140">Schema Name</span></span>||  
|<span data-ttu-id="30335-141">検証ファイル</span><span class="sxs-lookup"><span data-stu-id="30335-141">Validation File</span></span>||  
|<span data-ttu-id="30335-142">空にできる</span><span class="sxs-lookup"><span data-stu-id="30335-142">Can be Empty</span></span>||  
  
## <a name="see-also"></a><span data-ttu-id="30335-143">関連項目</span><span class="sxs-lookup"><span data-stu-id="30335-143">See also</span></span>

- <xref:System.Configuration.SchemeSettingElement?displayProperty=nameWithType>
- <xref:System.Configuration.SchemeSettingElementCollection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection.SchemeSettings%2A?displayProperty=nameWithType>
- <xref:System.GenericUriParserOptions?displayProperty=nameWithType>
- <xref:System.Uri?displayProperty=nameWithType>
- [<span data-ttu-id="30335-144">ネットワーク設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="30335-144">Network Settings Schema</span></span>](index.md)
