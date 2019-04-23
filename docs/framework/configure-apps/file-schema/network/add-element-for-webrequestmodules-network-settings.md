---
title: webRequestModules の <add> 要素 (ネットワーク設定)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/webRequestModules/add
- http://schemas.microsoft.com/.NetConfiguration/v2.0#add
helpviewer_keywords:
- <webRequestModules>, add element
- webRequestModules, add element
- add element, webRequestModules
- <add> element, webRequestModules
ms.assetid: 47ec4adc-f39f-4bcd-8680-1ec21fd26890
ms.openlocfilehash: 4c1116c088c12ad3859714c8d75704d0156c12f7
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59188250"
---
# <a name="add-element-for-webrequestmodules-network-settings"></a><span data-ttu-id="4db82-102">\<追加 > webRequestModules (ネットワーク設定) の要素</span><span class="sxs-lookup"><span data-stu-id="4db82-102">\<add> Element for webRequestModules (Network Settings)</span></span>
<span data-ttu-id="4db82-103">カスタムの Web 要求モジュールをアプリケーションに追加します。</span><span class="sxs-lookup"><span data-stu-id="4db82-103">Adds a custom Web request module to the application.</span></span>  
  
 <span data-ttu-id="4db82-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="4db82-104">\<configuration></span></span>  
<span data-ttu-id="4db82-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="4db82-105">\<system.net></span></span>  
<span data-ttu-id="4db82-106">\<webRequestModules></span><span class="sxs-lookup"><span data-stu-id="4db82-106">\<webRequestModules></span></span>  
<span data-ttu-id="4db82-107">\<add></span><span class="sxs-lookup"><span data-stu-id="4db82-107">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4db82-108">構文</span><span class="sxs-lookup"><span data-stu-id="4db82-108">Syntax</span></span>  
  
```xml  
<add   
  prefix="URI prefix"   
  type="type_fullname, assembly_fullname"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4db82-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="4db82-109">Attributes and Elements</span></span>  
 <span data-ttu-id="4db82-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="4db82-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4db82-111">属性</span><span class="sxs-lookup"><span data-stu-id="4db82-111">Attributes</span></span>  
  
|<span data-ttu-id="4db82-112">**属性**</span><span class="sxs-lookup"><span data-stu-id="4db82-112">**Attribute**</span></span>|<span data-ttu-id="4db82-113">**説明**</span><span class="sxs-lookup"><span data-stu-id="4db82-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`prefix`|<span data-ttu-id="4db82-114">この Web 要求モジュールによって処理される要求の URI プレフィックス。</span><span class="sxs-lookup"><span data-stu-id="4db82-114">The URI prefix for requests handled by this Web request module.</span></span>|  
|`type`|<span data-ttu-id="4db82-115">完全修飾型名 (によって示される、<xref:System.Type.FullName%2A>プロパティ) とアセンブリ名 (によって示される、<xref:System.Reflection.Assembly.FullName%2A>プロパティ)、この Web 要求モジュールを実装する、コンマで区切られました。</span><span class="sxs-lookup"><span data-stu-id="4db82-115">The fully qualified type name (indicated by the <xref:System.Type.FullName%2A> property) and the assembly name (indicated by the <xref:System.Reflection.Assembly.FullName%2A> property), separated by a comma, that implements this Web request module.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4db82-116">子要素</span><span class="sxs-lookup"><span data-stu-id="4db82-116">Child Elements</span></span>  
 <span data-ttu-id="4db82-117">なし。</span><span class="sxs-lookup"><span data-stu-id="4db82-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4db82-118">親要素</span><span class="sxs-lookup"><span data-stu-id="4db82-118">Parent Elements</span></span>  
  
|<span data-ttu-id="4db82-119">**要素**</span><span class="sxs-lookup"><span data-stu-id="4db82-119">**Element**</span></span>|<span data-ttu-id="4db82-120">**説明**</span><span class="sxs-lookup"><span data-stu-id="4db82-120">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="4db82-121">webRequestModules</span><span class="sxs-lookup"><span data-stu-id="4db82-121">webRequestModules</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/webrequestmodules-element-network-settings.md)|<span data-ttu-id="4db82-122">使用してネットワークのホストから情報を要求するモジュールを指定します。</span><span class="sxs-lookup"><span data-stu-id="4db82-122">Specifies modules to use to request information from network hosts.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4db82-123">Remarks</span><span class="sxs-lookup"><span data-stu-id="4db82-123">Remarks</span></span>  
 <span data-ttu-id="4db82-124">`prefix`属性が指定された Web 要求モジュールを使用する URI プレフィックスを定義します。</span><span class="sxs-lookup"><span data-stu-id="4db82-124">The `prefix` attribute defines the URI prefix that uses the specified Web request module.</span></span> <span data-ttu-id="4db82-125">Web 要求モジュールは通常、HTTP、FTP などの特定のプロトコルを処理するために登録しますが、特定のサーバーまたはサーバー上のパスへの要求を処理するために登録することができます。</span><span class="sxs-lookup"><span data-stu-id="4db82-125">Web request modules are typically registered to handle a specific protocol, such as HTTP or FTP, but can be registered to handle a request to a specific server or path on a server.</span></span>  
  
 <span data-ttu-id="4db82-126">一致する URI のプレフィックスが渡されるときに、Web 要求モジュールが作成された、<xref:System.Net.WebRequest.Create%2A?displayProperty=nameWithType>メソッド。</span><span class="sxs-lookup"><span data-stu-id="4db82-126">The Web request module is created when a URI matching prefix is passed to the <xref:System.Net.WebRequest.Create%2A?displayProperty=nameWithType> method.</span></span>  
  
 <span data-ttu-id="4db82-127">値、`prefix`属性が有効な URI の先頭の文字にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4db82-127">The value for the `prefix` attribute should be the leading characters of a valid URI.</span></span> <span data-ttu-id="4db82-128">たとえば、`http` または `http://www.contoso.com` のようにします。</span><span class="sxs-lookup"><span data-stu-id="4db82-128">For example, `http` or `http://www.contoso.com`.</span></span>
  
 <span data-ttu-id="4db82-129">値、`type`属性が有効な型名と対応するアセンブリ名、コンマで区切られたにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4db82-129">The value for the `type` attribute should be a valid type name and corresponding assembly name, separated by a comma.</span></span>
  
## <a name="configuration-files"></a><span data-ttu-id="4db82-130">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="4db82-130">Configuration Files</span></span>  
 <span data-ttu-id="4db82-131">この要素は、アプリケーション構成ファイルまたはマシン構成ファイル (Machine.config) で使用できます。</span><span class="sxs-lookup"><span data-stu-id="4db82-131">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="4db82-132">例</span><span class="sxs-lookup"><span data-stu-id="4db82-132">Example</span></span>  
 <span data-ttu-id="4db82-133">次の例では、HTTP の場合、カスタムの Web 要求モジュールを登録します。</span><span class="sxs-lookup"><span data-stu-id="4db82-133">The following example registers a custom Web request module for HTTP.</span></span> <span data-ttu-id="4db82-134">指定したモジュールの正しい値で、バージョンおよび PublicKeyToken の値を置き換える必要があります。</span><span class="sxs-lookup"><span data-stu-id="4db82-134">You should replace the values for Version and PublicKeyToken with the correct values for the specified module.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <webRequestModules>  
      <add prefix="http"  
           type="System.Net.HttpRequestCreator, System, Version=2.0.3600.0,  
           Culture=neutral, PublicKeyToken=b77a5c561934e089"  
      />  
    </webRequestModules>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="4db82-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="4db82-135">See also</span></span>

- <xref:System.Net.WebRequest>
- [<span data-ttu-id="4db82-136">ネットワーク設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="4db82-136">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
