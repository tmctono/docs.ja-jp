---
ms.openlocfilehash: 5b566dd89801caff7a253abc2fb62c5fd79591f7
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/15/2020
ms.locfileid: "90606774"
---
### <a name="sslstream-supports-tls-alerts"></a><span data-ttu-id="5756c-101">SslStream で TLS アラートに対応</span><span class="sxs-lookup"><span data-stu-id="5756c-101">SslStream supports TLS Alerts</span></span>

#### <a name="details"></a><span data-ttu-id="5756c-102">説明</span><span class="sxs-lookup"><span data-stu-id="5756c-102">Details</span></span>

<span data-ttu-id="5756c-103">TLS ハンドシェイクに失敗すると、最初の I/O 読み取り/書き込み操作によって <xref:System.IO.IOException?displayProperty=fullName> と内部例外 <xref:System.ComponentModel.Win32Exception?displayProperty=fullName> がスローされます。</span><span class="sxs-lookup"><span data-stu-id="5756c-103">After a failed TLS handshake, an <xref:System.IO.IOException?displayProperty=fullName> with an inner <xref:System.ComponentModel.Win32Exception?displayProperty=fullName> exception will be thrown by the first I/O Read/Write operation.</span></span> <span data-ttu-id="5756c-104">[TLS および SSL アラートの Schannel エラー コード](/windows/desktop/SecAuthN/schannel-error-codes-for-tls-and-ssl-alerts)を使用して、<xref:System.ComponentModel.Win32Exception?displayProperty=fullName> の <xref:System.ComponentModel.Win32Exception.NativeErrorCode?displayProperty=fullName> コードをリモート パーティからの TLS アラートにマップすることができます。詳しくは、[RFC 2246: セクション 7.2.2「Error alerts (エラー アラート)」](https://tools.ietf.org/html/rfc2246#section-7.2.2)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5756c-104">The <xref:System.ComponentModel.Win32Exception.NativeErrorCode?displayProperty=fullName> code for the <xref:System.ComponentModel.Win32Exception?displayProperty=fullName> can be mapped to the TLS Alert from the remote party using the [Schannel error codes for TLS and SSL alerts](/windows/desktop/SecAuthN/schannel-error-codes-for-tls-and-ssl-alerts).For more information, see [RFC 2246: Section 7.2.2 Error alerts](https://tools.ietf.org/html/rfc2246#section-7.2.2).</span></span> <br/><span data-ttu-id="5756c-105">.NET Framework 4.6.2 およびそれより前のバージョンでの動作では、他のパーティがハンドシェイクに失敗してそのすぐ後に接続を拒否した場合、トランスポート チャネル (通常は TCP 接続) は書き込みまたは読み取り中にタイムアウトします。</span><span class="sxs-lookup"><span data-stu-id="5756c-105">The behavior in .NET Framework 4.6.2 and earlier is that the transport channel (usually TCP connection) will timeout during either Write or Read if the other party failed the handshake and immediately afterwards rejected the connection.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="5756c-106">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="5756c-106">Suggestion</span></span>

<span data-ttu-id="5756c-107"><xref:System.IO.Stream.Read(System.Byte[],System.Int32,System.Int32)>/<xref:System.IO.Stream.Write(System.Byte[],System.Int32,System.Int32)> などのネットワーク I/O API を呼び出すアプリケーションは、<xref:System.IO.IOException> または <xref:System.TimeoutException?displayProperty=fullName> を処理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5756c-107">Applications calling network I/O APIs such as <xref:System.IO.Stream.Read(System.Byte[],System.Int32,System.Int32)>/<xref:System.IO.Stream.Write(System.Byte[],System.Int32,System.Int32)> should handle <xref:System.IO.IOException> or <xref:System.TimeoutException?displayProperty=fullName>.</span></span><br/><span data-ttu-id="5756c-108">TLS アラート機能は、.NET Framework 4.7 以降では既定で有効になります。</span><span class="sxs-lookup"><span data-stu-id="5756c-108">The TLS Alerts feature is enabled by default starting with .NET Framework 4.7.</span></span> <span data-ttu-id="5756c-109">.NET Framework 4.7 またはそれより後のシステムで動作する 4.0 から 4.6.2 のバージョンの .NET Framework を対象とするアプリケーションは、互換性を維持するためにこの機能を無効にします。</span><span class="sxs-lookup"><span data-stu-id="5756c-109">Applications targeting versions of the .NET Framework from 4.0 through 4.6.2 running on a .NET Framework 4.7 or higher system will have the feature disabled to preserve compatibility.</span></span> <br/><span data-ttu-id="5756c-110">.NET Framework 4.7 以降で動作する .NET Framework 4.6 以降のアプリケーションでこの機能を有効または無効にするには、次の構成 API を使います。</span><span class="sxs-lookup"><span data-stu-id="5756c-110">The following configuration API is available to enable or disable the feature for .NET Framework 4.6 and later applications running on .NET Framework 4.7 or later.</span></span>

- <span data-ttu-id="5756c-111">プログラムによる: ServicePointManager は 1 回のみ初期化するため、アプリケーションで行われる一番最初の動作にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="5756c-111">Programmatically:   Must be the very first thing the application does since ServicePointManager will initialize only once:</span></span>

    ```csharp
    AppContext.SetSwitch("TestSwitch.LocalAppContext.DisableCaching", true);

    // Set to 'false' to enable the feature in .NET Framework 4.6 - 4.6.2.
    AppContext.SetSwitch("Switch.System.Net.DontEnableTlsAlerts", true);
    ```

- <span data-ttu-id="5756c-112">AppConfig:</span><span class="sxs-lookup"><span data-stu-id="5756c-112">AppConfig:</span></span>

    ```xml
    <runtime>
      <AppContextSwitchOverrides value="Switch.System.Net.DontEnableTlsAlerts=true"/>
      <!-- Set to 'false' to enable the feature in .NET Framework 4.6 - 4.6.2. -->
    </runtime>
    ```

- <span data-ttu-id="5756c-113">レジストリ キー (マシン グローバル): .NET Framework 4.6 - 4.6.2 でこの機能を有効にするには、Value を `false` に設定します。</span><span class="sxs-lookup"><span data-stu-id="5756c-113">Registry key (machine global):   Set the Value to `false` to enable the feature in .NET Framework 4.6 - 4.6.2.</span></span>

    ```ini
    Key: HKLM\SOFTWARE\Wow6432Node\Microsoft\.NETFramework\AppContext\Switch.System.Net.DontEnableTlsAlerts
    - Type: String
    - Value: "true"
    ```

| <span data-ttu-id="5756c-114">名前</span><span class="sxs-lookup"><span data-stu-id="5756c-114">Name</span></span>    | <span data-ttu-id="5756c-115">[値]</span><span class="sxs-lookup"><span data-stu-id="5756c-115">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="5756c-116">スコープ</span><span class="sxs-lookup"><span data-stu-id="5756c-116">Scope</span></span>   | <span data-ttu-id="5756c-117">エッジ</span><span class="sxs-lookup"><span data-stu-id="5756c-117">Edge</span></span>        |
| <span data-ttu-id="5756c-118">バージョン</span><span class="sxs-lookup"><span data-stu-id="5756c-118">Version</span></span> | <span data-ttu-id="5756c-119">4.7</span><span class="sxs-lookup"><span data-stu-id="5756c-119">4.7</span></span>         |
| <span data-ttu-id="5756c-120">種類</span><span class="sxs-lookup"><span data-stu-id="5756c-120">Type</span></span>    | <span data-ttu-id="5756c-121">再ターゲット中</span><span class="sxs-lookup"><span data-stu-id="5756c-121">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="5756c-122">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="5756c-122">Affected APIs</span></span>

- <xref:System.Net.Security.SslStream?displayProperty=nameWithType>
- <xref:System.Net.WebRequest?displayProperty=nameWithType>
- <xref:System.Net.HttpWebRequest?displayProperty=nameWithType>
- <xref:System.Net.FtpWebRequest?displayProperty=nameWithType>
- <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>
- <xref:System.Net.Http?displayProperty=nameWithType>
