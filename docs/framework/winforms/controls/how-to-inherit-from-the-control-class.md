---
title: '方法: コントロール クラスを継承する'
ms.date: 03/30/2017
helpviewer_keywords:
- inheritance [Windows Forms], Windows Forms custom controls
- Control class [Windows Forms], inheriting from
- custom controls [Windows Forms], inheritance
- OnPaint method [Windows Forms]
- custom controls [Windows Forms], creating
ms.assetid: 46ba0df3-5cf7-443c-a3b4-a72660172476
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 02c40e310778bd476742f62ee8b9d8598b084a53
ms.sourcegitcommit: 121ab70c1ebedba41d276e436dd2b1502748a49f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/24/2019
ms.locfileid: "70015852"
---
# <a name="how-to-inherit-from-the-control-class"></a><span data-ttu-id="d5506-102">方法: コントロール クラスを継承する</span><span class="sxs-lookup"><span data-stu-id="d5506-102">How to: Inherit from the Control Class</span></span>

<span data-ttu-id="d5506-103">Windows フォームで使用する完全なカスタムコントロールを作成する場合は、 <xref:System.Windows.Forms.Control>クラスから継承する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d5506-103">If you want to create a completely custom control to use on a Windows Form, you should inherit from the <xref:System.Windows.Forms.Control> class.</span></span> <span data-ttu-id="d5506-104"><xref:System.Windows.Forms.Control>クラスから継承する場合は、より多くの計画と実装を実行する必要がありますが、最大のオプションも用意されています。</span><span class="sxs-lookup"><span data-stu-id="d5506-104">While inheriting from the <xref:System.Windows.Forms.Control> class requires that you perform more planning and implementation, it also provides you with the largest range of options.</span></span> <span data-ttu-id="d5506-105">から<xref:System.Windows.Forms.Control>継承する場合、コントロールを機能させるための非常に基本的な機能を継承します。</span><span class="sxs-lookup"><span data-stu-id="d5506-105">When inheriting from <xref:System.Windows.Forms.Control>, you inherit the very basic functionality that makes controls work.</span></span> <span data-ttu-id="d5506-106"><xref:System.Windows.Forms.Control>クラスに固有の機能は、キーボードとマウスを使用してユーザー入力を処理し、コントロールの境界とサイズを定義し、windows ハンドルを提供し、メッセージの処理とセキュリティを提供します。</span><span class="sxs-lookup"><span data-stu-id="d5506-106">The functionality inherent in the <xref:System.Windows.Forms.Control> class handles user input through the keyboard and mouse, defines the bounds and size of the control, provides a windows handle, and provides message handling and security.</span></span> <span data-ttu-id="d5506-107">描画機能 (ここではコントロールのグラフィカル インターフェイスを実際に表示する機能) や、ユーザーとやり取りするための特定の機能は含まれていません。</span><span class="sxs-lookup"><span data-stu-id="d5506-107">It does not incorporate any painting, which in this case is the actual rendering of the graphical interface of the control, nor does it incorporate any specific user interaction functionality.</span></span> <span data-ttu-id="d5506-108">このような機能はすべて、カスタム コードによって提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d5506-108">You must provide all of these aspects through custom code.</span></span>

## <a name="to-create-a-custom-control"></a><span data-ttu-id="d5506-109">カスタム コントロールを作成するには</span><span class="sxs-lookup"><span data-stu-id="d5506-109">To create a custom control</span></span>

1. <span data-ttu-id="d5506-110">Visual Studio で、新しい**Windows アプリケーション**プロジェクトまたは**windows コントロールライブラリ**プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="d5506-110">In Visual Studio, create a new **Windows Application** or **Windows Control Library** project.</span></span>

2. <span data-ttu-id="d5506-111">**[プロジェクト]** メニューの **[クラスの追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="d5506-111">From the **Project** menu, choose **Add Class**.</span></span>

3. <span data-ttu-id="d5506-112">**[新しい項目の追加]** ダイアログ ボックスの **[カスタム コントロール]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d5506-112">In the **Add New Item** dialog box, click **Custom Control**.</span></span>

   <span data-ttu-id="d5506-113">新しいカスタム コントロールがプロジェクトに追加されます。</span><span class="sxs-lookup"><span data-stu-id="d5506-113">A new custom control is added to your project.</span></span>

4. <span data-ttu-id="d5506-114">**F7**キーを押して、カスタムコントロールの**コードエディター**を開きます。</span><span class="sxs-lookup"><span data-stu-id="d5506-114">Press **F7** to open the **Code Editor** for your custom control.</span></span>

5. <span data-ttu-id="d5506-115">メソッドを探します。このメソッドは、基底クラスの<xref:System.Windows.Forms.Control.OnPaint%2A>メソッドの呼び出しを除いて空になります。 <xref:System.Windows.Forms.Control.OnPaint%2A></span><span class="sxs-lookup"><span data-stu-id="d5506-115">Locate the <xref:System.Windows.Forms.Control.OnPaint%2A> method, which will be empty except for a call to the <xref:System.Windows.Forms.Control.OnPaint%2A> method of the base class.</span></span>

6. <span data-ttu-id="d5506-116">コントロールで使用するカスタム描画が組み込まれるように、コードを修正します。</span><span class="sxs-lookup"><span data-stu-id="d5506-116">Modify the code to incorporate any custom painting you want for your control.</span></span>

   <span data-ttu-id="d5506-117">コントロールのグラフィックスをレンダリングするコードの記述については、「[コントロールのカスタム描画およびレンダリング](custom-control-painting-and-rendering.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d5506-117">For information about writing code to render graphics for controls, see [Custom Control Painting and Rendering](custom-control-painting-and-rendering.md).</span></span>

7. <span data-ttu-id="d5506-118">コントロールに組み込むカスタム メソッド、カスタム プロパティ、カスタム イベントを実装します。</span><span class="sxs-lookup"><span data-stu-id="d5506-118">Implement any custom methods, properties, or events that your control will incorporate.</span></span>

8. <span data-ttu-id="d5506-119">コントロールを保存して、動作確認を行います。</span><span class="sxs-lookup"><span data-stu-id="d5506-119">Save and test your control.</span></span>

## <a name="see-also"></a><span data-ttu-id="d5506-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="d5506-120">See also</span></span>

- [<span data-ttu-id="d5506-121">さまざまなカスタム コントロール</span><span class="sxs-lookup"><span data-stu-id="d5506-121">Varieties of Custom Controls</span></span>](varieties-of-custom-controls.md)
- [<span data-ttu-id="d5506-122">方法: UserControl クラスを継承する</span><span class="sxs-lookup"><span data-stu-id="d5506-122">How to: Inherit from the UserControl Class</span></span>](how-to-inherit-from-the-usercontrol-class.md)
- [<span data-ttu-id="d5506-123">方法: 既存の Windows フォームコントロールから継承する</span><span class="sxs-lookup"><span data-stu-id="d5506-123">How to: Inherit from Existing Windows Forms Controls</span></span>](how-to-inherit-from-existing-windows-forms-controls.md)
- [<span data-ttu-id="d5506-124">方法: Windows フォームの作成者コントロール</span><span class="sxs-lookup"><span data-stu-id="d5506-124">How to: Author Controls for Windows Forms</span></span>](how-to-author-controls-for-windows-forms.md)
- [<span data-ttu-id="d5506-125">Visual Basic での継承されたイベント ハンドラーのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="d5506-125">Troubleshooting Inherited Event Handlers in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md)
- [<span data-ttu-id="d5506-126">デザイン時の Windows フォーム コントロールの開発</span><span class="sxs-lookup"><span data-stu-id="d5506-126">Developing Windows Forms Controls at Design Time</span></span>](developing-windows-forms-controls-at-design-time.md)
