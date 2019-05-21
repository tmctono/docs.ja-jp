---
title: '方法: デザイナーを使って ImageList イメージを追加または削除する'
ms.date: 03/30/2017
helpviewer_keywords:
- ImageList component [Windows Forms], adding images
- ImageList component [Windows Forms], removing images
- images [Windows Forms], adding to ImageList component
ms.assetid: 5699b244-e37c-4d20-bc35-7441e55c1e3a
ms.openlocfilehash: 57c124f19d208192cb2d4500274f7f897948252a
ms.sourcegitcommit: ffd7dd79468a81bbb0d6449f6d65513e050c04c4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/21/2019
ms.locfileid: "65960156"
---
# <a name="how-to-add-or-remove-imagelist-images-with-the-designer"></a><span data-ttu-id="108fa-102">方法: デザイナーを使って ImageList イメージを追加または削除する</span><span class="sxs-lookup"><span data-stu-id="108fa-102">How to: Add or Remove ImageList Images with the Designer</span></span>

<span data-ttu-id="108fa-103">イメージを追加することができます、<xref:System.Windows.Forms.ImageList>コンポーネントのいくつかの方法です。</span><span class="sxs-lookup"><span data-stu-id="108fa-103">You can add images to an <xref:System.Windows.Forms.ImageList> component several different ways.</span></span> <span data-ttu-id="108fa-104">関連付けられているスマート タグを使用してイメージを非常に簡単に追加することができます、 <xref:System.Windows.Forms.ImageList>、やの他のいくつかのプロパティを設定する場合、 <xref:System.Windows.Forms.ImageList>、[プロパティ] ウィンドウを使用したイメージを追加する方が便利見つけることがあります。</span><span class="sxs-lookup"><span data-stu-id="108fa-104">You can add images very quickly by using the smart tag associated with the <xref:System.Windows.Forms.ImageList>, or if you are setting several other properties on the <xref:System.Windows.Forms.ImageList>, you may find it more convenient to add images with the Properties window.</span></span> <span data-ttu-id="108fa-105">コードを使用してイメージを追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="108fa-105">You can also add images by using code.</span></span> <span data-ttu-id="108fa-106">コードを使用したイメージを追加する方法の詳細については、次を参照してください。[方法。追加または削除のイメージで、Windows フォームの ImageList コンポーネント](how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md)します。</span><span class="sxs-lookup"><span data-stu-id="108fa-106">For more information about how to add images with code, see [How to: Add or Remove Images with the Windows Forms ImageList Component](how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md).</span></span> <span data-ttu-id="108fa-107">値を設定する通常、<xref:System.Windows.Forms.ImageList>コンポーネントにイメージの前に、コントロールに関連付けられているが、これは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="108fa-107">Typically you populate the <xref:System.Windows.Forms.ImageList> component with images before it is associated with a control, but this is not required.</span></span>

> [!NOTE]
> <span data-ttu-id="108fa-108">実際に画面に表示されるダイアログ ボックスとメニュー コマンドは、アクティブな設定またはエディションによっては、ヘルプの説明と異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="108fa-108">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="108fa-109">設定を変更するには、 **[ツール]** メニューの **[設定のインポートとエクスポート]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="108fa-109">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="108fa-110">詳細については、「[Visual Studio IDE のカスタマイズ](/visualstudio/ide/personalizing-the-visual-studio-ide)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="108fa-110">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>

### <a name="to-add-or-remove-images-by-using-the-properties-window"></a><span data-ttu-id="108fa-111">追加またはプロパティ ウィンドウを使用してイメージを削除するには</span><span class="sxs-lookup"><span data-stu-id="108fa-111">To add or remove images by using the Properties window</span></span>

1. <span data-ttu-id="108fa-112">選択、<xref:System.Windows.Forms.ImageList>コンポーネントをフォームに追加します。</span><span class="sxs-lookup"><span data-stu-id="108fa-112">Select the <xref:System.Windows.Forms.ImageList> component, or add one to the form.</span></span>

2. <span data-ttu-id="108fa-113">[プロパティ] ウィンドウで、省略記号ボタンをクリックします。 (![。 Visual Studio の [プロパティ] ウィンドウで、省略記号ボタン (…)](./media/visual-studio-ellipsis-button.png)) 横に、<xref:System.Windows.Forms.ImageList.Images%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="108fa-113">In the Properties window, click the ellipsis button (![The Ellipsis button (...) in the Properties window of Visual Studio.](./media/visual-studio-ellipsis-button.png)) next to the <xref:System.Windows.Forms.ImageList.Images%2A> property.</span></span>

3. <span data-ttu-id="108fa-114">**イメージ コレクション エディター**、 をクリックして**追加**または**削除**を追加または一覧からイメージを削除します。</span><span class="sxs-lookup"><span data-stu-id="108fa-114">In the **Image Collection Editor**, click **Add** or **Remove** to add or remove images from the list.</span></span>

### <a name="to-add-or-remove-images-using-the-smart-tag"></a><span data-ttu-id="108fa-115">スマート タグを使用してイメージを追加または削除</span><span class="sxs-lookup"><span data-stu-id="108fa-115">To add or remove images using the smart tag</span></span>

1. <span data-ttu-id="108fa-116">選択、<xref:System.Windows.Forms.ImageList>コンポーネントをフォームに追加します。</span><span class="sxs-lookup"><span data-stu-id="108fa-116">Select the <xref:System.Windows.Forms.ImageList> component, or add one to the form.</span></span>

2. <span data-ttu-id="108fa-117">スマート タグ グリフをクリックします (![スマート タグ グリフ](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph"))</span><span class="sxs-lookup"><span data-stu-id="108fa-117">Click the smart tag glyph (![Smart Tag Glyph](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph"))</span></span>

3. <span data-ttu-id="108fa-118">**ImageList タスク**ダイアログ ボックスで、**イメージの選択**します。</span><span class="sxs-lookup"><span data-stu-id="108fa-118">In the **ImageList Tasks** dialog box, select **Choose Images**.</span></span>

4. <span data-ttu-id="108fa-119">**イメージ コレクション エディター**クリックして**追加**または**削除**を追加または一覧からイメージを削除します。</span><span class="sxs-lookup"><span data-stu-id="108fa-119">In the **Images Collection Editor** click **Add** or **Remove** to add or remove images from the list.</span></span>

## <a name="see-also"></a><span data-ttu-id="108fa-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="108fa-120">See also</span></span>

- [<span data-ttu-id="108fa-121">イメージ、ビットマップ、メタファイル</span><span class="sxs-lookup"><span data-stu-id="108fa-121">Images, Bitmaps, and Metafiles</span></span>](../advanced/images-bitmaps-and-metafiles.md)
- [<span data-ttu-id="108fa-122">チュートリアル: スマートを使用して一般的なタスクを実行する Windows フォーム コントロールをタグ</span><span class="sxs-lookup"><span data-stu-id="108fa-122">Walkthrough: Performing Common Tasks Using Smart Tags on Windows Forms Controls</span></span>](performing-common-tasks-using-smart-tags-on-wf-controls.md)
- [<span data-ttu-id="108fa-123">ImageList コンポーネント</span><span class="sxs-lookup"><span data-stu-id="108fa-123">ImageList Component</span></span>](imagelist-component-windows-forms.md)
