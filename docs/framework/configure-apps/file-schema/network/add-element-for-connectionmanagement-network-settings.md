---
title: connectionManagement の <add> 要素 (ネットワーク設定)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#add
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/connectionManagement/add
helpviewer_keywords:
- <add> element, connectionManagement
- <connectionManagement>, add element
- add element, connectionManagement
- connectionManagement, add element
ms.assetid: 856bf57d-1c63-46c7-a178-03d97b0a4149
ms.openlocfilehash: 05e4a1bc42dc39c7d2b56e30c98bdeefd31e4416
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91149479"
---
# <a name="add-element-for-connectionmanagement-network-settings"></a><span data-ttu-id="2b402-102">connectionManagement の \<add> 要素 (ネットワーク設定)</span><span class="sxs-lookup"><span data-stu-id="2b402-102">\<add> Element for connectionManagement (Network Settings)</span></span>

<span data-ttu-id="2b402-103">IP アドレスまたは DNS 名を接続管理リストに追加します。</span><span class="sxs-lookup"><span data-stu-id="2b402-103">Adds an IP address or DNS name to the connection management list.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<connectionManagement>**](connectionmanagement-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**

## <a name="syntax"></a><span data-ttu-id="2b402-104">構文</span><span class="sxs-lookup"><span data-stu-id="2b402-104">Syntax</span></span>  
  
```xml  
<add
  address="address expression"
  maxconnection="integer"
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2b402-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="2b402-105">Attributes and Elements</span></span>  

 <span data-ttu-id="2b402-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="2b402-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2b402-107">属性</span><span class="sxs-lookup"><span data-stu-id="2b402-107">Attributes</span></span>  
  
|<span data-ttu-id="2b402-108">**属性**</span><span class="sxs-lookup"><span data-stu-id="2b402-108">**Attribute**</span></span>|<span data-ttu-id="2b402-109">**説明**</span><span class="sxs-lookup"><span data-stu-id="2b402-109">**Description**</span></span>|  
|-------------------|---------------------|  
|`address`|<span data-ttu-id="2b402-110">IP アドレスまたは DNS 名を記述する文字列。</span><span class="sxs-lookup"><span data-stu-id="2b402-110">A string describing an IP address or DNS name.</span></span>|  
|`maxconnection`|<span data-ttu-id="2b402-111">サーバーに対して許可される接続の最大数。</span><span class="sxs-lookup"><span data-stu-id="2b402-111">The maximum number of connections allowed to a server.</span></span> <span data-ttu-id="2b402-112">値が指定されていない場合、既定値は 2 です。</span><span class="sxs-lookup"><span data-stu-id="2b402-112">If not supplied, the default is 2.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2b402-113">子要素</span><span class="sxs-lookup"><span data-stu-id="2b402-113">Child Elements</span></span>  

 <span data-ttu-id="2b402-114">なし。</span><span class="sxs-lookup"><span data-stu-id="2b402-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2b402-115">親要素</span><span class="sxs-lookup"><span data-stu-id="2b402-115">Parent Elements</span></span>  
  
|<span data-ttu-id="2b402-116">**要素**</span><span class="sxs-lookup"><span data-stu-id="2b402-116">**Element**</span></span>|<span data-ttu-id="2b402-117">**説明**</span><span class="sxs-lookup"><span data-stu-id="2b402-117">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="2b402-118">connectionManagement</span><span class="sxs-lookup"><span data-stu-id="2b402-118">connectionManagement</span></span>](connectionmanagement-element-network-settings.md)|<span data-ttu-id="2b402-119">ネットワーク ホストへの接続の最大数を指定します。</span><span class="sxs-lookup"><span data-stu-id="2b402-119">Specifies the maximum number of connections to a network host.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2b402-120">解説</span><span class="sxs-lookup"><span data-stu-id="2b402-120">Remarks</span></span>  

 <span data-ttu-id="2b402-121">`address` 属性の値は、すべての接続を示すアスタリスク、または形式が `<schema>://<idn_hostname>[:<port>]` の文字列である必要があります。</span><span class="sxs-lookup"><span data-stu-id="2b402-121">The value of the `address` attribute should be either an asterisk to indicate all connections, or a string of the form `<schema>://<idn_hostname>[:<port>]`.</span></span>  
  
 <span data-ttu-id="2b402-122">HTTP API に渡される URI に Unicode が含まれる場合、punicode 文字列を返す可能性がある <xref:System.Uri.DnsSafeHost%2A> を使用して名前が内部的に変換されます (動作は現行 IDN 構成によって異なる)。</span><span class="sxs-lookup"><span data-stu-id="2b402-122">If the URI passed to any HTTP APIs contains Unicode, the name will be converted internally using <xref:System.Uri.DnsSafeHost%2A> which might return a punicode string (behavior dependent on the current IDN configuration).</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="2b402-123">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="2b402-123">Configuration Files</span></span>  

 <span data-ttu-id="2b402-124">この要素は、アプリケーション構成ファイルまたはマシン構成ファイル (Machine.config) で使用できます。</span><span class="sxs-lookup"><span data-stu-id="2b402-124">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="2b402-125">例</span><span class="sxs-lookup"><span data-stu-id="2b402-125">Example</span></span>  

 <span data-ttu-id="2b402-126">次の例では、サーバーへの4つの接続 `www.contoso.com` と、他のすべてのサーバーへの2つの接続を使用するようにアプリケーションを構成します。</span><span class="sxs-lookup"><span data-stu-id="2b402-126">The following example configures an application to use four connections to the server `www.contoso.com` and two connections to all other servers.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <connectionManagement>  
      <add address="http://www.contoso.com" maxconnection="4" />  
      <add address="*" maxconnection="2" />  
    </connectionManagement>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="2b402-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="2b402-127">See also</span></span>

- <xref:System.Net.ServicePoint>
- <xref:System.Net.ServicePointManager>
- [<span data-ttu-id="2b402-128">ネットワーク設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="2b402-128">Network Settings Schema</span></span>](index.md)
