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
ms.openlocfilehash: 4b0cbaf9a7bfe2a9b1610811f4201253d219a6b2
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "79154609"
---
# <a name="specifiedpickupdirectory-element-network-settings"></a><span data-ttu-id="a0a56-102">\<specifiedPickupDirectory> 要素 (ネットワーク設定)</span><span class="sxs-lookup"><span data-stu-id="a0a56-102">\<specifiedPickupDirectory> Element (Network Settings)</span></span>
<span data-ttu-id="a0a56-103">SMTP (Simple Mail Transport Protocol) サーバー用のローカル ディレクトリを設定します。</span><span class="sxs-lookup"><span data-stu-id="a0a56-103">Configures the local directory for a Simple Mail Transport Protocol (SMTP) server.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<mailSettings>**](mailsettings-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<smtp>**](smtp-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<specifiedPickupDirectory>**  
  
## <a name="syntax"></a><span data-ttu-id="a0a56-104">構文</span><span class="sxs-lookup"><span data-stu-id="a0a56-104">Syntax</span></span>  
  
```xml  
<specifiedPickupDirectory  
  pickupDirectoryLocation="directory"
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a0a56-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="a0a56-105">Attributes and Elements</span></span>  
 <span data-ttu-id="a0a56-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="a0a56-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a0a56-107">属性</span><span class="sxs-lookup"><span data-stu-id="a0a56-107">Attributes</span></span>  
  
|<span data-ttu-id="a0a56-108">属性</span><span class="sxs-lookup"><span data-stu-id="a0a56-108">Attribute</span></span>|<span data-ttu-id="a0a56-109">説明</span><span class="sxs-lookup"><span data-stu-id="a0a56-109">Description</span></span>|  
|---------------|-----------------|  
|`pickupDirectoryLocation`|<span data-ttu-id="a0a56-110">アプリケーションが SMTP サーバーによって後で処理するために電子メールを保存するディレクトリ。</span><span class="sxs-lookup"><span data-stu-id="a0a56-110">The directory where applications save email for later processing by the SMTP server.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a0a56-111">子要素</span><span class="sxs-lookup"><span data-stu-id="a0a56-111">Child Elements</span></span>  
 <span data-ttu-id="a0a56-112">なし。</span><span class="sxs-lookup"><span data-stu-id="a0a56-112">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a0a56-113">親要素</span><span class="sxs-lookup"><span data-stu-id="a0a56-113">Parent Elements</span></span>  
  
|<span data-ttu-id="a0a56-114">要素</span><span class="sxs-lookup"><span data-stu-id="a0a56-114">Element</span></span>|<span data-ttu-id="a0a56-115">Description</span><span class="sxs-lookup"><span data-stu-id="a0a56-115">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a0a56-116">\<smtp>要素 (ネットワーク設定)</span><span class="sxs-lookup"><span data-stu-id="a0a56-116">\<smtp> Element (Network Settings)</span></span>](smtp-element-network-settings.md)|<span data-ttu-id="a0a56-117">SMTP (Simple Mail Transport Protocol) メール送信オプションを構成します。</span><span class="sxs-lookup"><span data-stu-id="a0a56-117">Configures Simple Mail Transport Protocol (SMTP) mail sending options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a0a56-118">解説</span><span class="sxs-lookup"><span data-stu-id="a0a56-118">Remarks</span></span>  
 <span data-ttu-id="a0a56-119">属性は、 `specifiedPickupDirectory` アプリケーションが SMTP サーバーによって処理されるメールメッセージを保存するディレクトリを設定します。</span><span class="sxs-lookup"><span data-stu-id="a0a56-119">The `specifiedPickupDirectory` attribute sets the directory where applications save mail messages to be processed by the SMTP server.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a0a56-120">例</span><span class="sxs-lookup"><span data-stu-id="a0a56-120">Example</span></span>  
 <span data-ttu-id="a0a56-121">次の例では、電子メールのピックアップディレクトリとして c:\ maildrop を指定します。</span><span class="sxs-lookup"><span data-stu-id="a0a56-121">The following example specifies c:\maildrop as the mail pickup directory.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="a0a56-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="a0a56-122">See also</span></span>

- <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>
- <xref:System.Net.Configuration.SmtpSection?displayProperty=nameWithType>
- <xref:System.Net.Configuration.SmtpSpecifiedPickupDirectoryElement?displayProperty=nameWithType>
- [<span data-ttu-id="a0a56-123">ネットワーク設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="a0a56-123">Network Settings Schema</span></span>](index.md)
