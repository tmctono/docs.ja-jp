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
ms.openlocfilehash: 5e8ec13a0bb991accff080db502552e46913c66d
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64607508"
---
# <a name="socket-element-network-settings"></a><span data-ttu-id="b564f-102">\<ソケット > 要素 (ネットワーク設定)</span><span class="sxs-lookup"><span data-stu-id="b564f-102">\<socket> Element (Network Settings)</span></span>
<span data-ttu-id="b564f-103">ソケット操作が完了ポートを使用するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="b564f-103">Specifies whether socket operations use completion ports.</span></span>  
  
 <span data-ttu-id="b564f-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="b564f-104">\<configuration></span></span>  
<span data-ttu-id="b564f-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="b564f-105">\<system.net></span></span>  
<span data-ttu-id="b564f-106">\<settings></span><span class="sxs-lookup"><span data-stu-id="b564f-106">\<settings></span></span>  
<span data-ttu-id="b564f-107">\<socket></span><span class="sxs-lookup"><span data-stu-id="b564f-107">\<socket></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b564f-108">構文</span><span class="sxs-lookup"><span data-stu-id="b564f-108">Syntax</span></span>  
  
```xml  
<socket  
  alwaysUseCompletionPortsForConnect="true|false"  
  alwaysUseCompletionPortsForAccept="true|false"  
  ipProtectionLevel="EdgeRestricted|Restricted|Unrestricted|Unspecified"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b564f-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="b564f-109">Attributes and Elements</span></span>  
 <span data-ttu-id="b564f-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="b564f-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b564f-111">属性</span><span class="sxs-lookup"><span data-stu-id="b564f-111">Attributes</span></span>  
  
|<span data-ttu-id="b564f-112">**属性**</span><span class="sxs-lookup"><span data-stu-id="b564f-112">**Attribute**</span></span>|<span data-ttu-id="b564f-113">**説明**</span><span class="sxs-lookup"><span data-stu-id="b564f-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`alwaysUseCompletionPortsForAccept`|<span data-ttu-id="b564f-114">受け入れメソッド呼び出しの場合、ソケットで常に完了ポートを使用するかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="b564f-114">Indicates whether the socket should always use completion ports for Accept method calls.</span></span> <span data-ttu-id="b564f-115">既定値は `false` です。</span><span class="sxs-lookup"><span data-stu-id="b564f-115">The default value is `false`.</span></span>|  
|`alwaysUseCompletionPortsForConnect`|<span data-ttu-id="b564f-116">Connect メソッドの呼び出しの場合、ソケットで常に完了ポートを使用するかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="b564f-116">Indicates whether the socket should always use completion ports for Connect method calls.</span></span> <span data-ttu-id="b564f-117">既定値は `false` です。</span><span class="sxs-lookup"><span data-stu-id="b564f-117">The default value is `false`.</span></span>|  
|`ipProtectionLevel`|<span data-ttu-id="b564f-118">既定値を指定します<xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType>ソケットを使用します。</span><span class="sxs-lookup"><span data-stu-id="b564f-118">Specifies the default <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> to use for a socket.</span></span> <span data-ttu-id="b564f-119">既定値は、Windows のバージョンによって異なります。</span><span class="sxs-lookup"><span data-stu-id="b564f-119">The default value depends on the version of Windows.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b564f-120">子要素</span><span class="sxs-lookup"><span data-stu-id="b564f-120">Child Elements</span></span>  
 <span data-ttu-id="b564f-121">なし。</span><span class="sxs-lookup"><span data-stu-id="b564f-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b564f-122">親要素</span><span class="sxs-lookup"><span data-stu-id="b564f-122">Parent Elements</span></span>  
  
|<span data-ttu-id="b564f-123">**要素**</span><span class="sxs-lookup"><span data-stu-id="b564f-123">**Element**</span></span>|<span data-ttu-id="b564f-124">**説明**</span><span class="sxs-lookup"><span data-stu-id="b564f-124">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="b564f-125">settings</span><span class="sxs-lookup"><span data-stu-id="b564f-125">settings</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/settings-element-network-settings.md)|<span data-ttu-id="b564f-126"><xref:System.Net> 名前空間の基本的なネットワーク オプションを構成します。</span><span class="sxs-lookup"><span data-stu-id="b564f-126">Configures basic network options for the <xref:System.Net> namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b564f-127">Remarks</span><span class="sxs-lookup"><span data-stu-id="b564f-127">Remarks</span></span>  
 <span data-ttu-id="b564f-128">`alwaysUseCompletionPortsForAccept`と`alwaysUseCompletionPortsForConnect`内のクラスで属性を使用して、完了ポートの使用に関する既定の動作を指定、 <xref:System.Net.Sockets?displayProperty=nameWithType>.namespace します。</span><span class="sxs-lookup"><span data-stu-id="b564f-128">The `alwaysUseCompletionPortsForAccept` and `alwaysUseCompletionPortsForConnect` attributes are used to specify the default behavior regarding the use of completion ports by the classes in the <xref:System.Net.Sockets?displayProperty=nameWithType>.namespace.</span></span> <span data-ttu-id="b564f-129">高パフォーマンス サーバー アプリケーションは、完了ポートがお勧めします。</span><span class="sxs-lookup"><span data-stu-id="b564f-129">Completion ports are recommended for high performance server applications.</span></span>  
  
 <span data-ttu-id="b564f-130">既定値、`alwaysUseCompletionPortsForAccept`と`alwaysUseCompletionPortsForConnect`属性は**false**します。</span><span class="sxs-lookup"><span data-stu-id="b564f-130">The default value for the `alwaysUseCompletionPortsForAccept` and `alwaysUseCompletionPortsForConnect` attributes is **false**.</span></span>  
  
 <span data-ttu-id="b564f-131"><xref:System.Net.Configuration.SocketElement.AlwaysUseCompletionPortsForAccept%2A>の現在の値を取得するために使用できる、`alwaysUseCompletionPortsForAccept`該当する構成ファイルからの属性。</span><span class="sxs-lookup"><span data-stu-id="b564f-131">The <xref:System.Net.Configuration.SocketElement.AlwaysUseCompletionPortsForAccept%2A> can be used to get the current value of the `alwaysUseCompletionPortsForAccept` attribute from applicable configuration files.</span></span> <span data-ttu-id="b564f-132"><xref:System.Net.Configuration.SocketElement.AlwaysUseCompletionPortsForConnect%2A>の現在の値を取得するために使用できる、`alwaysUseCompletionPortsForConnect`該当する構成ファイルからの属性。</span><span class="sxs-lookup"><span data-stu-id="b564f-132">The <xref:System.Net.Configuration.SocketElement.AlwaysUseCompletionPortsForConnect%2A> can be used to get the current value of the `alwaysUseCompletionPortsForConnect` attribute from applicable configuration files.</span></span>  
  
 <span data-ttu-id="b564f-133">`ipProtectionLevel`属性を既定値を指定します<xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType>ソケットを使用します。</span><span class="sxs-lookup"><span data-stu-id="b564f-133">The `ipProtectionLevel` attribute specifies the default <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> to use for a socket.</span></span> <span data-ttu-id="b564f-134"><xref:System.Net.Configuration.SocketElement.IPProtectionLevel%2A>プロパティなど、リンク ローカルまたはサイト ローカル プレフィックスを同じアドレスを特定のスコープ、IPv6 ソケットの制限の構成を使用できます。</span><span class="sxs-lookup"><span data-stu-id="b564f-134">The <xref:System.Net.Configuration.SocketElement.IPProtectionLevel%2A> property enables configuration of a restriction for an IPv6 socket to a specified scope, such as addresses with the same link local or site local prefix.</span></span> <span data-ttu-id="b564f-135">このオプションにより、IPv6 ソケットに対するアクセス制限を設定できます。</span><span class="sxs-lookup"><span data-stu-id="b564f-135">This option enables applications to place access restrictions on IPv6 sockets.</span></span> <span data-ttu-id="b564f-136">この制限により、プライベート LAN で実行されるアプリケーションを外部からの攻撃に対して簡単かつ堅牢に強化できます。</span><span class="sxs-lookup"><span data-stu-id="b564f-136">Such restrictions enable an application running on a private LAN to simply and robustly harden itself against external attacks.</span></span> <span data-ttu-id="b564f-137">このオプションは、拡大変換されますか、適切な場合は、パブリックおよびプライベートのユーザーまたは必要に応じて、同じサイトにのみアクセスを制限することから無制限のアクセスを有効にすると、リッスン ソケットのスコープを絞り込みます。</span><span class="sxs-lookup"><span data-stu-id="b564f-137">This option widens or narrows the scope of a listening socket, enabling unrestricted access from public and private users when appropriate, or restricting access only to the same site, as required.</span></span>  
  
 <span data-ttu-id="b564f-138">これは、`ipProtectionLevel`属性の設定が最初に受信トラフィックのみに影響します。</span><span class="sxs-lookup"><span data-stu-id="b564f-138">This `ipProtectionLevel` attribute setting affects only initial incoming traffic:</span></span>  
  
- <span data-ttu-id="b564f-139">着信接続をソケットでリッスンしている TCP サーバー。</span><span class="sxs-lookup"><span data-stu-id="b564f-139">A TCP server listening for incoming connections on a socket.</span></span>  
  
- <span data-ttu-id="b564f-140">ソケットでのパケットを受信 UDP アプリケーションです。</span><span class="sxs-lookup"><span data-stu-id="b564f-140">A UDP application receiving a packet on a socket.</span></span>  
  
 <span data-ttu-id="b564f-141">この構成設定では既に確立されている TCP 接続が (トラフィックは両方向に無制限) には影響しません UDP パケットを送信するアプリケーションには影響しません。</span><span class="sxs-lookup"><span data-stu-id="b564f-141">This configuration setting does not affect already established TCP connections (traffic is unrestricted in both directions) and does not affect an application sending UDP packets.</span></span>  
  
 <span data-ttu-id="b564f-142">使用可能な値を`ipProtectionLevel`属性の設定が指定された定義済みの保護レベルに対応して、<xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType>列挙体として次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="b564f-142">The possible values for the `ipProtectionLevel` attribute setting correspond with the defined protection levels specified in the <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> enumeration as follows:</span></span>  
  
|<span data-ttu-id="b564f-143">**属性値**</span><span class="sxs-lookup"><span data-stu-id="b564f-143">**Attribute Value**</span></span>|<span data-ttu-id="b564f-144">**説明**</span><span class="sxs-lookup"><span data-stu-id="b564f-144">**Description**</span></span>|  
|-|-|  
|<span data-ttu-id="b564f-145">EdgeRestricted</span><span class="sxs-lookup"><span data-stu-id="b564f-145">EdgeRestricted</span></span>|<span data-ttu-id="b564f-146">IP 保護レベルはエッジ制限付きです。</span><span class="sxs-lookup"><span data-stu-id="b564f-146">The IP protection level is edge restricted.</span></span> <span data-ttu-id="b564f-147">この値は、インターネット経由で動作するように設計アプリケーションによって使用されます。</span><span class="sxs-lookup"><span data-stu-id="b564f-147">This value would be used by applications designed to operate across the Internet.</span></span> <span data-ttu-id="b564f-148">この設定は、Windows Teredo 実装を使用して、ネットワーク アドレス変換 (NAT) トラバーサルを許可しません。</span><span class="sxs-lookup"><span data-stu-id="b564f-148">This setting does not allow Network Address Translation (NAT) traversal using the Windows Teredo implementation.</span></span> <span data-ttu-id="b564f-149">これらのアプリケーションが IPv4 のファイアウォールをバイパスため、開かれたポートに送信するインターネット攻撃に対するアプリケーションのセキュリティを強化する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b564f-149">These applications may bypass IPv4 firewalls, so applications must be hardened against Internet attacks directed at the opened port.</span></span> <span data-ttu-id="b564f-150">Windows Server 2003 および Windows XP では、ソケットの IP 保護レベルの既定値はエッジ制限付きです。</span><span class="sxs-lookup"><span data-stu-id="b564f-150">On Windows Server 2003 and Windows XP, the default value for the IP Protection level on a socket is edge restricted.</span></span>|  
|<span data-ttu-id="b564f-151">Restricted</span><span class="sxs-lookup"><span data-stu-id="b564f-151">Restricted</span></span>|<span data-ttu-id="b564f-152">IP 保護レベルは、制限付きです。</span><span class="sxs-lookup"><span data-stu-id="b564f-152">The IP protection level is restricted.</span></span> <span data-ttu-id="b564f-153">この値については、インターネットのシナリオを実装しないイントラネット アプリケーションで使用します。</span><span class="sxs-lookup"><span data-stu-id="b564f-153">This value would be used by intranet applications that do not implement Internet scenarios.</span></span> <span data-ttu-id="b564f-154">これらのアプリケーションは通常、テストもインターネット スタイルの攻撃に対して強固です。</span><span class="sxs-lookup"><span data-stu-id="b564f-154">These applications are generally not tested or hardened against Internet-style attacks.</span></span> <span data-ttu-id="b564f-155">この設定は、受信トラフィックはリンク ローカルのみに制限されます。</span><span class="sxs-lookup"><span data-stu-id="b564f-155">This setting will limit the received traffic to link-local only.</span></span>|  
|<span data-ttu-id="b564f-156">無制限</span><span class="sxs-lookup"><span data-stu-id="b564f-156">Unrestricted</span></span>|<span data-ttu-id="b564f-157">IP 保護レベルは制限されません。</span><span class="sxs-lookup"><span data-stu-id="b564f-157">The IP protection level is unrestricted.</span></span> <span data-ttu-id="b564f-158">この値は組み込まれている IPv6 NAT traversal 機能を活用するアプリケーションを含め、インターネット経由で動作するようにデザインされたアプリケーションによって使用される Windows (Teredo の使用例) にします。</span><span class="sxs-lookup"><span data-stu-id="b564f-158">This value would be used by applications designed to operate across the Internet, including applications taking advantage of IPv6 NAT traversal capabilities built into Windows (Teredo, for example).</span></span> <span data-ttu-id="b564f-159">これらのアプリケーションが IPv4 のファイアウォールをバイパスため、開かれたポートに送信するインターネット攻撃に対するアプリケーションのセキュリティを強化する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b564f-159">These applications may bypass IPv4 firewalls, so applications must be hardened against Internet attacks directed at the opened port.</span></span> <span data-ttu-id="b564f-160">Windows Server 2008 R2 および Windows Vista では、ソケットの IP 保護レベルの既定値は制限されません。</span><span class="sxs-lookup"><span data-stu-id="b564f-160">On Windows Server 2008 R2 and Windows Vista, the default value for the IP Protection level on a socket is unrestricted.</span></span>|  
|<span data-ttu-id="b564f-161">指定されていません。</span><span class="sxs-lookup"><span data-stu-id="b564f-161">Unspecified</span></span>|<span data-ttu-id="b564f-162">IP 保護レベルでは、指定されていません。</span><span class="sxs-lookup"><span data-stu-id="b564f-162">The IP protection level is unspecified.</span></span> <span data-ttu-id="b564f-163">Windows 7 および Windows Server 2008 R2 では、ソケットの IP 保護レベルの既定値が指定されていません。</span><span class="sxs-lookup"><span data-stu-id="b564f-163">On Windows 7 and Windows Server 2008 R2, the default value for the IP Protection level on a socket is unspecified.</span></span>|  
  
 <span data-ttu-id="b564f-164">既定値、`ipProtectionLevel`属性が**未指定**します。</span><span class="sxs-lookup"><span data-stu-id="b564f-164">The default value for the `ipProtectionLevel` attribute is **Unspecified**.</span></span>  
  
 <span data-ttu-id="b564f-165"><xref:System.Net.Configuration.SocketElement.IPProtectionLevel%2A>プロパティを使用しての現在の値を取得すること、`ipProtectionLevel`該当する構成ファイルからの属性。</span><span class="sxs-lookup"><span data-stu-id="b564f-165">The <xref:System.Net.Configuration.SocketElement.IPProtectionLevel%2A> property can be used to get the current value of the `ipProtectionLevel` attribute from applicable configuration files.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="b564f-166">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="b564f-166">Configuration Files</span></span>  
 <span data-ttu-id="b564f-167">この要素は、アプリケーション構成ファイルまたはマシン構成ファイル (Machine.config) で使用できます。</span><span class="sxs-lookup"><span data-stu-id="b564f-167">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b564f-168">例</span><span class="sxs-lookup"><span data-stu-id="b564f-168">Example</span></span>  
 <span data-ttu-id="b564f-169">次の例は、完了ポートを使用することを指定する方法と、既定<xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType>制限する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b564f-169">The following example shows how to specify that completion ports should be used and that the default <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> should be unrestricted.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="b564f-170">関連項目</span><span class="sxs-lookup"><span data-stu-id="b564f-170">See also</span></span>

- <xref:System.Net?displayProperty=nameWithType>
- <xref:System.Net.Configuration.SocketElement?displayProperty=nameWithType>
- <xref:System.Net.Sockets?displayProperty=nameWithType>
- <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType>
- <xref:System.Net.Sockets.SocketOptionName.IPProtectionLevel?displayProperty=nameWithType>
- [<span data-ttu-id="b564f-171">ネットワーク設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="b564f-171">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
