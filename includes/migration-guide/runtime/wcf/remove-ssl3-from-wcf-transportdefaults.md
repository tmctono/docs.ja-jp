---
ms.openlocfilehash: a5f4047d70276a90c9d72918a2559fd795feb26e
ms.sourcegitcommit: 261e0c98a111357692b3b63c596edf0cacf72991
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2020
ms.locfileid: "90770843"
---
### <a name="remove-ssl3-from-the-wcf-transportdefaults"></a>WCF TransportDefaults からの Ssl3 の削除

#### <a name="details"></a>説明

トランスポート セキュリティで NetTcp を使用し、証明書の資格情報の種類を使用する場合、SSL 3 プロトコルは、安全な接続のネゴシエーションに使用される既定のプロトコルではなくなりました。 TLS 1.0 は常に NetTcp のプロトコル一覧に含まれているため、ほとんどの場合、既存のアプリには影響はないと考えられます。 既存のすべてのクライアントは TLS 1.0 以降を使用して接続をネゴシエートできるようになりました。

#### <a name="suggestion"></a>提案される解決策

Ssl3 が必要な場合は、以下の構成メカニズムのいずれかを使用して、ネゴシエートされたプロトコルの一覧に Ssl3 を追加します。

- <xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement.SslProtocols>
- <xref:System.ServiceModel.TcpTransportSecurity.SslProtocols>
- [\<netTcpBinding> の \<transport>](../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-nettcpbinding.md)
- [\<sslStreamSecurity>](../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md)

| 名前    | 値   |
|:--------|:--------|
| スコープ   | エッジ    |
| バージョン | 4.6.2   |
| 種類    | ランタイム |

#### <a name="affected-apis"></a>影響を受ける API

- <xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement.SslProtocols?displayProperty=nameWithType>
- <xref:System.ServiceModel.TcpTransportSecurity.SslProtocols?displayProperty=nameWithType>

<!--

#### Affected APIs

- `P:System.ServiceModel.Channels.SslStreamSecurityBindingElement.SslProtocols`
- `P:System.ServiceModel.TcpTransportSecurity.SslProtocols`

-->
