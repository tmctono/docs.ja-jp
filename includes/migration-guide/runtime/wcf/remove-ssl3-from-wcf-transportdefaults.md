---
ms.openlocfilehash: 23987c300ac4fbad401de180b63106cd234f8d27
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497240"
---
### <a name="remove-ssl3-from-the-wcf-transportdefaults"></a><span data-ttu-id="dcba0-101">WCF TransportDefaults からの Ssl3 の削除</span><span class="sxs-lookup"><span data-stu-id="dcba0-101">Remove Ssl3 from the WCF TransportDefaults</span></span>

#### <a name="details"></a><span data-ttu-id="dcba0-102">説明</span><span class="sxs-lookup"><span data-stu-id="dcba0-102">Details</span></span>

<span data-ttu-id="dcba0-103">トランスポート セキュリティで NetTcp を使用し、証明書の資格情報の種類を使用する場合、SSL 3 プロトコルは、安全な接続のネゴシエーションに使用される既定のプロトコルではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="dcba0-103">When using NetTcp with transport security and a credential type of certificate, the SSL 3 protocol is no longer a default protocol used for negotiating a secure connection.</span></span> <span data-ttu-id="dcba0-104">TLS 1.0 は常に NetTcp のプロトコル一覧に含まれているため、ほとんどの場合、既存のアプリには影響はないと考えられます。</span><span class="sxs-lookup"><span data-stu-id="dcba0-104">In most cases there should be no impact to existing apps as TLS 1.0 has always been included in the protocol list for NetTcp.</span></span> <span data-ttu-id="dcba0-105">既存のすべてのクライアントは TLS 1.0 以降を使用して接続をネゴシエートできるようになりました。</span><span class="sxs-lookup"><span data-stu-id="dcba0-105">All existing clients should be able to negotiate a connection using at least TLS1.0.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="dcba0-106">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="dcba0-106">Suggestion</span></span>

<span data-ttu-id="dcba0-107">Ssl3 が必要な場合は、以下の構成メカニズムのいずれかを使用して、ネゴシエートされたプロトコルの一覧に Ssl3 を追加します。</span><span class="sxs-lookup"><span data-stu-id="dcba0-107">If Ssl3 is required, use one of the following configuration mechanisms to add Ssl3 to the list of negotiated protocols.</span></span><ul><li><xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement.SslProtocols></li><li><xref:System.ServiceModel.TcpTransportSecurity.SslProtocols></li><li>[<](~/docs/framework/configure-apps/file-schema/wcf/transport-of-nettcpbinding.md)</li><li><span data-ttu-id="dcba0-108">[&lt;customBinding&gt; の &lt;sslStreamSecurity&gt; セクション]~/docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md)</span><span class="sxs-lookup"><span data-stu-id="dcba0-108">[&lt;sslStreamSecurity&gt; section of &lt;customBinding&gt;]~/docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md)</span></span></li></ul>

| <span data-ttu-id="dcba0-109">名前</span><span class="sxs-lookup"><span data-stu-id="dcba0-109">Name</span></span>    | <span data-ttu-id="dcba0-110">値</span><span class="sxs-lookup"><span data-stu-id="dcba0-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="dcba0-111">スコープ</span><span class="sxs-lookup"><span data-stu-id="dcba0-111">Scope</span></span>   |<span data-ttu-id="dcba0-112">エッジ</span><span class="sxs-lookup"><span data-stu-id="dcba0-112">Edge</span></span>|
|<span data-ttu-id="dcba0-113">バージョン</span><span class="sxs-lookup"><span data-stu-id="dcba0-113">Version</span></span>|<span data-ttu-id="dcba0-114">4.6.2</span><span class="sxs-lookup"><span data-stu-id="dcba0-114">4.6.2</span></span>|
|<span data-ttu-id="dcba0-115">種類</span><span class="sxs-lookup"><span data-stu-id="dcba0-115">Type</span></span>|<span data-ttu-id="dcba0-116">ランタイム</span><span class="sxs-lookup"><span data-stu-id="dcba0-116">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="dcba0-117">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="dcba0-117">Affected APIs</span></span>

- <xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement.SslProtocols?displayProperty=nameWithType>
- <xref:System.ServiceModel.TcpTransportSecurity.SslProtocols?displayProperty=nameWithType>

<!--

#### Affected APIs

- `P:System.ServiceModel.Channels.SslStreamSecurityBindingElement.SslProtocols`
- `P:System.ServiceModel.TcpTransportSecurity.SslProtocols`

-->
