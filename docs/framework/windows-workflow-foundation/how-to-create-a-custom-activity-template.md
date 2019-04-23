---
title: '方法: カスタム アクティビティ テンプレートを作成する'
ms.date: 03/30/2017
ms.assetid: 6760a5cc-6eb8-465f-b4fa-f89b39539429
ms.openlocfilehash: ee6f249092c5cf8643e3c9bfd15d32e77791d8bb
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59295849"
---
# <a name="how-to-create-a-custom-activity-template"></a><span data-ttu-id="b9110-102">方法: カスタム アクティビティ テンプレートを作成する</span><span class="sxs-lookup"><span data-stu-id="b9110-102">How to: Create a Custom Activity Template</span></span>

<span data-ttu-id="b9110-103">カスタム複合アクティビティなどのアクティビティの構成のカスタマイズには、カスタム アクティビティ テンプレートが使用されるため、手動で各アクティビティを個別に作成し、そのプロパティおよびその他の設定を構成する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="b9110-103">Custom activity templates are used to customize the configuration of activities, including custom composite activities, so that users do not have to create each activity individually and configure their properties and other settings manually.</span></span> <span data-ttu-id="b9110-104">これらのカスタム テンプレートで使用できる、**ツールボックス**上、[!INCLUDE[wfd1](../../../includes/wfd1-md.md)]または元のユーザーに画面にドラッグできる、構成済みのデザイン、再ホストされたデザイナーから。</span><span class="sxs-lookup"><span data-stu-id="b9110-104">These custom templates can be made available in the **Toolbox** on the [!INCLUDE[wfd1](../../../includes/wfd1-md.md)] or from a rehosted designer, from which users can drag them onto the preconfigured design surface.</span></span> [!INCLUDE[wfd2](../../../includes/wfd2-md.md)] <span data-ttu-id="b9110-105">このようなテンプレートの良い例が付属しています。 [SendAndReceiveReply テンプレート デザイナー](/visualstudio/workflow-designer/sendandreceivereply-template-designer)と[ReceiveAndSendReply テンプレート デザイナー](/visualstudio/workflow-designer/receiveandsendreply-template-designer)で、[メッセージング アクティビティ デザイナー](/visualstudio/workflow-designer/messaging-activity-designers)カテゴリ。</span><span class="sxs-lookup"><span data-stu-id="b9110-105">ships with good examples of such templates: the [SendAndReceiveReply Template Designer](/visualstudio/workflow-designer/sendandreceivereply-template-designer) and the [ReceiveAndSendReply Template Designer](/visualstudio/workflow-designer/receiveandsendreply-template-designer) in the [Messaging Activity Designers](/visualstudio/workflow-designer/messaging-activity-designers) category.</span></span>

 <span data-ttu-id="b9110-106">このトピックの最初の手順についてのカスタム アクティビティ テンプレートを作成する方法を説明します、**遅延**アクティビティと 2 番目の手順で使用できるようにする方法ではについて簡単に説明を[!INCLUDE[wfd2](../../../includes/wfd2-md.md)]カスタム テンプレートが機能することを確認します。</span><span class="sxs-lookup"><span data-stu-id="b9110-106">The first procedure in this topic describes how to create a custom activity template for a **Delay** activity and the second procedure describes briefly how to make it available in a [!INCLUDE[wfd2](../../../includes/wfd2-md.md)] to verify that the custom template works.</span></span>

 <span data-ttu-id="b9110-107">カスタム アクティビティ テンプレートに <xref:System.Activities.Presentation.IActivityTemplateFactory> を実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b9110-107">Custom activity templates must implement the <xref:System.Activities.Presentation.IActivityTemplateFactory>.</span></span> <span data-ttu-id="b9110-108">このインターフェイスには単一の <xref:System.Activities.Presentation.IActivityTemplateFactory.Create%2A> メソッドがあり、このメソッドを使用して、テンプレートで使用されるアクティビティ インスタンスを作成および構成できます。</span><span class="sxs-lookup"><span data-stu-id="b9110-108">The interface has a single <xref:System.Activities.Presentation.IActivityTemplateFactory.Create%2A> method with which you can create and configure the activity instances used in the template.</span></span>

## <a name="to-create-a-template-for-the-delay-activity"></a><span data-ttu-id="b9110-109">Delay アクティビティのテンプレートを作成するには</span><span class="sxs-lookup"><span data-stu-id="b9110-109">To create a template for the Delay activity</span></span>

1. <span data-ttu-id="b9110-110">Visual Studio 2010 を起動します。</span><span class="sxs-lookup"><span data-stu-id="b9110-110">Start Visual Studio 2010.</span></span>

2. <span data-ttu-id="b9110-111">**[ファイル]** メニューの **[新規作成]** をポイントし、**[プロジェクト]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b9110-111">On the **File** menu, point to **New**, and then select **Project**.</span></span>

     <span data-ttu-id="b9110-112">**[新しいプロジェクト]** ダイアログ ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b9110-112">The **New Project** dialog box opens.</span></span>

3. <span data-ttu-id="b9110-113">**プロジェクトの種類**ペインで、**ワークフロー**いずれかから、 **Visual c#** プロジェクトまたは**Visual Basic**に応じてグループ化、優先する言語。</span><span class="sxs-lookup"><span data-stu-id="b9110-113">In the **Project Types** pane, select **Workflow** from either the **Visual C#** projects or **Visual Basic** groupings depending on your language preference.</span></span>

4. <span data-ttu-id="b9110-114">**テンプレート**ペインで、**アクティビティ ライブラリ**します。</span><span class="sxs-lookup"><span data-stu-id="b9110-114">In the **Templates** pane, select **Activity Library**.</span></span>

5. <span data-ttu-id="b9110-115">**名前**ボックスに、入力`DelayActivityTemplate`します。</span><span class="sxs-lookup"><span data-stu-id="b9110-115">In the **Name** box, enter `DelayActivityTemplate`.</span></span>

6. <span data-ttu-id="b9110-116">既定値のまま、**場所**と**ソリューション名**テキスト ボックス、およびクリック **[ok]** します。</span><span class="sxs-lookup"><span data-stu-id="b9110-116">Accept the defaults in the **Location** and **Solution name** text boxes, and then click **OK**.</span></span>

7. <span data-ttu-id="b9110-117">DelayActivityTemplate プロジェクトの参照ディレクトリを右クリックして**ソリューション エクスプ ローラー**選択**参照の追加**を開く、**参照の追加** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="b9110-117">Right-click the References directory of the DelayActivityTemplate project in **Solution Explorer** and choose **Add Reference** to open the **Add Reference** dialog box.</span></span>

8. <span data-ttu-id="b9110-118">移動して、 **.NET**タブおよび選択**PresentationFramework**から、**コンポーネント名**をクリックし、左の列**OK**参照を追加するにはPresentationFramework.dll ファイル。</span><span class="sxs-lookup"><span data-stu-id="b9110-118">Go to the **.NET** tab and select **PresentationFramework** from the **Component Name** column on the left and click **OK** to add a reference to the PresentationFramework.dll file.</span></span>

9. <span data-ttu-id="b9110-119">この手順を繰り返して、System.Activities.Presentation.dll ファイルと WindowsBase.dll ファイルへの参照を追加します。</span><span class="sxs-lookup"><span data-stu-id="b9110-119">Repeat this procedure to add references to the System.Activities.Presentation.dll and the WindowsBase.dll files.</span></span>

10. <span data-ttu-id="b9110-120">DelayActivityTemplate プロジェクトを右クリックして**ソリューション エクスプ ローラー**選択**追加**し**新しい項目の**を開く、 **の新しい項目の追加** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="b9110-120">Right-click the DelayActivityTemplate project in **Solution Explorer** and choose **Add** and then **New Item** to open the **Add New Item** dialog box.</span></span>

11. <span data-ttu-id="b9110-121">選択、**クラス**テンプレート、MyDelayTemplate、という名前をクリックして**OK**します。</span><span class="sxs-lookup"><span data-stu-id="b9110-121">Select the **Class** template, name it MyDelayTemplate, and then click **OK**.</span></span>

12. <span data-ttu-id="b9110-122">MyDelayTemplate.cs ファイルを開き、次のステートメントを追加します。</span><span class="sxs-lookup"><span data-stu-id="b9110-122">Open the MyDelayTemplate.cs file and add the following statements.</span></span>

    ```
    //Namespaces added
    using System.Activities;
    using System.Activities.Statements;
    using System.Activities.Presentation;
    using System.Windows;
    ```

13. <span data-ttu-id="b9110-123">次のコードを使用して、<xref:System.Activities.Presentation.IActivityTemplateFactory> クラスを持つ `MyDelayActivity` を実装します。</span><span class="sxs-lookup"><span data-stu-id="b9110-123">Implement the <xref:System.Activities.Presentation.IActivityTemplateFactory> with the `MyDelayActivity` class with the following code.</span></span> <span data-ttu-id="b9110-124">これにより、10 秒間の遅延が構成されます。</span><span class="sxs-lookup"><span data-stu-id="b9110-124">This configures the delay to have a duration of 10 seconds.</span></span>

    ```
    public sealed class MyDelayActivity : IActivityTemplateFactory
    {
        public Activity Create(System.Windows.DependencyObject target)
        {
            return new System.Activities.Statements.Delay
            {
                DisplayName = "DelayActivityTemplate",
                Duration = new TimeSpan(0, 0, 10)

            };
        }
    }
    ```

14. <span data-ttu-id="b9110-125">選択**ソリューションのビルド**から、**ビルド**DelayActivityTemplate.dll ファイルを生成するメニュー。</span><span class="sxs-lookup"><span data-stu-id="b9110-125">Select **Build Solution** from the **Build** menu to generate the DelayActivityTemplate.dll file.</span></span>

### <a name="to-make-the-template-available-in-a-workflow-designer"></a><span data-ttu-id="b9110-126">ワークフロー デザイナーでテンプレートを利用できるようにするには</span><span class="sxs-lookup"><span data-stu-id="b9110-126">To make the template available in a Workflow Designer</span></span>

1. <span data-ttu-id="b9110-127">DelayActivityTemplate ソリューションを右クリックして**ソリューション エクスプ ローラー**選択**追加**し**新しいプロジェクト**を開く、 **の新しいプロジェクトの追加**  ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="b9110-127">Right-click the DelayActivityTemplate solution in **Solution Explorer** and choose **Add** and then **New Project** to open the **Add New Project** dialog box.</span></span>

2. <span data-ttu-id="b9110-128">選択、**ワークフロー コンソール アプリケーション**テンプレート、という名前を付けます`CustomActivityTemplateApp`、順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="b9110-128">Select the **Workflow Console Application** template, name it `CustomActivityTemplateApp`, and then click **OK**.</span></span>

3. <span data-ttu-id="b9110-129">CustomActivityTemplateApp プロジェクトの参照ディレクトリを右クリックして**ソリューション エクスプ ローラー**選択**参照の追加**を開く、**参照の追加**ダイアログボックス。</span><span class="sxs-lookup"><span data-stu-id="b9110-129">Right-click the References directory of the CustomActivityTemplateApp project in **Solution Explorer** and choose **Add Reference** to open the **Add Reference** dialog box.</span></span>

4. <span data-ttu-id="b9110-130">移動、**プロジェクト**タブおよび選択**DelayActivityTemplate**から、**プロジェクト名**をクリックし、左の列**OK**を追加する、最初の手順で作成した DelayActivityTemplate.dll ファイルへの参照します。</span><span class="sxs-lookup"><span data-stu-id="b9110-130">Go to the **Projects** tab and select **DelayActivityTemplate** from the **Project Name** column on the left and click **OK** to add a reference to the DelayActivityTemplate.dll file that you created in the first procedure.</span></span>

5. <span data-ttu-id="b9110-131">CustomActivityTemplateApp プロジェクトを右クリックして**ソリューション エクスプ ローラー**選択**ビルド**アプリケーションをコンパイルします。</span><span class="sxs-lookup"><span data-stu-id="b9110-131">Right-click the CustomActivityTemplateApp project in **Solution Explorer** and choose **Build** to compile the application.</span></span>

6. <span data-ttu-id="b9110-132">CustomActivityTemplateApp プロジェクトを右クリックして**ソリューション エクスプ ローラー**選択**スタートアップ プロジェクトとして設定**します。</span><span class="sxs-lookup"><span data-stu-id="b9110-132">Right-click the CustomActivityTemplateApp project in **Solution Explorer** and choose **Set as Startup Project**.</span></span>

7. <span data-ttu-id="b9110-133">選択**デバッグなしで開始**から、**デバッグ**メニューとキーを押して任意のキーを cmd.exe ウィンドウから入力を求められたらを続行します。</span><span class="sxs-lookup"><span data-stu-id="b9110-133">Select **Start Without Debugging** from the **Debug** menu and press any key to continue when prompted from the cmd.exe window.</span></span>

8. <span data-ttu-id="b9110-134">Workflow1.xaml ファイルを開き、開く、**ツールボックス**します。</span><span class="sxs-lookup"><span data-stu-id="b9110-134">Open the Workflow1.xaml file and open the **Toolbox**.</span></span>

9. <span data-ttu-id="b9110-135">検索、 **MyDelayActivity**テンプレート、 **DelayActivityTemplate**カテゴリ。</span><span class="sxs-lookup"><span data-stu-id="b9110-135">Locate the **MyDelayActivity** template in the **DelayActivityTemplate** category.</span></span> <span data-ttu-id="b9110-136">デザイン サーフェイスにドラッグします。</span><span class="sxs-lookup"><span data-stu-id="b9110-136">Drag it onto the design surface.</span></span> <span data-ttu-id="b9110-137">確認、**プロパティ**ウィンドウを`Duration`プロパティが 10 秒に設定されています。</span><span class="sxs-lookup"><span data-stu-id="b9110-137">Confirm in the **Properties** window that the `Duration` property has been set to 10 seconds.</span></span>

## <a name="example"></a><span data-ttu-id="b9110-138">例</span><span class="sxs-lookup"><span data-stu-id="b9110-138">Example</span></span>
 <span data-ttu-id="b9110-139">MyDelayActivity.cs ファイルには次のコードが含まれます。</span><span class="sxs-lookup"><span data-stu-id="b9110-139">The MyDelayActivity.cs file should contain the following code.</span></span>

```
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;

//Namespaces added
using System.Activities;
using System.Activities.Statements;
using System.Activities.Presentation;
using System.Windows;

namespace DelayActivityTemplate
{
    public sealed class MyDelayActivity : IActivityTemplateFactory
    {
        public Activity Create(System.Windows.DependencyObject target)
        {
            return new System.Activities.Statements.Delay
            {
                DisplayName = "DelayActivityTemplate",
                Duration = new TimeSpan(0, 0, 10)

            };
        }
    }
}
```

## <a name="see-also"></a><span data-ttu-id="b9110-140">関連項目</span><span class="sxs-lookup"><span data-stu-id="b9110-140">See also</span></span>

- <xref:System.Activities.Presentation.IActivityTemplateFactory>
- [<span data-ttu-id="b9110-141">ワークフロー デザイン操作のカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="b9110-141">Customizing the Workflow Design Experience</span></span>](customizing-the-workflow-design-experience.md)