---
title: <smtp> 要素 (ネットワーク設定)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/mailSettings/smtp
- http://schemas.microsoft.com/.NetConfiguration/v2.0#smtp
helpviewer_keywords:
- <smtp> element
- smtp element
ms.assetid: 220b0329-e384-4e0c-86b4-0945ad17efd9
ms.openlocfilehash: 2105a6dd25a7f6e5e4c1ce286be7f60beae1dca0
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2019
ms.locfileid: "71697609"
---
# <a name="smtp-element-network-settings"></a><span data-ttu-id="02e8b-102">\<smtp > 要素 (ネットワーク設定)</span><span class="sxs-lookup"><span data-stu-id="02e8b-102">\<smtp> Element (Network Settings)</span></span>
<span data-ttu-id="02e8b-103">電子メールの送信に使用する配信形式、配信方法、差出人アドレスを構成します。</span><span class="sxs-lookup"><span data-stu-id="02e8b-103">Configures the delivery format, delivery method, and from address for sending emails.</span></span>  
  
[<span data-ttu-id="02e8b-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="02e8b-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="02e8b-105">&nbsp; @ no__t-1[ **@no__t 47 >** ](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="02e8b-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>  
<span data-ttu-id="02e8b-106">&nbsp; @ no__t @ no__t-2 @ no__t-3[ **\<mailSettings >** ](mailsettings-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="02e8b-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<mailSettings>**](mailsettings-element-network-settings.md)</span></span>  
<span data-ttu-id="02e8b-107">&nbsp; @ no__t-1 @ no__t @ no__t @ no__t-5 **\< smtp >** のようになります。</span><span class="sxs-lookup"><span data-stu-id="02e8b-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<smtp>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="02e8b-108">構文</span><span class="sxs-lookup"><span data-stu-id="02e8b-108">Syntax</span></span>  
  
```xml  
<smtp  
  deliveryFormat="format"  
  deliveryMethod="method"  
  from="from address">
    <specifiedPickupDirectory>...</specifiedPickupDirectory>  
    <network>...</network>  
</smtp>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="02e8b-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="02e8b-109">Attributes and Elements</span></span>  
 <span data-ttu-id="02e8b-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="02e8b-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="02e8b-111">属性</span><span class="sxs-lookup"><span data-stu-id="02e8b-111">Attributes</span></span>  
  
|<span data-ttu-id="02e8b-112">属性</span><span class="sxs-lookup"><span data-stu-id="02e8b-112">Attribute</span></span>|<span data-ttu-id="02e8b-113">説明</span><span class="sxs-lookup"><span data-stu-id="02e8b-113">Description</span></span>|  
|---------------|-----------------|  
|`deliveryFormat`|<span data-ttu-id="02e8b-114">送信電子メールの配信形式を指定します。</span><span class="sxs-lookup"><span data-stu-id="02e8b-114">Specifies the delivery format for outgoing emails.</span></span> <span data-ttu-id="02e8b-115">指定できる値は SevenBit および International です。</span><span class="sxs-lookup"><span data-stu-id="02e8b-115">Acceptable values are SevenBit and International.</span></span>|  
|`deliveryMethod`|<span data-ttu-id="02e8b-116">電子メールの配信方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="02e8b-116">Specifies the delivery method for emails.</span></span> <span data-ttu-id="02e8b-117">使用可能な値は、Network、ピックアップディレクトリ Fromiis、および指定された指定された Updirectory です。</span><span class="sxs-lookup"><span data-stu-id="02e8b-117">Acceptable values are Network, PickupDirectoryFromIis, and SpecifiedPickupDirectory.</span></span>|  
|`from`|<span data-ttu-id="02e8b-118">送信メールの差出人アドレスを指定します。</span><span class="sxs-lookup"><span data-stu-id="02e8b-118">Specifies the from address for outgoing emails.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="02e8b-119">子要素</span><span class="sxs-lookup"><span data-stu-id="02e8b-119">Child Elements</span></span>  
  
|<span data-ttu-id="02e8b-120">属性</span><span class="sxs-lookup"><span data-stu-id="02e8b-120">Attribute</span></span>|<span data-ttu-id="02e8b-121">説明</span><span class="sxs-lookup"><span data-stu-id="02e8b-121">Description</span></span>|  
|---------------|-----------------|  
|`specifiedPickupDirectory`|<span data-ttu-id="02e8b-122">SMTP (Simple Mail Transport Protocol) サーバー用のローカル ディレクトリを設定します。</span><span class="sxs-lookup"><span data-stu-id="02e8b-122">Configures the local directory for a Simple Mail Transport Protocol (SMTP) server.</span></span>|  
|`network`|<span data-ttu-id="02e8b-123">外部 SMTP サーバー用のネットワーク オプションを設定します。</span><span class="sxs-lookup"><span data-stu-id="02e8b-123">Configures the network options for an external SMTP server.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="02e8b-124">親要素</span><span class="sxs-lookup"><span data-stu-id="02e8b-124">Parent Elements</span></span>  
  
|<span data-ttu-id="02e8b-125">**要素**</span><span class="sxs-lookup"><span data-stu-id="02e8b-125">**Element**</span></span>|<span data-ttu-id="02e8b-126">**[説明]**</span><span class="sxs-lookup"><span data-stu-id="02e8b-126">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="02e8b-127">\<mailSettings> 要素 (ネットワーク設定)</span><span class="sxs-lookup"><span data-stu-id="02e8b-127">\<mailSettings> Element (Network Settings)</span></span>](mailsettings-element-network-settings.md)|<span data-ttu-id="02e8b-128">電子メールの送信オプションを設定します。</span><span class="sxs-lookup"><span data-stu-id="02e8b-128">Configures mail sending options.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="02e8b-129">例</span><span class="sxs-lookup"><span data-stu-id="02e8b-129">Example</span></span>  
 <span data-ttu-id="02e8b-130">次の例では、既定のネットワーク資格情報を使用して電子メールを送信するための適切な SMTP パラメーターを指定しています。</span><span class="sxs-lookup"><span data-stu-id="02e8b-130">The following example specifies the appropriate SMTP parameters to send email using the default network credentials.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <mailSettings>  
      <smtp deliveryMethod="Network" deliveryFormat="SevenBit"  from="ben@contoso.com">  
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
  
## <a name="see-also"></a><span data-ttu-id="02e8b-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="02e8b-131">See also</span></span>

- <xref:System.Net.Configuration.SmtpSection?displayProperty=nameWithType>
- <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>
- <xref:System.Net.Mail.SmtpDeliveryFormat>
- <xref:System.Net.Mail.SmtpDeliveryMethod>
- [<span data-ttu-id="02e8b-132">ネットワーク設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="02e8b-132">Network Settings Schema</span></span>](index.md)
