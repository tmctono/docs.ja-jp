---
title: 'タスク 1: 新しい Windows Presentation Foundation アプリケーションの作成'
ms.date: 03/30/2017
ms.assetid: 270eaeba-9492-4532-af9f-403ce5c9935b
ms.openlocfilehash: 3205840da575041b449eb841fc8084e89937fca7
ms.sourcegitcommit: 10db6551ea3c971470cf5d2cc21ba1cbcefe5c55
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/08/2019
ms.locfileid: "72031894"
---
# <a name="task-1-create-a-new-windows-presentation-foundation-application"></a><span data-ttu-id="2b4f8-102">タスク 1: 新しい Windows Presentation Foundation アプリケーションの作成</span><span class="sxs-lookup"><span data-stu-id="2b4f8-102">Task 1: Create a New Windows Presentation Foundation Application</span></span>

<span data-ttu-id="2b4f8-103">このタスクでは、WPF Application Visual Studio テンプレートを使用して空の Windows Presentation Foundation (WPF) アプリケーションを作成し、適切な [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] ワークフローアセンブリに参照を追加します。</span><span class="sxs-lookup"><span data-stu-id="2b4f8-103">In this task, you will create an empty Windows Presentation Foundation (WPF) application by using the WPF Application Visual Studio template and add references to the appropriate [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] workflow assemblies.</span></span>  
  
## <a name="to-create-the-wpf-application-project"></a><span data-ttu-id="2b4f8-104">WPF アプリケーション プロジェクトを作成するには</span><span class="sxs-lookup"><span data-stu-id="2b4f8-104">To create the WPF Application project</span></span>

1. <span data-ttu-id="2b4f8-105">Visual Studio を開き、 **[ファイル]** メニューの **[新規作成]** をポイントし、 **[プロジェクト]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2b4f8-105">Open Visual Studio and on the **File** menu, point to **New**, and then click **Project**.</span></span>

2. <span data-ttu-id="2b4f8-106">**[新しいプロジェクト]** ダイアログボックスの左側の **[インストールされているテンプレート]** ペインで、 **[ C#ビジュアル]** または **[Visual Basic]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="2b4f8-106">In the **New Project** dialog box, select either **Visual C#** or **Visual Basic** from the **Installed Templates** pane on the left side of the box.</span></span> <span data-ttu-id="2b4f8-107">選択した言語が表示されない場合は、 **[その他の言語]** を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2b4f8-107">If the language of your choice does not appear, look under **Other Languages**.</span></span>

3. <span data-ttu-id="2b4f8-108">**[インストールさ]** れたテンプレート ペインで **[Windows]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="2b4f8-108">Select **Windows** in the **Installed Templates** pane.</span></span>

4. <span data-ttu-id="2b4f8-109">上部のウィンドウで、ドロップダウンリストボックスで (既定値) **.NET Framework 4**が選択されていることを確認し、 **[WPF アプリケーション]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="2b4f8-109">In the top pane, confirm that (the default value) **.NET Framework 4** has been selected in the drop-down list box, and then select **WPF Application**.</span></span>

5. <span data-ttu-id="2b4f8-110">ウィンドウの下部にあるプロジェクトの名前を**HostingApplication**に設定します。</span><span class="sxs-lookup"><span data-stu-id="2b4f8-110">Set the name of the project to **HostingApplication** at the bottom of the window.</span></span>

6. <span data-ttu-id="2b4f8-111">ソリューション名を**RehostingTheDesigner**に設定します。</span><span class="sxs-lookup"><span data-stu-id="2b4f8-111">Set the solution name to **RehostingTheDesigner**.</span></span>

7. <span data-ttu-id="2b4f8-112">[ **OK]** をクリックして、アプリケーションプロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="2b4f8-112">Click **OK** to create the application project.</span></span> <span data-ttu-id="2b4f8-113">Visual Studio では、アプリケーション用の基本的な WPF UI が作成され、適切な XAML と分離コードファイルが含まれます。</span><span class="sxs-lookup"><span data-stu-id="2b4f8-113">Visual Studio creates a basic WPF UI for your application and includes the appropriate XAML and code-behind files.</span></span>

8. <span data-ttu-id="2b4f8-114">**Workflowmodel**アセンブリへの参照を追加します。</span><span class="sxs-lookup"><span data-stu-id="2b4f8-114">Add references to **WorkflowModel** assemblies.</span></span> <span data-ttu-id="2b4f8-115">これを行うには、**ソリューションエクスプローラー**で**HostingApplication**プロジェクトを右クリックし、 **[参照の追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="2b4f8-115">To do this, in **Solution Explorer**, right-click the **HostingApplication** project and select **Add Reference**.</span></span>

9. <span data-ttu-id="2b4f8-116">**[参照の追加]** ダイアログボックスで、 **[.net]** タブをクリックし、CTRL キーを押しながら次のアセンブリを選択し、 **[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2b4f8-116">In the **Add Reference** dialog box, click the **.NET** tab, hold down the CTRL key, select the following assemblies, and then click **OK**:</span></span>

    - <span data-ttu-id="2b4f8-117">System.Activities</span><span class="sxs-lookup"><span data-stu-id="2b4f8-117">System.Activities</span></span>
    - <span data-ttu-id="2b4f8-118">System.Activities.Presentation</span><span class="sxs-lookup"><span data-stu-id="2b4f8-118">System.Activities.Presentation</span></span>
    - <span data-ttu-id="2b4f8-119">System.Activities.Core.Presentation</span><span class="sxs-lookup"><span data-stu-id="2b4f8-119">System.Activities.Core.Presentation</span></span>

10. <span data-ttu-id="2b4f8-120">ワークフローデザイナーデザインキャンバスをホストする方法については[、「タスク 2: ワークフローデザイナーのホスト](task-2-host-the-workflow-designer.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2b4f8-120">See [Task 2: Host the Workflow Designer](task-2-host-the-workflow-designer.md) to learn how to host the workflow designer design canvas.</span></span>

## <a name="see-also"></a><span data-ttu-id="2b4f8-121">参照</span><span class="sxs-lookup"><span data-stu-id="2b4f8-121">See also</span></span>

- [<span data-ttu-id="2b4f8-122">ワークフロー デザイナーのホスト変更</span><span class="sxs-lookup"><span data-stu-id="2b4f8-122">Rehosting the Workflow Designer</span></span>](rehosting-the-workflow-designer.md)
- [<span data-ttu-id="2b4f8-123">タスク 2: ワークフロー デザイナーのホスティング</span><span class="sxs-lookup"><span data-stu-id="2b4f8-123">Task 2: Host the Workflow Designer</span></span>](task-2-host-the-workflow-designer.md)
