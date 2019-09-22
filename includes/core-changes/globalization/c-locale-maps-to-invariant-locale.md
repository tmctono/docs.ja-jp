---
ms.openlocfilehash: 9e9e443be9ea51d214e95c676fc28f0d8790af8b
ms.sourcegitcommit: a4b10e1f2a8bb4e8ff902630855474a0c4f1b37a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2019
ms.locfileid: "71117175"
---
### <a name="c-locale-maps-to-the-invariant-locale"></a><span data-ttu-id="b6800-101">"C" ロケールは、インバリアント ロケールにマップされます</span><span class="sxs-lookup"><span data-stu-id="b6800-101">"C" locale maps to the invariant locale</span></span>

<span data-ttu-id="b6800-102">.NET Core 2.2 以前のバージョンでは、"C" ロケールを en_US_POSIX ロケールにマップする既定の ICU 動作に依存しています。</span><span class="sxs-lookup"><span data-stu-id="b6800-102">.NET Core 2.2 and earlier versions depend on the default ICU behavior, which maps the "C" locale to the en_US_POSIX locale.</span></span> <span data-ttu-id="b6800-103">en_US_POSIX ロケールでは、大文字と小文字を区別しない文字列比較がサポートされていないため、望ましくない照合順序の動作があります。</span><span class="sxs-lookup"><span data-stu-id="b6800-103">The en_US_POSIX locale has an undesirable collation behavior, because it doesn't support case-insensitive string comparisons.</span></span> <span data-ttu-id="b6800-104">一部の Linux ディストリビューションでは、"C" ロケールが既定のロケールとして設定されているため、ユーザーが予期しない動作が発生していました。</span><span class="sxs-lookup"><span data-stu-id="b6800-104">Because some Linux distributions set the "C" locale as the default locale, users were experiencing unexpected behavior.</span></span> 

#### <a name="details"></a><span data-ttu-id="b6800-105">説明</span><span class="sxs-lookup"><span data-stu-id="b6800-105">Details</span></span>

<span data-ttu-id="b6800-106">.NET Core 3.0 以降では、"C" ロケール マッピングが en_US_POSIX ではなくインバリアント ロケールを使用するように変更されました。</span><span class="sxs-lookup"><span data-stu-id="b6800-106">Starting with .NET Core 3.0, the "C" locale mapping has changed to use the Invariant locale instead of en_US_POSIX.</span></span> <span data-ttu-id="b6800-107">一貫性を確保するため、インバリアントへの "C" ロケールのマッピングは、Windows にも適用されます。</span><span class="sxs-lookup"><span data-stu-id="b6800-107">The "C" locale to Invariant mapping is also applied to Windows for consistency.</span></span>

<span data-ttu-id="b6800-108">en_US_POSIX では大文字と小文字を区別しない並べ替え/検索文字列操作がサポートされないため、"C" を en_US_POSIX カルチャにマッピングすると、お客様の混乱を招いていました。</span><span class="sxs-lookup"><span data-stu-id="b6800-108">Mapping "C" to en_US_POSIX culture caused customer confusion, because en_US_POSIX doesn't support case insensitive sorting/searching string operations.</span></span> <span data-ttu-id="b6800-109">"C" ロケールは一部の Linux ディストリビューションでは既定のロケールとして使用されているため、これらのオペレーティング システムでお客様にこのような望ましくない動作が発生していました。</span><span class="sxs-lookup"><span data-stu-id="b6800-109">Because the "C" locale is used as a default locale in some of the Linux distros, customers experienced this undesired behavior on these operating systems.</span></span> 

#### <a name="version-introduced"></a><span data-ttu-id="b6800-110">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="b6800-110">Version introduced</span></span>

<span data-ttu-id="b6800-111">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="b6800-111">.NET Core 3.0</span></span>

### <a name="recommended-action"></a><span data-ttu-id="b6800-112">推奨される操作</span><span class="sxs-lookup"><span data-stu-id="b6800-112">Recommended action</span></span>

<span data-ttu-id="b6800-113">この変更を認識する以外には特にありません。</span><span class="sxs-lookup"><span data-stu-id="b6800-113">Nothing specific more than the awareness of this change.</span></span> <span data-ttu-id="b6800-114">この変更は、"C" ロケール マッピングを使用するアプリケーションにのみ影響します。</span><span class="sxs-lookup"><span data-stu-id="b6800-114">This change affects only applications that use the "C" locale mapping.</span></span>

### <a name="category"></a><span data-ttu-id="b6800-115">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="b6800-115">Category</span></span>

<span data-ttu-id="b6800-116">グローバリゼーション</span><span class="sxs-lookup"><span data-stu-id="b6800-116">Globalization</span></span> 

### <a name="affected-apis"></a><span data-ttu-id="b6800-117">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="b6800-117">Affected APIs</span></span>

<span data-ttu-id="b6800-118">すべての照合順序 API とカルチャ API は、この変更の影響を受けます。</span><span class="sxs-lookup"><span data-stu-id="b6800-118">All collation and culture APIs are affected by this change.</span></span>

<!--

-->
