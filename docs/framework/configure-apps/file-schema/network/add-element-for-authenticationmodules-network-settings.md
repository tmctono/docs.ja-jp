---
title: authenticationModules の <add> 要素 (ネットワーク設定)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#add
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/authenticationModules/add
helpviewer_keywords:
- authenticationModules, add element
- add element, authenticationModules
- <authenticationModules>, add element
- <add> element, authenticationModules
ms.assetid: 333c5fb0-a2ab-4db8-8531-a7fe37bb9b5b
ms.openlocfilehash: 9c011cf1216b98fa20e330e185e4cf2c331b31d4
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/14/2019
ms.locfileid: "74087950"
---
# <a name="add-element-for-authenticationmodules-network-settings"></a><span data-ttu-id="9b5b1-102">authenticationModules の > 要素を追加 \<(ネットワーク設定)</span><span class="sxs-lookup"><span data-stu-id="9b5b1-102">\<add> Element for authenticationModules (Network Settings)</span></span>
<span data-ttu-id="9b5b1-103">アプリケーションに認証モジュールを追加します。</span><span class="sxs-lookup"><span data-stu-id="9b5b1-103">Adds an authentication module to the application.</span></span>  

<span data-ttu-id="9b5b1-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="9b5b1-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="9b5b1-105">&nbsp;&nbsp;[ **\<system. net >** ](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="9b5b1-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>\
<span data-ttu-id="9b5b1-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<authenticationModules >** ](authenticationmodules-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="9b5b1-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<authenticationModules>**](authenticationmodules-element-network-settings.md)</span></span>\
<span data-ttu-id="9b5b1-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**追加 >**</span><span class="sxs-lookup"><span data-stu-id="9b5b1-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>

## <a name="syntax"></a><span data-ttu-id="9b5b1-108">構文</span><span class="sxs-lookup"><span data-stu-id="9b5b1-108">Syntax</span></span>  
  
```xml  
<add
  type="type_fullname, assembly_fullname"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9b5b1-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="9b5b1-109">Attributes and Elements</span></span>  
 <span data-ttu-id="9b5b1-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="9b5b1-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9b5b1-111">属性</span><span class="sxs-lookup"><span data-stu-id="9b5b1-111">Attributes</span></span>  
  
|<span data-ttu-id="9b5b1-112">**属性**</span><span class="sxs-lookup"><span data-stu-id="9b5b1-112">**Attribute**</span></span>|<span data-ttu-id="9b5b1-113">**説明**</span><span class="sxs-lookup"><span data-stu-id="9b5b1-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`type`|<span data-ttu-id="9b5b1-114">コンマで区切られた、(<xref:System.Type.FullName%2A> プロパティによって示される) 完全修飾型名とアセンブリ名 (<xref:System.Reflection.Assembly.FullName%2A> プロパティによって示されます)。</span><span class="sxs-lookup"><span data-stu-id="9b5b1-114">The fully qualified type name (indicated by the <xref:System.Type.FullName%2A> property) and the assembly name (indicated by the <xref:System.Reflection.Assembly.FullName%2A> property), separated by a comma.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9b5b1-115">子要素</span><span class="sxs-lookup"><span data-stu-id="9b5b1-115">Child Elements</span></span>  
 <span data-ttu-id="9b5b1-116">なし。</span><span class="sxs-lookup"><span data-stu-id="9b5b1-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9b5b1-117">親要素</span><span class="sxs-lookup"><span data-stu-id="9b5b1-117">Parent Elements</span></span>  
  
|<span data-ttu-id="9b5b1-118">**要素**</span><span class="sxs-lookup"><span data-stu-id="9b5b1-118">**Element**</span></span>|<span data-ttu-id="9b5b1-119">**説明**</span><span class="sxs-lookup"><span data-stu-id="9b5b1-119">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="9b5b1-120">authenticationModules</span><span class="sxs-lookup"><span data-stu-id="9b5b1-120">authenticationModules</span></span>](authenticationmodules-element-network-settings.md)|<span data-ttu-id="9b5b1-121">ネットワーク要求を認証するために使用するモジュールを指定します。</span><span class="sxs-lookup"><span data-stu-id="9b5b1-121">Specifies modules used to authenticate network requests.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9b5b1-122">Remarks</span><span class="sxs-lookup"><span data-stu-id="9b5b1-122">Remarks</span></span>  
 <span data-ttu-id="9b5b1-123">`add` 要素は、登録されている認証モジュールの一覧の末尾に認証モジュールを追加します。</span><span class="sxs-lookup"><span data-stu-id="9b5b1-123">The `add` element adds an authentication module to the end of the list of registered authentication modules.</span></span> <span data-ttu-id="9b5b1-124">認証モジュールは、一覧に追加された順序で呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="9b5b1-124">Authentication modules are called in the order in which they were added to the list.</span></span>  
  
 <span data-ttu-id="9b5b1-125">`type` 属性の値には、有効な型名と、対応するアセンブリ名をコンマで区切って指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9b5b1-125">The value for the `type` attribute should be a valid type name and corresponding assembly name, separated by a comma.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="9b5b1-126">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="9b5b1-126">Configuration Files</span></span>  
 <span data-ttu-id="9b5b1-127">この要素は、アプリケーション構成ファイルまたはマシン構成ファイル (Machine.config) で使用できます。</span><span class="sxs-lookup"><span data-stu-id="9b5b1-127">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="9b5b1-128">例</span><span class="sxs-lookup"><span data-stu-id="9b5b1-128">Example</span></span>  
 <span data-ttu-id="9b5b1-129">次の例では、既定の認証モジュールを有効にします。</span><span class="sxs-lookup"><span data-stu-id="9b5b1-129">The following example enables the default authentication modules.</span></span> <span data-ttu-id="9b5b1-130">Version および PublicKeyToken の値は、指定されたモジュールの正しい値に置き換える必要があります。</span><span class="sxs-lookup"><span data-stu-id="9b5b1-130">You should replace the values for Version and PublicKeyToken with the correct values for the specified module.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
        <authenticationModules>  
            <add type="System.Net.DigestClient, System, Version=2.0.3600.0,  
                 Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
            <add type="System.Net.NegotiateClient, System, Version=2.0.3600.0,  
                 Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
            <add type="System.Net.KerberosClient, System, Version=2.0.3600.0,  
                 Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
            <add type="System.Net.NtlmClient, System, Version=2.0.3600.0,  
                 Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
            <add type="System.Net.BasicClient, System, Version=2.0.3600.0,  
                 Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
        </authenticationModules>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="9b5b1-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="9b5b1-131">See also</span></span>

- <xref:System.Net.IAuthenticationModule>
- <xref:System.Net.AuthenticationManager>
- [<span data-ttu-id="9b5b1-132">ネットワーク設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="9b5b1-132">Network Settings Schema</span></span>](index.md)
