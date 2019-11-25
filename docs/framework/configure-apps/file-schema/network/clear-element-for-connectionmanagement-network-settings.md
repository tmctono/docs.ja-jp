---
title: connectionManagement の <clear> 要素 (ネットワーク設定)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/connectionManagement/clear
- http://schemas.microsoft.com/.NetConfiguration/v2.0#clear
helpviewer_keywords:
- <clear> element, connectionManagement
- connectionManagement, clear element
- clear element, connectionManagement
- <connectionManagement>, clear element
ms.assetid: fb259282-84c4-4dc4-a226-78d904a6edc3
ms.openlocfilehash: a76df48a9de084e1121a5e96b22edf7aa3acba23
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/14/2019
ms.locfileid: "74088486"
---
# <a name="clear-element-for-connectionmanagement-network-settings"></a><span data-ttu-id="05099-102">connectionManagement の > 要素をクリア \<(ネットワーク設定)</span><span class="sxs-lookup"><span data-stu-id="05099-102">\<clear> Element for connectionManagement (Network Settings)</span></span>
<span data-ttu-id="05099-103">接続管理の一覧をクリアします。</span><span class="sxs-lookup"><span data-stu-id="05099-103">Clears the connection management list.</span></span>  

<span data-ttu-id="05099-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="05099-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="05099-105">&nbsp;&nbsp;[ **\<system. net >** ](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="05099-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>\
<span data-ttu-id="05099-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<connectionManagement >** ](connectionmanagement-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="05099-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<connectionManagement>**](connectionmanagement-element-network-settings.md)</span></span>\
<span data-ttu-id="05099-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**クリア >**</span><span class="sxs-lookup"><span data-stu-id="05099-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span></span>

## <a name="syntax"></a><span data-ttu-id="05099-108">構文</span><span class="sxs-lookup"><span data-stu-id="05099-108">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="05099-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="05099-109">Attributes and Elements</span></span>  
 <span data-ttu-id="05099-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="05099-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="05099-111">属性</span><span class="sxs-lookup"><span data-stu-id="05099-111">Attributes</span></span>  
 <span data-ttu-id="05099-112">なし。</span><span class="sxs-lookup"><span data-stu-id="05099-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="05099-113">子要素</span><span class="sxs-lookup"><span data-stu-id="05099-113">Child Elements</span></span>  
 <span data-ttu-id="05099-114">なし。</span><span class="sxs-lookup"><span data-stu-id="05099-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="05099-115">親要素</span><span class="sxs-lookup"><span data-stu-id="05099-115">Parent Elements</span></span>  
  
|<span data-ttu-id="05099-116">**要素**</span><span class="sxs-lookup"><span data-stu-id="05099-116">**Element**</span></span>|<span data-ttu-id="05099-117">**説明**</span><span class="sxs-lookup"><span data-stu-id="05099-117">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="05099-118">connectionManagement</span><span class="sxs-lookup"><span data-stu-id="05099-118">connectionManagement</span></span>](connectionmanagement-element-network-settings.md)|<span data-ttu-id="05099-119">ネットワーク ホストへの接続の最大数を指定します。</span><span class="sxs-lookup"><span data-stu-id="05099-119">Specifies the maximum number of connections to a network host.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="05099-120">Remarks</span><span class="sxs-lookup"><span data-stu-id="05099-120">Remarks</span></span>  
 <span data-ttu-id="05099-121">`clear` 要素は、接続管理リストからすべてのエントリを削除します。</span><span class="sxs-lookup"><span data-stu-id="05099-121">The `clear` element clears all entries from the connection management list.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="05099-122">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="05099-122">Configuration Files</span></span>  
 <span data-ttu-id="05099-123">この要素は、アプリケーション構成ファイルまたはマシン構成ファイル (Machine.config) で使用できます。</span><span class="sxs-lookup"><span data-stu-id="05099-123">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="05099-124">例</span><span class="sxs-lookup"><span data-stu-id="05099-124">Example</span></span>  
 <span data-ttu-id="05099-125">次の例では、接続管理の一覧をクリアし、サーバー `www.contoso.com` とその他のすべてのネットワークホストの新しい接続管理エントリを追加します。</span><span class="sxs-lookup"><span data-stu-id="05099-125">The following example clears the connection management list and then adds new connection management entries for the server `www.contoso.com` and all other network hosts.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <connectionManagement>  
      <clear/>  
      <add address = "http://www.contoso.com" maxconnection = "4" />  
      <add address = "*" maxconnection = "2" />  
    </connectionManagement>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="05099-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="05099-126">See also</span></span>

- <xref:System.Net.ServicePoint>
- <xref:System.Net.ServicePointManager>
- [<span data-ttu-id="05099-127">ネットワーク設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="05099-127">Network Settings Schema</span></span>](index.md)
