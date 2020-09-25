---
title: <connectionManagement> 要素 (ネットワーク設定)
description: <connectionManagement>ネットワーク設定要素は、.NET Framework 内のネットワークホストへの接続の最大数を指定します。
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/connectionManagement
- http://schemas.microsoft.com/.NetConfiguration/v2.0#connectionManagement
helpviewer_keywords:
- <connectionManagement> element
- connectionManagement element
ms.assetid: bedccaab-12a2-4511-8f67-e961f249aec6
ms.openlocfilehash: 52b780c739a00cb53694b547ee1a33c1b5d98c86
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91167315"
---
# <a name="connectionmanagement-element-network-settings"></a><span data-ttu-id="1a560-103">\<connectionManagement> 要素 (ネットワーク設定)</span><span class="sxs-lookup"><span data-stu-id="1a560-103">\<connectionManagement> Element (Network Settings)</span></span>

<span data-ttu-id="1a560-104">ネットワーク ホストへの接続の最大数を指定します。</span><span class="sxs-lookup"><span data-stu-id="1a560-104">Specifies the maximum number of connections to a network host.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<connectionManagement>**

## <a name="syntax"></a><span data-ttu-id="1a560-105">構文</span><span class="sxs-lookup"><span data-stu-id="1a560-105">Syntax</span></span>  
  
```xml  
<connectionManagement>
</connectionManagement>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1a560-106">属性および要素</span><span class="sxs-lookup"><span data-stu-id="1a560-106">Attributes and Elements</span></span>  

 <span data-ttu-id="1a560-107">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="1a560-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1a560-108">属性</span><span class="sxs-lookup"><span data-stu-id="1a560-108">Attributes</span></span>  

 <span data-ttu-id="1a560-109">なし。</span><span class="sxs-lookup"><span data-stu-id="1a560-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="1a560-110">子要素</span><span class="sxs-lookup"><span data-stu-id="1a560-110">Child Elements</span></span>  
  
|<span data-ttu-id="1a560-111">**要素**</span><span class="sxs-lookup"><span data-stu-id="1a560-111">**Element**</span></span>|<span data-ttu-id="1a560-112">**説明**</span><span class="sxs-lookup"><span data-stu-id="1a560-112">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="1a560-113">add</span><span class="sxs-lookup"><span data-stu-id="1a560-113">add</span></span>](add-element-for-connectionmanagement-network-settings.md)|<span data-ttu-id="1a560-114">IP アドレスまたは DNS 名を接続管理リストに追加します。</span><span class="sxs-lookup"><span data-stu-id="1a560-114">Adds an IP address or DNS name to the connection management list.</span></span>|  
|[<span data-ttu-id="1a560-115">オフ</span><span class="sxs-lookup"><span data-stu-id="1a560-115">clear</span></span>](clear-element-for-connectionmanagement-network-settings.md)|<span data-ttu-id="1a560-116">接続管理の一覧をクリアします。</span><span class="sxs-lookup"><span data-stu-id="1a560-116">Clears the connection management list.</span></span>|  
|[<span data-ttu-id="1a560-117">remove</span><span class="sxs-lookup"><span data-stu-id="1a560-117">remove</span></span>](remove-element-for-connectionmanagement-network-settings.md)|<span data-ttu-id="1a560-118">接続管理リストから IP アドレスまたは DNS 名を削除します。</span><span class="sxs-lookup"><span data-stu-id="1a560-118">Removes an IP address or DNS name from the connection management list.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="1a560-119">親要素</span><span class="sxs-lookup"><span data-stu-id="1a560-119">Parent Elements</span></span>  
  
|<span data-ttu-id="1a560-120">**要素**</span><span class="sxs-lookup"><span data-stu-id="1a560-120">**Element**</span></span>|<span data-ttu-id="1a560-121">**説明**</span><span class="sxs-lookup"><span data-stu-id="1a560-121">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="1a560-122">system.net</span><span class="sxs-lookup"><span data-stu-id="1a560-122">system.net</span></span>](system-net-element-network-settings.md)|<span data-ttu-id="1a560-123">.NET Framework がネットワークに接続する方法を指定するための設定が含まれています。</span><span class="sxs-lookup"><span data-stu-id="1a560-123">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1a560-124">解説</span><span class="sxs-lookup"><span data-stu-id="1a560-124">Remarks</span></span>  

 <span data-ttu-id="1a560-125">要素は、 `connectionManagement` サーバーまたはサーバーのグループへの接続の最大数を定義します。</span><span class="sxs-lookup"><span data-stu-id="1a560-125">The `connectionManagement` element defines the maximum number of connections to a server or group of servers.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="1a560-126">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="1a560-126">Configuration Files</span></span>  

 <span data-ttu-id="1a560-127">この要素は、アプリケーション構成ファイルまたはマシン構成ファイル (Machine.config) で使用できます。</span><span class="sxs-lookup"><span data-stu-id="1a560-127">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="1a560-128">例</span><span class="sxs-lookup"><span data-stu-id="1a560-128">Example</span></span>  

 <span data-ttu-id="1a560-129">次の例では、サーバーへの4つの接続 `www.contoso.com` と、他のすべてのサーバーへの2つの接続を使用するようにアプリケーションを構成します。</span><span class="sxs-lookup"><span data-stu-id="1a560-129">The following example configures an application to use four connections to the server `www.contoso.com` and two connections to all other servers.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="1a560-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="1a560-130">See also</span></span>

- <xref:System.Net.ServicePoint>
- <xref:System.Net.ServicePointManager>
- [<span data-ttu-id="1a560-131">ネットワーク設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="1a560-131">Network Settings Schema</span></span>](index.md)
