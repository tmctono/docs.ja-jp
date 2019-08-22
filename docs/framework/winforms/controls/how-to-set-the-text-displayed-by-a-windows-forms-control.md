---
title: '方法: Windows フォーム コントロールによって表示されるテキストを設定する'
ms.date: 08/20/2019
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Windows Forms, captions
- Button control [Windows Forms], button text
- StdFont object and CommandButton caption
- captions [Windows Forms], Windows Forms controls
- Text property [Windows Forms], Windows Forms control
- Button control [Windows Forms], text display
- labels [Windows Forms], adding to CommandButton control
- buttons [Windows Forms], text
- captions [Windows Forms], setting
- text
- examples [Windows Forms], controls
- text [Windows Forms], Windows Forms controls
- controls [Windows Forms], captions
- forms [Windows Forms], captions
ms.assetid: 36b95bff-8780-479d-b86a-f1a0673653aa
ms.openlocfilehash: 887aa5ec9b97770903cd87459d6df5adc3f7ddf0
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/21/2019
ms.locfileid: "69666153"
---
# <a name="how-to-set-the-text-displayed-by-a-windows-forms-control"></a><span data-ttu-id="a388e-102">方法: Windows フォームコントロールによって表示されるテキストを設定する</span><span class="sxs-lookup"><span data-stu-id="a388e-102">How to: Set the text displayed by a Windows Forms control</span></span>

<span data-ttu-id="a388e-103">Windows フォームコントロールには、通常、コントロールの主な機能に関連するテキストが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a388e-103">Windows Forms controls usually display some text that's related to the primary function of the control.</span></span> <span data-ttu-id="a388e-104">たとえば、コントロールに<xref:System.Windows.Forms.Button>は通常、ボタンがクリックされた場合に実行されるアクションを示すキャプションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a388e-104">For example, a <xref:System.Windows.Forms.Button> control usually displays a caption indicating what action will be performed if the button is clicked.</span></span> <span data-ttu-id="a388e-105">すべてのコントロールに対して、<xref:System.Windows.Forms.Control.Text%2A> プロパティを使用してテキストを設定または返すことができます。</span><span class="sxs-lookup"><span data-stu-id="a388e-105">For all controls, you can set or return the text by using the <xref:System.Windows.Forms.Control.Text%2A> property.</span></span> <span data-ttu-id="a388e-106"><xref:System.Windows.Forms.Control.Font%2A> プロパティを使用して、フォントを変更することができます。</span><span class="sxs-lookup"><span data-stu-id="a388e-106">You can change the font by using the <xref:System.Windows.Forms.Control.Font%2A> property.</span></span>

<span data-ttu-id="a388e-107">[デザイナー](#designer)を使用してテキストを設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="a388e-107">You can also set the text by using the [designer](#designer).</span></span>

## <a name="programmatic"></a><span data-ttu-id="a388e-108">一定</span><span class="sxs-lookup"><span data-stu-id="a388e-108">Programmatic</span></span>

1. <span data-ttu-id="a388e-109"><xref:System.Windows.Forms.Control.Text%2A> プロパティを文字列に設定します。</span><span class="sxs-lookup"><span data-stu-id="a388e-109">Set the <xref:System.Windows.Forms.Control.Text%2A> property to a string.</span></span>

   <span data-ttu-id="a388e-110">下線付きのアクセスキーを作成するには、アクセスキーにする文字の前にアンパサンド (&) を含めます。</span><span class="sxs-lookup"><span data-stu-id="a388e-110">To create an underlined access key, includes an ampersand (&) before the letter that will be the access key.</span></span>

2. <span data-ttu-id="a388e-111"><xref:System.Windows.Forms.Control.Font%2A> プロパティを型 <xref:System.Drawing.Font> のオブジェクトに設定します。</span><span class="sxs-lookup"><span data-stu-id="a388e-111">Set the <xref:System.Windows.Forms.Control.Font%2A> property to an object of type <xref:System.Drawing.Font>.</span></span>

    ```vb
    Button1.Text = "Click here to save changes"
    Button1.Font = New Font("Arial", 10, FontStyle.Bold, GraphicsUnit.Point)
    ```

    ```csharp
    button1.Text = "Click here to save changes";
    button1.Font = new Font("Arial", 10, FontStyle.Bold, GraphicsUnit.Point);
    ```

    ```cpp
    button1->Text = "Click here to save changes";
    button1->Font = new System::Drawing::Font("Arial", 10, FontStyle::Bold, GraphicsUnit::Point);
    ```

    > [!NOTE]
    > <span data-ttu-id="a388e-112">エスケープ文字を使用すると、メニュー項目など、通常は別の解釈がなされるユーザー インターフェイス要素の特殊文字を表示できます。</span><span class="sxs-lookup"><span data-stu-id="a388e-112">You can use an escape character to display a special character in user-interface elements that would normally interpret them differently, such as menu items.</span></span> <span data-ttu-id="a388e-113">たとえば、次のコード行では、メニュー項目のテキストが "& Now For all" というテキストに設定されています。</span><span class="sxs-lookup"><span data-stu-id="a388e-113">For example, the following line of code sets the menu item's text to read "& Now For Something Completely Different":</span></span>

    ```vb
    MPMenuItem.Text = "&& Now For Something Completely Different"
    ```

    ```csharp
    mpMenuItem.Text = "&& Now For Something Completely Different";
    ```

    ```cpp
    mpMenuItem->Text = "&& Now For Something Completely Different";
    ```

## <a name="designer"></a><span data-ttu-id="a388e-114">Designer</span><span class="sxs-lookup"><span data-stu-id="a388e-114">Designer</span></span>

1. <span data-ttu-id="a388e-115">Visual Studio の **[プロパティ]** ウィンドウで、コントロールの**Text**プロパティを適切な文字列に設定します。</span><span class="sxs-lookup"><span data-stu-id="a388e-115">In the **Properties** window in Visual Studio, set the **Text** property of the control to an appropriate string.</span></span>

   <span data-ttu-id="a388e-116">下線付きのショートカットキーを作成するには、ショートカットキーにする文字の前にアンパサンド (&) を含めます。</span><span class="sxs-lookup"><span data-stu-id="a388e-116">To create an underlined shortcut key, includes an ampersand (&) before the letter that will be the shortcut key.</span></span>

2. <span data-ttu-id="a388e-117">**[プロパティ]** ウィンドウで、 **[フォント]** プロパティ![の横にある省略記号ボタン (Visual Studio](./media/visual-studio-ellipsis-button.png)のプロパティウィンドウの省略記号ボタン (...)) を選択します。</span><span class="sxs-lookup"><span data-stu-id="a388e-117">In the **Properties** window, select the ellipsis button (![Ellipsis button (...) in the Properties window of Visual Studio](./media/visual-studio-ellipsis-button.png)) next to the **Font** property.</span></span>

   <span data-ttu-id="a388e-118">[標準フォント] ダイアログボックスで、フォント、フォントスタイル、サイズ、効果 (取り消し線、下線など)、および必要なスクリプトを選択します。</span><span class="sxs-lookup"><span data-stu-id="a388e-118">In the standard font dialog box, select the font, font style, size, effects (such as strikeout or underline), and script that you want.</span></span>

## <a name="see-also"></a><span data-ttu-id="a388e-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="a388e-119">See also</span></span>

- <xref:System.Windows.Forms.Control.Text%2A?displayProperty=nameWithType>
- [<span data-ttu-id="a388e-120">方法: Windows フォームコントロールのアクセスキーを作成する</span><span class="sxs-lookup"><span data-stu-id="a388e-120">How to: Create Access Keys for Windows Forms Controls</span></span>](how-to-create-access-keys-for-windows-forms-controls.md)
- [<span data-ttu-id="a388e-121">方法: Windows フォームボタンのクリックに応答する</span><span class="sxs-lookup"><span data-stu-id="a388e-121">How to: Respond to Windows Forms Button Clicks</span></span>](how-to-respond-to-windows-forms-button-clicks.md)
