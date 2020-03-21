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
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154609"
---
# <a name="specifiedpickupdirectory-element-network-settings"></a><span data-ttu-id="6d275-102">\<指定されたピックアップディレクトリ>要素 (ネットワーク設定)</span><span class="sxs-lookup"><span data-stu-id="6d275-102">\<specifiedPickupDirectory> Element (Network Settings)</span></span>
<span data-ttu-id="6d275-103">SMTP (Simple Mail Transport Protocol) サーバー用のローカル ディレクトリを設定します。</span><span class="sxs-lookup"><span data-stu-id="6d275-103">Configures the local directory for a Simple Mail Transport Protocol (SMTP) server.</span></span>  
  
<span data-ttu-id="6d275-104">[**\<構成>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="6d275-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="6d275-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="6d275-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>\
<span data-ttu-id="6d275-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<メール設定>**](mailsettings-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="6d275-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<mailSettings>**](mailsettings-element-network-settings.md)</span></span>\
<span data-ttu-id="6d275-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<smtp>**](smtp-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="6d275-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<smtp>**](smtp-element-network-settings.md)</span></span>\
<span data-ttu-id="6d275-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<指定されたピックアップディレクトリ>**</span><span class="sxs-lookup"><span data-stu-id="6d275-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<specifiedPickupDirectory>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6d275-109">構文</span><span class="sxs-lookup"><span data-stu-id="6d275-109">Syntax</span></span>  
  
```xml  
<specifiedPickupDirectory  
  pickupDirectoryLocation="directory"
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6d275-110">属性および要素</span><span class="sxs-lookup"><span data-stu-id="6d275-110">Attributes and Elements</span></span>  
 <span data-ttu-id="6d275-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="6d275-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6d275-112">属性</span><span class="sxs-lookup"><span data-stu-id="6d275-112">Attributes</span></span>  
  
|<span data-ttu-id="6d275-113">属性</span><span class="sxs-lookup"><span data-stu-id="6d275-113">Attribute</span></span>|<span data-ttu-id="6d275-114">説明</span><span class="sxs-lookup"><span data-stu-id="6d275-114">Description</span></span>|  
|---------------|-----------------|  
|`pickupDirectoryLocation`|<span data-ttu-id="6d275-115">アプリケーションが SMTP サーバーによって後で処理するために電子メールを保存するディレクトリ。</span><span class="sxs-lookup"><span data-stu-id="6d275-115">The directory where applications save email for later processing by the SMTP server.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6d275-116">子要素</span><span class="sxs-lookup"><span data-stu-id="6d275-116">Child Elements</span></span>  
 <span data-ttu-id="6d275-117">[なし] :</span><span class="sxs-lookup"><span data-stu-id="6d275-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6d275-118">親要素</span><span class="sxs-lookup"><span data-stu-id="6d275-118">Parent Elements</span></span>  
  
|<span data-ttu-id="6d275-119">要素</span><span class="sxs-lookup"><span data-stu-id="6d275-119">Element</span></span>|<span data-ttu-id="6d275-120">説明</span><span class="sxs-lookup"><span data-stu-id="6d275-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6d275-121">\<smtp>要素 (ネットワーク設定)</span><span class="sxs-lookup"><span data-stu-id="6d275-121">\<smtp> Element (Network Settings)</span></span>](smtp-element-network-settings.md)|<span data-ttu-id="6d275-122">簡易メール転送プロトコル (SMTP) メール送信オプションを構成します。</span><span class="sxs-lookup"><span data-stu-id="6d275-122">Configures Simple Mail Transport Protocol (SMTP) mail sending options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6d275-123">解説</span><span class="sxs-lookup"><span data-stu-id="6d275-123">Remarks</span></span>  
 <span data-ttu-id="6d275-124">この`specifiedPickupDirectory`属性は、SMTP サーバーが処理するメール メッセージをアプリケーションが保存するディレクトリを設定します。</span><span class="sxs-lookup"><span data-stu-id="6d275-124">The `specifiedPickupDirectory` attribute sets the directory where applications save mail messages to be processed by the SMTP server.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6d275-125">例</span><span class="sxs-lookup"><span data-stu-id="6d275-125">Example</span></span>  
 <span data-ttu-id="6d275-126">次の例では、メールピックアップディレクトリとして c:\maildrop を指定します。</span><span class="sxs-lookup"><span data-stu-id="6d275-126">The following example specifies c:\maildrop as the mail pickup directory.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="6d275-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="6d275-127">See also</span></span>

- <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>
- <xref:System.Net.Configuration.SmtpSection?displayProperty=nameWithType>
- <xref:System.Net.Configuration.SmtpSpecifiedPickupDirectoryElement?displayProperty=nameWithType>
- [<span data-ttu-id="6d275-128">ネットワーク設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="6d275-128">Network Settings Schema</span></span>](index.md)
