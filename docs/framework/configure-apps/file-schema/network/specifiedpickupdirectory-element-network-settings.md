---
title: <specifiedPickupDirectory> 要素 (ネットワーク設定)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#specifiedPickupDirectory
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/mailSettings/smtp/specifiedPickupDirectory
helpviewer_keywords:
- specifiedPickupDirectory element
- <specifiedPickupDirectory> element
ms.assetid: 0121f49d-bff2-4bc6-af06-f1628dcd61f1
ms.openlocfilehash: 1acc724bb14c3610f14d06452c30b3d5dac42e13
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/14/2019
ms.locfileid: "74089075"
---
# <a name="specifiedpickupdirectory-element-network-settings"></a><span data-ttu-id="d7595-102">\<には、> 要素 (ネットワーク設定) を設定します。</span><span class="sxs-lookup"><span data-stu-id="d7595-102">\<specifiedPickupDirectory> Element (Network Settings)</span></span>
<span data-ttu-id="d7595-103">SMTP (Simple Mail Transport Protocol) サーバー用のローカル ディレクトリを設定します。</span><span class="sxs-lookup"><span data-stu-id="d7595-103">Configures the local directory for a Simple Mail Transport Protocol (SMTP) server.</span></span>  
  
<span data-ttu-id="d7595-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="d7595-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="d7595-105">&nbsp;&nbsp;[ **\<system. net >** ](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="d7595-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>\
<span data-ttu-id="d7595-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<mailSettings >** ](mailsettings-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="d7595-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<mailSettings>**](mailsettings-element-network-settings.md)</span></span>\
<span data-ttu-id="d7595-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**smtp\<** ](smtp-element-network-settings.md) ></span><span class="sxs-lookup"><span data-stu-id="d7595-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<smtp>**](smtp-element-network-settings.md)\</span></span>
<span data-ttu-id="d7595-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<に**よって、></span><span class="sxs-lookup"><span data-stu-id="d7595-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<specifiedPickupDirectory>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d7595-109">構文</span><span class="sxs-lookup"><span data-stu-id="d7595-109">Syntax</span></span>  
  
```xml  
<specifiedPickupDirectory  
  pickupDirectoryLocation="directory"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d7595-110">属性および要素</span><span class="sxs-lookup"><span data-stu-id="d7595-110">Attributes and Elements</span></span>  
 <span data-ttu-id="d7595-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="d7595-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d7595-112">属性</span><span class="sxs-lookup"><span data-stu-id="d7595-112">Attributes</span></span>  
  
|<span data-ttu-id="d7595-113">属性</span><span class="sxs-lookup"><span data-stu-id="d7595-113">Attribute</span></span>|<span data-ttu-id="d7595-114">説明</span><span class="sxs-lookup"><span data-stu-id="d7595-114">Description</span></span>|  
|---------------|-----------------|  
|`pickupDirectoryLocation`|<span data-ttu-id="d7595-115">アプリケーションが SMTP サーバーによって後で処理するために電子メールを保存するディレクトリ。</span><span class="sxs-lookup"><span data-stu-id="d7595-115">The directory where applications save email for later processing by the SMTP server.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d7595-116">子要素</span><span class="sxs-lookup"><span data-stu-id="d7595-116">Child Elements</span></span>  
 <span data-ttu-id="d7595-117">なし。</span><span class="sxs-lookup"><span data-stu-id="d7595-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d7595-118">親要素</span><span class="sxs-lookup"><span data-stu-id="d7595-118">Parent Elements</span></span>  
  
|<span data-ttu-id="d7595-119">要素</span><span class="sxs-lookup"><span data-stu-id="d7595-119">Element</span></span>|<span data-ttu-id="d7595-120">説明</span><span class="sxs-lookup"><span data-stu-id="d7595-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d7595-121">\<smtp > 要素 (ネットワーク設定)</span><span class="sxs-lookup"><span data-stu-id="d7595-121">\<smtp> Element (Network Settings)</span></span>](smtp-element-network-settings.md)|<span data-ttu-id="d7595-122">SMTP (Simple Mail Transport Protocol) メール送信オプションを構成します。</span><span class="sxs-lookup"><span data-stu-id="d7595-122">Configures Simple Mail Transport Protocol (SMTP) mail sending options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d7595-123">Remarks</span><span class="sxs-lookup"><span data-stu-id="d7595-123">Remarks</span></span>  
 <span data-ttu-id="d7595-124">`specifiedPickupDirectory` 属性は、アプリケーションが SMTP サーバーによって処理されるメールメッセージを保存するディレクトリを設定します。</span><span class="sxs-lookup"><span data-stu-id="d7595-124">The `specifiedPickupDirectory` attribute sets the directory where applications save mail messages to be processed by the SMTP server.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d7595-125">例</span><span class="sxs-lookup"><span data-stu-id="d7595-125">Example</span></span>  
 <span data-ttu-id="d7595-126">次の例では、電子メールのピックアップディレクトリとして c:\ maildrop を指定します。</span><span class="sxs-lookup"><span data-stu-id="d7595-126">The following example specifies c:\maildrop as the mail pickup directory.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <mailSettings>  
      <smtp deliveryMethod="SpecifiedPickupDirectory">  
        <specifiedPickupDirectory  
          pickupDirectoryLocation="c:\maildrop"  
        />  
      </smtp>  
    </mailSettings>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="d7595-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="d7595-127">See also</span></span>

- <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>
- <xref:System.Net.Configuration.SmtpSection?displayProperty=nameWithType>
- <xref:System.Net.Configuration.SmtpSpecifiedPickupDirectoryElement?displayProperty=nameWithType>
- [<span data-ttu-id="d7595-128">ネットワーク設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="d7595-128">Network Settings Schema</span></span>](index.md)
