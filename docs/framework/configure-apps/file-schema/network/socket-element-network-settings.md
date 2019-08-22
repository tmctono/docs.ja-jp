---
title: <socket> 要素 (ネットワーク設定)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/socket
- http://schemas.microsoft.com/.NetConfiguration/v2.0#socket
helpviewer_keywords:
- <socket> element
- socket element
ms.assetid: 366c634c-7d16-478f-aedf-053eda94a1a0
ms.openlocfilehash: aa455945b839ada4100138d5bdf9fc239376e5cb
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/21/2019
ms.locfileid: "69663982"
---
# <a name="socket-element-network-settings"></a><span data-ttu-id="cdfc8-102">\<socket> 要素 (ネットワーク設定)</span><span class="sxs-lookup"><span data-stu-id="cdfc8-102">\<socket> Element (Network Settings)</span></span>
<span data-ttu-id="cdfc8-103">ソケット操作が完了ポートを使用するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="cdfc8-103">Specifies whether socket operations use completion ports.</span></span>  
  
 <span data-ttu-id="cdfc8-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="cdfc8-104">\<configuration></span></span>  
<span data-ttu-id="cdfc8-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="cdfc8-105">\<system.net></span></span>  
<span data-ttu-id="cdfc8-106">\<settings></span><span class="sxs-lookup"><span data-stu-id="cdfc8-106">\<settings></span></span>  
<span data-ttu-id="cdfc8-107">\<socket></span><span class="sxs-lookup"><span data-stu-id="cdfc8-107">\<socket></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cdfc8-108">構文</span><span class="sxs-lookup"><span data-stu-id="cdfc8-108">Syntax</span></span>  
  
```xml  
<socket  
  alwaysUseCompletionPortsForConnect="true|false"  
  alwaysUseCompletionPortsForAccept="true|false"  
  ipProtectionLevel="EdgeRestricted|Restricted|Unrestricted|Unspecified"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cdfc8-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="cdfc8-109">Attributes and Elements</span></span>  
 <span data-ttu-id="cdfc8-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="cdfc8-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cdfc8-111">属性</span><span class="sxs-lookup"><span data-stu-id="cdfc8-111">Attributes</span></span>  
  
|<span data-ttu-id="cdfc8-112">**属性**</span><span class="sxs-lookup"><span data-stu-id="cdfc8-112">**Attribute**</span></span>|<span data-ttu-id="cdfc8-113">**説明**</span><span class="sxs-lookup"><span data-stu-id="cdfc8-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`alwaysUseCompletionPortsForAccept`|<span data-ttu-id="cdfc8-114">Accept メソッド呼び出しに対して、ソケットが常に完了ポートを使用する必要があるかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="cdfc8-114">Indicates whether the socket should always use completion ports for Accept method calls.</span></span> <span data-ttu-id="cdfc8-115">既定値は `false` です。</span><span class="sxs-lookup"><span data-stu-id="cdfc8-115">The default value is `false`.</span></span>|  
|`alwaysUseCompletionPortsForConnect`|<span data-ttu-id="cdfc8-116">接続メソッドの呼び出しで、ソケットが常に完了ポートを使用する必要があるかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="cdfc8-116">Indicates whether the socket should always use completion ports for Connect method calls.</span></span> <span data-ttu-id="cdfc8-117">既定値は `false` です。</span><span class="sxs-lookup"><span data-stu-id="cdfc8-117">The default value is `false`.</span></span>|  
|`ipProtectionLevel`|<span data-ttu-id="cdfc8-118">ソケットに使用<xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType>する既定のを指定します。</span><span class="sxs-lookup"><span data-stu-id="cdfc8-118">Specifies the default <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> to use for a socket.</span></span> <span data-ttu-id="cdfc8-119">既定値は、Windows のバージョンによって異なります。</span><span class="sxs-lookup"><span data-stu-id="cdfc8-119">The default value depends on the version of Windows.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="cdfc8-120">子要素</span><span class="sxs-lookup"><span data-stu-id="cdfc8-120">Child Elements</span></span>  
 <span data-ttu-id="cdfc8-121">なし。</span><span class="sxs-lookup"><span data-stu-id="cdfc8-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="cdfc8-122">親要素</span><span class="sxs-lookup"><span data-stu-id="cdfc8-122">Parent Elements</span></span>  
  
|<span data-ttu-id="cdfc8-123">**要素**</span><span class="sxs-lookup"><span data-stu-id="cdfc8-123">**Element**</span></span>|<span data-ttu-id="cdfc8-124">**説明**</span><span class="sxs-lookup"><span data-stu-id="cdfc8-124">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="cdfc8-125">settings</span><span class="sxs-lookup"><span data-stu-id="cdfc8-125">settings</span></span>](settings-element-network-settings.md)|<span data-ttu-id="cdfc8-126"><xref:System.Net> 名前空間の基本的なネットワーク オプションを構成します。</span><span class="sxs-lookup"><span data-stu-id="cdfc8-126">Configures basic network options for the <xref:System.Net> namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cdfc8-127">Remarks</span><span class="sxs-lookup"><span data-stu-id="cdfc8-127">Remarks</span></span>  
 <span data-ttu-id="cdfc8-128">属性`alwaysUseCompletionPortsForAccept` <xref:System.Net.Sockets?displayProperty=nameWithType>と`alwaysUseCompletionPortsForConnect`属性は、名前空間のクラスによる完了ポートの使用に関する既定の動作を指定するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="cdfc8-128">The `alwaysUseCompletionPortsForAccept` and `alwaysUseCompletionPortsForConnect` attributes are used to specify the default behavior regarding the use of completion ports by the classes in the <xref:System.Net.Sockets?displayProperty=nameWithType>.namespace.</span></span> <span data-ttu-id="cdfc8-129">ハイパフォーマンスサーバーアプリケーションでは、完了ポートをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="cdfc8-129">Completion ports are recommended for high performance server applications.</span></span>  
  
 <span data-ttu-id="cdfc8-130">属性`alwaysUseCompletionPortsForAccept`と`alwaysUseCompletionPortsForConnect`属性の既定値は**false**です。</span><span class="sxs-lookup"><span data-stu-id="cdfc8-130">The default value for the `alwaysUseCompletionPortsForAccept` and `alwaysUseCompletionPortsForConnect` attributes is **false**.</span></span>  
  
 <span data-ttu-id="cdfc8-131">は<xref:System.Net.Configuration.SocketElement.AlwaysUseCompletionPortsForAccept%2A> 、適用可能`alwaysUseCompletionPortsForAccept`な構成ファイルから属性の現在の値を取得するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="cdfc8-131">The <xref:System.Net.Configuration.SocketElement.AlwaysUseCompletionPortsForAccept%2A> can be used to get the current value of the `alwaysUseCompletionPortsForAccept` attribute from applicable configuration files.</span></span> <span data-ttu-id="cdfc8-132">は<xref:System.Net.Configuration.SocketElement.AlwaysUseCompletionPortsForConnect%2A> 、適用可能`alwaysUseCompletionPortsForConnect`な構成ファイルから属性の現在の値を取得するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="cdfc8-132">The <xref:System.Net.Configuration.SocketElement.AlwaysUseCompletionPortsForConnect%2A> can be used to get the current value of the `alwaysUseCompletionPortsForConnect` attribute from applicable configuration files.</span></span>  
  
 <span data-ttu-id="cdfc8-133">属性`ipProtectionLevel`は、ソケットに<xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType>使用する既定のを指定します。</span><span class="sxs-lookup"><span data-stu-id="cdfc8-133">The `ipProtectionLevel` attribute specifies the default <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> to use for a socket.</span></span> <span data-ttu-id="cdfc8-134">プロパティ<xref:System.Net.Configuration.SocketElement.IPProtectionLevel%2A>を使用すると、同じリンクローカルまたはサイトローカルプレフィックスを持つアドレスなど、指定されたスコープに IPv6 ソケットの制限を構成できます。</span><span class="sxs-lookup"><span data-stu-id="cdfc8-134">The <xref:System.Net.Configuration.SocketElement.IPProtectionLevel%2A> property enables configuration of a restriction for an IPv6 socket to a specified scope, such as addresses with the same link local or site local prefix.</span></span> <span data-ttu-id="cdfc8-135">このオプションを使用すると、アプリケーションは IPv6 ソケットにアクセス制限を設けることができます。</span><span class="sxs-lookup"><span data-stu-id="cdfc8-135">This option enables applications to place access restrictions on IPv6 sockets.</span></span> <span data-ttu-id="cdfc8-136">この制限により、プライベート LAN で実行されるアプリケーションを外部からの攻撃に対して簡単かつ堅牢に強化できます。</span><span class="sxs-lookup"><span data-stu-id="cdfc8-136">Such restrictions enable an application running on a private LAN to simply and robustly harden itself against external attacks.</span></span> <span data-ttu-id="cdfc8-137">このオプションは、リッスンしているソケットの範囲を拡大または縮小し、必要に応じてパブリックユーザーおよびプライベートユーザーからの無制限のアクセスを有効にするか、必要に応じて同じサイトへのアクセスのみを制限します。</span><span class="sxs-lookup"><span data-stu-id="cdfc8-137">This option widens or narrows the scope of a listening socket, enabling unrestricted access from public and private users when appropriate, or restricting access only to the same site, as required.</span></span>  
  
 <span data-ttu-id="cdfc8-138">この`ipProtectionLevel`属性設定は、初期の受信トラフィックのみに影響します。</span><span class="sxs-lookup"><span data-stu-id="cdfc8-138">This `ipProtectionLevel` attribute setting affects only initial incoming traffic:</span></span>  
  
- <span data-ttu-id="cdfc8-139">ソケットで着信接続をリッスンしている TCP サーバー。</span><span class="sxs-lookup"><span data-stu-id="cdfc8-139">A TCP server listening for incoming connections on a socket.</span></span>  
  
- <span data-ttu-id="cdfc8-140">ソケットでパケットを受信する UDP アプリケーション。</span><span class="sxs-lookup"><span data-stu-id="cdfc8-140">A UDP application receiving a packet on a socket.</span></span>  
  
 <span data-ttu-id="cdfc8-141">この構成設定は、既に確立されている TCP 接続には影響しません (トラフィックは両方向に制限されません)。また、UDP パケットを送信するアプリケーションには影響しません。</span><span class="sxs-lookup"><span data-stu-id="cdfc8-141">This configuration setting does not affect already established TCP connections (traffic is unrestricted in both directions) and does not affect an application sending UDP packets.</span></span>  
  
 <span data-ttu-id="cdfc8-142">`ipProtectionLevel`属性の設定に使用できる値は、次のよう<xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType>に、列挙で指定されている定義済みの保護レベルに対応しています。</span><span class="sxs-lookup"><span data-stu-id="cdfc8-142">The possible values for the `ipProtectionLevel` attribute setting correspond with the defined protection levels specified in the <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> enumeration as follows:</span></span>  
  
|<span data-ttu-id="cdfc8-143">**属性値**</span><span class="sxs-lookup"><span data-stu-id="cdfc8-143">**Attribute Value**</span></span>|<span data-ttu-id="cdfc8-144">**説明**</span><span class="sxs-lookup"><span data-stu-id="cdfc8-144">**Description**</span></span>|  
|-|-|  
|<span data-ttu-id="cdfc8-145">EdgeRestricted</span><span class="sxs-lookup"><span data-stu-id="cdfc8-145">EdgeRestricted</span></span>|<span data-ttu-id="cdfc8-146">IP 保護レベルは edge で制限されています。</span><span class="sxs-lookup"><span data-stu-id="cdfc8-146">The IP protection level is edge restricted.</span></span> <span data-ttu-id="cdfc8-147">この値は、インターネット経由で動作するように設計されたアプリケーションによって使用されます。</span><span class="sxs-lookup"><span data-stu-id="cdfc8-147">This value would be used by applications designed to operate across the Internet.</span></span> <span data-ttu-id="cdfc8-148">この設定では、Windows Teredo 実装を使用したネットワークアドレス変換 (NAT) トラバーサルは許可されません。</span><span class="sxs-lookup"><span data-stu-id="cdfc8-148">This setting does not allow Network Address Translation (NAT) traversal using the Windows Teredo implementation.</span></span> <span data-ttu-id="cdfc8-149">これらのアプリケーションは IPv4 ファイアウォールをバイパスする可能性があるため、開いているポートを使用しているインターネット攻撃に対してアプリケーションを強化する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cdfc8-149">These applications may bypass IPv4 firewalls, so applications must be hardened against Internet attacks directed at the opened port.</span></span> <span data-ttu-id="cdfc8-150">Windows Server 2003 および Windows XP では、ソケットの IP 保護レベルの既定値はエッジに制限されています。</span><span class="sxs-lookup"><span data-stu-id="cdfc8-150">On Windows Server 2003 and Windows XP, the default value for the IP Protection level on a socket is edge restricted.</span></span>|  
|<span data-ttu-id="cdfc8-151">Restricted</span><span class="sxs-lookup"><span data-stu-id="cdfc8-151">Restricted</span></span>|<span data-ttu-id="cdfc8-152">IP 保護レベルは制限されています。</span><span class="sxs-lookup"><span data-stu-id="cdfc8-152">The IP protection level is restricted.</span></span> <span data-ttu-id="cdfc8-153">この値は、インターネットのシナリオを実装しないイントラネットアプリケーションで使用されます。</span><span class="sxs-lookup"><span data-stu-id="cdfc8-153">This value would be used by intranet applications that do not implement Internet scenarios.</span></span> <span data-ttu-id="cdfc8-154">これらのアプリケーションは、通常、インターネットスタイルの攻撃に対してテストまたはセキュリティで保護されていません。</span><span class="sxs-lookup"><span data-stu-id="cdfc8-154">These applications are generally not tested or hardened against Internet-style attacks.</span></span> <span data-ttu-id="cdfc8-155">この設定により、受信したトラフィックがリンクローカルのみに制限されます。</span><span class="sxs-lookup"><span data-stu-id="cdfc8-155">This setting will limit the received traffic to link-local only.</span></span>|  
|<span data-ttu-id="cdfc8-156">[無制限]</span><span class="sxs-lookup"><span data-stu-id="cdfc8-156">Unrestricted</span></span>|<span data-ttu-id="cdfc8-157">IP 保護レベルは無制限です。</span><span class="sxs-lookup"><span data-stu-id="cdfc8-157">The IP protection level is unrestricted.</span></span> <span data-ttu-id="cdfc8-158">この値は、インターネット経由で動作するように設計されたアプリケーション (たとえば、Windows に組み込まれた IPv6 NAT トラバーサル機能を利用するアプリケーションなど) によって使用されます。</span><span class="sxs-lookup"><span data-stu-id="cdfc8-158">This value would be used by applications designed to operate across the Internet, including applications taking advantage of IPv6 NAT traversal capabilities built into Windows (Teredo, for example).</span></span> <span data-ttu-id="cdfc8-159">これらのアプリケーションは IPv4 ファイアウォールをバイパスする可能性があるため、開いているポートを使用しているインターネット攻撃に対してアプリケーションを強化する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cdfc8-159">These applications may bypass IPv4 firewalls, so applications must be hardened against Internet attacks directed at the opened port.</span></span> <span data-ttu-id="cdfc8-160">Windows Server 2008 R2 および Windows Vista では、ソケットの IP 保護レベルの既定値は無制限です。</span><span class="sxs-lookup"><span data-stu-id="cdfc8-160">On Windows Server 2008 R2 and Windows Vista, the default value for the IP Protection level on a socket is unrestricted.</span></span>|  
|<span data-ttu-id="cdfc8-161">[未指定]</span><span class="sxs-lookup"><span data-stu-id="cdfc8-161">Unspecified</span></span>|<span data-ttu-id="cdfc8-162">IP 保護レベルが指定されていません。</span><span class="sxs-lookup"><span data-stu-id="cdfc8-162">The IP protection level is unspecified.</span></span> <span data-ttu-id="cdfc8-163">Windows 7 と Windows Server 2008 R2 では、ソケットの IP 保護レベルの既定値は指定されていません。</span><span class="sxs-lookup"><span data-stu-id="cdfc8-163">On Windows 7 and Windows Server 2008 R2, the default value for the IP Protection level on a socket is unspecified.</span></span>|  
  
 <span data-ttu-id="cdfc8-164">`ipProtectionLevel`属性の既定値は**指定**されていません。</span><span class="sxs-lookup"><span data-stu-id="cdfc8-164">The default value for the `ipProtectionLevel` attribute is **Unspecified**.</span></span>  
  
 <span data-ttu-id="cdfc8-165">プロパティ<xref:System.Net.Configuration.SocketElement.IPProtectionLevel%2A>は、適用可能`ipProtectionLevel`な構成ファイルから属性の現在の値を取得するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="cdfc8-165">The <xref:System.Net.Configuration.SocketElement.IPProtectionLevel%2A> property can be used to get the current value of the `ipProtectionLevel` attribute from applicable configuration files.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="cdfc8-166">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="cdfc8-166">Configuration Files</span></span>  
 <span data-ttu-id="cdfc8-167">この要素は、アプリケーション構成ファイルまたはマシン構成ファイル (Machine.config) で使用できます。</span><span class="sxs-lookup"><span data-stu-id="cdfc8-167">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="cdfc8-168">例</span><span class="sxs-lookup"><span data-stu-id="cdfc8-168">Example</span></span>  
 <span data-ttu-id="cdfc8-169">次の例では、完了ポートを使用するように指定する方法と<xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> 、既定値を無制限にすることを指定する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="cdfc8-169">The following example shows how to specify that completion ports should be used and that the default <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> should be unrestricted.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <settings>  
      <socket  
        alwaysUseCompletionPortsForAccept="true"  
        alwaysUseCompletionPortsForConnect="true"  
        ipProtectionLevel="Unrestricted"  
       />  
    </settings>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="cdfc8-170">関連項目</span><span class="sxs-lookup"><span data-stu-id="cdfc8-170">See also</span></span>

- <xref:System.Net?displayProperty=nameWithType>
- <xref:System.Net.Configuration.SocketElement?displayProperty=nameWithType>
- <xref:System.Net.Sockets?displayProperty=nameWithType>
- <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType>
- <xref:System.Net.Sockets.SocketOptionName.IPProtectionLevel?displayProperty=nameWithType>
- [<span data-ttu-id="cdfc8-171">ネットワーク設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="cdfc8-171">Network Settings Schema</span></span>](index.md)
