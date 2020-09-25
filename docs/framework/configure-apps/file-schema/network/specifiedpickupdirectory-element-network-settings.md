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
ms.openlocfilehash: 5bb7fc5405b1ee2f0f054bc6e9f043a3f9fcd1ec
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91176163"
---
# <a name="specifiedpickupdirectory-element-network-settings"></a><span data-ttu-id="a5611-103">\<specifiedPickupDirectory> 要素 (ネットワーク設定)</span><span class="sxs-lookup"><span data-stu-id="a5611-103">\<specifiedPickupDirectory> Element (Network Settings)</span></span>

<span data-ttu-id="a5611-104">SMTP (Simple Mail Transport Protocol) サーバー用のローカル ディレクトリを設定します。</span><span class="sxs-lookup"><span data-stu-id="a5611-104">Configures the local directory for a Simple Mail Transport Protocol (SMTP) server.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<mailSettings>**](mailsettings-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<smtp>**](smtp-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<specifiedPickupDirectory>**  
  
## <a name="syntax"></a><span data-ttu-id="a5611-105">構文</span><span class="sxs-lookup"><span data-stu-id="a5611-105">Syntax</span></span>  
  
```xml  
<specifiedPickupDirectory  
  pickupDirectoryLocation="directory"
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a5611-106">属性および要素</span><span class="sxs-lookup"><span data-stu-id="a5611-106">Attributes and Elements</span></span>  

 <span data-ttu-id="a5611-107">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="a5611-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a5611-108">属性</span><span class="sxs-lookup"><span data-stu-id="a5611-108">Attributes</span></span>  
  
|<span data-ttu-id="a5611-109">属性</span><span class="sxs-lookup"><span data-stu-id="a5611-109">Attribute</span></span>|<span data-ttu-id="a5611-110">[説明]</span><span class="sxs-lookup"><span data-stu-id="a5611-110">Description</span></span>|  
|---------------|-----------------|  
|`pickupDirectoryLocation`|<span data-ttu-id="a5611-111">アプリケーションが SMTP サーバーによって後で処理するために電子メールを保存するディレクトリ。</span><span class="sxs-lookup"><span data-stu-id="a5611-111">The directory where applications save email for later processing by the SMTP server.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a5611-112">子要素</span><span class="sxs-lookup"><span data-stu-id="a5611-112">Child Elements</span></span>  

 <span data-ttu-id="a5611-113">なし。</span><span class="sxs-lookup"><span data-stu-id="a5611-113">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a5611-114">親要素</span><span class="sxs-lookup"><span data-stu-id="a5611-114">Parent Elements</span></span>  
  
|<span data-ttu-id="a5611-115">要素</span><span class="sxs-lookup"><span data-stu-id="a5611-115">Element</span></span>|<span data-ttu-id="a5611-116">説明</span><span class="sxs-lookup"><span data-stu-id="a5611-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a5611-117">\<smtp> 要素 (ネットワーク設定)</span><span class="sxs-lookup"><span data-stu-id="a5611-117">\<smtp> Element (Network Settings)</span></span>](smtp-element-network-settings.md)|<span data-ttu-id="a5611-118">SMTP (Simple Mail Transport Protocol) メール送信オプションを構成します。</span><span class="sxs-lookup"><span data-stu-id="a5611-118">Configures Simple Mail Transport Protocol (SMTP) mail sending options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a5611-119">解説</span><span class="sxs-lookup"><span data-stu-id="a5611-119">Remarks</span></span>  

 <span data-ttu-id="a5611-120">属性は、 `specifiedPickupDirectory` アプリケーションが SMTP サーバーによって処理されるメールメッセージを保存するディレクトリを設定します。</span><span class="sxs-lookup"><span data-stu-id="a5611-120">The `specifiedPickupDirectory` attribute sets the directory where applications save mail messages to be processed by the SMTP server.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a5611-121">例</span><span class="sxs-lookup"><span data-stu-id="a5611-121">Example</span></span>  

 <span data-ttu-id="a5611-122">次の例では、電子メールのピックアップディレクトリとして c:\ maildrop を指定します。</span><span class="sxs-lookup"><span data-stu-id="a5611-122">The following example specifies c:\maildrop as the mail pickup directory.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="a5611-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="a5611-123">See also</span></span>

- <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>
- <xref:System.Net.Configuration.SmtpSection?displayProperty=nameWithType>
- <xref:System.Net.Configuration.SmtpSpecifiedPickupDirectoryElement?displayProperty=nameWithType>
- [<span data-ttu-id="a5611-124">ネットワーク設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="a5611-124">Network Settings Schema</span></span>](index.md)
