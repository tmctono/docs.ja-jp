---
ms.openlocfilehash: 3c6142fd536bad5676f02570fecd4eb0605db829
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2020
ms.locfileid: "83721142"
---
### <a name="begin-trusted-certificate-syntax-no-longer-supported-for-root-certificates-on-linux"></a><span data-ttu-id="c3bf5-101">Linux のルート証明書に対して "BEGIN TRUSTED CERTIFICATE" 構文がサポートされなくなった</span><span class="sxs-lookup"><span data-stu-id="c3bf5-101">"BEGIN TRUSTED CERTIFICATE" syntax no longer supported for root certificates on Linux</span></span>

<span data-ttu-id="c3bf5-102">Linux およびその他の Unix 類似システム (macOS 以外) のルート証明書は、標準の `BEGIN CERTIFICATE` PEM ヘッダーと、OpenSSL 固有の `BEGIN TRUSTED CERTIFICATE` PEM ヘッダーの 2 つの形式で提示できます。</span><span class="sxs-lookup"><span data-stu-id="c3bf5-102">Root certificates on Linux and other Unix-like systems (but not macOS) can be presented in two forms: the standard `BEGIN CERTIFICATE` PEM header, and the OpenSSL-specific `BEGIN TRUSTED CERTIFICATE` PEM header.</span></span> <span data-ttu-id="c3bf5-103">後者の構文では、.NET Core の <xref:System.Security.Cryptography.X509Certificates.X509Chain?displayProperty=fullName> クラスとの互換性の問題の原因となる追加の構成が可能です。</span><span class="sxs-lookup"><span data-stu-id="c3bf5-103">The latter syntax allows for additional configuration that has caused compatibility issues with .NET Core's <xref:System.Security.Cryptography.X509Certificates.X509Chain?displayProperty=fullName> class.</span></span> <span data-ttu-id="c3bf5-104">`BEGIN TRUSTED CERTIFICATE` ルート証明書の内容は、.NET Core 3.0 以降のチェーン エンジンでは読み込まれなくなりました。</span><span class="sxs-lookup"><span data-stu-id="c3bf5-104">`BEGIN TRUSTED CERTIFICATE` root certificate contents are no longer loaded by the chain engine starting in .NET Core 3.0.</span></span>

#### <a name="change-description"></a><span data-ttu-id="c3bf5-105">変更の説明</span><span class="sxs-lookup"><span data-stu-id="c3bf5-105">Change description</span></span>

<span data-ttu-id="c3bf5-106">以前は、ルート信頼リストを設定するために、`BEGIN CERTIFICATE` と `BEGIN TRUSTED CERTIFICATE` 両方の構文が使用されていました。</span><span class="sxs-lookup"><span data-stu-id="c3bf5-106">Previously, both the `BEGIN CERTIFICATE` and `BEGIN TRUSTED CERTIFICATE` syntaxes were used to populate the root trust list.</span></span> <span data-ttu-id="c3bf5-107">`BEGIN TRUSTED CERTIFICATE` 構文を使用し、ファイルで追加のオプションを指定した場合、信頼チェーンが明示的に禁止されたことが、<xref:System.Security.Cryptography.X509Certificates.X509Chain> によって報告される場合があります (<xref:System.Security.Cryptography.X509Certificates.X509ChainStatusFlags.ExplicitDistrust?displayProperty=nameWithType>)。</span><span class="sxs-lookup"><span data-stu-id="c3bf5-107">If the `BEGIN TRUSTED CERTIFICATE` syntax was used and additional options were specified in the file, <xref:System.Security.Cryptography.X509Certificates.X509Chain> may have reported that the chain trust was explicitly disallowed (<xref:System.Security.Cryptography.X509Certificates.X509ChainStatusFlags.ExplicitDistrust?displayProperty=nameWithType>).</span></span> <span data-ttu-id="c3bf5-108">ただし、その証明書が、それより前に読み込まれたファイルの `BEGIN CERTIFICATE` 構文でも指定されていた場合は、信頼チェーンは許可されました。</span><span class="sxs-lookup"><span data-stu-id="c3bf5-108">However, if the certificate was also specified with the `BEGIN CERTIFICATE` syntax in a previously loaded file, the chain trust was allowed.</span></span>

<span data-ttu-id="c3bf5-109">.NET Core 3.0 以降、`BEGIN TRUSTED CERTIFICATE` の内容は読み取られなくなりました。</span><span class="sxs-lookup"><span data-stu-id="c3bf5-109">Starting in .NET Core 3.0, `BEGIN TRUSTED CERTIFICATE` contents are no longer read.</span></span> <span data-ttu-id="c3bf5-110">証明書が標準の `BEGIN CERTIFICATE` 構文でも指定されていない場合、<xref:System.Security.Cryptography.X509Certificates.X509Chain> ではルートが信頼されていないと報告されます (<xref:System.Security.Cryptography.X509Certificates.X509ChainStatusFlags.UntrustedRoot?displayProperty=nameWithType>)。</span><span class="sxs-lookup"><span data-stu-id="c3bf5-110">If the certificate is not also specified via a standard `BEGIN CERTIFICATE` syntax, the <xref:System.Security.Cryptography.X509Certificates.X509Chain> reports that the root is not trusted (<xref:System.Security.Cryptography.X509Certificates.X509ChainStatusFlags.UntrustedRoot?displayProperty=nameWithType>).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="c3bf5-111">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="c3bf5-111">Version introduced</span></span>

<span data-ttu-id="c3bf5-112">3.0</span><span class="sxs-lookup"><span data-stu-id="c3bf5-112">3.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="c3bf5-113">推奨アクション</span><span class="sxs-lookup"><span data-stu-id="c3bf5-113">Recommended action</span></span>

<span data-ttu-id="c3bf5-114">ほとんどのアプリケーションはこの変更の影響を受けませんが、アクセス許可の問題のために両方のルート証明書ソースを確認できないアプリケーションでは、アップグレード後に予期しない `UntrustedRoot` エラーが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c3bf5-114">Most applications are unaffected by this change, but applications that cannot see both root certificate sources because of permissions problems may experience unexpected `UntrustedRoot` errors after upgrading.</span></span>

<span data-ttu-id="c3bf5-115">多くの Linux ディストリビューションでは、ルート証明書はファイルごとに 1 証明書のディレクトリと、1 ファイル連結の 2 つの場所に書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="c3bf5-115">Many Linux distributions (or distros) write root certificates into two locations: a one-certificate-per-file directory, and a one-file concatenation.</span></span> <span data-ttu-id="c3bf5-116">一部のディストリビューションでは、ファイルごとに 1 証明書のディレクトリには `BEGIN TRUSTED CERTIFICATE` 構文が使用され、ファイル連結には標準の `BEGIN CERTIFICATE` 構文が使用されています。</span><span class="sxs-lookup"><span data-stu-id="c3bf5-116">On some distros, the one-certificate-per-file directory uses the `BEGIN TRUSTED CERTIFICATE` syntax while the file concatenation uses the standard `BEGIN CERTIFICATE` syntax.</span></span> <span data-ttu-id="c3bf5-117">これらの場所の少なくとも 1 つにすべてのカスタム ルート証明書が `BEGIN CERTIFICATE` として追加されていること、およびアプリケーションで両方の場所を読み取ることができることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="c3bf5-117">Ensure that any custom root certificates are added as `BEGIN CERTIFICATE` in at least one of these locations, and that both locations can be read by your application.</span></span>

<span data-ttu-id="c3bf5-118">一般的なディレクトリは */etc/ssl/certs/* であり、一般的な連結されたファイルは */etc/ssl/cert.pem* です。</span><span class="sxs-lookup"><span data-stu-id="c3bf5-118">The typical directory is */etc/ssl/certs/* and the typical concatenated file is */etc/ssl/cert.pem*.</span></span> <span data-ttu-id="c3bf5-119">プラットフォーム固有のルートを確認するには、`openssl version -d` コマンドを使用します。これは、 */etc/ssl/* と異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="c3bf5-119">Use the command `openssl version -d` to determine the platform-specific root, which may differ from */etc/ssl/*.</span></span> <span data-ttu-id="c3bf5-120">たとえば、Ubuntu 18.04 では、ディレクトリは */usr/lib/ssl/certs/* であり、ファイルは */usr/lib/ssl/cert.pem* です。</span><span class="sxs-lookup"><span data-stu-id="c3bf5-120">For example, on Ubuntu 18.04, the directory is */usr/lib/ssl/certs/* and the file is */usr/lib/ssl/cert.pem*.</span></span> <span data-ttu-id="c3bf5-121">ただし、 */usr/lib/ssl/certs/* は */etc/ssl/certs/* へのシンボリック リンクであり、 */usr/lib/ssl/cert.pem* は存在しません。</span><span class="sxs-lookup"><span data-stu-id="c3bf5-121">However, */usr/lib/ssl/certs/* is a symlink to */etc/ssl/certs/* and */usr/lib/ssl/cert.pem* does not exist.</span></span>

```bash
$ openssl version -d
OPENSSLDIR: "/usr/lib/ssl"
$ ls -al /usr/lib/ssl
total 12
drwxr-xr-x  3 root root 4096 Dec 12 17:10 .
drwxr-xr-x 73 root root 4096 Feb 20 15:18 ..
lrwxrwxrwx  1 root root   14 Mar 27  2018 certs -> /etc/ssl/certs
drwxr-xr-x  2 root root 4096 Dec 12 17:10 misc
lrwxrwxrwx  1 root root   20 Nov 12 16:58 openssl.cnf -> /etc/ssl/openssl.cnf
lrwxrwxrwx  1 root root   16 Mar 27  2018 private -> /etc/ssl/private
```

#### <a name="category"></a><span data-ttu-id="c3bf5-122">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="c3bf5-122">Category</span></span>

<span data-ttu-id="c3bf5-123">暗号</span><span class="sxs-lookup"><span data-stu-id="c3bf5-123">Cryptography</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="c3bf5-124">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="c3bf5-124">Affected APIs</span></span>

- <xref:System.Security.Cryptography.X509Certificates.X509Chain?displayProperty=fullName>

<!--

#### Affected APIs

- `T:System.Security.Cryptography.X509Certificates.X509Chain`

-->
