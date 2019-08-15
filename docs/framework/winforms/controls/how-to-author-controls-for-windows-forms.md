---
title: '方法: Windows フォームのコントロールを作成する'
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], creating
- UserControl class [Windows Forms], Windows Forms
- custom controls [Windows Forms], creating
ms.assetid: 7570e982-545b-4c3a-a7c7-55581d313400
ms.openlocfilehash: 0804b9824b84a32bdd79c763031a3de4ffa54099
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/15/2019
ms.locfileid: "69039876"
---
# <a name="how-to-author-controls-for-windows-forms"></a><span data-ttu-id="a814b-102">方法: Windows フォームのコントロールを作成する</span><span class="sxs-lookup"><span data-stu-id="a814b-102">How to: Author Controls for Windows Forms</span></span>

<span data-ttu-id="a814b-103">コントロールは、ユーザーとプログラムの間のグラフィカルなリンクを表します。</span><span class="sxs-lookup"><span data-stu-id="a814b-103">A control represents a graphical link between the user and the program.</span></span> <span data-ttu-id="a814b-104">コントロールは、データの提供または処理、ユーザー入力の受け付け、イベントへの応答、ユーザーとアプリケーションを接続する他の任意の数の関数の実行を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="a814b-104">A control can provide or process data, accept user input, respond to events, or perform any number of other functions that connect the user and the application.</span></span> <span data-ttu-id="a814b-105">コントロールは、基本的にグラフィカル インターフェイスを持つコンポーネントであるため、ユーザーとの対話だけでなく、コンポーネントが実行するあらゆる機能を果たします。</span><span class="sxs-lookup"><span data-stu-id="a814b-105">Because a control is essentially a component with a graphical interface, it can serve any function that a component does, as well as provide user interaction.</span></span> <span data-ttu-id="a814b-106">コントロールは特定の目的に使用するために作成します。コントロールの作成は、まったく別のプログラミング タスクです。</span><span class="sxs-lookup"><span data-stu-id="a814b-106">Controls are created to serve specific purposes, and authoring controls is just another programming task.</span></span> <span data-ttu-id="a814b-107">このことを念頭に、次の手順では、コントロールの作成手順の概要を示します。</span><span class="sxs-lookup"><span data-stu-id="a814b-107">With that in mind, the following steps represent an overview of the control authoring process.</span></span> <span data-ttu-id="a814b-108">個々の手順のリンクで追加情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="a814b-108">Links provide additional information on the individual steps.</span></span>

> [!NOTE]
> <span data-ttu-id="a814b-109">Web フォームで使用するカスタム コントロールを作成する場合は、「[カスタム ASP.NET サーバー コントロールの開発](https://docs.microsoft.com/previous-versions/aspnet/zt27tfhy(v=vs.100))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a814b-109">If you want to author a custom control to use on Web Forms, see [Developing Custom ASP.NET Server Controls](https://docs.microsoft.com/previous-versions/aspnet/zt27tfhy(v=vs.100)).</span></span>

## <a name="to-author-a-control"></a><span data-ttu-id="a814b-110">コントロールを作成するには</span><span class="sxs-lookup"><span data-stu-id="a814b-110">To author a control</span></span>

1. <span data-ttu-id="a814b-111">コントロールで何を実行するか、またはアプリケーション内のどのような役割を果たすかを決定します。</span><span class="sxs-lookup"><span data-stu-id="a814b-111">Determine what you want your control to accomplish, or what part it will play in your application.</span></span> <span data-ttu-id="a814b-112">考慮すべき要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="a814b-112">Factors to consider are:</span></span>

    - <span data-ttu-id="a814b-113">どのようなグラフィカル インターフェイスが必要か。</span><span class="sxs-lookup"><span data-stu-id="a814b-113">What kind of graphical interface do you need?</span></span>

    - <span data-ttu-id="a814b-114">このコントロールでユーザーとの間で具体的にどのような対話を処理するか。</span><span class="sxs-lookup"><span data-stu-id="a814b-114">What specific user interactions will this control handle?</span></span>

    - <span data-ttu-id="a814b-115">必要とする機能が既存のコントロールによって提供されるかどうか。</span><span class="sxs-lookup"><span data-stu-id="a814b-115">Is the functionality you need provided by any existing controls?</span></span>

    - <span data-ttu-id="a814b-116">複数の Windows フォーム コントロールを組み合わせることによって必要とする機能を実現できるかどうか。</span><span class="sxs-lookup"><span data-stu-id="a814b-116">Can you get the functionality you need by combining several Windows Forms controls?</span></span>

2. <span data-ttu-id="a814b-117">コントロール用にオブジェクト モデルが必要な場合は、オブジェクト モデル全体に機能を配布する方法を決定し、コントロールと下位オブジェクトの間で機能を分割します。</span><span class="sxs-lookup"><span data-stu-id="a814b-117">If you need an object model for your control, determine how functionality will be distributed throughout the object model, and divide up functionality between the control and any subobjects.</span></span> <span data-ttu-id="a814b-118">複合コントロールを計画している場合や、複数の機能を組み込む場合は、オブジェクト モデルが役立つ可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a814b-118">An object model may be useful if you are planning a complex control, or want to incorporate several functionalities.</span></span>

3. <span data-ttu-id="a814b-119">必要なコントロールの種類 (ユーザー コントロール、カスタム コントロール、継承された Windows フォーム コントロールなど) を特定します。</span><span class="sxs-lookup"><span data-stu-id="a814b-119">Determine the type of control (for example, user control, custom control, inherited Windows Forms control) you need.</span></span> <span data-ttu-id="a814b-120">詳細については、「[コントロールの種類に関するアドバイス](control-type-recommendations.md)」と「[さまざまなカスタム コントロール](varieties-of-custom-controls.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a814b-120">For details, see [Control Type Recommendations](control-type-recommendations.md) and [Varieties of Custom Controls](varieties-of-custom-controls.md).</span></span>

4. <span data-ttu-id="a814b-121">機能をプロパティ、メソッド、およびコントロールとその下位オブジェクトまたは従属構造体のイベントとして表現し、適切なアクセス レベル (たとえば、public、protected など) を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="a814b-121">Express functionality as properties, methods, and events of the control and its subobjects or subsidiary structures, and assign appropriate access levels (for example, public, protected, and so on).</span></span>

5. <span data-ttu-id="a814b-122">コントロールのカスタム描画が必要な場合は、そのコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="a814b-122">If you need custom painting for your control, add code for it.</span></span> <span data-ttu-id="a814b-123">詳細については、「[コントロールのカスタム描画およびレンダリング](custom-control-painting-and-rendering.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a814b-123">For details, see [Custom Control Painting and Rendering](custom-control-painting-and-rendering.md).</span></span>

6. <span data-ttu-id="a814b-124">コントロールがから<xref:System.Windows.Forms.UserControl>継承されている場合は、コントロールプロジェクトをビルドし、 **UserControl テストコンテナー**で実行することによって、実行時の動作をテストできます。</span><span class="sxs-lookup"><span data-stu-id="a814b-124">If your control inherits from <xref:System.Windows.Forms.UserControl>, you can test its runtime behavior by building the control project and running it in the **UserControl Test Container**.</span></span> <span data-ttu-id="a814b-125">詳細については、「[方法 :UserControl](how-to-test-the-run-time-behavior-of-a-usercontrol.md)の実行時の動作をテストします。</span><span class="sxs-lookup"><span data-stu-id="a814b-125">For more information, see [How to: Test the Run-Time Behavior of a UserControl](how-to-test-the-run-time-behavior-of-a-usercontrol.md).</span></span>

7. <span data-ttu-id="a814b-126">Windows アプリケーションなどの新しいプロジェクトを作成してコンテナーに配置することで、コントロールをテストしてデバッグすることができます。</span><span class="sxs-lookup"><span data-stu-id="a814b-126">You can also test and debug your control by creating a new project, such as a Windows Application, and placing it into a container.</span></span> <span data-ttu-id="a814b-127">このプロセスは、チュートリアルの[一部として示されています。Visual Basic](walkthrough-authoring-a-composite-control-with-visual-basic.md)による複合コントロールの作成。</span><span class="sxs-lookup"><span data-stu-id="a814b-127">This process is demonstrated as part of [Walkthrough: Authoring a Composite Control with Visual Basic](walkthrough-authoring-a-composite-control-with-visual-basic.md).</span></span>

8. <span data-ttu-id="a814b-128">各機能を追加するときは、テスト プロジェクトに機能を追加して新しい機能を実行します。</span><span class="sxs-lookup"><span data-stu-id="a814b-128">As you add each feature, add features to your test project to exercise the new functionality.</span></span>

9. <span data-ttu-id="a814b-129">繰り返して、デザインを調整します。</span><span class="sxs-lookup"><span data-stu-id="a814b-129">Repeat, refining the design.</span></span>

10. <span data-ttu-id="a814b-130">コントロールをパッケージ化してデプロイします。</span><span class="sxs-lookup"><span data-stu-id="a814b-130">Package and deploy your control.</span></span> <span data-ttu-id="a814b-131">詳細については、「 [Visual Studio での配置の概要](/visualstudio/deployment/deploying-applications-services-and-components)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a814b-131">For details, see [First look at deployment in Visual Studio](/visualstudio/deployment/deploying-applications-services-and-components).</span></span>

## <a name="see-also"></a><span data-ttu-id="a814b-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="a814b-132">See also</span></span>

- [<span data-ttu-id="a814b-133">チュートリアル: Visual Basic による複合コントロールの作成</span><span class="sxs-lookup"><span data-stu-id="a814b-133">Walkthrough: Authoring a Composite Control with Visual Basic</span></span>](walkthrough-authoring-a-composite-control-with-visual-basic.md)
- [<span data-ttu-id="a814b-134">チュートリアル: Visual Basic を使用した Windows フォームコントロールからの継承</span><span class="sxs-lookup"><span data-stu-id="a814b-134">Walkthrough: Inheriting from a Windows Forms Control with Visual Basic</span></span>](walkthrough-inheriting-from-a-windows-forms-control-with-visual-basic.md)
- [<span data-ttu-id="a814b-135">方法: UserControl クラスを継承する</span><span class="sxs-lookup"><span data-stu-id="a814b-135">How to: Inherit from the UserControl Class</span></span>](how-to-inherit-from-the-usercontrol-class.md)
- [<span data-ttu-id="a814b-136">方法: コントロールクラスから継承する</span><span class="sxs-lookup"><span data-stu-id="a814b-136">How to: Inherit from the Control Class</span></span>](how-to-inherit-from-the-control-class.md)
- [<span data-ttu-id="a814b-137">方法: 既存の Windows フォームコントロールから継承する</span><span class="sxs-lookup"><span data-stu-id="a814b-137">How to: Inherit from Existing Windows Forms Controls</span></span>](how-to-inherit-from-existing-windows-forms-controls.md)
- [<span data-ttu-id="a814b-138">方法: UserControl の実行時の動作をテストする</span><span class="sxs-lookup"><span data-stu-id="a814b-138">How to: Test the Run-Time Behavior of a UserControl</span></span>](how-to-test-the-run-time-behavior-of-a-usercontrol.md)
- [<span data-ttu-id="a814b-139">さまざまなカスタム コントロール</span><span class="sxs-lookup"><span data-stu-id="a814b-139">Varieties of Custom Controls</span></span>](varieties-of-custom-controls.md)
