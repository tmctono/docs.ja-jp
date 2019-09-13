---
title: 'チュートリアル: Windows Communication Foundation サービスコントラクトを実装する'
ms.date: 03/19/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- service contracts [WCF], implementing
ms.assetid: d5ab51ba-61ae-403e-b3c8-e2669e326806
ms.openlocfilehash: 05923dc0a2223da5e5fcda483abc1ee1dd2d643f
ms.sourcegitcommit: 33c8d6f7342a4bb2c577842b7f075b0e20a2fa40
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2019
ms.locfileid: "70928704"
---
# <a name="tutorial-implement-a-windows-communication-foundation-service-contract"></a><span data-ttu-id="75858-102">チュートリアル: Windows Communication Foundation サービスコントラクトを実装する</span><span class="sxs-lookup"><span data-stu-id="75858-102">Tutorial: Implement a Windows Communication Foundation service contract</span></span>

<span data-ttu-id="75858-103">このチュートリアルでは、基本的な Windows Communication Foundation (WCF) アプリケーションを作成するために必要な5つのタスクについて説明します。</span><span class="sxs-lookup"><span data-stu-id="75858-103">This tutorial describes the second of five tasks required to create a basic Windows Communication Foundation (WCF) application.</span></span> <span data-ttu-id="75858-104">チュートリアルの概要については、 [「チュートリアル:Windows Communication Foundation アプリケーション](getting-started-tutorial.md)の概要」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="75858-104">For an overview of the tutorials, see [Tutorial: Get started with Windows Communication Foundation applications](getting-started-tutorial.md).</span></span>

<span data-ttu-id="75858-105">WCF アプリケーションを作成するための次の手順では、前の手順で作成した WCF サービスインターフェイスを実装するコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="75858-105">The next step for creating a WCF application is to add code to implement the WCF service interface that you created in the previous step.</span></span> <span data-ttu-id="75858-106">この手順では、ユーザー定義`CalculatorService` `ICalculator`のインターフェイスを実装するという名前のクラスを作成します。</span><span class="sxs-lookup"><span data-stu-id="75858-106">In this step, you create a class named `CalculatorService` that implements the user-defined `ICalculator` interface.</span></span> <span data-ttu-id="75858-107">次のコードの各メソッドは、電卓操作を呼び出し、テキストをコンソールに書き込んでテストします。</span><span class="sxs-lookup"><span data-stu-id="75858-107">Each method in the following code calls a calculator operation and writes text to the console to test it.</span></span> 

<span data-ttu-id="75858-108">このチュートリアルでは、次の作業を行う方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="75858-108">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="75858-109">WCF サービスコントラクトを実装するコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="75858-109">Add code to implement the WCF service contract.</span></span>
> - <span data-ttu-id="75858-110">ソリューションをビルドします。</span><span class="sxs-lookup"><span data-stu-id="75858-110">Build the solution.</span></span>

## <a name="add-code-to-implement-the-wcf-service-contract"></a><span data-ttu-id="75858-111">WCF サービスコントラクトを実装するコードを追加する</span><span class="sxs-lookup"><span data-stu-id="75858-111">Add code to implement the WCF service contract</span></span>

<span data-ttu-id="75858-112">**Service1.cs**または**Service1**ファイルを**開き、その**コードを次のコードに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="75858-112">In **GettingStartedLib**, open the **Service1.cs** or **Service1.vb** file and replace its code with the following code:</span></span>

```csharp
using System;
using System.ServiceModel;

namespace GettingStartedLib
{
    public class CalculatorService : ICalculator
    {
        public double Add(double n1, double n2)
        {
            double result = n1 + n2;
            Console.WriteLine("Received Add({0},{1})", n1, n2);
            // Code added to write output to the console window.
            Console.WriteLine("Return: {0}", result);
            return result;
        }

        public double Subtract(double n1, double n2)
        {
            double result = n1 - n2;
            Console.WriteLine("Received Subtract({0},{1})", n1, n2);
            Console.WriteLine("Return: {0}", result);
            return result;
        }

        public double Multiply(double n1, double n2)
        {
            double result = n1 * n2;
            Console.WriteLine("Received Multiply({0},{1})", n1, n2);
            Console.WriteLine("Return: {0}", result);
            return result;
        }

        public double Divide(double n1, double n2)
        {
            double result = n1 / n2;
            Console.WriteLine("Received Divide({0},{1})", n1, n2);
            Console.WriteLine("Return: {0}", result);
            return result;
        }
    }
}
```

```vb
Imports System.ServiceModel

Namespace GettingStartedLib

    Public Class CalculatorService
        Implements ICalculator

        Public Function Add(ByVal n1 As Double, ByVal n2 As Double) As Double Implements ICalculator.Add
            Dim result As Double = n1 + n2
            ' Code added to write output to the console window.
            Console.WriteLine("Received Add({0},{1})", n1, n2)
            Console.WriteLine("Return: {0}", result)
            Return result
        End Function

        Public Function Subtract(ByVal n1 As Double, ByVal n2 As Double) As Double Implements ICalculator.Subtract
            Dim result As Double = n1 - n2
            Console.WriteLine("Received Subtract({0},{1})", n1, n2)
            Console.WriteLine("Return: {0}", result)
            Return result

        End Function

        Public Function Multiply(ByVal n1 As Double, ByVal n2 As Double) As Double Implements ICalculator.Multiply
            Dim result As Double = n1 * n2
            Console.WriteLine("Received Multiply({0},{1})", n1, n2)
            Console.WriteLine("Return: {0}", result)
            Return result

        End Function

        Public Function Divide(ByVal n1 As Double, ByVal n2 As Double) As Double Implements ICalculator.Divide
            Dim result As Double = n1 / n2
            Console.WriteLine("Received Divide({0},{1})", n1, n2)
            Console.WriteLine("Return: {0}", result)
            Return result

        End Function
    End Class
End Namespace
```

## <a name="edit-appconfig"></a><span data-ttu-id="75858-113">App.config の編集</span><span class="sxs-lookup"><span data-stu-id="75858-113">Edit App.config</span></span>

<span data-ttu-id="75858-114">**Gettingstartedlib**で**app.config**を編集して、コードに加えた変更を反映します。</span><span class="sxs-lookup"><span data-stu-id="75858-114">Edit **App.config** in **GettingStartedLib** to reflect the changes you made to the code.</span></span>

- <span data-ttu-id="75858-115">Visual C#プロジェクトの場合:</span><span class="sxs-lookup"><span data-stu-id="75858-115">For Visual C# projects:</span></span>
  - <span data-ttu-id="75858-116">14行目をに変更します。`<service name="GettingStartedLib.CalculatorService">`</span><span class="sxs-lookup"><span data-stu-id="75858-116">Change line 14 to `<service name="GettingStartedLib.CalculatorService">`</span></span>
  - <span data-ttu-id="75858-117">17行目をに変更します。`<add baseAddress = "http://localhost:8000/GettingStarted/CalculatorService" />`</span><span class="sxs-lookup"><span data-stu-id="75858-117">Change line 17 to `<add baseAddress = "http://localhost:8000/GettingStarted/CalculatorService" />`</span></span>
  - <span data-ttu-id="75858-118">22行目をに変更します。`<endpoint address="" binding="wsHttpBinding" contract="GettingStartedLib.ICalculator">`</span><span class="sxs-lookup"><span data-stu-id="75858-118">Change line 22 to `<endpoint address="" binding="wsHttpBinding" contract="GettingStartedLib.ICalculator">`</span></span>

- <span data-ttu-id="75858-119">Visual Basic プロジェクトの場合は、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="75858-119">For Visual Basic projects:</span></span>
  - <span data-ttu-id="75858-120">14行目をに変更します。`<service name="GettingStartedLib.GettingStartedLib.CalculatorService">`</span><span class="sxs-lookup"><span data-stu-id="75858-120">Change line 14 to `<service name="GettingStartedLib.GettingStartedLib.CalculatorService">`</span></span>
  - <span data-ttu-id="75858-121">17行目をに変更します。`<add baseAddress = "http://localhost:8000/GettingStarted/CalculatorService" />`</span><span class="sxs-lookup"><span data-stu-id="75858-121">Change line 17 to `<add baseAddress = "http://localhost:8000/GettingStarted/CalculatorService" />`</span></span>
  - <span data-ttu-id="75858-122">22行目をに変更します。`<endpoint address="" binding="wsHttpBinding" contract="GettingStartedLib.GettingStartedLib.ICalculator">`</span><span class="sxs-lookup"><span data-stu-id="75858-122">Change line 22 to `<endpoint address="" binding="wsHttpBinding" contract="GettingStartedLib.GettingStartedLib.ICalculator">`</span></span>

## <a name="compile-the-code"></a><span data-ttu-id="75858-123">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="75858-123">Compile the code</span></span>

<span data-ttu-id="75858-124">ソリューションをビルドして、コンパイルエラーがないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="75858-124">Build the solution to verify there aren't any compilation errors.</span></span> <span data-ttu-id="75858-125">Visual Studio を使用している場合は、 **[ビルド]** メニューの **[ソリューションのビルド]** を選択します (または、 **Ctrl**+**Shift**+**B**キーを押します)。</span><span class="sxs-lookup"><span data-stu-id="75858-125">If you're using Visual Studio, on the **Build** menu select **Build Solution** (or press **Ctrl**+**Shift**+**B**).</span></span>

## <a name="next-steps"></a><span data-ttu-id="75858-126">次の手順</span><span class="sxs-lookup"><span data-stu-id="75858-126">Next steps</span></span>

<span data-ttu-id="75858-127">このチュートリアルでは、次の作業を行う方法を学びました。</span><span class="sxs-lookup"><span data-stu-id="75858-127">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="75858-128">WCF サービスコントラクトを実装するコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="75858-128">Add code to implement the WCF service contract.</span></span>
> - <span data-ttu-id="75858-129">ソリューションをビルドします。</span><span class="sxs-lookup"><span data-stu-id="75858-129">Build the solution.</span></span>

<span data-ttu-id="75858-130">次のチュートリアルに進み、WCF サービスを実行する方法を学習してください。</span><span class="sxs-lookup"><span data-stu-id="75858-130">Advance to the next tutorial to learn how to run the WCF service.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="75858-131">チュートリアル: 基本的な WCF サービスをホストして実行する</span><span class="sxs-lookup"><span data-stu-id="75858-131">Tutorial: Host and run a basic WCF service</span></span>](how-to-host-and-run-a-basic-wcf-service.md)
