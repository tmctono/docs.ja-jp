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
ms.openlocfilehash: 407ed85de109a671030eccff8ddd92af91628014
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61704987"
---
# <a name="servicepointmanager-element-network-settings"></a><span data-ttu-id="957d8-102">\<servicePointManager > 要素 (ネットワーク設定)</span><span class="sxs-lookup"><span data-stu-id="957d8-102">\<servicePointManager> Element (Network Settings)</span></span>
<span data-ttu-id="957d8-103">ネットワーク リソースへの接続を構成します。</span><span class="sxs-lookup"><span data-stu-id="957d8-103">Configures connections to network resources.</span></span>  
  
 <span data-ttu-id="957d8-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="957d8-104">\<configuration></span></span>  
<span data-ttu-id="957d8-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="957d8-105">\<system.net></span></span>  
<span data-ttu-id="957d8-106">\<settings></span><span class="sxs-lookup"><span data-stu-id="957d8-106">\<settings></span></span>  
<span data-ttu-id="957d8-107">\<servicePointManager></span><span class="sxs-lookup"><span data-stu-id="957d8-107">\<servicePointManager></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="957d8-108">構文</span><span class="sxs-lookup"><span data-stu-id="957d8-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="957d8-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="957d8-109">Attributes and Elements</span></span>  
 <span data-ttu-id="957d8-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="957d8-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="957d8-111">属性</span><span class="sxs-lookup"><span data-stu-id="957d8-111">Attributes</span></span>  
  
|<span data-ttu-id="957d8-112">**属性**</span><span class="sxs-lookup"><span data-stu-id="957d8-112">**Attribute**</span></span>|<span data-ttu-id="957d8-113">**説明**</span><span class="sxs-lookup"><span data-stu-id="957d8-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`checkCertificateName`|<span data-ttu-id="957d8-114">システムが証明書の名前、証明書を使用する前にサーバーのホスト名が一致することを確認する必要があるかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="957d8-114">Specifies whether the system should verify that the name on the certificate matches the server host name before using the certificate.</span></span> <span data-ttu-id="957d8-115">既定値は `true` です。</span><span class="sxs-lookup"><span data-stu-id="957d8-115">The default value is `true`.</span></span>|  
|`checkCertificateRevocationList`|<span data-ttu-id="957d8-116">システムが、証明書を使用する前に、証明書を失効するかどうかをチェックする必要があるかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="957d8-116">Specifies whether the system should check whether the certificate has been revoked before using the certificate.</span></span> <span data-ttu-id="957d8-117">既定値は `false` です。</span><span class="sxs-lookup"><span data-stu-id="957d8-117">The default value is `false`.</span></span>|  
|`dnsRefreshTimeout`|<span data-ttu-id="957d8-118">(ミリ秒単位)、DNS ラウンド ロビン オプションと共に、どのくらいの時間ドメイン ネーム サービス (DNS) 解決策はキャッシュを指定します。</span><span class="sxs-lookup"><span data-stu-id="957d8-118">Specifies how long Domain Name Service (DNS) resolutions are cached in conjunction with the DNS Round Robin option, in milliseconds.</span></span> <span data-ttu-id="957d8-119">既定値は 120,000 ミリ秒 (2 分) です。</span><span class="sxs-lookup"><span data-stu-id="957d8-119">The default value is 120,000 milliseconds (two minutes).</span></span>|  
|`enableDnsRoundRobin`|<span data-ttu-id="957d8-120">すべてのアドレス、または最初の 1 つだけホストの DNS 解決の戻り値の複数のインターネット プロトコル (IP) アドレスを持つ名前かどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="957d8-120">Specifies whether DNS resolutions of host names with multiple Internet Protocol (IP) addresses return all the addresses, or just the first one.</span></span> <span data-ttu-id="957d8-121">既定値は `false` です。</span><span class="sxs-lookup"><span data-stu-id="957d8-121">The default value is `false`.</span></span>|  
|`encryptionPolicy`|<span data-ttu-id="957d8-122">SSL や TLS セッションに適用する暗号化ポリシーを指定します、<xref:System.Net.ServicePointManager>インスタンス。</span><span class="sxs-lookup"><span data-stu-id="957d8-122">Specifies the encryption policy applied to an SSL/TLS session on a <xref:System.Net.ServicePointManager> instance.</span></span> <span data-ttu-id="957d8-123">使用可能な値がの値に等しい、<xref:System.Net.Security.EncryptionPolicy>列挙体。</span><span class="sxs-lookup"><span data-stu-id="957d8-123">The possible values are equivalent to the values for the <xref:System.Net.Security.EncryptionPolicy> enumeration.</span></span> <span data-ttu-id="957d8-124">使用<xref:System.Security.Authentication.CipherAlgorithmType.Null>暗号化ポリシーが設定されている場合は、必要な`NoEncryption`します。</span><span class="sxs-lookup"><span data-stu-id="957d8-124">The use of <xref:System.Security.Authentication.CipherAlgorithmType.Null> is required when the encryption policy is set to `NoEncryption`.</span></span> <span data-ttu-id="957d8-125">既定値は `RequireEncryption` です。</span><span class="sxs-lookup"><span data-stu-id="957d8-125">The default value is `RequireEncryption`.</span></span>|  
|`expect100Continue`|<span data-ttu-id="957d8-126">POST メソッドが受信することが予想されるかどうかを指定します、`100-continue`サーバーからの応答。</span><span class="sxs-lookup"><span data-stu-id="957d8-126">Specifies whether POST methods should expect to receive a `100-continue` response from the server.</span></span> <span data-ttu-id="957d8-127">既定値は `true` です。</span><span class="sxs-lookup"><span data-stu-id="957d8-127">The default value is `true`.</span></span>|  
|`useNagleAlgorithm`|<span data-ttu-id="957d8-128">サービス ポイントのマネージャーによって制御される接続で Nagle アルゴリズムを使用するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="957d8-128">Specifies whether connections controlled by the service point manager use the Nagle algorithm.</span></span> <span data-ttu-id="957d8-129">既定値は `true` です。</span><span class="sxs-lookup"><span data-stu-id="957d8-129">The default value is `true`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="957d8-130">子要素</span><span class="sxs-lookup"><span data-stu-id="957d8-130">Child Elements</span></span>  
 <span data-ttu-id="957d8-131">なし。</span><span class="sxs-lookup"><span data-stu-id="957d8-131">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="957d8-132">親要素</span><span class="sxs-lookup"><span data-stu-id="957d8-132">Parent Elements</span></span>  
  
|<span data-ttu-id="957d8-133">**要素**</span><span class="sxs-lookup"><span data-stu-id="957d8-133">**Element**</span></span>|<span data-ttu-id="957d8-134">**説明**</span><span class="sxs-lookup"><span data-stu-id="957d8-134">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="957d8-135">設定</span><span class="sxs-lookup"><span data-stu-id="957d8-135">Settings</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/settings-element-network-settings.md)|<span data-ttu-id="957d8-136"><xref:System.Net> 名前空間の基本的なネットワーク オプションを構成します。</span><span class="sxs-lookup"><span data-stu-id="957d8-136">Configures basic network options for the <xref:System.Net> namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="957d8-137">Remarks</span><span class="sxs-lookup"><span data-stu-id="957d8-137">Remarks</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="957d8-138">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="957d8-138">Configuration Files</span></span>  
 <span data-ttu-id="957d8-139">この要素は、アプリケーション構成ファイルまたはマシン構成ファイル (Machine.config) で使用できます。</span><span class="sxs-lookup"><span data-stu-id="957d8-139">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="957d8-140">関連項目</span><span class="sxs-lookup"><span data-stu-id="957d8-140">See also</span></span>

- <xref:System.Net.ServicePointManager>
- <xref:System.Net.Security.EncryptionPolicy>
- [<span data-ttu-id="957d8-141">ネットワーク設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="957d8-141">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
