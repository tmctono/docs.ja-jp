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
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "79154778"
---
# <a name="remove-element-for-authenticationmodules-network-settings"></a><span data-ttu-id="8b403-102">authenticationModules の \<remove> 要素 (ネットワーク設定)</span><span class="sxs-lookup"><span data-stu-id="8b403-102">\<remove> Element for authenticationModules (Network Settings)</span></span>
<span data-ttu-id="8b403-103">アプリケーションから認証モジュールを削除します。</span><span class="sxs-lookup"><span data-stu-id="8b403-103">Removes an authentication module from the application.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<authenticationModules>**](authenticationmodules-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**

## <a name="syntax"></a><span data-ttu-id="8b403-104">構文</span><span class="sxs-lookup"><span data-stu-id="8b403-104">Syntax</span></span>  
  
```xml  
<remove
   type="authentication module name"
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8b403-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="8b403-105">Attributes and Elements</span></span>  
 <span data-ttu-id="8b403-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="8b403-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8b403-107">属性</span><span class="sxs-lookup"><span data-stu-id="8b403-107">Attributes</span></span>  
  
|<span data-ttu-id="8b403-108">**属性**</span><span class="sxs-lookup"><span data-stu-id="8b403-108">**Attribute**</span></span>|<span data-ttu-id="8b403-109">**説明**</span><span class="sxs-lookup"><span data-stu-id="8b403-109">**Description**</span></span>|  
|-------------------|---------------------|  
|<span data-ttu-id="8b403-110">**type**</span><span class="sxs-lookup"><span data-stu-id="8b403-110">**type**</span></span>|<span data-ttu-id="8b403-111">削除する認証モジュールの名前。</span><span class="sxs-lookup"><span data-stu-id="8b403-111">The name of the authentication module to remove.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8b403-112">子要素</span><span class="sxs-lookup"><span data-stu-id="8b403-112">Child Elements</span></span>  
 <span data-ttu-id="8b403-113">なし。</span><span class="sxs-lookup"><span data-stu-id="8b403-113">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8b403-114">親要素</span><span class="sxs-lookup"><span data-stu-id="8b403-114">Parent Elements</span></span>  
  
|<span data-ttu-id="8b403-115">**要素**</span><span class="sxs-lookup"><span data-stu-id="8b403-115">**Element**</span></span>|<span data-ttu-id="8b403-116">**説明**</span><span class="sxs-lookup"><span data-stu-id="8b403-116">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="8b403-117">authenticationModules</span><span class="sxs-lookup"><span data-stu-id="8b403-117">authenticationModules</span></span>](authenticationmodules-element-network-settings.md)|<span data-ttu-id="8b403-118">ネットワーク要求を認証するために使用するモジュールを指定します。</span><span class="sxs-lookup"><span data-stu-id="8b403-118">Specifies modules used to authenticate network requests.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8b403-119">解説</span><span class="sxs-lookup"><span data-stu-id="8b403-119">Remarks</span></span>  
 <span data-ttu-id="8b403-120">要素は、構成 `remove` ファイルまたは構成階層の上位レベルで定義された認証モジュールを削除します。</span><span class="sxs-lookup"><span data-stu-id="8b403-120">The `remove` element removes authentication modules that were defined earlier in the configuration file or at a higher level in the configuration hierarchy.</span></span>  
  
 <span data-ttu-id="8b403-121">属性の値は、 `type` 有効なクラス名である必要があります。</span><span class="sxs-lookup"><span data-stu-id="8b403-121">The value for the `type` attribute should be a valid class name.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="8b403-122">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="8b403-122">Configuration Files</span></span>  
 <span data-ttu-id="8b403-123">この要素は、アプリケーション構成ファイルまたはマシン構成ファイル (Machine.config) で使用できます。</span><span class="sxs-lookup"><span data-stu-id="8b403-123">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="8b403-124">例</span><span class="sxs-lookup"><span data-stu-id="8b403-124">Example</span></span>  
 <span data-ttu-id="8b403-125">次の例では、認証モジュールを削除します。</span><span class="sxs-lookup"><span data-stu-id="8b403-125">The following example removes an authentication module.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <authenticationModules>  
      <remove type="System.Net.NtlmClient" />  
    </authenticationModules>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="8b403-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="8b403-126">See also</span></span>

- <xref:System.Net.IAuthenticationModule>
- <xref:System.Net.AuthenticationManager>
- [<span data-ttu-id="8b403-127">ネットワーク設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="8b403-127">Network Settings Schema</span></span>](index.md)
