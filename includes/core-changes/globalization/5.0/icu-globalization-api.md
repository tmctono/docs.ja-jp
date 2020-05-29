---
ms.openlocfilehash: 49041ce906ab0bb8b9482b79c44302465c4ca788
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2020
ms.locfileid: "83702316"
---
### <a name="globalization-apis-use-icu-libraries-on-windows"></a><span data-ttu-id="6ee31-101">グローバリゼーション API では Windows 上の ICU ライブラリが使用される</span><span class="sxs-lookup"><span data-stu-id="6ee31-101">Globalization APIs use ICU libraries on Windows</span></span>

<span data-ttu-id="6ee31-102">.NET 5.0 以降のバージョンでは、Windows 10 May 2019 Update 以降で実行されると、グローバリゼーション機能用に [International Components for Unicode (ICU)](http://site.icu-project.org/home) ライブラリが使用されます。</span><span class="sxs-lookup"><span data-stu-id="6ee31-102">.NET 5.0 and later versions use [International Components for Unicode (ICU)](http://site.icu-project.org/home) libraries for globalization functionality when running on Windows 10 May 2019 Update or later.</span></span>

#### <a name="change-description"></a><span data-ttu-id="6ee31-103">変更の説明</span><span class="sxs-lookup"><span data-stu-id="6ee31-103">Change description</span></span>

<span data-ttu-id="6ee31-104">それより前の .NET ライブラリでは、グローバリゼーション機能用に [National Language Support (NLS)](/windows/win32/intl/national-language-support) API が使用されていました。</span><span class="sxs-lookup"><span data-stu-id="6ee31-104">Previously, .NET libraries used [National Language Support (NLS)](/windows/win32/intl/national-language-support) APIs for globalization functionality.</span></span> <span data-ttu-id="6ee31-105">たとえば、日付と時刻の形式のパターンなどのカルチャ データの取得、文字列の比較、適切なカルチャでの文字列の大文字と小文字の使い分けの実行には、NLS 関数が使用されていました。</span><span class="sxs-lookup"><span data-stu-id="6ee31-105">For example, NLS functions were used to get culture data, such as date and time format patterns, compare strings, and perform string casing in the appropriate culture.</span></span>

<span data-ttu-id="6ee31-106">.NET 5.0 以降では、アプリが Windows 10 May 2019 Update 以降で実行されている場合、[ICU](http://site.icu-project.org/home) グローバリゼーション API が .NET ライブラリで使用されます。</span><span class="sxs-lookup"><span data-stu-id="6ee31-106">Starting in .NET 5.0, if an app is running on Windows 10 May 2019 Update or later, .NET libraries use [ICU](http://site.icu-project.org/home) globalization APIs.</span></span> <span data-ttu-id="6ee31-107">Windows 10 May 2019 Update 以降のバージョンには、ICU ネイティブ ライブラリが付属しています。</span><span class="sxs-lookup"><span data-stu-id="6ee31-107">Windows 10 May 2019 Update and later versions ship with the ICU native library.</span></span> <span data-ttu-id="6ee31-108">.NET ランタイムで ICU を読み込むことができない場合は、代わりに NLS が使用されます。</span><span class="sxs-lookup"><span data-stu-id="6ee31-108">If the .NET runtime can't load ICU, it uses NLS instead.</span></span>

<span data-ttu-id="6ee31-109">この変更は、次の 2 つの理由で導入されました。</span><span class="sxs-lookup"><span data-stu-id="6ee31-109">This change was introduced for two reasons:</span></span>

- <span data-ttu-id="6ee31-110">アプリのグローバリゼーション動作は、Linux、macOS、Windows など、プラットフォームが異なっても同じです。</span><span class="sxs-lookup"><span data-stu-id="6ee31-110">Apps have the same globalization behavior across platforms, including Linux, macOS, and Windows.</span></span>
- <span data-ttu-id="6ee31-111">アプリでは、カスタム ICU ライブラリを使用して、グローバリゼーションの動作を制御できます。</span><span class="sxs-lookup"><span data-stu-id="6ee31-111">Apps can control globalization behavior by using custom ICU libraries.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="6ee31-112">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="6ee31-112">Version introduced</span></span>

<span data-ttu-id="6ee31-113">.NET 5.0 Preview 4</span><span class="sxs-lookup"><span data-stu-id="6ee31-113">.NET 5.0 Preview 4</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="6ee31-114">推奨アクション</span><span class="sxs-lookup"><span data-stu-id="6ee31-114">Recommended action</span></span>

<span data-ttu-id="6ee31-115">開発者側では、何も行う必要はありません。</span><span class="sxs-lookup"><span data-stu-id="6ee31-115">No action is required on the part of the developer.</span></span> <span data-ttu-id="6ee31-116">ただし、NLS グローバリゼーション API を引き続き使いたい場合は、[ランタイム スイッチ](../../../../docs/core/run-time-config/globalization.md#nls)を設定して、その動作に戻すことができます。</span><span class="sxs-lookup"><span data-stu-id="6ee31-116">However, if you wish to continue using NLS globalization APIs, you can set a [run-time switch](../../../../docs/core/run-time-config/globalization.md#nls) to revert to that behavior.</span></span>

#### <a name="category"></a><span data-ttu-id="6ee31-117">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="6ee31-117">Category</span></span>

<span data-ttu-id="6ee31-118">グローバリゼーション</span><span class="sxs-lookup"><span data-stu-id="6ee31-118">Globalization</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="6ee31-119">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="6ee31-119">Affected APIs</span></span>

- <xref:System.Span%601?displayProperty=fullName>
- <xref:System.String?displayProperty=fullName>
- <span data-ttu-id="6ee31-120"><xref:System.Globalization?displayProperty=fullName> 名前空間のほとんどの型</span><span class="sxs-lookup"><span data-stu-id="6ee31-120">Most types in the <xref:System.Globalization?displayProperty=fullName> namespace</span></span>

<!--

#### Affected APIs

- `T:System.Span%601`
- `T:System.String`
- `N:System.Globalization`

-->
