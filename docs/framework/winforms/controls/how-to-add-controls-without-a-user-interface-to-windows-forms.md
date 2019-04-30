---
title: '方法: ユーザー インターフェイスを持たないコントロールを Windows フォームに追加する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
f1_keywords:
- NonVisualSelection
helpviewer_keywords:
- invisible controls [Windows Forms]
- Windows Forms controls, adding to form
- controls [Windows Forms], nonvisual
- Windows Forms controls, nonvisual
- nonvisual controls [Windows Forms]
ms.assetid: 52134d9c-cff6-4eed-8e2b-3d5eb3bd494e
ms.openlocfilehash: 0768f811653543b3370310ccc0b59890273baf52
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62011087"
---
# <a name="how-to-add-controls-without-a-user-interface-to-windows-forms"></a><span data-ttu-id="f3d59-102">方法: ユーザー インターフェイスを持たないコントロールを Windows フォームに追加する</span><span class="sxs-lookup"><span data-stu-id="f3d59-102">How to: Add Controls Without a User Interface to Windows Forms</span></span>
<span data-ttu-id="f3d59-103">非ビジュアル コントロール (またはコンポーネント) は、アプリケーションに機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="f3d59-103">A nonvisual control (or component) provides functionality to your application.</span></span> <span data-ttu-id="f3d59-104">他のコントロールとは異なり、コンポーネントは、ユーザーにユーザー インターフェイスを提供しないし、ので、Windows フォーム デザイナー画面に表示する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="f3d59-104">Unlike other controls, components do not provide a user interface to the user and thus do not need to be displayed on the Windows Forms Designer surface.</span></span> <span data-ttu-id="f3d59-105">コンポーネントはフォームに追加するときに、Windows フォーム デザイナーはすべてのコンポーネントが表示されるフォームの下部にあるサイズ変更可能なトレイを表示します。</span><span class="sxs-lookup"><span data-stu-id="f3d59-105">When a component is added to a form, the Windows Forms Designer displays a resizable tray at the bottom of the form where all components are displayed.</span></span> <span data-ttu-id="f3d59-106">コントロールがコンポーネント トレイに追加されたら、コンポーネントを選択し、フォーム上の他のコントロールと同様に、そのプロパティを設定することができます。</span><span class="sxs-lookup"><span data-stu-id="f3d59-106">Once a control has been added to the component tray, you can select the component and set its properties as you would any other control on the form.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f3d59-107">実際に画面に表示されるダイアログ ボックスとメニュー コマンドは、アクティブな設定またはエディションによっては、ヘルプの説明と異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="f3d59-107">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="f3d59-108">設定を変更するには、 **[ツール]** メニューの **[設定のインポートとエクスポート]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f3d59-108">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="f3d59-109">詳細については、「[Visual Studio IDE のカスタマイズ](/visualstudio/ide/personalizing-the-visual-studio-ide)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f3d59-109">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-add-a-component-to-a-windows-form"></a><span data-ttu-id="f3d59-110">Windows フォームにコンポーネントを追加するには</span><span class="sxs-lookup"><span data-stu-id="f3d59-110">To add a component to a Windows Form</span></span>  
  
1. <span data-ttu-id="f3d59-111">フォームを開きます。</span><span class="sxs-lookup"><span data-stu-id="f3d59-111">Open the form.</span></span> <span data-ttu-id="f3d59-112">詳細については、「[方法: デザイナーで Windows フォームを表示](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/w5yd62ts(v=vs.100))します。</span><span class="sxs-lookup"><span data-stu-id="f3d59-112">For details, see [How to: Display Windows Forms in the Designer](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/w5yd62ts(v=vs.100)).</span></span>  
  
2. <span data-ttu-id="f3d59-113">**ツールボックス**コンポーネントをクリックし、フォームにドラッグします。</span><span class="sxs-lookup"><span data-stu-id="f3d59-113">In the **Toolbox**, click a component and drag it to your form.</span></span>  
  
     <span data-ttu-id="f3d59-114">コンポーネントがコンポーネント トレイに表示されます。</span><span class="sxs-lookup"><span data-stu-id="f3d59-114">Your component appears in the component tray.</span></span>  
  
 <span data-ttu-id="f3d59-115">さらに、コンポーネントは、実行時にフォームに追加できます。</span><span class="sxs-lookup"><span data-stu-id="f3d59-115">Furthermore, components can be added to a form at run time.</span></span> <span data-ttu-id="f3d59-116">これは、コンポーネントにはユーザー インターフェイスを持つコントロールとは異なり、ビジュアルの式があるないため、特に一般的なシナリオです。</span><span class="sxs-lookup"><span data-stu-id="f3d59-116">This is a common scenario, especially because components do not have a visual expression, unlike controls that have a user interface.</span></span> <span data-ttu-id="f3d59-117">次の例で、<xref:System.Windows.Forms.Timer>実行時にコンポーネントを追加します。</span><span class="sxs-lookup"><span data-stu-id="f3d59-117">In the example below, a <xref:System.Windows.Forms.Timer> component is added at run time.</span></span> <span data-ttu-id="f3d59-118">(Visual Studio には、別のタイマーの数値が含まれています。 この場合は、Windows フォームを使用して、<xref:System.Windows.Forms.Timer>コンポーネント。</span><span class="sxs-lookup"><span data-stu-id="f3d59-118">(Note that Visual Studio contains a number of different timers; in this case, use a Windows Forms <xref:System.Windows.Forms.Timer> component.</span></span> <span data-ttu-id="f3d59-119">Visual Studio の別のタイマーの詳細については、次を参照してください[サーバー ベースのタイマーの概要](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/tb9yt5e6(v=vs.90))。)。</span><span class="sxs-lookup"><span data-stu-id="f3d59-119">For more information about the different timers in Visual Studio, see [Introduction to Server-Based Timers](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/tb9yt5e6(v=vs.90)).)</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="f3d59-120">コンポーネントには、効果的に機能するコンポーネントに設定する必要がありますコントロールに固有のプロパティが多くの場合があります。</span><span class="sxs-lookup"><span data-stu-id="f3d59-120">Components often have control-specific properties that must be set for the component to function effectively.</span></span> <span data-ttu-id="f3d59-121">場合、<xref:System.Windows.Forms.Timer>設定する次のコンポーネント、`Interval`プロパティ。</span><span class="sxs-lookup"><span data-stu-id="f3d59-121">In the case of the <xref:System.Windows.Forms.Timer> component below, you set the `Interval` property.</span></span> <span data-ttu-id="f3d59-122">プロジェクトにあるプロパティを設定する、そのコンポーネントに必要なコンポーネントを追加するときにしてください。</span><span class="sxs-lookup"><span data-stu-id="f3d59-122">Be sure, when adding components to your project, that you set the properties necessary for that component.</span></span>  
  
#### <a name="to-add-a-component-to-a-windows-form-programmatically"></a><span data-ttu-id="f3d59-123">プログラムでコンポーネントを Windows フォームに追加するには</span><span class="sxs-lookup"><span data-stu-id="f3d59-123">To add a component to a Windows Form programmatically</span></span>  
  
1. <span data-ttu-id="f3d59-124">インスタンスを作成、<xref:System.Windows.Forms.Timer>コード内のクラス。</span><span class="sxs-lookup"><span data-stu-id="f3d59-124">Create an instance of the <xref:System.Windows.Forms.Timer> class in code.</span></span>  
  
2. <span data-ttu-id="f3d59-125">設定、`Interval`タイマーのティック間の時間を決定するプロパティ。</span><span class="sxs-lookup"><span data-stu-id="f3d59-125">Set the `Interval` property to determine the time between ticks of the timer.</span></span>  
  
3. <span data-ttu-id="f3d59-126">コンポーネントに必要なその他のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="f3d59-126">Configure any other necessary properties for your component.</span></span>  
  
     <span data-ttu-id="f3d59-127">次のコードの作成を示しています、<xref:System.Windows.Forms.Timer>でその`Interval`プロパティ セット。</span><span class="sxs-lookup"><span data-stu-id="f3d59-127">The following code shows the creation of a <xref:System.Windows.Forms.Timer> with its `Interval` property set.</span></span>  
  
    ```vb  
    Public Sub CreateTimer()  
       Dim timerKeepTrack As New System.Windows.Forms.Timer  
       timerKeepTrack.Interval = 1000  
    End Sub  
    ```  
  
    ```csharp  
    public void createTimer()  
    {  
       System.Windows.Forms.Timer timerKeepTrack = new  
           System.Windows.Forms.Timer();  
       timerKeepTrack.Interval = 1000;  
    }  
    ```  
  
    ```cpp  
    public:  
       void createTimer()  
       {  
          System::Windows::Forms::Timer^ timerKeepTrack = gcnew  
             System::Windows::Forms::Timer();  
          timerKeepTrack->Interval = 1000;  
       }  
    ```  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="f3d59-128">悪意のあるユーザー コントロールを参照することで、ローカル コンピューターがネットワーク経由のセキュリティ リスクを公開する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f3d59-128">You might expose your local computer to a security risk through the network by referencing a malicious UserControl.</span></span> <span data-ttu-id="f3d59-129">誤ってそれをプロジェクトに追加した後に、有害なカスタム コントロールを作成する悪意のあるユーザーの場合の問題のみなります。</span><span class="sxs-lookup"><span data-stu-id="f3d59-129">This would only be a concern in the case of a malicious person creating a damaging custom control, followed by you mistakenly adding it to your project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3d59-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="f3d59-130">See also</span></span>

- [<span data-ttu-id="f3d59-131">Windows フォーム コントロール</span><span class="sxs-lookup"><span data-stu-id="f3d59-131">Windows Forms Controls</span></span>](index.md)
- [<span data-ttu-id="f3d59-132">方法: Windows フォームにコントロールを追加します。</span><span class="sxs-lookup"><span data-stu-id="f3d59-132">How to: Add Controls to Windows Forms</span></span>](how-to-add-controls-to-windows-forms.md)
- [<span data-ttu-id="f3d59-133">方法: Windows フォームに ActiveX コントロールを追加します。</span><span class="sxs-lookup"><span data-stu-id="f3d59-133">How to: Add ActiveX Controls to Windows Forms</span></span>](how-to-add-activex-controls-to-windows-forms.md)
- [<span data-ttu-id="f3d59-134">方法: Windows フォーム間でコントロールをコピーします。</span><span class="sxs-lookup"><span data-stu-id="f3d59-134">How to: Copy Controls Between Windows Forms</span></span>](how-to-copy-controls-between-windows-forms.md)
- [<span data-ttu-id="f3d59-135">Windows フォームへのコントロールの追加</span><span class="sxs-lookup"><span data-stu-id="f3d59-135">Putting Controls on Windows Forms</span></span>](putting-controls-on-windows-forms.md)
- [<span data-ttu-id="f3d59-136">各 Windows フォーム コントロールのラベル設定とショートカットの作成</span><span class="sxs-lookup"><span data-stu-id="f3d59-136">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
- [<span data-ttu-id="f3d59-137">Windows フォームで使用するコントロール</span><span class="sxs-lookup"><span data-stu-id="f3d59-137">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
- [<span data-ttu-id="f3d59-138">Windows フォーム コントロールの機能別一覧</span><span class="sxs-lookup"><span data-stu-id="f3d59-138">Windows Forms Controls by Function</span></span>](windows-forms-controls-by-function.md)
