---
title: 'チュートリアル: Visual C# による複合コントロールの作成'
ms.date: 03/30/2017
helpviewer_keywords:
- custom controls [C#]
- user controls [Windows Forms], creating with Visual C#
- UserControl class [Windows Forms], walkthroughs
- user controls [C#]
- custom controls [Windows Forms], creating
ms.assetid: f88481a8-c746-4a36-9479-374ce5f2e91f
ms.openlocfilehash: 1de1ff4147ddb8cb3316795aefd38622de205a73
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69950050"
---
# <a name="walkthrough-authoring-a-composite-control-with-visual-c"></a><span data-ttu-id="6dcd0-102">チュートリアル: Visual C を使用した複合コントロールの作成\#</span><span class="sxs-lookup"><span data-stu-id="6dcd0-102">Walkthrough: Authoring a Composite Control with Visual C\#</span></span>

<span data-ttu-id="6dcd0-103">複合コントロールは、カスタム グラフィカル インターフェイスを作成し、再利用するための手段を提供します。</span><span class="sxs-lookup"><span data-stu-id="6dcd0-103">Composite controls provide a means by which custom graphical interfaces can be created and reused.</span></span> <span data-ttu-id="6dcd0-104">複合コントロールは、基本的には視覚的に表示されるコンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="6dcd0-104">A composite control is essentially a component with a visual representation.</span></span> <span data-ttu-id="6dcd0-105">そのため、複合コントロールは、1 つ以上の Windows フォーム コントロール、コンポーネント、または機能を拡張できるコード ブロックで構成されます。コード ブロックでは、ユーザー入力の検証、表示プロパティの変更、作成者が必要とする他のタスクの実行などによって機能を拡張します。</span><span class="sxs-lookup"><span data-stu-id="6dcd0-105">As such, it might consist of one or more Windows Forms controls, components, or blocks of code that can extend functionality by validating user input, modifying display properties, or performing other tasks required by the author.</span></span> <span data-ttu-id="6dcd0-106">複合コントロールは、他のコントロールと同様に Windows フォームに配置できます。</span><span class="sxs-lookup"><span data-stu-id="6dcd0-106">Composite controls can be placed on Windows Forms in the same manner as other controls.</span></span> <span data-ttu-id="6dcd0-107">このチュートリアルの前半では、`ctlClock` という単純な複合コントロールを作成します。</span><span class="sxs-lookup"><span data-stu-id="6dcd0-107">In the first part of this walkthrough, you create a simple composite control called `ctlClock`.</span></span> <span data-ttu-id="6dcd0-108">チュートリアルの後半では、継承によって `ctlClock` の機能を拡張します。</span><span class="sxs-lookup"><span data-stu-id="6dcd0-108">In the second part of the walkthrough, you extend the functionality of `ctlClock` through inheritance.</span></span>

## <a name="creating-the-project"></a><span data-ttu-id="6dcd0-109">プロジェクトの作成</span><span class="sxs-lookup"><span data-stu-id="6dcd0-109">Creating the Project</span></span>

<span data-ttu-id="6dcd0-110">新しいプロジェクトを作成するときは、ルート名前空間、アセンブリ名、プロジェクト名を設定し、既定のコンポーネントが適切な名前空間に含まれるようにするために、プロジェクトの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="6dcd0-110">When you create a new project, you specify its name to set the root namespace, assembly name, and project name, and ensure that the default component will be in the correct namespace.</span></span>

### <a name="to-create-the-ctlclocklib-control-library-and-the-ctlclock-control"></a><span data-ttu-id="6dcd0-111">ctlClockLib コントロール ライブラリと ctlClock コントロールを作成するには</span><span class="sxs-lookup"><span data-stu-id="6dcd0-111">To create the ctlClockLib control library and the ctlClock control</span></span>

1. <span data-ttu-id="6dcd0-112">**[ファイル]** メニューの **[新規作成]** をポイントし、 **[プロジェクト]** をクリックして **[新しいプロジェクト]** ダイアログ ボックスを開きます。</span><span class="sxs-lookup"><span data-stu-id="6dcd0-112">On the **File** menu, point to **New**, and then click **Project** to open the **New Project** dialog box.</span></span>

2. <span data-ttu-id="6dcd0-113">ビジュアルC#プロジェクトの一覧から **[Windows フォームコントロールライブラリ]** プロジェクトテンプレートを選択し、 `ctlClockLib` **[名前]** ボックスに「」と入力して、 **[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6dcd0-113">From the list of Visual C# projects, select the **Windows Forms Control Library** project template, type `ctlClockLib` in the **Name** box, and then click **OK**.</span></span>

     <span data-ttu-id="6dcd0-114">プロジェクト名 `ctlClockLib` は、既定でルート名前空間にも割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="6dcd0-114">The project name, `ctlClockLib`, is also assigned to the root namespace by default.</span></span> <span data-ttu-id="6dcd0-115">ルート名前空間は、アセンブリ内のコンポーネント名の修飾に使用されます。</span><span class="sxs-lookup"><span data-stu-id="6dcd0-115">The root namespace is used to qualify the names of components in the assembly.</span></span> <span data-ttu-id="6dcd0-116">たとえば、`ctlClock` という名前のコンポーネントが 2 つのアセンブリに含まれている場合、`ctlClockLib.ctlClock.` を使用して目的の `ctlClock` コンポーネントを指定できます。</span><span class="sxs-lookup"><span data-stu-id="6dcd0-116">For example, if two assemblies provide components named `ctlClock`, you can specify your `ctlClock` component using `ctlClockLib.ctlClock.`</span></span>

3. <span data-ttu-id="6dcd0-117">ソリューション エクスプローラーで、 **[UserControl1.cs]** を右クリックし、 **[名前の変更]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6dcd0-117">In Solution Explorer, right-click **UserControl1.cs**, and then click **Rename**.</span></span> <span data-ttu-id="6dcd0-118">ファイル名を `ctlClock.cs` に変更します。</span><span class="sxs-lookup"><span data-stu-id="6dcd0-118">Change the file name to `ctlClock.cs`.</span></span> <span data-ttu-id="6dcd0-119">コード要素 "UserControl1" へのすべての参照の名前を変更するかどうかをたずねられたら、 **[はい]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6dcd0-119">Click the **Yes** button when you are asked if you want to rename all references to the code element "UserControl1".</span></span>

    > [!NOTE]
    > <span data-ttu-id="6dcd0-120">既定では、複合コントロールは、システム<xref:System.Windows.Forms.UserControl>によって提供されるクラスから継承されます。</span><span class="sxs-lookup"><span data-stu-id="6dcd0-120">By default, a composite control inherits from the <xref:System.Windows.Forms.UserControl> class provided by the system.</span></span> <span data-ttu-id="6dcd0-121">クラス<xref:System.Windows.Forms.UserControl>は、すべての複合コントロールに必要な機能を提供し、標準のメソッドとプロパティを実装します。</span><span class="sxs-lookup"><span data-stu-id="6dcd0-121">The <xref:System.Windows.Forms.UserControl> class provides functionality required by all composite controls, and implements standard methods and properties.</span></span>

4. <span data-ttu-id="6dcd0-122">**[ファイル]** メニューの **[すべて保存]** をクリックして、プロジェクトを保存します。</span><span class="sxs-lookup"><span data-stu-id="6dcd0-122">On the **File** menu, click **Save All** to save the project.</span></span>

## <a name="adding-windows-controls-and-components-to-the-composite-control"></a><span data-ttu-id="6dcd0-123">複合コントロールへの Windows コントロールとコンポーネントの追加</span><span class="sxs-lookup"><span data-stu-id="6dcd0-123">Adding Windows Controls and Components to the Composite Control</span></span>

<span data-ttu-id="6dcd0-124">ビジュアル インターフェイスは、複合コントロールに不可欠な部分です。</span><span class="sxs-lookup"><span data-stu-id="6dcd0-124">A visual interface is an essential part of your composite control.</span></span> <span data-ttu-id="6dcd0-125">このビジュアル インターフェイスは、デザイナー画面に 1 つ以上の Windows コントロールを追加することによって実装されます。</span><span class="sxs-lookup"><span data-stu-id="6dcd0-125">This visual interface is implemented by the addition of one or more Windows controls to the designer surface.</span></span> <span data-ttu-id="6dcd0-126">次の例では、複合コントロールに Windows コントロールを組み込み、機能を実装するコードを記述します。</span><span class="sxs-lookup"><span data-stu-id="6dcd0-126">In the following demonstration, you will incorporate Windows controls into your composite control and write code to implement functionality.</span></span>

### <a name="to-add-a-label-and-a-timer-to-your-composite-control"></a><span data-ttu-id="6dcd0-127">複合コントロールに Label と Timer を追加するには</span><span class="sxs-lookup"><span data-stu-id="6dcd0-127">To add a Label and a Timer to your composite control</span></span>

1. <span data-ttu-id="6dcd0-128">ソリューション エクスプローラーで、 **[ctlClock.cs]** を右クリックし、 **[デザイナーの表示]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6dcd0-128">In Solution Explorer, right-click **ctlClock.cs**, and then click **View Designer**.</span></span>

2. <span data-ttu-id="6dcd0-129">**ツールボックス**の **[コモン コントロール]** ノードを展開し、 **[Label]** をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="6dcd0-129">In the **Toolbox**, expand the **Common Controls** node, and then double-click **Label**.</span></span>

     <span data-ttu-id="6dcd0-130">という名前`label1`のコントロールがデザイナー画面上のコントロールに追加されます。<xref:System.Windows.Forms.Label></span><span class="sxs-lookup"><span data-stu-id="6dcd0-130">A <xref:System.Windows.Forms.Label> control named `label1` is added to your control on the designer surface.</span></span>

3. <span data-ttu-id="6dcd0-131">デザイナーで **[label1]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6dcd0-131">In the designer, click **label1**.</span></span> <span data-ttu-id="6dcd0-132">[プロパティ] ウィンドウで、次のプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="6dcd0-132">In the Properties window, set the following properties.</span></span>

    |<span data-ttu-id="6dcd0-133">プロパティ</span><span class="sxs-lookup"><span data-stu-id="6dcd0-133">Property</span></span>|<span data-ttu-id="6dcd0-134">変更後の値</span><span class="sxs-lookup"><span data-stu-id="6dcd0-134">Change to</span></span>|
    |--------------|---------------|
    |<span data-ttu-id="6dcd0-135">**Name**</span><span class="sxs-lookup"><span data-stu-id="6dcd0-135">**Name**</span></span>|`lblDisplay`|
    |<span data-ttu-id="6dcd0-136">**Text**</span><span class="sxs-lookup"><span data-stu-id="6dcd0-136">**Text**</span></span>|`(blank space)`|
    |<span data-ttu-id="6dcd0-137">**TextAlign**</span><span class="sxs-lookup"><span data-stu-id="6dcd0-137">**TextAlign**</span></span>|`MiddleCenter`|
    |<span data-ttu-id="6dcd0-138">**Font.Size**</span><span class="sxs-lookup"><span data-stu-id="6dcd0-138">**Font.Size**</span></span>|`14`|

4. <span data-ttu-id="6dcd0-139">**ツールボックス**の **[コンポーネント]** ノードを展開し、 **[Timer]** をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="6dcd0-139">In the **Toolbox**, expand the **Components** node, and then double-click **Timer**.</span></span>

     <span data-ttu-id="6dcd0-140">はコンポーネントであるため、実行時に視覚的に表示されることはありません。<xref:System.Windows.Forms.Timer></span><span class="sxs-lookup"><span data-stu-id="6dcd0-140">Because a <xref:System.Windows.Forms.Timer> is a component, it has no visual representation at run time.</span></span> <span data-ttu-id="6dcd0-141">そのため、コントロールと共にデザイナー画面に表示されるのではなく、**コンポーネント デザイナー** (デザイナー画面の下部にあるトレイ) に表示されます。</span><span class="sxs-lookup"><span data-stu-id="6dcd0-141">Therefore, it does not appear with the controls on the designer surface, but rather in the **Component Designer** (a tray at the bottom of the designer surface).</span></span>

5. <span data-ttu-id="6dcd0-142">**コンポーネントデザイナー**で **[timer1]** を<xref:System.Windows.Forms.Timer.Interval%2A>クリックし、プロパティをに`1000` <xref:System.Windows.Forms.Timer.Enabled%2A>設定し、プロパティを`true`に設定します。</span><span class="sxs-lookup"><span data-stu-id="6dcd0-142">In the **Component Designer**, click **timer1**, and then set the <xref:System.Windows.Forms.Timer.Interval%2A> property to `1000` and the <xref:System.Windows.Forms.Timer.Enabled%2A> property to `true`.</span></span>

     <span data-ttu-id="6dcd0-143">プロパティ<xref:System.Windows.Forms.Timer.Interval%2A>は、コンポーネントが<xref:System.Windows.Forms.Timer>ティックする頻度を制御します。</span><span class="sxs-lookup"><span data-stu-id="6dcd0-143">The <xref:System.Windows.Forms.Timer.Interval%2A> property controls the frequency with which the <xref:System.Windows.Forms.Timer> component ticks.</span></span> <span data-ttu-id="6dcd0-144">`timer1` が時を刻むたびに、`timer1_Tick` イベントのコードが実行されます。</span><span class="sxs-lookup"><span data-stu-id="6dcd0-144">Each time `timer1` ticks, it runs the code in the `timer1_Tick` event.</span></span> <span data-ttu-id="6dcd0-145">このプロパティは、タイマーの刻み間隔をミリ秒単位で表します。</span><span class="sxs-lookup"><span data-stu-id="6dcd0-145">The interval represents the number of milliseconds between ticks.</span></span>

6. <span data-ttu-id="6dcd0-146">**コンポーネント デザイナー**で **[timer1]** をダブルクリックして、`ctlClock` の `timer1_Tick` イベントに移動します。</span><span class="sxs-lookup"><span data-stu-id="6dcd0-146">In the **Component Designer**, double-click **timer1** to go to the `timer1_Tick` event for `ctlClock`.</span></span>

7. <span data-ttu-id="6dcd0-147">コードを次のコード サンプルのように変更します。</span><span class="sxs-lookup"><span data-stu-id="6dcd0-147">Modify the code so that it resembles the following code sample.</span></span> <span data-ttu-id="6dcd0-148">アクセス修飾子を `private` から `protected` に必ず変更してください。</span><span class="sxs-lookup"><span data-stu-id="6dcd0-148">Be sure to change the access modifier from `private` to `protected`.</span></span>

    ```csharp
    protected void timer1_Tick(object sender, System.EventArgs e)
    {
        // Causes the label to display the current time.
        lblDisplay.Text = DateTime.Now.ToLongTimeString();
    }
    ```

     <span data-ttu-id="6dcd0-149">このコードにより、現在の時刻が `lblDisplay` に表示されます。</span><span class="sxs-lookup"><span data-stu-id="6dcd0-149">This code will cause the current time to be shown in `lblDisplay`.</span></span> <span data-ttu-id="6dcd0-150">`timer1` の間隔が `1000` に設定されているため、このイベントは 1000 ミリ秒ごとに発生します。したがって、現在の時刻が 1 秒ごとに更新されます。</span><span class="sxs-lookup"><span data-stu-id="6dcd0-150">Because the interval of `timer1` was set to `1000`, this event will occur every thousand milliseconds, thus updating the current time every second.</span></span>

8. <span data-ttu-id="6dcd0-151">`virtual` キーワードを使用して、メソッドをオーバーライド可能に変更します。</span><span class="sxs-lookup"><span data-stu-id="6dcd0-151">Modify the method to be overridable with the `virtual` keyword.</span></span> <span data-ttu-id="6dcd0-152">詳細については、後述の「複合コントロールの継承」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6dcd0-152">For more information, see the  "Inheriting from a User Control" section below.</span></span>

    ```csharp
    protected virtual void timer1_Tick(object sender, System.EventArgs e)
    ```

9. <span data-ttu-id="6dcd0-153">**[ファイル]** メニューの **[すべて保存]** をクリックして、プロジェクトを保存します。</span><span class="sxs-lookup"><span data-stu-id="6dcd0-153">On the **File** menu, click **Save All** to save the project.</span></span>

## <a name="adding-properties-to-the-composite-control"></a><span data-ttu-id="6dcd0-154">複合コントロールへのプロパティの追加</span><span class="sxs-lookup"><span data-stu-id="6dcd0-154">Adding Properties to the Composite Control</span></span>

<span data-ttu-id="6dcd0-155">時計コントロールは<xref:System.Windows.Forms.Label> 、それぞれ独自のプロパティの<xref:System.Windows.Forms.Timer>セットを持つコントロールとコンポーネントをカプセル化するようになりました。</span><span class="sxs-lookup"><span data-stu-id="6dcd0-155">Your clock control now encapsulates a <xref:System.Windows.Forms.Label> control and a <xref:System.Windows.Forms.Timer> component, each with its own set of inherent properties.</span></span> <span data-ttu-id="6dcd0-156">時計コントロールを今後使用するユーザーは、これらのコントロールの個々のプロパティにアクセスすることはできませんが、適切なコード ブロックを記述することで、カスタム プロパティを作成して公開できます。</span><span class="sxs-lookup"><span data-stu-id="6dcd0-156">While the individual properties of these controls will not be accessible to subsequent users of your control, you can create and expose custom properties by writing the appropriate blocks of code.</span></span> <span data-ttu-id="6dcd0-157">次の手順では、ユーザーが背景とテキストの色を変更できるようにするプロパティをコントロールに追加します。</span><span class="sxs-lookup"><span data-stu-id="6dcd0-157">In the following procedure, you will add properties to your control that enable the user to change the color of the background and text.</span></span>

### <a name="to-add-a-property-to-your-composite-control"></a><span data-ttu-id="6dcd0-158">複合コントロールにプロパティを追加するには</span><span class="sxs-lookup"><span data-stu-id="6dcd0-158">To add a property to your composite control</span></span>

1. <span data-ttu-id="6dcd0-159">ソリューション エクスプローラーで、 **[ctlClock.cs]** を右クリックし、 **[コードの表示]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6dcd0-159">In Solution Explorer, right-click **ctlClock.cs**, and then click **View Code**.</span></span>

     <span data-ttu-id="6dcd0-160">コントロールの**コード エディター**が開きます。</span><span class="sxs-lookup"><span data-stu-id="6dcd0-160">The **Code Editor** for your control opens.</span></span>

2. <span data-ttu-id="6dcd0-161">`public partial class ctlClock` ステートメントを探します。</span><span class="sxs-lookup"><span data-stu-id="6dcd0-161">Locate the `public partial class ctlClock` statement.</span></span> <span data-ttu-id="6dcd0-162">左中かっこ (`{)` の下に次のコードを入力します。</span><span class="sxs-lookup"><span data-stu-id="6dcd0-162">Beneath the opening brace (`{)`, type the following code.</span></span>

    ```csharp
    private Color colFColor;
    private Color colBColor;
    ```

     <span data-ttu-id="6dcd0-163">これらのステートメントにより、作成するプロパティの値の格納に使用するプライベート変数が作成されます。</span><span class="sxs-lookup"><span data-stu-id="6dcd0-163">These statements create the private variables that you will use to store the values for the properties you are about to create.</span></span>

3. <span data-ttu-id="6dcd0-164">手順 2. の変数の宣言の下に次のコードを入力します。</span><span class="sxs-lookup"><span data-stu-id="6dcd0-164">Type the following code beneath the variable declarations from step 2.</span></span>

    ```csharp
    // Declares the name and type of the property.
    public Color ClockBackColor
    {
        // Retrieves the value of the private variable colBColor.
        get
        {
            return colBColor;
        }
        // Stores the selected value in the private variable colBColor, and
        // updates the background color of the label control lblDisplay.
        set
        {
            colBColor = value;
            lblDisplay.BackColor = colBColor;
        }
    }
    // Provides a similar set of instructions for the foreground color.
    public Color ClockForeColor
    {
        get
        {
            return colFColor;
        }
        set
        {
            colFColor = value;
            lblDisplay.ForeColor = colFColor;
        }
    }
    ```

     <span data-ttu-id="6dcd0-165">上記のコードは、このコントロールを今後使用するユーザーが、`ClockForeColor` と `ClockBackColor` の 2 つのカスタム プロパティを使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="6dcd0-165">The preceding code makes two custom properties, `ClockForeColor` and `ClockBackColor`, available to subsequent users of this control.</span></span> <span data-ttu-id="6dcd0-166">`get` ステートメントと `set` ステートメントは、プロパティ値を格納および取得できるようにし、そのプロパティに適した機能を実装するコードを提供します。</span><span class="sxs-lookup"><span data-stu-id="6dcd0-166">The `get` and `set` statements provide for storage and retrieval of the property value, as well as code to implement functionality appropriate to the property.</span></span>

4. <span data-ttu-id="6dcd0-167">**[ファイル]** メニューの **[すべて保存]** をクリックして、プロジェクトを保存します。</span><span class="sxs-lookup"><span data-stu-id="6dcd0-167">On the **File** menu, click **Save All** to save the project.</span></span>

## <a name="testing-the-control"></a><span data-ttu-id="6dcd0-168">コントロールのテスト</span><span class="sxs-lookup"><span data-stu-id="6dcd0-168">Testing the Control</span></span>

<span data-ttu-id="6dcd0-169">コントロールはスタンドアロン アプリケーションではないため、コンテナー内でホストする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6dcd0-169">Controls are not stand-alone applications; they must be hosted in a container.</span></span> <span data-ttu-id="6dcd0-170">**UserControl Test Container** でコントロールの実行時の動作をテストし、プロパティを実行します。</span><span class="sxs-lookup"><span data-stu-id="6dcd0-170">Test your control's run-time behavior and exercise its properties with the **UserControl Test Container**.</span></span> <span data-ttu-id="6dcd0-171">詳細については、「[方法 :UserControl](how-to-test-the-run-time-behavior-of-a-usercontrol.md)の実行時の動作をテストします。</span><span class="sxs-lookup"><span data-stu-id="6dcd0-171">For more information, see [How to: Test the Run-Time Behavior of a UserControl](how-to-test-the-run-time-behavior-of-a-usercontrol.md).</span></span>

### <a name="to-test-your-control"></a><span data-ttu-id="6dcd0-172">コントロールをテストするには</span><span class="sxs-lookup"><span data-stu-id="6dcd0-172">To test your control</span></span>

1. <span data-ttu-id="6dcd0-173">F5 キーを押してプロジェクトをビルドし、**UserControl Test Container** でコントロールを実行します。</span><span class="sxs-lookup"><span data-stu-id="6dcd0-173">Press F5 to build the project and run your control in the **UserControl Test Container**.</span></span>

2. <span data-ttu-id="6dcd0-174">テスト コンテナーのプロパティ グリッドで、`ClockBackColor` プロパティを探し、このプロパティを選択してカラー パレットを表示します。</span><span class="sxs-lookup"><span data-stu-id="6dcd0-174">In the test container's property grid, locate the `ClockBackColor` property, and then select the property to display the color palette.</span></span>

3. <span data-ttu-id="6dcd0-175">任意の色をクリックして選択します。</span><span class="sxs-lookup"><span data-stu-id="6dcd0-175">Choose a color by clicking it.</span></span>

     <span data-ttu-id="6dcd0-176">コントロールの背景色が選択した色に変更されます。</span><span class="sxs-lookup"><span data-stu-id="6dcd0-176">The background color of your control changes to the color you selected.</span></span>

4. <span data-ttu-id="6dcd0-177">同様のイベント シーケンスを使用して、`ClockForeColor` プロパティが予想どおりに機能していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="6dcd0-177">Use a similar sequence of events to verify that the `ClockForeColor` property is functioning as expected.</span></span>

     <span data-ttu-id="6dcd0-178">このセクションとこれまでのセクションでは、コンポーネントと Windows コントロールをコードと組み合わせてパッケージ化し、複合コントロールの形でカスタム機能を提供する方法を説明しました。</span><span class="sxs-lookup"><span data-stu-id="6dcd0-178">In this section and the preceding sections, you have seen how components and Windows controls can be combined with code and packaging to provide custom functionality in the form of a composite control.</span></span> <span data-ttu-id="6dcd0-179">また、複合コントロールのプロパティを公開し、完了後にコントロールをテストする方法も説明しました。</span><span class="sxs-lookup"><span data-stu-id="6dcd0-179">You have learned to expose properties in your composite control, and how to test your control after it is complete.</span></span> <span data-ttu-id="6dcd0-180">次のセクションでは、`ctlClock` をベースとして使用して、継承された複合コントロールを作成する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="6dcd0-180">In the next section you will learn how to construct an inherited composite control using `ctlClock` as a base.</span></span>

## <a name="inheriting-from-a-composite-control"></a><span data-ttu-id="6dcd0-181">複合コントロールの継承</span><span class="sxs-lookup"><span data-stu-id="6dcd0-181">Inheriting from a Composite Control</span></span>

<span data-ttu-id="6dcd0-182">これまでのセクションでは、Windows コントロール、コンポーネント、コードを組み合わせて、再利用可能な複合コントロールを作成する方法を説明しました。</span><span class="sxs-lookup"><span data-stu-id="6dcd0-182">In the previous sections, you learned how to combine Windows controls, components, and code into reusable composite controls.</span></span> <span data-ttu-id="6dcd0-183">作成した複合コントロールをベースとして使用して、他のコントロールを作成できます。</span><span class="sxs-lookup"><span data-stu-id="6dcd0-183">Your composite control can now be used as a base upon which other controls can be built.</span></span> <span data-ttu-id="6dcd0-184">基本クラスからクラスを派生するプロセスは "*継承*" と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="6dcd0-184">The process of deriving a class from a base class is called *inheritance*.</span></span> <span data-ttu-id="6dcd0-185">このセクションでは、`ctlAlarmClock` という複合コントロールを作成します。</span><span class="sxs-lookup"><span data-stu-id="6dcd0-185">In this section, you will create a composite control called `ctlAlarmClock`.</span></span> <span data-ttu-id="6dcd0-186">このコントロールは、親コントロールである `ctlClock` から派生します。</span><span class="sxs-lookup"><span data-stu-id="6dcd0-186">This control will be derived from its parent control, `ctlClock`.</span></span> <span data-ttu-id="6dcd0-187">ここでは、親のメソッドをオーバーライドし、新しいメソッドとプロパティを追加して、`ctlClock` の機能を拡張する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="6dcd0-187">You will learn to extend the functionality of `ctlClock` by overriding parent methods and adding new methods and properties.</span></span>

<span data-ttu-id="6dcd0-188">継承されたコントロールを作成するには、まず、親から派生します。</span><span class="sxs-lookup"><span data-stu-id="6dcd0-188">The first step in creating an inherited control is to derive it from its parent.</span></span> <span data-ttu-id="6dcd0-189">これにより、親コントロールのプロパティ、メソッド、グラフィカル特性をすべて備えた新しいコントロールが作成されます。このコントロールをベースとして使用して、新しい機能や変更された機能を追加できます。</span><span class="sxs-lookup"><span data-stu-id="6dcd0-189">This action creates a new control that has all of the properties, methods, and graphical characteristics of the parent control, but can also act as a base for the addition of new or modified functionality.</span></span>

### <a name="to-create-the-inherited-control"></a><span data-ttu-id="6dcd0-190">継承されたコントロールを作成するには</span><span class="sxs-lookup"><span data-stu-id="6dcd0-190">To create the inherited control</span></span>

1. <span data-ttu-id="6dcd0-191">ソリューション エクスプローラーで、 **[ctlClockLib]** を右クリックし、 **[追加]** をポイントして、 **[ユーザー コントロール]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6dcd0-191">In Solution Explorer, right-click **ctlClockLib**, point to **Add**, and then click **User Control**.</span></span>

     <span data-ttu-id="6dcd0-192">**[新しい項目の追加]** ダイアログ ボックスが開きます。</span><span class="sxs-lookup"><span data-stu-id="6dcd0-192">The **Add New Item** dialog box opens.</span></span>

2. <span data-ttu-id="6dcd0-193">**[継承されたユーザー コントロール]** テンプレートを選択します。</span><span class="sxs-lookup"><span data-stu-id="6dcd0-193">Select the **Inherited User Control** template.</span></span>

3. <span data-ttu-id="6dcd0-194">**[名前]** ボックスに「`ctlAlarmClock.cs`」と入力し、 **[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6dcd0-194">In the **Name** box, type `ctlAlarmClock.cs`, and then click **Add**.</span></span>

     <span data-ttu-id="6dcd0-195">**[継承ピッカー]** ダイアログ ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6dcd0-195">The **Inheritance Picker** dialog box appears.</span></span>

4. <span data-ttu-id="6dcd0-196">**[コンポーネント名]** の **[ctlClock]** をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="6dcd0-196">Under **Component Name**, double-click **ctlClock**.</span></span>

5. <span data-ttu-id="6dcd0-197">ソリューション エクスプローラーで、現在のプロジェクトを参照します。</span><span class="sxs-lookup"><span data-stu-id="6dcd0-197">In Solution Explorer, browse through the current projects.</span></span>

    > [!NOTE]
    > <span data-ttu-id="6dcd0-198">現在のプロジェクトに、**ctlAlarmClock.cs** というファイルが追加されています。</span><span class="sxs-lookup"><span data-stu-id="6dcd0-198">A file called **ctlAlarmClock.cs** has been added to the current project.</span></span>

### <a name="adding-the-alarm-properties"></a><span data-ttu-id="6dcd0-199">アラームのプロパティの追加</span><span class="sxs-lookup"><span data-stu-id="6dcd0-199">Adding the Alarm Properties</span></span>

<span data-ttu-id="6dcd0-200">複合コントロールにプロパティを追加する場合と同様に、継承されたコントロールにプロパティを追加します。</span><span class="sxs-lookup"><span data-stu-id="6dcd0-200">Properties are added to an inherited control in the same way they are added to a composite control.</span></span> <span data-ttu-id="6dcd0-201">ここでは、プロパティ宣言の構文を使用して、コントロールに 2 つのプロパティを追加します。`AlarmTime` プロパティは、アラームを鳴らす日時の値を格納し、`AlarmSet` プロパティは、アラームが設定されているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="6dcd0-201">You will now use the property declaration syntax to add two properties to your control: `AlarmTime`, which will store the value of the date and time the alarm is to go off, and `AlarmSet`, which will indicate whether the alarm is set.</span></span>

#### <a name="to-add-properties-to-your-composite-control"></a><span data-ttu-id="6dcd0-202">複合コントロールにプロパティを追加するには</span><span class="sxs-lookup"><span data-stu-id="6dcd0-202">To add properties to your composite control</span></span>

1. <span data-ttu-id="6dcd0-203">ソリューション エクスプローラーで、 **[ctlAlarmClock]** を右クリックし、 **[コードの表示]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6dcd0-203">In Solution Explorer, right-click **ctlAlarmClock**, and then click **View Code**.</span></span>

2. <span data-ttu-id="6dcd0-204">`public class` ステートメントを探します。</span><span class="sxs-lookup"><span data-stu-id="6dcd0-204">Locate the `public class` statement.</span></span> <span data-ttu-id="6dcd0-205">コントロールは `ctlClockLib.ctlClock` から継承されています。</span><span class="sxs-lookup"><span data-stu-id="6dcd0-205">Note that your control inherits from `ctlClockLib.ctlClock`.</span></span> <span data-ttu-id="6dcd0-206">左中かっこ (`{)` ステートメントの下に次のコードを入力します。</span><span class="sxs-lookup"><span data-stu-id="6dcd0-206">Beneath the opening brace (`{)` statement, type the following code.</span></span>

    ```csharp
    private DateTime dteAlarmTime;
    private bool blnAlarmSet;
    // These properties will be declared as public to allow future
    // developers to access them.
    public DateTime AlarmTime
    {
        get
        {
            return dteAlarmTime;
        }
        set
        {
            dteAlarmTime = value;
        }
    }
    public bool AlarmSet
    {
        get
        {
            return blnAlarmSet;
        }
        set
        {
            blnAlarmSet = value;
        }
    }
    ```

### <a name="adding-to-the-graphical-interface-of-the-control"></a><span data-ttu-id="6dcd0-207">コントロールのグラフィカル インターフェイスへの追加</span><span class="sxs-lookup"><span data-stu-id="6dcd0-207">Adding to the Graphical Interface of the Control</span></span>

<span data-ttu-id="6dcd0-208">継承されたコントロールには、継承元のコントロールと同じビジュアル インターフェイスがあります。</span><span class="sxs-lookup"><span data-stu-id="6dcd0-208">Your inherited control has a visual interface that is identical to the control it inherits from.</span></span> <span data-ttu-id="6dcd0-209">継承されたコントロールは親コントロールと同じ内在コントロールを持ちますが、内在コントロールのプロパティは、明確に公開されていない限り使用できません。</span><span class="sxs-lookup"><span data-stu-id="6dcd0-209">It possesses the same constituent controls as its parent control, but the properties of the constituent controls will not be available unless they were specifically exposed.</span></span> <span data-ttu-id="6dcd0-210">複合コントロールに追加する場合と同様に、継承された複合コントロールのグラフィカル インターフェイスに追加できます。</span><span class="sxs-lookup"><span data-stu-id="6dcd0-210">You may add to the graphical interface of an inherited composite control in the same manner as you would add to any composite control.</span></span> <span data-ttu-id="6dcd0-211">引き続き、アラーム時計のビジュアル インターフェイスに、アラームが鳴っているときに点滅するラベル コントロールを追加します。</span><span class="sxs-lookup"><span data-stu-id="6dcd0-211">To continue adding to your alarm clock's visual interface, you will add a label control that will flash when the alarm is sounding.</span></span>

#### <a name="to-add-the-label-control"></a><span data-ttu-id="6dcd0-212">ラベル コントロールを追加するには</span><span class="sxs-lookup"><span data-stu-id="6dcd0-212">To add the label control</span></span>

1. <span data-ttu-id="6dcd0-213">ソリューション エクスプローラーで、 **[ctlAlarmClock]** を右クリックし、 **[デザイナーの表示]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6dcd0-213">In Solution Explorer, right-click **ctlAlarmClock**, and then click **View Designer**.</span></span>

     <span data-ttu-id="6dcd0-214">メイン ウィンドウに、`ctlAlarmClock` のデザイナーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6dcd0-214">The designer for `ctlAlarmClock` opens in the main window.</span></span>

2. <span data-ttu-id="6dcd0-215">コントロールの表示部分をクリックし、[プロパティ] ウィンドウを表示します。</span><span class="sxs-lookup"><span data-stu-id="6dcd0-215">Click the display portion of the control, and view the Properties window.</span></span>

    > [!NOTE]
    > <span data-ttu-id="6dcd0-216">すべてのプロパティが表示されていますが、淡色表示になっています。</span><span class="sxs-lookup"><span data-stu-id="6dcd0-216">While all the properties are displayed, they are dimmed.</span></span> <span data-ttu-id="6dcd0-217">これは、これらのプロパティが `lblDisplay` に対してネイティブであり、[プロパティ] ウィンドウで変更したりアクセスしたりすることはできないことを示しています。</span><span class="sxs-lookup"><span data-stu-id="6dcd0-217">This indicates that these properties are native to `lblDisplay` and cannot be modified or accessed in the Properties window.</span></span> <span data-ttu-id="6dcd0-218">既定では、複合コントロールに含まれているコントロールは `private` であり、どのような方法でもプロパティにはアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="6dcd0-218">By default, controls contained in a composite control are `private`, and their properties are not accessible by any means.</span></span>

    > [!NOTE]
    > <span data-ttu-id="6dcd0-219">複合コントロールを今後使用するユーザーが、その内部のコントロールにアクセスできるようにする場合は、内部のコントロールを `public` または `protected` として宣言します。</span><span class="sxs-lookup"><span data-stu-id="6dcd0-219">If you want subsequent users of your composite control to have access to its internal controls, declare them as `public` or `protected`.</span></span> <span data-ttu-id="6dcd0-220">これにより、適切なコードを使用して、複合コントロールに含まれているコントロールのプロパティの設定や変更が可能になります。</span><span class="sxs-lookup"><span data-stu-id="6dcd0-220">This will allow you to set and modify properties of controls contained within your composite control by using the appropriate code.</span></span>

3. <span data-ttu-id="6dcd0-221">複合コントロールにコントロールを追加します。 <xref:System.Windows.Forms.Label></span><span class="sxs-lookup"><span data-stu-id="6dcd0-221">Add a <xref:System.Windows.Forms.Label> control to your composite control.</span></span>

4. <span data-ttu-id="6dcd0-222">マウスを使用して、 <xref:System.Windows.Forms.Label>コントロールを表示ボックスのすぐ下にドラッグします。</span><span class="sxs-lookup"><span data-stu-id="6dcd0-222">Using the mouse, drag the <xref:System.Windows.Forms.Label> control immediately beneath the display box.</span></span> <span data-ttu-id="6dcd0-223">[プロパティ] ウィンドウで、次のプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="6dcd0-223">In the Properties window, set the following properties.</span></span>

    |<span data-ttu-id="6dcd0-224">プロパティ</span><span class="sxs-lookup"><span data-stu-id="6dcd0-224">Property</span></span>|<span data-ttu-id="6dcd0-225">設定</span><span class="sxs-lookup"><span data-stu-id="6dcd0-225">Setting</span></span>|
    |--------------|-------------|
    |<span data-ttu-id="6dcd0-226">**Name**</span><span class="sxs-lookup"><span data-stu-id="6dcd0-226">**Name**</span></span>|`lblAlarm`|
    |<span data-ttu-id="6dcd0-227">**Text**</span><span class="sxs-lookup"><span data-stu-id="6dcd0-227">**Text**</span></span>|<span data-ttu-id="6dcd0-228">**Alarm!**</span><span class="sxs-lookup"><span data-stu-id="6dcd0-228">**Alarm!**</span></span>|
    |<span data-ttu-id="6dcd0-229">**TextAlign**</span><span class="sxs-lookup"><span data-stu-id="6dcd0-229">**TextAlign**</span></span>|`MiddleCenter`|
    |<span data-ttu-id="6dcd0-230">**Visible**</span><span class="sxs-lookup"><span data-stu-id="6dcd0-230">**Visible**</span></span>|`false`|

### <a name="adding-the-alarm-functionality"></a><span data-ttu-id="6dcd0-231">アラーム機能の追加</span><span class="sxs-lookup"><span data-stu-id="6dcd0-231">Adding the Alarm Functionality</span></span>

<span data-ttu-id="6dcd0-232">前の手順では、複合コントロールでアラーム機能を有効にするためのプロパティとコントロールを追加しました。</span><span class="sxs-lookup"><span data-stu-id="6dcd0-232">In the previous procedures, you added properties and a control that will enable alarm functionality in your composite control.</span></span> <span data-ttu-id="6dcd0-233">この手順では、現在の時刻をアラームの時刻と比較して、2 つの時刻が同じである場合にアラームを点滅させるコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="6dcd0-233">In this procedure, you will add code to compare the current time to the alarm time and, if they are the same, to flash an alarm.</span></span> <span data-ttu-id="6dcd0-234">`ctlClock` の `timer1_Tick` メソッドをオーバーライドし、コードを追加することで、`ctlClock` の固有の機能をすべて保持しながら、`ctlAlarmClock` の機能を拡張します。</span><span class="sxs-lookup"><span data-stu-id="6dcd0-234">By overriding the `timer1_Tick` method of `ctlClock` and adding additional code to it, you will extend the capability of `ctlAlarmClock` while retaining all of the inherent functionality of `ctlClock`.</span></span>

#### <a name="to-override-the-timer1_tick-method-of-ctlclock"></a><span data-ttu-id="6dcd0-235">ctlClock の timer1_Tick メソッドをオーバーライドするには</span><span class="sxs-lookup"><span data-stu-id="6dcd0-235">To override the timer1_Tick method of ctlClock</span></span>

1. <span data-ttu-id="6dcd0-236">**コード エディター**で、`private bool blnAlarmSet;` ステートメントを探します。</span><span class="sxs-lookup"><span data-stu-id="6dcd0-236">In the **Code Editor**, locate the `private bool blnAlarmSet;` statement.</span></span> <span data-ttu-id="6dcd0-237">このステートメントのすぐ下に、次のステートメントを追加します。</span><span class="sxs-lookup"><span data-stu-id="6dcd0-237">Immediately beneath it, add the following statement.</span></span>

    ```csharp
    private bool blnColorTicker;
    ```

2. <span data-ttu-id="6dcd0-238">**コード エディター**で、クラスの末尾にある右中かっこ (`})` を探します。</span><span class="sxs-lookup"><span data-stu-id="6dcd0-238">In the **Code Editor**, locate the closing brace (`})` at the end of the class.</span></span> <span data-ttu-id="6dcd0-239">中かっこの直前に次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="6dcd0-239">Just before the brace, add the following code.</span></span>

    ```csharp
    protected override void timer1_Tick(object sender, System.EventArgs e)
    {
        // Calls the Timer1_Tick method of ctlClock.
        base.timer1_Tick(sender, e);
        // Checks to see if the alarm is set.
        if (AlarmSet == false)
            return;
        else
            // If the date, hour, and minute of the alarm time are the same as
            // the current time, flash an alarm.
        {
            if (AlarmTime.Date == DateTime.Now.Date && AlarmTime.Hour ==
                DateTime.Now.Hour && AlarmTime.Minute == DateTime.Now.Minute)
            {
                // Sets lblAlarmVisible to true, and changes the background color based on
                // the value of blnColorTicker. The background color of the label
                // will flash once per tick of the clock.
                lblAlarm.Visible = true;
                if (blnColorTicker == false)
                {
                    lblAlarm.BackColor = Color.Red;
                    blnColorTicker = true;
                }
                else
                {
                    lblAlarm.BackColor = Color.Blue;
                    blnColorTicker = false;
                }
            }
            else
            {
                // Once the alarm has sounded for a minute, the label is made
                // invisible again.
                lblAlarm.Visible = false;
            }
        }
    }
    ```

     <span data-ttu-id="6dcd0-240">このコードを追加すると、いくつかのタスクが実行されます。</span><span class="sxs-lookup"><span data-stu-id="6dcd0-240">The addition of this code accomplishes several tasks.</span></span> <span data-ttu-id="6dcd0-241">`override` ステートメントは、基本コントロールから継承されたメソッドの代わりに、このメソッドを使用するようコントロールに指示します。</span><span class="sxs-lookup"><span data-stu-id="6dcd0-241">The `override` statement directs the control to use this method in place of the method that was inherited from the base control.</span></span> <span data-ttu-id="6dcd0-242">このメソッドが呼び出されると、メソッドは `base.timer1_Tick` ステートメントを呼び出して、オーバーライドしたメソッドを呼び出します。これにより、元のコントロールに組み込まれたすべての機能がこのコントロールに継承されます。</span><span class="sxs-lookup"><span data-stu-id="6dcd0-242">When this method is called, it calls the method it overrides by invoking the `base.timer1_Tick` statement, ensuring that all of the functionality incorporated in the original control is reproduced in this control.</span></span> <span data-ttu-id="6dcd0-243">その後、メソッドは追加のコードを実行してアラーム機能を組み込みます。</span><span class="sxs-lookup"><span data-stu-id="6dcd0-243">It then runs additional code to incorporate the alarm functionality.</span></span> <span data-ttu-id="6dcd0-244">アラームが発生すると、点滅するラベル コントロールが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6dcd0-244">A flashing label control will appear when the alarm occurs.</span></span>

     <span data-ttu-id="6dcd0-245">これで、アラーム時計コントロールはほぼ完成です。</span><span class="sxs-lookup"><span data-stu-id="6dcd0-245">Your alarm clock control is almost complete.</span></span> <span data-ttu-id="6dcd0-246">あとはアラームを止める方法を実装するだけです。</span><span class="sxs-lookup"><span data-stu-id="6dcd0-246">The only thing that remains is to implement a way to turn it off.</span></span> <span data-ttu-id="6dcd0-247">これを行うには、`lblAlarm_Click` メソッドにコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="6dcd0-247">To do this, you will add code to the `lblAlarm_Click` method.</span></span>

#### <a name="to-implement-the-shutoff-method"></a><span data-ttu-id="6dcd0-248">停止メソッドを実装するには</span><span class="sxs-lookup"><span data-stu-id="6dcd0-248">To implement the shutoff method</span></span>

1. <span data-ttu-id="6dcd0-249">ソリューション エクスプローラーで、 **[ctlAlarmClock.cs]** を右クリックし、 **[デザイナーの表示]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6dcd0-249">In Solution Explorer, right-click **ctlAlarmClock.cs**, and then click **View Designer**.</span></span>

     <span data-ttu-id="6dcd0-250">デザイナーが開きます。</span><span class="sxs-lookup"><span data-stu-id="6dcd0-250">The designer opens.</span></span>

2. <span data-ttu-id="6dcd0-251">コントロールにボタンを追加します。</span><span class="sxs-lookup"><span data-stu-id="6dcd0-251">Add a button to the control.</span></span> <span data-ttu-id="6dcd0-252">ボタンのプロパティを次のように設定します。</span><span class="sxs-lookup"><span data-stu-id="6dcd0-252">Set the properties of the button as follows.</span></span>

    |<span data-ttu-id="6dcd0-253">プロパティ</span><span class="sxs-lookup"><span data-stu-id="6dcd0-253">Property</span></span>|<span data-ttu-id="6dcd0-254">[値]</span><span class="sxs-lookup"><span data-stu-id="6dcd0-254">Value</span></span>|
    |--------------|-----------|
    |<span data-ttu-id="6dcd0-255">**Name**</span><span class="sxs-lookup"><span data-stu-id="6dcd0-255">**Name**</span></span>|`btnAlarmOff`|
    |<span data-ttu-id="6dcd0-256">**Text**</span><span class="sxs-lookup"><span data-stu-id="6dcd0-256">**Text**</span></span>|<span data-ttu-id="6dcd0-257">**Disable Alarm**</span><span class="sxs-lookup"><span data-stu-id="6dcd0-257">**Disable Alarm**</span></span>|

3. <span data-ttu-id="6dcd0-258">デザイナーで **[btnAlarmOff]** をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="6dcd0-258">In the designer, double-click **btnAlarmOff**.</span></span>

     <span data-ttu-id="6dcd0-259">**コード エディター**が開き、`private void btnAlarmOff_Click` 行が表示されます。</span><span class="sxs-lookup"><span data-stu-id="6dcd0-259">The **Code Editor** opens to the `private void btnAlarmOff_Click` line.</span></span>

4. <span data-ttu-id="6dcd0-260">このメソッドを次のコードのように変更します。</span><span class="sxs-lookup"><span data-stu-id="6dcd0-260">Modify this method so that it resembles the following code.</span></span>

    ```csharp
    private void btnAlarmOff_Click(object sender, System.EventArgs e)
    {
        // Turns off the alarm.
        AlarmSet = false;
        // Hides the flashing label.
        lblAlarm.Visible = false;
    }
    ```

5. <span data-ttu-id="6dcd0-261">**[ファイル]** メニューの **[すべて保存]** をクリックして、プロジェクトを保存します。</span><span class="sxs-lookup"><span data-stu-id="6dcd0-261">On the **File** menu, click **Save All** to save the project.</span></span>

### <a name="using-the-inherited-control-on-a-form"></a><span data-ttu-id="6dcd0-262">フォームでの継承されたコントロールの使用</span><span class="sxs-lookup"><span data-stu-id="6dcd0-262">Using the Inherited Control on a Form</span></span>

<span data-ttu-id="6dcd0-263">継承されたコントロールは、基本クラスコントロールを`ctlClock`テストしたときと同じ方法でテストできます。F5 キーを押してプロジェクトをビルドし、**UserControl Test Container** でコントロールを実行します。</span><span class="sxs-lookup"><span data-stu-id="6dcd0-263">You can test your inherited control the same way you tested the base class control, `ctlClock`: Press F5 to build the project and run your control in the **UserControl Test Container**.</span></span> <span data-ttu-id="6dcd0-264">詳細については、「[方法 :UserControl](how-to-test-the-run-time-behavior-of-a-usercontrol.md)の実行時の動作をテストします。</span><span class="sxs-lookup"><span data-stu-id="6dcd0-264">For more information, see [How to: Test the Run-Time Behavior of a UserControl](how-to-test-the-run-time-behavior-of-a-usercontrol.md).</span></span>

<span data-ttu-id="6dcd0-265">コントロールを使用するには、フォーム上でコントロールをホストする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6dcd0-265">To put your control to use, you will need to host it on a form.</span></span> <span data-ttu-id="6dcd0-266">標準の複合コントロールと同様に、継承された複合コントロールをスタンドアロンにすることはできないので、フォームまたは他のコンテナー内でホストする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6dcd0-266">As with a standard composite control, an inherited composite control cannot stand alone and must be hosted in a form or other container.</span></span> <span data-ttu-id="6dcd0-267">`ctlAlarmClock` は機能が拡張されているため、テストするには追加のコードが必要となります。</span><span class="sxs-lookup"><span data-stu-id="6dcd0-267">Since `ctlAlarmClock` has a greater depth of functionality, additional code is required to test it.</span></span> <span data-ttu-id="6dcd0-268">次の手順では、`ctlAlarmClock` の機能をテストするための簡単なプログラムを作成します。</span><span class="sxs-lookup"><span data-stu-id="6dcd0-268">In this procedure, you will write a simple program to test the functionality of `ctlAlarmClock`.</span></span> <span data-ttu-id="6dcd0-269">`ctlAlarmClock` の `AlarmTime` プロパティを設定して表示するコードを記述し、固有の機能をテストします。</span><span class="sxs-lookup"><span data-stu-id="6dcd0-269">You will write code to set and display the `AlarmTime` property of `ctlAlarmClock`, and will test its inherent functions.</span></span>

#### <a name="to-build-and-add-your-control-to-a-test-form"></a><span data-ttu-id="6dcd0-270">コントロールをビルドしてテスト フォームに追加するには</span><span class="sxs-lookup"><span data-stu-id="6dcd0-270">To build and add your control to a test form</span></span>

1. <span data-ttu-id="6dcd0-271">ソリューション エクスプローラーで、 **[ctlClockLib]** を右クリックし、 **[ビルド]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6dcd0-271">In Solution Explorer, right-click **ctlClockLib**, and then click **Build**.</span></span>

2. <span data-ttu-id="6dcd0-272">新しい **Windows アプリケーション** プロジェクトをソリューションに追加し、`Test` という名前を付けます。</span><span class="sxs-lookup"><span data-stu-id="6dcd0-272">Add a new **Windows Application** project to the solution, and name it `Test`.</span></span>

3. <span data-ttu-id="6dcd0-273">ソリューション エクスプローラーで、テスト プロジェクトの **[参照設定]** ノードを右クリックします。</span><span class="sxs-lookup"><span data-stu-id="6dcd0-273">In Solution Explorer, right-click the **References** node for your test project.</span></span> <span data-ttu-id="6dcd0-274">**[参照の追加]** をクリックして、 **[参照の追加]** ダイアログ ボックスを表示します。</span><span class="sxs-lookup"><span data-stu-id="6dcd0-274">Click **Add Reference** to display the **Add Reference** dialog box.</span></span> <span data-ttu-id="6dcd0-275">**[プロジェクト]** というラベルのタブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="6dcd0-275">Click the tab labeled **Projects**.</span></span> <span data-ttu-id="6dcd0-276">**[プロジェクト名]** に `ctlClockLib` プロジェクトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6dcd0-276">Your `ctlClockLib` project will be listed under **Project Name**.</span></span> <span data-ttu-id="6dcd0-277">プロジェクトをダブルクリックして、テスト プロジェクトへの参照を追加します。</span><span class="sxs-lookup"><span data-stu-id="6dcd0-277">Double-click the project to add the reference to the test project.</span></span>

4. <span data-ttu-id="6dcd0-278">ソリューション エクスプローラーで、 **[Test]** を右クリックし、 **[ビルド]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6dcd0-278">In Solution Explorer, right-click **Test**, and then click **Build**.</span></span>

5. <span data-ttu-id="6dcd0-279">**ツールボックス**で、 **[ctlClockLib コンポーネント]** ノードを展開します。</span><span class="sxs-lookup"><span data-stu-id="6dcd0-279">In the **Toolbox**, expand the **ctlClockLib Components** node.</span></span>

6. <span data-ttu-id="6dcd0-280">**[ctlAlarmClock]** をダブルクリックして、`ctlAlarmClock` のコピーをフォームに追加します。</span><span class="sxs-lookup"><span data-stu-id="6dcd0-280">Double-click **ctlAlarmClock** to add a copy of `ctlAlarmClock` to your form.</span></span>

7. <span data-ttu-id="6dcd0-281">**ツールボックス**で、 **[DateTimePicker]** を見つけてダブルクリックし<xref:System.Windows.Forms.DateTimePicker> 、フォームにコントロールを追加します。 <xref:System.Windows.Forms.Label>次に、 **[ラベル]** をダブルクリックしてコントロールを追加します。</span><span class="sxs-lookup"><span data-stu-id="6dcd0-281">In the **Toolbox**, locate and double-click **DateTimePicker** to add a <xref:System.Windows.Forms.DateTimePicker> control to your form, and then add a <xref:System.Windows.Forms.Label> control by double-clicking **Label**.</span></span>

8. <span data-ttu-id="6dcd0-282">マウスを使用して、各コントロールをフォーム上の使いやすい場所に配置します。</span><span class="sxs-lookup"><span data-stu-id="6dcd0-282">Use the mouse to position the controls in a convenient place on the form.</span></span>

9. <span data-ttu-id="6dcd0-283">これらのコントロールのプロパティを次のように設定します。</span><span class="sxs-lookup"><span data-stu-id="6dcd0-283">Set the properties of these controls in the following manner.</span></span>

    |<span data-ttu-id="6dcd0-284">コントロール</span><span class="sxs-lookup"><span data-stu-id="6dcd0-284">Control</span></span>|<span data-ttu-id="6dcd0-285">プロパティ</span><span class="sxs-lookup"><span data-stu-id="6dcd0-285">Property</span></span>|<span data-ttu-id="6dcd0-286">[値]</span><span class="sxs-lookup"><span data-stu-id="6dcd0-286">Value</span></span>|
    |-------------|--------------|-----------|
    |`label1`|<span data-ttu-id="6dcd0-287">**Text**</span><span class="sxs-lookup"><span data-stu-id="6dcd0-287">**Text**</span></span>|`(blank space)`|
    ||<span data-ttu-id="6dcd0-288">**Name**</span><span class="sxs-lookup"><span data-stu-id="6dcd0-288">**Name**</span></span>|`lblTest`|
    |`dateTimePicker1`|<span data-ttu-id="6dcd0-289">**Name**</span><span class="sxs-lookup"><span data-stu-id="6dcd0-289">**Name**</span></span>|`dtpTest`|
    ||<span data-ttu-id="6dcd0-290">**Format**</span><span class="sxs-lookup"><span data-stu-id="6dcd0-290">**Format**</span></span>|<xref:System.Windows.Forms.DateTimePickerFormat.Time>|

10. <span data-ttu-id="6dcd0-291">デザイナーで **[dtpTest]** をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="6dcd0-291">In the designer, double-click **dtpTest**.</span></span>

     <span data-ttu-id="6dcd0-292">**コード エディター**が開き、`private void dtpTest_ValueChanged` が表示されます。</span><span class="sxs-lookup"><span data-stu-id="6dcd0-292">The **Code Editor** opens to `private void dtpTest_ValueChanged`.</span></span>

11. <span data-ttu-id="6dcd0-293">コードを次のように変更します。</span><span class="sxs-lookup"><span data-stu-id="6dcd0-293">Modify the code so that it resembles the following.</span></span>

    ```csharp
    private void dtpTest_ValueChanged(object sender, System.EventArgs e)
    {
        ctlAlarmClock1.AlarmTime = dtpTest.Value;
        ctlAlarmClock1.AlarmSet = true;
        lblTest.Text = "Alarm Time is " +
            ctlAlarmClock1.AlarmTime.ToShortTimeString();
    }
    ```

12. <span data-ttu-id="6dcd0-294">ソリューション エクスプローラーで、 **[Test]** を右クリックし、 **[スタートアップ プロジェクトに設定]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6dcd0-294">In Solution Explorer, right-click **Test**, and then click **Set as StartUp Project**.</span></span>

13. <span data-ttu-id="6dcd0-295">**[デバッグ]** メニューの **[デバッグの開始]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6dcd0-295">On the **Debug** menu, click **Start Debugging**.</span></span>

     <span data-ttu-id="6dcd0-296">テスト プログラムが起動します。</span><span class="sxs-lookup"><span data-stu-id="6dcd0-296">The test program starts.</span></span> <span data-ttu-id="6dcd0-297">`ctlAlarmClock`コントロールで現在の時刻が更新され、 <xref:System.Windows.Forms.DateTimePicker>コントロールに開始時刻が表示されていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="6dcd0-297">Note that the current time is updated in the `ctlAlarmClock` control, and that the starting time is shown in the <xref:System.Windows.Forms.DateTimePicker> control.</span></span>

14. <span data-ttu-id="6dcd0-298">時間の<xref:System.Windows.Forms.DateTimePicker>分を表示するをクリックします。</span><span class="sxs-lookup"><span data-stu-id="6dcd0-298">Click the <xref:System.Windows.Forms.DateTimePicker> where the minutes of the hour are displayed.</span></span>

15. <span data-ttu-id="6dcd0-299">キーボードを使用して、`ctlAlarmClock` に表示されている現在の時刻の 1 分後の値を設定します。</span><span class="sxs-lookup"><span data-stu-id="6dcd0-299">Using the keyboard, set a value for minutes that is one minute greater than the current time shown by `ctlAlarmClock`.</span></span>

     <span data-ttu-id="6dcd0-300">アラーム設定の時刻が `lblTest` に表示されます。</span><span class="sxs-lookup"><span data-stu-id="6dcd0-300">The time for the alarm setting is shown in `lblTest`.</span></span> <span data-ttu-id="6dcd0-301">表示時刻がアラーム設定時刻になるまで待ちます。</span><span class="sxs-lookup"><span data-stu-id="6dcd0-301">Wait for the displayed time to reach the alarm setting time.</span></span> <span data-ttu-id="6dcd0-302">表示時刻がアラーム設定時刻になると、`lblAlarm` が点滅します。</span><span class="sxs-lookup"><span data-stu-id="6dcd0-302">When the displayed time reaches the time to which the alarm is set, the `lblAlarm` will flash.</span></span>

16. <span data-ttu-id="6dcd0-303">`btnAlarmOff` をクリックしてアラームを止めます。</span><span class="sxs-lookup"><span data-stu-id="6dcd0-303">Turn off the alarm by clicking `btnAlarmOff`.</span></span> <span data-ttu-id="6dcd0-304">これでアラームをリセットできます。</span><span class="sxs-lookup"><span data-stu-id="6dcd0-304">You may now reset the alarm.</span></span>

     <span data-ttu-id="6dcd0-305">このチュートリアルでは、多数の重要な概念を取り上げました。</span><span class="sxs-lookup"><span data-stu-id="6dcd0-305">This walkthrough has covered a number of key concepts.</span></span> <span data-ttu-id="6dcd0-306">コントロールとコンポーネントを複合コントロール コンテナーに組み込んで複合コントロールを作成する方法を説明しました。</span><span class="sxs-lookup"><span data-stu-id="6dcd0-306">You have learned to create a composite control by combining controls and components into a composite control container.</span></span> <span data-ttu-id="6dcd0-307">また、コントロールにプロパティを追加する方法と、カスタム機能を実装するコードを記述する方法も説明しました。</span><span class="sxs-lookup"><span data-stu-id="6dcd0-307">You have learned to add properties to your control, and to write code to implement custom functionality.</span></span> <span data-ttu-id="6dcd0-308">最後のセクションでは、継承によって特定の複合コントロールの機能を拡張する方法と、ホスト メソッドをオーバーライドすることでメソッドの機能を変更する方法を説明しました。</span><span class="sxs-lookup"><span data-stu-id="6dcd0-308">In the last section, you learned to extend the functionality of a given composite control through inheritance, and to alter the functionality of host methods by overriding those methods.</span></span>

## <a name="see-also"></a><span data-ttu-id="6dcd0-309">関連項目</span><span class="sxs-lookup"><span data-stu-id="6dcd0-309">See also</span></span>

- [<span data-ttu-id="6dcd0-310">さまざまなカスタム コントロール</span><span class="sxs-lookup"><span data-stu-id="6dcd0-310">Varieties of Custom Controls</span></span>](varieties-of-custom-controls.md)
- <span data-ttu-id="6dcd0-311">[方法: [ツールボックスアイテムの選択] ダイアログボックスにコントロールを表示する](how-to-display-a-control-in-the-choose-toolbox-items-dialog-box.md)</span><span class="sxs-lookup"><span data-stu-id="6dcd0-311">[How to: Display a Control in the Choose Toolbox Items Dialog Box](how-to-display-a-control-in-the-choose-toolbox-items-dialog-box.md)</span></span>
- [<span data-ttu-id="6dcd0-312">チュートリアル: ビジュアルを使用した Windows フォームコントロールからの継承C#</span><span class="sxs-lookup"><span data-stu-id="6dcd0-312">Walkthrough: Inheriting from a Windows Forms Control with Visual C#</span></span>](walkthrough-inheriting-from-a-windows-forms-control-with-visual-csharp.md)
