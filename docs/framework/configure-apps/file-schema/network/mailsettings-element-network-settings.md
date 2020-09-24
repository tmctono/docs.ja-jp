---
title: <mailSettings> 要素 (ネットワーク設定)
description: <mailSettings>Network settings 要素は、.NET Framework のメール送信オプションを構成します。
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#mailSettings
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/mailSettings
helpviewer_keywords:
- mailSettings element
- <mailSettings> element
ms.assetid: 54f0f153-17e5-4f49-afdc-deadb940c9c1
ms.openlocfilehash: a146874acc21f52507b37b1751c648792e23c8bb
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91158852"
---
# <a name="mailsettings-element-network-settings"></a><span data-ttu-id="b7a42-103">\<mailSettings> 要素 (ネットワーク設定)</span><span class="sxs-lookup"><span data-stu-id="b7a42-103">\<mailSettings> Element (Network Settings)</span></span>

<span data-ttu-id="b7a42-104">電子メールの送信オプションを設定します。</span><span class="sxs-lookup"><span data-stu-id="b7a42-104">Configures mail sending options.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<mailSettings>**

## <a name="syntax"></a><span data-ttu-id="b7a42-105">構文</span><span class="sxs-lookup"><span data-stu-id="b7a42-105">Syntax</span></span>  
  
```xml  
<mailSettings>
  <smtp>...</smtp>  
</mailSettings>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b7a42-106">属性および要素</span><span class="sxs-lookup"><span data-stu-id="b7a42-106">Attributes and Elements</span></span>  

 <span data-ttu-id="b7a42-107">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="b7a42-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b7a42-108">属性</span><span class="sxs-lookup"><span data-stu-id="b7a42-108">Attributes</span></span>  

 <span data-ttu-id="b7a42-109">なし。</span><span class="sxs-lookup"><span data-stu-id="b7a42-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="b7a42-110">子要素</span><span class="sxs-lookup"><span data-stu-id="b7a42-110">Child Elements</span></span>  
  
|<span data-ttu-id="b7a42-111">属性</span><span class="sxs-lookup"><span data-stu-id="b7a42-111">Attribute</span></span>|<span data-ttu-id="b7a42-112">[説明]</span><span class="sxs-lookup"><span data-stu-id="b7a42-112">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="b7a42-113">\<smtp> 要素 (ネットワーク設定)</span><span class="sxs-lookup"><span data-stu-id="b7a42-113">\<smtp> Element (Network Settings)</span></span>](smtp-element-network-settings.md)|<span data-ttu-id="b7a42-114">簡易メール転送プロトコルのオプションを構成します。</span><span class="sxs-lookup"><span data-stu-id="b7a42-114">Configures Simple Mail Transport Protocol options.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b7a42-115">親要素</span><span class="sxs-lookup"><span data-stu-id="b7a42-115">Parent Elements</span></span>  
  
|<span data-ttu-id="b7a42-116">**要素**</span><span class="sxs-lookup"><span data-stu-id="b7a42-116">**Element**</span></span>|<span data-ttu-id="b7a42-117">**説明**</span><span class="sxs-lookup"><span data-stu-id="b7a42-117">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="b7a42-118">\<system.Net> 要素 (ネットワーク設定)</span><span class="sxs-lookup"><span data-stu-id="b7a42-118">\<system.Net> Element (Network Settings)</span></span>](system-net-element-network-settings.md)|<span data-ttu-id="b7a42-119">.NET Framework がネットワークに接続する方法を指定するための設定が含まれています。</span><span class="sxs-lookup"><span data-stu-id="b7a42-119">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="b7a42-120">例</span><span class="sxs-lookup"><span data-stu-id="b7a42-120">Example</span></span>  

 <span data-ttu-id="b7a42-121">次の例では、既定のネットワーク資格情報を使用して電子メールを送信するための適切な SMTP パラメーターを指定しています。</span><span class="sxs-lookup"><span data-stu-id="b7a42-121">The following example specifies the appropriate SMTP parameters to send email using the default network credentials.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <mailSettings>  
      <smtp deliveryMethod="Network">  
        <network  
          host="localhost"  
          port="25"  
          defaultCredentials="true"  
        />  
      </smtp>  
    </mailSettings>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="b7a42-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="b7a42-122">See also</span></span>

- <xref:System.Net.Mail.SmtpClient>
- [<span data-ttu-id="b7a42-123">ネットワーク設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="b7a42-123">Network Settings Schema</span></span>](index.md)
