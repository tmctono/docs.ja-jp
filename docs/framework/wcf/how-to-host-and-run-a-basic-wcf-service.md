---
title: 'チュートリアル: 基本的な Windows Communication Foundation サービスをホストして実行する'
description: Wcf アプリケーションの作成を開始する際に役立つ一連の記事の一部として、コンソールアプリケーションで WCF サービスをホストする方法について説明します。
ms.date: 03/19/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF services [WCF]
- WCF services [WCF], running
ms.assetid: 31774d36-923b-4e2d-812e-aa190127266f
ms.openlocfilehash: 5318991087e71430523681d601d3b38c4513027b
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/23/2020
ms.locfileid: "85246131"
---
# <a name="tutorial-host-and-run-a-basic-windows-communication-foundation-service"></a><span data-ttu-id="5d287-103">チュートリアル: 基本的な Windows Communication Foundation サービスをホストして実行する</span><span class="sxs-lookup"><span data-stu-id="5d287-103">Tutorial: Host and run a basic Windows Communication Foundation service</span></span>

<span data-ttu-id="5d287-104">このチュートリアルでは、基本的な Windows Communication Foundation (WCF) アプリケーションを作成するために必要な5つのタスクについて説明します。</span><span class="sxs-lookup"><span data-stu-id="5d287-104">This tutorial describes the third of five tasks required to create a basic Windows Communication Foundation (WCF) application.</span></span> <span data-ttu-id="5d287-105">チュートリアルの概要については、「[チュートリアル: Windows Communication Foundation アプリケーションの](getting-started-tutorial.md)概要」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5d287-105">For an overview of the tutorials, see [Tutorial: Get started with Windows Communication Foundation applications](getting-started-tutorial.md).</span></span>

<span data-ttu-id="5d287-106">WCF アプリケーションを作成するための次のタスクは、コンソールアプリケーションで WCF サービスをホストすることです。</span><span class="sxs-lookup"><span data-stu-id="5d287-106">The next task for creating a WCF application is to host a WCF service in a console application.</span></span> <span data-ttu-id="5d287-107">WCF サービスは1つ以上の*エンドポイント*を公開し、それぞれが1つ以上のサービス操作を公開します。</span><span class="sxs-lookup"><span data-stu-id="5d287-107">A WCF service exposes one or more *endpoints*, each of which exposes one or more service operations.</span></span> <span data-ttu-id="5d287-108">サービスエンドポイントは、次の情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="5d287-108">A service endpoint specifies the following information:</span></span>

- <span data-ttu-id="5d287-109">サービスを検索できるアドレス。</span><span class="sxs-lookup"><span data-stu-id="5d287-109">An address where you can find the service.</span></span>
- <span data-ttu-id="5d287-110">クライアントがサービスと通信する方法を説明する情報を格納しているバインディング。</span><span class="sxs-lookup"><span data-stu-id="5d287-110">A binding that contains the information that describes how a client must communicate with the service.</span></span>
- <span data-ttu-id="5d287-111">サービスがクライアントに提供する機能を定義するコントラクト。</span><span class="sxs-lookup"><span data-stu-id="5d287-111">A contract that defines the functionality that the service provides to its clients.</span></span>

<span data-ttu-id="5d287-112">このチュートリアルでは、次の作業を行う方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="5d287-112">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="5d287-113">WCF サービスをホストするためのコンソールアプリプロジェクトを作成して構成します。</span><span class="sxs-lookup"><span data-stu-id="5d287-113">Create and configure a console app project for hosting a WCF service.</span></span>
> - <span data-ttu-id="5d287-114">WCF サービスをホストするコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="5d287-114">Add code to host the WCF service.</span></span>
> - <span data-ttu-id="5d287-115">構成ファイルを更新します。</span><span class="sxs-lookup"><span data-stu-id="5d287-115">Update the configuration file.</span></span>
> - <span data-ttu-id="5d287-116">WCF サービスを開始し、実行されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="5d287-116">Start the WCF service and verify it's running.</span></span>

## <a name="create-and-configure-a-console-app-project-for-hosting-the-service"></a><span data-ttu-id="5d287-117">サービスをホストするためのコンソールアプリプロジェクトを作成して構成する</span><span class="sxs-lookup"><span data-stu-id="5d287-117">Create and configure a console app project for hosting the service</span></span>

1. <span data-ttu-id="5d287-118">Visual Studio でコンソールアプリプロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="5d287-118">Create a console app project in Visual Studio:</span></span>

    1. <span data-ttu-id="5d287-119">[**ファイル**] メニューの [プロジェクト/ソリューションを**開く**] を選択し、前の作業で作成し  >  **Project/Solution**た**gettingstarted** (*gettingstarted. .sln*) を参照します。</span><span class="sxs-lookup"><span data-stu-id="5d287-119">From the **File** menu, select **Open** > **Project/Solution** and browse to the **GettingStarted** solution you previously created (*GettingStarted.sln*).</span></span> <span data-ttu-id="5d287-120">**[Open (開く)]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="5d287-120">Select **Open**.</span></span>

    2. <span data-ttu-id="5d287-121">[**表示**] メニューの [**ソリューションエクスプローラー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5d287-121">From the **View** menu, select **Solution Explorer**.</span></span>

    3. <span data-ttu-id="5d287-122">[**ソリューションエクスプローラー** ] ウィンドウで、[ **gettingstarted** ] ソリューション (最上位ノード) を選択**Add**し、  >  ショートカットメニューの [**新しいプロジェクト**の追加] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5d287-122">In the **Solution Explorer** window, select the **GettingStarted** solution (top node), and then select **Add** > **New Project** from the shortcut menu.</span></span>

    4. <span data-ttu-id="5d287-123">[**新しいプロジェクトの追加**] ウィンドウの左側にある [ **Visual C#** ] または [ **Visual Basic**] の下にある [ **Windows デスクトップ**] カテゴリを選択します。</span><span class="sxs-lookup"><span data-stu-id="5d287-123">In the **Add New Project** window, on the left side, select the **Windows Desktop** category under **Visual C#** or **Visual Basic**.</span></span>

    5. <span data-ttu-id="5d287-124">[**コンソールアプリ (.NET Framework)** ] テンプレートを選択し、**名前**として「 *gettingon host* 」と入力します。</span><span class="sxs-lookup"><span data-stu-id="5d287-124">Select the **Console App (.NET Framework)** template, and enter *GettingStartedHost* for the **Name**.</span></span> <span data-ttu-id="5d287-125">**[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="5d287-125">Select **OK**.</span></span>

2. <span data-ttu-id="5d287-126">**Gettingのホスト**プロジェクトに参照を追加して、 **Getting: lib**プロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="5d287-126">Add a reference in the **GettingStartedHost** project to the **GettingStartedLib** project:</span></span>

    1. <span data-ttu-id="5d287-127">[**ソリューションエクスプローラー** ] ウィンドウで、 **Gettingのホスト**プロジェクトの下にある [**参照**] フォルダーを選択し、ショートカットメニューの [**参照の追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5d287-127">In the **Solution Explorer** window, select the **References** folder under the **GettingStartedHost** project, and then select **Add Reference** from the shortcut menu.</span></span>

    2. <span data-ttu-id="5d287-128">[**参照の追加**] ダイアログボックスで、ウィンドウの左側にある [**プロジェクト**] の下にある [**ソリューション**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5d287-128">In the **Add Reference** dialog, under **Projects** on the left side of the window, select **Solution**.</span></span>

    3. <span data-ttu-id="5d287-129">ウィンドウの中央のセクションで [ **Getting] lib**を選択し、[ **OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="5d287-129">Select **GettingStartedLib** in the center section of the window, and then select **OK**.</span></span>

       <span data-ttu-id="5d287-130">このアクションにより、gettingの**lib**プロジェクトで定義されている型が**Gettingのホスト**プロジェクトで使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="5d287-130">This action makes the types defined in the **GettingStartedLib** project available to the **GettingStartedHost** project.</span></span>

3. <span data-ttu-id="5d287-131">**Gettingのホスト**プロジェクトで、アセンブリに参照を追加し <xref:System.ServiceModel> ます。</span><span class="sxs-lookup"><span data-stu-id="5d287-131">Add a reference in the **GettingStartedHost** project to the <xref:System.ServiceModel> assembly:</span></span>

    1. <span data-ttu-id="5d287-132">[**ソリューションエクスプローラー** ] ウィンドウで、 **Gettingのホスト**プロジェクトの下にある [**参照**] フォルダーを選択し、ショートカットメニューの [**参照の追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5d287-132">In the **Solution Explorer** window, select the **References** folder under the **GettingStartedHost** project, and then select **Add Reference** from the shortcut menu.</span></span>

    2. <span data-ttu-id="5d287-133">[**参照の追加**] ウィンドウの左側にある [**アセンブリ**] で、[**フレームワーク**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5d287-133">In the **Add Reference** window, under **Assemblies** on the left side of the window, select **Framework**.</span></span>

    3. <span data-ttu-id="5d287-134">[ **System.servicemodel**] を選択し、[ **OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="5d287-134">Select **System.ServiceModel**, and then select **OK**.</span></span>

    4. <span data-ttu-id="5d287-135">[**ファイル**] [  >  **すべて保存**] の順に選択して、ソリューションを保存します。</span><span class="sxs-lookup"><span data-stu-id="5d287-135">Save the solution by selecting **File** > **Save All**.</span></span>

## <a name="add-code-to-host-the-service"></a><span data-ttu-id="5d287-136">サービスをホストするコードを追加する</span><span class="sxs-lookup"><span data-stu-id="5d287-136">Add code to host the service</span></span>

<span data-ttu-id="5d287-137">サービスをホストするには、次の手順を実行するコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="5d287-137">To host the service, you add code to do the following steps:</span></span>

1. <span data-ttu-id="5d287-138">ベースアドレスの URI を作成します。</span><span class="sxs-lookup"><span data-stu-id="5d287-138">Create a URI for the base address.</span></span>
2. <span data-ttu-id="5d287-139">サービスをホストするためのクラスインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="5d287-139">Create a class instance for hosting the service.</span></span>
3. <span data-ttu-id="5d287-140">サービスエンドポイントを作成します。</span><span class="sxs-lookup"><span data-stu-id="5d287-140">Create a service endpoint.</span></span>
4. <span data-ttu-id="5d287-141">メタデータ交換を有効にします。</span><span class="sxs-lookup"><span data-stu-id="5d287-141">Enable metadata exchange.</span></span>
5. <span data-ttu-id="5d287-142">サービスホストを開いて、受信メッセージをリッスンします。</span><span class="sxs-lookup"><span data-stu-id="5d287-142">Open the service host to listen for incoming messages.</span></span>
  
<span data-ttu-id="5d287-143">コードに次の変更を加えます。</span><span class="sxs-lookup"><span data-stu-id="5d287-143">Make the following changes to the code:</span></span>

1. <span data-ttu-id="5d287-144">**GettingProgram.cs ホスト**プロジェクトの**Program.cs**ファイルまたは module1.vb ファイルを開き、そのコードを次のコードに置き換え**ます。**</span><span class="sxs-lookup"><span data-stu-id="5d287-144">Open the **Program.cs** or **Module1.vb** file in the **GettingStartedHost** project and replace its code with the following code:</span></span>

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
                    selfHost.Description.Behaviors.Add(smb);

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

    <span data-ttu-id="5d287-145">このコードの動作については、「[サービスホスティングプログラムの手順](#service-hosting-program-steps)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5d287-145">For information about how this code works, see [Service hosting program steps](#service-hosting-program-steps).</span></span>

2. <span data-ttu-id="5d287-146">プロジェクトのプロパティを更新します。</span><span class="sxs-lookup"><span data-stu-id="5d287-146">Update the project properties:</span></span>

   1. <span data-ttu-id="5d287-147">[**ソリューションエクスプローラー** ] ウィンドウで、[ **Getting] ホスト**フォルダーを選択し、ショートカットメニューの [**プロパティ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5d287-147">In the **Solution Explorer** window, select the **GettingStartedHost** folder, and then select **Properties** from the shortcut menu.</span></span>

   2. <span data-ttu-id="5d287-148">[ **Gettingon ホスト**のプロパティ] ページで、[**アプリケーション**] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="5d287-148">On the **GettingStartedHost** properties page, select the **Application** tab:</span></span>

      - <span data-ttu-id="5d287-149">C# プロジェクトの場合は、[**スタートアップオブジェクト**] ボックスの一覧から [ **Getting] ホスト**を選択します。</span><span class="sxs-lookup"><span data-stu-id="5d287-149">For C# projects, select **GettingStartedHost.Program** from the **Startup object** list.</span></span>

      - <span data-ttu-id="5d287-150">Visual Basic プロジェクトの場合は、[**スタートアップオブジェクト**] ボックスの一覧から [ **Service. プログラム**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5d287-150">For Visual Basic projects, select **Service.Program** from the **Startup object** list.</span></span>

   3. <span data-ttu-id="5d287-151">[**ファイル**] メニューの [**すべてを保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5d287-151">From the **File** menu, select **Save All**.</span></span>

## <a name="verify-the-service-is-working"></a><span data-ttu-id="5d287-152">サービスが動作していることを確認する</span><span class="sxs-lookup"><span data-stu-id="5d287-152">Verify the service is working</span></span>

1. <span data-ttu-id="5d287-153">ソリューションをビルドし、Visual Studio 内から**Gettingのホスト**コンソールアプリケーションを実行します。</span><span class="sxs-lookup"><span data-stu-id="5d287-153">Build the solution, and then run the **GettingStartedHost** console application from inside Visual Studio.</span></span>

    <span data-ttu-id="5d287-154">サービスは、管理者特権で実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5d287-154">The service must be run with administrator privileges.</span></span> <span data-ttu-id="5d287-155">Visual Studio を管理者特権で開いたので、Visual Studio で**Gettingon ホスト**を実行すると、アプリケーションも管理者特権で実行されます。</span><span class="sxs-lookup"><span data-stu-id="5d287-155">Because you opened Visual Studio with administrator privileges, when you run **GettingStartedHost** in Visual Studio, the application is run with administrator privileges as well.</span></span> <span data-ttu-id="5d287-156">または、管理者として新しいコマンドプロンプトを開き ( **More**  >  ショートカットメニューから [**管理者として実行**] を選択して)、その中で**GettingStartedHost.exe**を実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="5d287-156">As an alternative, you can open a new command prompt as an administrator (select **More** > **Run as administrator** from the shortcut menu) and run **GettingStartedHost.exe** within it.</span></span>

2. <span data-ttu-id="5d287-157">Web ブラウザーを開き、でサービスのページを参照し `http://localhost:8000/GettingStarted/CalculatorService` ます。</span><span class="sxs-lookup"><span data-stu-id="5d287-157">Open a web browser and browse to the service's page at `http://localhost:8000/GettingStarted/CalculatorService`.</span></span>

   > [!NOTE]
   > <span data-ttu-id="5d287-158">このようなサービスでは、リッスンするコンピューターに HTTP アドレスを登録するための適切なアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="5d287-158">Services such as this one require the proper permission to register HTTP addresses on the machine for listening.</span></span> <span data-ttu-id="5d287-159">管理者アカウントにはこのアクセス許可がありますが、管理者以外のアカウントの場合は、HTTP 名前空間へのアクセス許可を付与する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5d287-159">Administrator accounts have this permission, but non-administrator accounts must be granted permission for HTTP namespaces.</span></span> <span data-ttu-id="5d287-160">名前空間の予約を構成する方法については、「[Configuring HTTP and HTTPS](feature-details/configuring-http-and-https.md)」 (HTTP と HTTPS を構成する) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5d287-160">For more information about how to configure namespace reservations, see [Configuring HTTP and HTTPS](feature-details/configuring-http-and-https.md).</span></span>

## <a name="service-hosting-program-steps"></a><span data-ttu-id="5d287-161">サービスホスティングプログラムの手順</span><span class="sxs-lookup"><span data-stu-id="5d287-161">Service hosting program steps</span></span>

<span data-ttu-id="5d287-162">サービスをホストするために追加したコードの手順は、次のように記述されています。</span><span class="sxs-lookup"><span data-stu-id="5d287-162">The steps in the code you added to host the service are described as follows:</span></span>

- <span data-ttu-id="5d287-163">**手順 1**: `Uri` サービスのベースアドレスを保持するクラスのインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="5d287-163">**Step 1**: Create an instance of the `Uri` class to hold the base address of the service.</span></span> <span data-ttu-id="5d287-164">ベースアドレスを含む URL には、サービスを識別する省略可能な URI があります。</span><span class="sxs-lookup"><span data-stu-id="5d287-164">A URL that contains a base address has an optional URI that identifies a service.</span></span> <span data-ttu-id="5d287-165">ベースアドレスは、のように書式設定され `<transport>://<machine-name or domain><:optional port #>/<optional URI segment>` ます。</span><span class="sxs-lookup"><span data-stu-id="5d287-165">The base address is formatted as follows: `<transport>://<machine-name or domain><:optional port #>/<optional URI segment>`.</span></span> <span data-ttu-id="5d287-166">電卓サービスのベースアドレスは、HTTP トランスポート、localhost、ポート8000、および URI セグメント (GettingStarted) を使用します。</span><span class="sxs-lookup"><span data-stu-id="5d287-166">The base address for the calculator service uses the HTTP transport, localhost, port 8000, and the URI segment, GettingStarted.</span></span>

- <span data-ttu-id="5d287-167">**手順 2**: <xref:System.ServiceModel.ServiceHost> サービスをホストするために使用するクラスのインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="5d287-167">**Step 2**: Create an instance of the <xref:System.ServiceModel.ServiceHost> class, which you use to host the service.</span></span> <span data-ttu-id="5d287-168">コンストラクターは、サービスコントラクトを実装するクラスの型とサービスのベースアドレスの2つのパラメーターを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="5d287-168">The constructor takes two parameters: the type of the class that implements the service contract and the base address of the service.</span></span>

- <span data-ttu-id="5d287-169">**手順 3**: インスタンスを作成 <xref:System.ServiceModel.Description.ServiceEndpoint> します。</span><span class="sxs-lookup"><span data-stu-id="5d287-169">**Step 3**: Create a <xref:System.ServiceModel.Description.ServiceEndpoint> instance.</span></span> <span data-ttu-id="5d287-170">サービス エンドポイントは、アドレス、バインディング、およびサービス コントラクトから構成されます。</span><span class="sxs-lookup"><span data-stu-id="5d287-170">A service endpoint is composed of an address, a binding, and a service contract.</span></span> <span data-ttu-id="5d287-171"><xref:System.ServiceModel.Description.ServiceEndpoint>コンストラクターは、サービスコントラクトインターフェイスの型、バインディング、およびアドレスで構成されます。</span><span class="sxs-lookup"><span data-stu-id="5d287-171">The <xref:System.ServiceModel.Description.ServiceEndpoint> constructor is composed of the service contract interface type, a binding, and an address.</span></span> <span data-ttu-id="5d287-172">サービス コントラクトは、サービス型に定義および実装した `ICalculator` です。</span><span class="sxs-lookup"><span data-stu-id="5d287-172">The service contract is `ICalculator`, which you defined and implement in the service type.</span></span> <span data-ttu-id="5d287-173">このサンプルのバインドは、組み込みのバインドであり、 <xref:System.ServiceModel.WSHttpBinding> WS-\* 仕様に準拠するエンドポイントに接続されています。</span><span class="sxs-lookup"><span data-stu-id="5d287-173">The binding for this sample is <xref:System.ServiceModel.WSHttpBinding>, which is a built-in binding and connects to endpoints that conform to the WS-\* specifications.</span></span> <span data-ttu-id="5d287-174">WCF バインディングの詳細については、「 [wcf バインディングの概要](bindings-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5d287-174">For more information about WCF bindings, see [WCF bindings overview](bindings-overview.md).</span></span> <span data-ttu-id="5d287-175">アドレスをベースアドレスに追加して、エンドポイントを識別します。</span><span class="sxs-lookup"><span data-stu-id="5d287-175">You append the address to the base address to identify the endpoint.</span></span> <span data-ttu-id="5d287-176">このコードでは、このアドレスを計算し、そのエンドポイントの完全修飾アドレスをとして指定し `http://localhost:8000/GettingStarted/CalculatorService` ます。</span><span class="sxs-lookup"><span data-stu-id="5d287-176">The code specifies the address as CalculatorService and the fully qualified address for the endpoint as `http://localhost:8000/GettingStarted/CalculatorService`.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="5d287-177">.NET Framework バージョン4以降では、サービスエンドポイントの追加は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="5d287-177">For .NET Framework Version 4 and later, adding a service endpoint is optional.</span></span> <span data-ttu-id="5d287-178">これらのバージョンでは、コードまたは構成を追加しないと、サービスによって実装されたベースアドレスとコントラクトの組み合わせごとに既定のエンドポイントが1つ追加されます。</span><span class="sxs-lookup"><span data-stu-id="5d287-178">For these versions, if you don't add your code or configuration, WCF adds one default endpoint for each combination of base address and contract implemented by the service.</span></span> <span data-ttu-id="5d287-179">既定のエンドポイントの詳細については、「[エンドポイントアドレスの指定](specifying-an-endpoint-address.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5d287-179">For more information about default endpoints, see [Specifying an endpoint address](specifying-an-endpoint-address.md).</span></span> <span data-ttu-id="5d287-180">既定のエンドポイント、バインディング、および動作の詳細については、「簡略化された[構成](simplified-configuration.md)と[WCF サービスの簡略化](samples/simplified-configuration-for-wcf-services.md)された構成」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5d287-180">For more information about default endpoints, bindings, and behaviors, see [Simplified configuration](simplified-configuration.md) and [Simplified configuration for WCF services](samples/simplified-configuration-for-wcf-services.md).</span></span>

- <span data-ttu-id="5d287-181">**手順 4**: メタデータ交換を有効にします。</span><span class="sxs-lookup"><span data-stu-id="5d287-181">**Step 4**: Enable metadata exchange.</span></span> <span data-ttu-id="5d287-182">クライアントは、メタデータ交換を使用して、サービス操作を呼び出すためのプロキシを生成します。</span><span class="sxs-lookup"><span data-stu-id="5d287-182">Clients use metadata exchange to generate proxies for calling the service operations.</span></span> <span data-ttu-id="5d287-183">メタデータ交換を有効にするには、インスタンスを作成し、 <xref:System.ServiceModel.Description.ServiceMetadataBehavior> その <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpGetEnabled> プロパティをに設定 `true` して、 `ServiceMetadataBehavior` オブジェクトを <xref:System.ServiceModel.Description.ServiceDescription.Behaviors%2A> インスタンスのコレクションに追加し <xref:System.ServiceModel.ServiceHost> ます。</span><span class="sxs-lookup"><span data-stu-id="5d287-183">To enable metadata exchange, create a <xref:System.ServiceModel.Description.ServiceMetadataBehavior> instance, set its <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpGetEnabled> property to `true`, and add the `ServiceMetadataBehavior` object to the <xref:System.ServiceModel.Description.ServiceDescription.Behaviors%2A> collection of the <xref:System.ServiceModel.ServiceHost> instance.</span></span>

- <span data-ttu-id="5d287-184">**手順 5**: <xref:System.ServiceModel.ServiceHost> を開き、受信メッセージをリッスンします。</span><span class="sxs-lookup"><span data-stu-id="5d287-184">**Step 5**: Open <xref:System.ServiceModel.ServiceHost> to listen for incoming messages.</span></span> <span data-ttu-id="5d287-185">アプリケーションは、 **enter**キーを押すまで待機します。</span><span class="sxs-lookup"><span data-stu-id="5d287-185">The application waits for you to press **Enter**.</span></span> <span data-ttu-id="5d287-186">アプリケーションがインスタンス化されると <xref:System.ServiceModel.ServiceHost> 、try/catch ブロックが実行されます。</span><span class="sxs-lookup"><span data-stu-id="5d287-186">After the application instantiates <xref:System.ServiceModel.ServiceHost>, it executes a try/catch block.</span></span> <span data-ttu-id="5d287-187">によってスローされる例外を安全にキャッチする方法の詳細につい <xref:System.ServiceModel.ServiceHost> ては、「 [Close と Abort を使用して WCF クライアントリソースを解放する](samples/use-close-abort-release-wcf-client-resources.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5d287-187">For more information about safely catching exceptions thrown by <xref:System.ServiceModel.ServiceHost>, see [Use Close and Abort to release WCF client resources](samples/use-close-abort-release-wcf-client-resources.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5d287-188">WCF サービスライブラリを追加すると、サービスホストを起動してデバッグする場合、Visual Studio はそれをホストします。</span><span class="sxs-lookup"><span data-stu-id="5d287-188">When you add a WCF service library, Visual Studio hosts it for you if you debug it by starting a service host.</span></span> <span data-ttu-id="5d287-189">競合を回避するために、Visual Studio が WCF サービスライブラリをホストしないようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="5d287-189">To avoid conflicts, you can prevent Visual Studio from hosting the WCF service library.</span></span>
>
> 1. <span data-ttu-id="5d287-190">**ソリューションエクスプローラー**で**Gettingの lib**プロジェクトを選択し、ショートカットメニューの [**プロパティ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5d287-190">Select the **GettingStartedLib** project in **Solution Explorer** and choose **Properties** from the shortcut menu.</span></span>
> 2. <span data-ttu-id="5d287-191">[ **Wcf オプション**] を選択し、**同じソリューションで別のプロジェクトをデバッグするときに [wcf サービスホストを開始する**] チェックボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="5d287-191">Select **WCF Options** and uncheck **Start WCF Service Host when debugging another project in the same solution**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="5d287-192">次の手順</span><span class="sxs-lookup"><span data-stu-id="5d287-192">Next steps</span></span>

<span data-ttu-id="5d287-193">このチュートリアルでは、以下の内容を学習しました。</span><span class="sxs-lookup"><span data-stu-id="5d287-193">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="5d287-194">WCF サービスをホストするためのコンソールアプリプロジェクトを作成して構成します。</span><span class="sxs-lookup"><span data-stu-id="5d287-194">Create and configure a console app project for hosting a WCF service.</span></span>
> - <span data-ttu-id="5d287-195">WCF サービスをホストするコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="5d287-195">Add code to host the WCF service.</span></span>
> - <span data-ttu-id="5d287-196">構成ファイルを更新します。</span><span class="sxs-lookup"><span data-stu-id="5d287-196">Update the configuration file.</span></span>
> - <span data-ttu-id="5d287-197">WCF サービスを開始し、実行されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="5d287-197">Start the WCF service and verify it's running.</span></span>

<span data-ttu-id="5d287-198">次のチュートリアルに進み、WCF クライアントを作成する方法を学習してください。</span><span class="sxs-lookup"><span data-stu-id="5d287-198">Advance to the next tutorial to learn how to create a WCF client.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="5d287-199">チュートリアル: WCF クライアントを作成する</span><span class="sxs-lookup"><span data-stu-id="5d287-199">Tutorial: Create a WCF client</span></span>](how-to-create-a-wcf-client.md)
