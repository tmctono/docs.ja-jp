---
title: 'チュートリアル: 基本的な Windows コミュニケーション ファウンデーション サービスをホストして実行する'
ms.date: 03/19/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF services [WCF]
- WCF services [WCF], running
ms.assetid: 31774d36-923b-4e2d-812e-aa190127266f
ms.openlocfilehash: 30eb86987b83427b94c6fff22755cde3d73dd9f0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184084"
---
# <a name="tutorial-host-and-run-a-basic-windows-communication-foundation-service"></a><span data-ttu-id="d314a-102">チュートリアル: 基本的な Windows コミュニケーション ファウンデーション サービスをホストして実行する</span><span class="sxs-lookup"><span data-stu-id="d314a-102">Tutorial: Host and run a basic Windows Communication Foundation service</span></span>

<span data-ttu-id="d314a-103">このチュートリアルでは、基本的な Wcf (WCF) アプリケーションを作成するために必要な 5 つのタスクの 3 つ目について説明します。</span><span class="sxs-lookup"><span data-stu-id="d314a-103">This tutorial describes the third of five tasks required to create a basic Windows Communication Foundation (WCF) application.</span></span> <span data-ttu-id="d314a-104">チュートリアルの概要については、「[チュートリアル: Windows コミュニケーションファウンデーション アプリケーションの概要](getting-started-tutorial.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d314a-104">For an overview of the tutorials, see [Tutorial: Get started with Windows Communication Foundation applications](getting-started-tutorial.md).</span></span>

<span data-ttu-id="d314a-105">WCF アプリケーションを作成するための次のタスクは、コンソール アプリケーションで WCF サービスをホストすることです。</span><span class="sxs-lookup"><span data-stu-id="d314a-105">The next task for creating a WCF application is to host a WCF service in a console application.</span></span> <span data-ttu-id="d314a-106">WCF サービスは、 1 つ以上のエンドポイントを公開し *、* 各エンドポイントは 1 つ以上のサービス操作を公開します。</span><span class="sxs-lookup"><span data-stu-id="d314a-106">A WCF service exposes one or more *endpoints*, each of which exposes one or more service operations.</span></span> <span data-ttu-id="d314a-107">サービス エンドポイントは、次の情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="d314a-107">A service endpoint specifies the following information:</span></span>

- <span data-ttu-id="d314a-108">サービスを検索できるアドレス。</span><span class="sxs-lookup"><span data-stu-id="d314a-108">An address where you can find the service.</span></span>
- <span data-ttu-id="d314a-109">クライアントがサービスと通信する方法を説明する情報を含むバインディング。</span><span class="sxs-lookup"><span data-stu-id="d314a-109">A binding that contains the information that describes how a client must communicate with the service.</span></span>
- <span data-ttu-id="d314a-110">サービスがクライアントに提供する機能を定義するコントラクト。</span><span class="sxs-lookup"><span data-stu-id="d314a-110">A contract that defines the functionality that the service provides to its clients.</span></span>

<span data-ttu-id="d314a-111">このチュートリアルでは、以下の内容を学習します。</span><span class="sxs-lookup"><span data-stu-id="d314a-111">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="d314a-112">WCF サービスをホストするためのコンソール アプリ プロジェクトを作成して構成します。</span><span class="sxs-lookup"><span data-stu-id="d314a-112">Create and configure a console app project for hosting a WCF service.</span></span>
> - <span data-ttu-id="d314a-113">WCF サービスをホストするコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="d314a-113">Add code to host the WCF service.</span></span>
> - <span data-ttu-id="d314a-114">構成ファイルを更新します。</span><span class="sxs-lookup"><span data-stu-id="d314a-114">Update the configuration file.</span></span>
> - <span data-ttu-id="d314a-115">WCF サービスを起動し、実行中であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="d314a-115">Start the WCF service and verify it's running.</span></span>

## <a name="create-and-configure-a-console-app-project-for-hosting-the-service"></a><span data-ttu-id="d314a-116">サービスをホストするためのコンソール アプリ プロジェクトを作成および構成する</span><span class="sxs-lookup"><span data-stu-id="d314a-116">Create and configure a console app project for hosting the service</span></span>

1. <span data-ttu-id="d314a-117">Visual Studio でコンソール アプリ プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="d314a-117">Create a console app project in Visual Studio:</span></span>

    1. <span data-ttu-id="d314a-118">[**ファイル]** メニューの [**プロジェクト/ソリューション**を**開く** > ] を選択し、以前に作成した **[はじめに]** ソリューション (*GettingStarted.sln*) を参照します。</span><span class="sxs-lookup"><span data-stu-id="d314a-118">From the **File** menu, select **Open** > **Project/Solution** and browse to the **GettingStarted** solution you previously created (*GettingStarted.sln*).</span></span> <span data-ttu-id="d314a-119">**[開く]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="d314a-119">Select **Open**.</span></span>

    2. <span data-ttu-id="d314a-120">[**表示**] メニューの [**ソリューション エクスプローラ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d314a-120">From the **View** menu, select **Solution Explorer**.</span></span>

    3. <span data-ttu-id="d314a-121">[**ソリューション エクスプローラー** ] ウィンドウで **、"はじめに"** ソリューション (最上位ノード) を選択し、ショートカット メニューから **[新しいプロジェクト**の**追加** > ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="d314a-121">In the **Solution Explorer** window, select the **GettingStarted** solution (top node), and then select **Add** > **New Project** from the shortcut menu.</span></span>

    4. <span data-ttu-id="d314a-122">[**新しいプロジェクトの追加**] ウィンドウの左側で **、[Visual C#** または Visual **Basic]** の下にある **[Windows デスクトップ**] カテゴリを選択します。</span><span class="sxs-lookup"><span data-stu-id="d314a-122">In the **Add New Project** window, on the left side, select the **Windows Desktop** category under **Visual C#** or **Visual Basic**.</span></span>

    5. <span data-ttu-id="d314a-123">コンソール**アプリケーション (.NET Framework)** テンプレートを選択し、\**名前\*\*\*に「開始開始ホスト」* と入力します。</span><span class="sxs-lookup"><span data-stu-id="d314a-123">Select the **Console App (.NET Framework)** template, and enter *GettingStartedHost* for the **Name**.</span></span> <span data-ttu-id="d314a-124">**[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="d314a-124">Select **OK**.</span></span>

2. <span data-ttu-id="d314a-125">**プロジェクトに**参照を追加します。 **GettingStartedLib**</span><span class="sxs-lookup"><span data-stu-id="d314a-125">Add a reference in the **GettingStartedHost** project to the **GettingStartedLib** project:</span></span>

    1. <span data-ttu-id="d314a-126">**[ソリューション エクスプローラー** ] ウィンドウで **、GettingStartedHost**プロジェクトの下にある **[参照**] フォルダーを選択し、ショートカット メニューの **[参照の追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="d314a-126">In the **Solution Explorer** window, select the **References** folder under the **GettingStartedHost** project, and then select **Add Reference** from the shortcut menu.</span></span>

    2. <span data-ttu-id="d314a-127">[**参照の追加]** ダイアログの左側の [**プロジェクト**] で、[**ソリューション**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="d314a-127">In the **Add Reference** dialog, under **Projects** on the left side of the window, select **Solution**.</span></span>

    3. <span data-ttu-id="d314a-128">ウィンドウの中央のセクションで [**開始] を**選択し **、[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="d314a-128">Select **GettingStartedLib** in the center section of the window, and then select **OK**.</span></span>

       <span data-ttu-id="d314a-129">このアクションにより、次の操作を**行**うと、プロジェクトで定義された型が**使用**できるようになります。</span><span class="sxs-lookup"><span data-stu-id="d314a-129">This action makes the types defined in the **GettingStartedLib** project available to the **GettingStartedHost** project.</span></span>

3. <span data-ttu-id="d314a-130">**アセンブリに参照を追加します**<xref:System.ServiceModel>。</span><span class="sxs-lookup"><span data-stu-id="d314a-130">Add a reference in the **GettingStartedHost** project to the <xref:System.ServiceModel> assembly:</span></span>

    1. <span data-ttu-id="d314a-131">**[ソリューション エクスプローラー** ] ウィンドウで **、GettingStartedHost**プロジェクトの下にある **[参照**] フォルダーを選択し、ショートカット メニューの **[参照の追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="d314a-131">In the **Solution Explorer** window, select the **References** folder under the **GettingStartedHost** project, and then select **Add Reference** from the shortcut menu.</span></span>

    2. <span data-ttu-id="d314a-132">[**参照の追加**] ウィンドウの左側にある **[アセンブリ**] で、[**フレームワーク**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="d314a-132">In the **Add Reference** window, under **Assemblies** on the left side of the window, select **Framework**.</span></span>

    3. <span data-ttu-id="d314a-133">[**システム.サービスモデル**] を選択し **、[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="d314a-133">Select **System.ServiceModel**, and then select **OK**.</span></span>

    4. <span data-ttu-id="d314a-134">[ファイルをすべて保存] を選択してソリューション**を** > **保存**します。</span><span class="sxs-lookup"><span data-stu-id="d314a-134">Save the solution by selecting **File** > **Save All**.</span></span>

## <a name="add-code-to-host-the-service"></a><span data-ttu-id="d314a-135">サービスをホストするコードを追加する</span><span class="sxs-lookup"><span data-stu-id="d314a-135">Add code to host the service</span></span>

<span data-ttu-id="d314a-136">サービスをホストするには、次の手順を実行するコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="d314a-136">To host the service, you add code to do the following steps:</span></span>

1. <span data-ttu-id="d314a-137">ベース アドレスの URI を作成します。</span><span class="sxs-lookup"><span data-stu-id="d314a-137">Create a URI for the base address.</span></span>
2. <span data-ttu-id="d314a-138">サービスをホストするためのクラス インスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="d314a-138">Create a class instance for hosting the service.</span></span>
3. <span data-ttu-id="d314a-139">サービス エンドポイントを作成します。</span><span class="sxs-lookup"><span data-stu-id="d314a-139">Create a service endpoint.</span></span>
4. <span data-ttu-id="d314a-140">メタデータ交換を有効にします。</span><span class="sxs-lookup"><span data-stu-id="d314a-140">Enable metadata exchange.</span></span>
5. <span data-ttu-id="d314a-141">サービス ホストを開いて、受信メッセージをリッスンします。</span><span class="sxs-lookup"><span data-stu-id="d314a-141">Open the service host to listen for incoming messages.</span></span>
  
<span data-ttu-id="d314a-142">コードに次の変更を加えます。</span><span class="sxs-lookup"><span data-stu-id="d314a-142">Make the following changes to the code:</span></span>

1. <span data-ttu-id="d314a-143">**Program.cs**または**Program.cs** **Module1.vb**ファイルを開き、次のコードを使用してコードを置き換えます。</span><span class="sxs-lookup"><span data-stu-id="d314a-143">Open the **Program.cs** or **Module1.vb** file in the **GettingStartedHost** project and replace its code with the following code:</span></span>

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

    <span data-ttu-id="d314a-144">このコードの動作については、「[サービス ホスティング プログラムの手順](#service-hosting-program-steps)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d314a-144">For information about how this code works, see [Service hosting program steps](#service-hosting-program-steps).</span></span>

2. <span data-ttu-id="d314a-145">プロジェクトプロパティを更新します。</span><span class="sxs-lookup"><span data-stu-id="d314a-145">Update the project properties:</span></span>

   1. <span data-ttu-id="d314a-146">**[ソリューション エクスプローラー** ] ウィンドウで **、"GettingStartedHost"** フォルダーを選択し、ショートカット メニューの **[プロパティ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d314a-146">In the **Solution Explorer** window, select the **GettingStartedHost** folder, and then select **Properties** from the shortcut menu.</span></span>

   2. <span data-ttu-id="d314a-147">[**開始開始ホスト**のプロパティ] ページで、[**アプリケーション**] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="d314a-147">On the **GettingStartedHost** properties page, select the **Application** tab:</span></span>

      - <span data-ttu-id="d314a-148">C# プロジェクトの場合は、[**スタートアップ オブジェクト**] リスト**から [開始開始ホスト.プログラム**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="d314a-148">For C# projects, select **GettingStartedHost.Program** from the **Startup object** list.</span></span>

      - <span data-ttu-id="d314a-149">Visual Basic プロジェクトの場合は、[スタートアップ**オブジェクト**] ボックスの一覧から [**サービス.プログラム**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="d314a-149">For Visual Basic projects, select **Service.Program** from the **Startup object** list.</span></span>

   3. <span data-ttu-id="d314a-150">[**ファイル]** メニューの [**すべて保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d314a-150">From the **File** menu, select **Save All**.</span></span>

## <a name="verify-the-service-is-working"></a><span data-ttu-id="d314a-151">サービスが動作していることを確認する</span><span class="sxs-lookup"><span data-stu-id="d314a-151">Verify the service is working</span></span>

1. <span data-ttu-id="d314a-152">ソリューションをビルドし、Visual Studio 内から**開始開始ホスト**コンソール アプリケーションを実行します。</span><span class="sxs-lookup"><span data-stu-id="d314a-152">Build the solution, and then run the **GettingStartedHost** console application from inside Visual Studio.</span></span>

    <span data-ttu-id="d314a-153">サービスは管理者権限で実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d314a-153">The service must be run with administrator privileges.</span></span> <span data-ttu-id="d314a-154">管理者特権で Visual Studio を開いたので、Visual Studio で**GettingStartedHost**を実行すると、アプリケーションも管理者特権で実行されます。</span><span class="sxs-lookup"><span data-stu-id="d314a-154">Because you opened Visual Studio with administrator privileges, when you run **GettingStartedHost** in Visual Studio, the application is run with administrator privileges as well.</span></span> <span data-ttu-id="d314a-155">代わりに、新しいコマンド プロンプトを管理者として開き (ショートカット メニューから [**管理者として\*\*\*\*実行を増やす** > ] を選択) し、その中で**GettingStartedHost.exe を**実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="d314a-155">As an alternative, you can open a new command prompt as an administrator (select **More** > **Run as administrator** from the shortcut menu) and run **GettingStartedHost.exe** within it.</span></span>

2. <span data-ttu-id="d314a-156">Web ブラウザを開き、 でサービスのページを`http://localhost:8000/GettingStarted/CalculatorService`参照します。</span><span class="sxs-lookup"><span data-stu-id="d314a-156">Open a web browser and browse to the service's page at `http://localhost:8000/GettingStarted/CalculatorService`.</span></span>

   > [!NOTE]
   > <span data-ttu-id="d314a-157">このようなサービスには、リッスンするためにコンピュータに HTTP アドレスを登録するための適切なアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="d314a-157">Services such as this one require the proper permission to register HTTP addresses on the machine for listening.</span></span> <span data-ttu-id="d314a-158">管理者アカウントにはこのアクセス許可がありますが、管理者以外のアカウントの場合は、HTTP 名前空間へのアクセス許可を付与する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d314a-158">Administrator accounts have this permission, but non-administrator accounts must be granted permission for HTTP namespaces.</span></span> <span data-ttu-id="d314a-159">名前空間の予約を構成する方法については、「[Configuring HTTP and HTTPS](feature-details/configuring-http-and-https.md)」 (HTTP と HTTPS を構成する) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d314a-159">For more information about how to configure namespace reservations, see [Configuring HTTP and HTTPS](feature-details/configuring-http-and-https.md).</span></span>

## <a name="service-hosting-program-steps"></a><span data-ttu-id="d314a-160">サービス ホスティング プログラムの手順</span><span class="sxs-lookup"><span data-stu-id="d314a-160">Service hosting program steps</span></span>

<span data-ttu-id="d314a-161">サービスをホストするために追加したコードの手順は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="d314a-161">The steps in the code you added to host the service are described as follows:</span></span>

- <span data-ttu-id="d314a-162">**手順 1**: サービスの`Uri`ベース アドレスを保持するクラスのインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="d314a-162">**Step 1**: Create an instance of the `Uri` class to hold the base address of the service.</span></span> <span data-ttu-id="d314a-163">ベース アドレスを含む URL には、サービスを識別する省略可能な URI があります。</span><span class="sxs-lookup"><span data-stu-id="d314a-163">A URL that contains a base address has an optional URI that identifies a service.</span></span> <span data-ttu-id="d314a-164">ベース アドレスは、次のように書式設定されます。 `<transport>://<machine-name or domain><:optional port #>/<optional URI segment>`</span><span class="sxs-lookup"><span data-stu-id="d314a-164">The base address is formatted as follows: `<transport>://<machine-name or domain><:optional port #>/<optional URI segment>`.</span></span> <span data-ttu-id="d314a-165">計算機サービスのベース アドレスは、HTTP トランスポート、ローカル ホスト、ポート 8000、および URI セグメントである [はじめに] を使用します。</span><span class="sxs-lookup"><span data-stu-id="d314a-165">The base address for the calculator service uses the HTTP transport, localhost, port 8000, and the URI segment, GettingStarted.</span></span>

- <span data-ttu-id="d314a-166">**手順 2**: サービスの<xref:System.ServiceModel.ServiceHost>ホストに使用するクラスのインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="d314a-166">**Step 2**: Create an instance of the <xref:System.ServiceModel.ServiceHost> class, which you use to host the service.</span></span> <span data-ttu-id="d314a-167">コンストラクターは、サービス コントラクトを実装するクラスの型とサービスのベース アドレスという 2 つのパラメーターを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="d314a-167">The constructor takes two parameters: the type of the class that implements the service contract and the base address of the service.</span></span>

- <span data-ttu-id="d314a-168">**ステップ 3**:<xref:System.ServiceModel.Description.ServiceEndpoint>インスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="d314a-168">**Step 3**: Create a <xref:System.ServiceModel.Description.ServiceEndpoint> instance.</span></span> <span data-ttu-id="d314a-169">サービス エンドポイントは、アドレス、バインディング、およびサービス コントラクトから構成されます。</span><span class="sxs-lookup"><span data-stu-id="d314a-169">A service endpoint is composed of an address, a binding, and a service contract.</span></span> <span data-ttu-id="d314a-170">コンストラクター<xref:System.ServiceModel.Description.ServiceEndpoint>は、サービス コントラクト インターフェイス型、バインディング、およびアドレスで構成されます。</span><span class="sxs-lookup"><span data-stu-id="d314a-170">The <xref:System.ServiceModel.Description.ServiceEndpoint> constructor is composed of the service contract interface type, a binding, and an address.</span></span> <span data-ttu-id="d314a-171">サービス コントラクトは、サービス型に定義および実装した `ICalculator` です。</span><span class="sxs-lookup"><span data-stu-id="d314a-171">The service contract is `ICalculator`, which you defined and implement in the service type.</span></span> <span data-ttu-id="d314a-172">このサンプルのバインディングは<xref:System.ServiceModel.WSHttpBinding>、組み込みバインディングであり、WS-\* 仕様に準拠するエンドポイントに接続します。</span><span class="sxs-lookup"><span data-stu-id="d314a-172">The binding for this sample is <xref:System.ServiceModel.WSHttpBinding>, which is a built-in binding and connects to endpoints that conform to the WS-\* specifications.</span></span> <span data-ttu-id="d314a-173">WCF バインドの詳細については、「 [WCF バインドの概要](bindings-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d314a-173">For more information about WCF bindings, see [WCF bindings overview](bindings-overview.md).</span></span> <span data-ttu-id="d314a-174">アドレスをベース アドレスに追加して、エンドポイントを識別します。</span><span class="sxs-lookup"><span data-stu-id="d314a-174">You append the address to the base address to identify the endpoint.</span></span> <span data-ttu-id="d314a-175">コードでは、アドレスを CalculatorService として指定し、エンドポイントの完全修飾アドレス`http://localhost:8000/GettingStarted/CalculatorService`を .</span><span class="sxs-lookup"><span data-stu-id="d314a-175">The code specifies the address as CalculatorService and the fully qualified address for the endpoint as `http://localhost:8000/GettingStarted/CalculatorService`.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="d314a-176">NET Framework バージョン 4 以降では、サービス エンドポイントの追加はオプションです。</span><span class="sxs-lookup"><span data-stu-id="d314a-176">For .NET Framework Version 4 and later, adding a service endpoint is optional.</span></span> <span data-ttu-id="d314a-177">これらのバージョンでは、コードまたは構成を追加しない場合、WCF は、ベース アドレスとサービスによって実装されるコントラクトの組み合わせごとに 1 つの既定のエンドポイントを追加します。</span><span class="sxs-lookup"><span data-stu-id="d314a-177">For these versions, if you don't add your code or configuration, WCF adds one default endpoint for each combination of base address and contract implemented by the service.</span></span> <span data-ttu-id="d314a-178">既定のエンドポイントの詳細については、エンドポイント[アドレスの指定を](specifying-an-endpoint-address.md)参照してください。</span><span class="sxs-lookup"><span data-stu-id="d314a-178">For more information about default endpoints, see [Specifying an endpoint address](specifying-an-endpoint-address.md).</span></span> <span data-ttu-id="d314a-179">既定のエンドポイント、バインド、および動作の詳細については、「 WCF サービス[の構成の簡略化](simplified-configuration.md)」および「[簡易構成](samples/simplified-configuration-for-wcf-services.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d314a-179">For more information about default endpoints, bindings, and behaviors, see [Simplified configuration](simplified-configuration.md) and [Simplified configuration for WCF services](samples/simplified-configuration-for-wcf-services.md).</span></span>

- <span data-ttu-id="d314a-180">**ステップ 4:** メタデータの交換を有効にします。</span><span class="sxs-lookup"><span data-stu-id="d314a-180">**Step 4**: Enable metadata exchange.</span></span> <span data-ttu-id="d314a-181">クライアントは、メタデータ交換を使用して、サービス操作を呼び出すプロキシを生成します。</span><span class="sxs-lookup"><span data-stu-id="d314a-181">Clients use metadata exchange to generate proxies for calling the service operations.</span></span> <span data-ttu-id="d314a-182">メタデータ交換を有効にするには、インスタンスを<xref:System.ServiceModel.Description.ServiceMetadataBehavior>作成し、その<xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpGetEnabled>プロパティを`true`に設定し`ServiceMetadataBehavior`、オブジェクトを<xref:System.ServiceModel.Description.ServiceDescription.Behaviors%2A>インスタンスのコレクション<xref:System.ServiceModel.ServiceHost>に追加します。</span><span class="sxs-lookup"><span data-stu-id="d314a-182">To enable metadata exchange, create a <xref:System.ServiceModel.Description.ServiceMetadataBehavior> instance, set its <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpGetEnabled> property to `true`, and add the `ServiceMetadataBehavior` object to the <xref:System.ServiceModel.Description.ServiceDescription.Behaviors%2A> collection of the <xref:System.ServiceModel.ServiceHost> instance.</span></span>

- <span data-ttu-id="d314a-183">**ステップ5:** 受信<xref:System.ServiceModel.ServiceHost>メッセージをリッスンするために開きます。</span><span class="sxs-lookup"><span data-stu-id="d314a-183">**Step 5**: Open <xref:System.ServiceModel.ServiceHost> to listen for incoming messages.</span></span> <span data-ttu-id="d314a-184">アプリケーションは **、Enter**キーを押すまで待機します。</span><span class="sxs-lookup"><span data-stu-id="d314a-184">The application waits for you to press **Enter**.</span></span> <span data-ttu-id="d314a-185">アプリケーションは、 の<xref:System.ServiceModel.ServiceHost>インスタンスを作成した後、try/catch ブロックを実行します。</span><span class="sxs-lookup"><span data-stu-id="d314a-185">After the application instantiates <xref:System.ServiceModel.ServiceHost>, it executes a try/catch block.</span></span> <span data-ttu-id="d314a-186">によってスローされる<xref:System.ServiceModel.ServiceHost>例外を安全にキャッチする方法の詳細については、「 [[閉じる] および [中止] を使用して WCF クライアント リソースを解放する](samples/use-close-abort-release-wcf-client-resources.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d314a-186">For more information about safely catching exceptions thrown by <xref:System.ServiceModel.ServiceHost>, see [Use Close and Abort to release WCF client resources](samples/use-close-abort-release-wcf-client-resources.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d314a-187">WCF サービス ライブラリを追加すると、サービス ホストを起動してデバッグする場合は、Visual Studio によってそのライブラリがホストされます。</span><span class="sxs-lookup"><span data-stu-id="d314a-187">When you add a WCF service library, Visual Studio hosts it for you if you debug it by starting a service host.</span></span> <span data-ttu-id="d314a-188">競合を回避するには、Visual Studio が WCF サービス ライブラリをホストしないようにします。</span><span class="sxs-lookup"><span data-stu-id="d314a-188">To avoid conflicts, you can prevent Visual Studio from hosting the WCF service library.</span></span>
>
> 1. <span data-ttu-id="d314a-189">**ソリューション エクスプローラー**で **[FromFromLib]** プロジェクトを選択し、ショートカット メニューの **[プロパティ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d314a-189">Select the **GettingStartedLib** project in **Solution Explorer** and choose **Properties** from the shortcut menu.</span></span>
> 2. <span data-ttu-id="d314a-190">[WCF**オプション]** を選択し、[**同じソリューションで別のプロジェクトをデバッグするときに WCF サービス ホストを開始する**] チェック ボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="d314a-190">Select **WCF Options** and uncheck **Start WCF Service Host when debugging another project in the same solution**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="d314a-191">次のステップ</span><span class="sxs-lookup"><span data-stu-id="d314a-191">Next steps</span></span>

<span data-ttu-id="d314a-192">このチュートリアルでは、以下の内容を学習しました。</span><span class="sxs-lookup"><span data-stu-id="d314a-192">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="d314a-193">WCF サービスをホストするためのコンソール アプリ プロジェクトを作成して構成します。</span><span class="sxs-lookup"><span data-stu-id="d314a-193">Create and configure a console app project for hosting a WCF service.</span></span>
> - <span data-ttu-id="d314a-194">WCF サービスをホストするコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="d314a-194">Add code to host the WCF service.</span></span>
> - <span data-ttu-id="d314a-195">構成ファイルを更新します。</span><span class="sxs-lookup"><span data-stu-id="d314a-195">Update the configuration file.</span></span>
> - <span data-ttu-id="d314a-196">WCF サービスを起動し、実行中であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="d314a-196">Start the WCF service and verify it's running.</span></span>

<span data-ttu-id="d314a-197">WCF クライアントを作成する方法については、次のチュートリアルに進みます。</span><span class="sxs-lookup"><span data-stu-id="d314a-197">Advance to the next tutorial to learn how to create a WCF client.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="d314a-198">チュートリアル: WCF クライアントを作成する</span><span class="sxs-lookup"><span data-stu-id="d314a-198">Tutorial: Create a WCF client</span></span>](how-to-create-a-wcf-client.md)
