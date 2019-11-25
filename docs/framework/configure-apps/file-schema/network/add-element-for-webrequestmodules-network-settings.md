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
ms.openlocfilehash: 76dad0c0b75d20627e9f57fd1bb467bf17c9294c
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/14/2019
ms.locfileid: "74088513"
---
# <a name="add-element-for-webrequestmodules-network-settings"></a><span data-ttu-id="25ee8-102">webRequestModules の > 要素を追加 \<(ネットワーク設定)</span><span class="sxs-lookup"><span data-stu-id="25ee8-102">\<add> Element for webRequestModules (Network Settings)</span></span>
<span data-ttu-id="25ee8-103">アプリケーションにカスタム Web 要求モジュールを追加します。</span><span class="sxs-lookup"><span data-stu-id="25ee8-103">Adds a custom Web request module to the application.</span></span>  

<span data-ttu-id="25ee8-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="25ee8-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="25ee8-105">&nbsp;&nbsp;[ **\<system. net >** ](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="25ee8-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>\
<span data-ttu-id="25ee8-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<webRequestModules >** ](webrequestmodules-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="25ee8-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<webRequestModules>**](webrequestmodules-element-network-settings.md)</span></span>\
<span data-ttu-id="25ee8-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**追加 >**</span><span class="sxs-lookup"><span data-stu-id="25ee8-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>

## <a name="syntax"></a><span data-ttu-id="25ee8-108">構文</span><span class="sxs-lookup"><span data-stu-id="25ee8-108">Syntax</span></span>  
  
```xml  
<add   
  prefix="URI prefix"   
  type="type_fullname, assembly_fullname"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="25ee8-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="25ee8-109">Attributes and Elements</span></span>  
 <span data-ttu-id="25ee8-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="25ee8-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="25ee8-111">属性</span><span class="sxs-lookup"><span data-stu-id="25ee8-111">Attributes</span></span>  
  
|<span data-ttu-id="25ee8-112">**属性**</span><span class="sxs-lookup"><span data-stu-id="25ee8-112">**Attribute**</span></span>|<span data-ttu-id="25ee8-113">**説明**</span><span class="sxs-lookup"><span data-stu-id="25ee8-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`prefix`|<span data-ttu-id="25ee8-114">この Web 要求モジュールによって処理される要求の URI プレフィックス。</span><span class="sxs-lookup"><span data-stu-id="25ee8-114">The URI prefix for requests handled by this Web request module.</span></span>|  
|`type`|<span data-ttu-id="25ee8-115">この Web 要求モジュールを実装する完全修飾型名 (<xref:System.Type.FullName%2A> プロパティによって示されます) とアセンブリ名 (<xref:System.Reflection.Assembly.FullName%2A> プロパティによって示されます) をコンマで区切って指定します。</span><span class="sxs-lookup"><span data-stu-id="25ee8-115">The fully qualified type name (indicated by the <xref:System.Type.FullName%2A> property) and the assembly name (indicated by the <xref:System.Reflection.Assembly.FullName%2A> property), separated by a comma, that implements this Web request module.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="25ee8-116">子要素</span><span class="sxs-lookup"><span data-stu-id="25ee8-116">Child Elements</span></span>  
 <span data-ttu-id="25ee8-117">なし。</span><span class="sxs-lookup"><span data-stu-id="25ee8-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="25ee8-118">親要素</span><span class="sxs-lookup"><span data-stu-id="25ee8-118">Parent Elements</span></span>  
  
|<span data-ttu-id="25ee8-119">**要素**</span><span class="sxs-lookup"><span data-stu-id="25ee8-119">**Element**</span></span>|<span data-ttu-id="25ee8-120">**説明**</span><span class="sxs-lookup"><span data-stu-id="25ee8-120">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="25ee8-121">webRequestModules</span><span class="sxs-lookup"><span data-stu-id="25ee8-121">webRequestModules</span></span>](webrequestmodules-element-network-settings.md)|<span data-ttu-id="25ee8-122">ネットワークホストから情報を要求するために使用するモジュールを指定します。</span><span class="sxs-lookup"><span data-stu-id="25ee8-122">Specifies modules to use to request information from network hosts.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="25ee8-123">Remarks</span><span class="sxs-lookup"><span data-stu-id="25ee8-123">Remarks</span></span>  
 <span data-ttu-id="25ee8-124">`prefix` 属性は、指定された Web 要求モジュールを使用する URI プレフィックスを定義します。</span><span class="sxs-lookup"><span data-stu-id="25ee8-124">The `prefix` attribute defines the URI prefix that uses the specified Web request module.</span></span> <span data-ttu-id="25ee8-125">通常、Web 要求モジュールは、HTTP や FTP などの特定のプロトコルを処理するように登録されますが、サーバー上の特定のサーバーまたはパスへの要求を処理するように登録できます。</span><span class="sxs-lookup"><span data-stu-id="25ee8-125">Web request modules are typically registered to handle a specific protocol, such as HTTP or FTP, but can be registered to handle a request to a specific server or path on a server.</span></span>  
  
 <span data-ttu-id="25ee8-126">Web 要求モジュールは、URI 照合プレフィックスが <xref:System.Net.WebRequest.Create%2A?displayProperty=nameWithType> メソッドに渡されると作成されます。</span><span class="sxs-lookup"><span data-stu-id="25ee8-126">The Web request module is created when a URI matching prefix is passed to the <xref:System.Net.WebRequest.Create%2A?displayProperty=nameWithType> method.</span></span>  
  
 <span data-ttu-id="25ee8-127">`prefix` 属性の値は、有効な URI の先頭の文字である必要があります。</span><span class="sxs-lookup"><span data-stu-id="25ee8-127">The value for the `prefix` attribute should be the leading characters of a valid URI.</span></span> <span data-ttu-id="25ee8-128">たとえば、`http` または `http://www.contoso.com` のようにします。</span><span class="sxs-lookup"><span data-stu-id="25ee8-128">For example, `http` or `http://www.contoso.com`.</span></span>
  
 <span data-ttu-id="25ee8-129">`type` 属性の値には、有効な型名と、対応するアセンブリ名をコンマで区切って指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="25ee8-129">The value for the `type` attribute should be a valid type name and corresponding assembly name, separated by a comma.</span></span>
  
## <a name="configuration-files"></a><span data-ttu-id="25ee8-130">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="25ee8-130">Configuration Files</span></span>  
 <span data-ttu-id="25ee8-131">この要素は、アプリケーション構成ファイルまたはマシン構成ファイル (Machine.config) で使用できます。</span><span class="sxs-lookup"><span data-stu-id="25ee8-131">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="25ee8-132">例</span><span class="sxs-lookup"><span data-stu-id="25ee8-132">Example</span></span>  
 <span data-ttu-id="25ee8-133">次の例では、HTTP 用のカスタム Web 要求モジュールを登録します。</span><span class="sxs-lookup"><span data-stu-id="25ee8-133">The following example registers a custom Web request module for HTTP.</span></span> <span data-ttu-id="25ee8-134">Version および PublicKeyToken の値は、指定されたモジュールの正しい値に置き換える必要があります。</span><span class="sxs-lookup"><span data-stu-id="25ee8-134">You should replace the values for Version and PublicKeyToken with the correct values for the specified module.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="25ee8-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="25ee8-135">See also</span></span>

- <xref:System.Net.WebRequest>
- [<span data-ttu-id="25ee8-136">ネットワーク設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="25ee8-136">Network Settings Schema</span></span>](index.md)
