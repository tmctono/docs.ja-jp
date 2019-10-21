---
title: 'チュートリアル: 基本的な Windows Communication Foundation サービスをホストして実行する'
ms.date: 03/19/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF services [WCF]
- WCF services [WCF], running
ms.assetid: 31774d36-923b-4e2d-812e-aa190127266f
ms.openlocfilehash: 984c5e73a8efc4e9c2d487485267868ffa2f60f3
ms.sourcegitcommit: 33c8d6f7342a4bb2c577842b7f075b0e20a2fa40
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2019
ms.locfileid: "70928724"
---
# <a name="tutorial-host-and-run-a-basic-windows-communication-foundation-service"></a><span data-ttu-id="40c41-102">チュートリアル: 基本的な Windows Communication Foundation サービスをホストして実行する</span><span class="sxs-lookup"><span data-stu-id="40c41-102">Tutorial: Host and run a basic Windows Communication Foundation service</span></span>

<span data-ttu-id="40c41-103">このチュートリアルでは、基本的な Windows Communication Foundation (WCF) アプリケーションを作成するために必要な5つのタスクについて説明します。</span><span class="sxs-lookup"><span data-stu-id="40c41-103">This tutorial describes the third of five tasks required to create a basic Windows Communication Foundation (WCF) application.</span></span> <span data-ttu-id="40c41-104">チュートリアルの概要については、 [「チュートリアル:Windows Communication Foundation アプリケーション](getting-started-tutorial.md)の概要」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="40c41-104">For an overview of the tutorials, see [Tutorial: Get started with Windows Communication Foundation applications](getting-started-tutorial.md).</span></span>

<span data-ttu-id="40c41-105">WCF アプリケーションを作成するための次のタスクは、コンソールアプリケーションで WCF サービスをホストすることです。</span><span class="sxs-lookup"><span data-stu-id="40c41-105">The next task for creating a WCF application is to host a WCF service in a console application.</span></span> <span data-ttu-id="40c41-106">WCF サービスは1つ以上の*エンドポイント*を公開し、それぞれが1つ以上のサービス操作を公開します。</span><span class="sxs-lookup"><span data-stu-id="40c41-106">A WCF service exposes one or more *endpoints*, each of which exposes one or more service operations.</span></span> <span data-ttu-id="40c41-107">サービスエンドポイントは、次の情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="40c41-107">A service endpoint specifies the following information:</span></span>

- <span data-ttu-id="40c41-108">サービスを検索できるアドレス。</span><span class="sxs-lookup"><span data-stu-id="40c41-108">An address where you can find the service.</span></span>
- <span data-ttu-id="40c41-109">クライアントがサービスと通信する方法を説明する情報を格納しているバインディング。</span><span class="sxs-lookup"><span data-stu-id="40c41-109">A binding that contains the information that describes how a client must communicate with the service.</span></span> 
- <span data-ttu-id="40c41-110">サービスがクライアントに提供する機能を定義するコントラクト。</span><span class="sxs-lookup"><span data-stu-id="40c41-110">A contract that defines the functionality that the service provides to its clients.</span></span>

<span data-ttu-id="40c41-111">このチュートリアルでは、次の作業を行う方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="40c41-111">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="40c41-112">WCF サービスをホストするためのコンソールアプリプロジェクトを作成して構成します。</span><span class="sxs-lookup"><span data-stu-id="40c41-112">Create and configure a console app project for hosting a WCF service.</span></span>
> - <span data-ttu-id="40c41-113">WCF サービスをホストするコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="40c41-113">Add code to host the WCF service.</span></span>
> - <span data-ttu-id="40c41-114">構成ファイルを更新します。</span><span class="sxs-lookup"><span data-stu-id="40c41-114">Update the configuration file.</span></span>
> - <span data-ttu-id="40c41-115">WCF サービスを開始し、実行されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="40c41-115">Start the WCF service and verify it's running.</span></span>

## <a name="create-and-configure-a-console-app-project-for-hosting-the-service"></a><span data-ttu-id="40c41-116">サービスをホストするためのコンソールアプリプロジェクトを作成して構成する</span><span class="sxs-lookup"><span data-stu-id="40c41-116">Create and configure a console app project for hosting the service</span></span>

1. <span data-ttu-id="40c41-117">Visual Studio でコンソールアプリプロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="40c41-117">Create a console app project in Visual Studio:</span></span> 
 
    1. <span data-ttu-id="40c41-118">**[ファイル]** メニューの [**プロジェクト/ソリューション**を**開く** > ] を選択し、前の作業で作成した**gettingstarted** (*gettingstarted. .sln*) を参照します。</span><span class="sxs-lookup"><span data-stu-id="40c41-118">From the **File** menu, select **Open** > **Project/Solution** and browse to the **GettingStarted** solution you previously created (*GettingStarted.sln*).</span></span> <span data-ttu-id="40c41-119">**[開く]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="40c41-119">Select **Open**.</span></span>

    2. <span data-ttu-id="40c41-120">**[表示]** メニューの **[ソリューションエクスプローラー]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="40c41-120">From the **View** menu, select **Solution Explorer**.</span></span>
    
    3. <span data-ttu-id="40c41-121">**[ソリューションエクスプローラー]** ウィンドウで、 **[gettingstarted]** ソリューション (最上位ノード) を選択し、ショートカットメニューの [**新しいプロジェクト**の**追加** > ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="40c41-121">In the **Solution Explorer** window, select the **GettingStarted** solution (top node), and then select **Add** > **New Project** from the shortcut menu.</span></span> 

    4. <span data-ttu-id="40c41-122">**[新しいプロジェクトの追加]** ウィンドウの左側にある **[Visual C# ]** または **[Visual Basic]** の下にある **[Windows デスクトップ]** カテゴリを選択します。</span><span class="sxs-lookup"><span data-stu-id="40c41-122">In the **Add New Project** window, on the left side, select the **Windows Desktop** category under **Visual C#** or **Visual Basic**.</span></span> 

    5. <span data-ttu-id="40c41-123">**[コンソールアプリ (.NET Framework)]** テンプレートを選択し、**名前**として「 *gettingon host* 」と入力します。</span><span class="sxs-lookup"><span data-stu-id="40c41-123">Select the **Console App (.NET Framework)** template, and enter *GettingStartedHost* for the **Name**.</span></span> <span data-ttu-id="40c41-124">**[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="40c41-124">Select **OK**.</span></span>

2. <span data-ttu-id="40c41-125">**Gettingのホスト**プロジェクトに参照を追加して、 **Getting: lib**プロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="40c41-125">Add a reference in the **GettingStartedHost** project to the **GettingStartedLib** project:</span></span> 

    1. <span data-ttu-id="40c41-126">**[ソリューションエクスプローラー]** ウィンドウで、 **Gettingのホスト**プロジェクトの下にある **[参照]** フォルダーを選択し、ショートカットメニューの **[参照の追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="40c41-126">In the **Solution Explorer** window, select the **References** folder under the **GettingStartedHost** project, and then select **Add Reference** from the shortcut menu.</span></span> 

    2. <span data-ttu-id="40c41-127">**[参照の追加]** ダイアログボックスで、ウィンドウの左側にある **[プロジェクト]** の下にある **[ソリューション]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="40c41-127">In the **Add Reference** dialog, under **Projects** on the left side of the window, select **Solution**.</span></span> 
 
    3. <span data-ttu-id="40c41-128">ウィンドウの中央のセクションで [ **Getting] lib**を選択し、[ **OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="40c41-128">Select **GettingStartedLib** in the center section of the window, and then select **OK**.</span></span> 

       <span data-ttu-id="40c41-129">このアクションにより、gettingの**lib**プロジェクトで定義されている型が**Gettingのホスト**プロジェクトで使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="40c41-129">This action makes the types defined in the **GettingStartedLib** project available to the **GettingStartedHost** project.</span></span>

3. <span data-ttu-id="40c41-130">**Gettingのホスト**プロジェクトで、 <xref:System.ServiceModel>アセンブリに参照を追加します。</span><span class="sxs-lookup"><span data-stu-id="40c41-130">Add a reference in the **GettingStartedHost** project to the <xref:System.ServiceModel> assembly:</span></span> 

    1. <span data-ttu-id="40c41-131">**[ソリューションエクスプローラー]** ウィンドウで、 **Gettingのホスト**プロジェクトの下にある **[参照]** フォルダーを選択し、ショートカットメニューの **[参照の追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="40c41-131">In the **Solution Explorer** window, select the **References** folder under the **GettingStartedHost** project, and then select **Add Reference** from the shortcut menu.</span></span>
    
    2. <span data-ttu-id="40c41-132">**[参照の追加]** ウィンドウの左側にある **[アセンブリ]** で、 **[フレームワーク]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="40c41-132">In the **Add Reference** window, under **Assemblies** on the left side of the window, select **Framework**.</span></span> 

    3. <span data-ttu-id="40c41-133">**[System.servicemodel]** を選択し、[ **OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="40c41-133">Select **System.ServiceModel**, and then select **OK**.</span></span> 
    
    4. <span data-ttu-id="40c41-134">[**ファイル** > ] **[すべて保存]** の順に選択して、ソリューションを保存します。</span><span class="sxs-lookup"><span data-stu-id="40c41-134">Save the solution by selecting **File** > **Save All**.</span></span>

## <a name="add-code-to-host-the-service"></a><span data-ttu-id="40c41-135">サービスをホストするコードを追加する</span><span class="sxs-lookup"><span data-stu-id="40c41-135">Add code to host the service</span></span>

<span data-ttu-id="40c41-136">サービスをホストするには、次の手順を実行するコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="40c41-136">To host the service, you add code to do the following steps:</span></span> 

1. <span data-ttu-id="40c41-137">ベースアドレスの URI を作成します。</span><span class="sxs-lookup"><span data-stu-id="40c41-137">Create a URI for the base address.</span></span>
2. <span data-ttu-id="40c41-138">サービスをホストするためのクラスインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="40c41-138">Create a class instance for hosting the service.</span></span>
3. <span data-ttu-id="40c41-139">サービスエンドポイントを作成します。</span><span class="sxs-lookup"><span data-stu-id="40c41-139">Create a service endpoint.</span></span>
4. <span data-ttu-id="40c41-140">メタデータ交換を有効にします。</span><span class="sxs-lookup"><span data-stu-id="40c41-140">Enable metadata exchange.</span></span>
5. <span data-ttu-id="40c41-141">サービスホストを開いて、受信メッセージをリッスンします。</span><span class="sxs-lookup"><span data-stu-id="40c41-141">Open the service host to listen for incoming messages.</span></span>
  
<span data-ttu-id="40c41-142">コードに次の変更を加えます。</span><span class="sxs-lookup"><span data-stu-id="40c41-142">Make the following changes to the code:</span></span>

1. <span data-ttu-id="40c41-143">**GettingProgram.cs ホスト**プロジェクトのファイルまたは module1.vb ファイルを開き、そのコードを次のコードに置き換え**ます。**</span><span class="sxs-lookup"><span data-stu-id="40c41-143">Open the **Program.cs** or **Module1.vb** file in the **GettingStartedHost** project and replace its code with the following code:</span></span>

    ```csharp
    using System;
    using System.ServiceModel;
    using System.ServiceModel.Description;
    using GettingStartedLib;

    namespace GettingStartedHost
    {
        class Program
        {
            static void Main(string[] args)
            {
                // Step 1: Create a URI to serve as the base address.
                Uri baseAddress = new Uri("http://localhost:8000/GettingStarted/");

                // Step 2: Create a ServiceHost instance.
                ServiceHost selfHost = new ServiceHost(typeof(CalculatorService), baseAddress);

                try
                {
                    // Step 3: Add a service endpoint.
                    selfHost.AddServiceEndpoint(typeof(ICalculator), new WSHttpBinding(), "CalculatorService");

                    // Step 4: Enable metadata exchange.
                    ServiceMetadataBehavior smb = new ServiceMetadataBehavior();
                    smb.HttpGetEnabled = true;
                    selfHost.Description.Behaviors.Add(smb)    ;

                    // Step 5: Start the service.
                    selfHost.Open();
                    Console.WriteLine("The service is ready.");

                    // Close the ServiceHost to stop the service.
                    Console.WriteLine("Press <Enter> to terminate the service.");
                    Console.WriteLine();
                    Console.ReadLine();
                    selfHost.Close();
                }
                catch (CommunicationException ce)
                {
                    Console.WriteLine("An exception occurred: {0}", ce.Message);
                    selfHost.Abort();
                }
            }
        }
    }
    ```

    ```vb
    Imports System.ServiceModel
    Imports System.ServiceModel.Description
    Imports GettingStartedLib.GettingStartedLib

    Module Service

        Class Program
            Shared Sub Main()
                ' Step 1: Create a URI to serve as the base address.
                Dim baseAddress As New Uri("http://localhost:8000/GettingStarted/")

                ' Step 2: Create a ServiceHost instance.
                Dim selfHost As New ServiceHost(GetType(CalculatorService), baseAddress)
               Try

                    ' Step 3: Add a service endpoint.
                    selfHost.AddServiceEndpoint( _
                        GetType(ICalculator), _
                        New WSHttpBinding(), _
                        "CalculatorService")

                    ' Step 4: Enable metadata exchange.
                    Dim smb As New ServiceMetadataBehavior()
                    smb.HttpGetEnabled = True
                    selfHost.Description.Behaviors.Add(smb)

                    ' Step 5: Start the service.
                    selfHost.Open()
                    Console.WriteLine("The service is ready.")

                    ' Close the ServiceHost to stop the service.
                    Console.WriteLine("Press <Enter> to terminate the service.")
                    Console.WriteLine()
                    Console.ReadLine()
                    selfHost.Close()

                Catch ce As CommunicationException
                    Console.WriteLine("An exception occurred: {0}", ce.Message)
                    selfHost.Abort()
                End Try
            End Sub
        End Class

    End Module
    ```
    
    <span data-ttu-id="40c41-144">このコードの動作については、「[サービスホスティングプログラムの手順](#service-hosting-program-steps)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="40c41-144">For information about how this code works, see [Service hosting program steps](#service-hosting-program-steps).</span></span>

2. <span data-ttu-id="40c41-145">プロジェクトのプロパティを更新します。</span><span class="sxs-lookup"><span data-stu-id="40c41-145">Update the project properties:</span></span>

   1. <span data-ttu-id="40c41-146">**[ソリューションエクスプローラー]** ウィンドウで、[ **Getting] ホスト**フォルダーを選択し、ショートカットメニューの **[プロパティ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="40c41-146">In the **Solution Explorer** window, select the **GettingStartedHost** folder, and then select **Properties** from the shortcut menu.</span></span>

   2. <span data-ttu-id="40c41-147">**[Gettingon ホスト]** のプロパティ ページで、 **[アプリケーション]** タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="40c41-147">On the **GettingStartedHost** properties page, select the **Application** tab:</span></span>

      - <span data-ttu-id="40c41-148">プロジェクトC#の場合は、 **[スタートアップオブジェクト]** ボックスの一覧から [ **getting]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="40c41-148">For C# projects, select **GettingStartedHost.Program** from the **Startup object** list.</span></span>

      - <span data-ttu-id="40c41-149">Visual Basic プロジェクトの場合は、 **[スタートアップオブジェクト]** ボックスの一覧から **[Service. プログラム]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="40c41-149">For Visual Basic projects, select **Service.Program** from the **Startup object** list.</span></span>

   3. <span data-ttu-id="40c41-150">**[ファイル]** メニューの **[すべてを保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="40c41-150">From the **File** menu, select **Save All**.</span></span>

## <a name="verify-the-service-is-working"></a><span data-ttu-id="40c41-151">サービスが動作していることを確認する</span><span class="sxs-lookup"><span data-stu-id="40c41-151">Verify the service is working</span></span>

1. <span data-ttu-id="40c41-152">ソリューションをビルドし、Visual Studio 内から**Gettingのホスト**コンソールアプリケーションを実行します。</span><span class="sxs-lookup"><span data-stu-id="40c41-152">Build the solution, and then run the **GettingStartedHost** console application from inside Visual Studio.</span></span> 

    <span data-ttu-id="40c41-153">サービスは、管理者特権で実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="40c41-153">The service must be run with administrator privileges.</span></span> <span data-ttu-id="40c41-154">Visual Studio を管理者特権で開いたので、Visual Studio で**Gettingon ホスト**を実行すると、アプリケーションも管理者特権で実行されます。</span><span class="sxs-lookup"><span data-stu-id="40c41-154">Because you opened Visual Studio with administrator privileges, when you run **GettingStartedHost** in Visual Studio, the application is run with administrator privileges as well.</span></span> <span data-ttu-id="40c41-155">別の方法として、新しいコマンドプロンプトを管理者として開くこともできます (ショートカットメニューから [**その他** > の**実行**] を選択して、**その中で実行します)** 。</span><span class="sxs-lookup"><span data-stu-id="40c41-155">As an alternative, you can open a new command prompt as an administrator (select **More** > **Run as administrator** from the shortcut menu) and run **GettingStartedHost.exe** within it.</span></span>

2. <span data-ttu-id="40c41-156">Web ブラウザーを開き、で`http://localhost:8000/GettingStarted/CalculatorService`サービスのページを参照します。</span><span class="sxs-lookup"><span data-stu-id="40c41-156">Open a web browser and browse to the service's page at `http://localhost:8000/GettingStarted/CalculatorService`.</span></span>
   
   > [!NOTE]
   > <span data-ttu-id="40c41-157">このようなサービスでは、リッスンするコンピューターに HTTP アドレスを登録するための適切なアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="40c41-157">Services such as this one require the proper permission to register HTTP addresses on the machine for listening.</span></span> <span data-ttu-id="40c41-158">管理者アカウントにはこのアクセス許可がありますが、管理者以外のアカウントの場合は、HTTP 名前空間へのアクセス許可を付与する必要があります。</span><span class="sxs-lookup"><span data-stu-id="40c41-158">Administrator accounts have this permission, but non-administrator accounts must be granted permission for HTTP namespaces.</span></span> <span data-ttu-id="40c41-159">名前空間の予約を構成する方法については、「[HTTP および HTTPS の構成](feature-details/configuring-http-and-https.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="40c41-159">For more information about how to configure namespace reservations, see [Configuring HTTP and HTTPS](feature-details/configuring-http-and-https.md).</span></span> 

## <a name="service-hosting-program-steps"></a><span data-ttu-id="40c41-160">サービスホスティングプログラムの手順</span><span class="sxs-lookup"><span data-stu-id="40c41-160">Service hosting program steps</span></span>

<span data-ttu-id="40c41-161">サービスをホストするために追加したコードの手順は、次のように記述されています。</span><span class="sxs-lookup"><span data-stu-id="40c41-161">The steps in the code you added to host the service are described as follows:</span></span>

- <span data-ttu-id="40c41-162">**手順 1**:サービスのベースアドレスを`Uri`保持するクラスのインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="40c41-162">**Step 1**: Create an instance of the `Uri` class to hold the base address of the service.</span></span> <span data-ttu-id="40c41-163">ベースアドレスを含む URL には、サービスを識別する省略可能な URI があります。</span><span class="sxs-lookup"><span data-stu-id="40c41-163">A URL that contains a base address has an optional URI that identifies a service.</span></span> <span data-ttu-id="40c41-164">ベースアドレスは、のよう`<transport>://<machine-name or domain><:optional port #>/<optional URI segment>`に書式設定されます。</span><span class="sxs-lookup"><span data-stu-id="40c41-164">The base address is formatted as follows: `<transport>://<machine-name or domain><:optional port #>/<optional URI segment>`.</span></span> <span data-ttu-id="40c41-165">電卓サービスのベースアドレスは、HTTP トランスポート、localhost、ポート8000、および URI セグメント (GettingStarted) を使用します。</span><span class="sxs-lookup"><span data-stu-id="40c41-165">The base address for the calculator service uses the HTTP transport, localhost, port 8000, and the URI segment, GettingStarted.</span></span>

- <span data-ttu-id="40c41-166">**手順 2**:サービスをホストするため<xref:System.ServiceModel.ServiceHost>に使用するクラスのインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="40c41-166">**Step 2**: Create an instance of the <xref:System.ServiceModel.ServiceHost> class, which you use to host the service.</span></span> <span data-ttu-id="40c41-167">コンストラクターは、サービスコントラクトを実装するクラスの型とサービスのベースアドレスの2つのパラメーターを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="40c41-167">The constructor takes two parameters: the type of the class that implements the service contract and the base address of the service.</span></span>

- <span data-ttu-id="40c41-168">**手順 3**:<xref:System.ServiceModel.Description.ServiceEndpoint> インスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="40c41-168">**Step 3**: Create a <xref:System.ServiceModel.Description.ServiceEndpoint> instance.</span></span> <span data-ttu-id="40c41-169">サービス エンドポイントは、アドレス、バインディング、およびサービス コントラクトから構成されます。</span><span class="sxs-lookup"><span data-stu-id="40c41-169">A service endpoint is composed of an address, a binding, and a service contract.</span></span> <span data-ttu-id="40c41-170"><xref:System.ServiceModel.Description.ServiceEndpoint>コンストラクターは、サービスコントラクトインターフェイスの型、バインディング、およびアドレスで構成されます。</span><span class="sxs-lookup"><span data-stu-id="40c41-170">The <xref:System.ServiceModel.Description.ServiceEndpoint> constructor is composed of the service contract interface type, a binding, and an address.</span></span> <span data-ttu-id="40c41-171">サービス コントラクトは、サービス型に定義および実装した `ICalculator` です。</span><span class="sxs-lookup"><span data-stu-id="40c41-171">The service contract is `ICalculator`, which you defined and implement in the service type.</span></span> <span data-ttu-id="40c41-172">このサンプル<xref:System.ServiceModel.WSHttpBinding>のバインドは、組み込みのバインドであり、WS-\* 仕様に準拠するエンドポイントに接続されています。</span><span class="sxs-lookup"><span data-stu-id="40c41-172">The binding for this sample is <xref:System.ServiceModel.WSHttpBinding>, which is a built-in binding and connects to endpoints that conform to the WS-\* specifications.</span></span> <span data-ttu-id="40c41-173">WCF バインディングの詳細については、「 [wcf バインディングの概要](bindings-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="40c41-173">For more information about WCF bindings, see [WCF bindings overview](bindings-overview.md).</span></span> <span data-ttu-id="40c41-174">アドレスをベースアドレスに追加して、エンドポイントを識別します。</span><span class="sxs-lookup"><span data-stu-id="40c41-174">You append the address to the base address to identify the endpoint.</span></span> <span data-ttu-id="40c41-175">このコードでは、このアドレスを計算し、そのエンドポイントの完全修飾アドレス`http://localhost:8000/GettingStarted/CalculatorService`をとして指定します。</span><span class="sxs-lookup"><span data-stu-id="40c41-175">The code specifies the address as CalculatorService and the fully qualified address for the endpoint as `http://localhost:8000/GettingStarted/CalculatorService`.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="40c41-176">.NET Framework バージョン4以降では、サービスエンドポイントの追加は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="40c41-176">For .NET Framework Version 4 and later, adding a service endpoint is optional.</span></span> <span data-ttu-id="40c41-177">これらのバージョンでは、コードまたは構成を追加しないと、サービスによって実装されたベースアドレスとコントラクトの組み合わせごとに既定のエンドポイントが1つ追加されます。</span><span class="sxs-lookup"><span data-stu-id="40c41-177">For these versions, if you don't add your code or configuration, WCF adds one default endpoint for each combination of base address and contract implemented by the service.</span></span> <span data-ttu-id="40c41-178">既定のエンドポイントの詳細については、「[エンドポイントアドレスの指定](specifying-an-endpoint-address.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="40c41-178">For more information about default endpoints, see [Specifying an endpoint address](specifying-an-endpoint-address.md).</span></span> <span data-ttu-id="40c41-179">既定のエンドポイント、バインディング、および動作の詳細については、「簡略化された[構成](simplified-configuration.md)と[WCF サービスの簡略化](samples/simplified-configuration-for-wcf-services.md)された構成」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="40c41-179">For more information about default endpoints, bindings, and behaviors, see [Simplified configuration](simplified-configuration.md) and [Simplified configuration for WCF services](samples/simplified-configuration-for-wcf-services.md).</span></span>

- <span data-ttu-id="40c41-180">**手順 4**:メタデータ交換を有効にします。</span><span class="sxs-lookup"><span data-stu-id="40c41-180">**Step 4**: Enable metadata exchange.</span></span> <span data-ttu-id="40c41-181">クライアントは、メタデータ交換を使用して、サービス操作を呼び出すためのプロキシを生成します。</span><span class="sxs-lookup"><span data-stu-id="40c41-181">Clients use metadata exchange to generate proxies for calling the service operations.</span></span> <span data-ttu-id="40c41-182">メタデータ交換を有効にする<xref:System.ServiceModel.Description.ServiceMetadataBehavior>には、インスタンス<xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpGetEnabled>を作成`true`し、そのプロパティ`ServiceMetadataBehavior`をに設定<xref:System.ServiceModel.Description.ServiceDescription.Behaviors%2A>して、 <xref:System.ServiceModel.ServiceHost>オブジェクトをインスタンスのコレクションに追加します。</span><span class="sxs-lookup"><span data-stu-id="40c41-182">To enable metadata exchange, create a <xref:System.ServiceModel.Description.ServiceMetadataBehavior> instance, set its <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpGetEnabled> property to `true`, and add the `ServiceMetadataBehavior` object to the <xref:System.ServiceModel.Description.ServiceDescription.Behaviors%2A> collection of the <xref:System.ServiceModel.ServiceHost> instance.</span></span>

- <span data-ttu-id="40c41-183">**手順 5**:を<xref:System.ServiceModel.ServiceHost>開き、受信メッセージをリッスンします。</span><span class="sxs-lookup"><span data-stu-id="40c41-183">**Step 5**: Open <xref:System.ServiceModel.ServiceHost> to listen for incoming messages.</span></span> <span data-ttu-id="40c41-184">アプリケーションは、 **enter**キーを押すまで待機します。</span><span class="sxs-lookup"><span data-stu-id="40c41-184">The application waits for you to press **Enter**.</span></span> <span data-ttu-id="40c41-185">アプリケーションがインスタンス<xref:System.ServiceModel.ServiceHost>化されると、try/catch ブロックが実行されます。</span><span class="sxs-lookup"><span data-stu-id="40c41-185">After the application instantiates <xref:System.ServiceModel.ServiceHost>, it executes a try/catch block.</span></span> <span data-ttu-id="40c41-186">によって<xref:System.ServiceModel.ServiceHost>スローされる例外を安全にキャッチする方法の詳細については、「 [Close と Abort を使用して WCF クライアントリソースを解放する](samples/use-close-abort-release-wcf-client-resources.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="40c41-186">For more information about safely catching exceptions thrown by <xref:System.ServiceModel.ServiceHost>, see [Use Close and Abort to release WCF client resources](samples/use-close-abort-release-wcf-client-resources.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="40c41-187">WCF サービスライブラリを追加すると、サービスホストを起動してデバッグする場合、Visual Studio はそれをホストします。</span><span class="sxs-lookup"><span data-stu-id="40c41-187">When you add a WCF service library, Visual Studio hosts it for you if you debug it by starting a service host.</span></span> <span data-ttu-id="40c41-188">競合を回避するために、Visual Studio が WCF サービスライブラリをホストしないようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="40c41-188">To avoid conflicts, you can prevent Visual Studio from hosting the WCF service library.</span></span> 
>
> 1. <span data-ttu-id="40c41-189">**ソリューションエクスプローラー**で**Gettingの lib**プロジェクトを選択し、ショートカットメニューの **[プロパティ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="40c41-189">Select the **GettingStartedLib** project in **Solution Explorer** and choose **Properties** from the shortcut menu.</span></span>
> 2. <span data-ttu-id="40c41-190">**[Wcf オプション]** を選択し、**同じソリューションで別のプロジェクトをデバッグするときに [wcf サービスホストを開始する**] チェックボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="40c41-190">Select **WCF Options** and uncheck **Start WCF Service Host when debugging another project in the same solution**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="40c41-191">次の手順</span><span class="sxs-lookup"><span data-stu-id="40c41-191">Next steps</span></span>

<span data-ttu-id="40c41-192">このチュートリアルでは、次の作業を行う方法を学びました。</span><span class="sxs-lookup"><span data-stu-id="40c41-192">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="40c41-193">WCF サービスをホストするためのコンソールアプリプロジェクトを作成して構成します。</span><span class="sxs-lookup"><span data-stu-id="40c41-193">Create and configure a console app project for hosting a WCF service.</span></span>
> - <span data-ttu-id="40c41-194">WCF サービスをホストするコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="40c41-194">Add code to host the WCF service.</span></span>
> - <span data-ttu-id="40c41-195">構成ファイルを更新します。</span><span class="sxs-lookup"><span data-stu-id="40c41-195">Update the configuration file.</span></span>
> - <span data-ttu-id="40c41-196">WCF サービスを開始し、実行されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="40c41-196">Start the WCF service and verify it's running.</span></span>

<span data-ttu-id="40c41-197">次のチュートリアルに進み、WCF クライアントを作成する方法を学習してください。</span><span class="sxs-lookup"><span data-stu-id="40c41-197">Advance to the next tutorial to learn how to create a WCF client.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="40c41-198">チュートリアル: WCF クライアントを作成する</span><span class="sxs-lookup"><span data-stu-id="40c41-198">Tutorial: Create a WCF client</span></span>](how-to-create-a-wcf-client.md)
