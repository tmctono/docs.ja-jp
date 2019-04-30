---
title: '方法: UserControl クラスを継承する'
ms.date: 03/30/2017
helpviewer_keywords:
- inheritance [Windows Forms], Windows Forms custom controls
- UserControl class [Windows Forms], inheriting from
- user controls [Windows Forms], creating
- composite controls [Windows Forms], creating
ms.assetid: 67713625-e2e4-4f6a-bce7-0855ee5043d9
ms.openlocfilehash: 5e9bdb6d6628b1c696b7944dc0ea1f4c974c8172
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61941129"
---
# <a name="how-to-inherit-from-the-usercontrol-class"></a><span data-ttu-id="aaf29-102">方法: UserControl クラスを継承する</span><span class="sxs-lookup"><span data-stu-id="aaf29-102">How to: Inherit from the UserControl Class</span></span>
<span data-ttu-id="aaf29-103">カスタム コードを使用して 1 つ以上の Windows フォーム コントロールの機能を組み合わせるには、"*ユーザー コントロール*" を作成します。</span><span class="sxs-lookup"><span data-stu-id="aaf29-103">To combine the functionality of one or more Windows Forms controls with custom code, you can create a *user control*.</span></span> <span data-ttu-id="aaf29-104">ユーザー コントロールは、迅速なコントロール開発、標準の Windows フォーム コントロールの機能、およびカスタム プロパティやカスタム メソッドの多用途性を組み合わせたものです。</span><span class="sxs-lookup"><span data-stu-id="aaf29-104">User controls combine rapid control development, standard Windows Forms control functionality, and the versatility of custom properties and methods.</span></span> <span data-ttu-id="aaf29-105">ユーザー コントロールの作成を開始すると、デザイナーが表示され、標準の Windows フォーム コントロールを配置できます。</span><span class="sxs-lookup"><span data-stu-id="aaf29-105">When you begin creating a user control, you are presented with a visible designer, upon which you can place standard Windows Forms controls.</span></span> <span data-ttu-id="aaf29-106">これらのコントロールは、標準コントロールの外観と動作 (ルック アンド フィール) に加えて、固有の機能のすべてを保持します。</span><span class="sxs-lookup"><span data-stu-id="aaf29-106">These controls retain all of their inherent functionality, as well as the appearance and behavior (look and feel) of standard controls.</span></span> <span data-ttu-id="aaf29-107">ただし、これらのコントロールをユーザー コントロールに組み込んだ場合、コードを介して使用することはできなくなります。</span><span class="sxs-lookup"><span data-stu-id="aaf29-107">Once these controls are built into the user control, however, they are no longer available to you through code.</span></span> <span data-ttu-id="aaf29-108">ユーザー コントロールは独自の描画を行い、標準コントロールに関連付けられた基本的な機能もすべて処理します。</span><span class="sxs-lookup"><span data-stu-id="aaf29-108">The user control does its own painting and also handles all of the basic functionality associated with controls.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="aaf29-109">実際に画面に表示されるダイアログ ボックスとメニュー コマンドは、アクティブな設定またはエディションによっては、ヘルプの説明と異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="aaf29-109">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="aaf29-110">設定を変更するには、 **[ツール]** メニューの **[設定のインポートとエクスポート]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="aaf29-110">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="aaf29-111">詳細については、「[Visual Studio IDE のカスタマイズ](/visualstudio/ide/personalizing-the-visual-studio-ide)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="aaf29-111">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-create-a-user-control"></a><span data-ttu-id="aaf29-112">ユーザー コントロールを作成するには</span><span class="sxs-lookup"><span data-stu-id="aaf29-112">To create a user control</span></span>  
  
1. <span data-ttu-id="aaf29-113">新しい **Windows コントロール ライブラリ** プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="aaf29-113">Create a new **Windows Control Library** project.</span></span>  
  
     <span data-ttu-id="aaf29-114">空白のユーザー コントロールを含む新しいプロジェクトが作成されます。</span><span class="sxs-lookup"><span data-stu-id="aaf29-114">A new project is created with a blank user control.</span></span>  
  
2. <span data-ttu-id="aaf29-115">コントロールを、**ツールボックス**の **[Windows フォーム]** タブからデザイナーにドラッグします。</span><span class="sxs-lookup"><span data-stu-id="aaf29-115">Drag controls from the **Windows Forms** tab of the **Toolbox** onto your designer.</span></span>  
  
3. <span data-ttu-id="aaf29-116">こうしたコントロールは、最終的なユーザー コントロールに表示するときと同じように、配置およびデザインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="aaf29-116">These controls should be positioned and designed as you want them to appear in the final user control.</span></span> <span data-ttu-id="aaf29-117">開発者が内在コントロールにアクセスできるようにするには、内在コントロールをパブリックとして宣言するか、内在コントロールを選択して公開します。</span><span class="sxs-lookup"><span data-stu-id="aaf29-117">If you want to allow developers to access the constituent controls, you must declare them as public, or selectively expose properties of the constituent control.</span></span> <span data-ttu-id="aaf29-118">詳細については、「[方法: 内在コントロールのプロパティを公開](how-to-expose-properties-of-constituent-controls.md)します。</span><span class="sxs-lookup"><span data-stu-id="aaf29-118">For details, see [How to: Expose Properties of Constituent Controls](how-to-expose-properties-of-constituent-controls.md).</span></span>  
  
4. <span data-ttu-id="aaf29-119">コントロールに組み込むカスタム メソッドやカスタム プロパティを実装します。</span><span class="sxs-lookup"><span data-stu-id="aaf29-119">Implement any custom methods or properties that your control will incorporate.</span></span>  
  
5. <span data-ttu-id="aaf29-120">F5 キーを押してプロジェクトをビルドし、**UserControl Test Container** でコントロールを実行します。</span><span class="sxs-lookup"><span data-stu-id="aaf29-120">Press F5 to build the project and run your control in the **UserControl Test Container**.</span></span> <span data-ttu-id="aaf29-121">詳細については、「[方法 :UserControl の実行時の動作をテスト](how-to-test-the-run-time-behavior-of-a-usercontrol.md)します。</span><span class="sxs-lookup"><span data-stu-id="aaf29-121">For more information, see [How to: Test the Run-Time Behavior of a UserControl](how-to-test-the-run-time-behavior-of-a-usercontrol.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aaf29-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="aaf29-122">See also</span></span>

- [<span data-ttu-id="aaf29-123">さまざまなカスタム コントロール</span><span class="sxs-lookup"><span data-stu-id="aaf29-123">Varieties of Custom Controls</span></span>](varieties-of-custom-controls.md)
- [<span data-ttu-id="aaf29-124">方法: コントロール クラスから継承します。</span><span class="sxs-lookup"><span data-stu-id="aaf29-124">How to: Inherit from the Control Class</span></span>](how-to-inherit-from-the-control-class.md)
- [<span data-ttu-id="aaf29-125">方法: 継承可能な既存の Windows フォーム コントロール</span><span class="sxs-lookup"><span data-stu-id="aaf29-125">How to: Inherit from Existing Windows Forms Controls</span></span>](how-to-inherit-from-existing-windows-forms-controls.md)
- [<span data-ttu-id="aaf29-126">方法: Windows フォームのコントロールの作成</span><span class="sxs-lookup"><span data-stu-id="aaf29-126">How to: Author Controls for Windows Forms</span></span>](how-to-author-controls-for-windows-forms.md)
- [<span data-ttu-id="aaf29-127">Visual Basic での継承されたイベント ハンドラーのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="aaf29-127">Troubleshooting Inherited Event Handlers in Visual Basic</span></span>](~/docs/visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md)
- [<span data-ttu-id="aaf29-128">方法: UserControl の実行時の動作をテストします。</span><span class="sxs-lookup"><span data-stu-id="aaf29-128">How to: Test the Run-Time Behavior of a UserControl</span></span>](how-to-test-the-run-time-behavior-of-a-usercontrol.md)
