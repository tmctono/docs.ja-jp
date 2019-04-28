---
title: '方法: メッセージング アクティビティを使用してワークフロー サービスを作成する'
ms.date: 03/30/2017
ms.assetid: 53d094e2-6901-4aa1-88b8-024b27ccf78b
ms.openlocfilehash: f5bb8df5936be1890bf744300daa7ccb68e341e3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61787794"
---
# <a name="how-to-create-a-workflow-service-with-messaging-activities"></a><span data-ttu-id="cce00-102">方法: メッセージング アクティビティを使用してワークフロー サービスを作成する</span><span class="sxs-lookup"><span data-stu-id="cce00-102">How to: Create a Workflow Service with Messaging Activities</span></span>
<span data-ttu-id="cce00-103">このトピックでは、メッセージング アクティビティを使用して単純なワークフロー サービスを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="cce00-103">This topic describes how to create a simple workflow service using messaging activities.</span></span> <span data-ttu-id="cce00-104">ここでは、メッセージング アクティビティだけで構成されるサービスのワークフロー サービスを作成する機構に重点を置きます。</span><span class="sxs-lookup"><span data-stu-id="cce00-104">This topic focuses on the mechanics of creating a workflow service where the service consists solely of messaging activities.</span></span> <span data-ttu-id="cce00-105">実際のサービスでは、ワークフローに他の多くのアクティビティが含まれます。</span><span class="sxs-lookup"><span data-stu-id="cce00-105">In a real-world service, the workflow contains many other activities.</span></span> <span data-ttu-id="cce00-106">このサービスは、文字列を取得して、それを呼び出し元に返す、Echo という 1 つの操作を実装します。</span><span class="sxs-lookup"><span data-stu-id="cce00-106">The service implements one operation called Echo, which takes a string and returns the string to the caller.</span></span> <span data-ttu-id="cce00-107">このトピックは、一連の 2 つのトピックの最初のものです。</span><span class="sxs-lookup"><span data-stu-id="cce00-107">This topic is the first in a series of two topics.</span></span> <span data-ttu-id="cce00-108">次のトピック[How To:サービス アプリケーションからアクセスする、ワークフロー](../../../../docs/framework/wcf/feature-details/how-to-access-a-service-from-a-workflow-application.md)このトピックで作成したサービスを呼び出すことができるワークフロー アプリケーションを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="cce00-108">The next topic [How To: Access a Service From a Workflow Application](../../../../docs/framework/wcf/feature-details/how-to-access-a-service-from-a-workflow-application.md) discusses how to create a workflow application that can call the service created in this topic.</span></span>  
  
### <a name="to-create-a-workflow-service-project"></a><span data-ttu-id="cce00-109">ワークフロー サービス プロジェクトを作成するには</span><span class="sxs-lookup"><span data-stu-id="cce00-109">To create a workflow service project</span></span>  
  
1. <span data-ttu-id="cce00-110">Visual Studio 2012 を起動します。</span><span class="sxs-lookup"><span data-stu-id="cce00-110">Start Visual Studio 2012.</span></span>  
  
2. <span data-ttu-id="cce00-111">をクリックして、**ファイル**メニューの [**新規**、し**プロジェクト**を表示する、**新しいプロジェクト] ダイアログ**します。</span><span class="sxs-lookup"><span data-stu-id="cce00-111">Click the **File** menu, select **New**, and then **Project** to display the **New Project Dialog**.</span></span> <span data-ttu-id="cce00-112">選択**ワークフロー**インストール済みテンプレートの一覧から、 **WCF ワークフロー サービス アプリケーション**プロジェクトの種類の一覧から。</span><span class="sxs-lookup"><span data-stu-id="cce00-112">Select **Workflow** from the list of installed templates and **WCF Workflow Service Application** from the list of project types.</span></span> <span data-ttu-id="cce00-113">プロジェクトに名前を`MyWFService`し、次の図に示すように、既定の場所を使用します。</span><span class="sxs-lookup"><span data-stu-id="cce00-113">Name the project `MyWFService` and use the default location as shown in the following illustration.</span></span>  
  
     <span data-ttu-id="cce00-114">をクリックして、 **OK**を閉じる、**新しいプロジェクト ダイアログ**します。</span><span class="sxs-lookup"><span data-stu-id="cce00-114">Click the **OK** button to dismiss the **New Project Dialog**.</span></span>  
  
3. <span data-ttu-id="cce00-115">プロジェクトが作成されると、次の図に示すように、Service1.xamlx ファイルがデザイナーで開かれます。</span><span class="sxs-lookup"><span data-stu-id="cce00-115">When the project is created, the Service1.xamlx file is opened in the designer as shown in the following illustration.</span></span>  
  
     ![スクリーン ショットは、デザイナーで、Service1.xamlx ファイルを開くを示しています。](./media/how-to-create-a-workflow-service-with-messaging-activities/default-workflow-service.jpg)  
  
     <span data-ttu-id="cce00-117">というラベルの付いたアクティビティを右クリックして**シーケンシャル サービス**選択**削除**します。</span><span class="sxs-lookup"><span data-stu-id="cce00-117">Right-click the activity labeled **Sequential Service** and select **Delete**.</span></span>  
  
### <a name="to-implement-the-workflow-service"></a><span data-ttu-id="cce00-118">ワークフロー サービスを実装するには</span><span class="sxs-lookup"><span data-stu-id="cce00-118">To implement the workflow service</span></span>  
  
1. <span data-ttu-id="cce00-119">選択、**ツールボックス**をツールボックスを表示し、画鋲のアイコン、ウィンドウを開いたままを画面の左側にあるタブ。</span><span class="sxs-lookup"><span data-stu-id="cce00-119">Select the **Toolbox** tab on the left side of the screen to display the toolbox and click the pushpin to keep the window open.</span></span> <span data-ttu-id="cce00-120">展開、**メッセージング**セクションのツールボックスに次の図に示すように、メッセージング アクティビティおよびメッセージング アクティビティ テンプレートを表示します。</span><span class="sxs-lookup"><span data-stu-id="cce00-120">Expand the **Messaging** section of the toolbox to display the messaging activities and the messaging activity templates as shown in the following illustration.</span></span>  
  
     ![[メッセージング] セクションで、ツールボックスのスクリーン ショットが展開されます。](./media/how-to-create-a-workflow-service-with-messaging-activities/toolbox-messaging-section.jpg)  
  
2. <span data-ttu-id="cce00-122">ドラッグ アンド ドロップ、 **ReceiveAndSendReply**をワークフロー デザイナーのテンプレート。</span><span class="sxs-lookup"><span data-stu-id="cce00-122">Drag and drop a **ReceiveAndSendReply** template to the workflow designer.</span></span> <span data-ttu-id="cce00-123">これを作成します、<xref:System.Activities.Statements.Sequence>でアクティビティを**受信**アクティビティの後に、<xref:System.ServiceModel.Activities.SendReply>アクティビティの次の図に示すようにします。</span><span class="sxs-lookup"><span data-stu-id="cce00-123">This creates a <xref:System.Activities.Statements.Sequence> activity with a **Receive** activity followed by a <xref:System.ServiceModel.Activities.SendReply> activity as shown in the following illustration.</span></span>  
  
     ![ReceiveAndSendReply テンプレートを示すスクリーン ショット。](./media/how-to-create-a-workflow-service-with-messaging-activities/receiveandsendreply-template.jpg)  
  
     <span data-ttu-id="cce00-125"><xref:System.ServiceModel.Activities.SendReply> アクティビティの <xref:System.ServiceModel.Activities.SendReply.Request%2A> プロパティは `Receive` に設定されています。これは、<xref:System.ServiceModel.Activities.Receive> アクティビティが応答する <xref:System.ServiceModel.Activities.SendReply> アクティビティの名前です。</span><span class="sxs-lookup"><span data-stu-id="cce00-125">Notice that the <xref:System.ServiceModel.Activities.SendReply> activity’s <xref:System.ServiceModel.Activities.SendReply.Request%2A> property is set to `Receive`, the name of the <xref:System.ServiceModel.Activities.Receive> activity to which the <xref:System.ServiceModel.Activities.SendReply> activity is replying.</span></span>  
  
3. <span data-ttu-id="cce00-126"><xref:System.ServiceModel.Activities.Receive>アクティビティの種類`Echo`というラベルが付いたテキスト ボックスに**OperationName**します。</span><span class="sxs-lookup"><span data-stu-id="cce00-126">In the <xref:System.ServiceModel.Activities.Receive> activity type `Echo` into the textbox labeled **OperationName**.</span></span> <span data-ttu-id="cce00-127">これにより、サービスが実装する操作の名前が定義されます。</span><span class="sxs-lookup"><span data-stu-id="cce00-127">This defines the name of the operation the service implements.</span></span>  
  
     ![操作名を指定する場所を示すスクリーン ショット。](./media/how-to-create-a-workflow-service-with-messaging-activities/define-operation-name.jpg)  
  
4. <span data-ttu-id="cce00-129"><xref:System.ServiceModel.Activities.Receive>をクリックしてまだ開いていない場合は、選択すると、アクティビティにより、プロパティ ウィンドウを開き、**ビュー**メニュー**プロパティ ウィンドウ**します。</span><span class="sxs-lookup"><span data-stu-id="cce00-129">With the <xref:System.ServiceModel.Activities.Receive> activity selected, open the properties window if not already open by clicking the **View** menu and selecting **Properties Window**.</span></span> <span data-ttu-id="cce00-130">**プロパティ ウィンドウ**が表示されるまで下にスクロール**CanCreateInstance**次の図に示すように、チェック ボックスをクリックします。</span><span class="sxs-lookup"><span data-stu-id="cce00-130">In the **Properties Window** scroll down until you see **CanCreateInstance** and click the checkbox as shown in the following illustration.</span></span> <span data-ttu-id="cce00-131">この設定によって、ワークフロー サービス ホストはメッセージが受信されると (必要に応じて) サービスの新しいインスタンスを作成できるようになります。</span><span class="sxs-lookup"><span data-stu-id="cce00-131">This setting enables the workflow service host to create a new instance of the service (if needed) when a message is received.</span></span>  
  
     ![CanCreateInstance プロパティを示すスクリーン ショット。](./media/how-to-create-a-workflow-service-with-messaging-activities/cancreateinstance-property.jpg)  
  
5. <span data-ttu-id="cce00-133">選択、<xref:System.Activities.Statements.Sequence>アクティビティをクリックして、**変数**デザイナーの左下隅のボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="cce00-133">Select the <xref:System.Activities.Statements.Sequence> activity and click the **Variables** button in the lower left corner of the designer.</span></span> <span data-ttu-id="cce00-134">これにより、変数エディターが開かれます。</span><span class="sxs-lookup"><span data-stu-id="cce00-134">This displays the variables editor.</span></span> <span data-ttu-id="cce00-135">をクリックして、**変数の作成**のリンクを操作に送信される文字列を格納する変数を追加します。</span><span class="sxs-lookup"><span data-stu-id="cce00-135">Click the **Create Variable** link to add a variable to store the string sent to the operation.</span></span> <span data-ttu-id="cce00-136">変数の名前`msg`設定とその**変数**次の図に示すように、文字列を入力します。</span><span class="sxs-lookup"><span data-stu-id="cce00-136">Name the variable `msg` and set its **Variable** type to String as shown in the following illustration.</span></span>  
  
     ![変数を追加する方法を示すスクリーン ショット。](./media/how-to-create-a-workflow-service-with-messaging-activities/add-variable-msg-string.jpg)  
  
     <span data-ttu-id="cce00-138">をクリックして、**変数**ボタンをもう一度、変数エディターを閉じます。</span><span class="sxs-lookup"><span data-stu-id="cce00-138">Click the **Variables** button again to close the variables editor.</span></span>  
  
6. <span data-ttu-id="cce00-139">をクリックして、**定義.**</span><span class="sxs-lookup"><span data-stu-id="cce00-139">Click the **Define..**</span></span> <span data-ttu-id="cce00-140">内のリンク、**コンテンツ**テキスト ボックスに、<xref:System.ServiceModel.Activities.Receive>を表示するアクティビティ、**コンテンツ定義**ダイアログ。</span><span class="sxs-lookup"><span data-stu-id="cce00-140">link in the **Content** text box in the <xref:System.ServiceModel.Activities.Receive> activity to display the **Content Definition** dialog.</span></span> <span data-ttu-id="cce00-141">選択、**パラメーター**ラジオ ボタンをクリックして、**新しいパラメーターを追加**リンクに、入力`inMsg`で、**名前**テキスト ボックスで、**文字列**で、**型**ドロップダウン リスト ボックス、および種類`msg`で、**を割り当てる**テキスト ボックスの次の図に示すようにします。</span><span class="sxs-lookup"><span data-stu-id="cce00-141">Select the **Parameters** radio button, click the **Add new Parameter** link, type `inMsg` in the **name** text box, select **String** in the **Type** drop down list box, and type `msg` in the **Assign To** text box as shown in the following illustration.</span></span>  
  
     ![コンテンツのパラメーターを追加することを示すスクリーン ショット。](./media/how-to-create-a-workflow-service-with-messaging-activities/adding-parameters-content.jpg)  
  
     <span data-ttu-id="cce00-143">これにより、Receive アクティビティが文字列パラメーターを受け取り、そのデータが `msg` 変数にバインドされるように指定されます。</span><span class="sxs-lookup"><span data-stu-id="cce00-143">This specifies that the Receive activity receives string parameter and that data is bound to the `msg` variable.</span></span> <span data-ttu-id="cce00-144">をクリックして**OK**を閉じる、**コンテンツ定義**ダイアログ。</span><span class="sxs-lookup"><span data-stu-id="cce00-144">Click **OK** to close the **Content Definition** dialog.</span></span>  
  
7. <span data-ttu-id="cce00-145">をクリックして、**を定義しています.** のリンクを**コンテンツ**ボックスに、<xref:System.ServiceModel.Activities.SendReply>を表示するアクティビティ、**コンテンツ定義**ダイアログ。</span><span class="sxs-lookup"><span data-stu-id="cce00-145">Click the **Define...** link in the **Content** box in the <xref:System.ServiceModel.Activities.SendReply> activity to display the **Content Definition** dialog.</span></span> <span data-ttu-id="cce00-146">選択、**パラメーター**ラジオ ボタンをクリックして、**新しいパラメーターを追加**リンクに、入力`outMsg`で、**名前** ボックスに、選択**文字列**で、**型**ドロップダウン リスト ボックス、および`msg`で、**値**テキスト ボックスの次の図に示すようにします。</span><span class="sxs-lookup"><span data-stu-id="cce00-146">Select the **Parameters** radio button, click the **Add new Parameter** link, type `outMsg` in the **name** textbox, select **String** in the **Type** dropdown list box, and `msg` in the **Value** text box as shown in the following illustration.</span></span>  
  
     ![OutMsg パラメーターを追加する方法を示すスクリーン ショット。](./media/how-to-create-a-workflow-service-with-messaging-activities/outmsg-parameters-content.jpg)  
  
     <span data-ttu-id="cce00-148">これにより、<xref:System.ServiceModel.Activities.SendReply> アクティビティがメッセージまたはメッセージ コントラクト型を送信し、そのデータが `msg` 変数にバインドされるように指定されます。</span><span class="sxs-lookup"><span data-stu-id="cce00-148">This specifies that the <xref:System.ServiceModel.Activities.SendReply> activity sends a message or message contract type and that data is bound to the `msg` variable.</span></span> <span data-ttu-id="cce00-149">これは <xref:System.ServiceModel.Activities.SendReply> アクティビティであるため、`msg` のデータは、アクティビティがクライアントに送り返すメッセージの設定に使用されます。</span><span class="sxs-lookup"><span data-stu-id="cce00-149">Because this is a <xref:System.ServiceModel.Activities.SendReply> activity, this means the data in `msg` is used to populate the message the activity sends back to the client.</span></span> <span data-ttu-id="cce00-150">をクリックして**OK**を閉じる、**コンテンツ定義**ダイアログ。</span><span class="sxs-lookup"><span data-stu-id="cce00-150">Click **OK** to close the **Content Definition** dialog.</span></span>  
  
8. <span data-ttu-id="cce00-151">保存しをクリックして、ソリューションをビルド、**ビルド**メニュー**ソリューションのビルド**します。</span><span class="sxs-lookup"><span data-stu-id="cce00-151">Save and build the solution by clicking the **Build** menu and selecting **Build Solution**.</span></span>  
  
## <a name="configure-the-workflow-service-project"></a><span data-ttu-id="cce00-152">ワークフロー サービス プロジェクトの構成</span><span class="sxs-lookup"><span data-stu-id="cce00-152">Configure the Workflow Service Project</span></span>  
 <span data-ttu-id="cce00-153">ワークフロー サービスは完成しました。</span><span class="sxs-lookup"><span data-stu-id="cce00-153">The workflow service is complete.</span></span> <span data-ttu-id="cce00-154">ここでは、ホストと実行を容易にするように、ワークフロー サービス ソリューションを構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="cce00-154">This section explains how to configure the workflow service solution to make it easy to host and run.</span></span> <span data-ttu-id="cce00-155">このソリューションでは、ASP.NET 開発サーバーを使用してサービスをホストします。</span><span class="sxs-lookup"><span data-stu-id="cce00-155">This solution uses the ASP.NET Development Server to host the service.</span></span>  
  
#### <a name="to-set-project-start-up-options"></a><span data-ttu-id="cce00-156">プロジェクトのスタートアップ オプションを設定するには</span><span class="sxs-lookup"><span data-stu-id="cce00-156">To set project start up options</span></span>  
  
1. <span data-ttu-id="cce00-157">**ソリューション エクスプ ローラー**、右クリック**MyWFService**選択と**プロパティ**を表示する、**プロジェクトのプロパティ**ダイアログ。</span><span class="sxs-lookup"><span data-stu-id="cce00-157">In the **Solution Explorer**, right-click **MyWFService** and select **Properties** to display the **Project Properties** dialog.</span></span>  
  
2. <span data-ttu-id="cce00-158">選択、 **Web**タブおよび選択**特定のページ\*\*\*\*開始動作**と種類`Service1.xamlx`次の図に示すように、テキスト ボックスに。</span><span class="sxs-lookup"><span data-stu-id="cce00-158">Select the **Web** tab and select **Specific Page** under **Start Action** and type `Service1.xamlx` in the text box as shown in the following illustration.</span></span>  
  
     ![プロジェクトの [プロパティ] ダイアログ ボックスのスクリーン ショット。](./media/how-to-create-a-workflow-service-with-messaging-activities/project-properties-dialog.jpg)  
  
     <span data-ttu-id="cce00-160">これにより、ASP.NET 開発サーバーの Service1.xamlx で定義されたサービスがホストされます。</span><span class="sxs-lookup"><span data-stu-id="cce00-160">This hosts the service defined in Service1.xamlx in the ASP.NET Development Server.</span></span>  
  
3. <span data-ttu-id="cce00-161">Ctrl キーを押しながら F5 キーを押して、サービスを起動します。</span><span class="sxs-lookup"><span data-stu-id="cce00-161">Press Ctrl + F5 to launch the service.</span></span> <span data-ttu-id="cce00-162">次の図に示すように、ASP.NET 開発サーバーのアイコンが、デスクトップの右下側に表示されます。</span><span class="sxs-lookup"><span data-stu-id="cce00-162">The ASP.NET Development Server icon is displayed in the lower right side of the desktop as shown in the following image.</span></span>  
  
     ![ASP.NET 開発サーバーのアイコンを示すスクリーン ショット。](./media/how-to-create-a-workflow-service-with-messaging-activities/asp-net-dev-server-icon.jpg)  
  
     <span data-ttu-id="cce00-164">また、Internet Explorer に、サービスの WCF サービス ヘルプ ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="cce00-164">In addition, Internet Explorer displays the WCF Service Help Page for the service.</span></span>  
  
     ![WCF サービス ヘルプ ページを示すスクリーン ショット。](./media/how-to-create-a-workflow-service-with-messaging-activities/wcf-service-help-page.jpg)  
  
4. <span data-ttu-id="cce00-166">進み、[方法。サービス アプリケーションからアクセスする、ワークフロー](../../../../docs/framework/wcf/feature-details/how-to-access-a-service-from-a-workflow-application.md)をこのサービスを呼び出すワークフロー クライアントを作成するトピック。</span><span class="sxs-lookup"><span data-stu-id="cce00-166">Continue on to the [How To: Access a Service From a Workflow Application](../../../../docs/framework/wcf/feature-details/how-to-access-a-service-from-a-workflow-application.md) topic to create a workflow client that calls this service.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cce00-167">関連項目</span><span class="sxs-lookup"><span data-stu-id="cce00-167">See also</span></span>

- [<span data-ttu-id="cce00-168">ワークフロー サービス</span><span class="sxs-lookup"><span data-stu-id="cce00-168">Workflow Services</span></span>](../../../../docs/framework/wcf/feature-details/workflow-services.md)
- [<span data-ttu-id="cce00-169">ワークフロー サービスのホストの概要</span><span class="sxs-lookup"><span data-stu-id="cce00-169">Hosting Workflow Services Overview</span></span>](../../../../docs/framework/wcf/feature-details/hosting-workflow-services-overview.md)
- [<span data-ttu-id="cce00-170">メッセージング アクティビティ</span><span class="sxs-lookup"><span data-stu-id="cce00-170">Messaging Activities</span></span>](../../../../docs/framework/wcf/feature-details/messaging-activities.md)
