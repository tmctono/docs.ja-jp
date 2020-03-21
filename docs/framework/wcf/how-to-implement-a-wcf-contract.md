---
title: 'チュートリアル: Windows 通信基盤サービス コントラクトを実装する'
ms.date: 03/19/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- service contracts [WCF], implementing
ms.assetid: d5ab51ba-61ae-403e-b3c8-e2669e326806
ms.openlocfilehash: debdeeac7064f5bae21622b2d9de84a4d8a0e66f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184065"
---
# <a name="tutorial-implement-a-windows-communication-foundation-service-contract"></a><span data-ttu-id="725a2-102">チュートリアル: Windows 通信基盤サービス コントラクトを実装する</span><span class="sxs-lookup"><span data-stu-id="725a2-102">Tutorial: Implement a Windows Communication Foundation service contract</span></span>

<span data-ttu-id="725a2-103">このチュートリアルでは、基本的な Wcf (WCF) アプリケーションを作成するために必要な 5 つのタスクの 2 つ目について説明します。</span><span class="sxs-lookup"><span data-stu-id="725a2-103">This tutorial describes the second of five tasks required to create a basic Windows Communication Foundation (WCF) application.</span></span> <span data-ttu-id="725a2-104">チュートリアルの概要については、「[チュートリアル: Windows コミュニケーションファウンデーション アプリケーションの概要](getting-started-tutorial.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="725a2-104">For an overview of the tutorials, see [Tutorial: Get started with Windows Communication Foundation applications](getting-started-tutorial.md).</span></span>

<span data-ttu-id="725a2-105">WCF アプリケーションを作成するための次の手順は、前の手順で作成した WCF サービス インターフェイスを実装するコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="725a2-105">The next step for creating a WCF application is to add code to implement the WCF service interface that you created in the previous step.</span></span> <span data-ttu-id="725a2-106">この手順では、ユーザー定義`CalculatorService``ICalculator`インターフェイスを実装するクラスを作成します。</span><span class="sxs-lookup"><span data-stu-id="725a2-106">In this step, you create a class named `CalculatorService` that implements the user-defined `ICalculator` interface.</span></span> <span data-ttu-id="725a2-107">次のコードの各メソッドは、電卓の操作を呼び出し、コンソールにテキストを書き込んでテストします。</span><span class="sxs-lookup"><span data-stu-id="725a2-107">Each method in the following code calls a calculator operation and writes text to the console to test it.</span></span>

<span data-ttu-id="725a2-108">このチュートリアルでは、以下の内容を学習します。</span><span class="sxs-lookup"><span data-stu-id="725a2-108">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="725a2-109">WCF サービス コントラクトを実装するコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="725a2-109">Add code to implement the WCF service contract.</span></span>
> - <span data-ttu-id="725a2-110">ソリューションをビルドします。</span><span class="sxs-lookup"><span data-stu-id="725a2-110">Build the solution.</span></span>

## <a name="add-code-to-implement-the-wcf-service-contract"></a><span data-ttu-id="725a2-111">WCF サービス コントラクトを実装するコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="725a2-111">Add code to implement the WCF service contract</span></span>

<span data-ttu-id="725a2-112">**で、Service1.cs**または**Service1.cs\*\*\*\*Service1.vb**ファイルを開き、コードを次のコードに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="725a2-112">In **GettingStartedLib**, open the **Service1.cs** or **Service1.vb** file and replace its code with the following code:</span></span>

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

## <a name="edit-appconfig"></a><span data-ttu-id="725a2-113">アプリケーション構成の編集</span><span class="sxs-lookup"><span data-stu-id="725a2-113">Edit App.config</span></span>

<span data-ttu-id="725a2-114">コードに加えた変更を反映するように **、次のコードを取得中に Lib**で**App.config**を編集します。</span><span class="sxs-lookup"><span data-stu-id="725a2-114">Edit **App.config** in **GettingStartedLib** to reflect the changes you made to the code.</span></span>

- <span data-ttu-id="725a2-115">Visual C# プロジェクトの場合:</span><span class="sxs-lookup"><span data-stu-id="725a2-115">For Visual C# projects:</span></span>
  - <span data-ttu-id="725a2-116">行 14 を次の行に変更`<service name="GettingStartedLib.CalculatorService">`</span><span class="sxs-lookup"><span data-stu-id="725a2-116">Change line 14 to `<service name="GettingStartedLib.CalculatorService">`</span></span>
  - <span data-ttu-id="725a2-117">行 17 を次の行に変更`<add baseAddress = "http://localhost:8000/GettingStarted/CalculatorService" />`</span><span class="sxs-lookup"><span data-stu-id="725a2-117">Change line 17 to `<add baseAddress = "http://localhost:8000/GettingStarted/CalculatorService" />`</span></span>
  - <span data-ttu-id="725a2-118">行 22 を次の行に変更します`<endpoint address="" binding="wsHttpBinding" contract="GettingStartedLib.ICalculator">`</span><span class="sxs-lookup"><span data-stu-id="725a2-118">Change line 22 to `<endpoint address="" binding="wsHttpBinding" contract="GettingStartedLib.ICalculator">`</span></span>

- <span data-ttu-id="725a2-119">Visual Basic プロジェクトの場合は、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="725a2-119">For Visual Basic projects:</span></span>
  - <span data-ttu-id="725a2-120">行 14 を次の行に変更`<service name="GettingStartedLib.GettingStartedLib.CalculatorService">`</span><span class="sxs-lookup"><span data-stu-id="725a2-120">Change line 14 to `<service name="GettingStartedLib.GettingStartedLib.CalculatorService">`</span></span>
  - <span data-ttu-id="725a2-121">行 17 を次の行に変更`<add baseAddress = "http://localhost:8000/GettingStarted/CalculatorService" />`</span><span class="sxs-lookup"><span data-stu-id="725a2-121">Change line 17 to `<add baseAddress = "http://localhost:8000/GettingStarted/CalculatorService" />`</span></span>
  - <span data-ttu-id="725a2-122">行 22 を次の行に変更します`<endpoint address="" binding="wsHttpBinding" contract="GettingStartedLib.GettingStartedLib.ICalculator">`</span><span class="sxs-lookup"><span data-stu-id="725a2-122">Change line 22 to `<endpoint address="" binding="wsHttpBinding" contract="GettingStartedLib.GettingStartedLib.ICalculator">`</span></span>

## <a name="compile-the-code"></a><span data-ttu-id="725a2-123">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="725a2-123">Compile the code</span></span>

<span data-ttu-id="725a2-124">コンパイル エラーがないことを確認するソリューションをビルドします。</span><span class="sxs-lookup"><span data-stu-id="725a2-124">Build the solution to verify there aren't any compilation errors.</span></span> <span data-ttu-id="725a2-125">Visual Studio を使用している場合は、[**ビルド**] メニューの [**ソリューションのビルド**] を選択します (または**Ctrl**+**Shift**+**B**キーを押します)。</span><span class="sxs-lookup"><span data-stu-id="725a2-125">If you're using Visual Studio, on the **Build** menu select **Build Solution** (or press **Ctrl**+**Shift**+**B**).</span></span>

## <a name="next-steps"></a><span data-ttu-id="725a2-126">次のステップ</span><span class="sxs-lookup"><span data-stu-id="725a2-126">Next steps</span></span>

<span data-ttu-id="725a2-127">このチュートリアルでは、以下の内容を学習しました。</span><span class="sxs-lookup"><span data-stu-id="725a2-127">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="725a2-128">WCF サービス コントラクトを実装するコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="725a2-128">Add code to implement the WCF service contract.</span></span>
> - <span data-ttu-id="725a2-129">ソリューションをビルドします。</span><span class="sxs-lookup"><span data-stu-id="725a2-129">Build the solution.</span></span>

<span data-ttu-id="725a2-130">WCF サービスの実行方法については、次のチュートリアルに進んでください。</span><span class="sxs-lookup"><span data-stu-id="725a2-130">Advance to the next tutorial to learn how to run the WCF service.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="725a2-131">チュートリアル: 基本的な WCF サービスをホストして実行する</span><span class="sxs-lookup"><span data-stu-id="725a2-131">Tutorial: Host and run a basic WCF service</span></span>](how-to-host-and-run-a-basic-wcf-service.md)
