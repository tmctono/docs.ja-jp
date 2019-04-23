---
title: 複合 Windows フォーム コントロールの開発
ms.date: 03/30/2017
helpviewer_keywords:
- custom controls [Windows Forms], composite controls
- composite controls [Windows Forms]
- composite controls [Windows Forms], Windows Forms
- controls [Windows Forms], composite
ms.assetid: d086f2a3-baa3-4e09-b40c-a5bb3cfc51a6
ms.openlocfilehash: bfbb9091d40652bdd1ae277f3a77feefbccbf080
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59196464"
---
# <a name="developing-a-composite-windows-forms-control"></a><span data-ttu-id="898e1-102">複合 Windows フォーム コントロールの開発</span><span class="sxs-lookup"><span data-stu-id="898e1-102">Developing a Composite Windows Forms Control</span></span>
<span data-ttu-id="898e1-103">異なる複数の Windows フォーム コントロールを組み合わせることによって、複合 Windows フォーム コントロールを開発できます。</span><span class="sxs-lookup"><span data-stu-id="898e1-103">You can develop a composite Windows Forms control by combining other Windows Forms controls.</span></span> <span data-ttu-id="898e1-104">派生した複合コントロール<xref:System.Web.UI.UserControl>ユーザー コントロールと呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="898e1-104">Composite controls that derive from <xref:System.Web.UI.UserControl> are called user controls.</span></span> <span data-ttu-id="898e1-105">基底クラス <xref:System.Windows.Forms.UserControl> は、子コントロールに対してキーボード ルーティングを提供し、子コントロールがフォーカスを受け取れるようにします。</span><span class="sxs-lookup"><span data-stu-id="898e1-105">The base class, <xref:System.Windows.Forms.UserControl>, provides keyboard routing for the child controls, thus ensuring that child controls can receive focus.</span></span> <span data-ttu-id="898e1-106">ユーザー コントロールの例は、次を参照してください。、<xref:System.Windows.Forms.UserControl>サンプルは、[方法。Windows フォーム コントロールに属性を適用](how-to-apply-attributes-in-windows-forms-controls.md)します。</span><span class="sxs-lookup"><span data-stu-id="898e1-106">For an example of a user control, see the <xref:System.Windows.Forms.UserControl> sample in [How to: Apply Attributes in Windows Forms Controls](how-to-apply-attributes-in-windows-forms-controls.md).</span></span>  
  
 <span data-ttu-id="898e1-107">Visual Studio での Windows フォーム デザイナーは、ユーザー コントロールを作成するための豊富なデザイン時サポートを提供します。</span><span class="sxs-lookup"><span data-stu-id="898e1-107">The Windows Forms designer in Visual Studio provides rich design-time support for authoring user controls.</span></span>  
  
-   [<span data-ttu-id="898e1-108">方法: 内のコントロールを表示、ツールボックス項目 ダイアログ ボックスの選択</span><span class="sxs-lookup"><span data-stu-id="898e1-108">How to: Display a Control in the Choose Toolbox Items Dialog Box</span></span>](how-to-display-a-control-in-the-choose-toolbox-items-dialog-box.md)  
  
-   [<span data-ttu-id="898e1-109">チュートリアル: Designerserializationvisibilityattribute を使用、基本データ型のコレクションをシリアル化します。</span><span class="sxs-lookup"><span data-stu-id="898e1-109">Walkthrough: Serializing Collections of Standard Types with the DesignerSerializationVisibilityAttribute</span></span>](serializing-collections-designerserializationvisibilityattribute.md)  
  
-   [<span data-ttu-id="898e1-110">チュートリアル: ビジュアルを含む Windows フォーム コントロールからの継承C#</span><span class="sxs-lookup"><span data-stu-id="898e1-110">Walkthrough: Inheriting from a Windows Forms Control with Visual C#</span></span>](walkthrough-inheriting-from-a-windows-forms-control-with-visual-csharp.md)  
  
-   [<span data-ttu-id="898e1-111">方法: コントロールにツールボックス ビットマップを指定します。</span><span class="sxs-lookup"><span data-stu-id="898e1-111">How to: Provide a Toolbox Bitmap for a Control</span></span>](how-to-provide-a-toolbox-bitmap-for-a-control.md)  
  
-   [<span data-ttu-id="898e1-112">方法: 継承可能な既存の Windows フォーム コントロール</span><span class="sxs-lookup"><span data-stu-id="898e1-112">How to: Inherit from Existing Windows Forms Controls</span></span>](how-to-inherit-from-existing-windows-forms-controls.md)  
  
-   [<span data-ttu-id="898e1-113">チュートリアル: カスタム Windows フォーム コントロールのデザイン時のデバッグ</span><span class="sxs-lookup"><span data-stu-id="898e1-113">Walkthrough: Debugging Custom Windows Forms Controls at Design Time</span></span>](walkthrough-debugging-custom-windows-forms-controls-at-design-time.md)  
  
-   [<span data-ttu-id="898e1-114">方法: コントロール クラスから継承します。</span><span class="sxs-lookup"><span data-stu-id="898e1-114">How to: Inherit from the Control Class</span></span>](how-to-inherit-from-the-control-class.md)  
  
-   [<span data-ttu-id="898e1-115">方法: UserControl の実行時の動作をテストします。</span><span class="sxs-lookup"><span data-stu-id="898e1-115">How to: Test the Run-Time Behavior of a UserControl</span></span>](how-to-test-the-run-time-behavior-of-a-usercontrol.md)  
  
-   [<span data-ttu-id="898e1-116">方法: デザイン時にコントロールをフォームの端を揃える</span><span class="sxs-lookup"><span data-stu-id="898e1-116">How to: Align a Control to the Edges of Forms at Design Time</span></span>](how-to-align-a-control-to-the-edges-of-forms-at-design-time.md)  
  
-   [<span data-ttu-id="898e1-117">方法: UserControl クラスを継承します。</span><span class="sxs-lookup"><span data-stu-id="898e1-117">How to: Inherit from the UserControl Class</span></span>](how-to-inherit-from-the-usercontrol-class.md)  
  
-   [<span data-ttu-id="898e1-118">方法: Windows フォームのコントロールの作成</span><span class="sxs-lookup"><span data-stu-id="898e1-118">How to: Author Controls for Windows Forms</span></span>](how-to-author-controls-for-windows-forms.md)  
  
-   [<span data-ttu-id="898e1-119">方法: 複合コントロールを作成</span><span class="sxs-lookup"><span data-stu-id="898e1-119">How to: Author Composite Controls</span></span>](how-to-author-composite-controls.md)  
  
-   [<span data-ttu-id="898e1-120">チュートリアル: Visual Basic による複合コントロールの作成</span><span class="sxs-lookup"><span data-stu-id="898e1-120">Walkthrough: Authoring a Composite Control with Visual Basic</span></span>](walkthrough-authoring-a-composite-control-with-visual-basic.md)  
  
-   [<span data-ttu-id="898e1-121">チュートリアル: ビジュアルを含む複合コントロールの作成C#</span><span class="sxs-lookup"><span data-stu-id="898e1-121">Walkthrough: Authoring a Composite Control with Visual C#</span></span>](walkthrough-authoring-a-composite-control-with-visual-csharp.md)  
  
-   [<span data-ttu-id="898e1-122">チュートリアル: Visual Basic による Windows フォーム コントロールから継承します。</span><span class="sxs-lookup"><span data-stu-id="898e1-122">Walkthrough: Inheriting from a Windows Forms Control with Visual Basic</span></span>](walkthrough-inheriting-from-a-windows-forms-control-with-visual-basic.md)  
  
-   [<span data-ttu-id="898e1-123">チュートリアル: Visual Studio のデザイン時機能を活用した Windows フォーム コントロールの作成</span><span class="sxs-lookup"><span data-stu-id="898e1-123">Walkthrough: Creating a Windows Forms Control That Takes Advantage of Visual Studio Design-Time Features</span></span>](creating-a-wf-control-design-time-features.md)  
  
-   <span data-ttu-id="898e1-124">[方法: デザイン時機能を活用した Windows フォーム コントロールを作成します。](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/307hck25(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="898e1-124">[How to: Create a Windows Forms Control That Takes Advantage of Design-Time Features](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/307hck25(v=vs.120))</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="898e1-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="898e1-125">See also</span></span>

- [<span data-ttu-id="898e1-126">方法: Windows フォーム コントロールに属性を適用します。</span><span class="sxs-lookup"><span data-stu-id="898e1-126">How to: Apply Attributes in Windows Forms Controls</span></span>](how-to-apply-attributes-in-windows-forms-controls.md)
- [<span data-ttu-id="898e1-127">.NET Framework を使用したカスタム Windows フォーム コントロールの開発</span><span class="sxs-lookup"><span data-stu-id="898e1-127">Developing Custom Windows Forms Controls with the .NET Framework</span></span>](developing-custom-windows-forms-controls.md)
- [<span data-ttu-id="898e1-128">さまざまなカスタム コントロール</span><span class="sxs-lookup"><span data-stu-id="898e1-128">Varieties of Custom Controls</span></span>](varieties-of-custom-controls.md)
