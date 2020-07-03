---
title: IPv6 の有効化と無効化
description: 次の構成手順に従って、IPv6 プロトコルの使用を有効にします。これには、コンピューターまたはアプリケーションの構成ファイルの変更も含まれます。
ms.date: 03/30/2017
ms.assetid: 6408d3ef-c9ba-49d9-b15e-fe74bd3ef031
ms.openlocfilehash: 7729647b09df20a98d5d639a641cb0a31f557330
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "84502614"
---
# <a name="enabling-and-disabling-ipv6"></a><span data-ttu-id="72598-103">IPv6 の有効化と無効化</span><span class="sxs-lookup"><span data-stu-id="72598-103">Enabling and Disabling IPv6</span></span>
<span data-ttu-id="72598-104">IPv6 プロトコルを使用するには、IPv6 をサポートしているオペレーティング システムのバージョンを実行していることを確認し、オペレーティング システムとネットワーク クラスが正しく構成されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="72598-104">To use the IPv6 protocol, ensure that you are running a version of the operating system that supports IPv6 and ensure that the operating system and the networking classes are configured properly.</span></span>  
  
## <a name="configuration-steps"></a><span data-ttu-id="72598-105">構成手順</span><span class="sxs-lookup"><span data-stu-id="72598-105">Configuration Steps</span></span>  
 <span data-ttu-id="72598-106">次の表に、さまざまな構成を示します。</span><span class="sxs-lookup"><span data-stu-id="72598-106">The following table lists various configurations</span></span>  
  
|<span data-ttu-id="72598-107">オペレーティング システムが IPv6 に対応しているか</span><span class="sxs-lookup"><span data-stu-id="72598-107">Operating system IPv6-enabled?</span></span>|<span data-ttu-id="72598-108">ネットワーク クラスが IPv6 に対応しているか</span><span class="sxs-lookup"><span data-stu-id="72598-108">Networking classes IPv6-enabled?</span></span>|<span data-ttu-id="72598-109">説明</span><span class="sxs-lookup"><span data-stu-id="72598-109">Description</span></span>|  
|-------------------------------------|---------------------------------------|-----------------|  
|<span data-ttu-id="72598-110">いいえ</span><span class="sxs-lookup"><span data-stu-id="72598-110">No</span></span>|<span data-ttu-id="72598-111">いいえ</span><span class="sxs-lookup"><span data-stu-id="72598-111">No</span></span>|<span data-ttu-id="72598-112">IPv6 アドレスを解析できます。</span><span class="sxs-lookup"><span data-stu-id="72598-112">Can parse IPv6 addresses.</span></span>|  
|<span data-ttu-id="72598-113">いいえ</span><span class="sxs-lookup"><span data-stu-id="72598-113">No</span></span>|<span data-ttu-id="72598-114">はい</span><span class="sxs-lookup"><span data-stu-id="72598-114">Yes</span></span>|<span data-ttu-id="72598-115">IPv6 アドレスを解析できます。</span><span class="sxs-lookup"><span data-stu-id="72598-115">Can parse IPv6 addresses.</span></span>|  
|<span data-ttu-id="72598-116">はい</span><span class="sxs-lookup"><span data-stu-id="72598-116">Yes</span></span>|<span data-ttu-id="72598-117">いいえ</span><span class="sxs-lookup"><span data-stu-id="72598-117">No</span></span>|<span data-ttu-id="72598-118">IPv6 アドレスを解析し、旧式マークが付けられていない名前解決のメソッドを使用して、IPv6 アドレスを解決できます。</span><span class="sxs-lookup"><span data-stu-id="72598-118">Can parse IPv6 addresses and resolve IPv6 addresses using name resolution methods not marked obsolete.</span></span>|  
|<span data-ttu-id="72598-119">はい</span><span class="sxs-lookup"><span data-stu-id="72598-119">Yes</span></span>|<span data-ttu-id="72598-120">はい</span><span class="sxs-lookup"><span data-stu-id="72598-120">Yes</span></span>|<span data-ttu-id="72598-121">IPv6 アドレスを解析し、旧式マークが付けられているものも含め、すべてのメソッドを使用して IPv6 アドレスを解決できます。</span><span class="sxs-lookup"><span data-stu-id="72598-121">Can parse and resolve IPv6 addresses using all methods including those marked obsolete.</span></span>|  
  
 <span data-ttu-id="72598-122">System.Net 名前空間のすべてのクラスに対して IPv6 のサポートを有効にするには、コンピューターの構成ファイルまたはアプリケーションの構成ファイルを変更する必要があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="72598-122">Be aware that to enable the IPv6 support for all classes in the System.Net namespace, you must modify the computer configuration file or the configuration file for the application.</span></span> <span data-ttu-id="72598-123">アプリケーション構成ファイルは、コンピューターの構成ファイルよりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="72598-123">The configuration file for an application has precedence over the computer configuration file.</span></span>  
  
 <span data-ttu-id="72598-124">IPv6 のサポートを有効にするようにコンピューター構成ファイル *machine.config* を変更する方法の例については、「[方法: IPv6 のサポートを有効にするようにコンピューター構成ファイルを変更する](how-to-modify-the-computer-configuration-file-to-enable-ipv6-support.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="72598-124">For an example of how to modify the computer configuration file, *machine.config*, to enable Ipv6 support see, [How to: Modify the Computer Configuration File to Enable Ipv6 Support](how-to-modify-the-computer-configuration-file-to-enable-ipv6-support.md).</span></span> <span data-ttu-id="72598-125">また、オペレーティング システムの IPv6 のサポートが有効になっていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="72598-125">Also, ensure that the IPv6 support is enabled for the operating system.</span></span>  
  
 <span data-ttu-id="72598-126">.NET Framework には、構成ファイル内に次のように設定された構成スイッチがあります。</span><span class="sxs-lookup"><span data-stu-id="72598-126">The .NET Framework has a configuration switch set in a configuration file as follows</span></span>  
  
```xml  
<system.net>  
  ...  
  <settings>  
    ...  
    <ipv6 enabled="true"/>  
    ...  
  </settings>  
  ...  
</system.net>  
```  
  
 <span data-ttu-id="72598-127">.NET Framework バージョン 1.1 以前では、**ipv6 enabled** 構成スイッチの値で <xref:System.Net.Dns?displayProperty=nameWithType> クラスのメンバーが IPv6 アドレスを返すかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="72598-127">For .NET Framework version 1.1 and earlier, the value of the **ipv6 enabled** configuration switch specifies whether members of the <xref:System.Net.Dns?displayProperty=nameWithType> class return IPv6 addresses.</span></span>  
  
 <span data-ttu-id="72598-128">.NET Framework バージョン 2.0 以降では、Windows が IPv6 をサポートしている場合、<xref:System.Net.Dns?displayProperty=nameWithType> クラスのメンバー (<xref:System.Net.Dns.GetHostEntry%2A?displayProperty=nameWithType> メソッドなど) が 1 つの制限付きで IPv6 アドレスを返します。</span><span class="sxs-lookup"><span data-stu-id="72598-128">For .NET Framework version 2.0 and later, if Windows supports IPv6, then members of the <xref:System.Net.Dns?displayProperty=nameWithType> class, (for example, the <xref:System.Net.Dns.GetHostEntry%2A?displayProperty=nameWithType> method), will return IPv6 addresses with one limitation.</span></span> <span data-ttu-id="72598-129">DNS <xref:System.Net.Dns?displayProperty=nameWithType> の古いメンバー (<xref:System.Net.Dns.Resolve%2A?displayProperty=nameWithType> メソッドなど) は、構成ファイル内の ipv6 enabled 設定の値を読み取り、認識します。</span><span class="sxs-lookup"><span data-stu-id="72598-129">Obsolete members of the DNS <xref:System.Net.Dns?displayProperty=nameWithType> (for example, the <xref:System.Net.Dns.Resolve%2A?displayProperty=nameWithType> method) will read and recognize the value in the configuration file for the ipv6 enabled setting.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72598-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="72598-130">See also</span></span>

- [<span data-ttu-id="72598-131">インターネット プロトコル バージョン 6</span><span class="sxs-lookup"><span data-stu-id="72598-131">Internet Protocol Version 6</span></span>](internet-protocol-version-6.md)
- [<span data-ttu-id="72598-132">ソケット</span><span class="sxs-lookup"><span data-stu-id="72598-132">Sockets</span></span>](sockets.md)
- [<span data-ttu-id="72598-133">ネットワーク設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="72598-133">Network Settings Schema</span></span>](../configure-apps/file-schema/network/index.md)
- [<span data-ttu-id="72598-134">\<ipv6> 要素 (ネットワーク設定)</span><span class="sxs-lookup"><span data-stu-id="72598-134">\<ipv6> Element (Network Settings)</span></span>](../configure-apps/file-schema/network/ipv6-element-network-settings.md)
