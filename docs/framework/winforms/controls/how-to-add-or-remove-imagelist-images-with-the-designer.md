---
title: '方法: デザイナーを使って ImageList イメージを追加または削除する'
ms.date: 03/30/2017
helpviewer_keywords:
- ImageList component [Windows Forms], adding images
- ImageList component [Windows Forms], removing images
- images [Windows Forms], adding to ImageList component
ms.assetid: 5699b244-e37c-4d20-bc35-7441e55c1e3a
ms.openlocfilehash: be17d5e6a12824c1c9edc867c99e77a6a1437a36
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/21/2019
ms.locfileid: "69658580"
---
# <a name="how-to-add-or-remove-imagelist-images-with-the-designer"></a><span data-ttu-id="d160a-102">方法: デザイナーを使って ImageList イメージを追加または削除する</span><span class="sxs-lookup"><span data-stu-id="d160a-102">How to: Add or Remove ImageList Images with the Designer</span></span>

<span data-ttu-id="d160a-103"><xref:System.Windows.Forms.ImageList>コンポーネントにイメージを追加するには、さまざまな方法があります。</span><span class="sxs-lookup"><span data-stu-id="d160a-103">You can add images to an <xref:System.Windows.Forms.ImageList> component several different ways.</span></span> <span data-ttu-id="d160a-104">に関連付けられ<xref:System.Windows.Forms.ImageList>たスマートタグを使用すると、イメージをすばやく追加できます。また、 <xref:System.Windows.Forms.ImageList>で他のプロパティをいくつか設定する場合は、プロパティウィンドウで画像を追加する方が便利な場合があります。</span><span class="sxs-lookup"><span data-stu-id="d160a-104">You can add images very quickly by using the smart tag associated with the <xref:System.Windows.Forms.ImageList>, or if you are setting several other properties on the <xref:System.Windows.Forms.ImageList>, you may find it more convenient to add images with the Properties window.</span></span> <span data-ttu-id="d160a-105">コードを使用してイメージを追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="d160a-105">You can also add images by using code.</span></span> <span data-ttu-id="d160a-106">コードを使用してイメージを追加する方法の詳細[については、「」を参照してください。Windows フォーム ImageList コンポーネント](how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md)を使用してイメージを追加または削除します。</span><span class="sxs-lookup"><span data-stu-id="d160a-106">For more information about how to add images with code, see [How to: Add or Remove Images with the Windows Forms ImageList Component](how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md).</span></span> <span data-ttu-id="d160a-107">通常は、コントロール<xref:System.Windows.Forms.ImageList>に関連付けられる前にコンポーネントにイメージを設定しますが、これは必須ではありません。</span><span class="sxs-lookup"><span data-stu-id="d160a-107">Typically you populate the <xref:System.Windows.Forms.ImageList> component with images before it is associated with a control, but this is not required.</span></span>

### <a name="to-add-or-remove-images-by-using-the-properties-window"></a><span data-ttu-id="d160a-108">プロパティウィンドウを使用してイメージを追加または削除するには</span><span class="sxs-lookup"><span data-stu-id="d160a-108">To add or remove images by using the Properties window</span></span>

1. <span data-ttu-id="d160a-109"><xref:System.Windows.Forms.ImageList>コンポーネントを選択するか、フォームに追加します。</span><span class="sxs-lookup"><span data-stu-id="d160a-109">Select the <xref:System.Windows.Forms.ImageList> component, or add one to the form.</span></span>

2. <span data-ttu-id="d160a-110">プロパティウィンドウで、プロパティの![ <xref:System.Windows.Forms.ImageList.Images%2A>横にある省略記号ボタン (Visual](./media/visual-studio-ellipsis-button.png)Studio のプロパティウィンドウの省略記号ボタン (...)) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d160a-110">In the Properties window, click the ellipsis button (![The Ellipsis button (...) in the Properties window of Visual Studio.](./media/visual-studio-ellipsis-button.png)) next to the <xref:System.Windows.Forms.ImageList.Images%2A> property.</span></span>

3. <span data-ttu-id="d160a-111">**イメージコレクションエディター**で、 **[追加]** または **[削除]** をクリックして、一覧からイメージを追加または削除します。</span><span class="sxs-lookup"><span data-stu-id="d160a-111">In the **Image Collection Editor**, click **Add** or **Remove** to add or remove images from the list.</span></span>

### <a name="to-add-or-remove-images-using-the-smart-tag"></a><span data-ttu-id="d160a-112">スマートタグを使用してイメージを追加または削除するには</span><span class="sxs-lookup"><span data-stu-id="d160a-112">To add or remove images using the smart tag</span></span>

1. <span data-ttu-id="d160a-113"><xref:System.Windows.Forms.ImageList>コンポーネントを選択するか、フォームに追加します。</span><span class="sxs-lookup"><span data-stu-id="d160a-113">Select the <xref:System.Windows.Forms.ImageList> component, or add one to the form.</span></span>

2. <span data-ttu-id="d160a-114">スマートタググリフ (![スマートタググリフ](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d160a-114">Click the smart tag glyph (![Smart Tag Glyph](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph"))</span></span>

3. <span data-ttu-id="d160a-115">**[ImageList Tasks]** ダイアログボックスで、 **[Images の選択]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="d160a-115">In the **ImageList Tasks** dialog box, select **Choose Images**.</span></span>

4. <span data-ttu-id="d160a-116">**イメージコレクションエディター**で、 **[追加]** または **[削除]** をクリックして、一覧からイメージを追加または削除します。</span><span class="sxs-lookup"><span data-stu-id="d160a-116">In the **Images Collection Editor** click **Add** or **Remove** to add or remove images from the list.</span></span>

## <a name="see-also"></a><span data-ttu-id="d160a-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="d160a-117">See also</span></span>

- [<span data-ttu-id="d160a-118">イメージ、ビットマップ、メタファイル</span><span class="sxs-lookup"><span data-stu-id="d160a-118">Images, Bitmaps, and Metafiles</span></span>](../advanced/images-bitmaps-and-metafiles.md)
- [<span data-ttu-id="d160a-119">チュートリアル: Windows フォームコントロールでのスマートタグを使用した一般的なタスクの実行</span><span class="sxs-lookup"><span data-stu-id="d160a-119">Walkthrough: Performing Common Tasks Using Smart Tags on Windows Forms Controls</span></span>](performing-common-tasks-using-smart-tags-on-wf-controls.md)
- [<span data-ttu-id="d160a-120">ImageList コンポーネント</span><span class="sxs-lookup"><span data-stu-id="d160a-120">ImageList Component</span></span>](imagelist-component-windows-forms.md)
