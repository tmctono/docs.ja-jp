---
ms.openlocfilehash: b49b2f88b130bb952b77964d5bf38374dc606385
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2020
ms.locfileid: "74567984"
---
### <a name="net-core-30-prefers-openssl-11x-to-openssl-10x"></a><span data-ttu-id="587bd-101">.NET Core 3.0 では、OpenSSL 1.0.x よりも OpenSSL 1.1.x が優先されます</span><span class="sxs-lookup"><span data-stu-id="587bd-101">.NET Core 3.0 prefers OpenSSL 1.1.x to OpenSSL 1.0.x</span></span>

<span data-ttu-id="587bd-102">Linux 用 .NET Core では、複数の Linux ディストリビューションで動作するため、OpenSSL 1.0.x と OpenSSL 1.1.x の両方がサポートされます。</span><span class="sxs-lookup"><span data-stu-id="587bd-102">.NET Core for Linux, which works across multiple Linux distributions, can support both OpenSSL 1.0.x and OpenSSL 1.1.x.</span></span>  <span data-ttu-id="587bd-103">.NET Core 2.1 および .NET Core 2.2 では、最初に 1.0.x が検索されてから、1.1.x にフォールバックされます。 .NET Core 3.0 では、最初に 1.1.x が検索されます。</span><span class="sxs-lookup"><span data-stu-id="587bd-103">.NET Core 2.1 and .NET Core 2.2 look for 1.0.x first, then fall back to 1.1.x; .NET Core 3.0 looks for 1.1.x first.</span></span> <span data-ttu-id="587bd-104">この変更は、新しい暗号化標準のサポートを追加するために行われました。</span><span class="sxs-lookup"><span data-stu-id="587bd-104">This change was made to add support for new cryptographic standards.</span></span>

<span data-ttu-id="587bd-105">この変更は、.NET Core で OpenSSL 固有の相互運用型とのプラットフォーム相互運用を行うライブラリまたはアプリケーションに影響を与える可能性があります。</span><span class="sxs-lookup"><span data-stu-id="587bd-105">This change may impact libraries or applications that do platform interop with the OpenSSL-specific interop types in .NET Core.</span></span>

#### <a name="change-description"></a><span data-ttu-id="587bd-106">変更の説明</span><span class="sxs-lookup"><span data-stu-id="587bd-106">Change description</span></span>

<span data-ttu-id="587bd-107">.NET Core 2.2 以前のバージョンで、ランタイムでは OpenSSL 1.1.x よりも 1.0.x の読み込みが優先されます。</span><span class="sxs-lookup"><span data-stu-id="587bd-107">In .NET Core 2.2 and earlier versions, the runtime prefers loading OpenSSL 1.0.x over 1.1.x.</span></span> <span data-ttu-id="587bd-108">これは、OpenSSL との相互運用に使用する <xref:System.IntPtr> と <xref:System.Runtime.InteropServices.SafeHandle> の型が優先設定に応じて libcrypto.so.1.0.0/libcrypto.so.1.0/libcrypto.so.10 のいずれかで使用されることを意味します。</span><span class="sxs-lookup"><span data-stu-id="587bd-108">This means that the <xref:System.IntPtr> and <xref:System.Runtime.InteropServices.SafeHandle> types for interop with OpenSSL are used with libcrypto.so.1.0.0 / libcrypto.so.1.0 / libcrypto.so.10 by preference.</span></span>

<span data-ttu-id="587bd-109">.NET Core 3.0 以降で、ランタイムでは OpenSSL 1.0.x よりも OpenSSL 1.1.x の読み込みが優先されるため、OpenSSL との相互運用に使用する <xref:System.IntPtr> と <xref:System.Runtime.InteropServices.SafeHandle> の型は優先設定に応じて libcrypto.so.1.1/libcrypto.so.11/libcrypto.so.1.1.0/libcrypto.so.1.1.1 のいずれかで使用されます。</span><span class="sxs-lookup"><span data-stu-id="587bd-109">Starting with .NET Core 3.0, the runtime prefers loading OpenSSL 1.1.x over OpenSSL 1.0.x, so the <xref:System.IntPtr> and <xref:System.Runtime.InteropServices.SafeHandle> types for interop with OpenSSL are used with libcrypto.so.1.1 / libcrypto.so.11 / libcrypto.so.1.1.0 / libcrypto.so.1.1.1 by preference.</span></span> <span data-ttu-id="587bd-110">その結果、OpenSSL と直接相互運用できるライブラリとアプリケーションは、.NET Core 2.1 または .NET Core 2.2 からアップグレードするときに、.NET Core で公開されている値と互換性のないポインターを持つ場合があります。</span><span class="sxs-lookup"><span data-stu-id="587bd-110">As a result, libraries and applications that interoperate with OpenSSL directly may have incompatible pointers with the .NET Core-exposed values when upgrading from .NET Core 2.1 or .NET Core 2.2.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="587bd-111">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="587bd-111">Version introduced</span></span>

<span data-ttu-id="587bd-112">3.0</span><span class="sxs-lookup"><span data-stu-id="587bd-112">3.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="587bd-113">推奨アクション</span><span class="sxs-lookup"><span data-stu-id="587bd-113">Recommended action</span></span>

<span data-ttu-id="587bd-114">OpenSSL を直接操作するライブラリやアプリケーションは、.NET Core ランタイムと同じバージョンの OpenSSL を使用するように注意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="587bd-114">Libraries and applications that do direct operations with OpenSSL need to be careful to ensure they are using the same version of OpenSSL as the .NET Core runtime.</span></span>

<span data-ttu-id="587bd-115">OpenSSL を直接使用する .NET Core 暗号化の種類から <xref:System.IntPtr> または <xref:System.Runtime.InteropServices.SafeHandle> の値を使用するすべてのライブラリやアプリケーションでは、新しい <xref:System.Security.Cryptography.SafeEvpPKeyHandle.OpenSslVersion?displayProperty=nameWithType> プロパティで使用するライブラリのバージョンを比較し、ポインターの互換性を確保する必要があります。</span><span class="sxs-lookup"><span data-stu-id="587bd-115">All libraries or applications that use <xref:System.IntPtr> or <xref:System.Runtime.InteropServices.SafeHandle> values from the .NET Core cryptographic types directly with OpenSSL should compare the version of the library they use with the new <xref:System.Security.Cryptography.SafeEvpPKeyHandle.OpenSslVersion?displayProperty=nameWithType> property to ensure the pointers are compatible.</span></span>

#### <a name="category"></a><span data-ttu-id="587bd-116">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="587bd-116">Category</span></span>

<span data-ttu-id="587bd-117">暗号</span><span class="sxs-lookup"><span data-stu-id="587bd-117">Cryptography</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="587bd-118">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="587bd-118">Affected APIs</span></span>

- <xref:System.Security.Cryptography.SafeEvpPKeyHandle.%23ctor%2A?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.RSAOpenSsl.%23ctor(System.IntPtr)?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.RSAOpenSsl.%23ctor(System.Security.Cryptography.SafeEvpPKeyHandle)?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.RSAOpenSsl.DuplicateKeyHandle?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.DSAOpenSsl.%23ctor(System.IntPtr)?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.DSAOpenSsl.%23ctor(System.Security.Cryptography.SafeEvpPKeyHandle)?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.DSAOpenSsl.DuplicateKeyHandle?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.ECDsaOpenSsl.%23ctor(System.IntPtr)?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.ECDsaOpenSsl.%23ctor(System.Security.Cryptography.SafeEvpPKeyHandle)?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.ECDsaOpenSsl.DuplicateKeyHandle?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.ECDiffieHellmanOpenSsl.%23ctor(System.IntPtr)?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.ECDiffieHellmanOpenSsl.%23ctor(System.Security.Cryptography.SafeEvpPKeyHandle)?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.ECDiffieHellmanOpenSsl.DuplicateKeyHandle?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.X509Certificates.X509Certificate.Handle?displayProperty=nameWithType>

<!--

### Affected APIs

- `Overload:System.Security.Cryptography.SafeEvpPKeyHandle.#ctor`
- `M:System.Security.Cryptography.RSAOpenSsl.#ctor(System.IntPtr)`
- `M:System.Security.Cryptography.RSAOpenSsl.#ctor(System.Security.Cryptography.SafeEvpPKeyHandle)`
- `M:System.Security.Cryptography.RSAOpenSsl.DuplicateKeyHandle`
- `M:System.Security.Cryptography.DSAOpenSsl.#ctor(System.IntPtr)`
- `M:System.Security.Cryptography.DSAOpenSsl.#ctor(System.Security.Cryptography.SafeEvpPKeyHandle)`
- `M:System.Security.Cryptography.DSAOpenSsl.DuplicateKeyHandle`
- `M:System.Security.Cryptography.ECDsaOpenSsl.#ctor(System.IntPtr)`
- `M:System.Security.Cryptography.ECDsaOpenSsl.#ctor(System.Security.CryptographySafeEvpPKeyHandle)`
- `M:System.Security.Cryptography.ECDsaOpenSsl.DuplicateKeyHandle`
- `M:System.Security.Cryptography.ECDiffieHellmanOpenSsl.#ctor(System.IntPtr)`
- `M:System.Security.Cryptography.ECDiffieHellmanOpenSsl.#ctor(System.Security.Cryptography.SafeEvpPKeyHandle)`
- `M:System.Security.Cryptography.ECDiffieHellmanOpenSsl.DuplicateKeyHandle`
- `P:System.Security.Cryptography.X509Certificates.X509Certificate.Handle`

-->
