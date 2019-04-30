---
title: '方法: Windows フォーム上のオブジェクトをレイヤー化する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Windows Forms controls, layering
- controls [Windows Forms], layering
- z order
- controls [Windows Forms], positioning
- z-order
ms.assetid: 1acc4281-2976-4715-86f4-bda68134baaf
ms.openlocfilehash: 8d0abbf0f71ac176d17261a0ae863938c575bdaf
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61941077"
---
# <a name="how-to-layer-objects-on-windows-forms"></a><span data-ttu-id="8ff4c-102">方法: Windows フォーム上のオブジェクトをレイヤー化する</span><span class="sxs-lookup"><span data-stu-id="8ff4c-102">How to: Layer Objects on Windows Forms</span></span>
<span data-ttu-id="8ff4c-103">複雑なユーザー インターフェイスを作成またはマルチ ドキュメント インターフェイス (MDI) フォームを使用するときにコントロールと複雑なユーザー インターフェイス (UI) を作成する子フォームをレイヤーには多くの場合、します。</span><span class="sxs-lookup"><span data-stu-id="8ff4c-103">When you create a complex user interface, or work with a multiple document interface (MDI) form, you will often want to layer both controls and child forms to create more complex user interfaces (UI).</span></span> <span data-ttu-id="8ff4c-104">コントロールと windows グループのコンテキスト内での追跡に移動するには、z オーダーを操作します。</span><span class="sxs-lookup"><span data-stu-id="8ff4c-104">To move and keep track of controls and windows within the context of a group, you manipulate their z-order.</span></span> <span data-ttu-id="8ff4c-105">*Z オーダー* (深度) のフォームの z 軸に沿ってフォーム上のコントロールのビジュアル レイヤーが。</span><span class="sxs-lookup"><span data-stu-id="8ff4c-105">*Z-order* is the visual layering of controls on a form along the form's z-axis (depth).</span></span> <span data-ttu-id="8ff4c-106">Z オーダーの上部にあるウィンドウには、その他のすべてのウィンドウが重複しています。</span><span class="sxs-lookup"><span data-stu-id="8ff4c-106">The window at the top of the z-order overlaps all other windows.</span></span> <span data-ttu-id="8ff4c-107">その他のすべての windows では、z オーダーの一番下にあるウィンドウが重複します。</span><span class="sxs-lookup"><span data-stu-id="8ff4c-107">All other windows overlap the window at the bottom of the z-order.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8ff4c-108">実際に画面に表示されるダイアログ ボックスとメニュー コマンドは、アクティブな設定またはエディションによっては、ヘルプの説明と異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="8ff4c-108">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="8ff4c-109">設定を変更するには、 **[ツール]** メニューの **[設定のインポートとエクスポート]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8ff4c-109">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="8ff4c-110">詳細については、「[Visual Studio IDE のカスタマイズ](/visualstudio/ide/personalizing-the-visual-studio-ide)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8ff4c-110">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-layer-controls-at-design-time"></a><span data-ttu-id="8ff4c-111">デザイン時にコントロールをレイヤーに</span><span class="sxs-lookup"><span data-stu-id="8ff4c-111">To layer controls at design time</span></span>  
  
1. <span data-ttu-id="8ff4c-112">レイヤー化コントロールを選択します。</span><span class="sxs-lookup"><span data-stu-id="8ff4c-112">Select a control that you want to layer.</span></span>  
  
2. <span data-ttu-id="8ff4c-113">**形式**メニューで、**順序**、 をクリックし、**前面へ移動**または**背面へ**。</span><span class="sxs-lookup"><span data-stu-id="8ff4c-113">On the **Format** menu, point to **Order**, and then click **Bring To Front** or **Send To Back**.</span></span>  
  
### <a name="to-layer-controls-programmatically"></a><span data-ttu-id="8ff4c-114">コントロールをプログラムでレイヤーを</span><span class="sxs-lookup"><span data-stu-id="8ff4c-114">To layer controls programmatically</span></span>  
  
- <span data-ttu-id="8ff4c-115">使用して、<xref:System.Windows.Forms.Control.BringToFront%2A>と<xref:System.Windows.Forms.Control.SendToBack%2A>コントロールの z オーダーを操作するメソッド。</span><span class="sxs-lookup"><span data-stu-id="8ff4c-115">Use the <xref:System.Windows.Forms.Control.BringToFront%2A> and <xref:System.Windows.Forms.Control.SendToBack%2A> methods to manipulate the z-order of the controls.</span></span>  
  
     <span data-ttu-id="8ff4c-116">たとえば場合、<xref:System.Windows.Forms.TextBox>コントロール、`txtFirstName`が下に別コントロールし、上部で、次のコードを使用します。</span><span class="sxs-lookup"><span data-stu-id="8ff4c-116">For example, if a <xref:System.Windows.Forms.TextBox> control, `txtFirstName`, is underneath another control and you want to have it on top, use the following code:</span></span>  
  
    ```vb  
    txtFirstName.BringToFront()  
    ```  
  
    ```csharp  
    txtFirstName.BringToFront();  
    ```  
  
    ```cpp  
    txtFirstName->BringToFront();  
    ```  
  
> [!NOTE]
>  <span data-ttu-id="8ff4c-117">Windows フォームのサポート*コントロール コンテインメント*します。</span><span class="sxs-lookup"><span data-stu-id="8ff4c-117">Windows Forms supports *control containment*.</span></span> <span data-ttu-id="8ff4c-118">コントロール コンテインメントの数などのコンテナー コントロール内のコントロールが配置<xref:System.Windows.Forms.RadioButton>内で制御する<xref:System.Windows.Forms.GroupBox>コントロール。</span><span class="sxs-lookup"><span data-stu-id="8ff4c-118">Control containment involves placing a number of controls within a containing control, such as a number of <xref:System.Windows.Forms.RadioButton> controls within a <xref:System.Windows.Forms.GroupBox> control.</span></span> <span data-ttu-id="8ff4c-119">格納しているコントロール内のコントロールを重ねることができます。</span><span class="sxs-lookup"><span data-stu-id="8ff4c-119">You can then layer the controls within the containing control.</span></span> <span data-ttu-id="8ff4c-120">グループ ボックスを移動すると、その内部に含まれているために同様に、コントロールが移動します。</span><span class="sxs-lookup"><span data-stu-id="8ff4c-120">Moving the group box moves the controls as well, because they are contained inside it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ff4c-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="8ff4c-121">See also</span></span>

- [<span data-ttu-id="8ff4c-122">Windows フォーム コントロール</span><span class="sxs-lookup"><span data-stu-id="8ff4c-122">Windows Forms Controls</span></span>](index.md)
- [<span data-ttu-id="8ff4c-123">Windows フォームでのコントロールの配置</span><span class="sxs-lookup"><span data-stu-id="8ff4c-123">Arranging Controls on Windows Forms</span></span>](arranging-controls-on-windows-forms.md)
- [<span data-ttu-id="8ff4c-124">各 Windows フォーム コントロールのラベル設定とショートカットの作成</span><span class="sxs-lookup"><span data-stu-id="8ff4c-124">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
- [<span data-ttu-id="8ff4c-125">Windows フォームで使用するコントロール</span><span class="sxs-lookup"><span data-stu-id="8ff4c-125">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
- [<span data-ttu-id="8ff4c-126">Windows フォーム コントロールの機能別一覧</span><span class="sxs-lookup"><span data-stu-id="8ff4c-126">Windows Forms Controls by Function</span></span>](windows-forms-controls-by-function.md)
