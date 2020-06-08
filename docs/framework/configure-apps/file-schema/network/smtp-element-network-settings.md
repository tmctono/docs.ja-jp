---
title: <smtp> 要素 (ネットワーク設定)
description: <smtp>ネットワーク設定要素は、.NET Framework の電子メールオプションを送信するための配信形式、配信方法、および差出人アドレスを構成します。
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/mailSettings/smtp
- http://schemas.microsoft.com/.NetConfiguration/v2.0#smtp
helpviewer_keywords:
- <smtp> element
- smtp element
ms.assetid: 220b0329-e384-4e0c-86b4-0945ad17efd9
ms.openlocfilehash: b30b82922a69ea660f4c4abfd808e89fa9945183
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "84504512"
---
# <a name="smtp-element-network-settings"></a><span data-ttu-id="64157-103">\<smtp> 要素 (ネットワーク設定)</span><span class="sxs-lookup"><span data-stu-id="64157-103">\<smtp> Element (Network Settings)</span></span>
<span data-ttu-id="64157-104">電子メールの送信に使用する配信形式、配信方法、差出人アドレスを構成します。</span><span class="sxs-lookup"><span data-stu-id="64157-104">Configures the delivery format, delivery method, and from address for sending emails.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<mailSettings>**](mailsettings-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<smtp>**
  
## <a name="syntax"></a><span data-ttu-id="64157-105">構文</span><span class="sxs-lookup"><span data-stu-id="64157-105">Syntax</span></span>  
  
```xml  
<smtp  
  deliveryFormat="format"  
  deliveryMethod="method"  
  from="from address">
    <specifiedPickupDirectory>...</specifiedPickupDirectory>  
    <network>...</network>  
</smtp>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="64157-106">属性および要素</span><span class="sxs-lookup"><span data-stu-id="64157-106">Attributes and Elements</span></span>  
 <span data-ttu-id="64157-107">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="64157-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="64157-108">属性</span><span class="sxs-lookup"><span data-stu-id="64157-108">Attributes</span></span>  
  
|<span data-ttu-id="64157-109">属性</span><span class="sxs-lookup"><span data-stu-id="64157-109">Attribute</span></span>|<span data-ttu-id="64157-110">説明</span><span class="sxs-lookup"><span data-stu-id="64157-110">Description</span></span>|  
|---------------|-----------------|  
|`deliveryFormat`|<span data-ttu-id="64157-111">送信電子メールの配信形式を指定します。</span><span class="sxs-lookup"><span data-stu-id="64157-111">Specifies the delivery format for outgoing emails.</span></span> <span data-ttu-id="64157-112">指定できる値は SevenBit および International です。</span><span class="sxs-lookup"><span data-stu-id="64157-112">Acceptable values are SevenBit and International.</span></span>|  
|`deliveryMethod`|<span data-ttu-id="64157-113">電子メールの配信方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="64157-113">Specifies the delivery method for emails.</span></span> <span data-ttu-id="64157-114">使用可能な値は、Network、ピックアップディレクトリ Fromiis、および指定された指定された Updirectory です。</span><span class="sxs-lookup"><span data-stu-id="64157-114">Acceptable values are Network, PickupDirectoryFromIis, and SpecifiedPickupDirectory.</span></span>|  
|`from`|<span data-ttu-id="64157-115">送信メールの差出人アドレスを指定します。</span><span class="sxs-lookup"><span data-stu-id="64157-115">Specifies the from address for outgoing emails.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="64157-116">子要素</span><span class="sxs-lookup"><span data-stu-id="64157-116">Child Elements</span></span>  
  
|<span data-ttu-id="64157-117">属性</span><span class="sxs-lookup"><span data-stu-id="64157-117">Attribute</span></span>|<span data-ttu-id="64157-118">説明</span><span class="sxs-lookup"><span data-stu-id="64157-118">Description</span></span>|  
|---------------|-----------------|  
|`specifiedPickupDirectory`|<span data-ttu-id="64157-119">SMTP (Simple Mail Transport Protocol) サーバー用のローカル ディレクトリを設定します。</span><span class="sxs-lookup"><span data-stu-id="64157-119">Configures the local directory for a Simple Mail Transport Protocol (SMTP) server.</span></span>|  
|`network`|<span data-ttu-id="64157-120">外部 SMTP サーバー用のネットワーク オプションを設定します。</span><span class="sxs-lookup"><span data-stu-id="64157-120">Configures the network options for an external SMTP server.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="64157-121">親要素</span><span class="sxs-lookup"><span data-stu-id="64157-121">Parent Elements</span></span>  
  
|<span data-ttu-id="64157-122">**要素**</span><span class="sxs-lookup"><span data-stu-id="64157-122">**Element**</span></span>|<span data-ttu-id="64157-123">**説明**</span><span class="sxs-lookup"><span data-stu-id="64157-123">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="64157-124">\<mailSettings>要素 (ネットワーク設定)</span><span class="sxs-lookup"><span data-stu-id="64157-124">\<mailSettings> Element (Network Settings)</span></span>](mailsettings-element-network-settings.md)|<span data-ttu-id="64157-125">電子メールの送信オプションを設定します。</span><span class="sxs-lookup"><span data-stu-id="64157-125">Configures mail sending options.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="64157-126">例</span><span class="sxs-lookup"><span data-stu-id="64157-126">Example</span></span>  
 <span data-ttu-id="64157-127">次の例では、既定のネットワーク資格情報を使用して電子メールを送信するための適切な SMTP パラメーターを指定しています。</span><span class="sxs-lookup"><span data-stu-id="64157-127">The following example specifies the appropriate SMTP parameters to send email using the default network credentials.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="64157-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="64157-128">See also</span></span>

- <xref:System.Net.Configuration.SmtpSection?displayProperty=nameWithType>
- <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>
- <xref:System.Net.Mail.SmtpDeliveryFormat>
- <xref:System.Net.Mail.SmtpDeliveryMethod>
- [<span data-ttu-id="64157-129">ネットワーク設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="64157-129">Network Settings Schema</span></span>](index.md)
