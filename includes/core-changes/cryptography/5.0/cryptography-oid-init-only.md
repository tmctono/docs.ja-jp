---
ms.openlocfilehash: cf51d5f6b3eee7189fd9613b3d780a829d197a04
ms.sourcegitcommit: 8bfeb5930ca48b2ee6053f16082dcaf24d46d221
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/18/2020
ms.locfileid: "88558006"
---
### <a name="systemsecuritycryptographyoid-is-functionally-init-only"></a>System.Security.Cryptography.Oid は機能的に初期化専用

ASN.1 オブジェクト識別子の値とその "わかりやすい" 名前を表すために使用される <xref:System.Security.Cryptography.Oid?displayProperty=fullName> クラスは、以前は完全に変更可能でした。 この変更可能性は意外にも見落とされがちでした。 割り当てられた後に値を変更しようとすると、プロパティの setter で <xref:System.PlatformNotSupportedException> がスローされるようになりました。

#### <a name="change-description"></a>変更の説明

以前のバージョンでは、<xref:System.Security.Cryptography.Oid> のプロパティの setter を使用して、<xref:System.Security.Cryptography.Oid.FriendlyName> および <xref:System.Security.Cryptography.Oid.Value> プロパティの値を変更できます。

.NET 5.0 以降のバージョンでは、プロパティの setter は値の初期化にのみ使用できます。 プロパティにコンストラクターから、あるいはプロパティの setter の前の呼び出しからの値が設定されると、プロパティの setter で常に <xref:System.PlatformNotSupportedException> がスローされます。

#### <a name="reason-for-change"></a>変更理由

この変更により、パブリック API で戻り値の一部として <xref:System.Security.Cryptography.Oid> オブジェクトを再利用し、オブジェクト割り当てプロファイルを減らせるようになります。 <xref:System.Security.Cryptography.Oid> 値が入力として使用されるときに、一時的な "防御用" コピーを作成する必要がなくなります。

#### <a name="version-introduced"></a>導入されたバージョン

5.0 Preview 8

#### <a name="recommended-action"></a>推奨アクション

オブジェクトの初期化以外に、<xref:System.Security.Cryptography.Oid> プロパティの setter を使用しないようにしてください。 新しい値を表す場合は、既存のオブジェクトの値を変更するのではなく、新しいインスタンスを使用します。

#### <a name="category"></a>カテゴリ

暗号

#### <a name="affected-apis"></a>影響を受ける API

- <xref:System.Security.Cryptography.Oid.FriendlyName?displayProperty=fullName>
- <xref:System.Security.Cryptography.Oid.Value?displayProperty=fullName>

<!--

#### Affected APIs

- `P:System.Security.Cryptography.Oid.FriendlyName`
- `P:System.Security.Cryptography.Oid.Value`

-->
