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
ms.openlocfilehash: 4e8bf23ce39edadf80f019315c690b597b3d7361
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "74089229"
---
# <a name="mailsettings-element-network-settings"></a><span data-ttu-id="e08f0-102">\<mailSettings> 要素 (ネットワーク設定)</span><span class="sxs-lookup"><span data-stu-id="e08f0-102">\<mailSettings> Element (Network Settings)</span></span>
<span data-ttu-id="e08f0-103">電子メールの送信オプションを設定します。</span><span class="sxs-lookup"><span data-stu-id="e08f0-103">Configures mail sending options.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<mailSettings>**

## <a name="syntax"></a><span data-ttu-id="e08f0-104">構文</span><span class="sxs-lookup"><span data-stu-id="e08f0-104">Syntax</span></span>  
  
```xml  
<mailSettings>
  <smtp>...</smtp>  
</mailSettings>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e08f0-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="e08f0-105">Attributes and Elements</span></span>  
 <span data-ttu-id="e08f0-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="e08f0-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e08f0-107">属性</span><span class="sxs-lookup"><span data-stu-id="e08f0-107">Attributes</span></span>  
 <span data-ttu-id="e08f0-108">なし。</span><span class="sxs-lookup"><span data-stu-id="e08f0-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="e08f0-109">子要素</span><span class="sxs-lookup"><span data-stu-id="e08f0-109">Child Elements</span></span>  
  
|<span data-ttu-id="e08f0-110">属性</span><span class="sxs-lookup"><span data-stu-id="e08f0-110">Attribute</span></span>|<span data-ttu-id="e08f0-111">説明</span><span class="sxs-lookup"><span data-stu-id="e08f0-111">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="e08f0-112">\<smtp>要素 (ネットワーク設定)</span><span class="sxs-lookup"><span data-stu-id="e08f0-112">\<smtp> Element (Network Settings)</span></span>](smtp-element-network-settings.md)|<span data-ttu-id="e08f0-113">簡易メール転送プロトコルのオプションを構成します。</span><span class="sxs-lookup"><span data-stu-id="e08f0-113">Configures Simple Mail Transport Protocol options.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e08f0-114">親要素</span><span class="sxs-lookup"><span data-stu-id="e08f0-114">Parent Elements</span></span>  
  
|<span data-ttu-id="e08f0-115">**要素**</span><span class="sxs-lookup"><span data-stu-id="e08f0-115">**Element**</span></span>|<span data-ttu-id="e08f0-116">**説明**</span><span class="sxs-lookup"><span data-stu-id="e08f0-116">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="e08f0-117">\<system.Net>要素 (ネットワーク設定)</span><span class="sxs-lookup"><span data-stu-id="e08f0-117">\<system.Net> Element (Network Settings)</span></span>](system-net-element-network-settings.md)|<span data-ttu-id="e08f0-118">.NET Framework がネットワークに接続する方法を指定するための設定が含まれています。</span><span class="sxs-lookup"><span data-stu-id="e08f0-118">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="e08f0-119">例</span><span class="sxs-lookup"><span data-stu-id="e08f0-119">Example</span></span>  
 <span data-ttu-id="e08f0-120">次の例では、既定のネットワーク資格情報を使用して電子メールを送信するための適切な SMTP パラメーターを指定しています。</span><span class="sxs-lookup"><span data-stu-id="e08f0-120">The following example specifies the appropriate SMTP parameters to send email using the default network credentials.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="e08f0-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="e08f0-121">See also</span></span>

- <xref:System.Net.Mail.SmtpClient>
- [<span data-ttu-id="e08f0-122">ネットワーク設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="e08f0-122">Network Settings Schema</span></span>](index.md)
