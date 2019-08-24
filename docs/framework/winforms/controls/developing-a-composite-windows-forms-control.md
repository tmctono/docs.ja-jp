---
title: 複合 Windows フォーム コントロールの開発
ms.date: 03/30/2017
helpviewer_keywords:
- custom controls [Windows Forms], composite controls
- composite controls [Windows Forms]
- composite controls [Windows Forms], Windows Forms
- controls [Windows Forms], composite
ms.assetid: d086f2a3-baa3-4e09-b40c-a5bb3cfc51a6
ms.openlocfilehash: 9ccbf3de3f5c65b99a06c29ffce4c96896d11fae
ms.sourcegitcommit: 121ab70c1ebedba41d276e436dd2b1502748a49f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/24/2019
ms.locfileid: "70015955"
---
# <a name="develop-a-composite-windows-forms-control"></a><span data-ttu-id="a7971-102">複合 Windows フォームコントロールの開発</span><span class="sxs-lookup"><span data-stu-id="a7971-102">Develop a composite Windows Forms control</span></span>

<span data-ttu-id="a7971-103">異なる複数の Windows フォーム コントロールを組み合わせることによって、複合 Windows フォーム コントロールを開発できます。</span><span class="sxs-lookup"><span data-stu-id="a7971-103">You can develop a composite Windows Forms control by combining other Windows Forms controls.</span></span> <span data-ttu-id="a7971-104">から<xref:System.Web.UI.UserControl>派生する複合コントロールは、ユーザーコントロールと呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="a7971-104">Composite controls that derive from <xref:System.Web.UI.UserControl> are called user controls.</span></span> <span data-ttu-id="a7971-105">基底クラス <xref:System.Windows.Forms.UserControl> は、子コントロールに対してキーボード ルーティングを提供し、子コントロールがフォーカスを受け取れるようにします。</span><span class="sxs-lookup"><span data-stu-id="a7971-105">The base class, <xref:System.Windows.Forms.UserControl>, provides keyboard routing for the child controls, thus ensuring that child controls can receive focus.</span></span> <span data-ttu-id="a7971-106">ユーザーコントロールの例については、「 <xref:System.Windows.Forms.UserControl> [方法:Windows フォームコントロール](how-to-apply-attributes-in-windows-forms-controls.md)に属性を適用します。</span><span class="sxs-lookup"><span data-stu-id="a7971-106">For an example of a user control, see the <xref:System.Windows.Forms.UserControl> sample in [How to: Apply Attributes in Windows Forms Controls](how-to-apply-attributes-in-windows-forms-controls.md).</span></span>

<span data-ttu-id="a7971-107">Visual Studio の Windows フォームデザイナーには、ユーザーコントロールを作成するための豊富なデザイン時サポートが用意されています。</span><span class="sxs-lookup"><span data-stu-id="a7971-107">The Windows Forms designer in Visual Studio provides rich design-time support for authoring user controls.</span></span>

- <span data-ttu-id="a7971-108">[方法: [ツールボックスアイテムの選択] ダイアログボックスにコントロールを表示する](how-to-display-a-control-in-the-choose-toolbox-items-dialog-box.md)</span><span class="sxs-lookup"><span data-stu-id="a7971-108">[How to: Display a Control in the Choose Toolbox Items Dialog Box](how-to-display-a-control-in-the-choose-toolbox-items-dialog-box.md)</span></span>

- [<span data-ttu-id="a7971-109">チュートリアル: DesignerSerializationVisibilityAttribute を使用した標準型のコレクションのシリアル化</span><span class="sxs-lookup"><span data-stu-id="a7971-109">Walkthrough: Serializing Collections of Standard Types with the DesignerSerializationVisibilityAttribute</span></span>](serializing-collections-designerserializationvisibilityattribute.md)

- [<span data-ttu-id="a7971-110">チュートリアル: ビジュアルを使用した Windows フォームコントロールからの継承C#</span><span class="sxs-lookup"><span data-stu-id="a7971-110">Walkthrough: Inheriting from a Windows Forms Control with Visual C#</span></span>](walkthrough-inheriting-from-a-windows-forms-control-with-visual-csharp.md)

- [<span data-ttu-id="a7971-111">方法: コントロールのツールボックスビットマップを指定する</span><span class="sxs-lookup"><span data-stu-id="a7971-111">How to: Provide a Toolbox Bitmap for a Control</span></span>](how-to-provide-a-toolbox-bitmap-for-a-control.md)

- [<span data-ttu-id="a7971-112">方法: 既存の Windows フォームコントロールから継承する</span><span class="sxs-lookup"><span data-stu-id="a7971-112">How to: Inherit from Existing Windows Forms Controls</span></span>](how-to-inherit-from-existing-windows-forms-controls.md)

- [<span data-ttu-id="a7971-113">チュートリアル: カスタム Windows フォーム コントロールのデザイン時のデバッグ</span><span class="sxs-lookup"><span data-stu-id="a7971-113">Walkthrough: Debugging Custom Windows Forms Controls at Design Time</span></span>](walkthrough-debugging-custom-windows-forms-controls-at-design-time.md)

- [<span data-ttu-id="a7971-114">方法: コントロールクラスから継承する</span><span class="sxs-lookup"><span data-stu-id="a7971-114">How to: Inherit from the Control Class</span></span>](how-to-inherit-from-the-control-class.md)

- [<span data-ttu-id="a7971-115">方法: UserControl の実行時の動作をテストする</span><span class="sxs-lookup"><span data-stu-id="a7971-115">How to: Test the Run-Time Behavior of a UserControl</span></span>](how-to-test-the-run-time-behavior-of-a-usercontrol.md)

- [<span data-ttu-id="a7971-116">方法: デザイン時にコントロールをフォームの端に揃える</span><span class="sxs-lookup"><span data-stu-id="a7971-116">How to: Align a Control to the Edges of Forms at Design Time</span></span>](how-to-align-a-control-to-the-edges-of-forms-at-design-time.md)

- [<span data-ttu-id="a7971-117">方法: UserControl クラスを継承する</span><span class="sxs-lookup"><span data-stu-id="a7971-117">How to: Inherit from the UserControl Class</span></span>](how-to-inherit-from-the-usercontrol-class.md)

- [<span data-ttu-id="a7971-118">方法: Windows フォームの作成者コントロール</span><span class="sxs-lookup"><span data-stu-id="a7971-118">How to: Author Controls for Windows Forms</span></span>](how-to-author-controls-for-windows-forms.md)

- [<span data-ttu-id="a7971-119">方法: 複合コントロールの作成</span><span class="sxs-lookup"><span data-stu-id="a7971-119">How to: Author Composite Controls</span></span>](how-to-author-composite-controls.md)

- [<span data-ttu-id="a7971-120">チュートリアル: ビジュアルを使用した複合コントロールの作成C#</span><span class="sxs-lookup"><span data-stu-id="a7971-120">Walkthrough: Authoring a Composite Control with Visual C#</span></span>](walkthrough-authoring-a-composite-control-with-visual-csharp.md)

- [<span data-ttu-id="a7971-121">チュートリアル: Visual Studio のデザイン時機能を利用する Windows フォームコントロールの作成</span><span class="sxs-lookup"><span data-stu-id="a7971-121">Walkthrough: Creating a Windows Forms Control That Takes Advantage of Visual Studio Design-Time Features</span></span>](creating-a-wf-control-design-time-features.md)

- <span data-ttu-id="a7971-122">[方法: デザイン時機能を利用する Windows フォームコントロールを作成する](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/307hck25(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="a7971-122">[How to: Create a Windows Forms Control That Takes Advantage of Design-Time Features](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/307hck25(v=vs.120))</span></span>

## <a name="see-also"></a><span data-ttu-id="a7971-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="a7971-123">See also</span></span>

- [<span data-ttu-id="a7971-124">方法: Windows フォームコントロールでの属性の適用</span><span class="sxs-lookup"><span data-stu-id="a7971-124">How to: Apply Attributes in Windows Forms Controls</span></span>](how-to-apply-attributes-in-windows-forms-controls.md)
- [<span data-ttu-id="a7971-125">.NET Framework を使用したカスタム Windows フォーム コントロールの開発</span><span class="sxs-lookup"><span data-stu-id="a7971-125">Developing Custom Windows Forms Controls with the .NET Framework</span></span>](developing-custom-windows-forms-controls.md)
- [<span data-ttu-id="a7971-126">さまざまなカスタム コントロール</span><span class="sxs-lookup"><span data-stu-id="a7971-126">Varieties of Custom Controls</span></span>](varieties-of-custom-controls.md)
