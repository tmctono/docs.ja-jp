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
ms.openlocfilehash: d171fea193bbae068e69b8976abb8e56a5623f02
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154778"
---
# <a name="remove-element-for-authenticationmodules-network-settings"></a><span data-ttu-id="ba667-102">\<>認証の要素を削除するモジュール (ネットワーク設定)</span><span class="sxs-lookup"><span data-stu-id="ba667-102">\<remove> Element for authenticationModules (Network Settings)</span></span>
<span data-ttu-id="ba667-103">アプリケーションから認証モジュールを削除します。</span><span class="sxs-lookup"><span data-stu-id="ba667-103">Removes an authentication module from the application.</span></span>  

<span data-ttu-id="ba667-104">[**\<構成>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="ba667-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="ba667-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="ba667-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>\
<span data-ttu-id="ba667-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<認証モジュール>**](authenticationmodules-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="ba667-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<authenticationModules>**](authenticationmodules-element-network-settings.md)</span></span>\
<span data-ttu-id="ba667-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<>を削除する**</span><span class="sxs-lookup"><span data-stu-id="ba667-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**</span></span>

## <a name="syntax"></a><span data-ttu-id="ba667-108">構文</span><span class="sxs-lookup"><span data-stu-id="ba667-108">Syntax</span></span>  
  
```xml  
<remove
   type="authentication module name"
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ba667-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="ba667-109">Attributes and Elements</span></span>  
 <span data-ttu-id="ba667-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="ba667-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ba667-111">属性</span><span class="sxs-lookup"><span data-stu-id="ba667-111">Attributes</span></span>  
  
|<span data-ttu-id="ba667-112">**属性**</span><span class="sxs-lookup"><span data-stu-id="ba667-112">**Attribute**</span></span>|<span data-ttu-id="ba667-113">**説明**</span><span class="sxs-lookup"><span data-stu-id="ba667-113">**Description**</span></span>|  
|-------------------|---------------------|  
|<span data-ttu-id="ba667-114">**型**</span><span class="sxs-lookup"><span data-stu-id="ba667-114">**type**</span></span>|<span data-ttu-id="ba667-115">削除する認証モジュールの名前。</span><span class="sxs-lookup"><span data-stu-id="ba667-115">The name of the authentication module to remove.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ba667-116">子要素</span><span class="sxs-lookup"><span data-stu-id="ba667-116">Child Elements</span></span>  
 <span data-ttu-id="ba667-117">[なし] :</span><span class="sxs-lookup"><span data-stu-id="ba667-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ba667-118">親要素</span><span class="sxs-lookup"><span data-stu-id="ba667-118">Parent Elements</span></span>  
  
|<span data-ttu-id="ba667-119">**Element**</span><span class="sxs-lookup"><span data-stu-id="ba667-119">**Element**</span></span>|<span data-ttu-id="ba667-120">**説明**</span><span class="sxs-lookup"><span data-stu-id="ba667-120">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="ba667-121">authenticationModules</span><span class="sxs-lookup"><span data-stu-id="ba667-121">authenticationModules</span></span>](authenticationmodules-element-network-settings.md)|<span data-ttu-id="ba667-122">ネットワーク要求の認証に使用するモジュールを指定します。</span><span class="sxs-lookup"><span data-stu-id="ba667-122">Specifies modules used to authenticate network requests.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ba667-123">解説</span><span class="sxs-lookup"><span data-stu-id="ba667-123">Remarks</span></span>  
 <span data-ttu-id="ba667-124">この`remove`要素は、構成ファイルで以前に定義された認証モジュール、または構成階層の上位レベルで定義された認証モジュールを削除します。</span><span class="sxs-lookup"><span data-stu-id="ba667-124">The `remove` element removes authentication modules that were defined earlier in the configuration file or at a higher level in the configuration hierarchy.</span></span>  
  
 <span data-ttu-id="ba667-125">属性の`type`値は、有効なクラス名である必要があります。</span><span class="sxs-lookup"><span data-stu-id="ba667-125">The value for the `type` attribute should be a valid class name.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="ba667-126">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="ba667-126">Configuration Files</span></span>  
 <span data-ttu-id="ba667-127">この要素は、アプリケーション構成ファイルまたはマシン構成ファイル (Machine.config) で使用できます。</span><span class="sxs-lookup"><span data-stu-id="ba667-127">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ba667-128">例</span><span class="sxs-lookup"><span data-stu-id="ba667-128">Example</span></span>  
 <span data-ttu-id="ba667-129">認証モジュールを削除する例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="ba667-129">The following example removes an authentication module.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <authenticationModules>  
      <remove type="System.Net.NtlmClient" />  
    </authenticationModules>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="ba667-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="ba667-130">See also</span></span>

- <xref:System.Net.IAuthenticationModule>
- <xref:System.Net.AuthenticationManager>
- [<span data-ttu-id="ba667-131">ネットワーク設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="ba667-131">Network Settings Schema</span></span>](index.md)
