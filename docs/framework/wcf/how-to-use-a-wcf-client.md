---
title: 'チュートリアル: Windows Communication Foundation クライアントを使用します。'
ms.date: 03/19/2019
helpviewer_keywords:
- WCF clients [WCF], using
dev_langs:
- CSharp
- VB
ms.assetid: 190349fc-0573-49c7-bb85-8e316df7f31f
ms.openlocfilehash: fa9aa3612a8dc72623fc4ea4b1ea337ac773fa26
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61928844"
---
# <a name="tutorial-use-a-windows-communication-foundation-client"></a><span data-ttu-id="d8246-102">チュートリアル: Windows Communication Foundation クライアントを使用します。</span><span class="sxs-lookup"><span data-stu-id="d8246-102">Tutorial: Use a Windows Communication Foundation client</span></span>

<span data-ttu-id="d8246-103">このチュートリアルでは、基本的な Windows Communication Foundation (WCF) アプリケーションを作成するために必要な 5 つのタスクの最後のタスクについて説明します。</span><span class="sxs-lookup"><span data-stu-id="d8246-103">This tutorial describes the last of five tasks required to create a basic Windows Communication Foundation (WCF) application.</span></span> <span data-ttu-id="d8246-104">チュートリアルの概要については、次を参照してください。[チュートリアル。Windows Communication Foundation アプリケーションの概要](getting-started-tutorial.md)します。</span><span class="sxs-lookup"><span data-stu-id="d8246-104">For an overview of the tutorials, see [Tutorial: Get started with Windows Communication Foundation applications](getting-started-tutorial.md).</span></span>

<span data-ttu-id="d8246-105">作成、Windows Communication Foundation (WCF) プロキシを構成したら後、は、クライアント インスタンスを作成し、クライアント アプリケーションをコンパイルします。</span><span class="sxs-lookup"><span data-stu-id="d8246-105">After you've created and configured a Windows Communication Foundation (WCF) proxy, you create a client instance and compile the client application.</span></span> <span data-ttu-id="d8246-106">使用する WCF サービスと通信します。</span><span class="sxs-lookup"><span data-stu-id="d8246-106">You then use it to communicate with the WCF service.</span></span> 

<span data-ttu-id="d8246-107">このチュートリアルでは、次の作業を行う方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="d8246-107">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
> - <span data-ttu-id="d8246-108">WCF クライアントを使用するコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="d8246-108">Add code to use the WCF client.</span></span>
> - <span data-ttu-id="d8246-109">WCF クライアントをテストします。</span><span class="sxs-lookup"><span data-stu-id="d8246-109">Test the WCF client.</span></span>

## <a name="add-code-to-use-the-wcf-client"></a><span data-ttu-id="d8246-110">WCF クライアントを使用するコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="d8246-110">Add code to use the WCF client</span></span>

<span data-ttu-id="d8246-111">クライアント コードは、次の手順を行います。</span><span class="sxs-lookup"><span data-stu-id="d8246-111">The client code does the following steps:</span></span>
- <span data-ttu-id="d8246-112">WCF クライアントをインスタンス化します。</span><span class="sxs-lookup"><span data-stu-id="d8246-112">Instantiates the WCF client.</span></span>
- <span data-ttu-id="d8246-113">生成されたプロキシからサービス操作を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="d8246-113">Calls the service operations from the generated proxy.</span></span>
- <span data-ttu-id="d8246-114">操作の呼び出しが完了した後は、クライアントを閉じます。</span><span class="sxs-lookup"><span data-stu-id="d8246-114">Closes the client after the operation call is completed.</span></span>

<span data-ttu-id="d8246-115">開く、 **Program.cs**または**Module1.vb**ファイルから、 **GettingStartedClient**プロジェクトし、そのコードを次のコードに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="d8246-115">Open the **Program.cs** or **Module1.vb** file from the **GettingStartedClient** project and replace its code with the following code:</span></span>

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

<span data-ttu-id="d8246-116">通知、 `using` (ビジュアルのC#) または`Imports`(Visual Basic) のインポート ステートメント`GettingStartedClient.ServiceReference1`します。</span><span class="sxs-lookup"><span data-stu-id="d8246-116">Notice the `using` (for Visual C#) or `Imports` (for Visual Basic) statement that imports `GettingStartedClient.ServiceReference1`.</span></span> <span data-ttu-id="d8246-117">このステートメントで Visual Studio が生成されたコードをインポートする、**サービス参照の追加**関数。</span><span class="sxs-lookup"><span data-stu-id="d8246-117">This statement imports the code that Visual Studio generated with the **Add Service Reference** function.</span></span> <span data-ttu-id="d8246-118">コードでは、WCF プロキシをインスタンス化し、電卓サービスを公開するサービス操作の各を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="d8246-118">The code instantiates the WCF proxy and calls each of the service operations that the calculator service exposes.</span></span> <span data-ttu-id="d8246-119">プロキシを終了し、プログラムが終了します。</span><span class="sxs-lookup"><span data-stu-id="d8246-119">It then closes the proxy and ends the program.</span></span>

## <a name="test-the-wcf-client"></a><span data-ttu-id="d8246-120">WCF クライアントをテストします。</span><span class="sxs-lookup"><span data-stu-id="d8246-120">Test the WCF client</span></span>

### <a name="test-the-application-from-visual-studio"></a><span data-ttu-id="d8246-121">Visual Studio からアプリケーションをテストします。</span><span class="sxs-lookup"><span data-stu-id="d8246-121">Test the application from Visual Studio</span></span>

1. <span data-ttu-id="d8246-122">保存し、ソリューションをビルドします。</span><span class="sxs-lookup"><span data-stu-id="d8246-122">Save and build the solution.</span></span>

2. <span data-ttu-id="d8246-123">選択、 **GettingStartedLib**フォルダー、および選択**スタートアップ プロジェクトとして設定**ショートカット メニューから。</span><span class="sxs-lookup"><span data-stu-id="d8246-123">Select the **GettingStartedLib** folder, and then select **Set as Startup Project** from the shortcut menu.</span></span>

3. <span data-ttu-id="d8246-124">**スタートアップ プロジェクト**を選択します**GettingStartedLib**ドロップダウン リストからを選択し、**実行**またはキーを押します**F5**します。</span><span class="sxs-lookup"><span data-stu-id="d8246-124">From **Startup Projects**, select **GettingStartedLib** from the drop-down list, then select **Run** or press **F5**.</span></span>

### <a name="test-the-application-from-a-command-prompt"></a><span data-ttu-id="d8246-125">コマンド プロンプトからアプリケーションをテストします。</span><span class="sxs-lookup"><span data-stu-id="d8246-125">Test the application from a command prompt</span></span>

1. <span data-ttu-id="d8246-126">管理者は、コマンド プロンプトを開きし、Visual Studio のソリューション ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="d8246-126">Open a command prompt as an administrator, and then navigate to your Visual Studio solution directory.</span></span> 

2. <span data-ttu-id="d8246-127">サービスを開始します。入力*GettingStartedHost\bin\Debug\GettingStartedHost.exe*します。</span><span class="sxs-lookup"><span data-stu-id="d8246-127">To start the service: Enter *GettingStartedHost\bin\Debug\GettingStartedHost.exe*.</span></span>

3. <span data-ttu-id="d8246-128">クライアントを起動します。別のコマンド プロンプトを開きし、Visual Studio のソリューション ディレクトリに移動して、入力*GettingStartedClient\bin\Debug\GettingStartedClient.exe*します。</span><span class="sxs-lookup"><span data-stu-id="d8246-128">To start the client: Open another command prompt, navigate to your Visual Studio solution directory, then enter *GettingStartedClient\bin\Debug\GettingStartedClient.exe*.</span></span>

   <span data-ttu-id="d8246-129">*GettingStartedHost.exe*次の出力が生成されます。</span><span class="sxs-lookup"><span data-stu-id="d8246-129">*GettingStartedHost.exe* produces the following output:</span></span>

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

   <span data-ttu-id="d8246-130">*GettingStartedClient.exe*次の出力が生成されます。</span><span class="sxs-lookup"><span data-stu-id="d8246-130">*GettingStartedClient.exe* produces the following output:</span></span>

   ```text
   Add(100,15.99) = 115.99
   Subtract(145,76.54) = 68.46
   Multiply(9,81.25) = 731.25
   Divide(22,7) = 3.14285714285714

   Press <Enter> to terminate the client.
   ```

## <a name="next-steps"></a><span data-ttu-id="d8246-131">次の手順</span><span class="sxs-lookup"><span data-stu-id="d8246-131">Next steps</span></span>

<span data-ttu-id="d8246-132">WCF 入門チュートリアルで、すべてのタスクを完了します。</span><span class="sxs-lookup"><span data-stu-id="d8246-132">You've now completed all the tasks in the WCF get started tutorial.</span></span> <span data-ttu-id="d8246-133">このチュートリアルでは、次の作業を行う方法を学びました。</span><span class="sxs-lookup"><span data-stu-id="d8246-133">In this tutorial, you learned how to:</span></span>

<span data-ttu-id="d8246-134">このチュートリアルでは、次の作業を行う方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="d8246-134">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
> - <span data-ttu-id="d8246-135">WCF クライアントを使用するコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="d8246-135">Add code to use the WCF client.</span></span>
> - <span data-ttu-id="d8246-136">WCF クライアントをテストします。</span><span class="sxs-lookup"><span data-stu-id="d8246-136">Test the WCF client.</span></span>

<span data-ttu-id="d8246-137">手順のいずれかである場合の問題やエラーは場合は、それを修正するトラブルシューティング記事の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="d8246-137">If you have problems or errors in any of the steps, follow the steps in the troubleshooting article to fix them.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="d8246-138">Get のトラブルシューティングでは、WCF のチュートリアルを開始</span><span class="sxs-lookup"><span data-stu-id="d8246-138">Troubleshoot the Get started with WCF tutorials</span></span>](troubleshooting-the-getting-started-tutorial.md)
