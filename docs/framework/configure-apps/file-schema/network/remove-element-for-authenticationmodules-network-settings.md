---
title: authenticationModules の <remove> 要素 (ネットワーク設定)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/authenticationModules/remove
- http://schemas.microsoft.com/.NetConfiguration/v2.0#remove
helpviewer_keywords:
- remove element, authenticationModules
- <authenticationModules>, remove element
- <remove> element, authenticationModules
- authenticationModules, remove element
ms.assetid: abf79949-b05c-465a-b51c-bbeda9a74173
ms.openlocfilehash: 2113b2b81ae347b398b0f25028dc6c361aec8447
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/14/2019
ms.locfileid: "74089178"
---
# <a name="remove-element-for-authenticationmodules-network-settings"></a><span data-ttu-id="0f9e2-102">authenticationModules の > 要素 (ネットワーク設定) を削除 \<には</span><span class="sxs-lookup"><span data-stu-id="0f9e2-102">\<remove> Element for authenticationModules (Network Settings)</span></span>
<span data-ttu-id="0f9e2-103">アプリケーションから認証モジュールを削除します。</span><span class="sxs-lookup"><span data-stu-id="0f9e2-103">Removes an authentication module from the application.</span></span>  

<span data-ttu-id="0f9e2-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="0f9e2-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="0f9e2-105">&nbsp;&nbsp;[ **\<system. net >** ](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="0f9e2-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>\
<span data-ttu-id="0f9e2-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<authenticationModules >** ](authenticationmodules-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="0f9e2-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<authenticationModules>**](authenticationmodules-element-network-settings.md)</span></span>\
<span data-ttu-id="0f9e2-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**削除**></span><span class="sxs-lookup"><span data-stu-id="0f9e2-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**</span></span>

## <a name="syntax"></a><span data-ttu-id="0f9e2-108">構文</span><span class="sxs-lookup"><span data-stu-id="0f9e2-108">Syntax</span></span>  
  
```xml  
<remove   
   type="authentication module name"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0f9e2-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="0f9e2-109">Attributes and Elements</span></span>  
 <span data-ttu-id="0f9e2-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="0f9e2-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0f9e2-111">属性</span><span class="sxs-lookup"><span data-stu-id="0f9e2-111">Attributes</span></span>  
  
|<span data-ttu-id="0f9e2-112">**属性**</span><span class="sxs-lookup"><span data-stu-id="0f9e2-112">**Attribute**</span></span>|<span data-ttu-id="0f9e2-113">**説明**</span><span class="sxs-lookup"><span data-stu-id="0f9e2-113">**Description**</span></span>|  
|-------------------|---------------------|  
|<span data-ttu-id="0f9e2-114">**type**</span><span class="sxs-lookup"><span data-stu-id="0f9e2-114">**type**</span></span>|<span data-ttu-id="0f9e2-115">削除する認証モジュールの名前。</span><span class="sxs-lookup"><span data-stu-id="0f9e2-115">The name of the authentication module to remove.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0f9e2-116">子要素</span><span class="sxs-lookup"><span data-stu-id="0f9e2-116">Child Elements</span></span>  
 <span data-ttu-id="0f9e2-117">なし。</span><span class="sxs-lookup"><span data-stu-id="0f9e2-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0f9e2-118">親要素</span><span class="sxs-lookup"><span data-stu-id="0f9e2-118">Parent Elements</span></span>  
  
|<span data-ttu-id="0f9e2-119">**要素**</span><span class="sxs-lookup"><span data-stu-id="0f9e2-119">**Element**</span></span>|<span data-ttu-id="0f9e2-120">**説明**</span><span class="sxs-lookup"><span data-stu-id="0f9e2-120">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="0f9e2-121">authenticationModules</span><span class="sxs-lookup"><span data-stu-id="0f9e2-121">authenticationModules</span></span>](authenticationmodules-element-network-settings.md)|<span data-ttu-id="0f9e2-122">ネットワーク要求を認証するために使用するモジュールを指定します。</span><span class="sxs-lookup"><span data-stu-id="0f9e2-122">Specifies modules used to authenticate network requests.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0f9e2-123">Remarks</span><span class="sxs-lookup"><span data-stu-id="0f9e2-123">Remarks</span></span>  
 <span data-ttu-id="0f9e2-124">`remove` 要素は、構成ファイルまたは構成階層の上位レベルで定義された認証モジュールを削除します。</span><span class="sxs-lookup"><span data-stu-id="0f9e2-124">The `remove` element removes authentication modules that were defined earlier in the configuration file or at a higher level in the configuration hierarchy.</span></span>  
  
 <span data-ttu-id="0f9e2-125">`type` 属性の値は、有効なクラス名である必要があります。</span><span class="sxs-lookup"><span data-stu-id="0f9e2-125">The value for the `type` attribute should be a valid class name.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="0f9e2-126">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="0f9e2-126">Configuration Files</span></span>  
 <span data-ttu-id="0f9e2-127">この要素は、アプリケーション構成ファイルまたはマシン構成ファイル (Machine.config) で使用できます。</span><span class="sxs-lookup"><span data-stu-id="0f9e2-127">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="0f9e2-128">例</span><span class="sxs-lookup"><span data-stu-id="0f9e2-128">Example</span></span>  
 <span data-ttu-id="0f9e2-129">次の例では、認証モジュールを削除します。</span><span class="sxs-lookup"><span data-stu-id="0f9e2-129">The following example removes an authentication module.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <authenticationModules>  
      <remove type="System.Net.NtlmClient" />  
    </authenticationModules>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="0f9e2-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="0f9e2-130">See also</span></span>

- <xref:System.Net.IAuthenticationModule>
- <xref:System.Net.AuthenticationManager>
- [<span data-ttu-id="0f9e2-131">ネットワーク設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="0f9e2-131">Network Settings Schema</span></span>](index.md)
