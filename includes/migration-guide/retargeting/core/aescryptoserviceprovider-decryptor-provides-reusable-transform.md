---
ms.openlocfilehash: 36a9db601f7637185bf48dfcbe2233b4489fcdcf
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614660"
---
### <a name="aescryptoserviceprovider-decryptor-provides-a-reusable-transform"></a><span data-ttu-id="57688-101">AesCryptoServiceProvider の復号で変換が再利用可能に</span><span class="sxs-lookup"><span data-stu-id="57688-101">AesCryptoServiceProvider decryptor provides a reusable transform</span></span>

#### <a name="details"></a><span data-ttu-id="57688-102">説明</span><span class="sxs-lookup"><span data-stu-id="57688-102">Details</span></span>

<span data-ttu-id="57688-103">.NET Framework 4.6.2 以降を対象とするアプリでは、<xref:System.Security.Cryptography.AesCryptoServiceProvider> の復号で変換を再利用できます。</span><span class="sxs-lookup"><span data-stu-id="57688-103">Starting with apps that target the .NET Framework 4.6.2, the <xref:System.Security.Cryptography.AesCryptoServiceProvider> decryptor provides a reusable transform.</span></span> <span data-ttu-id="57688-104"><xref:System.Security.Cryptography.CryptoAPITransform.TransformFinalBlock(System.Byte[],System.Int32,System.Int32)?displayProperty=fullName> の呼び出しの後、変換は初期化し直され、再利用することができます。</span><span class="sxs-lookup"><span data-stu-id="57688-104">After a call to <xref:System.Security.Cryptography.CryptoAPITransform.TransformFinalBlock(System.Byte[],System.Int32,System.Int32)?displayProperty=fullName>, the transform is reinitialized and can be reused.</span></span> <span data-ttu-id="57688-105">以前のバージョンの .NET Framework を対象とするアプリでは、<xref:System.Security.Cryptography.CryptoAPITransform.TransformFinalBlock(System.Byte[],System.Int32,System.Int32)?displayProperty=fullName> の呼び出しの後に、<xref:System.Security.Cryptography.CryptoAPITransform.TransformBlock(System.Byte[],System.Int32,System.Int32,System.Byte[],System.Int32)?displayProperty=fullName> を呼び出して、復号を再利用しようとすると、<xref:System.Security.Cryptography.CryptographicException> をスローするか、破損しているデータが生成されます。</span><span class="sxs-lookup"><span data-stu-id="57688-105">For apps that target earlier versions of the .NET Framework, attempting to reuse the decryptor by calling <xref:System.Security.Cryptography.CryptoAPITransform.TransformBlock(System.Byte[],System.Int32,System.Int32,System.Byte[],System.Int32)?displayProperty=fullName> after a call to <xref:System.Security.Cryptography.CryptoAPITransform.TransformFinalBlock(System.Byte[],System.Int32,System.Int32)?displayProperty=fullName> throws a <xref:System.Security.Cryptography.CryptographicException> or produces corrupted data.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="57688-106">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="57688-106">Suggestion</span></span>

<span data-ttu-id="57688-107">この動作は想定済みであり、この変更の影響は最小限に抑えられているはずです。この変更の影響は前の動作に依存するアプリケーションは、そのアプリケーションの構成ファイルの `<runtime>` セクションに次の構成設定を追加して、この動作の使用を無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="57688-107">The impact of this change should be minimal, since this is the expected behavior.Applications that depend on the previous behavior can opt out of it using it by adding the following configuration setting to the `<runtime>` section of the application's configuration file:</span></span>

```xml
<runtime>
<AppContextSwitchOverrides value="Switch.System.Security.Cryptography.AesCryptoServiceProvider.DontCorrectlyResetDecryptor=true"/>
</runtime>
```

<span data-ttu-id="57688-108">また、以前のバージョンの .NET Framework を対象とするものの、.NET Framework 4.6.2 以降のバージョンの .NET Framework で実行されているアプリでは、そのアプリケーションの構成ファイルの `<runtime>` セクションに次の構成設定を追加して、この動作を有効にできます。</span><span class="sxs-lookup"><span data-stu-id="57688-108">In addition, applications that target a previous version of the .NET Framework but are running under a version of the .NET Framework starting with .NET Framework 4.6.2 can opt in to it by adding the following configuration setting to the `<runtime>` section of the application's configuration file:</span></span>

```xml
<runtime>
<AppContextSwitchOverrides value="Switch.System.Security.Cryptography.AesCryptoServiceProvider.DontCorrectlyResetDecryptor=false"/>
</runtime>
```

| <span data-ttu-id="57688-109">名前</span><span class="sxs-lookup"><span data-stu-id="57688-109">Name</span></span>    | <span data-ttu-id="57688-110">値</span><span class="sxs-lookup"><span data-stu-id="57688-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="57688-111">スコープ</span><span class="sxs-lookup"><span data-stu-id="57688-111">Scope</span></span>   | <span data-ttu-id="57688-112">マイナー</span><span class="sxs-lookup"><span data-stu-id="57688-112">Minor</span></span>       |
| <span data-ttu-id="57688-113">バージョン</span><span class="sxs-lookup"><span data-stu-id="57688-113">Version</span></span> | <span data-ttu-id="57688-114">4.6.2</span><span class="sxs-lookup"><span data-stu-id="57688-114">4.6.2</span></span>       |
| <span data-ttu-id="57688-115">種類</span><span class="sxs-lookup"><span data-stu-id="57688-115">Type</span></span>    | <span data-ttu-id="57688-116">再ターゲット中</span><span class="sxs-lookup"><span data-stu-id="57688-116">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="57688-117">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="57688-117">Affected APIs</span></span>

- <xref:System.Security.Cryptography.AesCryptoServiceProvider.CreateDecryptor?displayProperty=nameWithType>
