---
title: '方法: Windows フォームを継承する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- inherited forms [Windows Forms], creating at run-time
- inheritance [Windows Forms], forms
- Windows Forms, inheritance
ms.assetid: cb3e1c0f-3d2a-4cdc-b0d1-c92eae567ffb
ms.openlocfilehash: 0d8799359a12b9bb64331d83df2500bede8c0ff2
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59314544"
---
# <a name="how-to-inherit-windows-forms"></a><span data-ttu-id="13d74-102">方法: Windows フォームを継承する</span><span class="sxs-lookup"><span data-stu-id="13d74-102">How to: Inherit Windows Forms</span></span>
<span data-ttu-id="13d74-103">新規の Windows フォームは、基本フォームから継承して簡単に複製できます。フォームが必要になるたびに、最初から作成し直す必要はありません。</span><span class="sxs-lookup"><span data-stu-id="13d74-103">Creating new Windows Forms by inheriting from base forms is a handy way to duplicate your best efforts without going through the process of entirely recreating a form every time you require it.</span></span>  
  
 <span data-ttu-id="13d74-104">使用してデザイン時にフォームの継承の詳細については、**継承ピッカー**継承されるコントロールのダイアログ ボックスとのセキュリティ レベルを視覚的に区別する方法は、「[方法。継承ピッカー ダイアログ ボックスを使用してフォームを継承する](how-to-inherit-forms-using-the-inheritance-picker-dialog-box.md)します。</span><span class="sxs-lookup"><span data-stu-id="13d74-104">For more information about inheriting forms at design time using the **Inheritance Picker** dialog box and how to visually distinguish between security levels of inherited controls, see [How to: Inherit Forms Using the Inheritance Picker Dialog Box](how-to-inherit-forms-using-the-inheritance-picker-dialog-box.md).</span></span>  
  
 <span data-ttu-id="13d74-105">**メモ** フォームを継承するには、そのフォームを含むファイルまたは名前空間が実行可能ファイルまたは DLL に組み込まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="13d74-105">**Note** In order to inherit from a form, the file or namespace containing that form must have been built into an executable file or DLL.</span></span> <span data-ttu-id="13d74-106">プロジェクトをビルドするには、**[ビルド]** メニューの **[ビルド]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="13d74-106">To build the project, choose **Build** from the **Build** menu.</span></span> <span data-ttu-id="13d74-107">また、フォームの継承先となるクラスに、名前空間への参照を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="13d74-107">Also, a reference to the namespace must be added to the class inheriting the form.</span></span> <span data-ttu-id="13d74-108">実際に画面に表示されるダイアログ ボックスとメニュー コマンドは、アクティブな設定またはエディションによっては、ヘルプの説明と異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="13d74-108">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="13d74-109">設定を変更するには、 **[ツール]** メニューの **[設定のインポートとエクスポート]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="13d74-109">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="13d74-110">詳細については、「[Visual Studio IDE のカスタマイズ](/visualstudio/ide/personalizing-the-visual-studio-ide)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="13d74-110">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-inherit-a-form-programmatically"></a><span data-ttu-id="13d74-111">プログラムによってフォームを継承するには</span><span class="sxs-lookup"><span data-stu-id="13d74-111">To inherit a form programmatically</span></span>  
  
1. <span data-ttu-id="13d74-112">クラスに、継承元のフォームを含む名前空間への参照を追加します。</span><span class="sxs-lookup"><span data-stu-id="13d74-112">In your class, add a reference to the namespace containing the form you wish to inherit from.</span></span>  
  
2. <span data-ttu-id="13d74-113">クラス定義に、継承元のフォームへの参照を追加します。</span><span class="sxs-lookup"><span data-stu-id="13d74-113">In the class definition, add a reference to the form to inherit from.</span></span> <span data-ttu-id="13d74-114">参照では、フォームを含んでいる名前空間を指定し、その後にピリオド、続いて基本フォーム自体の名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="13d74-114">The reference should include the namespace that contains the form, followed by a period, then the name of the base form itself.</span></span>  
  
    ```vb  
    Public Class Form2  
        Inherits Namespace1.Form1  
    ```  
  
    ```csharp  
    public class Form2 : Namespace1.Form1  
    ```  
  
 <span data-ttu-id="13d74-115">フォームを継承する場合は、イベント ハンドラーが 2 回呼び出されることで問題が発生する可能性があることに注意してください。これは、各イベントが基底クラスと継承クラスの両方によって処理されるためです。</span><span class="sxs-lookup"><span data-stu-id="13d74-115">When inheriting forms, keep in mind that issues may arise with regard to event handlers being called twice, because each event is being handled by both the base class and the inherited class.</span></span> <span data-ttu-id="13d74-116">この問題を回避する方法の詳細については、「[Visual Basic で継承されたイベント ハンドラーのトラブルシューティング](~/docs/visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="13d74-116">For more information on how to avoid this problem, see [Troubleshooting Inherited Event Handlers in Visual Basic](~/docs/visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13d74-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="13d74-117">See also</span></span>

- [<span data-ttu-id="13d74-118">Inherits ステートメント</span><span class="sxs-lookup"><span data-stu-id="13d74-118">Inherits Statement</span></span>](~/docs/visual-basic/language-reference/statements/inherits-statement.md)
- [<span data-ttu-id="13d74-119">Imports ステートメント (.NET 名前空間および型)</span><span class="sxs-lookup"><span data-stu-id="13d74-119">Imports Statement (.NET Namespace and Type)</span></span>](~/docs/visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)
- [<span data-ttu-id="13d74-120">using</span><span class="sxs-lookup"><span data-stu-id="13d74-120">using</span></span>](~/docs/csharp/language-reference/keywords/using.md)
- [<span data-ttu-id="13d74-121">基本フォームの外観を変更した場合の影響</span><span class="sxs-lookup"><span data-stu-id="13d74-121">Effects of Modifying a Base Form's Appearance</span></span>](effects-of-modifying-base-form-appearance.md)
- [<span data-ttu-id="13d74-122">Windows フォームのビジュアルの継承</span><span class="sxs-lookup"><span data-stu-id="13d74-122">Windows Forms Visual Inheritance</span></span>](windows-forms-visual-inheritance.md)
