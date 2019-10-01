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
ms.openlocfilehash: 17b380b12977423669fd413132d69a3082daca41
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2019
ms.locfileid: "71698357"
---
# <a name="clear-element-for-connectionmanagement-network-settings"></a><span data-ttu-id="4648b-102">connectionManagement の \<clear> 要素 (ネットワーク設定)</span><span class="sxs-lookup"><span data-stu-id="4648b-102">\<clear> Element for connectionManagement (Network Settings)</span></span>
<span data-ttu-id="4648b-103">接続管理の一覧をクリアします。</span><span class="sxs-lookup"><span data-stu-id="4648b-103">Clears the connection management list.</span></span>  
  
[<span data-ttu-id="4648b-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="4648b-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="4648b-105">&nbsp; @ no__t-1[ **@no__t 47 >** ](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="4648b-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>  
<span data-ttu-id="4648b-106">&nbsp; @ no__t @ no__t-2 @ no__t-3[ **\<connectionManagement >** ](connectionmanagement-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="4648b-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<connectionManagement>**](connectionmanagement-element-network-settings.md)</span></span>  
<span data-ttu-id="4648b-107">&nbsp; @ no__t-1 @ no__t @ no__t @ no__t-5 **\<clear をクリア**します。</span><span class="sxs-lookup"><span data-stu-id="4648b-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4648b-108">構文</span><span class="sxs-lookup"><span data-stu-id="4648b-108">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4648b-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="4648b-109">Attributes and Elements</span></span>  
 <span data-ttu-id="4648b-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="4648b-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4648b-111">属性</span><span class="sxs-lookup"><span data-stu-id="4648b-111">Attributes</span></span>  
 <span data-ttu-id="4648b-112">[なし] :</span><span class="sxs-lookup"><span data-stu-id="4648b-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="4648b-113">子要素</span><span class="sxs-lookup"><span data-stu-id="4648b-113">Child Elements</span></span>  
 <span data-ttu-id="4648b-114">なし。</span><span class="sxs-lookup"><span data-stu-id="4648b-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4648b-115">親要素</span><span class="sxs-lookup"><span data-stu-id="4648b-115">Parent Elements</span></span>  
  
|<span data-ttu-id="4648b-116">**要素**</span><span class="sxs-lookup"><span data-stu-id="4648b-116">**Element**</span></span>|<span data-ttu-id="4648b-117">**[説明]**</span><span class="sxs-lookup"><span data-stu-id="4648b-117">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="4648b-118">connectionManagement</span><span class="sxs-lookup"><span data-stu-id="4648b-118">connectionManagement</span></span>](connectionmanagement-element-network-settings.md)|<span data-ttu-id="4648b-119">ネットワーク ホストへの接続の最大数を指定します。</span><span class="sxs-lookup"><span data-stu-id="4648b-119">Specifies the maximum number of connections to a network host.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4648b-120">コメント</span><span class="sxs-lookup"><span data-stu-id="4648b-120">Remarks</span></span>  
 <span data-ttu-id="4648b-121">@No__t-0 要素は、接続管理リストからすべてのエントリを削除します。</span><span class="sxs-lookup"><span data-stu-id="4648b-121">The `clear` element clears all entries from the connection management list.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="4648b-122">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="4648b-122">Configuration Files</span></span>  
 <span data-ttu-id="4648b-123">この要素は、アプリケーション構成ファイルまたはマシン構成ファイル (Machine.config) で使用できます。</span><span class="sxs-lookup"><span data-stu-id="4648b-123">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="4648b-124">例</span><span class="sxs-lookup"><span data-stu-id="4648b-124">Example</span></span>  
 <span data-ttu-id="4648b-125">次の例では、接続管理の一覧をクリアし、サーバー `www.contoso.com` およびその他すべてのネットワークホストの新しい接続管理エントリを追加します。</span><span class="sxs-lookup"><span data-stu-id="4648b-125">The following example clears the connection management list and then adds new connection management entries for the server `www.contoso.com` and all other network hosts.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="4648b-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="4648b-126">See also</span></span>

- <xref:System.Net.ServicePoint>
- <xref:System.Net.ServicePointManager>
- [<span data-ttu-id="4648b-127">ネットワーク設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="4648b-127">Network Settings Schema</span></span>](index.md)
