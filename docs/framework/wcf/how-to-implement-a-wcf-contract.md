---
title: 'チュートリアル: Windows Communication Foundation サービスコントラクトの実装'
description: Wcf アプリケーションの作成を開始する際に役立つ一連の記事の一部として、WCF サービスインターフェイスを実装するコードを追加する方法について説明します。
ms.date: 03/19/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- service contracts [WCF], implementing
ms.assetid: d5ab51ba-61ae-403e-b3c8-e2669e326806
ms.openlocfilehash: 89f97610cccd42c2a5d298baa667327d077fd472
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/23/2020
ms.locfileid: "85244648"
---
# <a name="tutorial-implement-a-windows-communication-foundation-service-contract"></a><span data-ttu-id="d0da6-103">チュートリアル: Windows Communication Foundation サービスコントラクトの実装</span><span class="sxs-lookup"><span data-stu-id="d0da6-103">Tutorial: Implement a Windows Communication Foundation service contract</span></span>

<span data-ttu-id="d0da6-104">このチュートリアルでは、基本的な Windows Communication Foundation (WCF) アプリケーションを作成するために必要な5つのタスクについて説明します。</span><span class="sxs-lookup"><span data-stu-id="d0da6-104">This tutorial describes the second of five tasks required to create a basic Windows Communication Foundation (WCF) application.</span></span> <span data-ttu-id="d0da6-105">チュートリアルの概要については、「[チュートリアル: Windows Communication Foundation アプリケーションの](getting-started-tutorial.md)概要」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d0da6-105">For an overview of the tutorials, see [Tutorial: Get started with Windows Communication Foundation applications](getting-started-tutorial.md).</span></span>

<span data-ttu-id="d0da6-106">WCF アプリケーションを作成するための次の手順では、前の手順で作成した WCF サービスインターフェイスを実装するコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="d0da6-106">The next step for creating a WCF application is to add code to implement the WCF service interface that you created in the previous step.</span></span> <span data-ttu-id="d0da6-107">この手順では、ユーザー定義のインターフェイスを実装するという名前のクラスを作成し `CalculatorService` `ICalculator` ます。</span><span class="sxs-lookup"><span data-stu-id="d0da6-107">In this step, you create a class named `CalculatorService` that implements the user-defined `ICalculator` interface.</span></span> <span data-ttu-id="d0da6-108">次のコードの各メソッドは、電卓操作を呼び出し、テキストをコンソールに書き込んでテストします。</span><span class="sxs-lookup"><span data-stu-id="d0da6-108">Each method in the following code calls a calculator operation and writes text to the console to test it.</span></span>

<span data-ttu-id="d0da6-109">このチュートリアルでは、次の作業を行う方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="d0da6-109">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="d0da6-110">WCF サービスコントラクトを実装するコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="d0da6-110">Add code to implement the WCF service contract.</span></span>
> - <span data-ttu-id="d0da6-111">ソリューションをビルドします。</span><span class="sxs-lookup"><span data-stu-id="d0da6-111">Build the solution.</span></span>

## <a name="add-code-to-implement-the-wcf-service-contract"></a><span data-ttu-id="d0da6-112">WCF サービスコントラクトを実装するコードを追加する</span><span class="sxs-lookup"><span data-stu-id="d0da6-112">Add code to implement the WCF service contract</span></span>

<span data-ttu-id="d0da6-113">**Service1.cs**または**Service1**ファイルを**開き、その**コードを次のコードに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="d0da6-113">In **GettingStartedLib**, open the **Service1.cs** or **Service1.vb** file and replace its code with the following code:</span></span>

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

## <a name="edit-appconfig"></a><span data-ttu-id="d0da6-114">App.config の編集</span><span class="sxs-lookup"><span data-stu-id="d0da6-114">Edit App.config</span></span>

<span data-ttu-id="d0da6-115">**Gettingon lib**で**App.config**を編集して、コードに加えた変更を反映します。</span><span class="sxs-lookup"><span data-stu-id="d0da6-115">Edit **App.config** in **GettingStartedLib** to reflect the changes you made to the code.</span></span>

- <span data-ttu-id="d0da6-116">Visual C# プロジェクトの場合:</span><span class="sxs-lookup"><span data-stu-id="d0da6-116">For Visual C# projects:</span></span>
  - <span data-ttu-id="d0da6-117">14行目をに変更します。`<service name="GettingStartedLib.CalculatorService">`</span><span class="sxs-lookup"><span data-stu-id="d0da6-117">Change line 14 to `<service name="GettingStartedLib.CalculatorService">`</span></span>
  - <span data-ttu-id="d0da6-118">17行目をに変更します。`<add baseAddress = "http://localhost:8000/GettingStarted/CalculatorService" />`</span><span class="sxs-lookup"><span data-stu-id="d0da6-118">Change line 17 to `<add baseAddress = "http://localhost:8000/GettingStarted/CalculatorService" />`</span></span>
  - <span data-ttu-id="d0da6-119">22行目をに変更します。`<endpoint address="" binding="wsHttpBinding" contract="GettingStartedLib.ICalculator">`</span><span class="sxs-lookup"><span data-stu-id="d0da6-119">Change line 22 to `<endpoint address="" binding="wsHttpBinding" contract="GettingStartedLib.ICalculator">`</span></span>

- <span data-ttu-id="d0da6-120">Visual Basic プロジェクトの場合は、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="d0da6-120">For Visual Basic projects:</span></span>
  - <span data-ttu-id="d0da6-121">14行目をに変更します。`<service name="GettingStartedLib.GettingStartedLib.CalculatorService">`</span><span class="sxs-lookup"><span data-stu-id="d0da6-121">Change line 14 to `<service name="GettingStartedLib.GettingStartedLib.CalculatorService">`</span></span>
  - <span data-ttu-id="d0da6-122">17行目をに変更します。`<add baseAddress = "http://localhost:8000/GettingStarted/CalculatorService" />`</span><span class="sxs-lookup"><span data-stu-id="d0da6-122">Change line 17 to `<add baseAddress = "http://localhost:8000/GettingStarted/CalculatorService" />`</span></span>
  - <span data-ttu-id="d0da6-123">22行目をに変更します。`<endpoint address="" binding="wsHttpBinding" contract="GettingStartedLib.GettingStartedLib.ICalculator">`</span><span class="sxs-lookup"><span data-stu-id="d0da6-123">Change line 22 to `<endpoint address="" binding="wsHttpBinding" contract="GettingStartedLib.GettingStartedLib.ICalculator">`</span></span>

## <a name="compile-the-code"></a><span data-ttu-id="d0da6-124">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="d0da6-124">Compile the code</span></span>

<span data-ttu-id="d0da6-125">ソリューションをビルドして、コンパイルエラーがないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="d0da6-125">Build the solution to verify there aren't any compilation errors.</span></span> <span data-ttu-id="d0da6-126">Visual Studio を使用している場合は、[**ビルド**] メニューの [**ソリューションのビルド**] を選択します (または、 **Ctrl** + **Shift** + **B**キーを押します)。</span><span class="sxs-lookup"><span data-stu-id="d0da6-126">If you're using Visual Studio, on the **Build** menu select **Build Solution** (or press **Ctrl**+**Shift**+**B**).</span></span>

## <a name="next-steps"></a><span data-ttu-id="d0da6-127">次の手順</span><span class="sxs-lookup"><span data-stu-id="d0da6-127">Next steps</span></span>

<span data-ttu-id="d0da6-128">このチュートリアルでは、以下の内容を学習しました。</span><span class="sxs-lookup"><span data-stu-id="d0da6-128">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="d0da6-129">WCF サービスコントラクトを実装するコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="d0da6-129">Add code to implement the WCF service contract.</span></span>
> - <span data-ttu-id="d0da6-130">ソリューションをビルドします。</span><span class="sxs-lookup"><span data-stu-id="d0da6-130">Build the solution.</span></span>

<span data-ttu-id="d0da6-131">次のチュートリアルに進み、WCF サービスを実行する方法を学習してください。</span><span class="sxs-lookup"><span data-stu-id="d0da6-131">Advance to the next tutorial to learn how to run the WCF service.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="d0da6-132">チュートリアル: 基本的な WCF サービスをホストして実行する</span><span class="sxs-lookup"><span data-stu-id="d0da6-132">Tutorial: Host and run a basic WCF service</span></span>](how-to-host-and-run-a-basic-wcf-service.md)
