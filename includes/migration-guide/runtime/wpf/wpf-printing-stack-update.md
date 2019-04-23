---
ms.openlocfilehash: 6fafb689af5d50b31b19f5d1fe7090a6c256ca45
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59804364"
---
### <a name="wpf-printing-stack-update"></a><span data-ttu-id="a92c3-101">WPF での印刷スタックの更新</span><span class="sxs-lookup"><span data-stu-id="a92c3-101">WPF Printing Stack Update</span></span>

|   |   |
|---|---|
|<span data-ttu-id="a92c3-102">説明</span><span class="sxs-lookup"><span data-stu-id="a92c3-102">Details</span></span>|<span data-ttu-id="a92c3-103"><xref:System.Printing.PrintQueue?displayProperty=name> を使う WPF の印刷 API は、非推奨になった XPS 印刷 API ではなく Windows ドキュメント印刷パッケージ API を呼び出すようになりました。</span><span class="sxs-lookup"><span data-stu-id="a92c3-103">WPF's Printing APIs using <xref:System.Printing.PrintQueue?displayProperty=name> now call Window's Print Document Package API in favor of the now deprecated XPS Print API.</span></span> <span data-ttu-id="a92c3-104">この変更はサービス性を考慮して行われたもので、ユーザーも開発者も、動作または API の使用の変化を目にすることはありません。</span><span class="sxs-lookup"><span data-stu-id="a92c3-104">The change was made with serviceability in mind; neither users nor developers should see any changes in behavior or API usage.</span></span> <span data-ttu-id="a92c3-105">Windows 10 Creators Update で実行すると、新しい印刷スタックは既定で有効になります。</span><span class="sxs-lookup"><span data-stu-id="a92c3-105">The new printing stack is enabled by default when running in Windows 10 Creators Update.</span></span> <span data-ttu-id="a92c3-106">以前のバージョンの Windows では、以前の印刷スタックが引き続き同じように動作します。</span><span class="sxs-lookup"><span data-stu-id="a92c3-106">The old printing stack will still continue to work just as before in older Windows versions.</span></span>|
|<span data-ttu-id="a92c3-107">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="a92c3-107">Suggestion</span></span>|<span data-ttu-id="a92c3-108">Windows 10 Creators Update で以前のスタックを使用するには、<code>HKEY_CURRENT_USER\Software\Microsoft\.NETFramework\Windows Presentation Foundation\Printing</code> レジストリ キーの <code>UseXpsOMPrinting</code> REG_DWORD 値を <code>1</code> に設定します。</span><span class="sxs-lookup"><span data-stu-id="a92c3-108">To use the old stack in Windows 10 Creators Update, set the <code>UseXpsOMPrinting</code> REG_DWORD value of the <code>HKEY_CURRENT_USER\Software\Microsoft\.NETFramework\Windows Presentation Foundation\Printing</code> registry key to <code>1</code>.</span></span>|
|<span data-ttu-id="a92c3-109">スコープ</span><span class="sxs-lookup"><span data-stu-id="a92c3-109">Scope</span></span>|<span data-ttu-id="a92c3-110">エッジ</span><span class="sxs-lookup"><span data-stu-id="a92c3-110">Edge</span></span>|
|<span data-ttu-id="a92c3-111">Version</span><span class="sxs-lookup"><span data-stu-id="a92c3-111">Version</span></span>|<span data-ttu-id="a92c3-112">4.7</span><span class="sxs-lookup"><span data-stu-id="a92c3-112">4.7</span></span>|
|<span data-ttu-id="a92c3-113">型</span><span class="sxs-lookup"><span data-stu-id="a92c3-113">Type</span></span>|<span data-ttu-id="a92c3-114">ランタイム</span><span class="sxs-lookup"><span data-stu-id="a92c3-114">Runtime</span></span>|
