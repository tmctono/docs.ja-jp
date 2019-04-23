---
title: TableLayoutPanel コントロール (Windows フォーム)
ms.date: 03/30/2017
helpviewer_keywords:
- TableLayoutPanel control [Windows Forms]
- layout [Windows Forms]
- controls [Windows Forms], sizing
- sizing [Windows Forms], automatic
- layout [Windows Forms], TableLayoutPanel control
- automatic sizing
ms.assetid: f55175c6-424e-4782-a86e-3f79c1550235
ms.openlocfilehash: b51d3bd8e9d8816dfae6c10fc752adb0b3cea59c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59337787"
---
# <a name="tablelayoutpanel-control-windows-forms"></a><span data-ttu-id="ef1b3-102">TableLayoutPanel コントロール (Windows フォーム)</span><span class="sxs-lookup"><span data-stu-id="ef1b3-102">TableLayoutPanel Control (Windows Forms)</span></span>
<span data-ttu-id="ef1b3-103"><xref:System.Windows.Forms.TableLayoutPanel> コントロールは、その内容をグリッド内に配置します。</span><span class="sxs-lookup"><span data-stu-id="ef1b3-103">The <xref:System.Windows.Forms.TableLayoutPanel> control arranges its contents in a grid.</span></span> <span data-ttu-id="ef1b3-104">レイアウトはデザイン時と実行時の両方で行われるため、アプリケーション環境の変更に合わせて動的に変更できます。</span><span class="sxs-lookup"><span data-stu-id="ef1b3-104">Because the layout is performed both at design time and run time, it can change dynamically as the application environment changes.</span></span> <span data-ttu-id="ef1b3-105">また、パネル内のコントロールが適切にサイズ変更されるため、親コントロールのサイズ変更や、ローカリゼーションに伴うテキスト長の変更に対応できます。</span><span class="sxs-lookup"><span data-stu-id="ef1b3-105">This gives the controls in the panel the ability to proportionally resize, so it can respond to changes such as the parent control resizing or text length changing due to localization.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ef1b3-106">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="ef1b3-106">In This Section</span></span>  
 [<span data-ttu-id="ef1b3-107">TableLayoutPanel コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="ef1b3-107">TableLayoutPanel Control Overview</span></span>](tablelayoutpanel-control-overview.md)  
 <span data-ttu-id="ef1b3-108"><xref:System.Windows.Forms.TableLayoutPanel> コントロールの全般的な概念を説明します。このコントロールを使用すると、行と列から成るレイアウトを構築できます。</span><span class="sxs-lookup"><span data-stu-id="ef1b3-108">Introduces the general concepts of the <xref:System.Windows.Forms.TableLayoutPanel> control, which allows you to create a layout with rows and columns.</span></span>  
  
 [<span data-ttu-id="ef1b3-109">TableLayoutPanel コントロールの推奨される手順</span><span class="sxs-lookup"><span data-stu-id="ef1b3-109">Best Practices for the TableLayoutPanel Control</span></span>](best-practices-for-the-tablelayoutpanel-control.md)  
 <span data-ttu-id="ef1b3-110"><xref:System.Windows.Forms.TableLayoutPanel> コントロールのレイアウト機能を最大限に活用するために役立つ手法について、概要を示します。</span><span class="sxs-lookup"><span data-stu-id="ef1b3-110">Outlines recommendations to help you get the most out of the layout features of the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>  
  
 [<span data-ttu-id="ef1b3-111">TableLayoutPanel コントロールにおける AutoSize 動作</span><span class="sxs-lookup"><span data-stu-id="ef1b3-111">AutoSize Behavior in the TableLayoutPanel Control</span></span>](autosize-behavior-in-the-tablelayoutpanel-control.md)  
 <span data-ttu-id="ef1b3-112"><xref:System.Windows.Forms.TableLayoutPanel> コントロールが自動サイズ変更の動作をどのようにサポートするかを説明します。</span><span class="sxs-lookup"><span data-stu-id="ef1b3-112">Explains the ways in which the <xref:System.Windows.Forms.TableLayoutPanel> control supports automatic sizing behavior.</span></span>  
  
 [<span data-ttu-id="ef1b3-113">方法: 固定およびドッキング TableLayoutPanel コントロールで子コントロール</span><span class="sxs-lookup"><span data-stu-id="ef1b3-113">How to: Anchor and Dock Child Controls in a TableLayoutPanel Control</span></span>](how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)  
 <span data-ttu-id="ef1b3-114"><xref:System.Windows.Forms.TableLayoutPanel> コントロールの子コントロールを固定およびドッキングする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="ef1b3-114">Shows how to anchor and dock child controls in a <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>  
  
 [<span data-ttu-id="ef1b3-115">方法: ローカリゼーションに対応する Windows フォーム レイアウトをデザインします。</span><span class="sxs-lookup"><span data-stu-id="ef1b3-115">How to: Design a Windows Forms Layout that Responds Well to Localization</span></span>](how-to-design-a-windows-forms-layout-that-responds-well-to-localization.md)  
 <span data-ttu-id="ef1b3-116"><xref:System.Windows.Forms.TableLayoutPanel> コントロールを使用して、ローカリゼーションに適切に対応できるフォームを作成する例を示します。</span><span class="sxs-lookup"><span data-stu-id="ef1b3-116">Demonstrates using a <xref:System.Windows.Forms.TableLayoutPanel> control to build a form that responds well to localization.</span></span>  
  
 [<span data-ttu-id="ef1b3-117">方法: データ入力用のサイズ変更可能な Windows フォームを作成します。</span><span class="sxs-lookup"><span data-stu-id="ef1b3-117">How to: Create a Resizable Windows Form for Data Entry</span></span>](how-to-create-a-resizable-windows-form-for-data-entry.md)  
 <span data-ttu-id="ef1b3-118"><xref:System.Windows.Forms.TableLayoutPanel> コントロールを使用して、サイズ変更に適切に対応できるフォームを作成する例を示します。</span><span class="sxs-lookup"><span data-stu-id="ef1b3-118">Demonstrates using a <xref:System.Windows.Forms.TableLayoutPanel> control to build a form that responds well to resizing.</span></span>  
  
1. [<span data-ttu-id="ef1b3-119">方法: 配置して、コントロールを TableLayoutPanel コントロールで伸縮</span><span class="sxs-lookup"><span data-stu-id="ef1b3-119">How to: Align and Stretch a Control in a TableLayoutPanel Control</span></span>](how-to-align-and-stretch-a-control-in-a-tablelayoutpanel-control.md)  
  
2. [<span data-ttu-id="ef1b3-120">方法: TableLayoutPanel コントロールの行と列にまたがる</span><span class="sxs-lookup"><span data-stu-id="ef1b3-120">How to: Span Rows and Columns in a TableLayoutPanel Control</span></span>](how-to-span-rows-and-columns-in-a-tablelayoutpanel-control.md)  
  
3. [<span data-ttu-id="ef1b3-121">方法: TableLayoutPanel コントロールの列と行を編集します。</span><span class="sxs-lookup"><span data-stu-id="ef1b3-121">How to: Edit Columns and Rows in a TableLayoutPanel Control</span></span>](how-to-edit-columns-and-rows-in-a-tablelayoutpanel-control.md)  
  
4. [<span data-ttu-id="ef1b3-122">チュートリアル: TableLayoutPanel を使用して Windows フォーム コントロールの配置</span><span class="sxs-lookup"><span data-stu-id="ef1b3-122">Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel</span></span>](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)  
  
## <a name="reference"></a><span data-ttu-id="ef1b3-123">参照</span><span class="sxs-lookup"><span data-stu-id="ef1b3-123">Reference</span></span>  
 <xref:System.Windows.Forms.TableLayoutPanel>  
 <span data-ttu-id="ef1b3-124"><xref:System.Windows.Forms.TableLayoutPanel> コントロールのリファレンス ドキュメントを提供します。</span><span class="sxs-lookup"><span data-stu-id="ef1b3-124">Provides reference documentation for the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>  
  
 <xref:System.Windows.Forms.TableLayoutSettings>  
 <span data-ttu-id="ef1b3-125"><xref:System.Windows.Forms.TableLayoutSettings> 型のリファレンス ドキュメントを提供します。</span><span class="sxs-lookup"><span data-stu-id="ef1b3-125">Provides reference documentation for the <xref:System.Windows.Forms.TableLayoutSettings> type.</span></span>  
  
 <xref:System.Windows.Forms.FlowLayoutPanel>  
 <span data-ttu-id="ef1b3-126"><xref:System.Windows.Forms.FlowLayoutPanel> コントロールのリファレンス ドキュメントを提供します。</span><span class="sxs-lookup"><span data-stu-id="ef1b3-126">Provides reference documentation for the <xref:System.Windows.Forms.FlowLayoutPanel> control.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="ef1b3-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="ef1b3-127">Related Sections</span></span>  
 [<span data-ttu-id="ef1b3-128">ローカリゼーション</span><span class="sxs-lookup"><span data-stu-id="ef1b3-128">Localization</span></span>](../../../standard/globalization-localization/localization.md)  
 <span data-ttu-id="ef1b3-129">ローカリゼーションに関連するトピックの概要を示します。</span><span class="sxs-lookup"><span data-stu-id="ef1b3-129">Provides an overview of topics relating to localization.</span></span>  
  
 <span data-ttu-id="ef1b3-130">参照してください[Localizing Applications](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/z68135h5(v=vs.120))します。</span><span class="sxs-lookup"><span data-stu-id="ef1b3-130">Also see [Localizing Applications](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/z68135h5(v=vs.120)).</span></span>
