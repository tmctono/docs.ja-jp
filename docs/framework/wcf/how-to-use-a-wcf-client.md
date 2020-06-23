---
title: 'チュートリアル: Windows Communication Foundation クライアントを使用する'
description: WCF アプリケーションの作成に関する一連の記事の一部として、クライアントインスタンスを作成し、アプリケーションをコンパイルし、サービスと通信する方法について説明します。
ms.date: 03/19/2019
helpviewer_keywords:
- WCF clients [WCF], using
dev_langs:
- CSharp
- VB
ms.assetid: 190349fc-0573-49c7-bb85-8e316df7f31f
ms.openlocfilehash: 5c94d5f8af679580c4194aaaadeda759098953d2
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/23/2020
ms.locfileid: "85244336"
---
# <a name="tutorial-use-a-windows-communication-foundation-client"></a><span data-ttu-id="cc10e-103">チュートリアル: Windows Communication Foundation クライアントを使用する</span><span class="sxs-lookup"><span data-stu-id="cc10e-103">Tutorial: Use a Windows Communication Foundation client</span></span>

<span data-ttu-id="cc10e-104">このチュートリアルでは、基本的な Windows Communication Foundation (WCF) アプリケーションを作成するために必要な5つのタスクについて説明します。</span><span class="sxs-lookup"><span data-stu-id="cc10e-104">This tutorial describes the last of five tasks required to create a basic Windows Communication Foundation (WCF) application.</span></span> <span data-ttu-id="cc10e-105">チュートリアルの概要については、「[チュートリアル: Windows Communication Foundation アプリケーションの](getting-started-tutorial.md)概要」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cc10e-105">For an overview of the tutorials, see [Tutorial: Get started with Windows Communication Foundation applications](getting-started-tutorial.md).</span></span>

<span data-ttu-id="cc10e-106">Windows Communication Foundation (WCF) プロキシを作成して構成したら、クライアントインスタンスを作成し、クライアントアプリケーションをコンパイルします。</span><span class="sxs-lookup"><span data-stu-id="cc10e-106">After you've created and configured a Windows Communication Foundation (WCF) proxy, you create a client instance and compile the client application.</span></span> <span data-ttu-id="cc10e-107">次に、WCF サービスとの通信に使用します。</span><span class="sxs-lookup"><span data-stu-id="cc10e-107">You then use it to communicate with the WCF service.</span></span>

<span data-ttu-id="cc10e-108">このチュートリアルでは、次の作業を行う方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="cc10e-108">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="cc10e-109">WCF クライアントを使用するコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="cc10e-109">Add code to use the WCF client.</span></span>
> - <span data-ttu-id="cc10e-110">WCF クライアントをテストします。</span><span class="sxs-lookup"><span data-stu-id="cc10e-110">Test the WCF client.</span></span>

## <a name="add-code-to-use-the-wcf-client"></a><span data-ttu-id="cc10e-111">WCF クライアントを使用するコードを追加する</span><span class="sxs-lookup"><span data-stu-id="cc10e-111">Add code to use the WCF client</span></span>

<span data-ttu-id="cc10e-112">クライアントコードでは、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="cc10e-112">The client code does the following steps:</span></span>

- <span data-ttu-id="cc10e-113">WCF クライアントをインスタンス化します。</span><span class="sxs-lookup"><span data-stu-id="cc10e-113">Instantiates the WCF client.</span></span>
- <span data-ttu-id="cc10e-114">生成されたプロキシからサービス操作を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="cc10e-114">Calls the service operations from the generated proxy.</span></span>
- <span data-ttu-id="cc10e-115">操作の呼び出しが完了した後にクライアントを閉じます。</span><span class="sxs-lookup"><span data-stu-id="cc10e-115">Closes the client after the operation call is completed.</span></span>

<span data-ttu-id="cc10e-116">**GettingProgram.cs クライアント**プロジェクトから、次のコードに置き換えて、**そのファイルの**コードを開きます。 **Program.cs**</span><span class="sxs-lookup"><span data-stu-id="cc10e-116">Open the **Program.cs** or **Module1.vb** file from the **GettingStartedClient** project and replace its code with the following code:</span></span>

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using GettingStartedClient.ServiceReference1;

namespace GettingStartedClient
{
    class Program
    {
        static void Main(string[] args)
        {
            //Step 1: Create an instance of the WCF proxy.
            CalculatorClient client = new CalculatorClient();

            // Step 2: Call the service operations.
            // Call the Add service operation.
            double value1 = 100.00D;
            double value2 = 15.99D;
            double result = client.Add(value1, value2);
            Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result);

            // Call the Subtract service operation.
            value1 = 145.00D;
            value2 = 76.54D;
            result = client.Subtract(value1, value2);
            Console.WriteLine("Subtract({0},{1}) = {2}", value1, value2, result);

            // Call the Multiply service operation.
            value1 = 9.00D;
            value2 = 81.25D;
            result = client.Multiply(value1, value2);
            Console.WriteLine("Multiply({0},{1}) = {2}", value1, value2, result);

            // Call the Divide service operation.
            value1 = 22.00D;
            value2 = 7.00D;
            result = client.Divide(value1, value2);
            Console.WriteLine("Divide({0},{1}) = {2}", value1, value2, result);

            // Step 3: Close the client to gracefully close the connection and clean up resources.
            Console.WriteLine("\nPress <Enter> to terminate the client.");
            Console.ReadLine();
            client.Close();
        }
    }
}
```

```vb
Imports System.Collections.Generic
Imports System.Text
Imports System.ServiceModel
Imports GettingStartedClient.ServiceReference1

Module Module1

    Sub Main()
        ' Step 1: Create an instance of the WCF proxy.
        Dim Client As New CalculatorClient()

        ' Step 2: Call the service operations.
        ' Call the Add service operation.
        Dim value1 As Double = 100D
        Dim value2 As Double = 15.99D
        Dim result As Double = Client.Add(value1, value2)
        Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result)

        ' Call the Subtract service operation.
        value1 = 145D
        value2 = 76.54D
        result = Client.Subtract(value1, value2)
        Console.WriteLine("Subtract({0},{1}) = {2}", value1, value2, result)

        ' Call the Multiply service operation.
        value1 = 9D
        value2 = 81.25D
        result = Client.Multiply(value1, value2)
        Console.WriteLine("Multiply({0},{1}) = {2}", value1, value2, result)

        ' Call the Divide service operation.
        value1 = 22D
        value2 = 7D
        result = Client.Divide(value1, value2)
        Console.WriteLine("Divide({0},{1}) = {2}", value1, value2, result)

        ' Step 3: Close the client to gracefully close the connection and clean up resources.
        Console.WriteLine()
        Console.WriteLine("Press <Enter> to terminate the client.")
        Console.ReadLine()
        Client.Close()

    End Sub

End Module
```

<span data-ttu-id="cc10e-117">を `using` インポートする (Visual C# の場合) または `Imports` (Visual Basic) ステートメントがあることに注意して `GettingStartedClient.ServiceReference1` ください。</span><span class="sxs-lookup"><span data-stu-id="cc10e-117">Notice the `using` (for Visual C#) or `Imports` (for Visual Basic) statement that imports `GettingStartedClient.ServiceReference1`.</span></span> <span data-ttu-id="cc10e-118">このステートメントは、Visual Studio によって生成されたコードを**サービス参照の追加**関数でインポートします。</span><span class="sxs-lookup"><span data-stu-id="cc10e-118">This statement imports the code that Visual Studio generated with the **Add Service Reference** function.</span></span> <span data-ttu-id="cc10e-119">このコードは、WCF プロキシをインスタンス化し、電卓サービスが公開する各サービス操作を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="cc10e-119">The code instantiates the WCF proxy and calls each of the service operations that the calculator service exposes.</span></span> <span data-ttu-id="cc10e-120">次に、プロキシを閉じてプログラムを終了します。</span><span class="sxs-lookup"><span data-stu-id="cc10e-120">It then closes the proxy and ends the program.</span></span>

## <a name="test-the-wcf-client"></a><span data-ttu-id="cc10e-121">WCF クライアントをテストする</span><span class="sxs-lookup"><span data-stu-id="cc10e-121">Test the WCF client</span></span>

### <a name="test-the-application-from-visual-studio"></a><span data-ttu-id="cc10e-122">Visual Studio からのアプリケーションのテスト</span><span class="sxs-lookup"><span data-stu-id="cc10e-122">Test the application from Visual Studio</span></span>

1. <span data-ttu-id="cc10e-123">保存し、ソリューションをビルドします。</span><span class="sxs-lookup"><span data-stu-id="cc10e-123">Save and build the solution.</span></span>

2. <span data-ttu-id="cc10e-124">[ **Gettingstartup lib** ] フォルダーを選択し、ショートカットメニューの [**スタートアッププロジェクトに設定**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="cc10e-124">Select the **GettingStartedLib** folder, and then select **Set as Startup Project** from the shortcut menu.</span></span>

3. <span data-ttu-id="cc10e-125">**スタートアッププロジェクト**から、ドロップダウンリストから [ **Gettingstartup lib** ] を選択し、[**実行**] を選択するか、 **F5**キーを押します。</span><span class="sxs-lookup"><span data-stu-id="cc10e-125">From **Startup Projects**, select **GettingStartedLib** from the drop-down list, then select **Run** or press **F5**.</span></span>

### <a name="test-the-application-from-a-command-prompt"></a><span data-ttu-id="cc10e-126">コマンドプロンプトからのアプリケーションのテスト</span><span class="sxs-lookup"><span data-stu-id="cc10e-126">Test the application from a command prompt</span></span>

1. <span data-ttu-id="cc10e-127">管理者としてコマンドプロンプトを開き、Visual Studio ソリューションのディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="cc10e-127">Open a command prompt as an administrator, and then navigate to your Visual Studio solution directory.</span></span>

2. <span data-ttu-id="cc10e-128">サービスを開始するには、「 *GettingStartedHost\bin\Debug\GettingStartedHost.exe*」と入力します。</span><span class="sxs-lookup"><span data-stu-id="cc10e-128">To start the service: Enter *GettingStartedHost\bin\Debug\GettingStartedHost.exe*.</span></span>

3. <span data-ttu-id="cc10e-129">クライアントを起動するには: 別のコマンドプロンプトを開き、Visual Studio ソリューションのディレクトリに移動して、「 *GettingStartedClient\bin\Debug\GettingStartedClient.exe*」と入力します。</span><span class="sxs-lookup"><span data-stu-id="cc10e-129">To start the client: Open another command prompt, navigate to your Visual Studio solution directory, then enter *GettingStartedClient\bin\Debug\GettingStartedClient.exe*.</span></span>

   <span data-ttu-id="cc10e-130">*GettingStartedHost.exe*では、次の出力が生成されます。</span><span class="sxs-lookup"><span data-stu-id="cc10e-130">*GettingStartedHost.exe* produces the following output:</span></span>

   ```text
   The service is ready.
   Press <Enter> to terminate the service.

   Received Add(100,15.99)
   Return: 115.99
   Received Subtract(145,76.54)
   Return: 68.46
   Received Multiply(9,81.25)
   Return: 731.25
   Received Divide(22,7)
   Return: 3.14285714285714
   ```

   <span data-ttu-id="cc10e-131">*GettingStartedClient.exe*では、次の出力が生成されます。</span><span class="sxs-lookup"><span data-stu-id="cc10e-131">*GettingStartedClient.exe* produces the following output:</span></span>

   ```text
   Add(100,15.99) = 115.99
   Subtract(145,76.54) = 68.46
   Multiply(9,81.25) = 731.25
   Divide(22,7) = 3.14285714285714

   Press <Enter> to terminate the client.
   ```

## <a name="next-steps"></a><span data-ttu-id="cc10e-132">次の手順</span><span class="sxs-lookup"><span data-stu-id="cc10e-132">Next steps</span></span>

<span data-ttu-id="cc10e-133">これで、WCF 入門チュートリアルのすべてのタスクが完了しました。</span><span class="sxs-lookup"><span data-stu-id="cc10e-133">You've now completed all the tasks in the WCF get started tutorial.</span></span> <span data-ttu-id="cc10e-134">このチュートリアルでは、以下の内容を学習しました。</span><span class="sxs-lookup"><span data-stu-id="cc10e-134">In this tutorial, you learned how to:</span></span>

<span data-ttu-id="cc10e-135">このチュートリアルでは、次の作業を行う方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="cc10e-135">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="cc10e-136">WCF クライアントを使用するコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="cc10e-136">Add code to use the WCF client.</span></span>
> - <span data-ttu-id="cc10e-137">WCF クライアントをテストします。</span><span class="sxs-lookup"><span data-stu-id="cc10e-137">Test the WCF client.</span></span>

<span data-ttu-id="cc10e-138">いずれかの手順で問題やエラーが発生した場合は、トラブルシューティングの記事に記載されている手順に従って修正してください。</span><span class="sxs-lookup"><span data-stu-id="cc10e-138">If you have problems or errors in any of the steps, follow the steps in the troubleshooting article to fix them.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="cc10e-139">WCF の概要チュートリアルのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="cc10e-139">Troubleshoot the Get started with WCF tutorials</span></span>](troubleshooting-the-getting-started-tutorial.md)
