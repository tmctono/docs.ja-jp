---
ms.openlocfilehash: d7cf32eb369e2607ee540d7188cc680b9506c261
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/11/2019
ms.locfileid: "67856926"
---
### <a name="keytips-behavior-improved-in-wpf"></a><span data-ttu-id="d63db-101">WPF での KeyTip の動作が改良された</span><span class="sxs-lookup"><span data-stu-id="d63db-101">Keytips behavior improved in WPF</span></span>

|   |   |
|---|---|
|<span data-ttu-id="d63db-102">説明</span><span class="sxs-lookup"><span data-stu-id="d63db-102">Details</span></span>|<span data-ttu-id="d63db-103">KeyTip の動作が、Microsoft Word やエクスプローラーでの動作と同等に変更されています。</span><span class="sxs-lookup"><span data-stu-id="d63db-103">Keytips behavior has been modified to bring parity with behavior on Microsoft Word and Windows Explorer.</span></span> <span data-ttu-id="d63db-104"><xref:System.Windows.Input.KeyEventArgs.SystemKey> (具体的には <xref:System.Windows.Input.Key> または <xref:System.Windows.Input.Key.F11>) が押された場合に KeyTip の状態が有効かどうかを調べることによって、WPF は KeyTip キーを適切に処理します。</span><span class="sxs-lookup"><span data-stu-id="d63db-104">By checking whether keytip state is enabled or not in the case of a <xref:System.Windows.Input.KeyEventArgs.SystemKey> (in particular, <xref:System.Windows.Input.Key> or <xref:System.Windows.Input.Key.F11>) being pressed, WPF handles keytip keys appropriately.</span></span> <span data-ttu-id="d63db-105">メニューがマウスによって開かれている場合でも、KeyTip はメニューを閉じるようになっています。</span><span class="sxs-lookup"><span data-stu-id="d63db-105">Keytips now dismiss a menu even when it is opened by mouse.</span></span>|
|<span data-ttu-id="d63db-106">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="d63db-106">Suggestion</span></span>|<span data-ttu-id="d63db-107">N/A</span><span class="sxs-lookup"><span data-stu-id="d63db-107">N/A</span></span>|
|<span data-ttu-id="d63db-108">スコープ</span><span class="sxs-lookup"><span data-stu-id="d63db-108">Scope</span></span>|<span data-ttu-id="d63db-109">エッジ</span><span class="sxs-lookup"><span data-stu-id="d63db-109">Edge</span></span>|
|<span data-ttu-id="d63db-110">Version</span><span class="sxs-lookup"><span data-stu-id="d63db-110">Version</span></span>|<span data-ttu-id="d63db-111">4.7.2</span><span class="sxs-lookup"><span data-stu-id="d63db-111">4.7.2</span></span>|
|<span data-ttu-id="d63db-112">型</span><span class="sxs-lookup"><span data-stu-id="d63db-112">Type</span></span>|<span data-ttu-id="d63db-113">ランタイム</span><span class="sxs-lookup"><span data-stu-id="d63db-113">Runtime</span></span>|

