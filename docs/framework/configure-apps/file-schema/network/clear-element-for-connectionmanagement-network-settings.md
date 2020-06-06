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
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "74088486"
---
# <a name="clear-element-for-connectionmanagement-network-settings"></a><span data-ttu-id="82fae-102">connectionManagement の \<clear> 要素 (ネットワーク設定)</span><span class="sxs-lookup"><span data-stu-id="82fae-102">\<clear> Element for connectionManagement (Network Settings)</span></span>
<span data-ttu-id="82fae-103">接続管理の一覧をクリアします。</span><span class="sxs-lookup"><span data-stu-id="82fae-103">Clears the connection management list.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<connectionManagement>**](connectionmanagement-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**

## <a name="syntax"></a><span data-ttu-id="82fae-104">構文</span><span class="sxs-lookup"><span data-stu-id="82fae-104">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="82fae-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="82fae-105">Attributes and Elements</span></span>  
 <span data-ttu-id="82fae-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="82fae-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="82fae-107">属性</span><span class="sxs-lookup"><span data-stu-id="82fae-107">Attributes</span></span>  
 <span data-ttu-id="82fae-108">なし。</span><span class="sxs-lookup"><span data-stu-id="82fae-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="82fae-109">子要素</span><span class="sxs-lookup"><span data-stu-id="82fae-109">Child Elements</span></span>  
 <span data-ttu-id="82fae-110">[なし] :</span><span class="sxs-lookup"><span data-stu-id="82fae-110">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="82fae-111">親要素</span><span class="sxs-lookup"><span data-stu-id="82fae-111">Parent Elements</span></span>  
  
|<span data-ttu-id="82fae-112">**要素**</span><span class="sxs-lookup"><span data-stu-id="82fae-112">**Element**</span></span>|<span data-ttu-id="82fae-113">**説明**</span><span class="sxs-lookup"><span data-stu-id="82fae-113">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="82fae-114">connectionManagement</span><span class="sxs-lookup"><span data-stu-id="82fae-114">connectionManagement</span></span>](connectionmanagement-element-network-settings.md)|<span data-ttu-id="82fae-115">ネットワーク ホストへの接続の最大数を指定します。</span><span class="sxs-lookup"><span data-stu-id="82fae-115">Specifies the maximum number of connections to a network host.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="82fae-116">解説</span><span class="sxs-lookup"><span data-stu-id="82fae-116">Remarks</span></span>  
 <span data-ttu-id="82fae-117">要素は、 `clear` 接続管理リストからすべてのエントリを削除します。</span><span class="sxs-lookup"><span data-stu-id="82fae-117">The `clear` element clears all entries from the connection management list.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="82fae-118">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="82fae-118">Configuration Files</span></span>  
 <span data-ttu-id="82fae-119">この要素は、アプリケーション構成ファイルまたはマシン構成ファイル (Machine.config) で使用できます。</span><span class="sxs-lookup"><span data-stu-id="82fae-119">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="82fae-120">例</span><span class="sxs-lookup"><span data-stu-id="82fae-120">Example</span></span>  
 <span data-ttu-id="82fae-121">次の例では、接続管理の一覧をクリアし、サーバー `www.contoso.com` とその他のすべてのネットワークホストの新しい接続管理エントリを追加します。</span><span class="sxs-lookup"><span data-stu-id="82fae-121">The following example clears the connection management list and then adds new connection management entries for the server `www.contoso.com` and all other network hosts.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="82fae-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="82fae-122">See also</span></span>

- <xref:System.Net.ServicePoint>
- <xref:System.Net.ServicePointManager>
- [<span data-ttu-id="82fae-123">ネットワーク設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="82fae-123">Network Settings Schema</span></span>](index.md)
