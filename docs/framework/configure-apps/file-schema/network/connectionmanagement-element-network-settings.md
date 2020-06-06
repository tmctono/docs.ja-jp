---
title: <connectionManagement> 要素 (ネットワーク設定)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/connectionManagement
- http://schemas.microsoft.com/.NetConfiguration/v2.0#connectionManagement
helpviewer_keywords:
- <connectionManagement> element
- connectionManagement element
ms.assetid: bedccaab-12a2-4511-8f67-e961f249aec6
ms.openlocfilehash: 9f1e382bbbaad2cb95e2c33bbbdfb4c505378c9e
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "79154895"
---
# <a name="connectionmanagement-element-network-settings"></a><span data-ttu-id="cfcf8-102">\<connectionManagement> 要素 (ネットワーク設定)</span><span class="sxs-lookup"><span data-stu-id="cfcf8-102">\<connectionManagement> Element (Network Settings)</span></span>
<span data-ttu-id="cfcf8-103">ネットワーク ホストへの接続の最大数を指定します。</span><span class="sxs-lookup"><span data-stu-id="cfcf8-103">Specifies the maximum number of connections to a network host.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<connectionManagement>**

## <a name="syntax"></a><span data-ttu-id="cfcf8-104">構文</span><span class="sxs-lookup"><span data-stu-id="cfcf8-104">Syntax</span></span>  
  
```xml  
<connectionManagement>
</connectionManagement>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cfcf8-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="cfcf8-105">Attributes and Elements</span></span>  
 <span data-ttu-id="cfcf8-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="cfcf8-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cfcf8-107">属性</span><span class="sxs-lookup"><span data-stu-id="cfcf8-107">Attributes</span></span>  
 <span data-ttu-id="cfcf8-108">なし。</span><span class="sxs-lookup"><span data-stu-id="cfcf8-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="cfcf8-109">子要素</span><span class="sxs-lookup"><span data-stu-id="cfcf8-109">Child Elements</span></span>  
  
|<span data-ttu-id="cfcf8-110">**要素**</span><span class="sxs-lookup"><span data-stu-id="cfcf8-110">**Element**</span></span>|<span data-ttu-id="cfcf8-111">**説明**</span><span class="sxs-lookup"><span data-stu-id="cfcf8-111">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="cfcf8-112">add</span><span class="sxs-lookup"><span data-stu-id="cfcf8-112">add</span></span>](add-element-for-connectionmanagement-network-settings.md)|<span data-ttu-id="cfcf8-113">IP アドレスまたは DNS 名を接続管理リストに追加します。</span><span class="sxs-lookup"><span data-stu-id="cfcf8-113">Adds an IP address or DNS name to the connection management list.</span></span>|  
|[<span data-ttu-id="cfcf8-114">オフ</span><span class="sxs-lookup"><span data-stu-id="cfcf8-114">clear</span></span>](clear-element-for-connectionmanagement-network-settings.md)|<span data-ttu-id="cfcf8-115">接続管理の一覧をクリアします。</span><span class="sxs-lookup"><span data-stu-id="cfcf8-115">Clears the connection management list.</span></span>|  
|[<span data-ttu-id="cfcf8-116">remove</span><span class="sxs-lookup"><span data-stu-id="cfcf8-116">remove</span></span>](remove-element-for-connectionmanagement-network-settings.md)|<span data-ttu-id="cfcf8-117">接続管理リストから IP アドレスまたは DNS 名を削除します。</span><span class="sxs-lookup"><span data-stu-id="cfcf8-117">Removes an IP address or DNS name from the connection management list.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="cfcf8-118">親要素</span><span class="sxs-lookup"><span data-stu-id="cfcf8-118">Parent Elements</span></span>  
  
|<span data-ttu-id="cfcf8-119">**要素**</span><span class="sxs-lookup"><span data-stu-id="cfcf8-119">**Element**</span></span>|<span data-ttu-id="cfcf8-120">**説明**</span><span class="sxs-lookup"><span data-stu-id="cfcf8-120">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="cfcf8-121">system.net</span><span class="sxs-lookup"><span data-stu-id="cfcf8-121">system.net</span></span>](system-net-element-network-settings.md)|<span data-ttu-id="cfcf8-122">.NET Framework がネットワークに接続する方法を指定するための設定が含まれています。</span><span class="sxs-lookup"><span data-stu-id="cfcf8-122">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cfcf8-123">解説</span><span class="sxs-lookup"><span data-stu-id="cfcf8-123">Remarks</span></span>  
 <span data-ttu-id="cfcf8-124">要素は、 `connectionManagement` サーバーまたはサーバーのグループへの接続の最大数を定義します。</span><span class="sxs-lookup"><span data-stu-id="cfcf8-124">The `connectionManagement` element defines the maximum number of connections to a server or group of servers.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="cfcf8-125">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="cfcf8-125">Configuration Files</span></span>  
 <span data-ttu-id="cfcf8-126">この要素は、アプリケーション構成ファイルまたはマシン構成ファイル (Machine.config) で使用できます。</span><span class="sxs-lookup"><span data-stu-id="cfcf8-126">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="cfcf8-127">例</span><span class="sxs-lookup"><span data-stu-id="cfcf8-127">Example</span></span>  
 <span data-ttu-id="cfcf8-128">次の例では、サーバーへの4つの接続 `www.contoso.com` と、他のすべてのサーバーへの2つの接続を使用するようにアプリケーションを構成します。</span><span class="sxs-lookup"><span data-stu-id="cfcf8-128">The following example configures an application to use four connections to the server `www.contoso.com` and two connections to all other servers.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <connectionManagement>  
      <add address = "http://www.contoso.com" maxconnection = "4" />  
      <add address = "*" maxconnection = "2" />  
    </connectionManagement>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="cfcf8-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="cfcf8-129">See also</span></span>

- <xref:System.Net.ServicePoint>
- <xref:System.Net.ServicePointManager>
- [<span data-ttu-id="cfcf8-130">ネットワーク設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="cfcf8-130">Network Settings Schema</span></span>](index.md)
