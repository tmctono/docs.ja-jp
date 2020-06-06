---
title: connectionManagement の <remove> 要素 (ネットワーク設定)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/connectionManagement/remove
- http://schemas.microsoft.com/.NetConfiguration/v2.0#remove
helpviewer_keywords:
- connectionManagement, remove element
- <remove> element, connectionManagement
- <connectionManagement>, remove element
- remove element, connectionManagement
ms.assetid: 94b81775-5a22-4975-8c47-8620c40c3f35
ms.openlocfilehash: 39ce85c3c15a2d4bdfce801a35e9ca088bd5091b
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "79154739"
---
# <a name="remove-element-for-connectionmanagement-network-settings"></a><span data-ttu-id="53b36-102">connectionManagement の \<remove> 要素 (ネットワーク設定)</span><span class="sxs-lookup"><span data-stu-id="53b36-102">\<remove> Element for connectionManagement (Network Settings)</span></span>
<span data-ttu-id="53b36-103">接続管理リストから IP アドレスまたは DNS 名を削除します。</span><span class="sxs-lookup"><span data-stu-id="53b36-103">Removes an IP address or DNS name from the connection management list.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<connectionManagement>**](connectionmanagement-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**

## <a name="syntax"></a><span data-ttu-id="53b36-104">構文</span><span class="sxs-lookup"><span data-stu-id="53b36-104">Syntax</span></span>  
  
```xml  
<remove
  address="server name or IP address"
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="53b36-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="53b36-105">Attributes and Elements</span></span>  
 <span data-ttu-id="53b36-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="53b36-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="53b36-107">属性</span><span class="sxs-lookup"><span data-stu-id="53b36-107">Attributes</span></span>  
  
|<span data-ttu-id="53b36-108">**属性**</span><span class="sxs-lookup"><span data-stu-id="53b36-108">**Attribute**</span></span>|<span data-ttu-id="53b36-109">**説明**</span><span class="sxs-lookup"><span data-stu-id="53b36-109">**Description**</span></span>|  
|-------------------|---------------------|  
|`address`|<span data-ttu-id="53b36-110">IP アドレスまたは DNS 名。</span><span class="sxs-lookup"><span data-stu-id="53b36-110">An IP address or DNS name.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="53b36-111">子要素</span><span class="sxs-lookup"><span data-stu-id="53b36-111">Child Elements</span></span>  
 <span data-ttu-id="53b36-112">なし。</span><span class="sxs-lookup"><span data-stu-id="53b36-112">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="53b36-113">親要素</span><span class="sxs-lookup"><span data-stu-id="53b36-113">Parent Elements</span></span>  
  
|<span data-ttu-id="53b36-114">**要素**</span><span class="sxs-lookup"><span data-stu-id="53b36-114">**Element**</span></span>|<span data-ttu-id="53b36-115">**説明**</span><span class="sxs-lookup"><span data-stu-id="53b36-115">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="53b36-116">connectionManagement</span><span class="sxs-lookup"><span data-stu-id="53b36-116">connectionManagement</span></span>](connectionmanagement-element-network-settings.md)|<span data-ttu-id="53b36-117">ネットワーク ホストへの接続の最大数を指定します。</span><span class="sxs-lookup"><span data-stu-id="53b36-117">Specifies the maximum number of connections to a network host.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="53b36-118">解説</span><span class="sxs-lookup"><span data-stu-id="53b36-118">Remarks</span></span>  
 <span data-ttu-id="53b36-119">要素は、 `remove` 指定されたサーバーの接続管理リストのエントリを削除します。</span><span class="sxs-lookup"><span data-stu-id="53b36-119">The `remove` element removes the connection management list entry for the specified server.</span></span>  
  
 <span data-ttu-id="53b36-120">属性の値は、 `address` 有効な IP アドレスまたはホスト名である必要があります。</span><span class="sxs-lookup"><span data-stu-id="53b36-120">The value of the `address` attribute should be a valid IP address or host name.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="53b36-121">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="53b36-121">Configuration Files</span></span>  
 <span data-ttu-id="53b36-122">この要素は、アプリケーション構成ファイルまたはマシン構成ファイル (Machine.config) で使用できます。</span><span class="sxs-lookup"><span data-stu-id="53b36-122">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="53b36-123">例</span><span class="sxs-lookup"><span data-stu-id="53b36-123">Example</span></span>  
 <span data-ttu-id="53b36-124">次の例では、サーバーに対する接続管理の一覧のエントリをすべて削除し、 `www.adventure-works.com` サーバーへの接続を4つ、 `www.contoso.com` 他のすべてのサーバーへの接続を2つ使用するようにアプリケーションを構成します。</span><span class="sxs-lookup"><span data-stu-id="53b36-124">The following example removes any connection management list entries for the server `www.adventure-works.com` and then configures an application to use four connections to the server `www.contoso.com` and two connections to all other servers.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <connectionManagement>  
      <remove address="http://www.adventure-works.com" />  
      <add address="http://www.contoso.com" maxconnection="4" />  
      <add address="*" maxconnection="2" />  
    </connectionManagement>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="53b36-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="53b36-125">See also</span></span>

- <xref:System.Net.ServicePoint>
- <xref:System.Net.ServicePointManager>
- [<span data-ttu-id="53b36-126">ネットワーク設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="53b36-126">Network Settings Schema</span></span>](index.md)
