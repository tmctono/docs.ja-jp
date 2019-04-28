---
title: 'チュートリアル: ホストおよび基本的な Windows Communication Foundation サービスの実行'
ms.date: 03/19/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF services [WCF]
- WCF services [WCF], running
ms.assetid: 31774d36-923b-4e2d-812e-aa190127266f
ms.openlocfilehash: ad9536b1f27ba3945bf76d0474de4825033a1e8b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61929104"
---
# <a name="tutorial-host-and-run-a-basic-windows-communication-foundation-service"></a><span data-ttu-id="00ce4-102">チュートリアル: ホストおよび基本的な Windows Communication Foundation サービスの実行</span><span class="sxs-lookup"><span data-stu-id="00ce4-102">Tutorial: Host and run a basic Windows Communication Foundation service</span></span>

<span data-ttu-id="00ce4-103">このチュートリアルでは、3 番目の基本的な Windows Communication Foundation (WCF) アプリケーションを作成するために必要な 5 つのタスクについて説明します。</span><span class="sxs-lookup"><span data-stu-id="00ce4-103">This tutorial describes the third of five tasks required to create a basic Windows Communication Foundation (WCF) application.</span></span> <span data-ttu-id="00ce4-104">チュートリアルの概要については、次を参照してください。[チュートリアル。Windows Communication Foundation アプリケーションの概要](getting-started-tutorial.md)します。</span><span class="sxs-lookup"><span data-stu-id="00ce4-104">For an overview of the tutorials, see [Tutorial: Get started with Windows Communication Foundation applications](getting-started-tutorial.md).</span></span>

<span data-ttu-id="00ce4-105">WCF アプリケーションを作成するための次のタスクでは、コンソール アプリケーションで WCF サービスをホストします。</span><span class="sxs-lookup"><span data-stu-id="00ce4-105">The next task for creating a WCF application is to host a WCF service in a console application.</span></span> <span data-ttu-id="00ce4-106">WCF サービスは、1 つまたは複数公開*エンドポイント*、1 つまたは複数のサービス操作を公開します。</span><span class="sxs-lookup"><span data-stu-id="00ce4-106">A WCF service exposes one or more *endpoints*, each of which exposes one or more service operations.</span></span> <span data-ttu-id="00ce4-107">サービス エンドポイントは、次の情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="00ce4-107">A service endpoint specifies the following information:</span></span> 
- <span data-ttu-id="00ce4-108">サービスが得られるアドレスです。</span><span class="sxs-lookup"><span data-stu-id="00ce4-108">An address where you can find the service.</span></span>
- <span data-ttu-id="00ce4-109">クライアントがサービスと通信する必要がある方法を説明する情報を含んでいるバインディング。</span><span class="sxs-lookup"><span data-stu-id="00ce4-109">A binding that contains the information that describes how a client must communicate with the service.</span></span> 
- <span data-ttu-id="00ce4-110">サービスがクライアントに提供する機能を定義するコントラクト。</span><span class="sxs-lookup"><span data-stu-id="00ce4-110">A contract that defines the functionality that the service provides to its clients.</span></span>

<span data-ttu-id="00ce4-111">このチュートリアルでは、次の作業を行う方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="00ce4-111">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
> - <span data-ttu-id="00ce4-112">作成し、WCF サービスをホストするためのコンソール アプリ プロジェクトを構成します。</span><span class="sxs-lookup"><span data-stu-id="00ce4-112">Create and configure a console app project for hosting a WCF service.</span></span>
> - <span data-ttu-id="00ce4-113">WCF サービスをホストするためのコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="00ce4-113">Add code to host the WCF service.</span></span>
> - <span data-ttu-id="00ce4-114">構成ファイルを更新します。</span><span class="sxs-lookup"><span data-stu-id="00ce4-114">Update the configuration file.</span></span>
> - <span data-ttu-id="00ce4-115">WCF サービスを開始し、確認が実行されています。</span><span class="sxs-lookup"><span data-stu-id="00ce4-115">Start the WCF service and verify it's running.</span></span>

## <a name="create-and-configure-a-console-app-project-for-hosting-the-service"></a><span data-ttu-id="00ce4-116">作成し、サービスをホストするためのコンソール アプリ プロジェクトを構成します。</span><span class="sxs-lookup"><span data-stu-id="00ce4-116">Create and configure a console app project for hosting the service</span></span>

1. <span data-ttu-id="00ce4-117">Visual Studio でコンソール アプリ プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="00ce4-117">Create a console app project in Visual Studio:</span></span> 
 
    1. <span data-ttu-id="00ce4-118">**ファイル**メニューの **オープン** > **プロジェクト/ソリューション**を見つけて、 **GettingStarted**ソリューションを以前に作成した (*GettingStarted.sln*)。</span><span class="sxs-lookup"><span data-stu-id="00ce4-118">From the **File** menu, select **Open** > **Project/Solution** and browse to the **GettingStarted** solution you previously created (*GettingStarted.sln*).</span></span> <span data-ttu-id="00ce4-119">**[開く]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="00ce4-119">Select **Open**.</span></span>

    2. <span data-ttu-id="00ce4-120">**ビュー**メニューの **ソリューション エクスプ ローラー**します。</span><span class="sxs-lookup"><span data-stu-id="00ce4-120">From the **View** menu, select **Solution Explorer**.</span></span>
    
    3. <span data-ttu-id="00ce4-121">**ソリューション エクスプ ローラー**ウィンドウで、 **GettingStarted**ソリューション (最上位ノード) し、選択**追加** > **の新しいプロジェクト**ショートカット メニューから。</span><span class="sxs-lookup"><span data-stu-id="00ce4-121">In the **Solution Explorer** window, select the **GettingStarted** solution (top node), and then select **Add** > **New Project** from the shortcut menu.</span></span> 

    4. <span data-ttu-id="00ce4-122">**新しいプロジェクトの追加**ウィンドウで、左側にある、選択、 **Windows デスクトップ**カテゴリ  **Visual C#** または**Visual Basic**.</span><span class="sxs-lookup"><span data-stu-id="00ce4-122">In the **Add New Project** window, on the left side, select the **Windows Desktop** category under **Visual C#** or **Visual Basic**.</span></span> 

    5. <span data-ttu-id="00ce4-123">選択、**コンソール アプリ (.NET Framework)** テンプレート、入力と*GettingStartedHost*の**名前**します。</span><span class="sxs-lookup"><span data-stu-id="00ce4-123">Select the **Console App (.NET Framework)** template, and enter *GettingStartedHost* for the **Name**.</span></span> <span data-ttu-id="00ce4-124">**[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="00ce4-124">Select **OK**.</span></span>

2. <span data-ttu-id="00ce4-125">参照を追加、 **GettingStartedHost**プロジェクトを**GettingStartedLib**プロジェクト。</span><span class="sxs-lookup"><span data-stu-id="00ce4-125">Add a reference in the **GettingStartedHost** project to the **GettingStartedLib** project:</span></span> 

    1. <span data-ttu-id="00ce4-126">**ソリューション エクスプ ローラー**ウィンドウで、**参照**の下のフォルダー、 **GettingStartedHost**プロジェクトを選び**参照の追加**ショートカット メニューから。</span><span class="sxs-lookup"><span data-stu-id="00ce4-126">In the **Solution Explorer** window, select the **References** folder under the **GettingStartedHost** project, and then select **Add Reference** from the shortcut menu.</span></span> 

    2. <span data-ttu-id="00ce4-127">**参照の追加**ダイアログで、**プロジェクト**ウィンドウの左側にある、次のように選択します。**ソリューション**します。</span><span class="sxs-lookup"><span data-stu-id="00ce4-127">In the **Add Reference** dialog, under **Projects** on the left side of the window, select **Solution**.</span></span> 
 
    3. <span data-ttu-id="00ce4-128">選択**GettingStartedLib**選択し、ウィンドウの中央のセクションで**OK**します。</span><span class="sxs-lookup"><span data-stu-id="00ce4-128">Select **GettingStartedLib** in the center section of the window, and then select **OK**.</span></span> 

       <span data-ttu-id="00ce4-129">この操作によってで定義された型、 **GettingStartedLib**プロジェクトに使用可能な**GettingStartedHost**プロジェクト。</span><span class="sxs-lookup"><span data-stu-id="00ce4-129">This action makes the types defined in the **GettingStartedLib** project available to the **GettingStartedHost** project.</span></span>

3. <span data-ttu-id="00ce4-130">参照を追加、 **GettingStartedHost**プロジェクトを<xref:System.ServiceModel>アセンブリ。</span><span class="sxs-lookup"><span data-stu-id="00ce4-130">Add a reference in the **GettingStartedHost** project to the <xref:System.ServiceModel> assembly:</span></span> 

    1. <span data-ttu-id="00ce4-131">**ソリューション エクスプ ローラー**ウィンドウで、**参照**の下のフォルダー、 **GettingStartedHost**プロジェクトを選び**参照の追加**ショートカット メニューから。</span><span class="sxs-lookup"><span data-stu-id="00ce4-131">In the **Solution Explorer** window, select the **References** folder under the **GettingStartedHost** project, and then select **Add Reference** from the shortcut menu.</span></span>
    
    2. <span data-ttu-id="00ce4-132">**参照の追加**ウィンドウで、**アセンブリ**ウィンドウの左側にある、次のように選択します。 **Framework**します。</span><span class="sxs-lookup"><span data-stu-id="00ce4-132">In the **Add Reference** window, under **Assemblies** on the left side of the window, select **Framework**.</span></span> 

    3. <span data-ttu-id="00ce4-133">選択**System.ServiceModel**、し、 **OK**します。</span><span class="sxs-lookup"><span data-stu-id="00ce4-133">Select **System.ServiceModel**, and then select **OK**.</span></span> 
    
    4. <span data-ttu-id="00ce4-134">ソリューションを選択して保存**ファイル** > **すべて保存**します。</span><span class="sxs-lookup"><span data-stu-id="00ce4-134">Save the solution by selecting **File** > **Save All**.</span></span>

## <a name="add-code-to-host-the-service"></a><span data-ttu-id="00ce4-135">サービスをホストするコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="00ce4-135">Add code to host the service</span></span>

<span data-ttu-id="00ce4-136">サービスをホストするには、次の手順を実行するコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="00ce4-136">To host the service, you add code to do the following steps:</span></span> 
   1. <span data-ttu-id="00ce4-137">ベース アドレスの URI を作成します。</span><span class="sxs-lookup"><span data-stu-id="00ce4-137">Create a URI for the base address.</span></span>
   2. <span data-ttu-id="00ce4-138">サービスをホストするためのクラスのインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="00ce4-138">Create a class instance for hosting the service.</span></span>
   3. <span data-ttu-id="00ce4-139">サービス エンドポイントを作成します。</span><span class="sxs-lookup"><span data-stu-id="00ce4-139">Create a service endpoint.</span></span>
   4. <span data-ttu-id="00ce4-140">メタデータ交換を有効にします。</span><span class="sxs-lookup"><span data-stu-id="00ce4-140">Enable metadata exchange.</span></span>
   5. <span data-ttu-id="00ce4-141">受信メッセージをリッスンするサービス ホストを開きます。</span><span class="sxs-lookup"><span data-stu-id="00ce4-141">Open the service host to listen for incoming messages.</span></span>
  
<span data-ttu-id="00ce4-142">コードを次の変更。</span><span class="sxs-lookup"><span data-stu-id="00ce4-142">Make the following changes to the code:</span></span>

1. <span data-ttu-id="00ce4-143">開く、 **Program.cs**または**Module1.vb**ファイル、 **GettingStartedHost**プロジェクトし、そのコードを次のコードに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="00ce4-143">Open the **Program.cs** or **Module1.vb** file in the **GettingStartedHost** project and replace its code with the following code:</span></span>

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
    
    <span data-ttu-id="00ce4-144">このコードの動作については、次を参照してください。[プログラムの手順をホストしているサービス](#service-hosting-program-steps)します。</span><span class="sxs-lookup"><span data-stu-id="00ce4-144">For information about how this code works, see [Service hosting program steps](#service-hosting-program-steps).</span></span>

2. <span data-ttu-id="00ce4-145">プロジェクトのプロパティを更新します。</span><span class="sxs-lookup"><span data-stu-id="00ce4-145">Update the project properties:</span></span>

   1. <span data-ttu-id="00ce4-146">**ソリューション エクスプ ローラー**ウィンドウで、 **GettingStartedHost**フォルダー、および選択**プロパティ**ショートカット メニューから。</span><span class="sxs-lookup"><span data-stu-id="00ce4-146">In the **Solution Explorer** window, select the **GettingStartedHost** folder, and then select **Properties** from the shortcut menu.</span></span>

   2. <span data-ttu-id="00ce4-147">**GettingStartedHost**プロパティ ページで、**アプリケーション** タブ。</span><span class="sxs-lookup"><span data-stu-id="00ce4-147">On the **GettingStartedHost** properties page, select the **Application** tab:</span></span>

      - <span data-ttu-id="00ce4-148">C#プロジェクトで、 **GettingStartedHost.Program**から、**スタートアップ オブジェクト**一覧。</span><span class="sxs-lookup"><span data-stu-id="00ce4-148">For C# projects, select **GettingStartedHost.Program** from the **Startup object** list.</span></span>

      - <span data-ttu-id="00ce4-149">Visual Basic プロジェクトでは、次のように選択します。 **Service.Program**から、**スタートアップ オブジェクト**一覧。</span><span class="sxs-lookup"><span data-stu-id="00ce4-149">For Visual Basic projects, select **Service.Program** from the **Startup object** list.</span></span>

   3. <span data-ttu-id="00ce4-150">**ファイル**メニューの **すべて保存**します。</span><span class="sxs-lookup"><span data-stu-id="00ce4-150">From the **File** menu, select **Save All**.</span></span>

## <a name="verify-the-service-is-working"></a><span data-ttu-id="00ce4-151">サービスが動作を確認します。</span><span class="sxs-lookup"><span data-stu-id="00ce4-151">Verify the service is working</span></span>

1. <span data-ttu-id="00ce4-152">ソリューションをビルドし、実行、 **GettingStartedHost**コンソール Visual Studio 内からアプリケーション。</span><span class="sxs-lookup"><span data-stu-id="00ce4-152">Build the solution, and then run the **GettingStartedHost** console application from inside Visual Studio.</span></span> 

    <span data-ttu-id="00ce4-153">サービスは、管理者特権で実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="00ce4-153">The service must be run with administrator privileges.</span></span> <span data-ttu-id="00ce4-154">実行すると、管理者特権で Visual Studio が開いているため**GettingStartedHost** Visual Studio で、アプリケーションが管理者特権もで実行します。</span><span class="sxs-lookup"><span data-stu-id="00ce4-154">Because you opened Visual Studio with administrator privileges, when you run **GettingStartedHost** in Visual Studio, the application is run with administrator privileges as well.</span></span> <span data-ttu-id="00ce4-155">代わりに、管理者として新しいコマンド プロンプトを開くことができます (選択**詳細** > **管理者として実行**ショートカット メニューから) 実行**GettingStartedHost.exe**内。</span><span class="sxs-lookup"><span data-stu-id="00ce4-155">As an alternative, you can open a new command prompt as an administrator (select **More** > **Run as administrator** from the shortcut menu) and run **GettingStartedHost.exe** within it.</span></span>

2. <span data-ttu-id="00ce4-156">Web ブラウザーを開き、サービスのページを参照`http://localhost:8000/GettingStarted/CalculatorService`します。</span><span class="sxs-lookup"><span data-stu-id="00ce4-156">Open a web browser and browse to the service's page at `http://localhost:8000/GettingStarted/CalculatorService`.</span></span>
   
   > [!NOTE]
   > <span data-ttu-id="00ce4-157">このいずれかなどのサービスには、リッスンを行うコンピューター上で HTTP アドレスを登録する適切なアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="00ce4-157">Services such as this one require the proper permission to register HTTP addresses on the machine for listening.</span></span> <span data-ttu-id="00ce4-158">管理者アカウントにはこのアクセス許可がありますが、管理者以外のアカウントの場合は、HTTP 名前空間へのアクセス許可を付与する必要があります。</span><span class="sxs-lookup"><span data-stu-id="00ce4-158">Administrator accounts have this permission, but non-administrator accounts must be granted permission for HTTP namespaces.</span></span> <span data-ttu-id="00ce4-159">名前空間の予約を構成する方法については、「[Configuring HTTP and HTTPS](feature-details/configuring-http-and-https.md)」 (HTTP と HTTPS を構成する) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="00ce4-159">For more information about how to configure namespace reservations, see [Configuring HTTP and HTTPS](feature-details/configuring-http-and-https.md).</span></span> 

## <a name="service-hosting-program-steps"></a><span data-ttu-id="00ce4-160">サービスのホスト プログラムのステップ</span><span class="sxs-lookup"><span data-stu-id="00ce4-160">Service hosting program steps</span></span>

<span data-ttu-id="00ce4-161">サービスは次のように説明されているホストに追加したコードの手順:</span><span class="sxs-lookup"><span data-stu-id="00ce4-161">The steps in the code you added to host the service are described as follows:</span></span>

- <span data-ttu-id="00ce4-162">**手順 1.**:インスタンスを作成、`Uri`サービスのベース アドレスを保持するクラス。</span><span class="sxs-lookup"><span data-stu-id="00ce4-162">**Step 1**: Create an instance of the `Uri` class to hold the base address of the service.</span></span> <span data-ttu-id="00ce4-163">ベース アドレスを含む URL が、省略可能なサービスを識別する URI。</span><span class="sxs-lookup"><span data-stu-id="00ce4-163">A URL that contains a base address has an optional URI that identifies a service.</span></span> <span data-ttu-id="00ce4-164">ベース アドレスは次の形式:`<transport>://<machine-name or domain><:optional port #>/<optional URI segment>`します。</span><span class="sxs-lookup"><span data-stu-id="00ce4-164">The base address is formatted as follows: `<transport>://<machine-name or domain><:optional port #>/<optional URI segment>`.</span></span> <span data-ttu-id="00ce4-165">電卓サービスのベース アドレスは、HTTP トランスポート、localhost、ポート 8000、および URI セグメント、GettingStarted を使用します。</span><span class="sxs-lookup"><span data-stu-id="00ce4-165">The base address for the calculator service uses the HTTP transport, localhost, port 8000, and the URI segment, GettingStarted.</span></span>

- <span data-ttu-id="00ce4-166">**手順 2**:インスタンスを作成、<xref:System.ServiceModel.ServiceHost>クラスは、サービスをホストするために使用します。</span><span class="sxs-lookup"><span data-stu-id="00ce4-166">**Step 2**: Create an instance of the <xref:System.ServiceModel.ServiceHost> class, which you use to host the service.</span></span> <span data-ttu-id="00ce4-167">コンス トラクターは 2 つのパラメーター: サービス コントラクトとサービスのベース アドレスを実装するクラスの型。</span><span class="sxs-lookup"><span data-stu-id="00ce4-167">The constructor takes two parameters: the type of the class that implements the service contract and the base address of the service.</span></span>

- <span data-ttu-id="00ce4-168">**手順 3**:<xref:System.ServiceModel.Description.ServiceEndpoint> インスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="00ce4-168">**Step 3**: Create a <xref:System.ServiceModel.Description.ServiceEndpoint> instance.</span></span> <span data-ttu-id="00ce4-169">サービス エンドポイントは、アドレス、バインディング、およびサービス コントラクトから構成されます。</span><span class="sxs-lookup"><span data-stu-id="00ce4-169">A service endpoint is composed of an address, a binding, and a service contract.</span></span> <span data-ttu-id="00ce4-170"><xref:System.ServiceModel.Description.ServiceEndpoint>コンス トラクターは、サービス コントラクト インターフェイスの型、バインディング、およびアドレスで構成されます。</span><span class="sxs-lookup"><span data-stu-id="00ce4-170">The <xref:System.ServiceModel.Description.ServiceEndpoint> constructor is composed of the service contract interface type, a binding, and an address.</span></span> <span data-ttu-id="00ce4-171">サービス コントラクトは、サービス型に定義および実装した `ICalculator` です。</span><span class="sxs-lookup"><span data-stu-id="00ce4-171">The service contract is `ICalculator`, which you defined and implement in the service type.</span></span> <span data-ttu-id="00ce4-172">このサンプルのバインディングが<xref:System.ServiceModel.WSHttpBinding>、組み込みのバインディングし、は、ws-に準拠するエンドポイントに接続 \* の仕様。</span><span class="sxs-lookup"><span data-stu-id="00ce4-172">The binding for this sample is <xref:System.ServiceModel.WSHttpBinding>, which is a built-in binding and connects to endpoints that conform to the WS-\* specifications.</span></span> <span data-ttu-id="00ce4-173">WCF バインドの詳細については、次を参照してください。 [WCF のバインディングの概要](bindings-overview.md)します。</span><span class="sxs-lookup"><span data-stu-id="00ce4-173">For more information about WCF bindings, see [WCF bindings overview](bindings-overview.md).</span></span> <span data-ttu-id="00ce4-174">エンドポイントを識別するためにベース アドレスには、アドレスを追加します。</span><span class="sxs-lookup"><span data-stu-id="00ce4-174">You append the address to the base address to identify the endpoint.</span></span> <span data-ttu-id="00ce4-175">コードは、CalculatorService ととしてエンドポイントの完全修飾アドレスとしてアドレスを指定します`http://localhost:8000/GettingStarted/CalculatorService`します。</span><span class="sxs-lookup"><span data-stu-id="00ce4-175">The code specifies the address as CalculatorService and the fully qualified address for the endpoint as `http://localhost:8000/GettingStarted/CalculatorService`.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="00ce4-176">.NET Framework バージョン 4 以降、サービス エンドポイントの追加は省略可能にします。</span><span class="sxs-lookup"><span data-stu-id="00ce4-176">For .NET Framework Version 4 and later, adding a service endpoint is optional.</span></span> <span data-ttu-id="00ce4-177">これらのバージョン、コードや構成を追加しない場合、WCF はベース アドレスと、サービスによって実装されるコントラクトの組み合わせごとに 1 つの既定のエンドポイントを追加します。</span><span class="sxs-lookup"><span data-stu-id="00ce4-177">For these versions, if you don't add your code or configuration, WCF adds one default endpoint for each combination of base address and contract implemented by the service.</span></span> <span data-ttu-id="00ce4-178">既定のエンドポイントの詳細については、次を参照してください。[エンドポイント アドレスを指定する](specifying-an-endpoint-address.md)します。</span><span class="sxs-lookup"><span data-stu-id="00ce4-178">For more information about default endpoints, see [Specifying an endpoint address](specifying-an-endpoint-address.md).</span></span> <span data-ttu-id="00ce4-179">既定のエンドポイント、バインディング、および動作の詳細については、次を参照してください。[簡略化された構成](simplified-configuration.md)と[WCF サービスの構成を簡略化された](samples/simplified-configuration-for-wcf-services.md)します。</span><span class="sxs-lookup"><span data-stu-id="00ce4-179">For more information about default endpoints, bindings, and behaviors, see [Simplified configuration](simplified-configuration.md) and [Simplified configuration for WCF services](samples/simplified-configuration-for-wcf-services.md).</span></span>

- <span data-ttu-id="00ce4-180">**手順 4**:メタデータ交換を有効にします。</span><span class="sxs-lookup"><span data-stu-id="00ce4-180">**Step 4**: Enable metadata exchange.</span></span> <span data-ttu-id="00ce4-181">クライアントは、サービス操作を呼び出すためのプロキシを生成するのにメタデータ交換を使用します。</span><span class="sxs-lookup"><span data-stu-id="00ce4-181">Clients use metadata exchange to generate proxies for calling the service operations.</span></span> <span data-ttu-id="00ce4-182">メタデータ交換を有効にするには作成、<xref:System.ServiceModel.Description.ServiceMetadataBehavior>インスタンスは、設定、<xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpGetEnabled>プロパティを`true`、追加、`ServiceMetadataBehavior`オブジェクトを<xref:System.ServiceModel.Description.ServiceDescription.Behaviors%2A>のコレクション、<xref:System.ServiceModel.ServiceHost>インスタンス。</span><span class="sxs-lookup"><span data-stu-id="00ce4-182">To enable metadata exchange, create a <xref:System.ServiceModel.Description.ServiceMetadataBehavior> instance, set its <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpGetEnabled> property to `true`, and add the `ServiceMetadataBehavior` object to the <xref:System.ServiceModel.Description.ServiceDescription.Behaviors%2A> collection of the <xref:System.ServiceModel.ServiceHost> instance.</span></span>

- <span data-ttu-id="00ce4-183">**手順 5**:開いている<xref:System.ServiceModel.ServiceHost>受信メッセージをリッスンします。</span><span class="sxs-lookup"><span data-stu-id="00ce4-183">**Step 5**: Open <xref:System.ServiceModel.ServiceHost> to listen for incoming messages.</span></span> <span data-ttu-id="00ce4-184">アプリケーションがボタンを押すまで待機**Enter**します。</span><span class="sxs-lookup"><span data-stu-id="00ce4-184">The application waits for you to press **Enter**.</span></span> <span data-ttu-id="00ce4-185">アプリケーションをインスタンス化後<xref:System.ServiceModel.ServiceHost>、try/catch ブロックを実行します。</span><span class="sxs-lookup"><span data-stu-id="00ce4-185">After the application instantiates <xref:System.ServiceModel.ServiceHost>, it executes a try/catch block.</span></span> <span data-ttu-id="00ce4-186">によってスローされた例外を安全にキャッチの詳細については<xref:System.ServiceModel.ServiceHost>を参照してください[使用終了、中止 WCF クライアントのリソースを解放する](samples/use-close-abort-release-wcf-client-resources.md)します。</span><span class="sxs-lookup"><span data-stu-id="00ce4-186">For more information about safely catching exceptions thrown by <xref:System.ServiceModel.ServiceHost>, see [Use Close and Abort to release WCF client resources](samples/use-close-abort-release-wcf-client-resources.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="00ce4-187">WCF サービス ライブラリを追加するときに Visual Studio ホストがサービス ホストを起動してデバッグする場合。</span><span class="sxs-lookup"><span data-stu-id="00ce4-187">When you add a WCF service library, Visual Studio hosts it for you if you debug it by starting a service host.</span></span> <span data-ttu-id="00ce4-188">競合を回避するには、WCF サービス ライブラリをホストしているから Visual Studio を回避できます。</span><span class="sxs-lookup"><span data-stu-id="00ce4-188">To avoid conflicts, you can prevent Visual Studio from hosting the WCF service library.</span></span> 
> 1. <span data-ttu-id="00ce4-189">選択、 **GettingStartedLib**プロジェクト**ソリューション エクスプ ローラー**選択**プロパティ**ショートカット メニューから。</span><span class="sxs-lookup"><span data-stu-id="00ce4-189">Select the **GettingStartedLib** project in **Solution Explorer** and choose **Properties** from the shortcut menu.</span></span>
> 2. <span data-ttu-id="00ce4-190">選択**WCF オプション**をオフにし、**開始 WCF サービス ホスト、同じソリューション内の別のプロジェクトをデバッグするときに**します。</span><span class="sxs-lookup"><span data-stu-id="00ce4-190">Select **WCF Options** and uncheck **Start WCF Service Host when debugging another project in the same solution**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="00ce4-191">次の手順</span><span class="sxs-lookup"><span data-stu-id="00ce4-191">Next steps</span></span>

<span data-ttu-id="00ce4-192">このチュートリアルでは、次の作業を行う方法を学びました。</span><span class="sxs-lookup"><span data-stu-id="00ce4-192">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
> - <span data-ttu-id="00ce4-193">作成し、WCF サービスをホストするためのコンソール アプリ プロジェクトを構成します。</span><span class="sxs-lookup"><span data-stu-id="00ce4-193">Create and configure a console app project for hosting a WCF service.</span></span>
> - <span data-ttu-id="00ce4-194">WCF サービスをホストするためのコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="00ce4-194">Add code to host the WCF service.</span></span>
> - <span data-ttu-id="00ce4-195">構成ファイルを更新します。</span><span class="sxs-lookup"><span data-stu-id="00ce4-195">Update the configuration file.</span></span>
> - <span data-ttu-id="00ce4-196">WCF サービスを開始し、確認が実行されています。</span><span class="sxs-lookup"><span data-stu-id="00ce4-196">Start the WCF service and verify it's running.</span></span>

<span data-ttu-id="00ce4-197">WCF クライアントを作成する方法については、次のチュートリアルに進んでください。</span><span class="sxs-lookup"><span data-stu-id="00ce4-197">Advance to the next tutorial to learn how to create a WCF client.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="00ce4-198">チュートリアル: WCF クライアントを作成します。</span><span class="sxs-lookup"><span data-stu-id="00ce4-198">Tutorial: Create a WCF client</span></span>](how-to-create-a-wcf-client.md)
