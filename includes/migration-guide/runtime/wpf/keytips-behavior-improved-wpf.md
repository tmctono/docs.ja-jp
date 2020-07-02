---
ms.openlocfilehash: 9659068304eb208fd6a0a753273453bc669fbc56
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621272"
---
### <a name="keytips-behavior-improved-in-wpf"></a><span data-ttu-id="cedb2-101">WPF での KeyTip の動作が改良された</span><span class="sxs-lookup"><span data-stu-id="cedb2-101">Keytips behavior improved in WPF</span></span>

#### <a name="details"></a><span data-ttu-id="cedb2-102">説明</span><span class="sxs-lookup"><span data-stu-id="cedb2-102">Details</span></span>

<span data-ttu-id="cedb2-103">KeyTip の動作が、Microsoft Word やエクスプローラーでの動作と同等に変更されています。</span><span class="sxs-lookup"><span data-stu-id="cedb2-103">Keytips behavior has been modified to bring parity with behavior on Microsoft Word and Windows Explorer.</span></span> <span data-ttu-id="cedb2-104"><xref:System.Windows.Input.KeyEventArgs.SystemKey> (具体的には <xref:System.Windows.Input.Key> または <xref:System.Windows.Input.Key.F11>) が押された場合に KeyTip の状態が有効かどうかを調べることによって、WPF は KeyTip キーを適切に処理します。</span><span class="sxs-lookup"><span data-stu-id="cedb2-104">By checking whether keytip state is enabled or not in the case of a <xref:System.Windows.Input.KeyEventArgs.SystemKey> (in particular, <xref:System.Windows.Input.Key> or <xref:System.Windows.Input.Key.F11>) being pressed, WPF handles keytip keys appropriately.</span></span> <span data-ttu-id="cedb2-105">メニューがマウスによって開かれている場合でも、KeyTip はメニューを閉じるようになっています。</span><span class="sxs-lookup"><span data-stu-id="cedb2-105">Keytips now dismiss a menu even when it is opened by mouse.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="cedb2-106">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="cedb2-106">Suggestion</span></span>

<span data-ttu-id="cedb2-107">N/A</span><span class="sxs-lookup"><span data-stu-id="cedb2-107">N/A</span></span>

| <span data-ttu-id="cedb2-108">名前</span><span class="sxs-lookup"><span data-stu-id="cedb2-108">Name</span></span>    | <span data-ttu-id="cedb2-109">[値]</span><span class="sxs-lookup"><span data-stu-id="cedb2-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="cedb2-110">スコープ</span><span class="sxs-lookup"><span data-stu-id="cedb2-110">Scope</span></span>   |<span data-ttu-id="cedb2-111">エッジ</span><span class="sxs-lookup"><span data-stu-id="cedb2-111">Edge</span></span>|
|<span data-ttu-id="cedb2-112">バージョン</span><span class="sxs-lookup"><span data-stu-id="cedb2-112">Version</span></span>|<span data-ttu-id="cedb2-113">4.7.2</span><span class="sxs-lookup"><span data-stu-id="cedb2-113">4.7.2</span></span>|
|<span data-ttu-id="cedb2-114">種類</span><span class="sxs-lookup"><span data-stu-id="cedb2-114">Type</span></span>|<span data-ttu-id="cedb2-115">ランタイム</span><span class="sxs-lookup"><span data-stu-id="cedb2-115">Runtime</span></span>|
