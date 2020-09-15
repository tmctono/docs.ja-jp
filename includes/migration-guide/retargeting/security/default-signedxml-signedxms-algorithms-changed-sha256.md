---
ms.openlocfilehash: e2ae329d027d605e6331afe422e550990fab1042
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614808"
---
### <a name="default-signedxml-and-signedxms-algorithms-changed-to-sha256"></a><span data-ttu-id="9222b-101">既定の SignedXML アルゴリズムと SignedXMS アルゴリズムが SHA256 に変更</span><span class="sxs-lookup"><span data-stu-id="9222b-101">Default SignedXML and SignedXMS algorithms changed to SHA256</span></span>

#### <a name="details"></a><span data-ttu-id="9222b-102">説明</span><span class="sxs-lookup"><span data-stu-id="9222b-102">Details</span></span>

<span data-ttu-id="9222b-103">.NET Framework 4.7 以前では、一部の操作において SignedXML と SignedCMS の初期設定が SHA1 でした。 .NET Framework 4.7.1 より、同じ操作で SHA256 が既定で有効になります。</span><span class="sxs-lookup"><span data-stu-id="9222b-103">In the .NET Framework 4.7 and earlier, SignedXML and SignedCMS default to SHA1 for some operations.Starting with the .NET Framework 4.7.1, SHA256 is enabled by default for these operations.</span></span> <span data-ttu-id="9222b-104">この変更が必要になったのは、SHA1 は安全であると見なされなくなったためです。</span><span class="sxs-lookup"><span data-stu-id="9222b-104">This change is necessary because SHA1 is no longer considered to be secure.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="9222b-105">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="9222b-105">Suggestion</span></span>

<span data-ttu-id="9222b-106">SHA1 (安全でない) または SHA256 を既定で使用するかどうかを制御する新しいコンテキスト スイッチ値が 2 つあります。</span><span class="sxs-lookup"><span data-stu-id="9222b-106">There are two new context switch values to control whether SHA1 (insecure) or SHA256 is used by default:</span></span>

- <span data-ttu-id="9222b-107">Switch.System.Security.Cryptography.Xml.UseInsecureHashAlgorithms</span><span class="sxs-lookup"><span data-stu-id="9222b-107">Switch.System.Security.Cryptography.Xml.UseInsecureHashAlgorithms</span></span>
- <span data-ttu-id="9222b-108">Switch.System.Security.Cryptography.Pkcs.UseInsecureHashAlgorithms。.NET Framework 4.7.1 以降のバージョンを対象とするアプリケーションで SHA256 の使用が望ましくない場合は、アプリ構成ファイルの [runtime](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) セクションに次の構成スイッチを追加することで既定を SHA1 に戻すことができます。</span><span class="sxs-lookup"><span data-stu-id="9222b-108">Switch.System.Security.Cryptography.Pkcs.UseInsecureHashAlgorithms For applications that target the .NET Framework 4.7.1 and later versions, if the use of SHA256 is undesirable, you can restore the default to SHA1 by adding the following configuration switch to the [runtime](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) section of your app config file:</span></span>

```xml
<AppContextSwitchOverrides value="Switch.System.Security.Cryptography.Xml.UseInsecureHashAlgorithms=true;Switch.System.Security.Cryptography.Pkcs.UseInsecureHashAlgorithms=true" />
```

<span data-ttu-id="9222b-109">.NET Framework 4.7 以前のバージョンを対象とするアプリケーションの場合、アプリの構成ファイルの [runtime](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) セクションに次の構成スイッチを追加することでこの変更を選択できます。</span><span class="sxs-lookup"><span data-stu-id="9222b-109">For applications that target the .NET Framework 4.7 and earlier versions, you can opt into this change by adding the following configuration switch to the [runtime](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) section of your app config file:</span></span>

```xml
<AppContextSwitchOverrides value="Switch.System.Security.Cryptography.Xml.UseInsecureHashAlgorithms=false;Switch.System.Security.Cryptography.Pkcs.UseInsecureHashAlgorithms=false" />
```

| <span data-ttu-id="9222b-110">名前</span><span class="sxs-lookup"><span data-stu-id="9222b-110">Name</span></span>    | <span data-ttu-id="9222b-111">[値]</span><span class="sxs-lookup"><span data-stu-id="9222b-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="9222b-112">スコープ</span><span class="sxs-lookup"><span data-stu-id="9222b-112">Scope</span></span>   | <span data-ttu-id="9222b-113">マイナー</span><span class="sxs-lookup"><span data-stu-id="9222b-113">Minor</span></span>       |
| <span data-ttu-id="9222b-114">バージョン</span><span class="sxs-lookup"><span data-stu-id="9222b-114">Version</span></span> | <span data-ttu-id="9222b-115">4.7.1</span><span class="sxs-lookup"><span data-stu-id="9222b-115">4.7.1</span></span>       |
| <span data-ttu-id="9222b-116">種類</span><span class="sxs-lookup"><span data-stu-id="9222b-116">Type</span></span>    | <span data-ttu-id="9222b-117">再ターゲット中</span><span class="sxs-lookup"><span data-stu-id="9222b-117">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="9222b-118">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="9222b-118">Affected APIs</span></span>

- <xref:System.Security.Cryptography.Pkcs.CmsSigner?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.Xml.SignedXml?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.Xml.Reference?displayProperty=nameWithType>
