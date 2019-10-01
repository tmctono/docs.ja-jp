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
ms.openlocfilehash: 47aa357dac8b6bf71ce8c391004af16f8c98e347
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2019
ms.locfileid: "71697589"
---
# <a name="specifiedpickupdirectory-element-network-settings"></a><span data-ttu-id="3160b-102">\< に設定します。 > 要素 (ネットワーク設定)</span><span class="sxs-lookup"><span data-stu-id="3160b-102">\<specifiedPickupDirectory> Element (Network Settings)</span></span>
<span data-ttu-id="3160b-103">SMTP (Simple Mail Transport Protocol) サーバー用のローカル ディレクトリを設定します。</span><span class="sxs-lookup"><span data-stu-id="3160b-103">Configures the local directory for a Simple Mail Transport Protocol (SMTP) server.</span></span>  
  
[<span data-ttu-id="3160b-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="3160b-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="3160b-105">&nbsp; @ no__t-1[ **@no__t 47 >** ](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="3160b-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>  
<span data-ttu-id="3160b-106">&nbsp; @ no__t @ no__t-2 @ no__t-3[ **\<mailSettings >** ](mailsettings-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="3160b-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<mailSettings>**](mailsettings-element-network-settings.md)</span></span>  
<span data-ttu-id="3160b-107">&nbsp; @ no__t-1 @ no__t @ no__t @ no__t-5[ **\<smtp >** のようになります。](smtp-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="3160b-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<smtp>**](smtp-element-network-settings.md)</span></span>  
<span data-ttu-id="3160b-108">&nbsp; @ no__t-1 @ no__t @ no__t @ no__t @ no__t-6 @ no__t-7 **\<の場合は、を >** します。</span><span class="sxs-lookup"><span data-stu-id="3160b-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<specifiedPickupDirectory>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3160b-109">構文</span><span class="sxs-lookup"><span data-stu-id="3160b-109">Syntax</span></span>  
  
```xml  
<specifiedPickupDirectory  
  pickupDirectoryLocation="directory"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3160b-110">属性および要素</span><span class="sxs-lookup"><span data-stu-id="3160b-110">Attributes and Elements</span></span>  
 <span data-ttu-id="3160b-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="3160b-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3160b-112">属性</span><span class="sxs-lookup"><span data-stu-id="3160b-112">Attributes</span></span>  
  
|<span data-ttu-id="3160b-113">属性</span><span class="sxs-lookup"><span data-stu-id="3160b-113">Attribute</span></span>|<span data-ttu-id="3160b-114">説明</span><span class="sxs-lookup"><span data-stu-id="3160b-114">Description</span></span>|  
|---------------|-----------------|  
|`pickupDirectoryLocation`|<span data-ttu-id="3160b-115">アプリケーションが SMTP サーバーによって後で処理するために電子メールを保存するディレクトリ。</span><span class="sxs-lookup"><span data-stu-id="3160b-115">The directory where applications save email for later processing by the SMTP server.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3160b-116">子要素</span><span class="sxs-lookup"><span data-stu-id="3160b-116">Child Elements</span></span>  
 <span data-ttu-id="3160b-117">なし。</span><span class="sxs-lookup"><span data-stu-id="3160b-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3160b-118">親要素</span><span class="sxs-lookup"><span data-stu-id="3160b-118">Parent Elements</span></span>  
  
|<span data-ttu-id="3160b-119">要素</span><span class="sxs-lookup"><span data-stu-id="3160b-119">Element</span></span>|<span data-ttu-id="3160b-120">説明</span><span class="sxs-lookup"><span data-stu-id="3160b-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3160b-121">\<smtp> 要素 (ネットワーク設定)</span><span class="sxs-lookup"><span data-stu-id="3160b-121">\<smtp> Element (Network Settings)</span></span>](smtp-element-network-settings.md)|<span data-ttu-id="3160b-122">簡易メール転送プロトコル (SMTP) 電子メールの送信オプションを構成します。</span><span class="sxs-lookup"><span data-stu-id="3160b-122">Configures Simple Mail Transport Protocol (SMTP) mail sending options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3160b-123">コメント</span><span class="sxs-lookup"><span data-stu-id="3160b-123">Remarks</span></span>  
 <span data-ttu-id="3160b-124">@No__t-0 属性は、アプリケーションが SMTP サーバーによって処理されるメールメッセージを保存するディレクトリを設定します。</span><span class="sxs-lookup"><span data-stu-id="3160b-124">The `specifiedPickupDirectory` attribute sets the directory where applications save mail messages to be processed by the SMTP server.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3160b-125">例</span><span class="sxs-lookup"><span data-stu-id="3160b-125">Example</span></span>  
 <span data-ttu-id="3160b-126">次の例では、電子メールのピックアップディレクトリとして c:\ maildrop を指定します。</span><span class="sxs-lookup"><span data-stu-id="3160b-126">The following example specifies c:\maildrop as the mail pickup directory.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="3160b-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="3160b-127">See also</span></span>

- <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>
- <xref:System.Net.Configuration.SmtpSection?displayProperty=nameWithType>
- <xref:System.Net.Configuration.SmtpSpecifiedPickupDirectoryElement?displayProperty=nameWithType>
- [<span data-ttu-id="3160b-128">ネットワーク設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="3160b-128">Network Settings Schema</span></span>](index.md)
