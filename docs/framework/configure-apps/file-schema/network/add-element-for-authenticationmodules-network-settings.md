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
ms.openlocfilehash: 4181a045079bdb455a63ebda722dd6b0daf33c4d
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "79155116"
---
# <a name="add-element-for-authenticationmodules-network-settings"></a><span data-ttu-id="5cae2-102">authenticationModules の \<add> 要素 (ネットワーク設定)</span><span class="sxs-lookup"><span data-stu-id="5cae2-102">\<add> Element for authenticationModules (Network Settings)</span></span>
<span data-ttu-id="5cae2-103">アプリケーションに認証モジュールを追加します。</span><span class="sxs-lookup"><span data-stu-id="5cae2-103">Adds an authentication module to the application.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<authenticationModules>**](authenticationmodules-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**

## <a name="syntax"></a><span data-ttu-id="5cae2-104">構文</span><span class="sxs-lookup"><span data-stu-id="5cae2-104">Syntax</span></span>  
  
```xml  
<add
  type="type_fullname, assembly_fullname"
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5cae2-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="5cae2-105">Attributes and Elements</span></span>  
 <span data-ttu-id="5cae2-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="5cae2-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5cae2-107">属性</span><span class="sxs-lookup"><span data-stu-id="5cae2-107">Attributes</span></span>  
  
|<span data-ttu-id="5cae2-108">**属性**</span><span class="sxs-lookup"><span data-stu-id="5cae2-108">**Attribute**</span></span>|<span data-ttu-id="5cae2-109">**説明**</span><span class="sxs-lookup"><span data-stu-id="5cae2-109">**Description**</span></span>|  
|-------------------|---------------------|  
|`type`|<span data-ttu-id="5cae2-110">コンマで区切られた、完全修飾型名 (プロパティによって示され <xref:System.Type.FullName%2A> ます) とアセンブリ名 (プロパティによって示され <xref:System.Reflection.Assembly.FullName%2A> ます)。</span><span class="sxs-lookup"><span data-stu-id="5cae2-110">The fully qualified type name (indicated by the <xref:System.Type.FullName%2A> property) and the assembly name (indicated by the <xref:System.Reflection.Assembly.FullName%2A> property), separated by a comma.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5cae2-111">子要素</span><span class="sxs-lookup"><span data-stu-id="5cae2-111">Child Elements</span></span>  
 <span data-ttu-id="5cae2-112">なし。</span><span class="sxs-lookup"><span data-stu-id="5cae2-112">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5cae2-113">親要素</span><span class="sxs-lookup"><span data-stu-id="5cae2-113">Parent Elements</span></span>  
  
|<span data-ttu-id="5cae2-114">**要素**</span><span class="sxs-lookup"><span data-stu-id="5cae2-114">**Element**</span></span>|<span data-ttu-id="5cae2-115">**説明**</span><span class="sxs-lookup"><span data-stu-id="5cae2-115">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="5cae2-116">authenticationModules</span><span class="sxs-lookup"><span data-stu-id="5cae2-116">authenticationModules</span></span>](authenticationmodules-element-network-settings.md)|<span data-ttu-id="5cae2-117">ネットワーク要求を認証するために使用するモジュールを指定します。</span><span class="sxs-lookup"><span data-stu-id="5cae2-117">Specifies modules used to authenticate network requests.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5cae2-118">解説</span><span class="sxs-lookup"><span data-stu-id="5cae2-118">Remarks</span></span>  
 <span data-ttu-id="5cae2-119">要素は、 `add` 登録されている認証モジュールの一覧の末尾に認証モジュールを追加します。</span><span class="sxs-lookup"><span data-stu-id="5cae2-119">The `add` element adds an authentication module to the end of the list of registered authentication modules.</span></span> <span data-ttu-id="5cae2-120">認証モジュールは、一覧に追加された順序で呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="5cae2-120">Authentication modules are called in the order in which they were added to the list.</span></span>  
  
 <span data-ttu-id="5cae2-121">属性の値は、 `type` 有効な型名と、それに対応するアセンブリ名をコンマで区切って指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5cae2-121">The value for the `type` attribute should be a valid type name and corresponding assembly name, separated by a comma.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="5cae2-122">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="5cae2-122">Configuration Files</span></span>  
 <span data-ttu-id="5cae2-123">この要素は、アプリケーション構成ファイルまたはマシン構成ファイル (Machine.config) で使用できます。</span><span class="sxs-lookup"><span data-stu-id="5cae2-123">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="5cae2-124">例</span><span class="sxs-lookup"><span data-stu-id="5cae2-124">Example</span></span>  
 <span data-ttu-id="5cae2-125">次の例では、既定の認証モジュールを有効にします。</span><span class="sxs-lookup"><span data-stu-id="5cae2-125">The following example enables the default authentication modules.</span></span> <span data-ttu-id="5cae2-126">Version および PublicKeyToken の値は、指定されたモジュールの正しい値に置き換える必要があります。</span><span class="sxs-lookup"><span data-stu-id="5cae2-126">You should replace the values for Version and PublicKeyToken with the correct values for the specified module.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="5cae2-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="5cae2-127">See also</span></span>

- <xref:System.Net.IAuthenticationModule>
- <xref:System.Net.AuthenticationManager>
- [<span data-ttu-id="5cae2-128">ネットワーク設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="5cae2-128">Network Settings Schema</span></span>](index.md)
