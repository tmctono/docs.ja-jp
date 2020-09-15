---
ms.openlocfilehash: 9c3c0bf7fbd8d45eba84eaa8634fd2d834195702
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617207"
---
### <a name="systemuri-parsing-adheres-to-rfc-3987"></a><span data-ttu-id="291ce-101">System.Uri 解析が RFC 3987 に準拠</span><span class="sxs-lookup"><span data-stu-id="291ce-101">System.Uri parsing adheres to RFC 3987</span></span>

#### <a name="details"></a><span data-ttu-id="291ce-102">説明</span><span class="sxs-lookup"><span data-stu-id="291ce-102">Details</span></span>

<span data-ttu-id="291ce-103">.NET Framework 4.5 では、URI 解析がいくつかの点で変更されました。</span><span class="sxs-lookup"><span data-stu-id="291ce-103">URI parsing has changed in several ways in .NET Framework 4.5.</span></span> <span data-ttu-id="291ce-104">ただし、これらの変更は .NET Framework 4.5 を対象としたコードのみに影響することに注意してください。</span><span class="sxs-lookup"><span data-stu-id="291ce-104">Note, however, that these changes only affect code targeting .NET Framework 4.5.</span></span> <span data-ttu-id="291ce-105">バイナリが .NET Framework 4.0 を対象としている場合、以前の動作が実行されます。</span><span class="sxs-lookup"><span data-stu-id="291ce-105">If a binary targets .NET Framework 4.0, the old behavior will be observed.</span></span> <span data-ttu-id="291ce-106">.NET Framework 4.5 での URI 解析の変更は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="291ce-106">Changes to URI parsing in .NET Framework 4.5 include:</span></span>

- <span data-ttu-id="291ce-107">URI 解析は、RFC 3987 の最新の IRI 規則に従って、正規化と文字チェックを実行します。</span><span class="sxs-lookup"><span data-stu-id="291ce-107">URI parsing will perform normalization and character checking according to the latest IRI rules in RFC 3987.</span></span>
- <span data-ttu-id="291ce-108">Unicode 正規化フォーム C は、URI のホスト部分でのみ実行されます。</span><span class="sxs-lookup"><span data-stu-id="291ce-108">Unicode normalization form C will only be performed on the host portion of the URI.</span></span>
- <span data-ttu-id="291ce-109">無効な mailto:URI は、例外の原因になります。</span><span class="sxs-lookup"><span data-stu-id="291ce-109">Invalid mailto: URIs will now cause an exception.</span></span>
- <span data-ttu-id="291ce-110">パス セグメントの最後の末尾のドットが保存されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="291ce-110">Trailing dots at the end of a path segment are now preserved.</span></span>
- <span data-ttu-id="291ce-111">`file://` URI は `?` 文字をエスケープしません。</span><span class="sxs-lookup"><span data-stu-id="291ce-111">`file://` URIs do not escape the `?` character.</span></span>
- <span data-ttu-id="291ce-112">Unicode 制御文字の `U+0080` から `U+009F` まではサポートされません。</span><span class="sxs-lookup"><span data-stu-id="291ce-112">Unicode control characters `U+0080` through `U+009F` are not supported.</span></span>
- <span data-ttu-id="291ce-113">コンマ文字 `,` または `%2c` は自動的にエスケープ解除されません。</span><span class="sxs-lookup"><span data-stu-id="291ce-113">Comma characters `,` or `%2c` are not automatically unescaped.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="291ce-114">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="291ce-114">Suggestion</span></span>

<span data-ttu-id="291ce-115">古い .NET Framework 4.0 URI 解析セマンティクスが必要な場合 (めったにありません)、.NET Framework 4.0 を対象とすることによって使用できます。</span><span class="sxs-lookup"><span data-stu-id="291ce-115">If the old .NET Framework 4.0 URI parsing semantics are necessary (they often aren't), they can be used by targeting .NET Framework 4.0.</span></span> <span data-ttu-id="291ce-116">これは、アセンブリで <xref:System.Runtime.Versioning.TargetFrameworkAttribute?displayProperty=fullName> を使用することによって、または、[プロジェクトのプロパティ] ページの Visual Studio のプロジェクト システム UI によって実現できます。</span><span class="sxs-lookup"><span data-stu-id="291ce-116">This can be accomplished by using a <xref:System.Runtime.Versioning.TargetFrameworkAttribute?displayProperty=fullName> on the assembly, or through Visual Studio's project system UI in the 'project properties' page.</span></span>

| <span data-ttu-id="291ce-117">名前</span><span class="sxs-lookup"><span data-stu-id="291ce-117">Name</span></span>    | <span data-ttu-id="291ce-118">[値]</span><span class="sxs-lookup"><span data-stu-id="291ce-118">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="291ce-119">スコープ</span><span class="sxs-lookup"><span data-stu-id="291ce-119">Scope</span></span>   | <span data-ttu-id="291ce-120">Major</span><span class="sxs-lookup"><span data-stu-id="291ce-120">Major</span></span>       |
| <span data-ttu-id="291ce-121">バージョン</span><span class="sxs-lookup"><span data-stu-id="291ce-121">Version</span></span> | <span data-ttu-id="291ce-122">4.5</span><span class="sxs-lookup"><span data-stu-id="291ce-122">4.5</span></span>         |
| <span data-ttu-id="291ce-123">種類</span><span class="sxs-lookup"><span data-stu-id="291ce-123">Type</span></span>    | <span data-ttu-id="291ce-124">再ターゲット中</span><span class="sxs-lookup"><span data-stu-id="291ce-124">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="291ce-125">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="291ce-125">Affected APIs</span></span>

- <xref:System.Uri.%23ctor(System.String)>
- <xref:System.Uri.%23ctor(System.String,System.Boolean)>
- <xref:System.Uri.%23ctor(System.String,System.UriKind)>
- <xref:System.Uri.%23ctor(System.Uri,System.String)>
- <xref:System.Uri.TryCreate(System.String,System.UriKind,System.Uri@)?displayProperty=nameWithType>
- <xref:System.Uri.TryCreate(System.Uri,System.String,System.Uri@)?displayProperty=nameWithType>
- <xref:System.Uri.TryCreate(System.Uri,System.Uri,System.Uri@)?displayProperty=nameWithType>
