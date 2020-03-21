---
title: 'チュートリアル: Windows 通信基盤サービス コントラクトの定義'
ms.date: 03/19/2019
helpviewer_keywords:
- service contracts [WCF], defining
dev_langs:
- CSharp
- VB
ms.assetid: 67bf05b7-1d08-4911-83b7-a45d0b036fc3
ms.openlocfilehash: 7c1c42c4f22a1a9627c147440e8e198551470b7b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184090"
---
# <a name="tutorial-define-a-windows-communication-foundation-service-contract"></a><span data-ttu-id="7e1e3-102">チュートリアル: Windows 通信基盤サービス コントラクトの定義</span><span class="sxs-lookup"><span data-stu-id="7e1e3-102">Tutorial: Define a Windows Communication Foundation service contract</span></span>

<span data-ttu-id="7e1e3-103">このチュートリアルでは、基本的な Wcf (WCF) アプリケーションを作成するために必要な 5 つのタスクの最初の作業について説明します。</span><span class="sxs-lookup"><span data-stu-id="7e1e3-103">This tutorial describes the first of five tasks required to create a basic Windows Communication Foundation (WCF) application.</span></span> <span data-ttu-id="7e1e3-104">チュートリアルの概要については、「[チュートリアル: Windows コミュニケーションファウンデーション アプリケーションの概要](getting-started-tutorial.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7e1e3-104">For an overview of the tutorials, see [Tutorial: Get started with Windows Communication Foundation applications](getting-started-tutorial.md).</span></span>

<span data-ttu-id="7e1e3-105">WCF サービスを作成する場合、最初のタスクはサービス コントラクトを定義することです。</span><span class="sxs-lookup"><span data-stu-id="7e1e3-105">When you create a WCF service, your first task is to define a service contract.</span></span> <span data-ttu-id="7e1e3-106">サービス コントラクトでは、サービスがサポートする操作を指定します。</span><span class="sxs-lookup"><span data-stu-id="7e1e3-106">The service contract specifies what operations the service supports.</span></span> <span data-ttu-id="7e1e3-107">操作は Web サービス メソッドと見なすことができます。</span><span class="sxs-lookup"><span data-stu-id="7e1e3-107">An operation can be thought of as a Web service method.</span></span> <span data-ttu-id="7e1e3-108">サービス コントラクトを作成するには、C# または Visual Basic インターフェイスを定義します。</span><span class="sxs-lookup"><span data-stu-id="7e1e3-108">You create service contracts by defining a C# or Visual Basic interface.</span></span> <span data-ttu-id="7e1e3-109">インターフェイスには、次の特性があります。</span><span class="sxs-lookup"><span data-stu-id="7e1e3-109">An interface has the following characteristics:</span></span>

- <span data-ttu-id="7e1e3-110">インターフェイスの各メソッドは、特定のサービス操作に対応しています。</span><span class="sxs-lookup"><span data-stu-id="7e1e3-110">Each method in the interface corresponds to a specific service operation.</span></span>
- <span data-ttu-id="7e1e3-111">各インターフェイスに対して、属性を<xref:System.ServiceModel.ServiceContractAttribute>適用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7e1e3-111">For each interface, you must apply the <xref:System.ServiceModel.ServiceContractAttribute> attribute.</span></span>
- <span data-ttu-id="7e1e3-112">各操作/メソッドに対して、属性を<xref:System.ServiceModel.OperationContractAttribute>適用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7e1e3-112">For each operation/method, you must apply the <xref:System.ServiceModel.OperationContractAttribute> attribute.</span></span>

<span data-ttu-id="7e1e3-113">このチュートリアルでは、以下の内容を学習します。</span><span class="sxs-lookup"><span data-stu-id="7e1e3-113">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="7e1e3-114">WCF**サービス ライブラリ**プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="7e1e3-114">Create a **WCF Service Library** project.</span></span>
> - <span data-ttu-id="7e1e3-115">サービス コントラクト インターフェイスを定義します。</span><span class="sxs-lookup"><span data-stu-id="7e1e3-115">Define a service contract interface.</span></span>

## <a name="create-a-wcf-service-library-project-and-define-a-service-contract-interface"></a><span data-ttu-id="7e1e3-116">WCF サービス ライブラリ プロジェクトを作成し、サービス コントラクト インターフェイスを定義します。</span><span class="sxs-lookup"><span data-stu-id="7e1e3-116">Create a WCF Service Library project and define a service contract interface</span></span>

1. <span data-ttu-id="7e1e3-117">Visual Studio を管理者として開きます。</span><span class="sxs-lookup"><span data-stu-id="7e1e3-117">Open Visual Studio as an administrator.</span></span> <span data-ttu-id="7e1e3-118">これを行うには、[**スタート]** メニューで Visual Studio プログラムを選択し、ショートカット メニューから **[管理者としてその他** > の**実行**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="7e1e3-118">To do so, select the Visual Studio program in the **Start** menu, and then select **More** > **Run as administrator** from the shortcut menu.</span></span>

2. <span data-ttu-id="7e1e3-119">WCF**サービス ライブラリ**プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="7e1e3-119">Create a **WCF Service Library** project.</span></span>

   1. <span data-ttu-id="7e1e3-120">**[ファイル]** メニューから、**[新規]** > **[プロジェクト]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="7e1e3-120">From the **File** menu, select **New** > **Project**.</span></span>

   2. <span data-ttu-id="7e1e3-121">[**新しいプロジェクト**] ダイアログ ボックスの左側で **、[Visual C#]** または **[Visual Basic]** を展開し **、[WCF]** カテゴリを選択します。</span><span class="sxs-lookup"><span data-stu-id="7e1e3-121">In the **New Project** dialog, on the left-hand side, expand **Visual C#** or **Visual Basic**, and then select the **WCF** category.</span></span> <span data-ttu-id="7e1e3-122">プロジェクト テンプレートの一覧がウィンドウの中央セクションに表示されます。</span><span class="sxs-lookup"><span data-stu-id="7e1e3-122">Visual Studio displays a list of project templates in the center section of the window.</span></span> <span data-ttu-id="7e1e3-123">[WCF**サービス ライブラリ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="7e1e3-123">Select **WCF Service Library**.</span></span>

      > [!NOTE]
      > <span data-ttu-id="7e1e3-124">**WCF**プロジェクト テンプレート カテゴリが表示されない場合は、Visual Studio の**Windows コミュニケーション基礎**コンポーネントをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="7e1e3-124">If you don't see the **WCF** project template category, you may need to install the **Windows Communication Foundation** component of Visual Studio.</span></span> <span data-ttu-id="7e1e3-125">[**新しいプロジェクト**] ダイアログ ボックスで、左側にある **[Visual Studio インストーラーを開く**] リンクを選択します。</span><span class="sxs-lookup"><span data-stu-id="7e1e3-125">In the **New Project** dialog box, select the **Open Visual Studio Installer** link on the left side.</span></span> <span data-ttu-id="7e1e3-126">[**個々のコンポーネント**] タブを選択し、[**開発活動**] カテゴリの下にある **[Windows コミュニケーション 基盤**] を検索して選択します。</span><span class="sxs-lookup"><span data-stu-id="7e1e3-126">Select the **Individual components** tab, and then find and select **Windows Communication Foundation** under the **Development activities** category.</span></span> <span data-ttu-id="7e1e3-127">[**変更]** を選択して、コンポーネントのインストールを開始します。</span><span class="sxs-lookup"><span data-stu-id="7e1e3-127">Choose **Modify** to begin installing the component.</span></span>

   3. <span data-ttu-id="7e1e3-128">ウィンドウの下部に、「**名前\*\*\*」に「はじめに開始」* と入力し、\*\*ソリューション名\*\*\*に「はじめに*」と入力します。</span><span class="sxs-lookup"><span data-stu-id="7e1e3-128">In the bottom section of the window, enter *GettingStartedLib* for the **Name** and *GettingStarted* for the **Solution name**.</span></span>

   4. <span data-ttu-id="7e1e3-129">**[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="7e1e3-129">Select **OK**.</span></span>

      <span data-ttu-id="7e1e3-130">プロジェクトは *、IService1.cs* (または Visual Basic プロジェクトの*場合は IService1.vb)、Service1.cs* (または Visual Basic プロジェクトの場合は*Service1.vb)、\*\*および App.config*の 3 つのファイルを含むプロジェクトを作成します。 *Service1.cs*これらのファイルは、次のように定義されます。</span><span class="sxs-lookup"><span data-stu-id="7e1e3-130">Visual Studio creates the project, which has three files: *IService1.cs* (or *IService1.vb* for a Visual Basic project), *Service1.cs* (or *Service1.vb* for a Visual Basic project), and *App.config*. Visual Studio defines these files as follows:</span></span>
      - <span data-ttu-id="7e1e3-131">*IService1*ファイルには、サービス コントラクトの既定の定義が含まれています。</span><span class="sxs-lookup"><span data-stu-id="7e1e3-131">The *IService1* file contains the default definition of the service contract.</span></span>
      - <span data-ttu-id="7e1e3-132">*Service1*ファイルには、サービス コントラクトの既定の実装が含まれています。</span><span class="sxs-lookup"><span data-stu-id="7e1e3-132">The *Service1* file contains the default implementation of the service contract.</span></span>
      - <span data-ttu-id="7e1e3-133">*App.config*ファイルには、Visual Studio WCF サービス ホスト ツールを使用して既定のサービスを読み込むために必要な構成情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="7e1e3-133">The *App.config* file contains the configuration info needed to load the default service with the Visual Studio WCF Service Host tool.</span></span> <span data-ttu-id="7e1e3-134">WCF サービス ホスト ツールの詳細については[、「WCF サービス ホスト (WcfSvcHost.exe)」を参照してください](wcf-service-host-wcfsvchost-exe.md)。</span><span class="sxs-lookup"><span data-stu-id="7e1e3-134">For more information about the WCF Service Host tool, see [WCF Service Host (WcfSvcHost.exe)](wcf-service-host-wcfsvchost-exe.md).</span></span>

      > [!NOTE]
      > <span data-ttu-id="7e1e3-135">Visual Basic の開発者環境設定を使用して Visual Studio をインストールした場合、ソリューションが非表示になっている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="7e1e3-135">If you installed Visual Studio with Visual Basic developer environment settings, the solution might be hidden.</span></span> <span data-ttu-id="7e1e3-136">この場合は、[**ツール**] メニューの **[オプション]** を選択し、[**オプション]** **ウィンドウで**[**プロジェクトとソリューション** > 全般] を選択します。</span><span class="sxs-lookup"><span data-stu-id="7e1e3-136">If this is the case, select **Options** from the **Tools** menu, then select **Projects and Solutions** > **General** in the **Options** window.</span></span> <span data-ttu-id="7e1e3-137">[**常にソリューションを表示する] を選択**します。</span><span class="sxs-lookup"><span data-stu-id="7e1e3-137">Select **Always show solution**.</span></span> <span data-ttu-id="7e1e3-138">また、[**作成時に新しいプロジェクトを保存]** が選択されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="7e1e3-138">Also, verify that **Save new projects when created** is selected.</span></span>

3. <span data-ttu-id="7e1e3-139">**ソリューション エクスプローラー**で **、IService1.cs**または**IService1.vb**ファイルを開き、コードを次のコードに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="7e1e3-139">From **Solution Explorer**, open the **IService1.cs** or **IService1.vb** file, and replace its code with the following code:</span></span>

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

     <span data-ttu-id="7e1e3-140">このコントラクトは、オンライン電卓を定義します。</span><span class="sxs-lookup"><span data-stu-id="7e1e3-140">This contract defines an online calculator.</span></span> <span data-ttu-id="7e1e3-141">インターフェイスに`ICalculator`<xref:System.ServiceModel.ServiceContractAttribute>属性が付いていることに注意`ServiceContract`してください ( として簡略化されます)。</span><span class="sxs-lookup"><span data-stu-id="7e1e3-141">Notice the `ICalculator` interface is marked with the <xref:System.ServiceModel.ServiceContractAttribute> attribute (simplified as `ServiceContract`).</span></span> <span data-ttu-id="7e1e3-142">この属性は、コントラクト名を明確にする名前空間を定義します。</span><span class="sxs-lookup"><span data-stu-id="7e1e3-142">This attribute defines a namespace to disambiguate the contract name.</span></span> <span data-ttu-id="7e1e3-143">このコードは、各電卓の<xref:System.ServiceModel.OperationContractAttribute>操作を属性でマーク`OperationContract`します (として簡略化)。</span><span class="sxs-lookup"><span data-stu-id="7e1e3-143">The code marks each calculator operation with the <xref:System.ServiceModel.OperationContractAttribute> attribute (simplified as `OperationContract`).</span></span>

## <a name="next-steps"></a><span data-ttu-id="7e1e3-144">次のステップ</span><span class="sxs-lookup"><span data-stu-id="7e1e3-144">Next steps</span></span>

<span data-ttu-id="7e1e3-145">このチュートリアルでは、以下の内容を学習しました。</span><span class="sxs-lookup"><span data-stu-id="7e1e3-145">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="7e1e3-146">WCF サービス ライブラリ プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="7e1e3-146">Create a WCF Service Library project.</span></span>
> - <span data-ttu-id="7e1e3-147">サービス コントラクト インターフェイスを定義します。</span><span class="sxs-lookup"><span data-stu-id="7e1e3-147">Define a service contract interface.</span></span>

<span data-ttu-id="7e1e3-148">WCF サービス コントラクトを実装する方法については、次のチュートリアルに進みます。</span><span class="sxs-lookup"><span data-stu-id="7e1e3-148">Advance to the next tutorial to learn how to implement the WCF service contract.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="7e1e3-149">チュートリアル: WCF サービス コントラクトを実装する</span><span class="sxs-lookup"><span data-stu-id="7e1e3-149">Tutorial: Implement a WCF service contract</span></span>](how-to-implement-a-wcf-contract.md)
