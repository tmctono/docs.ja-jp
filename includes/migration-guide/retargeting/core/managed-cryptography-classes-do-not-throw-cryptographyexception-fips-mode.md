---
ms.openlocfilehash: 0b62eff8d70873293aafa539f40bf032672df57a
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85616269"
---
### <a name="managed-cryptography-classes-do-not-throw-a-cryptographyexception-in-fips-mode"></a><span data-ttu-id="c74fe-101">FIPS モードのマネージド暗号クラスで CryptographyException がスローされない</span><span class="sxs-lookup"><span data-stu-id="c74fe-101">Managed cryptography classes do not throw a CryptographyException in FIPS mode</span></span>

#### <a name="details"></a><span data-ttu-id="c74fe-102">説明</span><span class="sxs-lookup"><span data-stu-id="c74fe-102">Details</span></span>

<span data-ttu-id="c74fe-103">.NET Framework 4.7.2 以前のバージョンでは、システムの暗号化ライブラリが FIPS モードで構成されていると、<xref:System.Security.Cryptography.SHA256Managed> などのマネージド暗号化プロバイダー クラスで <xref:System.Security.Cryptography.CryptographicException> がスローされます。</span><span class="sxs-lookup"><span data-stu-id="c74fe-103">In .NET Framework 4.7.2 and earlier versions, managed cryptographic provider classes such as <xref:System.Security.Cryptography.SHA256Managed> throw a <xref:System.Security.Cryptography.CryptographicException> when the system cryptographic libraries are configured in FIPS mode.</span></span> <span data-ttu-id="c74fe-104">これらの例外がスローされるのは、マネージド バージョンが FIPS (Federal Information Processing Standards) 140-2 の認定を受けていないためであり、また、FIPS ルールに基づく承認の対象と見なされなかった暗号アルゴリズムをブロックするためです。</span><span class="sxs-lookup"><span data-stu-id="c74fe-104">These exceptions are thrown because the managed versions have not undergone FIPS (Federal Information Processing Standards) 140-2 certification, as well as to block cryptographic algorithms that were not considered to be approved based on the FIPS rules.</span></span>  <span data-ttu-id="c74fe-105">少数の開発者は開発用コンピューターを FIPS モードで利用するため、これらの例外は運用システムでのみ頻繁にスローされます。 .NET Framework 4.8 以降のバージョンをターゲットとするアプリケーションでは、より新しい緩いポリシーに自動的に切り替えられるため、そのような場合、<xref:System.Security.Cryptography.CryptographicException> が既定でスローされなくなりました。</span><span class="sxs-lookup"><span data-stu-id="c74fe-105">Because few developers have their development machines in FIPS mode, these exceptions are frequently thrown only on production systems.Applications that target .NET Framework 4.8 and later versions automatically switch to the newer, relaxed policy, so that a <xref:System.Security.Cryptography.CryptographicException> is no longer thrown by default in such cases.</span></span> <span data-ttu-id="c74fe-106">代わりに、マネージド暗号化クラスでは、暗号化操作がシステムの暗号化ライブラリにリダイレクトされます。</span><span class="sxs-lookup"><span data-stu-id="c74fe-106">Instead, the managed cryptography classes redirect cryptographic operations to a system cryptography library.</span></span> <span data-ttu-id="c74fe-107">このポリシー変更により、開発者環境と運用環境での混乱を招く可能性のある違いは実質的になくなり、ネイティブ コンポーネントとマネージド コンポーネントは同じ暗号化ポリシーの下で動作するようになります。</span><span class="sxs-lookup"><span data-stu-id="c74fe-107">This policy change effectively removes a potentially confusing difference between developer environments and the production environments and makes native components and managed components operate under the same cryptographic policy.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="c74fe-108">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="c74fe-108">Suggestion</span></span>

<span data-ttu-id="c74fe-109">この動作が望ましくない場合は、それを選択せずに、以前の動作を復元し、次の [AppContextSwitchOverrides](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) 構成設定を、アプリケーション構成ファイルの [\<runtime>](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) セクションに追加することで、<xref:System.Security.Cryptography.CryptographicException> が FIPS モードでスローされるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="c74fe-109">If this behavior is undesirable, you can opt out of it and restore the previous behavior so that a <xref:System.Security.Cryptography.CryptographicException> is thrown in FIPS mode by adding the following [AppContextSwitchOverrides](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) configuration setting to the [\<runtime>](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) section of your application configuration file:</span></span>

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.Security.Cryptography.UseLegacyFipsThrow=true" />
</runtime>
```

<span data-ttu-id="c74fe-110">アプリケーションのターゲットが .NET Framework 4.7.2 以前である場合は、次の [AppContextSwitchOverrides](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) 構成設定を、アプリケーション構成ファイルの [\<runtime>](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) セクションに追加することで、この変更を選択することもできます。</span><span class="sxs-lookup"><span data-stu-id="c74fe-110">If your application targets .NET Framework 4.7.2 or earlier, you can also opt in to this change by adding the following [AppContextSwitchOverrides](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) configuration setting to the [\<runtime>](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) section of your application configuration file:</span></span>

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.Security.Cryptography.UseLegacyFipsThrow=false" />
</runtime>
```

| <span data-ttu-id="c74fe-111">名前</span><span class="sxs-lookup"><span data-stu-id="c74fe-111">Name</span></span>    | <span data-ttu-id="c74fe-112">[値]</span><span class="sxs-lookup"><span data-stu-id="c74fe-112">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="c74fe-113">スコープ</span><span class="sxs-lookup"><span data-stu-id="c74fe-113">Scope</span></span>   | <span data-ttu-id="c74fe-114">エッジ</span><span class="sxs-lookup"><span data-stu-id="c74fe-114">Edge</span></span>        |
| <span data-ttu-id="c74fe-115">バージョン</span><span class="sxs-lookup"><span data-stu-id="c74fe-115">Version</span></span> | <span data-ttu-id="c74fe-116">4.8</span><span class="sxs-lookup"><span data-stu-id="c74fe-116">4.8</span></span>         |
| <span data-ttu-id="c74fe-117">種類</span><span class="sxs-lookup"><span data-stu-id="c74fe-117">Type</span></span>    | <span data-ttu-id="c74fe-118">再ターゲット中</span><span class="sxs-lookup"><span data-stu-id="c74fe-118">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="c74fe-119">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="c74fe-119">Affected APIs</span></span>

- <xref:System.Security.Cryptography.AesManaged?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.MD5Cng?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.MD5CryptoServiceProvider?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.RC2CryptoServiceProvider?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.RijndaelManaged?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.RIPEMD160Managed?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.SHA1Managed?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.SHA256Managed?displayProperty=nameWithType>
