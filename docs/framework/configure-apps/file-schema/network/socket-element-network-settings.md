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
ms.openlocfilehash: 0e2b369eccfbc658a790ef61a961315a88361669
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "74089087"
---
# <a name="socket-element-network-settings"></a><span data-ttu-id="466cc-102">\<socket> 要素 (ネットワーク設定)</span><span class="sxs-lookup"><span data-stu-id="466cc-102">\<socket> Element (Network Settings)</span></span>
<span data-ttu-id="466cc-103">ソケット操作が完了ポートを使用するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="466cc-103">Specifies whether socket operations use completion ports.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<settings>**](settings-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<socket>**

## <a name="syntax"></a><span data-ttu-id="466cc-104">構文</span><span class="sxs-lookup"><span data-stu-id="466cc-104">Syntax</span></span>  
  
```xml  
<socket  
  alwaysUseCompletionPortsForConnect="true|false"  
  alwaysUseCompletionPortsForAccept="true|false"  
  ipProtectionLevel="EdgeRestricted|Restricted|Unrestricted|Unspecified"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="466cc-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="466cc-105">Attributes and Elements</span></span>  
 <span data-ttu-id="466cc-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="466cc-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="466cc-107">属性</span><span class="sxs-lookup"><span data-stu-id="466cc-107">Attributes</span></span>  
  
|<span data-ttu-id="466cc-108">**属性**</span><span class="sxs-lookup"><span data-stu-id="466cc-108">**Attribute**</span></span>|<span data-ttu-id="466cc-109">**説明**</span><span class="sxs-lookup"><span data-stu-id="466cc-109">**Description**</span></span>|  
|-------------------|---------------------|  
|`alwaysUseCompletionPortsForAccept`|<span data-ttu-id="466cc-110">Accept メソッド呼び出しに対して、ソケットが常に完了ポートを使用する必要があるかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="466cc-110">Indicates whether the socket should always use completion ports for Accept method calls.</span></span> <span data-ttu-id="466cc-111">既定値は `false` です。</span><span class="sxs-lookup"><span data-stu-id="466cc-111">The default value is `false`.</span></span>|  
|`alwaysUseCompletionPortsForConnect`|<span data-ttu-id="466cc-112">接続メソッドの呼び出しで、ソケットが常に完了ポートを使用する必要があるかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="466cc-112">Indicates whether the socket should always use completion ports for Connect method calls.</span></span> <span data-ttu-id="466cc-113">既定値は `false` です。</span><span class="sxs-lookup"><span data-stu-id="466cc-113">The default value is `false`.</span></span>|  
|`ipProtectionLevel`|<span data-ttu-id="466cc-114">ソケットに使用する既定のを指定し <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> ます。</span><span class="sxs-lookup"><span data-stu-id="466cc-114">Specifies the default <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> to use for a socket.</span></span> <span data-ttu-id="466cc-115">既定値は、Windows のバージョンによって異なります。</span><span class="sxs-lookup"><span data-stu-id="466cc-115">The default value depends on the version of Windows.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="466cc-116">子要素</span><span class="sxs-lookup"><span data-stu-id="466cc-116">Child Elements</span></span>  
 <span data-ttu-id="466cc-117">なし。</span><span class="sxs-lookup"><span data-stu-id="466cc-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="466cc-118">親要素</span><span class="sxs-lookup"><span data-stu-id="466cc-118">Parent Elements</span></span>  
  
|<span data-ttu-id="466cc-119">**要素**</span><span class="sxs-lookup"><span data-stu-id="466cc-119">**Element**</span></span>|<span data-ttu-id="466cc-120">**説明**</span><span class="sxs-lookup"><span data-stu-id="466cc-120">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="466cc-121">設定</span><span class="sxs-lookup"><span data-stu-id="466cc-121">settings</span></span>](settings-element-network-settings.md)|<span data-ttu-id="466cc-122"><xref:System.Net> 名前空間の基本的なネットワーク オプションを構成します。</span><span class="sxs-lookup"><span data-stu-id="466cc-122">Configures basic network options for the <xref:System.Net> namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="466cc-123">解説</span><span class="sxs-lookup"><span data-stu-id="466cc-123">Remarks</span></span>  
 <span data-ttu-id="466cc-124">`alwaysUseCompletionPortsForAccept`属性と `alwaysUseCompletionPortsForConnect` 属性は、名前空間のクラスによる完了ポートの使用に関する既定の動作を指定するために使用されます。 <xref:System.Net.Sockets?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="466cc-124">The `alwaysUseCompletionPortsForAccept` and `alwaysUseCompletionPortsForConnect` attributes are used to specify the default behavior regarding the use of completion ports by the classes in the <xref:System.Net.Sockets?displayProperty=nameWithType>.namespace.</span></span> <span data-ttu-id="466cc-125">ハイパフォーマンスサーバーアプリケーションでは、完了ポートをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="466cc-125">Completion ports are recommended for high performance server applications.</span></span>  
  
 <span data-ttu-id="466cc-126">`alwaysUseCompletionPortsForAccept`属性と属性の既定値 `alwaysUseCompletionPortsForConnect` は**false**です。</span><span class="sxs-lookup"><span data-stu-id="466cc-126">The default value for the `alwaysUseCompletionPortsForAccept` and `alwaysUseCompletionPortsForConnect` attributes is **false**.</span></span>  
  
 <span data-ttu-id="466cc-127">は、 <xref:System.Net.Configuration.SocketElement.AlwaysUseCompletionPortsForAccept%2A> 適用可能な `alwaysUseCompletionPortsForAccept` 構成ファイルから属性の現在の値を取得するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="466cc-127">The <xref:System.Net.Configuration.SocketElement.AlwaysUseCompletionPortsForAccept%2A> can be used to get the current value of the `alwaysUseCompletionPortsForAccept` attribute from applicable configuration files.</span></span> <span data-ttu-id="466cc-128">は、 <xref:System.Net.Configuration.SocketElement.AlwaysUseCompletionPortsForConnect%2A> 適用可能な `alwaysUseCompletionPortsForConnect` 構成ファイルから属性の現在の値を取得するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="466cc-128">The <xref:System.Net.Configuration.SocketElement.AlwaysUseCompletionPortsForConnect%2A> can be used to get the current value of the `alwaysUseCompletionPortsForConnect` attribute from applicable configuration files.</span></span>  
  
 <span data-ttu-id="466cc-129">属性は、 `ipProtectionLevel` ソケットに使用する既定のを指定し <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> ます。</span><span class="sxs-lookup"><span data-stu-id="466cc-129">The `ipProtectionLevel` attribute specifies the default <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> to use for a socket.</span></span> <span data-ttu-id="466cc-130"><xref:System.Net.Configuration.SocketElement.IPProtectionLevel%2A>プロパティを使用すると、同じリンクローカルまたはサイトローカルプレフィックスを持つアドレスなど、指定されたスコープに IPv6 ソケットの制限を構成できます。</span><span class="sxs-lookup"><span data-stu-id="466cc-130">The <xref:System.Net.Configuration.SocketElement.IPProtectionLevel%2A> property enables configuration of a restriction for an IPv6 socket to a specified scope, such as addresses with the same link local or site local prefix.</span></span> <span data-ttu-id="466cc-131">このオプションを使用すると、アプリケーションは IPv6 ソケットにアクセス制限を設けることができます。</span><span class="sxs-lookup"><span data-stu-id="466cc-131">This option enables applications to place access restrictions on IPv6 sockets.</span></span> <span data-ttu-id="466cc-132">この制限により、プライベート LAN で実行されるアプリケーションを外部からの攻撃に対して簡単かつ堅牢に強化できます。</span><span class="sxs-lookup"><span data-stu-id="466cc-132">Such restrictions enable an application running on a private LAN to simply and robustly harden itself against external attacks.</span></span> <span data-ttu-id="466cc-133">このオプションは、リッスンしているソケットの範囲を拡大または縮小し、必要に応じてパブリックユーザーおよびプライベートユーザーからの無制限のアクセスを有効にするか、必要に応じて同じサイトへのアクセスのみを制限します。</span><span class="sxs-lookup"><span data-stu-id="466cc-133">This option widens or narrows the scope of a listening socket, enabling unrestricted access from public and private users when appropriate, or restricting access only to the same site, as required.</span></span>  
  
 <span data-ttu-id="466cc-134">この `ipProtectionLevel` 属性設定は、初期の受信トラフィックのみに影響します。</span><span class="sxs-lookup"><span data-stu-id="466cc-134">This `ipProtectionLevel` attribute setting affects only initial incoming traffic:</span></span>  
  
- <span data-ttu-id="466cc-135">ソケットで着信接続をリッスンしている TCP サーバー。</span><span class="sxs-lookup"><span data-stu-id="466cc-135">A TCP server listening for incoming connections on a socket.</span></span>  
  
- <span data-ttu-id="466cc-136">ソケットでパケットを受信する UDP アプリケーション。</span><span class="sxs-lookup"><span data-stu-id="466cc-136">A UDP application receiving a packet on a socket.</span></span>  
  
 <span data-ttu-id="466cc-137">この構成設定は、既に確立されている TCP 接続には影響しません (トラフィックは両方向に制限されません)。また、UDP パケットを送信するアプリケーションには影響しません。</span><span class="sxs-lookup"><span data-stu-id="466cc-137">This configuration setting does not affect already established TCP connections (traffic is unrestricted in both directions) and does not affect an application sending UDP packets.</span></span>  
  
 <span data-ttu-id="466cc-138">属性の設定に使用できる値は、次のよう `ipProtectionLevel` に、列挙で指定されている定義済みの保護レベルに対応してい <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> ます。</span><span class="sxs-lookup"><span data-stu-id="466cc-138">The possible values for the `ipProtectionLevel` attribute setting correspond with the defined protection levels specified in the <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> enumeration as follows:</span></span>  
  
|<span data-ttu-id="466cc-139">**属性値**</span><span class="sxs-lookup"><span data-stu-id="466cc-139">**Attribute Value**</span></span>|<span data-ttu-id="466cc-140">**説明**</span><span class="sxs-lookup"><span data-stu-id="466cc-140">**Description**</span></span>|  
|-|-|  
|<span data-ttu-id="466cc-141">EdgeRestricted</span><span class="sxs-lookup"><span data-stu-id="466cc-141">EdgeRestricted</span></span>|<span data-ttu-id="466cc-142">IP 保護レベルはエッジ制限付きです。</span><span class="sxs-lookup"><span data-stu-id="466cc-142">The IP protection level is edge restricted.</span></span> <span data-ttu-id="466cc-143">この値は、インターネット経由で動作するように設計されているアプリケーションによって使用されます。</span><span class="sxs-lookup"><span data-stu-id="466cc-143">This value would be used by applications designed to operate across the Internet.</span></span> <span data-ttu-id="466cc-144">この設定を使用する場合、Windows Teredo 実装を使用したネットワーク アドレス変換 (NAT: Network Address Translation) トラバーサルは使用できません。</span><span class="sxs-lookup"><span data-stu-id="466cc-144">This setting does not allow Network Address Translation (NAT) traversal using the Windows Teredo implementation.</span></span> <span data-ttu-id="466cc-145">これらのアプリケーションは、IPv4 のファイアウォールをバイパスすることがあるため、開いているポートを対象としたインターネットからの攻撃に対して堅牢である必要があります。</span><span class="sxs-lookup"><span data-stu-id="466cc-145">These applications may bypass IPv4 firewalls, so applications must be hardened against Internet attacks directed at the opened port.</span></span> <span data-ttu-id="466cc-146">Windows Server 2003 と Windows XP では、ソケットの IP 保護レベルの既定値はエッジ制限付きです。</span><span class="sxs-lookup"><span data-stu-id="466cc-146">On Windows Server 2003 and Windows XP, the default value for the IP Protection level on a socket is edge restricted.</span></span>|  
|<span data-ttu-id="466cc-147">制限付き</span><span class="sxs-lookup"><span data-stu-id="466cc-147">Restricted</span></span>|<span data-ttu-id="466cc-148">IP 保護レベルは制限付きです。</span><span class="sxs-lookup"><span data-stu-id="466cc-148">The IP protection level is restricted.</span></span> <span data-ttu-id="466cc-149">この値は、インターネットのシナリオを実装しないイントラネット アプリケーションによって使用されます。</span><span class="sxs-lookup"><span data-stu-id="466cc-149">This value would be used by intranet applications that do not implement Internet scenarios.</span></span> <span data-ttu-id="466cc-150">これらのアプリケーションは、一般的に、インターネット型の攻撃に対してテストが行われていなかったり堅牢ではなかったりします。</span><span class="sxs-lookup"><span data-stu-id="466cc-150">These applications are generally not tested or hardened against Internet-style attacks.</span></span> <span data-ttu-id="466cc-151">この設定を使用する場合、受信トラフィックはリンクローカルのみに制限されます。</span><span class="sxs-lookup"><span data-stu-id="466cc-151">This setting will limit the received traffic to link-local only.</span></span>|  
|<span data-ttu-id="466cc-152">無制限</span><span class="sxs-lookup"><span data-stu-id="466cc-152">Unrestricted</span></span>|<span data-ttu-id="466cc-153">IP 保護レベルは無制限です。</span><span class="sxs-lookup"><span data-stu-id="466cc-153">The IP protection level is unrestricted.</span></span> <span data-ttu-id="466cc-154">この値は、Windows に組み込まれている IPv6 NAT Traversal 機能 (たとえば、Teredo) を使用するアプリケーションを含む、インターネット経由で動作するように設計されているアプリケーションによって使用されます。</span><span class="sxs-lookup"><span data-stu-id="466cc-154">This value would be used by applications designed to operate across the Internet, including applications taking advantage of IPv6 NAT traversal capabilities built into Windows (Teredo, for example).</span></span> <span data-ttu-id="466cc-155">これらのアプリケーションは、IPv4 のファイアウォールをバイパスすることがあるため、開いているポートを対象としたインターネットからの攻撃に対して堅牢である必要があります。</span><span class="sxs-lookup"><span data-stu-id="466cc-155">These applications may bypass IPv4 firewalls, so applications must be hardened against Internet attacks directed at the opened port.</span></span> <span data-ttu-id="466cc-156">Windows Server 2008 R2 と Windows Vista では、ソケットの IP 保護レベルの既定値は無制限です。</span><span class="sxs-lookup"><span data-stu-id="466cc-156">On Windows Server 2008 R2 and Windows Vista, the default value for the IP Protection level on a socket is unrestricted.</span></span>|  
|<span data-ttu-id="466cc-157">指定されていません。</span><span class="sxs-lookup"><span data-stu-id="466cc-157">Unspecified</span></span>|<span data-ttu-id="466cc-158">IP 保護レベルは未指定です。</span><span class="sxs-lookup"><span data-stu-id="466cc-158">The IP protection level is unspecified.</span></span> <span data-ttu-id="466cc-159">Windows 7 と Windows Server 2008 R2 では、ソケットの IP 保護レベルの既定値は未指定です。</span><span class="sxs-lookup"><span data-stu-id="466cc-159">On Windows 7 and Windows Server 2008 R2, the default value for the IP Protection level on a socket is unspecified.</span></span>|  
  
 <span data-ttu-id="466cc-160">属性の既定値 `ipProtectionLevel` は**指定**されていません。</span><span class="sxs-lookup"><span data-stu-id="466cc-160">The default value for the `ipProtectionLevel` attribute is **Unspecified**.</span></span>  
  
 <span data-ttu-id="466cc-161">プロパティは、 <xref:System.Net.Configuration.SocketElement.IPProtectionLevel%2A> `ipProtectionLevel` 適用可能な構成ファイルから属性の現在の値を取得するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="466cc-161">The <xref:System.Net.Configuration.SocketElement.IPProtectionLevel%2A> property can be used to get the current value of the `ipProtectionLevel` attribute from applicable configuration files.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="466cc-162">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="466cc-162">Configuration Files</span></span>  
 <span data-ttu-id="466cc-163">この要素は、アプリケーション構成ファイルまたはマシン構成ファイル (Machine.config) で使用できます。</span><span class="sxs-lookup"><span data-stu-id="466cc-163">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="466cc-164">例</span><span class="sxs-lookup"><span data-stu-id="466cc-164">Example</span></span>  
 <span data-ttu-id="466cc-165">次の例では、完了ポートを使用するように指定する方法と、既定値を無制限にすることを指定する方法を示し <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> ます。</span><span class="sxs-lookup"><span data-stu-id="466cc-165">The following example shows how to specify that completion ports should be used and that the default <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> should be unrestricted.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="466cc-166">関連項目</span><span class="sxs-lookup"><span data-stu-id="466cc-166">See also</span></span>

- <xref:System.Net?displayProperty=nameWithType>
- <xref:System.Net.Configuration.SocketElement?displayProperty=nameWithType>
- <xref:System.Net.Sockets?displayProperty=nameWithType>
- <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType>
- <xref:System.Net.Sockets.SocketOptionName.IPProtectionLevel?displayProperty=nameWithType>
- [<span data-ttu-id="466cc-167">ネットワーク設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="466cc-167">Network Settings Schema</span></span>](index.md)
