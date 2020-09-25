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
ms.openlocfilehash: 0829f57d8dca91c2d895085dceaeea422229537c
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91176202"
---
# <a name="remove-element-for-authenticationmodules-network-settings"></a><span data-ttu-id="8ff78-102">authenticationModules の \<remove> 要素 (ネットワーク設定)</span><span class="sxs-lookup"><span data-stu-id="8ff78-102">\<remove> Element for authenticationModules (Network Settings)</span></span>

<span data-ttu-id="8ff78-103">アプリケーションから認証モジュールを削除します。</span><span class="sxs-lookup"><span data-stu-id="8ff78-103">Removes an authentication module from the application.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<authenticationModules>**](authenticationmodules-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**

## <a name="syntax"></a><span data-ttu-id="8ff78-104">構文</span><span class="sxs-lookup"><span data-stu-id="8ff78-104">Syntax</span></span>  
  
```xml  
<remove
   type="authentication module name"
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8ff78-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="8ff78-105">Attributes and Elements</span></span>  

 <span data-ttu-id="8ff78-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="8ff78-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8ff78-107">属性</span><span class="sxs-lookup"><span data-stu-id="8ff78-107">Attributes</span></span>  
  
|<span data-ttu-id="8ff78-108">**属性**</span><span class="sxs-lookup"><span data-stu-id="8ff78-108">**Attribute**</span></span>|<span data-ttu-id="8ff78-109">**説明**</span><span class="sxs-lookup"><span data-stu-id="8ff78-109">**Description**</span></span>|  
|-------------------|---------------------|  
|<span data-ttu-id="8ff78-110">**type**</span><span class="sxs-lookup"><span data-stu-id="8ff78-110">**type**</span></span>|<span data-ttu-id="8ff78-111">削除する認証モジュールの名前。</span><span class="sxs-lookup"><span data-stu-id="8ff78-111">The name of the authentication module to remove.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8ff78-112">子要素</span><span class="sxs-lookup"><span data-stu-id="8ff78-112">Child Elements</span></span>  

 <span data-ttu-id="8ff78-113">なし。</span><span class="sxs-lookup"><span data-stu-id="8ff78-113">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8ff78-114">親要素</span><span class="sxs-lookup"><span data-stu-id="8ff78-114">Parent Elements</span></span>  
  
|<span data-ttu-id="8ff78-115">**要素**</span><span class="sxs-lookup"><span data-stu-id="8ff78-115">**Element**</span></span>|<span data-ttu-id="8ff78-116">**説明**</span><span class="sxs-lookup"><span data-stu-id="8ff78-116">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="8ff78-117">authenticationModules</span><span class="sxs-lookup"><span data-stu-id="8ff78-117">authenticationModules</span></span>](authenticationmodules-element-network-settings.md)|<span data-ttu-id="8ff78-118">ネットワーク要求を認証するために使用するモジュールを指定します。</span><span class="sxs-lookup"><span data-stu-id="8ff78-118">Specifies modules used to authenticate network requests.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8ff78-119">解説</span><span class="sxs-lookup"><span data-stu-id="8ff78-119">Remarks</span></span>  

 <span data-ttu-id="8ff78-120">要素は、構成 `remove` ファイルまたは構成階層の上位レベルで定義された認証モジュールを削除します。</span><span class="sxs-lookup"><span data-stu-id="8ff78-120">The `remove` element removes authentication modules that were defined earlier in the configuration file or at a higher level in the configuration hierarchy.</span></span>  
  
 <span data-ttu-id="8ff78-121">属性の値は、 `type` 有効なクラス名である必要があります。</span><span class="sxs-lookup"><span data-stu-id="8ff78-121">The value for the `type` attribute should be a valid class name.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="8ff78-122">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="8ff78-122">Configuration Files</span></span>  

 <span data-ttu-id="8ff78-123">この要素は、アプリケーション構成ファイルまたはマシン構成ファイル (Machine.config) で使用できます。</span><span class="sxs-lookup"><span data-stu-id="8ff78-123">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="8ff78-124">例</span><span class="sxs-lookup"><span data-stu-id="8ff78-124">Example</span></span>  

 <span data-ttu-id="8ff78-125">次の例では、認証モジュールを削除します。</span><span class="sxs-lookup"><span data-stu-id="8ff78-125">The following example removes an authentication module.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <authenticationModules>  
      <remove type="System.Net.NtlmClient" />  
    </authenticationModules>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="8ff78-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="8ff78-126">See also</span></span>

- <xref:System.Net.IAuthenticationModule>
- <xref:System.Net.AuthenticationManager>
- [<span data-ttu-id="8ff78-127">ネットワーク設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="8ff78-127">Network Settings Schema</span></span>](index.md)
