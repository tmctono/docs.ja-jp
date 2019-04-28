---
title: 'チュートリアル: Windows Communication Foundation サービス コントラクトを実装します。'
ms.date: 03/19/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- service contracts [WCF], implementing
ms.assetid: d5ab51ba-61ae-403e-b3c8-e2669e326806
ms.openlocfilehash: fa8c5457c636d7f37215f0d4b4fdbb1c96c9481e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61929054"
---
# <a name="tutorial-implement-a-windows-communication-foundation-service-contract"></a><span data-ttu-id="e6690-102">チュートリアル: Windows Communication Foundation サービス コントラクトを実装します。</span><span class="sxs-lookup"><span data-stu-id="e6690-102">Tutorial: Implement a Windows Communication Foundation service contract</span></span>

<span data-ttu-id="e6690-103">このチュートリアルでは、2 番目の基本的な Windows Communication Foundation (WCF) アプリケーションを作成するために必要な 5 つのタスクについて説明します。</span><span class="sxs-lookup"><span data-stu-id="e6690-103">This tutorial describes the second of five tasks required to create a basic Windows Communication Foundation (WCF) application.</span></span> <span data-ttu-id="e6690-104">チュートリアルの概要については、次を参照してください。[チュートリアル。Windows Communication Foundation アプリケーションの概要](getting-started-tutorial.md)します。</span><span class="sxs-lookup"><span data-stu-id="e6690-104">For an overview of the tutorials, see [Tutorial: Get started with Windows Communication Foundation applications](getting-started-tutorial.md).</span></span>

<span data-ttu-id="e6690-105">WCF アプリケーションを作成する場合は、次の手順では、前の手順で作成した WCF サービスのインターフェイスを実装するコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="e6690-105">The next step for creating a WCF application is to add code to implement the WCF service interface that you created in the previous step.</span></span> <span data-ttu-id="e6690-106">この手順でという名前のクラスを作成する`CalculatorService`ユーザー定義を実装する`ICalculator`インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="e6690-106">In this step, you create a class named `CalculatorService` that implements the user-defined `ICalculator` interface.</span></span> <span data-ttu-id="e6690-107">次のコード内の各メソッドでは、電卓操作を呼び出すし、テスト コンソールにテキストを書き込みます。</span><span class="sxs-lookup"><span data-stu-id="e6690-107">Each method in the following code calls a calculator operation and writes text to the console to test it.</span></span> 

<span data-ttu-id="e6690-108">このチュートリアルでは、次の作業を行う方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="e6690-108">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
> - <span data-ttu-id="e6690-109">WCF サービス コントラクトを実装するコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="e6690-109">Add code to implement the WCF service contract.</span></span>
> - <span data-ttu-id="e6690-110">ソリューションをビルドします。</span><span class="sxs-lookup"><span data-stu-id="e6690-110">Build the solution.</span></span>

## <a name="add-code-to-implement-the-wcf-service-contract"></a><span data-ttu-id="e6690-111">WCF サービス コントラクトを実装するコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="e6690-111">Add code to implement the WCF service contract</span></span>

<span data-ttu-id="e6690-112">**GettingStartedLib**、オープン、 **Service1.cs**または**Service1.vb**ファイルし、そのコードを次のコードに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="e6690-112">In **GettingStartedLib**, open the **Service1.cs** or **Service1.vb** file and replace its code with the following code:</span></span>

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

## <a name="edit-appconfig"></a><span data-ttu-id="e6690-113">App.config を編集します。</span><span class="sxs-lookup"><span data-stu-id="e6690-113">Edit App.config</span></span>

<span data-ttu-id="e6690-114">編集**App.config**で**GettingStartedLib**コードに加えた変更を反映します。</span><span class="sxs-lookup"><span data-stu-id="e6690-114">Edit **App.config** in **GettingStartedLib** to reflect the changes you made to the code.</span></span>
- <span data-ttu-id="e6690-115">ビジュアルのC#プロジェクト。</span><span class="sxs-lookup"><span data-stu-id="e6690-115">For Visual C# projects:</span></span>
  - <span data-ttu-id="e6690-116">14 行を変更します。 `<service name="GettingStartedLib.CalculatorService">`</span><span class="sxs-lookup"><span data-stu-id="e6690-116">Change line 14 to `<service name="GettingStartedLib.CalculatorService">`</span></span>
  - <span data-ttu-id="e6690-117">行 17 を変更します。 `<add baseAddress = "http://localhost:8000/GettingStarted/CalculatorService" />`</span><span class="sxs-lookup"><span data-stu-id="e6690-117">Change line 17 to `<add baseAddress = "http://localhost:8000/GettingStarted/CalculatorService" />`</span></span>
  - <span data-ttu-id="e6690-118">変更するには、22 行目 `<endpoint address="" binding="wsHttpBinding" contract="GettingStartedLib.ICalculator">`</span><span class="sxs-lookup"><span data-stu-id="e6690-118">Change line 22 to `<endpoint address="" binding="wsHttpBinding" contract="GettingStartedLib.ICalculator">`</span></span>

- <span data-ttu-id="e6690-119">Visual Basic プロジェクトの場合は、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="e6690-119">For Visual Basic projects:</span></span>
  - <span data-ttu-id="e6690-120">14 行を変更します。 `<service name="GettingStartedLib.GettingStartedLib.CalculatorService">`</span><span class="sxs-lookup"><span data-stu-id="e6690-120">Change line 14 to `<service name="GettingStartedLib.GettingStartedLib.CalculatorService">`</span></span>
  - <span data-ttu-id="e6690-121">行 17 を変更します。 `<add baseAddress = "http://localhost:8000/GettingStarted/CalculatorService" />`</span><span class="sxs-lookup"><span data-stu-id="e6690-121">Change line 17 to `<add baseAddress = "http://localhost:8000/GettingStarted/CalculatorService" />`</span></span>
  - <span data-ttu-id="e6690-122">変更するには、22 行目 `<endpoint address="" binding="wsHttpBinding" contract="GettingStartedLib.GettingStartedLib.ICalculator">`</span><span class="sxs-lookup"><span data-stu-id="e6690-122">Change line 22 to `<endpoint address="" binding="wsHttpBinding" contract="GettingStartedLib.GettingStartedLib.ICalculator">`</span></span>

## <a name="compile-the-code"></a><span data-ttu-id="e6690-123">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="e6690-123">Compile the code</span></span>

<span data-ttu-id="e6690-124">コンパイル エラーがないことを確認するソリューションをビルドします。</span><span class="sxs-lookup"><span data-stu-id="e6690-124">Build the solution to verify there aren't any compilation errors.</span></span> <span data-ttu-id="e6690-125">Visual Studio を使用している場合、**ビルド**メニューの **ソリューションのビルド**(またはキーを押します**Ctrl**+**Shift** + **B**)。</span><span class="sxs-lookup"><span data-stu-id="e6690-125">If you're using Visual Studio, on the **Build** menu select **Build Solution** (or press **Ctrl**+**Shift**+**B**).</span></span>

## <a name="next-steps"></a><span data-ttu-id="e6690-126">次の手順</span><span class="sxs-lookup"><span data-stu-id="e6690-126">Next steps</span></span>

<span data-ttu-id="e6690-127">このチュートリアルでは、次の作業を行う方法を学びました。</span><span class="sxs-lookup"><span data-stu-id="e6690-127">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
> - <span data-ttu-id="e6690-128">WCF サービス コントラクトを実装するコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="e6690-128">Add code to implement the WCF service contract.</span></span>
> - <span data-ttu-id="e6690-129">ソリューションをビルドします。</span><span class="sxs-lookup"><span data-stu-id="e6690-129">Build the solution.</span></span>

<span data-ttu-id="e6690-130">WCF サービスを実行する方法については、次のチュートリアルに進んでください。</span><span class="sxs-lookup"><span data-stu-id="e6690-130">Advance to the next tutorial to learn how to run the WCF service.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="e6690-131">チュートリアル: ホストおよび基本的な WCF サービスの実行</span><span class="sxs-lookup"><span data-stu-id="e6690-131">Tutorial: Host and run a basic WCF service</span></span>](how-to-host-and-run-a-basic-wcf-service.md)
