---
title: デザイン時の Windows フォーム コントロールの開発
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms controls [Windows Forms]
- Windows Forms controls, creating
- controls [Windows Forms]
- controls [Windows Forms], creating
- user controls [Windows Forms]
- custom controls [Windows Forms]
ms.assetid: e5a8e088-7ec8-4fd9-bcb3-9078fd134829
ms.openlocfilehash: 641a6c1c99169c6836c33b3e84b2ae02aba298d2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61972238"
---
# <a name="developing-windows-forms-controls-at-design-time"></a><span data-ttu-id="dce00-102">デザイン時の Windows フォーム コントロールの開発</span><span class="sxs-lookup"><span data-stu-id="dce00-102">Developing Windows Forms Controls at Design Time</span></span>
<span data-ttu-id="dce00-103">コントロールの作成者は、.NET Framework のさまざまなコントロール作成テクノロジを利用できます。</span><span class="sxs-lookup"><span data-stu-id="dce00-103">For control authors, the .NET Framework provides a wealth of control authoring technology.</span></span> <span data-ttu-id="dce00-104">既存のコントロールを組み合わせた複合コントロールしかデザインできないといった制約はなくなりました。</span><span class="sxs-lookup"><span data-stu-id="dce00-104">Authors are no longer limited to designing composite controls that act as a collection of preexisting controls.</span></span> <span data-ttu-id="dce00-105">継承により、既存の複合コントロールや既存の Windows フォーム コントロールから、独自のコントロールを作成できます。</span><span class="sxs-lookup"><span data-stu-id="dce00-105">Through inheritance, you can create your own controls from preexisting composite controls or preexisting Windows Forms controls.</span></span> <span data-ttu-id="dce00-106">カスタム描画を実装する独自のコントロールを設計することもできます。</span><span class="sxs-lookup"><span data-stu-id="dce00-106">You can also design your own controls that implement custom painting.</span></span> <span data-ttu-id="dce00-107">これらのオプションを使うと、非常に柔軟にビジュアル インターフェイスのデザインと機能を決めることができます。</span><span class="sxs-lookup"><span data-stu-id="dce00-107">These options enable a great deal of flexibility to the design and functionality of the visual interface.</span></span> <span data-ttu-id="dce00-108">これらの機能を利用するには、オブジェクト ベースのプログラミング概念について理解しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="dce00-108">To take advantage of these features, you should be familiar with object-based programming concepts.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="dce00-109">継承、十分に理解する必要はありませんを参照する役に立つ場合があります[継承の基本 (Visual Basic)](~/docs/visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)します。</span><span class="sxs-lookup"><span data-stu-id="dce00-109">It is not necessary to have a thorough understanding of inheritance, but you may find it useful to refer to [Inheritance basics (Visual Basic)](~/docs/visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md).</span></span>  
  
 <span data-ttu-id="dce00-110">Web フォームで使うカスタム コントロールを作る場合は、「[カスタム ASP.NET サーバー コントロールの開発](https://docs.microsoft.com/previous-versions/aspnet/zt27tfhy(v=vs.100))」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="dce00-110">If you want to create custom controls to use on Web Forms, see [Developing Custom ASP.NET Server Controls](https://docs.microsoft.com/previous-versions/aspnet/zt27tfhy(v=vs.100)).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="dce00-111">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="dce00-111">In This Section</span></span>  
 [<span data-ttu-id="dce00-112">チュートリアル: Visual Basic による複合コントロールの作成</span><span class="sxs-lookup"><span data-stu-id="dce00-112">Walkthrough: Authoring a Composite Control with Visual Basic</span></span>](walkthrough-authoring-a-composite-control-with-visual-basic.md)  
 <span data-ttu-id="dce00-113">Visual Basic で簡単な複合コントロールを作る方法を示します。</span><span class="sxs-lookup"><span data-stu-id="dce00-113">Shows how to create a simple composite control in Visual Basic.</span></span>  
  
 [<span data-ttu-id="dce00-114">チュートリアル: ビジュアルを含む複合コントロールの作成C#</span><span class="sxs-lookup"><span data-stu-id="dce00-114">Walkthrough: Authoring a Composite Control with Visual C#</span></span>](walkthrough-authoring-a-composite-control-with-visual-csharp.md)  
 <span data-ttu-id="dce00-115">C# で簡単な複合コントロールを作る方法を示します。</span><span class="sxs-lookup"><span data-stu-id="dce00-115">Shows how to create a simple composite control in C#.</span></span>  
  
 [<span data-ttu-id="dce00-116">チュートリアル: Visual Basic による Windows フォーム コントロールから継承します。</span><span class="sxs-lookup"><span data-stu-id="dce00-116">Walkthrough: Inheriting from a Windows Forms Control with Visual Basic</span></span>](walkthrough-inheriting-from-a-windows-forms-control-with-visual-basic.md)  
 <span data-ttu-id="dce00-117">Visual Basic で継承を使って簡単な Windows フォーム コントロールを作る方法を示します。</span><span class="sxs-lookup"><span data-stu-id="dce00-117">Shows how to create a simple Windows Forms control using inheritance in Visual Basic.</span></span>  
  
 [<span data-ttu-id="dce00-118">チュートリアル: ビジュアルを含む Windows フォーム コントロールからの継承C#</span><span class="sxs-lookup"><span data-stu-id="dce00-118">Walkthrough: Inheriting from a Windows Forms Control with Visual C#</span></span>](walkthrough-inheriting-from-a-windows-forms-control-with-visual-csharp.md)  
 <span data-ttu-id="dce00-119">C# で継承を使って簡単な Windows フォーム コントロールを作る方法を示します。</span><span class="sxs-lookup"><span data-stu-id="dce00-119">Shows how to create a simple Windows Forms control using inheritance in C#.</span></span>  
  
 [<span data-ttu-id="dce00-120">チュートリアル: スマートを使用して一般的なタスクを実行する Windows フォーム コントロールをタグ</span><span class="sxs-lookup"><span data-stu-id="dce00-120">Walkthrough: Performing Common Tasks Using Smart Tags on Windows Forms Controls</span></span>](performing-common-tasks-using-smart-tags-on-wf-controls.md)  
 <span data-ttu-id="dce00-121">Windows フォーム コントロールでスマート タグ機能を使う方法を示します。</span><span class="sxs-lookup"><span data-stu-id="dce00-121">Shows how to use the smart tag feature on Windows Forms controls.</span></span>  
  
 [<span data-ttu-id="dce00-122">チュートリアル: Designerserializationvisibilityattribute を使用、基本データ型のコレクションをシリアル化します。</span><span class="sxs-lookup"><span data-stu-id="dce00-122">Walkthrough: Serializing Collections of Standard Types with the DesignerSerializationVisibilityAttribute</span></span>](serializing-collections-designerserializationvisibilityattribute.md)  
 <span data-ttu-id="dce00-123">使用する方法を示しています、<xref:System.ComponentModel.DesignerSerializationVisibilityAttribute.Content?displayProperty=nameWithType>コレクションをシリアル化する属性。</span><span class="sxs-lookup"><span data-stu-id="dce00-123">Shows how to use the <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute.Content?displayProperty=nameWithType> attribute to serialize a collection.</span></span>  
  
 [<span data-ttu-id="dce00-124">チュートリアル: カスタム Windows フォーム コントロールのデザイン時のデバッグ</span><span class="sxs-lookup"><span data-stu-id="dce00-124">Walkthrough: Debugging Custom Windows Forms Controls at Design Time</span></span>](walkthrough-debugging-custom-windows-forms-controls-at-design-time.md)  
 <span data-ttu-id="dce00-125">Windows フォーム コントロールのデザイン時動作をデバッグする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="dce00-125">Shows how to debug the design-time behavior of a Windows Forms control.</span></span>  
  
 [<span data-ttu-id="dce00-126">チュートリアル: Visual Studio のデザイン時機能を活用した Windows フォーム コントロールの作成</span><span class="sxs-lookup"><span data-stu-id="dce00-126">Walkthrough: Creating a Windows Forms Control That Takes Advantage of Visual Studio Design-Time Features</span></span>](creating-a-wf-control-design-time-features.md)  
 <span data-ttu-id="dce00-127">デザイン環境に複合コントロールを緊密に統合する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="dce00-127">Shows how to tightly integrate a composite control into the design environment.</span></span>  
  
 [<span data-ttu-id="dce00-128">方法: Windows フォームのコントロールの作成</span><span class="sxs-lookup"><span data-stu-id="dce00-128">How to: Author Controls for Windows Forms</span></span>](how-to-author-controls-for-windows-forms.md)  
 <span data-ttu-id="dce00-129">Windows フォーム コントロールの実装に関する考慮事項の概要を説明します。</span><span class="sxs-lookup"><span data-stu-id="dce00-129">Provides an overview of considerations for implementing a Windows Forms control.</span></span>  
  
 [<span data-ttu-id="dce00-130">方法: 複合コントロールを作成</span><span class="sxs-lookup"><span data-stu-id="dce00-130">How to: Author Composite Controls</span></span>](how-to-author-composite-controls.md)  
 <span data-ttu-id="dce00-131">複合コントロールから継承することでコントロールを作る方法を示します。</span><span class="sxs-lookup"><span data-stu-id="dce00-131">Shows how to create a control by inheriting from a composite control.</span></span>  
  
 [<span data-ttu-id="dce00-132">方法: UserControl クラスを継承します。</span><span class="sxs-lookup"><span data-stu-id="dce00-132">How to: Inherit from the UserControl Class</span></span>](how-to-inherit-from-the-usercontrol-class.md)  
 <span data-ttu-id="dce00-133">複合コントロール作成手順の概要を説明します。</span><span class="sxs-lookup"><span data-stu-id="dce00-133">Provides an overview of the procedure for creating a composite control.</span></span>  
  
 [<span data-ttu-id="dce00-134">方法: 継承可能な既存の Windows フォーム コントロール</span><span class="sxs-lookup"><span data-stu-id="dce00-134">How to: Inherit from Existing Windows Forms Controls</span></span>](how-to-inherit-from-existing-windows-forms-controls.md)  
 <span data-ttu-id="dce00-135">継承することにより拡張コントロールを作成する方法を示しています、<xref:System.Windows.Forms.Button>クラスを制御します。</span><span class="sxs-lookup"><span data-stu-id="dce00-135">Shows how to create an extended control by inheriting from the <xref:System.Windows.Forms.Button> control class.</span></span>  
  
 [<span data-ttu-id="dce00-136">方法: コントロール クラスから継承します。</span><span class="sxs-lookup"><span data-stu-id="dce00-136">How to: Inherit from the Control Class</span></span>](how-to-inherit-from-the-control-class.md)  
 <span data-ttu-id="dce00-137">拡張コントロールの作成の概要を説明します。</span><span class="sxs-lookup"><span data-stu-id="dce00-137">Provides an overview of creating an extended control.</span></span>  
  
 [<span data-ttu-id="dce00-138">方法: デザイン時にコントロールをフォームの端を揃える</span><span class="sxs-lookup"><span data-stu-id="dce00-138">How to: Align a Control to the Edges of Forms at Design Time</span></span>](how-to-align-a-control-to-the-edges-of-forms-at-design-time.md)  
 <span data-ttu-id="dce00-139">使用する方法を示しています、<xref:System.Windows.Forms.Control.Dock%2A>プロパティを合わせて、フォームの端にコントロールを配置します。</span><span class="sxs-lookup"><span data-stu-id="dce00-139">Shows how to use the <xref:System.Windows.Forms.Control.Dock%2A> property to align your control to the edge of the form it occupies.</span></span>  
  
 [<span data-ttu-id="dce00-140">方法: 内のコントロールを表示、ツールボックス項目 ダイアログ ボックスの選択</span><span class="sxs-lookup"><span data-stu-id="dce00-140">How to: Display a Control in the Choose Toolbox Items Dialog Box</span></span>](how-to-display-a-control-in-the-choose-toolbox-items-dialog-box.md)  
 <span data-ttu-id="dce00-141">**ツールボックスのカスタマイズ** ダイアログ ボックスに表示されるようにコントロールをインストールする手順を示します。</span><span class="sxs-lookup"><span data-stu-id="dce00-141">Shows the procedure for installing your control so that it appears in the **Customize Toolbox** dialog box.</span></span>  
  
 [<span data-ttu-id="dce00-142">方法: コントロールにツールボックス ビットマップを指定します。</span><span class="sxs-lookup"><span data-stu-id="dce00-142">How to: Provide a Toolbox Bitmap for a Control</span></span>](how-to-provide-a-toolbox-bitmap-for-a-control.md)  
 <span data-ttu-id="dce00-143">使用する方法を示しています、<xref:System.Drawing.ToolboxBitmapAttribute>で、カスタム コントロールの横にあるアイコンを表示する、**ツールボックス**します。</span><span class="sxs-lookup"><span data-stu-id="dce00-143">Shows how to use the <xref:System.Drawing.ToolboxBitmapAttribute> to display an icon next to your custom control in the **Toolbox**.</span></span>  
  
 [<span data-ttu-id="dce00-144">方法: UserControl の実行時の動作をテストします。</span><span class="sxs-lookup"><span data-stu-id="dce00-144">How to: Test the Run-Time Behavior of a UserControl</span></span>](how-to-test-the-run-time-behavior-of-a-usercontrol.md)  
 <span data-ttu-id="dce00-145">**UserControl テスト コンテナー**を使って複合コントロールの動作をテストする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="dce00-145">Shows how to use the **UserControl Test Container** to test the behavior of a composite control.</span></span>  
  
 [<span data-ttu-id="dce00-146">Windows フォーム デザイナーでのデザイン時エラー</span><span class="sxs-lookup"><span data-stu-id="dce00-146">Design-Time Errors in the Windows Forms Designer</span></span>](design-time-errors-in-the-windows-forms-designer.md)  
 <span data-ttu-id="dce00-147">Windows フォーム デザイナーで読み込みに失敗したときに Microsoft Visual Studio に表示されるデザイン時エラー リストの意味と使用法について説明します。</span><span class="sxs-lookup"><span data-stu-id="dce00-147">Explains the meaning and use of the Design-Time Error List that appears in Microsoft Visual Studio when the Windows Forms designer fails to load.</span></span>  
  
 [<span data-ttu-id="dce00-148">コントロールとコンポーネントの作成時のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="dce00-148">Troubleshooting Control and Component Authoring</span></span>](troubleshooting-control-and-component-authoring.md)  
 <span data-ttu-id="dce00-149">カスタム コンポーネントやコントロールを作るときに発生する可能性がある一般的な問題を診断して解決する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="dce00-149">Shows how to diagnose and fix common issues that can occur when you author a custom component or control.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="dce00-150">参照</span><span class="sxs-lookup"><span data-stu-id="dce00-150">Reference</span></span>  
 <xref:System.Windows.Forms.Control?displayProperty=nameWithType>  
 <span data-ttu-id="dce00-151">このクラスについて説明し、すべてのメンバーへのリンクの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="dce00-151">Describes this class and has links to all of its members.</span></span>  
  
 <xref:System.Windows.Forms.UserControl?displayProperty=nameWithType>  
 <span data-ttu-id="dce00-152">このクラスについて説明し、すべてのメンバーへのリンクの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="dce00-152">Describes this class and has links to all of its members.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="dce00-153">関連項目</span><span class="sxs-lookup"><span data-stu-id="dce00-153">Related Sections</span></span>  
 [<span data-ttu-id="dce00-154">.NET Framework を使用したカスタム Windows フォーム コントロールの開発</span><span class="sxs-lookup"><span data-stu-id="dce00-154">Developing Custom Windows Forms Controls with the .NET Framework</span></span>](developing-custom-windows-forms-controls.md)  
 <span data-ttu-id="dce00-155">.NET Framework で独自のカスタム コントロールを作る方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="dce00-155">Discusses how to create your own custom controls with the .NET Framework.</span></span>  
  
 [<span data-ttu-id="dce00-156">言語への非依存性、および言語非依存コンポーネント</span><span class="sxs-lookup"><span data-stu-id="dce00-156">Language Independence and Language-Independent Components</span></span>](../../../standard/language-independence-and-language-independent-components.md)  
 <span data-ttu-id="dce00-157">コンポーネントの作成と使用を簡略化するように設計されている共通言語ランタイムの概要について説明します。</span><span class="sxs-lookup"><span data-stu-id="dce00-157">Introduces the common language runtime, which is designed to simplify the creation and use of components.</span></span> <span data-ttu-id="dce00-158">この簡略化の重要な側面は、さまざまなプログラミング言語で記述されたコンポーネント間の相互運用性の拡張です。</span><span class="sxs-lookup"><span data-stu-id="dce00-158">An important aspect of this simplification is enhanced interoperability between components written using different programming languages.</span></span> <span data-ttu-id="dce00-159">共通言語仕様 (CLS) を使うと、複数のプログラミング言語で動作するツールやコンポーネントを作ることができます。</span><span class="sxs-lookup"><span data-stu-id="dce00-159">The Common Language Specification (CLS) makes it possible to create tools and components that work with multiple programming languages.</span></span>  
  
 [<span data-ttu-id="dce00-160">チュートリアル: カスタム コンポーネントでツールボックスが自動的に入力</span><span class="sxs-lookup"><span data-stu-id="dce00-160">Walkthrough: Automatically Populating the Toolbox with Custom Components</span></span>](walkthrough-automatically-populating-the-toolbox-with-custom-components.md)  
 <span data-ttu-id="dce00-161">コンポーネントやコントロールを**ツールボックスのカスタマイズ** ダイアログ ボックスに表示できるようにする方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="dce00-161">Describes how to enable your component or control to be displayed in the **Customize Toolbox** dialog box.</span></span>
