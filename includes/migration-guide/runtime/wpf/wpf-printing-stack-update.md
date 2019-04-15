---
ms.openlocfilehash: 6fafb689af5d50b31b19f5d1fe7090a6c256ca45
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59236257"
---
### <a name="wpf-printing-stack-update"></a><span data-ttu-id="2df2e-101">WPF での印刷スタックの更新</span><span class="sxs-lookup"><span data-stu-id="2df2e-101">WPF Printing Stack Update</span></span>

|   |   |
|---|---|
|<span data-ttu-id="2df2e-102">説明</span><span class="sxs-lookup"><span data-stu-id="2df2e-102">Details</span></span>|<span data-ttu-id="2df2e-103"><xref:System.Printing.PrintQueue?displayProperty=name> を使う WPF の印刷 API は、非推奨になった XPS 印刷 API ではなく Windows ドキュメント印刷パッケージ API を呼び出すようになりました。</span><span class="sxs-lookup"><span data-stu-id="2df2e-103">WPF's Printing APIs using <xref:System.Printing.PrintQueue?displayProperty=name> now call Window's Print Document Package API in favor of the now deprecated XPS Print API.</span></span> <span data-ttu-id="2df2e-104">この変更はサービス性を考慮して行われたもので、ユーザーも開発者も、動作または API の使用の変化を目にすることはありません。</span><span class="sxs-lookup"><span data-stu-id="2df2e-104">The change was made with serviceability in mind; neither users nor developers should see any changes in behavior or API usage.</span></span> <span data-ttu-id="2df2e-105">Windows 10 Creators Update で実行すると、新しい印刷スタックは既定で有効になります。</span><span class="sxs-lookup"><span data-stu-id="2df2e-105">The new printing stack is enabled by default when running in Windows 10 Creators Update.</span></span> <span data-ttu-id="2df2e-106">以前のバージョンの Windows では、以前の印刷スタックが引き続き同じように動作します。</span><span class="sxs-lookup"><span data-stu-id="2df2e-106">The old printing stack will still continue to work just as before in older Windows versions.</span></span>|
|<span data-ttu-id="2df2e-107">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="2df2e-107">Suggestion</span></span>|<span data-ttu-id="2df2e-108">Windows 10 Creators Update で以前のスタックを使用するには、<code>HKEY_CURRENT_USER\Software\Microsoft\.NETFramework\Windows Presentation Foundation\Printing</code> レジストリ キーの <code>UseXpsOMPrinting</code> REG_DWORD 値を <code>1</code> に設定します。</span><span class="sxs-lookup"><span data-stu-id="2df2e-108">To use the old stack in Windows 10 Creators Update, set the <code>UseXpsOMPrinting</code> REG_DWORD value of the <code>HKEY_CURRENT_USER\Software\Microsoft\.NETFramework\Windows Presentation Foundation\Printing</code> registry key to <code>1</code>.</span></span>|
|<span data-ttu-id="2df2e-109">スコープ</span><span class="sxs-lookup"><span data-stu-id="2df2e-109">Scope</span></span>|<span data-ttu-id="2df2e-110">エッジ</span><span class="sxs-lookup"><span data-stu-id="2df2e-110">Edge</span></span>|
|<span data-ttu-id="2df2e-111">Version</span><span class="sxs-lookup"><span data-stu-id="2df2e-111">Version</span></span>|<span data-ttu-id="2df2e-112">4.7</span><span class="sxs-lookup"><span data-stu-id="2df2e-112">4.7</span></span>|
|<span data-ttu-id="2df2e-113">型</span><span class="sxs-lookup"><span data-stu-id="2df2e-113">Type</span></span>|<span data-ttu-id="2df2e-114">ランタイム</span><span class="sxs-lookup"><span data-stu-id="2df2e-114">Runtime</span></span>|
