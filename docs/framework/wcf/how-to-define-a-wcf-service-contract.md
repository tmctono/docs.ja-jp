---
title: 'チュートリアル: Windows Communication Foundation サービスコントラクトの定義'
ms.date: 03/19/2019
helpviewer_keywords:
- service contracts [WCF], defining
dev_langs:
- CSharp
- VB
ms.assetid: 67bf05b7-1d08-4911-83b7-a45d0b036fc3
ms.openlocfilehash: 49526808a65b68c6df734bd7f3e76eff1e4a6bc5
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/25/2019
ms.locfileid: "75338292"
---
# <a name="tutorial-define-a-windows-communication-foundation-service-contract"></a><span data-ttu-id="f7e12-102">チュートリアル: Windows Communication Foundation サービスコントラクトの定義</span><span class="sxs-lookup"><span data-stu-id="f7e12-102">Tutorial: Define a Windows Communication Foundation service contract</span></span>

<span data-ttu-id="f7e12-103">このチュートリアルでは、基本的な Windows Communication Foundation (WCF) アプリケーションを作成するために必要な5つのタスクについて説明します。</span><span class="sxs-lookup"><span data-stu-id="f7e12-103">This tutorial describes the first of five tasks required to create a basic Windows Communication Foundation (WCF) application.</span></span> <span data-ttu-id="f7e12-104">チュートリアルの概要については、「[チュートリアル: Windows Communication Foundation アプリケーションの](getting-started-tutorial.md)概要」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f7e12-104">For an overview of the tutorials, see [Tutorial: Get started with Windows Communication Foundation applications](getting-started-tutorial.md).</span></span>

<span data-ttu-id="f7e12-105">WCF サービスを作成する場合、最初のタスクとして、サービスコントラクトを定義します。</span><span class="sxs-lookup"><span data-stu-id="f7e12-105">When you create a WCF service, your first task is to define a service contract.</span></span> <span data-ttu-id="f7e12-106">サービス コントラクトは、サービスがサポートする操作を指定します。</span><span class="sxs-lookup"><span data-stu-id="f7e12-106">The service contract specifies what operations the service supports.</span></span> <span data-ttu-id="f7e12-107">操作は Web サービス メソッドと見なすことができます。</span><span class="sxs-lookup"><span data-stu-id="f7e12-107">An operation can be thought of as a Web service method.</span></span> <span data-ttu-id="f7e12-108">サービスコントラクトを作成するにはC# 、または Visual Basic インターフェイスを定義します。</span><span class="sxs-lookup"><span data-stu-id="f7e12-108">You create service contracts by defining a C# or Visual Basic interface.</span></span> <span data-ttu-id="f7e12-109">インターフェイスには、次の特性があります。</span><span class="sxs-lookup"><span data-stu-id="f7e12-109">An interface has the following characteristics:</span></span>

- <span data-ttu-id="f7e12-110">インターフェイスの各メソッドは、特定のサービス操作に対応しています。</span><span class="sxs-lookup"><span data-stu-id="f7e12-110">Each method in the interface corresponds to a specific service operation.</span></span> 
- <span data-ttu-id="f7e12-111">インターフェイスごとに、<xref:System.ServiceModel.ServiceContractAttribute> 属性を適用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f7e12-111">For each interface, you must apply the <xref:System.ServiceModel.ServiceContractAttribute> attribute.</span></span>
- <span data-ttu-id="f7e12-112">各操作/メソッドに対して、<xref:System.ServiceModel.OperationContractAttribute> 属性を適用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f7e12-112">For each operation/method, you must apply the <xref:System.ServiceModel.OperationContractAttribute> attribute.</span></span> 

<span data-ttu-id="f7e12-113">このチュートリアルでは、次の作業を行う方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="f7e12-113">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="f7e12-114">**WCF サービスライブラリ**プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="f7e12-114">Create a **WCF Service Library** project.</span></span>
> - <span data-ttu-id="f7e12-115">サービスコントラクトインターフェイスを定義します。</span><span class="sxs-lookup"><span data-stu-id="f7e12-115">Define a service contract interface.</span></span>

## <a name="create-a-wcf-service-library-project-and-define-a-service-contract-interface"></a><span data-ttu-id="f7e12-116">WCF サービスライブラリプロジェクトを作成し、サービスコントラクトインターフェイスを定義する</span><span class="sxs-lookup"><span data-stu-id="f7e12-116">Create a WCF Service Library project and define a service contract interface</span></span>

1. <span data-ttu-id="f7e12-117">Visual Studio を管理者として開きます。</span><span class="sxs-lookup"><span data-stu-id="f7e12-117">Open Visual Studio as an administrator.</span></span> <span data-ttu-id="f7e12-118">これを行うには、**スタート** メニューで Visual Studio プログラムを選択し、ショートカットメニューの **その他** > **管理者として実行** を選択します。</span><span class="sxs-lookup"><span data-stu-id="f7e12-118">To do so, select the Visual Studio program in the **Start** menu, and then select **More** > **Run as administrator** from the shortcut menu.</span></span>

2. <span data-ttu-id="f7e12-119">**WCF サービスライブラリ**プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="f7e12-119">Create a **WCF Service Library** project.</span></span>

   1. <span data-ttu-id="f7e12-120">**[ファイル]** メニューで **[新規作成]**  >  **[プロジェクト]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="f7e12-120">From the **File** menu, select **New** > **Project**.</span></span>

   2. <span data-ttu-id="f7e12-121">**[新しいプロジェクト]** ダイアログボックスの左側で、 **[ C#ビジュアル]** または **[Visual Basic]** を展開し、 **[WCF]** カテゴリを選択します。</span><span class="sxs-lookup"><span data-stu-id="f7e12-121">In the **New Project** dialog, on the left-hand side, expand **Visual C#** or **Visual Basic**, and then select the **WCF** category.</span></span> <span data-ttu-id="f7e12-122">Visual Studio によって、ウィンドウの中央のセクションにプロジェクトテンプレートの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f7e12-122">Visual Studio displays a list of project templates in the center section of the window.</span></span> <span data-ttu-id="f7e12-123">**[WCF サービスライブラリ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="f7e12-123">Select **WCF Service Library**.</span></span>

      > [!NOTE]
      > <span data-ttu-id="f7e12-124">[ **WCF**プロジェクトテンプレート] カテゴリが表示されない場合は、Visual Studio の**Windows Communication Foundation**コンポーネントのインストールが必要になることがあります。</span><span class="sxs-lookup"><span data-stu-id="f7e12-124">If you don't see the **WCF** project template category, you may need to install the **Windows Communication Foundation** component of Visual Studio.</span></span> <span data-ttu-id="f7e12-125">**[新しいプロジェクト]** ダイアログボックスで、左側の **[Visual Studio インストーラーを開く]** リンクを選択します。</span><span class="sxs-lookup"><span data-stu-id="f7e12-125">In the **New Project** dialog box, select the **Open Visual Studio Installer** link on the left side.</span></span> <span data-ttu-id="f7e12-126">**[個々のコンポーネント]** タブを選択し、 **[開発アクティビティ]** カテゴリの下の **[Windows Communication Foundation]** を見つけて選択します。</span><span class="sxs-lookup"><span data-stu-id="f7e12-126">Select the **Individual components** tab, and then find and select **Windows Communication Foundation** under the **Development activities** category.</span></span> <span data-ttu-id="f7e12-127">**[変更]** を選択して、コンポーネントのインストールを開始します。</span><span class="sxs-lookup"><span data-stu-id="f7e12-127">Choose **Modify** to begin installing the component.</span></span>

   3. <span data-ttu-id="f7e12-128">ウィンドウの下部にある **[名前]** に「 *Getting、lib* 」と入力し、**ソリューション名**に「 *getting始め*」と入力します。</span><span class="sxs-lookup"><span data-stu-id="f7e12-128">In the bottom section of the window, enter *GettingStartedLib* for the **Name** and *GettingStarted* for the **Solution name**.</span></span> 

   4. <span data-ttu-id="f7e12-129">**[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="f7e12-129">Select **OK**.</span></span>

      <span data-ttu-id="f7e12-130">Visual Studio によってプロジェクトが作成されます。このプロジェクトには、 *IService1.cs* (または、Visual Basic プロジェクトの場合は IService1)、 *Service1.cs* (またはプロジェクトの Visual Basic 場合は*Service1* )、 *app.config*という3つのファイルがあります。Visual Studio では、これらのファイルを次のように定義します。</span><span class="sxs-lookup"><span data-stu-id="f7e12-130">Visual Studio creates the project, which has three files: *IService1.cs* (or *IService1.vb* for a Visual Basic project), *Service1.cs* (or *Service1.vb* for a Visual Basic project), and *App.config*. Visual Studio defines these files as follows:</span></span> 
      - <span data-ttu-id="f7e12-131">*IService1*ファイルには、サービスコントラクトの既定の定義が含まれています。</span><span class="sxs-lookup"><span data-stu-id="f7e12-131">The *IService1* file contains the default definition of the service contract.</span></span> 
      - <span data-ttu-id="f7e12-132">*Service1*ファイルには、サービスコントラクトの既定の実装が含まれています。</span><span class="sxs-lookup"><span data-stu-id="f7e12-132">The *Service1* file contains the default implementation of the service contract.</span></span> 
      - <span data-ttu-id="f7e12-133">*App.config*ファイルには、VISUAL Studio WCF サービスホストツールを使用して既定のサービスを読み込むために必要な構成情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="f7e12-133">The *App.config* file contains the configuration info needed to load the default service with the Visual Studio WCF Service Host tool.</span></span> <span data-ttu-id="f7e12-134">WCF サービスホストツールの詳細については、「 [Wcf サービスホスト (wcfsvchost.exe)](wcf-service-host-wcfsvchost-exe.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f7e12-134">For more information about the WCF Service Host tool, see [WCF Service Host (WcfSvcHost.exe)](wcf-service-host-wcfsvchost-exe.md).</span></span>

      > [!NOTE]
      > <span data-ttu-id="f7e12-135">Visual Basic 開発者向け環境設定を使用して Visual Studio をインストールした場合は、ソリューションが非表示になることがあります。</span><span class="sxs-lookup"><span data-stu-id="f7e12-135">If you installed Visual Studio with Visual Basic developer environment settings, the solution might be hidden.</span></span> <span data-ttu-id="f7e12-136">この場合は、 **[ツール]** メニューの **[オプション]** を選択し、 **[オプション]** ウィンドウで [**プロジェクトおよびソリューション** > **全般**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f7e12-136">If this is the case, select **Options** from the **Tools** menu, then select **Projects and Solutions** > **General** in the **Options** window.</span></span> <span data-ttu-id="f7e12-137">**[常にソリューションを表示]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="f7e12-137">Select **Always show solution**.</span></span> <span data-ttu-id="f7e12-138">また、[**作成時に新しいプロジェクトを保存**する] が選択されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="f7e12-138">Also, verify that **Save new projects when created** is selected.</span></span>

3. <span data-ttu-id="f7e12-139">**ソリューションエクスプローラー**から、 **IService1.cs**または**IService1**ファイルを開き、そのコードを次のコードに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="f7e12-139">From **Solution Explorer**, open the **IService1.cs** or **IService1.vb** file, and replace its code with the following code:</span></span>

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

     <span data-ttu-id="f7e12-140">このコントラクトは、オンライン電卓を定義します。</span><span class="sxs-lookup"><span data-stu-id="f7e12-140">This contract defines an online calculator.</span></span> <span data-ttu-id="f7e12-141">`ICalculator` インターフェイスが <xref:System.ServiceModel.ServiceContractAttribute> 属性でマークされていることに注意してください (`ServiceContract`として簡略化されています)。</span><span class="sxs-lookup"><span data-stu-id="f7e12-141">Notice the `ICalculator` interface is marked with the <xref:System.ServiceModel.ServiceContractAttribute> attribute (simplified as `ServiceContract`).</span></span> <span data-ttu-id="f7e12-142">この属性は、コントラクト名を明確に区別する名前空間を定義します。</span><span class="sxs-lookup"><span data-stu-id="f7e12-142">This attribute defines a namespace to disambiguate the contract name.</span></span> <span data-ttu-id="f7e12-143">このコードは、各電卓操作に <xref:System.ServiceModel.OperationContractAttribute> 属性 (`OperationContract`として簡略化) をマークします。</span><span class="sxs-lookup"><span data-stu-id="f7e12-143">The code marks each calculator operation with the <xref:System.ServiceModel.OperationContractAttribute> attribute (simplified as `OperationContract`).</span></span>

## <a name="next-steps"></a><span data-ttu-id="f7e12-144">次のステップ:</span><span class="sxs-lookup"><span data-stu-id="f7e12-144">Next steps</span></span>

<span data-ttu-id="f7e12-145">このチュートリアルでは、次の作業を行う方法を学びました。</span><span class="sxs-lookup"><span data-stu-id="f7e12-145">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="f7e12-146">WCF サービスライブラリプロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="f7e12-146">Create a WCF Service Library project.</span></span>
> - <span data-ttu-id="f7e12-147">サービスコントラクトインターフェイスを定義します。</span><span class="sxs-lookup"><span data-stu-id="f7e12-147">Define a service contract interface.</span></span>

<span data-ttu-id="f7e12-148">次のチュートリアルに進み、WCF サービスコントラクトを実装する方法を学習してください。</span><span class="sxs-lookup"><span data-stu-id="f7e12-148">Advance to the next tutorial to learn how to implement the WCF service contract.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="f7e12-149">チュートリアル: WCF サービスコントラクトの実装</span><span class="sxs-lookup"><span data-stu-id="f7e12-149">Tutorial: Implement a WCF service contract</span></span>](how-to-implement-a-wcf-contract.md)
