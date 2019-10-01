---
title: authenticationModules の <clear> 要素 (ネットワーク設定)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/authenticationModules/clear
- http://schemas.microsoft.com/.NetConfiguration/v2.0#clear
helpviewer_keywords:
- clear element, authenticationModules
- <authenticationModules>, clear element
- <clear> element, authenticationModules
- authenticationModules, clear element
ms.assetid: dc522c45-4a80-4831-8955-f7b68a47edfd
ms.openlocfilehash: 052f7eef30500d37389585956728250a46b718a3
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2019
ms.locfileid: "71698397"
---
# <a name="clear-element-for-authenticationmodules-network-settings"></a><span data-ttu-id="c42dd-102">authenticationModules の \<clear> 要素 (ネットワーク設定)</span><span class="sxs-lookup"><span data-stu-id="c42dd-102">\<clear> Element for authenticationModules (Network Settings)</span></span>
<span data-ttu-id="c42dd-103">アプリケーションからすべての認証モジュールを削除します。</span><span class="sxs-lookup"><span data-stu-id="c42dd-103">Clears all authentication modules from the application.</span></span>  
  
[<span data-ttu-id="c42dd-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="c42dd-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="c42dd-105">&nbsp; @ no__t-1[ **@no__t 47 >** ](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="c42dd-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>  
<span data-ttu-id="c42dd-106">&nbsp; @ no__t-1 @ no__t @ no__t @-3[ **\<authenticationModules >** ](authenticationmodules-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="c42dd-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<authenticationModules>**](authenticationmodules-element-network-settings.md)</span></span>  
<span data-ttu-id="c42dd-107">&nbsp; @ no__t-1 @ no__t @ no__t @ no__t-5 **\<clear をクリア**します。</span><span class="sxs-lookup"><span data-stu-id="c42dd-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c42dd-108">構文</span><span class="sxs-lookup"><span data-stu-id="c42dd-108">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c42dd-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="c42dd-109">Attributes and Elements</span></span>  
 <span data-ttu-id="c42dd-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="c42dd-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c42dd-111">属性</span><span class="sxs-lookup"><span data-stu-id="c42dd-111">Attributes</span></span>  
 <span data-ttu-id="c42dd-112">[なし] :</span><span class="sxs-lookup"><span data-stu-id="c42dd-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="c42dd-113">子要素</span><span class="sxs-lookup"><span data-stu-id="c42dd-113">Child Elements</span></span>  
 <span data-ttu-id="c42dd-114">なし。</span><span class="sxs-lookup"><span data-stu-id="c42dd-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c42dd-115">親要素</span><span class="sxs-lookup"><span data-stu-id="c42dd-115">Parent Elements</span></span>  
  
|<span data-ttu-id="c42dd-116">**要素**</span><span class="sxs-lookup"><span data-stu-id="c42dd-116">**Element**</span></span>|<span data-ttu-id="c42dd-117">**[説明]**</span><span class="sxs-lookup"><span data-stu-id="c42dd-117">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="c42dd-118">authenticationModules</span><span class="sxs-lookup"><span data-stu-id="c42dd-118">authenticationModules</span></span>](authenticationmodules-element-network-settings.md)|<span data-ttu-id="c42dd-119">ネットワーク要求を認証するために使用するモジュールを指定します。</span><span class="sxs-lookup"><span data-stu-id="c42dd-119">Specifies modules used to authenticate network requests.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c42dd-120">コメント</span><span class="sxs-lookup"><span data-stu-id="c42dd-120">Remarks</span></span>  
 <span data-ttu-id="c42dd-121">@No__t-0 要素は、構成ファイルまたは構成階層の上位レベルに定義されているすべての認証モジュールを削除します。</span><span class="sxs-lookup"><span data-stu-id="c42dd-121">The `clear` element removes all authentication modules that were defined earlier in the configuration file or at a higher level in the configuration hierarchy.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="c42dd-122">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="c42dd-122">Configuration Files</span></span>  
 <span data-ttu-id="c42dd-123">この要素は、アプリケーション構成ファイルまたはマシン構成ファイル (Machine.config) で使用できます。</span><span class="sxs-lookup"><span data-stu-id="c42dd-123">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="c42dd-124">例</span><span class="sxs-lookup"><span data-stu-id="c42dd-124">Example</span></span>  
 <span data-ttu-id="c42dd-125">次の例では、構成されているすべての認証モジュールを削除します。</span><span class="sxs-lookup"><span data-stu-id="c42dd-125">The following example removes all configured authentication modules.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <authenticationModules>  
      <clear/>  
    </authenticationModules>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="c42dd-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="c42dd-126">See also</span></span>

- <xref:System.Net.IAuthenticationModule>
- <xref:System.Net.AuthenticationManager>
- [<span data-ttu-id="c42dd-127">ネットワーク設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="c42dd-127">Network Settings Schema</span></span>](index.md)
