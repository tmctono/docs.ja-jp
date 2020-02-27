---
title: '方法 : デザイナーを使って ImageList イメージを追加または削除する'
ms.date: 03/30/2017
helpviewer_keywords:
- ImageList component [Windows Forms], adding images
- ImageList component [Windows Forms], removing images
- images [Windows Forms], adding to ImageList component
ms.assetid: 5699b244-e37c-4d20-bc35-7441e55c1e3a
ms.openlocfilehash: cdc7b563a0ee4f8779b99b4e9a6786e78f8d500f
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/26/2020
ms.locfileid: "77628723"
---
# <a name="how-to-add-or-remove-imagelist-images-with-the-designer"></a><span data-ttu-id="f43b9-102">方法 : デザイナーを使って ImageList イメージを追加または削除する</span><span class="sxs-lookup"><span data-stu-id="f43b9-102">How to: Add or Remove ImageList Images with the Designer</span></span>

<span data-ttu-id="f43b9-103"><xref:System.Windows.Forms.ImageList> コンポーネントに画像を追加するには、さまざまな方法があります。</span><span class="sxs-lookup"><span data-stu-id="f43b9-103">You can add images to an <xref:System.Windows.Forms.ImageList> component several different ways.</span></span> <span data-ttu-id="f43b9-104"><xref:System.Windows.Forms.ImageList>に関連付けられたスマートタグを使用すると、イメージをすばやく追加できます。また、<xref:System.Windows.Forms.ImageList>で他のプロパティをいくつか設定する場合は、プロパティウィンドウに画像を追加する方が便利な場合があります。</span><span class="sxs-lookup"><span data-stu-id="f43b9-104">You can add images very quickly by using the smart tag associated with the <xref:System.Windows.Forms.ImageList>, or if you are setting several other properties on the <xref:System.Windows.Forms.ImageList>, you may find it more convenient to add images with the Properties window.</span></span> <span data-ttu-id="f43b9-105">コードを使用してイメージを追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="f43b9-105">You can also add images by using code.</span></span> <span data-ttu-id="f43b9-106">コードを使用してイメージを追加する方法の詳細については、「[方法: Windows フォーム ImageList コンポーネントを使用してイメージを追加または削除](how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f43b9-106">For more information about how to add images with code, see [How to: Add or Remove Images with the Windows Forms ImageList Component](how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md).</span></span> <span data-ttu-id="f43b9-107">通常は、コントロールに関連付けられる前に <xref:System.Windows.Forms.ImageList> コンポーネントにイメージを設定しますが、これは必須ではありません。</span><span class="sxs-lookup"><span data-stu-id="f43b9-107">Typically you populate the <xref:System.Windows.Forms.ImageList> component with images before it is associated with a control, but this is not required.</span></span>

### <a name="to-add-or-remove-images-by-using-the-properties-window"></a><span data-ttu-id="f43b9-108">プロパティウィンドウを使用してイメージを追加または削除するには</span><span class="sxs-lookup"><span data-stu-id="f43b9-108">To add or remove images by using the Properties window</span></span>

1. <span data-ttu-id="f43b9-109"><xref:System.Windows.Forms.ImageList> コンポーネントを選択するか、フォームに追加します。</span><span class="sxs-lookup"><span data-stu-id="f43b9-109">Select the <xref:System.Windows.Forms.ImageList> component, or add one to the form.</span></span>

2. <span data-ttu-id="f43b9-110">プロパティウィンドウで、<xref:System.Windows.Forms.ImageList.Images%2A> プロパティの横にある省略記号ボタン![([...]) をクリックします (Visual Studio のプロパティウィンドウの](./media/visual-studio-ellipsis-button.png))。</span><span class="sxs-lookup"><span data-stu-id="f43b9-110">In the Properties window, click the ellipsis button (![The Ellipsis button (...) in the Properties window of Visual Studio.](./media/visual-studio-ellipsis-button.png)) next to the <xref:System.Windows.Forms.ImageList.Images%2A> property.</span></span>

3. <span data-ttu-id="f43b9-111">**イメージコレクションエディター**で、 **[追加]** または **[削除]** をクリックして、一覧からイメージを追加または削除します。</span><span class="sxs-lookup"><span data-stu-id="f43b9-111">In the **Image Collection Editor**, click **Add** or **Remove** to add or remove images from the list.</span></span>

### <a name="to-add-or-remove-images-using-the-smart-tag"></a><span data-ttu-id="f43b9-112">スマートタグを使用してイメージを追加または削除するには</span><span class="sxs-lookup"><span data-stu-id="f43b9-112">To add or remove images using the smart tag</span></span>

1. <span data-ttu-id="f43b9-113"><xref:System.Windows.Forms.ImageList> コンポーネントを選択するか、フォームに追加します。</span><span class="sxs-lookup"><span data-stu-id="f43b9-113">Select the <xref:System.Windows.Forms.ImageList> component, or add one to the form.</span></span>

2. <span data-ttu-id="f43b9-114">デザイナーアクショングリフをクリックします (</span><span class="sxs-lookup"><span data-stu-id="f43b9-114">Click the designer actions glyph (</span></span>![小さい黒い矢印](./media/designer-actions-glyph.gif)<span data-ttu-id="f43b9-116">)</span><span class="sxs-lookup"><span data-stu-id="f43b9-116">)</span></span>

3. <span data-ttu-id="f43b9-117">**[ImageList Tasks]** ダイアログボックスで、 **[Images の選択]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="f43b9-117">In the **ImageList Tasks** dialog box, select **Choose Images**.</span></span>

4. <span data-ttu-id="f43b9-118">**イメージコレクションエディター**で、 **[追加]** または **[削除]** をクリックして、一覧からイメージを追加または削除します。</span><span class="sxs-lookup"><span data-stu-id="f43b9-118">In the **Images Collection Editor** click **Add** or **Remove** to add or remove images from the list.</span></span>

## <a name="see-also"></a><span data-ttu-id="f43b9-119">参照</span><span class="sxs-lookup"><span data-stu-id="f43b9-119">See also</span></span>

- [<span data-ttu-id="f43b9-120">イメージ、ビットマップ、メタファイル</span><span class="sxs-lookup"><span data-stu-id="f43b9-120">Images, Bitmaps, and Metafiles</span></span>](../advanced/images-bitmaps-and-metafiles.md)
- [<span data-ttu-id="f43b9-121">チュートリアル: デザイナーアクションを使用した一般的なタスクの実行</span><span class="sxs-lookup"><span data-stu-id="f43b9-121">Walkthrough: Perform common tasks using designer actions</span></span>](perform-common-tasks-design-actions.md)
- [<span data-ttu-id="f43b9-122">ImageList コンポーネント</span><span class="sxs-lookup"><span data-stu-id="f43b9-122">ImageList Component</span></span>](imagelist-component-windows-forms.md)
