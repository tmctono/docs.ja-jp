---
title: 'チュートリアル: Windows Communication Foundation クライアントを使用する'
ms.date: 03/19/2019
helpviewer_keywords:
- WCF clients [WCF], using
dev_langs:
- CSharp
- VB
ms.assetid: 190349fc-0573-49c7-bb85-8e316df7f31f
ms.openlocfilehash: 5c280933c81ef54ba58181e3005e30775b9b8e42
ms.sourcegitcommit: 33c8d6f7342a4bb2c577842b7f075b0e20a2fa40
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2019
ms.locfileid: "70928889"
---
# <a name="tutorial-use-a-windows-communication-foundation-client"></a><span data-ttu-id="8f32a-102">チュートリアル: Windows Communication Foundation クライアントを使用する</span><span class="sxs-lookup"><span data-stu-id="8f32a-102">Tutorial: Use a Windows Communication Foundation client</span></span>

<span data-ttu-id="8f32a-103">このチュートリアルでは、基本的な Windows Communication Foundation (WCF) アプリケーションを作成するために必要な5つのタスクについて説明します。</span><span class="sxs-lookup"><span data-stu-id="8f32a-103">This tutorial describes the last of five tasks required to create a basic Windows Communication Foundation (WCF) application.</span></span> <span data-ttu-id="8f32a-104">チュートリアルの概要については、 [「チュートリアル:Windows Communication Foundation アプリケーション](getting-started-tutorial.md)の概要」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="8f32a-104">For an overview of the tutorials, see [Tutorial: Get started with Windows Communication Foundation applications](getting-started-tutorial.md).</span></span>

<span data-ttu-id="8f32a-105">Windows Communication Foundation (WCF) プロキシを作成して構成したら、クライアントインスタンスを作成し、クライアントアプリケーションをコンパイルします。</span><span class="sxs-lookup"><span data-stu-id="8f32a-105">After you've created and configured a Windows Communication Foundation (WCF) proxy, you create a client instance and compile the client application.</span></span> <span data-ttu-id="8f32a-106">次に、WCF サービスとの通信に使用します。</span><span class="sxs-lookup"><span data-stu-id="8f32a-106">You then use it to communicate with the WCF service.</span></span> 

<span data-ttu-id="8f32a-107">このチュートリアルでは、次の作業を行う方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="8f32a-107">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="8f32a-108">WCF クライアントを使用するコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="8f32a-108">Add code to use the WCF client.</span></span>
> - <span data-ttu-id="8f32a-109">WCF クライアントをテストします。</span><span class="sxs-lookup"><span data-stu-id="8f32a-109">Test the WCF client.</span></span>

## <a name="add-code-to-use-the-wcf-client"></a><span data-ttu-id="8f32a-110">WCF クライアントを使用するコードを追加する</span><span class="sxs-lookup"><span data-stu-id="8f32a-110">Add code to use the WCF client</span></span>

<span data-ttu-id="8f32a-111">クライアントコードでは、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="8f32a-111">The client code does the following steps:</span></span>

- <span data-ttu-id="8f32a-112">WCF クライアントをインスタンス化します。</span><span class="sxs-lookup"><span data-stu-id="8f32a-112">Instantiates the WCF client.</span></span>
- <span data-ttu-id="8f32a-113">生成されたプロキシからサービス操作を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="8f32a-113">Calls the service operations from the generated proxy.</span></span>
- <span data-ttu-id="8f32a-114">操作の呼び出しが完了した後にクライアントを閉じます。</span><span class="sxs-lookup"><span data-stu-id="8f32a-114">Closes the client after the operation call is completed.</span></span>

<span data-ttu-id="8f32a-115">**GettingProgram.cs クライアント**プロジェクトから、次のコードに置き換えて、**そのファイルの**コードを開きます。</span><span class="sxs-lookup"><span data-stu-id="8f32a-115">Open the **Program.cs** or **Module1.vb** file from the **GettingStartedClient** project and replace its code with the following code:</span></span>

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
Imports System
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

<span data-ttu-id="8f32a-116">`using` C# `Imports`インポートする(Visualの場合)または(VisualBasic)ステートメントがあることに注意してください。`GettingStartedClient.ServiceReference1`</span><span class="sxs-lookup"><span data-stu-id="8f32a-116">Notice the `using` (for Visual C#) or `Imports` (for Visual Basic) statement that imports `GettingStartedClient.ServiceReference1`.</span></span> <span data-ttu-id="8f32a-117">このステートメントは、Visual Studio によって生成されたコードを**サービス参照の追加**関数でインポートします。</span><span class="sxs-lookup"><span data-stu-id="8f32a-117">This statement imports the code that Visual Studio generated with the **Add Service Reference** function.</span></span> <span data-ttu-id="8f32a-118">このコードは、WCF プロキシをインスタンス化し、電卓サービスが公開する各サービス操作を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="8f32a-118">The code instantiates the WCF proxy and calls each of the service operations that the calculator service exposes.</span></span> <span data-ttu-id="8f32a-119">次に、プロキシを閉じてプログラムを終了します。</span><span class="sxs-lookup"><span data-stu-id="8f32a-119">It then closes the proxy and ends the program.</span></span>

## <a name="test-the-wcf-client"></a><span data-ttu-id="8f32a-120">WCF クライアントをテストする</span><span class="sxs-lookup"><span data-stu-id="8f32a-120">Test the WCF client</span></span>

### <a name="test-the-application-from-visual-studio"></a><span data-ttu-id="8f32a-121">Visual Studio からのアプリケーションのテスト</span><span class="sxs-lookup"><span data-stu-id="8f32a-121">Test the application from Visual Studio</span></span>

1. <span data-ttu-id="8f32a-122">ソリューションを保存してビルドします。</span><span class="sxs-lookup"><span data-stu-id="8f32a-122">Save and build the solution.</span></span>

2. <span data-ttu-id="8f32a-123">**[Gettingstartup lib]** フォルダーを選択し、ショートカットメニューの **[スタートアッププロジェクトに設定]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="8f32a-123">Select the **GettingStartedLib** folder, and then select **Set as Startup Project** from the shortcut menu.</span></span>

3. <span data-ttu-id="8f32a-124">**スタートアッププロジェクト**から、ドロップダウンリストから **[Gettingstartup lib]** を選択し、 **[実行]** を選択するか、 **F5**キーを押します。</span><span class="sxs-lookup"><span data-stu-id="8f32a-124">From **Startup Projects**, select **GettingStartedLib** from the drop-down list, then select **Run** or press **F5**.</span></span>

### <a name="test-the-application-from-a-command-prompt"></a><span data-ttu-id="8f32a-125">コマンドプロンプトからのアプリケーションのテスト</span><span class="sxs-lookup"><span data-stu-id="8f32a-125">Test the application from a command prompt</span></span>

1. <span data-ttu-id="8f32a-126">管理者としてコマンドプロンプトを開き、Visual Studio ソリューションのディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="8f32a-126">Open a command prompt as an administrator, and then navigate to your Visual Studio solution directory.</span></span> 

2. <span data-ttu-id="8f32a-127">サービスを開始するには:「 *GettingStartedHost\bin\Debug\GettingStartedHost.exe*」と入力します。</span><span class="sxs-lookup"><span data-stu-id="8f32a-127">To start the service: Enter *GettingStartedHost\bin\Debug\GettingStartedHost.exe*.</span></span>

3. <span data-ttu-id="8f32a-128">クライアントを起動するには:別のコマンドプロンプトを開き、Visual Studio ソリューションのディレクトリに移動して、「 *GettingStartedClient\bin\Debug\GettingStartedClient.exe*」と入力します。</span><span class="sxs-lookup"><span data-stu-id="8f32a-128">To start the client: Open another command prompt, navigate to your Visual Studio solution directory, then enter *GettingStartedClient\bin\Debug\GettingStartedClient.exe*.</span></span>

   <span data-ttu-id="8f32a-129">この*ホスト*は、次の出力を生成します。</span><span class="sxs-lookup"><span data-stu-id="8f32a-129">*GettingStartedHost.exe* produces the following output:</span></span>

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

   <span data-ttu-id="8f32a-130">*クライアント .exe*は、次の出力を生成します。</span><span class="sxs-lookup"><span data-stu-id="8f32a-130">*GettingStartedClient.exe* produces the following output:</span></span>

   ```text
   Add(100,15.99) = 115.99
   Subtract(145,76.54) = 68.46
   Multiply(9,81.25) = 731.25
   Divide(22,7) = 3.14285714285714

   Press <Enter> to terminate the client.
   ```

## <a name="next-steps"></a><span data-ttu-id="8f32a-131">次の手順</span><span class="sxs-lookup"><span data-stu-id="8f32a-131">Next steps</span></span>

<span data-ttu-id="8f32a-132">これで、WCF 入門チュートリアルのすべてのタスクが完了しました。</span><span class="sxs-lookup"><span data-stu-id="8f32a-132">You've now completed all the tasks in the WCF get started tutorial.</span></span> <span data-ttu-id="8f32a-133">このチュートリアルでは、次の作業を行う方法を学びました。</span><span class="sxs-lookup"><span data-stu-id="8f32a-133">In this tutorial, you learned how to:</span></span>

<span data-ttu-id="8f32a-134">このチュートリアルでは、次の作業を行う方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="8f32a-134">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="8f32a-135">WCF クライアントを使用するコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="8f32a-135">Add code to use the WCF client.</span></span>
> - <span data-ttu-id="8f32a-136">WCF クライアントをテストします。</span><span class="sxs-lookup"><span data-stu-id="8f32a-136">Test the WCF client.</span></span>

<span data-ttu-id="8f32a-137">いずれかの手順で問題やエラーが発生した場合は、トラブルシューティングの記事に記載されている手順に従って修正してください。</span><span class="sxs-lookup"><span data-stu-id="8f32a-137">If you have problems or errors in any of the steps, follow the steps in the troubleshooting article to fix them.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="8f32a-138">WCF の概要チュートリアルのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="8f32a-138">Troubleshoot the Get started with WCF tutorials</span></span>](troubleshooting-the-getting-started-tutorial.md)
