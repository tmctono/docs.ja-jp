---
title: authenticationModules の <add> 要素 (ネットワーク設定)
description: <add>Connectionmanagement のネットワーク設定要素によって、.NET Framework の接続管理リストに IP アドレスまたは DNS 名が追加されます。
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
ms.openlocfilehash: 1a6d0f79f076a69cec33ac14f0e0f33f7c3c6577
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "84504642"
---
# <a name="add-element-for-authenticationmodules-network-settings"></a><span data-ttu-id="60ee2-103">authenticationModules の \<add> 要素 (ネットワーク設定)</span><span class="sxs-lookup"><span data-stu-id="60ee2-103">\<add> Element for authenticationModules (Network Settings)</span></span>
<span data-ttu-id="60ee2-104">アプリケーションに認証モジュールを追加します。</span><span class="sxs-lookup"><span data-stu-id="60ee2-104">Adds an authentication module to the application.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<authenticationModules>**](authenticationmodules-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**

## <a name="syntax"></a><span data-ttu-id="60ee2-105">構文</span><span class="sxs-lookup"><span data-stu-id="60ee2-105">Syntax</span></span>  
  
```xml  
<add
  type="type_fullname, assembly_fullname"
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="60ee2-106">属性および要素</span><span class="sxs-lookup"><span data-stu-id="60ee2-106">Attributes and Elements</span></span>  
 <span data-ttu-id="60ee2-107">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="60ee2-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="60ee2-108">属性</span><span class="sxs-lookup"><span data-stu-id="60ee2-108">Attributes</span></span>  
  
|<span data-ttu-id="60ee2-109">**属性**</span><span class="sxs-lookup"><span data-stu-id="60ee2-109">**Attribute**</span></span>|<span data-ttu-id="60ee2-110">**説明**</span><span class="sxs-lookup"><span data-stu-id="60ee2-110">**Description**</span></span>|  
|-------------------|---------------------|  
|`type`|<span data-ttu-id="60ee2-111">コンマで区切られた、完全修飾型名 (プロパティによって示され <xref:System.Type.FullName%2A> ます) とアセンブリ名 (プロパティによって示され <xref:System.Reflection.Assembly.FullName%2A> ます)。</span><span class="sxs-lookup"><span data-stu-id="60ee2-111">The fully qualified type name (indicated by the <xref:System.Type.FullName%2A> property) and the assembly name (indicated by the <xref:System.Reflection.Assembly.FullName%2A> property), separated by a comma.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="60ee2-112">子要素</span><span class="sxs-lookup"><span data-stu-id="60ee2-112">Child Elements</span></span>  
 <span data-ttu-id="60ee2-113">なし。</span><span class="sxs-lookup"><span data-stu-id="60ee2-113">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="60ee2-114">親要素</span><span class="sxs-lookup"><span data-stu-id="60ee2-114">Parent Elements</span></span>  
  
|<span data-ttu-id="60ee2-115">**要素**</span><span class="sxs-lookup"><span data-stu-id="60ee2-115">**Element**</span></span>|<span data-ttu-id="60ee2-116">**説明**</span><span class="sxs-lookup"><span data-stu-id="60ee2-116">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="60ee2-117">authenticationModules</span><span class="sxs-lookup"><span data-stu-id="60ee2-117">authenticationModules</span></span>](authenticationmodules-element-network-settings.md)|<span data-ttu-id="60ee2-118">ネットワーク要求を認証するために使用するモジュールを指定します。</span><span class="sxs-lookup"><span data-stu-id="60ee2-118">Specifies modules used to authenticate network requests.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="60ee2-119">解説</span><span class="sxs-lookup"><span data-stu-id="60ee2-119">Remarks</span></span>  
 <span data-ttu-id="60ee2-120">要素は、 `add` 登録されている認証モジュールの一覧の末尾に認証モジュールを追加します。</span><span class="sxs-lookup"><span data-stu-id="60ee2-120">The `add` element adds an authentication module to the end of the list of registered authentication modules.</span></span> <span data-ttu-id="60ee2-121">認証モジュールは、一覧に追加された順序で呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="60ee2-121">Authentication modules are called in the order in which they were added to the list.</span></span>  
  
 <span data-ttu-id="60ee2-122">属性の値は、 `type` 有効な型名と、それに対応するアセンブリ名をコンマで区切って指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="60ee2-122">The value for the `type` attribute should be a valid type name and corresponding assembly name, separated by a comma.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="60ee2-123">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="60ee2-123">Configuration Files</span></span>  
 <span data-ttu-id="60ee2-124">この要素は、アプリケーション構成ファイルまたはマシン構成ファイル (Machine.config) で使用できます。</span><span class="sxs-lookup"><span data-stu-id="60ee2-124">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="60ee2-125">例</span><span class="sxs-lookup"><span data-stu-id="60ee2-125">Example</span></span>  
 <span data-ttu-id="60ee2-126">次の例では、既定の認証モジュールを有効にします。</span><span class="sxs-lookup"><span data-stu-id="60ee2-126">The following example enables the default authentication modules.</span></span> <span data-ttu-id="60ee2-127">Version および PublicKeyToken の値は、指定されたモジュールの正しい値に置き換える必要があります。</span><span class="sxs-lookup"><span data-stu-id="60ee2-127">You should replace the values for Version and PublicKeyToken with the correct values for the specified module.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="60ee2-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="60ee2-128">See also</span></span>

- <xref:System.Net.IAuthenticationModule>
- <xref:System.Net.AuthenticationManager>
- [<span data-ttu-id="60ee2-129">ネットワーク設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="60ee2-129">Network Settings Schema</span></span>](index.md)
