---
title: <specifiedPickupDirectory> 要素 (ネットワーク設定)
description: <specifiedPickupDirectory>Network settings 要素は、.NET Framework の SMTP サーバーオプションのローカルディレクトリを構成します。
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#specifiedPickupDirectory
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/mailSettings/smtp/specifiedPickupDirectory
helpviewer_keywords:
- specifiedPickupDirectory element
- <specifiedPickupDirectory> element
ms.assetid: 0121f49d-bff2-4bc6-af06-f1628dcd61f1
ms.openlocfilehash: f0c4c1845e9542d0f3b836ff03f16bdf2979ebd8
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "84504499"
---
# <a name="specifiedpickupdirectory-element-network-settings"></a><span data-ttu-id="2504d-103">\<specifiedPickupDirectory> 要素 (ネットワーク設定)</span><span class="sxs-lookup"><span data-stu-id="2504d-103">\<specifiedPickupDirectory> Element (Network Settings)</span></span>
<span data-ttu-id="2504d-104">SMTP (Simple Mail Transport Protocol) サーバー用のローカル ディレクトリを設定します。</span><span class="sxs-lookup"><span data-stu-id="2504d-104">Configures the local directory for a Simple Mail Transport Protocol (SMTP) server.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<mailSettings>**](mailsettings-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<smtp>**](smtp-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<specifiedPickupDirectory>**  
  
## <a name="syntax"></a><span data-ttu-id="2504d-105">構文</span><span class="sxs-lookup"><span data-stu-id="2504d-105">Syntax</span></span>  
  
```xml  
<specifiedPickupDirectory  
  pickupDirectoryLocation="directory"
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2504d-106">属性および要素</span><span class="sxs-lookup"><span data-stu-id="2504d-106">Attributes and Elements</span></span>  
 <span data-ttu-id="2504d-107">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="2504d-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2504d-108">属性</span><span class="sxs-lookup"><span data-stu-id="2504d-108">Attributes</span></span>  
  
|<span data-ttu-id="2504d-109">属性</span><span class="sxs-lookup"><span data-stu-id="2504d-109">Attribute</span></span>|<span data-ttu-id="2504d-110">説明</span><span class="sxs-lookup"><span data-stu-id="2504d-110">Description</span></span>|  
|---------------|-----------------|  
|`pickupDirectoryLocation`|<span data-ttu-id="2504d-111">アプリケーションが SMTP サーバーによって後で処理するために電子メールを保存するディレクトリ。</span><span class="sxs-lookup"><span data-stu-id="2504d-111">The directory where applications save email for later processing by the SMTP server.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2504d-112">子要素</span><span class="sxs-lookup"><span data-stu-id="2504d-112">Child Elements</span></span>  
 <span data-ttu-id="2504d-113">なし。</span><span class="sxs-lookup"><span data-stu-id="2504d-113">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2504d-114">親要素</span><span class="sxs-lookup"><span data-stu-id="2504d-114">Parent Elements</span></span>  
  
|<span data-ttu-id="2504d-115">要素</span><span class="sxs-lookup"><span data-stu-id="2504d-115">Element</span></span>|<span data-ttu-id="2504d-116">説明</span><span class="sxs-lookup"><span data-stu-id="2504d-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2504d-117">\<smtp>要素 (ネットワーク設定)</span><span class="sxs-lookup"><span data-stu-id="2504d-117">\<smtp> Element (Network Settings)</span></span>](smtp-element-network-settings.md)|<span data-ttu-id="2504d-118">SMTP (Simple Mail Transport Protocol) メール送信オプションを構成します。</span><span class="sxs-lookup"><span data-stu-id="2504d-118">Configures Simple Mail Transport Protocol (SMTP) mail sending options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2504d-119">解説</span><span class="sxs-lookup"><span data-stu-id="2504d-119">Remarks</span></span>  
 <span data-ttu-id="2504d-120">属性は、 `specifiedPickupDirectory` アプリケーションが SMTP サーバーによって処理されるメールメッセージを保存するディレクトリを設定します。</span><span class="sxs-lookup"><span data-stu-id="2504d-120">The `specifiedPickupDirectory` attribute sets the directory where applications save mail messages to be processed by the SMTP server.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2504d-121">例</span><span class="sxs-lookup"><span data-stu-id="2504d-121">Example</span></span>  
 <span data-ttu-id="2504d-122">次の例では、電子メールのピックアップディレクトリとして c:\ maildrop を指定します。</span><span class="sxs-lookup"><span data-stu-id="2504d-122">The following example specifies c:\maildrop as the mail pickup directory.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="2504d-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="2504d-123">See also</span></span>

- <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>
- <xref:System.Net.Configuration.SmtpSection?displayProperty=nameWithType>
- <xref:System.Net.Configuration.SmtpSpecifiedPickupDirectoryElement?displayProperty=nameWithType>
- [<span data-ttu-id="2504d-124">ネットワーク設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="2504d-124">Network Settings Schema</span></span>](index.md)
