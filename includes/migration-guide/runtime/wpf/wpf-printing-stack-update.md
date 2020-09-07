---
ms.openlocfilehash: e42bce91afab68e509cb35a8992fa3ca2f096872
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496725"
---
### <a name="wpf-printing-stack-update"></a><span data-ttu-id="055bd-101">WPF での印刷スタックの更新</span><span class="sxs-lookup"><span data-stu-id="055bd-101">WPF Printing Stack Update</span></span>

#### <a name="details"></a><span data-ttu-id="055bd-102">説明</span><span class="sxs-lookup"><span data-stu-id="055bd-102">Details</span></span>

<span data-ttu-id="055bd-103"><xref:System.Printing.PrintQueue?displayProperty=fullName> を使う WPF の印刷 API は、非推奨になった XPS 印刷 API ではなく Windows ドキュメント印刷パッケージ API を呼び出すようになりました。</span><span class="sxs-lookup"><span data-stu-id="055bd-103">WPF's Printing APIs using <xref:System.Printing.PrintQueue?displayProperty=fullName> now call Window's Print Document Package API in favor of the now deprecated XPS Print API.</span></span> <span data-ttu-id="055bd-104">この変更はサービス性を考慮して行われたもので、ユーザーも開発者も、動作または API の使用の変化を目にすることはありません。</span><span class="sxs-lookup"><span data-stu-id="055bd-104">The change was made with serviceability in mind; neither users nor developers should see any changes in behavior or API usage.</span></span> <span data-ttu-id="055bd-105">Windows 10 Creators Update で実行すると、新しい印刷スタックは既定で有効になります。</span><span class="sxs-lookup"><span data-stu-id="055bd-105">The new printing stack is enabled by default when running in Windows 10 Creators Update.</span></span> <span data-ttu-id="055bd-106">以前のバージョンの Windows では、以前の印刷スタックが引き続き同じように動作します。</span><span class="sxs-lookup"><span data-stu-id="055bd-106">The old printing stack will still continue to work just as before in older Windows versions.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="055bd-107">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="055bd-107">Suggestion</span></span>

<span data-ttu-id="055bd-108">Windows 10 Creators Update で以前のスタックを使用するには、<code>HKEY_CURRENT_USER\Software\Microsoft\.NETFramework\Windows Presentation Foundation\Printing</code> レジストリ キーの <code>UseXpsOMPrinting</code> REG_DWORD 値を <code>1</code> に設定します。</span><span class="sxs-lookup"><span data-stu-id="055bd-108">To use the old stack in Windows 10 Creators Update, set the <code>UseXpsOMPrinting</code> REG_DWORD value of the <code>HKEY_CURRENT_USER\Software\Microsoft\.NETFramework\Windows Presentation Foundation\Printing</code> registry key to <code>1</code>.</span></span>

| <span data-ttu-id="055bd-109">名前</span><span class="sxs-lookup"><span data-stu-id="055bd-109">Name</span></span>    | <span data-ttu-id="055bd-110">値</span><span class="sxs-lookup"><span data-stu-id="055bd-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="055bd-111">スコープ</span><span class="sxs-lookup"><span data-stu-id="055bd-111">Scope</span></span>   |<span data-ttu-id="055bd-112">エッジ</span><span class="sxs-lookup"><span data-stu-id="055bd-112">Edge</span></span>|
|<span data-ttu-id="055bd-113">バージョン</span><span class="sxs-lookup"><span data-stu-id="055bd-113">Version</span></span>|<span data-ttu-id="055bd-114">4.7</span><span class="sxs-lookup"><span data-stu-id="055bd-114">4.7</span></span>|
|<span data-ttu-id="055bd-115">種類</span><span class="sxs-lookup"><span data-stu-id="055bd-115">Type</span></span>|<span data-ttu-id="055bd-116">ランタイム</span><span class="sxs-lookup"><span data-stu-id="055bd-116">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="055bd-117">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="055bd-117">Affected APIs</span></span>

<span data-ttu-id="055bd-118">API 分析では検出できません。</span><span class="sxs-lookup"><span data-stu-id="055bd-118">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
