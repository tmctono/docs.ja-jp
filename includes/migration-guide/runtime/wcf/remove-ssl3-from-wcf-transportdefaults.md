---
ms.openlocfilehash: 37d771305bb0a4a38eeac9713e8667d158962174
ms.sourcegitcommit: 5d9f4b805787f890ca6e0dc7ea30a43018bc9cbb
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2019
ms.locfileid: "57788882"
---
### <a name="remove-ssl3-from-the-wcf-transportdefaults"></a><span data-ttu-id="d2951-101">WCF TransportDefaults からの Ssl3 の削除</span><span class="sxs-lookup"><span data-stu-id="d2951-101">Remove Ssl3 from the WCF TransportDefaults</span></span>

|   |   |
|---|---|
|<span data-ttu-id="d2951-102">説明</span><span class="sxs-lookup"><span data-stu-id="d2951-102">Details</span></span>|<span data-ttu-id="d2951-103">トランスポート セキュリティで NetTcp を使用し、証明書の資格情報の種類を使用する場合、SSL 3 プロトコルは、安全な接続のネゴシエーションに使用される既定のプロトコルではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="d2951-103">When using NetTcp with transport security and a credential type of certificate, the SSL 3 protocol is no longer a default protocol used for negotiating a secure connection.</span></span> <span data-ttu-id="d2951-104">TLS 1.0 は常に NetTcp のプロトコル一覧に含まれているため、ほとんどの場合、既存のアプリには影響はないと考えられます。</span><span class="sxs-lookup"><span data-stu-id="d2951-104">In most cases there should be no impact to existing apps as TLS 1.0 has always been included in the protocol list for NetTcp.</span></span> <span data-ttu-id="d2951-105">既存のすべてのクライアントは TLS 1.0 以降を使用して接続をネゴシエートできるようになりました。</span><span class="sxs-lookup"><span data-stu-id="d2951-105">All existing clients should be able to negotiate a connection using at least TLS1.0.</span></span>|
|<span data-ttu-id="d2951-106">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="d2951-106">Suggestion</span></span>|<span data-ttu-id="d2951-107">Ssl3 が必要な場合は、以下の構成メカニズムのいずれかを使用して、ネゴシエートされたプロトコルの一覧に Ssl3 を追加します。</span><span class="sxs-lookup"><span data-stu-id="d2951-107">If Ssl3 is required, use one of the following configuration mechanisms to add Ssl3 to the list of negotiated protocols.</span></span><ul><li><xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement.SslProtocols></li><li><xref:System.ServiceModel.TcpTransportSecurity.SslProtocols></li><li>[<span data-ttu-id="d2951-108">\<netTcpBinding> の \<transport></span><span class="sxs-lookup"><span data-stu-id="d2951-108">\<transport> of \<netTcpBinding></span></span>](~/docs/framework/configure-apps/file-schema/wcf/transport-of-nettcpbinding.md)</li><li>[<span data-ttu-id="d2951-109">&lt;customBinding&gt; の&lt;sslStreamSecurity&gt; セクション</span><span class="sxs-lookup"><span data-stu-id="d2951-109">&lt;sslStreamSecurity&gt; section of &lt;customBinding&gt;</span></span>](~/docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md)</li></ul>|
|<span data-ttu-id="d2951-110">スコープ</span><span class="sxs-lookup"><span data-stu-id="d2951-110">Scope</span></span>|<span data-ttu-id="d2951-111">エッジ</span><span class="sxs-lookup"><span data-stu-id="d2951-111">Edge</span></span>|
|<span data-ttu-id="d2951-112">バージョン</span><span class="sxs-lookup"><span data-stu-id="d2951-112">Version</span></span>|<span data-ttu-id="d2951-113">4.6.2</span><span class="sxs-lookup"><span data-stu-id="d2951-113">4.6.2</span></span>|
|<span data-ttu-id="d2951-114">型</span><span class="sxs-lookup"><span data-stu-id="d2951-114">Type</span></span>|<span data-ttu-id="d2951-115">ランタイム</span><span class="sxs-lookup"><span data-stu-id="d2951-115">Runtime</span></span>|
|<span data-ttu-id="d2951-116">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="d2951-116">Affected APIs</span></span>|<ul><li><xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement.SslProtocols?displayProperty=nameWithType></li><li><xref:System.ServiceModel.TcpTransportSecurity.SslProtocols?displayProperty=nameWithType></li></ul>|

