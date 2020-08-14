---
ms.openlocfilehash: e0cdcce9b8c7d591925b08635e3354dadaf22b7b
ms.sourcegitcommit: b7a8b09828bab4e90f66af8d495ecd7024c45042
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/04/2020
ms.locfileid: "87556029"
---
### <a name="envelopedcms-defaults-to-aes-256-encryption"></a>EnvelopedCms が AES-256 暗号化を既定で使用

`EnvelopedCms` で使用される既定の対称暗号化アルゴリズムが TripleDES から AES-256 に変更されました。

#### <a name="change-description"></a>変更の説明

以前のバージョンでは、コンストラクターのオーバーロードを使って対称暗号化アルゴリズムを指定せずに <xref:System.Security.Cryptography.Pkcs.EnvelopedCms> を使用してデータを暗号化する場合、データは TripleDES/3DES/3DEA/DES3-EDE アルゴリズムで暗号化されます。

.NET Core 3.0 以降では ([System.Security.Cryptography.Pkcs](https://www.nuget.org/packages/System.Security.Cryptography.Pkcs/) NuGet パッケージのバージョン 4.6.0 を介して)、アルゴリズムを最新化し、既定のオプションのセキュリティを向上するために、既定のアルゴリズムが AES-256 に変更されました。 メッセージ受信者の証明書に Diffie-Hellman (非 EC) 公開キーが含まれている場合、基になるプラットフォームの制限のために、暗号化操作は、<xref:System.Security.Cryptography.CryptographicException> で失敗する可能性があります。

次のサンプル コードでは、.NET Core 2.2 以前で実行されている場合、データは TripleDES で暗号化されます。 NET Core 3.0 以降で実行されている場合は AES-256 で暗号化されます。

```csharp
EnvelopedCms cms = new EnvelopedCms(content);
cms.Encrypt(recipient);
return cms.Encode();
```

#### <a name="version-introduced"></a>導入されたバージョン

3.0

#### <a name="recommended-action"></a>推奨アクション

この変更によって悪影響を受ける場合は、型 <xref:System.Security.Cryptography.Pkcs.AlgorithmIdentifier> を含む <xref:System.Security.Cryptography.Pkcs.EnvelopedCms> コンストラクターで暗号化アルゴリズム識別子を明示的に指定することで、TripleDES 暗号化に戻すことができます。次に例を示します。

```csharp
Oid tripleDesOid = new Oid("1.2.840.113549.3.7", null);
AlgorithmIdentifier tripleDesIdentifier = new AlgorithmIdentifier(tripleDesOid);
EnvelopedCms cms = new EnvelopedCms(content, tripleDesIdentifier);

cms.Encrypt(recipient);
return cms.Encode()l
```

#### <a name="category"></a>カテゴリ

暗号

#### <a name="affected-apis"></a>影響を受ける API

- <xref:System.Security.Cryptography.Pkcs.EnvelopedCms.%23ctor>
- <xref:System.Security.Cryptography.Pkcs.EnvelopedCms.%23ctor(System.Security.Cryptography.Pkcs.ContentInfo)>
- <xref:System.Security.Cryptography.Pkcs.EnvelopedCms.%23ctor(System.Security.Cryptography.Pkcs.SubjectIdentifierType,System.Security.Cryptography.Pkcs.ContentInfo)>

<!--

#### Affected APIs

- `M:System.Security.Cryptography.Pkcs.EnvelopedCms.#ctor`
- `M:System.Security.Cryptography.Pkcs.EnvelopedCms.#ctor(System.Security.Cryptography.Pkcs.ContentInfo)`
- `M:System.Security.Cryptography.Pkcs.EnvelopedCms.%23ctor(System.Security.Cryptography.Pkcs.SubjectIdentifierType,System.Security.Cryptography.Pkcs.ContentInfo)`

-->
