---
ms.openlocfilehash: 4788f5b80306116e63ee56584d65b862ce0606ee
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497170"
---
### <a name="rsacng-and-dsacng-are-once-again-usable-in-partial-trust-scenarios"></a><span data-ttu-id="0b0f9-101">部分信頼のシナリオで RSACng と DSACng が再び使用可能に</span><span class="sxs-lookup"><span data-stu-id="0b0f9-101">RSACng and DSACng are once again usable in Partial Trust scenarios</span></span>

#### <a name="details"></a><span data-ttu-id="0b0f9-102">説明</span><span class="sxs-lookup"><span data-stu-id="0b0f9-102">Details</span></span>

<span data-ttu-id="0b0f9-103">CngLightup (<xref:System.Security.Cryptography.Xml.EncryptedXml?displayProperty=nameWithType> などの複数の上位レベル暗号化 API で使われます) および <xref:System.Security.Cryptography.RSACng?displayProperty=nameWithType> は、完全信頼に依存する場合があります。</span><span class="sxs-lookup"><span data-stu-id="0b0f9-103">CngLightup (used in several higher-level crypto apis, such as <xref:System.Security.Cryptography.Xml.EncryptedXml?displayProperty=nameWithType>) and <xref:System.Security.Cryptography.RSACng?displayProperty=nameWithType> in some cases rely on full trust.</span></span> <span data-ttu-id="0b0f9-104">たとえば、<xref:System.Security.Permissions.SecurityPermissionFlag.UnmanagedCode?displayProperty=nameWithType> アクセス許可をアサートしない P/Invoke や、<xref:System.Security.Cryptography.CngKey?displayProperty=nameWithType> に <xref:System.Security.Permissions.SecurityPermissionFlag.UnmanagedCode?displayProperty=nameWithType> に対するアクセス許可要求があるコード パスなどです。</span><span class="sxs-lookup"><span data-stu-id="0b0f9-104">These include P/Invokes without asserting <xref:System.Security.Permissions.SecurityPermissionFlag.UnmanagedCode?displayProperty=nameWithType> permissions, and code paths where <xref:System.Security.Cryptography.CngKey?displayProperty=nameWithType> has permission demands for <xref:System.Security.Permissions.SecurityPermissionFlag.UnmanagedCode?displayProperty=nameWithType>.</span></span> <span data-ttu-id="0b0f9-105">.NET Framework 4.6.2 以降では、CngLightup は可能な場合に常に <xref:System.Security.Cryptography.RSACng?displayProperty=nameWithType> に切り替えるために使われました。</span><span class="sxs-lookup"><span data-stu-id="0b0f9-105">Starting with the .NET Framework 4.6.2, CngLightup was used to switch to <xref:System.Security.Cryptography.RSACng?displayProperty=nameWithType> wherever possible.</span></span> <span data-ttu-id="0b0f9-106">その結果、<xref:System.Security.Cryptography.Xml.EncryptedXml?displayProperty=nameWithType> を正常に使っていた部分信頼アプリが、失敗して <xref:System.Security.SecurityException> 例外をスローするようになりました。この変更では、CngLightup を使っているすべての関数が必要なアクセス許可を持つように、必要なアサートが追加されます。</span><span class="sxs-lookup"><span data-stu-id="0b0f9-106">As a result, partial trust apps that successfully used <xref:System.Security.Cryptography.Xml.EncryptedXml?displayProperty=nameWithType> began to fail and throw <xref:System.Security.SecurityException> exceptions.This change adds the required asserts so that all functions using CngLightup have the required permissions.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="0b0f9-107">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="0b0f9-107">Suggestion</span></span>

<span data-ttu-id="0b0f9-108">.NET Framework 4.6.2 でのこの変更により部分信頼アプリに悪影響があった場合は、.NET Framework 4.7.1 にアップグレードしてください。</span><span class="sxs-lookup"><span data-stu-id="0b0f9-108">If this change in the .NET Framework 4.6.2 has negatively impacted your partial trust apps, upgrade to the .NET Framework 4.7.1.</span></span>

| <span data-ttu-id="0b0f9-109">名前</span><span class="sxs-lookup"><span data-stu-id="0b0f9-109">Name</span></span>    | <span data-ttu-id="0b0f9-110">値</span><span class="sxs-lookup"><span data-stu-id="0b0f9-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="0b0f9-111">スコープ</span><span class="sxs-lookup"><span data-stu-id="0b0f9-111">Scope</span></span>   |<span data-ttu-id="0b0f9-112">エッジ</span><span class="sxs-lookup"><span data-stu-id="0b0f9-112">Edge</span></span>|
|<span data-ttu-id="0b0f9-113">バージョン</span><span class="sxs-lookup"><span data-stu-id="0b0f9-113">Version</span></span>|<span data-ttu-id="0b0f9-114">4.6.2</span><span class="sxs-lookup"><span data-stu-id="0b0f9-114">4.6.2</span></span>|
|<span data-ttu-id="0b0f9-115">種類</span><span class="sxs-lookup"><span data-stu-id="0b0f9-115">Type</span></span>|<span data-ttu-id="0b0f9-116">ランタイム</span><span class="sxs-lookup"><span data-stu-id="0b0f9-116">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="0b0f9-117">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="0b0f9-117">Affected APIs</span></span>

- <xref:System.Security.Cryptography.DSACng.%23ctor(System.Security.Cryptography.CngKey)>
- <xref:System.Security.Cryptography.DSACng.Key?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.DSACng.LegalKeySizes?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.DSACng.CreateSignature(System.Byte[])?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.DSACng.VerifySignature(System.Byte[],System.Byte[])?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.RSACng.%23ctor(System.Security.Cryptography.CngKey)>
- <xref:System.Security.Cryptography.RSACng.Key?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.RSACng.Decrypt(System.Byte[],System.Security.Cryptography.RSAEncryptionPadding)?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.RSACng.SignHash(System.Byte[],System.Security.Cryptography.HashAlgorithmName,System.Security.Cryptography.RSASignaturePadding)?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Security.Cryptography.DSACng.#ctor(System.Security.Cryptography.CngKey)`
- `P:System.Security.Cryptography.DSACng.Key`
- `P:System.Security.Cryptography.DSACng.LegalKeySizes`
- `M:System.Security.Cryptography.DSACng.CreateSignature(System.Byte[])`
- `M:System.Security.Cryptography.DSACng.VerifySignature(System.Byte[],System.Byte[])`
- `M:System.Security.Cryptography.RSACng.#ctor(System.Security.Cryptography.CngKey)`
- `P:System.Security.Cryptography.RSACng.Key`
- `M:System.Security.Cryptography.RSACng.Decrypt(System.Byte[],System.Security.Cryptography.RSAEncryptionPadding)`
- `M:System.Security.Cryptography.RSACng.SignHash(System.Byte[],System.Security.Cryptography.HashAlgorithmName,System.Security.Cryptography.RSASignaturePadding)`

-->
