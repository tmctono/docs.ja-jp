---
title: <mailSettings> 要素 (ネットワーク設定)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#mailSettings
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/mailSettings
helpviewer_keywords:
- mailSettings element
- <mailSettings> element
ms.assetid: 54f0f153-17e5-4f49-afdc-deadb940c9c1
ms.openlocfilehash: 54fb68ab0bf8aa2665d70391350c626131ccb4bc
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61674507"
---
# <a name="mailsettings-element-network-settings"></a><span data-ttu-id="73f18-102">\<mailSettings > 要素 (ネットワーク設定)</span><span class="sxs-lookup"><span data-stu-id="73f18-102">\<mailSettings> Element (Network Settings)</span></span>
<span data-ttu-id="73f18-103">電子メールの送信オプションを設定します。</span><span class="sxs-lookup"><span data-stu-id="73f18-103">Configures mail sending options.</span></span>  

<span data-ttu-id="73f18-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="73f18-104">\<configuration></span></span>  
<span data-ttu-id="73f18-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="73f18-105">\<system.net></span></span>  
<span data-ttu-id="73f18-106">\<mailSettings></span><span class="sxs-lookup"><span data-stu-id="73f18-106">\<mailSettings></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="73f18-107">構文</span><span class="sxs-lookup"><span data-stu-id="73f18-107">Syntax</span></span>  
  
```xml  
<mailSettings>
  <smtp>...</smtp>  
</mailSettings>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="73f18-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="73f18-108">Attributes and Elements</span></span>  
 <span data-ttu-id="73f18-109">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="73f18-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="73f18-110">属性</span><span class="sxs-lookup"><span data-stu-id="73f18-110">Attributes</span></span>  
 <span data-ttu-id="73f18-111">なし。</span><span class="sxs-lookup"><span data-stu-id="73f18-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="73f18-112">子要素</span><span class="sxs-lookup"><span data-stu-id="73f18-112">Child Elements</span></span>  
  
|<span data-ttu-id="73f18-113">属性</span><span class="sxs-lookup"><span data-stu-id="73f18-113">Attribute</span></span>|<span data-ttu-id="73f18-114">説明</span><span class="sxs-lookup"><span data-stu-id="73f18-114">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="73f18-115">\<smtp> 要素 (ネットワーク設定)</span><span class="sxs-lookup"><span data-stu-id="73f18-115">\<smtp> Element (Network Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/smtp-element-network-settings.md)|<span data-ttu-id="73f18-116">簡易メール転送プロトコル オプションを構成します。</span><span class="sxs-lookup"><span data-stu-id="73f18-116">Configures Simple Mail Transport Protocol options.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="73f18-117">親要素</span><span class="sxs-lookup"><span data-stu-id="73f18-117">Parent Elements</span></span>  
  
|<span data-ttu-id="73f18-118">**要素**</span><span class="sxs-lookup"><span data-stu-id="73f18-118">**Element**</span></span>|<span data-ttu-id="73f18-119">**説明**</span><span class="sxs-lookup"><span data-stu-id="73f18-119">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="73f18-120">\<system.Net> 要素 (ネットワーク設定)</span><span class="sxs-lookup"><span data-stu-id="73f18-120">\<system.Net> Element (Network Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md)|<span data-ttu-id="73f18-121">.NET Framework がネットワークに接続する方法を指定するための設定が含まれています。</span><span class="sxs-lookup"><span data-stu-id="73f18-121">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="73f18-122">例</span><span class="sxs-lookup"><span data-stu-id="73f18-122">Example</span></span>  
 <span data-ttu-id="73f18-123">次の例では、既定のネットワーク資格情報を使用して電子メールを送信する適切な SMTP パラメーターを指定します。</span><span class="sxs-lookup"><span data-stu-id="73f18-123">The following example specifies the appropriate SMTP parameters to send email using the default network credentials.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="73f18-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="73f18-124">See also</span></span>

- <xref:System.Net.Mail.SmtpClient>
- [<span data-ttu-id="73f18-125">ネットワーク設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="73f18-125">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
