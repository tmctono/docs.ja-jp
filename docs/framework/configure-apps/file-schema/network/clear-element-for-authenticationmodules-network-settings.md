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
ms.openlocfilehash: e3abd1b4c76ebda885703ccf961d58657b582f19
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "74087509"
---
# <a name="clear-element-for-authenticationmodules-network-settings"></a><span data-ttu-id="b6912-102">authenticationModules の \<clear> 要素 (ネットワーク設定)</span><span class="sxs-lookup"><span data-stu-id="b6912-102">\<clear> Element for authenticationModules (Network Settings)</span></span>
<span data-ttu-id="b6912-103">アプリケーションからすべての認証モジュールを削除します。</span><span class="sxs-lookup"><span data-stu-id="b6912-103">Clears all authentication modules from the application.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<authenticationModules>**](authenticationmodules-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**

## <a name="syntax"></a><span data-ttu-id="b6912-104">構文</span><span class="sxs-lookup"><span data-stu-id="b6912-104">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b6912-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="b6912-105">Attributes and Elements</span></span>  
 <span data-ttu-id="b6912-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="b6912-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b6912-107">属性</span><span class="sxs-lookup"><span data-stu-id="b6912-107">Attributes</span></span>  
 <span data-ttu-id="b6912-108">なし。</span><span class="sxs-lookup"><span data-stu-id="b6912-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="b6912-109">子要素</span><span class="sxs-lookup"><span data-stu-id="b6912-109">Child Elements</span></span>  
 <span data-ttu-id="b6912-110">[なし] :</span><span class="sxs-lookup"><span data-stu-id="b6912-110">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b6912-111">親要素</span><span class="sxs-lookup"><span data-stu-id="b6912-111">Parent Elements</span></span>  
  
|<span data-ttu-id="b6912-112">**要素**</span><span class="sxs-lookup"><span data-stu-id="b6912-112">**Element**</span></span>|<span data-ttu-id="b6912-113">**説明**</span><span class="sxs-lookup"><span data-stu-id="b6912-113">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="b6912-114">authenticationModules</span><span class="sxs-lookup"><span data-stu-id="b6912-114">authenticationModules</span></span>](authenticationmodules-element-network-settings.md)|<span data-ttu-id="b6912-115">ネットワーク要求を認証するために使用するモジュールを指定します。</span><span class="sxs-lookup"><span data-stu-id="b6912-115">Specifies modules used to authenticate network requests.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b6912-116">解説</span><span class="sxs-lookup"><span data-stu-id="b6912-116">Remarks</span></span>  
 <span data-ttu-id="b6912-117">要素は、構成 `clear` ファイルまたは構成階層内の上位レベルで定義されたすべての認証モジュールを削除します。</span><span class="sxs-lookup"><span data-stu-id="b6912-117">The `clear` element removes all authentication modules that were defined earlier in the configuration file or at a higher level in the configuration hierarchy.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="b6912-118">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="b6912-118">Configuration Files</span></span>  
 <span data-ttu-id="b6912-119">この要素は、アプリケーション構成ファイルまたはマシン構成ファイル (Machine.config) で使用できます。</span><span class="sxs-lookup"><span data-stu-id="b6912-119">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b6912-120">例</span><span class="sxs-lookup"><span data-stu-id="b6912-120">Example</span></span>  
 <span data-ttu-id="b6912-121">次の例では、構成されているすべての認証モジュールを削除します。</span><span class="sxs-lookup"><span data-stu-id="b6912-121">The following example removes all configured authentication modules.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <authenticationModules>  
      <clear/>  
    </authenticationModules>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="b6912-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="b6912-122">See also</span></span>

- <xref:System.Net.IAuthenticationModule>
- <xref:System.Net.AuthenticationManager>
- [<span data-ttu-id="b6912-123">ネットワーク設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="b6912-123">Network Settings Schema</span></span>](index.md)
