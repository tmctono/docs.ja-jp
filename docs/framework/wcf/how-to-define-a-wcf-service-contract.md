---
title: 'チュートリアル: Windows Communication Foundation サービスコントラクトの定義'
description: WCF アプリケーションの作成を開始する際に役立つ一連の記事の一部として、サービスコントラクトを定義する方法について説明します。
ms.date: 03/19/2019
helpviewer_keywords:
- service contracts [WCF], defining
dev_langs:
- CSharp
- VB
ms.assetid: 67bf05b7-1d08-4911-83b7-a45d0b036fc3
ms.openlocfilehash: 5cb371da8c7180b8c4cbf5ac11468fbb8e0e13cc
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/23/2020
ms.locfileid: "85246312"
---
# <a name="tutorial-define-a-windows-communication-foundation-service-contract"></a><span data-ttu-id="0a621-103">チュートリアル: Windows Communication Foundation サービスコントラクトの定義</span><span class="sxs-lookup"><span data-stu-id="0a621-103">Tutorial: Define a Windows Communication Foundation service contract</span></span>

<span data-ttu-id="0a621-104">このチュートリアルでは、基本的な Windows Communication Foundation (WCF) アプリケーションを作成するために必要な5つのタスクについて説明します。</span><span class="sxs-lookup"><span data-stu-id="0a621-104">This tutorial describes the first of five tasks required to create a basic Windows Communication Foundation (WCF) application.</span></span> <span data-ttu-id="0a621-105">チュートリアルの概要については、「[チュートリアル: Windows Communication Foundation アプリケーションの](getting-started-tutorial.md)概要」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0a621-105">For an overview of the tutorials, see [Tutorial: Get started with Windows Communication Foundation applications](getting-started-tutorial.md).</span></span>

<span data-ttu-id="0a621-106">WCF サービスを作成する場合、最初のタスクとして、サービスコントラクトを定義します。</span><span class="sxs-lookup"><span data-stu-id="0a621-106">When you create a WCF service, your first task is to define a service contract.</span></span> <span data-ttu-id="0a621-107">サービス コントラクトでは、サービスがサポートする操作を指定します。</span><span class="sxs-lookup"><span data-stu-id="0a621-107">The service contract specifies what operations the service supports.</span></span> <span data-ttu-id="0a621-108">操作は Web サービス メソッドと見なすことができます。</span><span class="sxs-lookup"><span data-stu-id="0a621-108">An operation can be thought of as a Web service method.</span></span> <span data-ttu-id="0a621-109">サービスコントラクトを作成するには、C# または Visual Basic インターフェイスを定義します。</span><span class="sxs-lookup"><span data-stu-id="0a621-109">You create service contracts by defining a C# or Visual Basic interface.</span></span> <span data-ttu-id="0a621-110">インターフェイスには、次の特性があります。</span><span class="sxs-lookup"><span data-stu-id="0a621-110">An interface has the following characteristics:</span></span>

- <span data-ttu-id="0a621-111">インターフェイスの各メソッドは、特定のサービス操作に対応しています。</span><span class="sxs-lookup"><span data-stu-id="0a621-111">Each method in the interface corresponds to a specific service operation.</span></span>
- <span data-ttu-id="0a621-112">インターフェイスごとに、属性を適用する必要があり <xref:System.ServiceModel.ServiceContractAttribute> ます。</span><span class="sxs-lookup"><span data-stu-id="0a621-112">For each interface, you must apply the <xref:System.ServiceModel.ServiceContractAttribute> attribute.</span></span>
- <span data-ttu-id="0a621-113">各操作/メソッドに対して、属性を適用する必要があり <xref:System.ServiceModel.OperationContractAttribute> ます。</span><span class="sxs-lookup"><span data-stu-id="0a621-113">For each operation/method, you must apply the <xref:System.ServiceModel.OperationContractAttribute> attribute.</span></span>

<span data-ttu-id="0a621-114">このチュートリアルでは、次の作業を行う方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="0a621-114">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="0a621-115">**WCF サービスライブラリ**プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="0a621-115">Create a **WCF Service Library** project.</span></span>
> - <span data-ttu-id="0a621-116">サービスコントラクトインターフェイスを定義します。</span><span class="sxs-lookup"><span data-stu-id="0a621-116">Define a service contract interface.</span></span>

## <a name="create-a-wcf-service-library-project-and-define-a-service-contract-interface"></a><span data-ttu-id="0a621-117">WCF サービスライブラリプロジェクトを作成し、サービスコントラクトインターフェイスを定義する</span><span class="sxs-lookup"><span data-stu-id="0a621-117">Create a WCF Service Library project and define a service contract interface</span></span>

1. <span data-ttu-id="0a621-118">Visual Studio を管理者として開きます。</span><span class="sxs-lookup"><span data-stu-id="0a621-118">Open Visual Studio as an administrator.</span></span> <span data-ttu-id="0a621-119">これを行うには、[**スタート**] メニューで Visual Studio プログラムを選択し、ショートカットメニューの [ **More**  >  **管理者として実行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0a621-119">To do so, select the Visual Studio program in the **Start** menu, and then select **More** > **Run as administrator** from the shortcut menu.</span></span>

2. <span data-ttu-id="0a621-120">**WCF サービスライブラリ**プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="0a621-120">Create a **WCF Service Library** project.</span></span>

   1. <span data-ttu-id="0a621-121">**[ファイル]** メニューで **[新規作成]**  >  **[プロジェクト]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="0a621-121">From the **File** menu, select **New** > **Project**.</span></span>

   2. <span data-ttu-id="0a621-122">[**新しいプロジェクト**] ダイアログの左側にある [ **Visual C#** ] または [ **Visual Basic**] を展開し、[ **WCF** ] カテゴリを選択します。</span><span class="sxs-lookup"><span data-stu-id="0a621-122">In the **New Project** dialog, on the left-hand side, expand **Visual C#** or **Visual Basic**, and then select the **WCF** category.</span></span> <span data-ttu-id="0a621-123">Visual Studio によって、ウィンドウの中央のセクションにプロジェクトテンプレートの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="0a621-123">Visual Studio displays a list of project templates in the center section of the window.</span></span> <span data-ttu-id="0a621-124">[ **WCF サービスライブラリ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="0a621-124">Select **WCF Service Library**.</span></span>

      > [!NOTE]
      > <span data-ttu-id="0a621-125">[ **WCF**プロジェクトテンプレート] カテゴリが表示されない場合は、Visual Studio の**Windows Communication Foundation**コンポーネントのインストールが必要になることがあります。</span><span class="sxs-lookup"><span data-stu-id="0a621-125">If you don't see the **WCF** project template category, you may need to install the **Windows Communication Foundation** component of Visual Studio.</span></span> <span data-ttu-id="0a621-126">[**新しいプロジェクト**] ダイアログボックスで、左側の [ **Visual Studio インストーラーを開く**] リンクを選択します。</span><span class="sxs-lookup"><span data-stu-id="0a621-126">In the **New Project** dialog box, select the **Open Visual Studio Installer** link on the left side.</span></span> <span data-ttu-id="0a621-127">[**個々のコンポーネント**] タブを選択し、[**開発アクティビティ**] カテゴリの下の [ **Windows Communication Foundation** ] を見つけて選択します。</span><span class="sxs-lookup"><span data-stu-id="0a621-127">Select the **Individual components** tab, and then find and select **Windows Communication Foundation** under the **Development activities** category.</span></span> <span data-ttu-id="0a621-128">[**変更**] を選択して、コンポーネントのインストールを開始します。</span><span class="sxs-lookup"><span data-stu-id="0a621-128">Choose **Modify** to begin installing the component.</span></span>

   3. <span data-ttu-id="0a621-129">ウィンドウの下部にある [**名前**] に「 *Getting、lib* 」と入力し、**ソリューション名**に「 *getting始め*」と入力します。</span><span class="sxs-lookup"><span data-stu-id="0a621-129">In the bottom section of the window, enter *GettingStartedLib* for the **Name** and *GettingStarted* for the **Solution name**.</span></span>

   4. <span data-ttu-id="0a621-130">**[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="0a621-130">Select **OK**.</span></span>

      <span data-ttu-id="0a621-131">Visual Studio によってプロジェクトが作成されます。このプロジェクトには、 *IService1.cs* (または、Visual Basic プロジェクトの場合は*IService1* ) という3つのファイル、 *Service1.cs* (Visual Basic プロジェクトの場合は*Service1* )、および*App.config*があります。Visual Studio では、これらのファイルを次のように定義します。</span><span class="sxs-lookup"><span data-stu-id="0a621-131">Visual Studio creates the project, which has three files: *IService1.cs* (or *IService1.vb* for a Visual Basic project), *Service1.cs* (or *Service1.vb* for a Visual Basic project), and *App.config*. Visual Studio defines these files as follows:</span></span>
      - <span data-ttu-id="0a621-132">*IService1*ファイルには、サービスコントラクトの既定の定義が含まれています。</span><span class="sxs-lookup"><span data-stu-id="0a621-132">The *IService1* file contains the default definition of the service contract.</span></span>
      - <span data-ttu-id="0a621-133">*Service1*ファイルには、サービスコントラクトの既定の実装が含まれています。</span><span class="sxs-lookup"><span data-stu-id="0a621-133">The *Service1* file contains the default implementation of the service contract.</span></span>
      - <span data-ttu-id="0a621-134">*App.config*ファイルには、VISUAL Studio WCF サービスホストツールを使用して既定のサービスを読み込むために必要な構成情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="0a621-134">The *App.config* file contains the configuration info needed to load the default service with the Visual Studio WCF Service Host tool.</span></span> <span data-ttu-id="0a621-135">WCF サービスホストツールの詳細については、「 [Wcf サービスホスト (WcfSvcHost.exe)](wcf-service-host-wcfsvchost-exe.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0a621-135">For more information about the WCF Service Host tool, see [WCF Service Host (WcfSvcHost.exe)](wcf-service-host-wcfsvchost-exe.md).</span></span>

      > [!NOTE]
      > <span data-ttu-id="0a621-136">Visual Basic 開発者向け環境設定を使用して Visual Studio をインストールした場合は、ソリューションが非表示になることがあります。</span><span class="sxs-lookup"><span data-stu-id="0a621-136">If you installed Visual Studio with Visual Basic developer environment settings, the solution might be hidden.</span></span> <span data-ttu-id="0a621-137">この場合は、[**ツール**] メニューの [**オプション**] を選択し、[オプション] ウィンドウで [**プロジェクトおよびソリューション**] [全般] を選択し  >  **General** **Options**ます。</span><span class="sxs-lookup"><span data-stu-id="0a621-137">If this is the case, select **Options** from the **Tools** menu, then select **Projects and Solutions** > **General** in the **Options** window.</span></span> <span data-ttu-id="0a621-138">[**常にソリューションを表示**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="0a621-138">Select **Always show solution**.</span></span> <span data-ttu-id="0a621-139">また、[**作成時に新しいプロジェクトを保存**する] が選択されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="0a621-139">Also, verify that **Save new projects when created** is selected.</span></span>

3. <span data-ttu-id="0a621-140">**ソリューションエクスプローラー**から、 **IService1.cs**または**IService1**ファイルを開き、そのコードを次のコードに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="0a621-140">From **Solution Explorer**, open the **IService1.cs** or **IService1.vb** file, and replace its code with the following code:</span></span>

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

     <span data-ttu-id="0a621-141">このコントラクトは、オンライン電卓を定義します。</span><span class="sxs-lookup"><span data-stu-id="0a621-141">This contract defines an online calculator.</span></span> <span data-ttu-id="0a621-142">`ICalculator`インターフェイスが属性でマークされていることに注意し <xref:System.ServiceModel.ServiceContractAttribute> てください (簡略化されて `ServiceContract` います)。</span><span class="sxs-lookup"><span data-stu-id="0a621-142">Notice the `ICalculator` interface is marked with the <xref:System.ServiceModel.ServiceContractAttribute> attribute (simplified as `ServiceContract`).</span></span> <span data-ttu-id="0a621-143">この属性は、コントラクト名を明確に区別する名前空間を定義します。</span><span class="sxs-lookup"><span data-stu-id="0a621-143">This attribute defines a namespace to disambiguate the contract name.</span></span> <span data-ttu-id="0a621-144">このコードでは、各電卓操作を属性でマークし <xref:System.ServiceModel.OperationContractAttribute> ています (簡略化されて `OperationContract` います)。</span><span class="sxs-lookup"><span data-stu-id="0a621-144">The code marks each calculator operation with the <xref:System.ServiceModel.OperationContractAttribute> attribute (simplified as `OperationContract`).</span></span>

## <a name="next-steps"></a><span data-ttu-id="0a621-145">次の手順</span><span class="sxs-lookup"><span data-stu-id="0a621-145">Next steps</span></span>

<span data-ttu-id="0a621-146">このチュートリアルでは、以下の内容を学習しました。</span><span class="sxs-lookup"><span data-stu-id="0a621-146">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="0a621-147">WCF サービスライブラリプロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="0a621-147">Create a WCF Service Library project.</span></span>
> - <span data-ttu-id="0a621-148">サービスコントラクトインターフェイスを定義します。</span><span class="sxs-lookup"><span data-stu-id="0a621-148">Define a service contract interface.</span></span>

<span data-ttu-id="0a621-149">次のチュートリアルに進み、WCF サービスコントラクトを実装する方法を学習してください。</span><span class="sxs-lookup"><span data-stu-id="0a621-149">Advance to the next tutorial to learn how to implement the WCF service contract.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="0a621-150">チュートリアル: WCF サービスコントラクトの実装</span><span class="sxs-lookup"><span data-stu-id="0a621-150">Tutorial: Implement a WCF service contract</span></span>](how-to-implement-a-wcf-contract.md)
