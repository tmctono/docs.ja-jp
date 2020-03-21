---
title: 'チュートリアル: Windows コミュニケーション ファウンデーション クライアントを使用する'
ms.date: 03/19/2019
helpviewer_keywords:
- WCF clients [WCF], using
dev_langs:
- CSharp
- VB
ms.assetid: 190349fc-0573-49c7-bb85-8e316df7f31f
ms.openlocfilehash: d2357c134aef8da204dcdb19d6c1fc93cfdc068c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184008"
---
# <a name="tutorial-use-a-windows-communication-foundation-client"></a><span data-ttu-id="61404-102">チュートリアル: Windows コミュニケーション ファウンデーション クライアントを使用する</span><span class="sxs-lookup"><span data-stu-id="61404-102">Tutorial: Use a Windows Communication Foundation client</span></span>

<span data-ttu-id="61404-103">このチュートリアルでは、基本的な Wcf (WCF) アプリケーションを作成するために必要な最後の 5 つのタスクについて説明します。</span><span class="sxs-lookup"><span data-stu-id="61404-103">This tutorial describes the last of five tasks required to create a basic Windows Communication Foundation (WCF) application.</span></span> <span data-ttu-id="61404-104">チュートリアルの概要については、「[チュートリアル: Windows コミュニケーションファウンデーション アプリケーションの概要](getting-started-tutorial.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="61404-104">For an overview of the tutorials, see [Tutorial: Get started with Windows Communication Foundation applications](getting-started-tutorial.md).</span></span>

<span data-ttu-id="61404-105">Windows 通信基盤 (WCF) プロキシを作成して構成したら、クライアント インスタンスを作成し、クライアント アプリケーションをコンパイルします。</span><span class="sxs-lookup"><span data-stu-id="61404-105">After you've created and configured a Windows Communication Foundation (WCF) proxy, you create a client instance and compile the client application.</span></span> <span data-ttu-id="61404-106">次に、このサービスを使用して WCF サービスと通信します。</span><span class="sxs-lookup"><span data-stu-id="61404-106">You then use it to communicate with the WCF service.</span></span>

<span data-ttu-id="61404-107">このチュートリアルでは、以下の内容を学習します。</span><span class="sxs-lookup"><span data-stu-id="61404-107">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="61404-108">WCF クライアントを使用するコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="61404-108">Add code to use the WCF client.</span></span>
> - <span data-ttu-id="61404-109">WCF クライアントをテストします。</span><span class="sxs-lookup"><span data-stu-id="61404-109">Test the WCF client.</span></span>

## <a name="add-code-to-use-the-wcf-client"></a><span data-ttu-id="61404-110">WCF クライアントを使用するコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="61404-110">Add code to use the WCF client</span></span>

<span data-ttu-id="61404-111">クライアント コードは、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="61404-111">The client code does the following steps:</span></span>

- <span data-ttu-id="61404-112">WCF クライアントをインスタンス化します。</span><span class="sxs-lookup"><span data-stu-id="61404-112">Instantiates the WCF client.</span></span>
- <span data-ttu-id="61404-113">生成されたプロキシからサービス操作を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="61404-113">Calls the service operations from the generated proxy.</span></span>
- <span data-ttu-id="61404-114">操作の呼び出しが完了した後にクライアントを閉じます。</span><span class="sxs-lookup"><span data-stu-id="61404-114">Closes the client after the operation call is completed.</span></span>

<span data-ttu-id="61404-115">**プロジェクト**から**Program.cs**または**Module1.vb**ファイルを開き、コードを次のコードに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="61404-115">Open the **Program.cs** or **Module1.vb** file from the **GettingStartedClient** project and replace its code with the following code:</span></span>

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

<span data-ttu-id="61404-116">インポートする`using`ステートメント (Visual C#`Imports`の場合) または (Visual `GettingStartedClient.ServiceReference1`Basic の場合) に注意してください。</span><span class="sxs-lookup"><span data-stu-id="61404-116">Notice the `using` (for Visual C#) or `Imports` (for Visual Basic) statement that imports `GettingStartedClient.ServiceReference1`.</span></span> <span data-ttu-id="61404-117">このステートメントは、Visual Studio が**サービス参照の追加**機能で生成したコードをインポートします。</span><span class="sxs-lookup"><span data-stu-id="61404-117">This statement imports the code that Visual Studio generated with the **Add Service Reference** function.</span></span> <span data-ttu-id="61404-118">このコードは、WCF プロキシをインスタンス化し、電卓サービスが公開する各サービス操作を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="61404-118">The code instantiates the WCF proxy and calls each of the service operations that the calculator service exposes.</span></span> <span data-ttu-id="61404-119">次に、プロキシを閉じ、プログラムを終了します。</span><span class="sxs-lookup"><span data-stu-id="61404-119">It then closes the proxy and ends the program.</span></span>

## <a name="test-the-wcf-client"></a><span data-ttu-id="61404-120">WCF クライアントをテストする</span><span class="sxs-lookup"><span data-stu-id="61404-120">Test the WCF client</span></span>

### <a name="test-the-application-from-visual-studio"></a><span data-ttu-id="61404-121">アプリケーションを Visual Studio からテストする</span><span class="sxs-lookup"><span data-stu-id="61404-121">Test the application from Visual Studio</span></span>

1. <span data-ttu-id="61404-122">保存し、ソリューションをビルドします。</span><span class="sxs-lookup"><span data-stu-id="61404-122">Save and build the solution.</span></span>

2. <span data-ttu-id="61404-123">**[開始] フォルダー**を選択し、ショートカット メニューから **[スタートアップ プロジェクトとして設定**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="61404-123">Select the **GettingStartedLib** folder, and then select **Set as Startup Project** from the shortcut menu.</span></span>

3. <span data-ttu-id="61404-124">スタートアップ**プロジェクト**で、ドロップダウン リスト**から [FromStartedLib]** を選択し、[**実行**] を選択するか **、F5**キーを押します。</span><span class="sxs-lookup"><span data-stu-id="61404-124">From **Startup Projects**, select **GettingStartedLib** from the drop-down list, then select **Run** or press **F5**.</span></span>

### <a name="test-the-application-from-a-command-prompt"></a><span data-ttu-id="61404-125">コマンド プロンプトからアプリケーションをテストする</span><span class="sxs-lookup"><span data-stu-id="61404-125">Test the application from a command prompt</span></span>

1. <span data-ttu-id="61404-126">管理者としてコマンド プロンプトを開き、Visual Studio ソリューション ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="61404-126">Open a command prompt as an administrator, and then navigate to your Visual Studio solution directory.</span></span>

2. <span data-ttu-id="61404-127">サービスを開始するには、*次のように*入力します。</span><span class="sxs-lookup"><span data-stu-id="61404-127">To start the service: Enter *GettingStartedHost\bin\Debug\GettingStartedHost.exe*.</span></span>

3. <span data-ttu-id="61404-128">クライアントを起動するには、別のコマンド プロンプトを開き、Visual Studio ソリューション ディレクトリに移動し *、「GettingStartedClient\bin\Debug\GettingStartedClient.exe」* と入力します。</span><span class="sxs-lookup"><span data-stu-id="61404-128">To start the client: Open another command prompt, navigate to your Visual Studio solution directory, then enter *GettingStartedClient\bin\Debug\GettingStartedClient.exe*.</span></span>

   <span data-ttu-id="61404-129">*次の*出力が生成されます。</span><span class="sxs-lookup"><span data-stu-id="61404-129">*GettingStartedHost.exe* produces the following output:</span></span>

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

   <span data-ttu-id="61404-130">*次の*出力が生成されます。</span><span class="sxs-lookup"><span data-stu-id="61404-130">*GettingStartedClient.exe* produces the following output:</span></span>

   ```text
   Add(100,15.99) = 115.99
   Subtract(145,76.54) = 68.46
   Multiply(9,81.25) = 731.25
   Divide(22,7) = 3.14285714285714

   Press <Enter> to terminate the client.
   ```

## <a name="next-steps"></a><span data-ttu-id="61404-131">次のステップ</span><span class="sxs-lookup"><span data-stu-id="61404-131">Next steps</span></span>

<span data-ttu-id="61404-132">これで、WCF の概要チュートリアルのすべてのタスクが完了しました。</span><span class="sxs-lookup"><span data-stu-id="61404-132">You've now completed all the tasks in the WCF get started tutorial.</span></span> <span data-ttu-id="61404-133">このチュートリアルでは、以下の内容を学習しました。</span><span class="sxs-lookup"><span data-stu-id="61404-133">In this tutorial, you learned how to:</span></span>

<span data-ttu-id="61404-134">このチュートリアルでは、以下の内容を学習します。</span><span class="sxs-lookup"><span data-stu-id="61404-134">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="61404-135">WCF クライアントを使用するコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="61404-135">Add code to use the WCF client.</span></span>
> - <span data-ttu-id="61404-136">WCF クライアントをテストします。</span><span class="sxs-lookup"><span data-stu-id="61404-136">Test the WCF client.</span></span>

<span data-ttu-id="61404-137">いずれかの手順で問題やエラーが発生した場合は、トラブルシューティングの記事の手順に従って修正します。</span><span class="sxs-lookup"><span data-stu-id="61404-137">If you have problems or errors in any of the steps, follow the steps in the troubleshooting article to fix them.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="61404-138">WCF チュートリアルの概要のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="61404-138">Troubleshoot the Get started with WCF tutorials</span></span>](troubleshooting-the-getting-started-tutorial.md)
