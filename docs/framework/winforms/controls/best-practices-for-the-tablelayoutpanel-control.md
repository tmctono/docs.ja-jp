---
title: TableLayoutPanel コントロールの推奨される手順
ms.date: 03/30/2017
helpviewer_keywords:
- layout [Windows Forms]
- TableLayoutPanel control [Windows Forms], best practices
- forms [Windows Forms], best practices
- AutoSize property [Windows Forms], tableLayoutPanel control
- controls [Windows Forms], sizing
- TableLayoutPanel control [Windows Forms], AutoSize behavior
- layout [Windows Forms], AutoSize
- layout [Windows Forms], best practices
- best practices [Windows Forms], tableLayoutPanel control
- sizing [Windows Forms], automatic
- automatic sizing
ms.assetid: b6706efb-d7a4-45ec-8cf4-08fa993e3afb
ms.openlocfilehash: e46d0fe6913bec61bd56199b7cb56a9b24d15bd0
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65211357"
---
# <a name="best-practices-for-the-tablelayoutpanel-control"></a><span data-ttu-id="dae39-102">TableLayoutPanel コントロールの推奨される手順</span><span class="sxs-lookup"><span data-stu-id="dae39-102">Best Practices for the TableLayoutPanel Control</span></span>
<span data-ttu-id="dae39-103"><xref:System.Windows.Forms.TableLayoutPanel>コントロールは、Windows フォームで使用する前に慎重に考慮すべき強力なレイアウト機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="dae39-103">The <xref:System.Windows.Forms.TableLayoutPanel> control provides powerful layout features that you should consider carefully before using on your Windows Forms.</span></span>

## <a name="recommendations"></a><span data-ttu-id="dae39-104">推奨事項</span><span class="sxs-lookup"><span data-stu-id="dae39-104">Recommendations</span></span>
 <span data-ttu-id="dae39-105">次の推奨事項では、使用するのに役立つ、<xref:System.Windows.Forms.TableLayoutPanel>最大限に活用するコントロール。</span><span class="sxs-lookup"><span data-stu-id="dae39-105">The following recommendations will help you use the <xref:System.Windows.Forms.TableLayoutPanel> control to its best advantage.</span></span>

### <a name="targeted-use"></a><span data-ttu-id="dae39-106">対象の使用</span><span class="sxs-lookup"><span data-stu-id="dae39-106">Targeted Use</span></span>
 <span data-ttu-id="dae39-107">使用して、<xref:System.Windows.Forms.TableLayoutPanel>慎重に制御します。</span><span class="sxs-lookup"><span data-stu-id="dae39-107">Use the <xref:System.Windows.Forms.TableLayoutPanel> control sparingly.</span></span> <span data-ttu-id="dae39-108">サイズ変更可能なレイアウトを必要とするすべての状況で使用する必要がありますできません。</span><span class="sxs-lookup"><span data-stu-id="dae39-108">You should not use it in all situations that require a resizable layout.</span></span> <span data-ttu-id="dae39-109">次の一覧の使用を最大限に活用できるレイアウトの説明、<xref:System.Windows.Forms.TableLayoutPanel>コントロール。</span><span class="sxs-lookup"><span data-stu-id="dae39-109">The following list describes layouts that benefit most from the use of the <xref:System.Windows.Forms.TableLayoutPanel> control:</span></span>

- <span data-ttu-id="dae39-110">レイアウトでは、相互に比例してサイズが変更されるフォームの複数の部分があります。</span><span class="sxs-lookup"><span data-stu-id="dae39-110">Layouts in which there are multiple parts of the form that resize proportionally to each other.</span></span>

- <span data-ttu-id="dae39-111">変更または追加または削除されるユーザーにカスタマイズ可能なフィールドがデータ エントリ フォームなどの実行時に動的に生成されるレイアウトは、基本設定に基づいています。</span><span class="sxs-lookup"><span data-stu-id="dae39-111">Layouts that will be modified or generated dynamically at run time, such as data entry forms that have user-customizable fields added or subtracted based on preferences.</span></span>

- <span data-ttu-id="dae39-112">全体の固定サイズのままにレイアウトします。</span><span class="sxs-lookup"><span data-stu-id="dae39-112">Layouts that should remain at an overall fixed size.</span></span> <span data-ttu-id="dae39-113">たとえば、ダイアログ ボックスが 800 x 600 未満にしておく必要がありますが、ローカライズされた文字列をサポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="dae39-113">For example, you may have a dialog box that should remain smaller than 800 x 600, but you need to support localized strings.</span></span>

 <span data-ttu-id="dae39-114">次に示しますを大幅に利用しないレイアウト、<xref:System.Windows.Forms.TableLayoutPanel>コントロール。</span><span class="sxs-lookup"><span data-stu-id="dae39-114">The following list describes layouts that do not benefit greatly from using the <xref:System.Windows.Forms.TableLayoutPanel> control:</span></span>

- <span data-ttu-id="dae39-115">1 つの列のラベルとテキスト入力領域の 1 つの列のエントリのフォームが単純なデータ。</span><span class="sxs-lookup"><span data-stu-id="dae39-115">Simple data entry forms with a single column of labels and a single column of text-entry areas.</span></span>

- <span data-ttu-id="dae39-116">1 つの大きなフォームには、サイズ変更が発生したときに使用可能なすべての領域の塗りつぶし領域が表示されます。</span><span class="sxs-lookup"><span data-stu-id="dae39-116">Forms with a single large display area that should fill all the available space when a resize occurs.</span></span> <span data-ttu-id="dae39-117">この例は、1 つを表示するフォーム<xref:System.Windows.Forms.PropertyGrid>コントロール。</span><span class="sxs-lookup"><span data-stu-id="dae39-117">An example of this is a form that displays a single <xref:System.Windows.Forms.PropertyGrid> control.</span></span> <span data-ttu-id="dae39-118">この場合、アンカー、ために使用、フォームのサイズが変更されたときに他に何も展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dae39-118">In this case, use anchoring, because nothing else should expand when the form is resized.</span></span>

 <span data-ttu-id="dae39-119">どのコントロールでは、必要がありますは慎重に選択、<xref:System.Windows.Forms.TableLayoutPanel>コントロール。</span><span class="sxs-lookup"><span data-stu-id="dae39-119">Choose carefully which controls need to be in a <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span> <span data-ttu-id="dae39-120">増加 30% がアンカーを使用して、文字列がある場合は、使用を検討して、<xref:System.Windows.Forms.Control.Anchor%2A>プロパティのみです。</span><span class="sxs-lookup"><span data-stu-id="dae39-120">If you have room for your text to grow by 30% using anchoring, consider using the <xref:System.Windows.Forms.Control.Anchor%2A> property only.</span></span> <span data-ttu-id="dae39-121">場合は、レイアウトが必要な容量を見積もるを使用して<xref:System.Windows.Forms.Control.Dock%2A>と<xref:System.Windows.Forms.Control.Anchor%2A>が残りの領域の詳細を見積もるよりも簡単と<xref:System.Windows.Forms.Control.AutoSize%2A>動作します。</span><span class="sxs-lookup"><span data-stu-id="dae39-121">If you can estimate the space required by your layout, use of <xref:System.Windows.Forms.Control.Dock%2A> and <xref:System.Windows.Forms.Control.Anchor%2A> is easier than estimating the details of remaining space and <xref:System.Windows.Forms.Control.AutoSize%2A> behavior.</span></span>

 <span data-ttu-id="dae39-122">一般を使用してレイアウトを設計するときに、<xref:System.Windows.Forms.TableLayoutPanel>コントロールを設計をできるだけシンプルに保ちます。</span><span class="sxs-lookup"><span data-stu-id="dae39-122">In general, when designing your layout with the <xref:System.Windows.Forms.TableLayoutPanel> control, keep the design as simple as possible.</span></span>

### <a name="use-the-document-outline-window"></a><span data-ttu-id="dae39-123">ドキュメント アウトライン ウィンドウを使用します。</span><span class="sxs-lookup"><span data-stu-id="dae39-123">Use the Document Outline Window</span></span>
 <span data-ttu-id="dae39-124">ドキュメント アウトライン ウィンドウでは、ツリー ビュー、レイアウト、コントロールの z オーダーと親子のリレーションシップの操作に使用することができます。</span><span class="sxs-lookup"><span data-stu-id="dae39-124">The Document Outline window gives you a tree view of your layout, which you can use to manipulate the z-order and parent-child relationships of your controls.</span></span> <span data-ttu-id="dae39-125">**ビュー メニュー**を選択します**その他の Windows**を選択し、**ドキュメント アウトライン**します。</span><span class="sxs-lookup"><span data-stu-id="dae39-125">From the **View menu**, select **Other Windows**, then select **Document Outline**.</span></span>

### <a name="avoid-nesting"></a><span data-ttu-id="dae39-126">入れ子を回避します。</span><span class="sxs-lookup"><span data-stu-id="dae39-126">Avoid Nesting</span></span>
 <span data-ttu-id="dae39-127">その他の入れ子を避ける<xref:System.Windows.Forms.TableLayoutPanel>内で制御を<xref:System.Windows.Forms.TableLayoutPanel>コントロール。</span><span class="sxs-lookup"><span data-stu-id="dae39-127">Avoid nesting other <xref:System.Windows.Forms.TableLayoutPanel> controls within a <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span> <span data-ttu-id="dae39-128">入れ子になったレイアウトのデバッグは困難なことができます。</span><span class="sxs-lookup"><span data-stu-id="dae39-128">Debugging nested layouts can be difficult.</span></span>

### <a name="avoid-visual-inheritance"></a><span data-ttu-id="dae39-129">ビジュアル継承を回避します。</span><span class="sxs-lookup"><span data-stu-id="dae39-129">Avoid Visual Inheritance</span></span>
 <span data-ttu-id="dae39-130"><xref:System.Windows.Forms.TableLayoutPanel>コントロールが Visual Studio での Windows フォーム デザイナーでビジュアルの継承をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="dae39-130">The <xref:System.Windows.Forms.TableLayoutPanel> control does not support visual inheritance in the Windows Forms Designer in Visual Studio.</span></span> <span data-ttu-id="dae39-131">A<xref:System.Windows.Forms.TableLayoutPanel>デザイン時に、「ロック」として、派生クラスでのコントロールが表示されます。</span><span class="sxs-lookup"><span data-stu-id="dae39-131">A <xref:System.Windows.Forms.TableLayoutPanel> control in a derived class appears as "locked" at design time.</span></span>

## <a name="see-also"></a><span data-ttu-id="dae39-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="dae39-132">See also</span></span>

- <xref:System.Windows.Forms.TableLayoutPanel>
- <xref:System.Windows.Forms.FlowLayoutPanel>
