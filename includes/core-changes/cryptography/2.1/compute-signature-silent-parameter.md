---
ms.openlocfilehash: 9583d868ee01117d7bd6e465e7d89a734489d1a8
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "77449223"
---
### <a name="boolean-parameter-of-signedcmscomputesignature-is-respected"></a><span data-ttu-id="9565a-101">SignedCms.ComputeSignature のブール型パラメーターの尊重</span><span class="sxs-lookup"><span data-stu-id="9565a-101">Boolean parameter of SignedCms.ComputeSignature is respected</span></span>

<span data-ttu-id="9565a-102">.NET Core では、<xref:System.Security.Cryptography.Pkcs.SignedCms.ComputeSignature(System.Security.Cryptography.Pkcs.CmsSigner,System.Boolean)?displayProperty=nameWithType> メソッドのブール型の `silent` パラメーターが尊重されます。</span><span class="sxs-lookup"><span data-stu-id="9565a-102">In .NET Core, the Boolean `silent` parameter of the <xref:System.Security.Cryptography.Pkcs.SignedCms.ComputeSignature(System.Security.Cryptography.Pkcs.CmsSigner,System.Boolean)?displayProperty=nameWithType> method is respected.</span></span> <span data-ttu-id="9565a-103">このパラメーターが `true` に設定されている場合、PIN プロンプトは表示されません。</span><span class="sxs-lookup"><span data-stu-id="9565a-103">A PIN prompt is not shown if this parameter is set to `true`.</span></span>

#### <a name="change-description"></a><span data-ttu-id="9565a-104">変更の説明</span><span class="sxs-lookup"><span data-stu-id="9565a-104">Change description</span></span>

<span data-ttu-id="9565a-105">.NET Framework では、<xref:System.Security.Cryptography.Pkcs.SignedCms.ComputeSignature(System.Security.Cryptography.Pkcs.CmsSigner,System.Boolean)?displayProperty=nameWithType> メソッドの `silent` パラメーターは無視され、プロバイダーから要求された場合は常に PIN プロンプトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="9565a-105">In .NET Framework, the `silent` parameter of the <xref:System.Security.Cryptography.Pkcs.SignedCms.ComputeSignature(System.Security.Cryptography.Pkcs.CmsSigner,System.Boolean)?displayProperty=nameWithType> method is ignored, and a PIN prompt is always shown if required by the provider.</span></span> <span data-ttu-id="9565a-106">.NET Core では、`silent` パラメーターが尊重されます。`true` に設定すると、プロバイダーから要求される場合でも PIN プロンプトは表示されません。</span><span class="sxs-lookup"><span data-stu-id="9565a-106">In .NET Core, the `silent` parameter is respected, and if set to `true`, a PIN prompt is never shown, even if it's required by the provider.</span></span>

<span data-ttu-id="9565a-107">.NET Core のバージョン 2.1 では、CMS/PKCS #7 メッセージのサポートが導入されました。</span><span class="sxs-lookup"><span data-stu-id="9565a-107">Support for CMS/PKCS #7 messages was introduced into .NET Core in version 2.1.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="9565a-108">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="9565a-108">Version introduced</span></span>

<span data-ttu-id="9565a-109">2.1</span><span class="sxs-lookup"><span data-stu-id="9565a-109">2.1</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="9565a-110">推奨アクション</span><span class="sxs-lookup"><span data-stu-id="9565a-110">Recommended action</span></span>

<span data-ttu-id="9565a-111">必要に応じて PIN プロンプトが表示されるようにするには、デスクトップ アプリケーションで <xref:System.Security.Cryptography.Pkcs.SignedCms.ComputeSignature(System.Security.Cryptography.Pkcs.CmsSigner,System.Boolean)?displayProperty=nameWithType> を呼び出し、ブール型パラメーターを `false` に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9565a-111">To ensure a PIN prompt appears if required, desktop applications should call <xref:System.Security.Cryptography.Pkcs.SignedCms.ComputeSignature(System.Security.Cryptography.Pkcs.CmsSigner,System.Boolean)?displayProperty=nameWithType> and set the Boolean parameter to `false`.</span></span> <span data-ttu-id="9565a-112">結果の動作は、サイレント コンテキストが無効かどうかに関係なく .NET Framework と同じになります。</span><span class="sxs-lookup"><span data-stu-id="9565a-112">The resulting behavior is the same as on .NET Framework regardless of whether the silent context is disabled there.</span></span>

### <a name="category"></a><span data-ttu-id="9565a-113">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="9565a-113">Category</span></span>

<span data-ttu-id="9565a-114">暗号</span><span class="sxs-lookup"><span data-stu-id="9565a-114">Cryptography</span></span>

### <a name="affected-apis"></a><span data-ttu-id="9565a-115">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="9565a-115">Affected APIs</span></span>

- <xref:System.Security.Cryptography.Pkcs.SignedCms.ComputeSignature(System.Security.Cryptography.Pkcs.CmsSigner,System.Boolean)?displayProperty=nameWithType>

<!--

### Affected APIs

- `M:System.Security.Cryptography.Pkcs.SignedCms.ComputeSignature(System.Security.Cryptography.Pkcs.CmsSigner,System.Boolean)`

-->
