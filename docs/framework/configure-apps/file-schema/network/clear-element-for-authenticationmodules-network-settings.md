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
ms.openlocfilehash: 6ac2287ba9b17727835d43a3e3b8876f210fb5c7
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91167328"
---
# <a name="clear-element-for-authenticationmodules-network-settings"></a><span data-ttu-id="abeac-102">authenticationModules の \<clear> 要素 (ネットワーク設定)</span><span class="sxs-lookup"><span data-stu-id="abeac-102">\<clear> Element for authenticationModules (Network Settings)</span></span>

<span data-ttu-id="abeac-103">アプリケーションからすべての認証モジュールを削除します。</span><span class="sxs-lookup"><span data-stu-id="abeac-103">Clears all authentication modules from the application.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<authenticationModules>**](authenticationmodules-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**

## <a name="syntax"></a><span data-ttu-id="abeac-104">構文</span><span class="sxs-lookup"><span data-stu-id="abeac-104">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="abeac-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="abeac-105">Attributes and Elements</span></span>  

 <span data-ttu-id="abeac-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="abeac-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="abeac-107">属性</span><span class="sxs-lookup"><span data-stu-id="abeac-107">Attributes</span></span>  

 <span data-ttu-id="abeac-108">なし。</span><span class="sxs-lookup"><span data-stu-id="abeac-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="abeac-109">子要素</span><span class="sxs-lookup"><span data-stu-id="abeac-109">Child Elements</span></span>  

 <span data-ttu-id="abeac-110">なし。</span><span class="sxs-lookup"><span data-stu-id="abeac-110">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="abeac-111">親要素</span><span class="sxs-lookup"><span data-stu-id="abeac-111">Parent Elements</span></span>  
  
|<span data-ttu-id="abeac-112">**要素**</span><span class="sxs-lookup"><span data-stu-id="abeac-112">**Element**</span></span>|<span data-ttu-id="abeac-113">**説明**</span><span class="sxs-lookup"><span data-stu-id="abeac-113">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="abeac-114">authenticationModules</span><span class="sxs-lookup"><span data-stu-id="abeac-114">authenticationModules</span></span>](authenticationmodules-element-network-settings.md)|<span data-ttu-id="abeac-115">ネットワーク要求を認証するために使用するモジュールを指定します。</span><span class="sxs-lookup"><span data-stu-id="abeac-115">Specifies modules used to authenticate network requests.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="abeac-116">解説</span><span class="sxs-lookup"><span data-stu-id="abeac-116">Remarks</span></span>  

 <span data-ttu-id="abeac-117">要素は、構成 `clear` ファイルまたは構成階層内の上位レベルで定義されたすべての認証モジュールを削除します。</span><span class="sxs-lookup"><span data-stu-id="abeac-117">The `clear` element removes all authentication modules that were defined earlier in the configuration file or at a higher level in the configuration hierarchy.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="abeac-118">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="abeac-118">Configuration Files</span></span>  

 <span data-ttu-id="abeac-119">この要素は、アプリケーション構成ファイルまたはマシン構成ファイル (Machine.config) で使用できます。</span><span class="sxs-lookup"><span data-stu-id="abeac-119">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="abeac-120">例</span><span class="sxs-lookup"><span data-stu-id="abeac-120">Example</span></span>  

 <span data-ttu-id="abeac-121">次の例では、構成されているすべての認証モジュールを削除します。</span><span class="sxs-lookup"><span data-stu-id="abeac-121">The following example removes all configured authentication modules.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <authenticationModules>  
      <clear/>  
    </authenticationModules>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="abeac-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="abeac-122">See also</span></span>

- <xref:System.Net.IAuthenticationModule>
- <xref:System.Net.AuthenticationManager>
- [<span data-ttu-id="abeac-123">ネットワーク設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="abeac-123">Network Settings Schema</span></span>](index.md)
