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
ms.openlocfilehash: 1b5f7406f995a86f0a192dbf3249c067dff570ea
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59140375"
---
# <a name="smtp-element-network-settings"></a><span data-ttu-id="777b4-102">\<smtp > 要素 (ネットワーク設定)</span><span class="sxs-lookup"><span data-stu-id="777b4-102">\<smtp> Element (Network Settings)</span></span>
<span data-ttu-id="777b4-103">構成の配信形式、配信方法、および送信者の電子メールを送信するためのアドレス。</span><span class="sxs-lookup"><span data-stu-id="777b4-103">Configures the delivery format, delivery method, and from address for sending emails.</span></span>  
  
 <span data-ttu-id="777b4-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="777b4-104">\<configuration></span></span>  
<span data-ttu-id="777b4-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="777b4-105">\<system.net></span></span>  
<span data-ttu-id="777b4-106">\<mailSettings></span><span class="sxs-lookup"><span data-stu-id="777b4-106">\<mailSettings></span></span>  
<span data-ttu-id="777b4-107">\<smtp></span><span class="sxs-lookup"><span data-stu-id="777b4-107">\<smtp></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="777b4-108">構文</span><span class="sxs-lookup"><span data-stu-id="777b4-108">Syntax</span></span>  
  
```xml  
<smtp  
  deliveryFormat="format"  
  deliveryMethod="method"  
  from="from address">
    <specifiedPickupDirectory>...</specifiedPickupDirectory>  
    <network>...</network>  
</smtp>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="777b4-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="777b4-109">Attributes and Elements</span></span>  
 <span data-ttu-id="777b4-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="777b4-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="777b4-111">属性</span><span class="sxs-lookup"><span data-stu-id="777b4-111">Attributes</span></span>  
  
|<span data-ttu-id="777b4-112">属性</span><span class="sxs-lookup"><span data-stu-id="777b4-112">Attribute</span></span>|<span data-ttu-id="777b4-113">説明</span><span class="sxs-lookup"><span data-stu-id="777b4-113">Description</span></span>|  
|---------------|-----------------|  
|`deliveryFormat`|<span data-ttu-id="777b4-114">送信電子メールの配信形式を指定します。</span><span class="sxs-lookup"><span data-stu-id="777b4-114">Specifies the delivery format for outgoing emails.</span></span> <span data-ttu-id="777b4-115">指定できる値は SevenBit および International です。</span><span class="sxs-lookup"><span data-stu-id="777b4-115">Acceptable values are SevenBit and International.</span></span>|  
|`deliveryMethod`|<span data-ttu-id="777b4-116">電子メールの配信方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="777b4-116">Specifies the delivery method for emails.</span></span> <span data-ttu-id="777b4-117">使用可能な値は、Network、PickupDirectoryFromIis、および specifiedpickupdirectory です。</span><span class="sxs-lookup"><span data-stu-id="777b4-117">Acceptable values are Network, PickupDirectoryFromIis, and SpecifiedPickupDirectory.</span></span>|  
|`from`|<span data-ttu-id="777b4-118">指定します、送信電子メールの差出人アドレス。</span><span class="sxs-lookup"><span data-stu-id="777b4-118">Specifies the from address for outgoing emails.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="777b4-119">子要素</span><span class="sxs-lookup"><span data-stu-id="777b4-119">Child Elements</span></span>  
  
|<span data-ttu-id="777b4-120">属性</span><span class="sxs-lookup"><span data-stu-id="777b4-120">Attribute</span></span>|<span data-ttu-id="777b4-121">説明</span><span class="sxs-lookup"><span data-stu-id="777b4-121">Description</span></span>|  
|---------------|-----------------|  
|`specifiedPickupDirectory`|<span data-ttu-id="777b4-122">SMTP (Simple Mail Transport Protocol) サーバー用のローカル ディレクトリを設定します。</span><span class="sxs-lookup"><span data-stu-id="777b4-122">Configures the local directory for a Simple Mail Transport Protocol (SMTP) server.</span></span>|  
|`network`|<span data-ttu-id="777b4-123">外部 SMTP サーバー用のネットワーク オプションを設定します。</span><span class="sxs-lookup"><span data-stu-id="777b4-123">Configures the network options for an external SMTP server.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="777b4-124">親要素</span><span class="sxs-lookup"><span data-stu-id="777b4-124">Parent Elements</span></span>  
  
|<span data-ttu-id="777b4-125">**要素**</span><span class="sxs-lookup"><span data-stu-id="777b4-125">**Element**</span></span>|<span data-ttu-id="777b4-126">**説明**</span><span class="sxs-lookup"><span data-stu-id="777b4-126">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="777b4-127">\<mailSettings> 要素 (ネットワーク設定)</span><span class="sxs-lookup"><span data-stu-id="777b4-127">\<mailSettings> Element (Network Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/mailsettings-element-network-settings.md)|<span data-ttu-id="777b4-128">電子メールの送信オプションを設定します。</span><span class="sxs-lookup"><span data-stu-id="777b4-128">Configures mail sending options.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="777b4-129">例</span><span class="sxs-lookup"><span data-stu-id="777b4-129">Example</span></span>  
 <span data-ttu-id="777b4-130">次の例では、既定のネットワーク資格情報を使用して電子メールを送信する適切な SMTP パラメーターを指定します。</span><span class="sxs-lookup"><span data-stu-id="777b4-130">The following example specifies the appropriate SMTP parameters to send email using the default network credentials.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="777b4-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="777b4-131">See also</span></span>

- <xref:System.Net.Configuration.SmtpSection?displayProperty=nameWithType>
- <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>
- <xref:System.Net.Mail.SmtpDeliveryFormat>
- <xref:System.Net.Mail.SmtpDeliveryMethod>
- [<span data-ttu-id="777b4-132">ネットワーク設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="777b4-132">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
