---
ms.openlocfilehash: ccd056f23d26e6cce4cc691542784792bffe9fc6
ms.sourcegitcommit: 8bfeb5930ca48b2ee6053f16082dcaf24d46d221
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/18/2020
ms.locfileid: "88558182"
---
### <a name="environmentosversion-returns-the-correct-operating-system-version"></a><span data-ttu-id="33079-101">Environment.OSVersion で正しいオペレーティング システム バージョンが返される</span><span class="sxs-lookup"><span data-stu-id="33079-101">Environment.OSVersion returns the correct operating system version</span></span>

<span data-ttu-id="33079-102"><xref:System.Environment.OSVersion?displayProperty=nameWithType> で、アプリケーションの互換性のために選択される OS などではなく、オペレーティング システム (OS) の実際のバージョンが返されます。</span><span class="sxs-lookup"><span data-stu-id="33079-102"><xref:System.Environment.OSVersion?displayProperty=nameWithType> returns the actual version of the operating system (OS) instead of, for example, the OS that's selected for application compatibility.</span></span>

#### <a name="change-description"></a><span data-ttu-id="33079-103">変更の説明</span><span class="sxs-lookup"><span data-stu-id="33079-103">Change description</span></span>

<span data-ttu-id="33079-104">以前のバージョンの .NET では、アプリケーションが Windows 互換モードで実行されている場合、<xref:System.Environment.OSVersion?displayProperty=nameWithType> によって、正しくない可能性がある OS バージョンが返されます。</span><span class="sxs-lookup"><span data-stu-id="33079-104">In previous .NET versions, <xref:System.Environment.OSVersion?displayProperty=nameWithType> returns an OS version that may be incorrect when an application runs under Windows compatibility mode.</span></span> <span data-ttu-id="33079-105">詳細については、[GetVersionExA 関数の解説](/windows/win32/api/sysinfoapi/nf-sysinfoapi-getversionexa#remarks)に関する記述を参照してください。</span><span class="sxs-lookup"><span data-stu-id="33079-105">For more information, see [GetVersionExA function remarks](/windows/win32/api/sysinfoapi/nf-sysinfoapi-getversionexa#remarks).</span></span>

<span data-ttu-id="33079-106">.NET 5.0 以降では、<xref:System.Environment.OSVersion?displayProperty=nameWithType> によってオペレーティング システムの実際のバージョンが返されます。</span><span class="sxs-lookup"><span data-stu-id="33079-106">Starting in .NET 5.0, <xref:System.Environment.OSVersion?displayProperty=nameWithType> returns the actual version of the operating system.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="33079-107">変更理由</span><span class="sxs-lookup"><span data-stu-id="33079-107">Reason for change</span></span>

<span data-ttu-id="33079-108">このプロパティのユーザーは、オペレーティング システムの実際のバージョンが返されることを期待しています。</span><span class="sxs-lookup"><span data-stu-id="33079-108">Users of this property expect it to return the actual version of the operating system.</span></span> <span data-ttu-id="33079-109">ほとんどの .NET アプリにより、アプリケーション マニフェストでサポートされているバージョンが指定されないため、dotnet ホストから既定でサポートされているバージョンが取得されます。</span><span class="sxs-lookup"><span data-stu-id="33079-109">Most .NET apps don't specify their supported version in their application manifest, and thus get the default supported version from the dotnet host.</span></span> <span data-ttu-id="33079-110">その結果、実行されているアプリでは互換性 shim はほとんど意味がなくなります。</span><span class="sxs-lookup"><span data-stu-id="33079-110">As a result, the compatibility shim is rarely meaningful for the app that's running.</span></span> <span data-ttu-id="33079-111">Windows で新しいバージョンがリリースされており、古い dotnet ホストがまだ使用されている場合は、これらのアプリの OS バージョンが正しくない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="33079-111">When Windows releases a new version and an older dotnet host is still in use, these apps may get an incorrect OS version.</span></span> <span data-ttu-id="33079-112">実際のバージョンを返すことが、この API に対する開発者の期待により沿うことになります。</span><span class="sxs-lookup"><span data-stu-id="33079-112">Returning the actual version is more inline with developers' expectations of this API.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="33079-113">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="33079-113">Version introduced</span></span>

<span data-ttu-id="33079-114">5.0</span><span class="sxs-lookup"><span data-stu-id="33079-114">5.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="33079-115">推奨アクション</span><span class="sxs-lookup"><span data-stu-id="33079-115">Recommended action</span></span>

<span data-ttu-id="33079-116"><xref:System.Environment.OSVersion?displayProperty=nameWithType> を使用するコードを確認してテストし、確実に期待どおりに動作するようにします。</span><span class="sxs-lookup"><span data-stu-id="33079-116">Review and test any code that uses <xref:System.Environment.OSVersion?displayProperty=nameWithType> to ensure it behaves as desired.</span></span>

#### <a name="category"></a><span data-ttu-id="33079-117">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="33079-117">Category</span></span>

<span data-ttu-id="33079-118">Core .NET ライブラリ</span><span class="sxs-lookup"><span data-stu-id="33079-118">Core .NET libraries</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="33079-119">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="33079-119">Affected APIs</span></span>

- <xref:System.Environment.OSVersion?displayProperty=fullName>

<!--

#### Affected APIs

- `P:System.Environment.OSVersion`

-->
