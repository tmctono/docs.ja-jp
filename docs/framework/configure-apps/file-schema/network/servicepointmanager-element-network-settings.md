---
title: <servicePointManager> 要素 (ネットワーク設定)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#servicePointManager
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/servicePointManager
helpviewer_keywords:
- servicePointManager element
- <servicePointManager> element
ms.assetid: 6e5def51-3646-4ef6-a7bd-c69151321bec
ms.openlocfilehash: b7333016fea2d46285d3c98181c0ca4904c376f8
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "74089125"
---
# <a name="servicepointmanager-element-network-settings"></a><span data-ttu-id="995f4-102">\<servicePointManager> 要素 (ネットワーク設定)</span><span class="sxs-lookup"><span data-stu-id="995f4-102">\<servicePointManager> Element (Network Settings)</span></span>
<span data-ttu-id="995f4-103">ネットワークリソースへの接続を構成します。</span><span class="sxs-lookup"><span data-stu-id="995f4-103">Configures connections to network resources.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<settings>**](settings-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<servicePointManager>**

## <a name="syntax"></a><span data-ttu-id="995f4-104">構文</span><span class="sxs-lookup"><span data-stu-id="995f4-104">Syntax</span></span>  
  
```xml  
<servicePointManager  
  checkCertificateName="true|false"  
  checkCertificateRevocationList="true|false"  
  encryptionPolicy="AllowNoEncryption|NoEncryption|RequireEncryption"  
  expect100Continue="true|false"  
  useNagleAlgorithm="true|false"  
  enableDnsRoundRobin="true|false"  
  dnsRefreshTimeout="time"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="995f4-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="995f4-105">Attributes and Elements</span></span>  
 <span data-ttu-id="995f4-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="995f4-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="995f4-107">属性</span><span class="sxs-lookup"><span data-stu-id="995f4-107">Attributes</span></span>  
  
|<span data-ttu-id="995f4-108">**属性**</span><span class="sxs-lookup"><span data-stu-id="995f4-108">**Attribute**</span></span>|<span data-ttu-id="995f4-109">**説明**</span><span class="sxs-lookup"><span data-stu-id="995f4-109">**Description**</span></span>|  
|-------------------|---------------------|  
|`checkCertificateName`|<span data-ttu-id="995f4-110">証明書を使用する前に、証明書の名前がサーバーホスト名と一致するかどうかをシステムが確認する必要があるかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="995f4-110">Specifies whether the system should verify that the name on the certificate matches the server host name before using the certificate.</span></span> <span data-ttu-id="995f4-111">既定値は `true` です。</span><span class="sxs-lookup"><span data-stu-id="995f4-111">The default value is `true`.</span></span>|  
|`checkCertificateRevocationList`|<span data-ttu-id="995f4-112">証明書を使用する前に証明書が失効しているかどうかをシステムが確認するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="995f4-112">Specifies whether the system should check whether the certificate has been revoked before using the certificate.</span></span> <span data-ttu-id="995f4-113">既定値は `false` です。</span><span class="sxs-lookup"><span data-stu-id="995f4-113">The default value is `false`.</span></span>|  
|`dnsRefreshTimeout`|<span data-ttu-id="995f4-114">DNS ラウンドロビンオプションと共に、ドメインネームサービス (DNS) の解決時間をミリ秒単位でキャッシュする期間を指定します。</span><span class="sxs-lookup"><span data-stu-id="995f4-114">Specifies how long Domain Name Service (DNS) resolutions are cached in conjunction with the DNS Round Robin option, in milliseconds.</span></span> <span data-ttu-id="995f4-115">既定値は 120,000 ミリ秒 (2 分) です。</span><span class="sxs-lookup"><span data-stu-id="995f4-115">The default value is 120,000 milliseconds (two minutes).</span></span>|  
|`enableDnsRoundRobin`|<span data-ttu-id="995f4-116">複数のインターネットプロトコル (IP) アドレスを持つホスト名の DNS 解決が、すべてのアドレスを返すのか、それとも1つだけを返すのかを指定します。</span><span class="sxs-lookup"><span data-stu-id="995f4-116">Specifies whether DNS resolutions of host names with multiple Internet Protocol (IP) addresses return all the addresses, or just the first one.</span></span> <span data-ttu-id="995f4-117">既定値は `false` です。</span><span class="sxs-lookup"><span data-stu-id="995f4-117">The default value is `false`.</span></span>|  
|`encryptionPolicy`|<span data-ttu-id="995f4-118">インスタンスの SSL/TLS セッションに適用される暗号化ポリシーを指定し <xref:System.Net.ServicePointManager> ます。</span><span class="sxs-lookup"><span data-stu-id="995f4-118">Specifies the encryption policy applied to an SSL/TLS session on a <xref:System.Net.ServicePointManager> instance.</span></span> <span data-ttu-id="995f4-119">指定できる値は、列挙体の値と同じです <xref:System.Net.Security.EncryptionPolicy> 。</span><span class="sxs-lookup"><span data-stu-id="995f4-119">The possible values are equivalent to the values for the <xref:System.Net.Security.EncryptionPolicy> enumeration.</span></span> <span data-ttu-id="995f4-120"><xref:System.Security.Authentication.CipherAlgorithmType.Null>暗号化ポリシーがに設定されている場合は、を使用する必要が `NoEncryption` あります。</span><span class="sxs-lookup"><span data-stu-id="995f4-120">The use of <xref:System.Security.Authentication.CipherAlgorithmType.Null> is required when the encryption policy is set to `NoEncryption`.</span></span> <span data-ttu-id="995f4-121">既定値は `RequireEncryption` です。</span><span class="sxs-lookup"><span data-stu-id="995f4-121">The default value is `RequireEncryption`.</span></span>|  
|`expect100Continue`|<span data-ttu-id="995f4-122">POST メソッドがサーバーからの応答を受信する必要があるかどうかを指定し `100-continue` ます。</span><span class="sxs-lookup"><span data-stu-id="995f4-122">Specifies whether POST methods should expect to receive a `100-continue` response from the server.</span></span> <span data-ttu-id="995f4-123">既定値は `true` です。</span><span class="sxs-lookup"><span data-stu-id="995f4-123">The default value is `true`.</span></span>|  
|`useNagleAlgorithm`|<span data-ttu-id="995f4-124">サービスポイントマネージャーによって制御される接続が Nagle アルゴリズムを使用するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="995f4-124">Specifies whether connections controlled by the service point manager use the Nagle algorithm.</span></span> <span data-ttu-id="995f4-125">既定値は `true` です。</span><span class="sxs-lookup"><span data-stu-id="995f4-125">The default value is `true`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="995f4-126">子要素</span><span class="sxs-lookup"><span data-stu-id="995f4-126">Child Elements</span></span>  
 <span data-ttu-id="995f4-127">なし。</span><span class="sxs-lookup"><span data-stu-id="995f4-127">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="995f4-128">親要素</span><span class="sxs-lookup"><span data-stu-id="995f4-128">Parent Elements</span></span>  
  
|<span data-ttu-id="995f4-129">**要素**</span><span class="sxs-lookup"><span data-stu-id="995f4-129">**Element**</span></span>|<span data-ttu-id="995f4-130">**説明**</span><span class="sxs-lookup"><span data-stu-id="995f4-130">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="995f4-131">設定</span><span class="sxs-lookup"><span data-stu-id="995f4-131">Settings</span></span>](settings-element-network-settings.md)|<span data-ttu-id="995f4-132"><xref:System.Net> 名前空間の基本的なネットワーク オプションを構成します。</span><span class="sxs-lookup"><span data-stu-id="995f4-132">Configures basic network options for the <xref:System.Net> namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="995f4-133">解説</span><span class="sxs-lookup"><span data-stu-id="995f4-133">Remarks</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="995f4-134">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="995f4-134">Configuration Files</span></span>  
 <span data-ttu-id="995f4-135">この要素は、アプリケーション構成ファイルまたはマシン構成ファイル (Machine.config) で使用できます。</span><span class="sxs-lookup"><span data-stu-id="995f4-135">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="995f4-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="995f4-136">See also</span></span>

- <xref:System.Net.ServicePointManager>
- <xref:System.Net.Security.EncryptionPolicy>
- [<span data-ttu-id="995f4-137">ネットワーク設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="995f4-137">Network Settings Schema</span></span>](index.md)
