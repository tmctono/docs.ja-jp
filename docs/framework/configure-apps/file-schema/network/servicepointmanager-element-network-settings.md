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
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/14/2019
ms.locfileid: "74089125"
---
# <a name="servicepointmanager-element-network-settings"></a><span data-ttu-id="f0f37-102">\<servicePointManager > 要素 (ネットワーク設定)</span><span class="sxs-lookup"><span data-stu-id="f0f37-102">\<servicePointManager> Element (Network Settings)</span></span>
<span data-ttu-id="f0f37-103">ネットワークリソースへの接続を構成します。</span><span class="sxs-lookup"><span data-stu-id="f0f37-103">Configures connections to network resources.</span></span>  

<span data-ttu-id="f0f37-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="f0f37-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="f0f37-105">&nbsp;&nbsp;[ **\<system. net >** ](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="f0f37-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>\
<span data-ttu-id="f0f37-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<設定 >** ](settings-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="f0f37-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<settings>**](settings-element-network-settings.md)</span></span>\
<span data-ttu-id="f0f37-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**servicePointManager >**</span><span class="sxs-lookup"><span data-stu-id="f0f37-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<servicePointManager>**</span></span>

## <a name="syntax"></a><span data-ttu-id="f0f37-108">構文</span><span class="sxs-lookup"><span data-stu-id="f0f37-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f0f37-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="f0f37-109">Attributes and Elements</span></span>  
 <span data-ttu-id="f0f37-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="f0f37-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f0f37-111">属性</span><span class="sxs-lookup"><span data-stu-id="f0f37-111">Attributes</span></span>  
  
|<span data-ttu-id="f0f37-112">**属性**</span><span class="sxs-lookup"><span data-stu-id="f0f37-112">**Attribute**</span></span>|<span data-ttu-id="f0f37-113">**説明**</span><span class="sxs-lookup"><span data-stu-id="f0f37-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`checkCertificateName`|<span data-ttu-id="f0f37-114">証明書を使用する前に、証明書の名前がサーバーホスト名と一致するかどうかをシステムが確認する必要があるかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="f0f37-114">Specifies whether the system should verify that the name on the certificate matches the server host name before using the certificate.</span></span> <span data-ttu-id="f0f37-115">既定値は `true`です。</span><span class="sxs-lookup"><span data-stu-id="f0f37-115">The default value is `true`.</span></span>|  
|`checkCertificateRevocationList`|<span data-ttu-id="f0f37-116">証明書を使用する前に証明書が失効しているかどうかをシステムが確認するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="f0f37-116">Specifies whether the system should check whether the certificate has been revoked before using the certificate.</span></span> <span data-ttu-id="f0f37-117">既定値は `false`です。</span><span class="sxs-lookup"><span data-stu-id="f0f37-117">The default value is `false`.</span></span>|  
|`dnsRefreshTimeout`|<span data-ttu-id="f0f37-118">DNS ラウンドロビンオプションと共に、ドメインネームサービス (DNS) の解決時間をミリ秒単位でキャッシュする期間を指定します。</span><span class="sxs-lookup"><span data-stu-id="f0f37-118">Specifies how long Domain Name Service (DNS) resolutions are cached in conjunction with the DNS Round Robin option, in milliseconds.</span></span> <span data-ttu-id="f0f37-119">既定値は 120,000 ミリ秒 (2 分) です。</span><span class="sxs-lookup"><span data-stu-id="f0f37-119">The default value is 120,000 milliseconds (two minutes).</span></span>|  
|`enableDnsRoundRobin`|<span data-ttu-id="f0f37-120">複数のインターネットプロトコル (IP) アドレスを持つホスト名の DNS 解決が、すべてのアドレスを返すのか、それとも1つだけを返すのかを指定します。</span><span class="sxs-lookup"><span data-stu-id="f0f37-120">Specifies whether DNS resolutions of host names with multiple Internet Protocol (IP) addresses return all the addresses, or just the first one.</span></span> <span data-ttu-id="f0f37-121">既定値は `false`です。</span><span class="sxs-lookup"><span data-stu-id="f0f37-121">The default value is `false`.</span></span>|  
|`encryptionPolicy`|<span data-ttu-id="f0f37-122"><xref:System.Net.ServicePointManager> インスタンスの SSL/TLS セッションに適用される暗号化ポリシーを指定します。</span><span class="sxs-lookup"><span data-stu-id="f0f37-122">Specifies the encryption policy applied to an SSL/TLS session on a <xref:System.Net.ServicePointManager> instance.</span></span> <span data-ttu-id="f0f37-123">指定できる値は、<xref:System.Net.Security.EncryptionPolicy> 列挙型の値と同じです。</span><span class="sxs-lookup"><span data-stu-id="f0f37-123">The possible values are equivalent to the values for the <xref:System.Net.Security.EncryptionPolicy> enumeration.</span></span> <span data-ttu-id="f0f37-124">暗号化ポリシーが `NoEncryption`に設定されている場合は、<xref:System.Security.Authentication.CipherAlgorithmType.Null> を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f0f37-124">The use of <xref:System.Security.Authentication.CipherAlgorithmType.Null> is required when the encryption policy is set to `NoEncryption`.</span></span> <span data-ttu-id="f0f37-125">既定値は `RequireEncryption`です。</span><span class="sxs-lookup"><span data-stu-id="f0f37-125">The default value is `RequireEncryption`.</span></span>|  
|`expect100Continue`|<span data-ttu-id="f0f37-126">POST メソッドがサーバーから `100-continue` 応答を受け取ることを期待するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="f0f37-126">Specifies whether POST methods should expect to receive a `100-continue` response from the server.</span></span> <span data-ttu-id="f0f37-127">既定値は `true`です。</span><span class="sxs-lookup"><span data-stu-id="f0f37-127">The default value is `true`.</span></span>|  
|`useNagleAlgorithm`|<span data-ttu-id="f0f37-128">サービスポイントマネージャーによって制御される接続が Nagle アルゴリズムを使用するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="f0f37-128">Specifies whether connections controlled by the service point manager use the Nagle algorithm.</span></span> <span data-ttu-id="f0f37-129">既定値は `true`です。</span><span class="sxs-lookup"><span data-stu-id="f0f37-129">The default value is `true`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f0f37-130">子要素</span><span class="sxs-lookup"><span data-stu-id="f0f37-130">Child Elements</span></span>  
 <span data-ttu-id="f0f37-131">なし。</span><span class="sxs-lookup"><span data-stu-id="f0f37-131">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f0f37-132">親要素</span><span class="sxs-lookup"><span data-stu-id="f0f37-132">Parent Elements</span></span>  
  
|<span data-ttu-id="f0f37-133">**要素**</span><span class="sxs-lookup"><span data-stu-id="f0f37-133">**Element**</span></span>|<span data-ttu-id="f0f37-134">**説明**</span><span class="sxs-lookup"><span data-stu-id="f0f37-134">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="f0f37-135">設定</span><span class="sxs-lookup"><span data-stu-id="f0f37-135">Settings</span></span>](settings-element-network-settings.md)|<span data-ttu-id="f0f37-136"><xref:System.Net> 名前空間の基本的なネットワーク オプションを構成します。</span><span class="sxs-lookup"><span data-stu-id="f0f37-136">Configures basic network options for the <xref:System.Net> namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f0f37-137">Remarks</span><span class="sxs-lookup"><span data-stu-id="f0f37-137">Remarks</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="f0f37-138">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="f0f37-138">Configuration Files</span></span>  
 <span data-ttu-id="f0f37-139">この要素は、アプリケーション構成ファイルまたはマシン構成ファイル (Machine.config) で使用できます。</span><span class="sxs-lookup"><span data-stu-id="f0f37-139">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0f37-140">関連項目</span><span class="sxs-lookup"><span data-stu-id="f0f37-140">See also</span></span>

- <xref:System.Net.ServicePointManager>
- <xref:System.Net.Security.EncryptionPolicy>
- [<span data-ttu-id="f0f37-141">ネットワーク設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="f0f37-141">Network Settings Schema</span></span>](index.md)
