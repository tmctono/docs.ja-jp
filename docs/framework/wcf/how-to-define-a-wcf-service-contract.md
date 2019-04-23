---
title: 'チュートリアル: Windows Communication Foundation サービス コントラクトを定義します。'
ms.date: 03/19/2019
helpviewer_keywords:
- service contracts [WCF], defining
dev_langs:
- CSharp
- VB
ms.assetid: 67bf05b7-1d08-4911-83b7-a45d0b036fc3
ms.openlocfilehash: a1908339460191fcb81d03d45c56dd57b2cf4c4e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59228394"
---
# <a name="tutorial-define-a-windows-communication-foundation-service-contract"></a><span data-ttu-id="c7655-102">チュートリアル: Windows Communication Foundation サービス コントラクトを定義します。</span><span class="sxs-lookup"><span data-stu-id="c7655-102">Tutorial: Define a Windows Communication Foundation service contract</span></span>

<span data-ttu-id="c7655-103">このチュートリアルでは、最初の基本的な Windows Communication Foundation (WCF) アプリケーションを作成するために必要な 5 つのタスクについて説明します。</span><span class="sxs-lookup"><span data-stu-id="c7655-103">This tutorial describes the first of five tasks required to create a basic Windows Communication Foundation (WCF) application.</span></span> <span data-ttu-id="c7655-104">チュートリアルの概要については、次を参照してください。[チュートリアル。Windows Communication Foundation アプリケーションの概要](getting-started-tutorial.md)します。</span><span class="sxs-lookup"><span data-stu-id="c7655-104">For an overview of the tutorials, see [Tutorial: Get started with Windows Communication Foundation applications](getting-started-tutorial.md).</span></span>

<span data-ttu-id="c7655-105">WCF サービスを作成するときに、最初のタスクは、サービス コントラクトを定義します。</span><span class="sxs-lookup"><span data-stu-id="c7655-105">When you create a WCF service, your first task is to define a service contract.</span></span> <span data-ttu-id="c7655-106">サービス コントラクトは、サービスがサポートする操作を指定します。</span><span class="sxs-lookup"><span data-stu-id="c7655-106">The service contract specifies what operations the service supports.</span></span> <span data-ttu-id="c7655-107">操作は Web サービス メソッドと見なすことができます。</span><span class="sxs-lookup"><span data-stu-id="c7655-107">An operation can be thought of as a Web service method.</span></span> <span data-ttu-id="c7655-108">ビジュアルを定義してサービス コントラクトを作成するC#または Visual Basic (VB) インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="c7655-108">You create service contracts by defining a Visual C# or Visual Basic (VB) interface.</span></span> <span data-ttu-id="c7655-109">インターフェイスには、次の特徴があります。</span><span class="sxs-lookup"><span data-stu-id="c7655-109">An interface has the following characteristics:</span></span>

- <span data-ttu-id="c7655-110">インターフェイスの各メソッドは、特定のサービス操作に対応しています。</span><span class="sxs-lookup"><span data-stu-id="c7655-110">Each method in the interface corresponds to a specific service operation.</span></span> 
- <span data-ttu-id="c7655-111">インターフェイスごとに適用する必要があります、<xref:System.ServiceModel.ServiceContractAttribute>属性。</span><span class="sxs-lookup"><span data-stu-id="c7655-111">For each interface, you must apply the <xref:System.ServiceModel.ServiceContractAttribute> attribute.</span></span>
- <span data-ttu-id="c7655-112">各操作またはメソッドに適用する必要があります、<xref:System.ServiceModel.OperationContractAttribute>属性。</span><span class="sxs-lookup"><span data-stu-id="c7655-112">For each operation/method, you must apply the <xref:System.ServiceModel.OperationContractAttribute> attribute.</span></span> 

<span data-ttu-id="c7655-113">このチュートリアルでは、次の作業を行う方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c7655-113">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
> - <span data-ttu-id="c7655-114">作成、 **WCF サービス ライブラリ**プロジェクト。</span><span class="sxs-lookup"><span data-stu-id="c7655-114">Create a **WCF Service Library** project.</span></span>
> - <span data-ttu-id="c7655-115">サービス コントラクト インターフェイスを定義します。</span><span class="sxs-lookup"><span data-stu-id="c7655-115">Define a service contract interface.</span></span>

## <a name="create-a-wcf-service-library-project-and-define-a-service-contract-interface"></a><span data-ttu-id="c7655-116">WCF サービス ライブラリ プロジェクトを作成し、サービス コントラクト インターフェイスの定義</span><span class="sxs-lookup"><span data-stu-id="c7655-116">Create a WCF Service Library project and define a service contract interface</span></span>

1. <span data-ttu-id="c7655-117">Visual Studio を管理者として開きます。</span><span class="sxs-lookup"><span data-stu-id="c7655-117">Open Visual Studio as an administrator.</span></span> <span data-ttu-id="c7655-118">これを行うで Visual Studio のプログラムを選択します。、**開始**] メニューの [クリックして**詳細** > **管理者として実行**ショートカット メニューから。</span><span class="sxs-lookup"><span data-stu-id="c7655-118">To do so, select the Visual Studio program in the **Start** menu, and then select **More** > **Run as administrator** from the shortcut menu.</span></span>

2. <span data-ttu-id="c7655-119">作成、 **WCF サービス ライブラリ**プロジェクト。</span><span class="sxs-lookup"><span data-stu-id="c7655-119">Create a **WCF Service Library** project.</span></span>

   1. <span data-ttu-id="c7655-120">**[ファイル]** メニューで、**[新規作成]**、 > **[プロジェクト]** の順に作成します。</span><span class="sxs-lookup"><span data-stu-id="c7655-120">From the **File** menu, select **New** > **Project**.</span></span>

   2. <span data-ttu-id="c7655-121">**新しいプロジェクト**] ダイアログの左側にある [展開**Visual c#** または**Visual Basic**、クリックして、 **WCF**カテゴリ。</span><span class="sxs-lookup"><span data-stu-id="c7655-121">In the **New Project** dialog, on the left-hand side, expand **Visual C#** or **Visual Basic**, and then select the **WCF** category.</span></span> <span data-ttu-id="c7655-122">Visual Studio は、ウィンドウの中央のセクションで、プロジェクト テンプレートの一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="c7655-122">Visual Studio displays a list of project templates in the center section of the window.</span></span> <span data-ttu-id="c7655-123">選択**WCF サービス ライブラリ**します。</span><span class="sxs-lookup"><span data-stu-id="c7655-123">Select **WCF Service Library**.</span></span>

      > [!NOTE]
      > <span data-ttu-id="c7655-124">表示されない場合、 **WCF**プロジェクト テンプレートのカテゴリをインストールする必要があります、 **Windows Communication Foundation** Visual Studio のコンポーネント。</span><span class="sxs-lookup"><span data-stu-id="c7655-124">If you don't see the **WCF** project template category, you may need to install the **Windows Communication Foundation** component of Visual Studio.</span></span> <span data-ttu-id="c7655-125">**新しいプロジェクト**ダイアログ ボックスで、 **Visual Studio インストーラーを開く**左側にあるリンクです。</span><span class="sxs-lookup"><span data-stu-id="c7655-125">In the **New Project** dialog box, select the **Open Visual Studio Installer** link on the left side.</span></span> <span data-ttu-id="c7655-126">選択、**個々 のコンポーネント**] タブの [、し、検索して選択します**Windows Communication Foundation**下、**開発アクティビティ**カテゴリ。</span><span class="sxs-lookup"><span data-stu-id="c7655-126">Select the **Individual components** tab, and then find and select **Windows Communication Foundation** under the **Development activities** category.</span></span> <span data-ttu-id="c7655-127">選択**変更**コンポーネントのインストールを開始します。</span><span class="sxs-lookup"><span data-stu-id="c7655-127">Choose **Modify** to begin installing the component.</span></span>

   3. <span data-ttu-id="c7655-128">ウィンドウの下部のセクションで次のように入力します。 *GettingStartedLib*の、**名前**と*GettingStarted*の、**ソリューション名**します。</span><span class="sxs-lookup"><span data-stu-id="c7655-128">In the bottom section of the window, enter *GettingStartedLib* for the **Name** and *GettingStarted* for the **Solution name**.</span></span> 

   4. <span data-ttu-id="c7655-129">**[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="c7655-129">Select **OK**.</span></span>

      <span data-ttu-id="c7655-130">Visual Studio では、プロジェクトを 3 つのファイルが作成されます。*IService1.cs* (または*IService1.vb* Visual Basic プロジェクトの)、 *Service1.cs* (または*Service1.vb* Visual Basic プロジェクトの)、および*App.config*します。Visual Studio では、次のように、これらのファイルを定義します。</span><span class="sxs-lookup"><span data-stu-id="c7655-130">Visual Studio creates the project, which has three files: *IService1.cs* (or *IService1.vb* for a Visual Basic project), *Service1.cs* (or *Service1.vb* for a Visual Basic project), and *App.config*. Visual Studio defines these files as follows:</span></span> 
      - <span data-ttu-id="c7655-131">*IService1*ファイルには、サービス コントラクトの既定の定義が含まれています。</span><span class="sxs-lookup"><span data-stu-id="c7655-131">The *IService1* file contains the default definition of the service contract.</span></span> 
      - <span data-ttu-id="c7655-132">*Service1*ファイルには、サービス コントラクトの既定の実装が含まれています。</span><span class="sxs-lookup"><span data-stu-id="c7655-132">The *Service1* file contains the default implementation of the service contract.</span></span> 
      - <span data-ttu-id="c7655-133">*App.config*ファイルには、Visual Studio WCF サービス ホスト ツールを使用して既定のサービスを読み込むために必要な構成情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="c7655-133">The *App.config* file contains the configuration info needed to load the default service with the Visual Studio WCF Service Host tool.</span></span> <span data-ttu-id="c7655-134">WCF サービス ホスト ツールの詳細については、次を参照してください。 [WCF サービス ホスト (WcfSvcHost.exe)](wcf-service-host-wcfsvchost-exe.md)します。</span><span class="sxs-lookup"><span data-stu-id="c7655-134">For more information about the WCF Service Host tool, see [WCF Service Host (WcfSvcHost.exe)](wcf-service-host-wcfsvchost-exe.md).</span></span>

      > [!NOTE]
      > <span data-ttu-id="c7655-135">Visual Basic 開発者設定が環境で Visual Studio をインストールした場合、ソリューションを非表示に可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c7655-135">If you installed Visual Studio with Visual Basic developer environment settings, the solution might be hidden.</span></span> <span data-ttu-id="c7655-136">大文字と小文字の場合は、選択**オプション**から、**ツール**メニューを選択し、**プロジェクトおよびソリューション** > **全般**で**オプション**ウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="c7655-136">If this is the case, select **Options** from the **Tools** menu, then select **Projects and Solutions** > **General** in the **Options** window.</span></span> <span data-ttu-id="c7655-137">選択**常にソリューションを表示する**します。</span><span class="sxs-lookup"><span data-stu-id="c7655-137">Select **Always show solution**.</span></span> <span data-ttu-id="c7655-138">また、いることを確認**作成時に新しいプロジェクトを保存**が選択されています。</span><span class="sxs-lookup"><span data-stu-id="c7655-138">Also, verify that **Save new projects when created** is selected.</span></span>

3. <span data-ttu-id="c7655-139">**ソリューション エクスプ ローラー**、オープン、 **IService1.cs**または**IService1.vb**ファイルを開き、そのコードを次のコードに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="c7655-139">From **Solution Explorer**, open the **IService1.cs** or **IService1.vb** file, and replace its code with the following code:</span></span>

    ```csharp
    using System;
    using System.ServiceModel;

    namespace GettingStartedLib
    {
            [ServiceContract(Namespace = "http://Microsoft.ServiceModel.Samples")]
            public interface ICalculator
            {
                [OperationContract]
                double Add(double n1, double n2);
                [OperationContract]
                double Subtract(double n1, double n2);
                [OperationContract]
                double Multiply(double n1, double n2);
                [OperationContract]
                double Divide(double n1, double n2);
            }
    }
    ```

    ```vb
    Imports System.ServiceModel

    Namespace GettingStartedLib

        <ServiceContract(Namespace:="http://Microsoft.ServiceModel.Samples")> _
        Public Interface ICalculator

            <OperationContract()> _
            Function Add(ByVal n1 As Double, ByVal n2 As Double) As Double
            <OperationContract()> _
            Function Subtract(ByVal n1 As Double, ByVal n2 As Double) As Double
            <OperationContract()> _
            Function Multiply(ByVal n1 As Double, ByVal n2 As Double) As Double
            <OperationContract()> _
            Function Divide(ByVal n1 As Double, ByVal n2 As Double) As Double
        End Interface
    End Namespace
    ```

     <span data-ttu-id="c7655-140">このコントラクトは、オンライン電卓を定義します。</span><span class="sxs-lookup"><span data-stu-id="c7655-140">This contract defines an online calculator.</span></span> <span data-ttu-id="c7655-141">通知、`ICalculator`インターフェイスが付いて、<xref:System.ServiceModel.ServiceContractAttribute>属性 (として簡略化された`ServiceContract`)。</span><span class="sxs-lookup"><span data-stu-id="c7655-141">Notice the `ICalculator` interface is marked with the <xref:System.ServiceModel.ServiceContractAttribute> attribute (simplified as `ServiceContract`).</span></span> <span data-ttu-id="c7655-142">この属性は、コントラクト名を明確に区別する名前空間を定義します。</span><span class="sxs-lookup"><span data-stu-id="c7655-142">This attribute defines a namespace to disambiguate the contract name.</span></span> <span data-ttu-id="c7655-143">コードでは、各電卓操作をマークする、<xref:System.ServiceModel.OperationContractAttribute>属性 (として簡略化された`OperationContract`)。</span><span class="sxs-lookup"><span data-stu-id="c7655-143">The code marks each calculator operation with the <xref:System.ServiceModel.OperationContractAttribute> attribute (simplified as `OperationContract`).</span></span>

## <a name="next-steps"></a><span data-ttu-id="c7655-144">次の手順</span><span class="sxs-lookup"><span data-stu-id="c7655-144">Next steps</span></span>

<span data-ttu-id="c7655-145">このチュートリアルでは、次の作業を行う方法を学びました。</span><span class="sxs-lookup"><span data-stu-id="c7655-145">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
> - <span data-ttu-id="c7655-146">WCF サービス ライブラリ プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="c7655-146">Create a WCF Service Library project.</span></span>
> - <span data-ttu-id="c7655-147">サービス コントラクト インターフェイスを定義します。</span><span class="sxs-lookup"><span data-stu-id="c7655-147">Define a service contract interface.</span></span>

<span data-ttu-id="c7655-148">WCF サービス コントラクトを実装する方法については、次のチュートリアルに進んでください。</span><span class="sxs-lookup"><span data-stu-id="c7655-148">Advance to the next tutorial to learn how to implement the WCF service contract.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="c7655-149">チュートリアル: WCF サービス コントラクトを実装します。</span><span class="sxs-lookup"><span data-stu-id="c7655-149">Tutorial: Implement a WCF service contract</span></span>](how-to-implement-a-wcf-contract.md)
