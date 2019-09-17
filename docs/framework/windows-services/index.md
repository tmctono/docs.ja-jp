---
title: Windows サービス アプリケーションの開発
ms.date: 03/30/2017
helpviewer_keywords:
- ServiceInstaller class, Windows Service applications
- Service class, Windows Service applications
- Windows Service applications
- Windows NT services
- ServiceProcessInstaller class, Windows Service applications
- services
- .NET applications, Windows applications
ms.assetid: ba72d648-9553-4849-b829-069ad5ea014b
author: ghogen
ms.openlocfilehash: 61f969c22ac06bd6ed20ccfa9124db3bb35d0692
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2019
ms.locfileid: "71053542"
---
# <a name="develop-windows-service-apps"></a><span data-ttu-id="c11da-102">Windows サービス アプリを開発する</span><span class="sxs-lookup"><span data-stu-id="c11da-102">Develop Windows service apps</span></span>

<span data-ttu-id="c11da-103">Visual Studio または .NET Framework SDK を使用すると、サービスとしてインストールするアプリケーションを作成することで簡単に作成できます。</span><span class="sxs-lookup"><span data-stu-id="c11da-103">Using Visual Studio or the .NET Framework SDK, you can easily create services by creating an application that is installed as a service.</span></span> <span data-ttu-id="c11da-104">この種類のアプリケーションは、Windows サービスと呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="c11da-104">This type of application is called a Windows service.</span></span> <span data-ttu-id="c11da-105">フレームワーク機能を使用することで、サービスを作成、インストール、開始、停止したり、動作を制御したりできます。</span><span class="sxs-lookup"><span data-stu-id="c11da-105">With framework features, you can create services, install them, and start, stop, and otherwise control their behavior.</span></span>

> [!NOTE]
> <span data-ttu-id="c11da-106">Visual Studio では、必要に応じて既存の C++ コードと相互運用できる Visual C# または Visual Basic のマネージド コードでサービスを作成できます。</span><span class="sxs-lookup"><span data-stu-id="c11da-106">In Visual Studio you can create a service in managed code in Visual C# or Visual Basic, which can interoperate with existing C++ code if required.</span></span> <span data-ttu-id="c11da-107">また、[ATL プロジェクト ウィザード](/cpp/atl/reference/atl-project-wizard)を使用して、ネイティブ C ++で Windows サービスを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="c11da-107">Or, you can create a Windows service in native C++ by using the [ATL Project Wizard](/cpp/atl/reference/atl-project-wizard).</span></span>

## <a name="in-this-section"></a><span data-ttu-id="c11da-108">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="c11da-108">In this section</span></span>

[<span data-ttu-id="c11da-109">Windows サービス アプリケーションの概要</span><span class="sxs-lookup"><span data-stu-id="c11da-109">Introduction to Windows Service Applications</span></span>](introduction-to-windows-service-applications.md)

<span data-ttu-id="c11da-110">Windows サービス アプリケーションの概要、サービスの有効期間、およびサービスがその他の一般的な種類のプロジェクトどのように異なるかを説明します。</span><span class="sxs-lookup"><span data-stu-id="c11da-110">Provides an overview of Windows service applications, the lifetime of a service, and how service applications differ from other common project types.</span></span>

[<span data-ttu-id="c11da-111">チュートリアル: コンポーネント デザイナーによる Windows サービス アプリケーションの作成</span><span class="sxs-lookup"><span data-stu-id="c11da-111">Walkthrough: Creating a Windows Service Application in the Component Designer</span></span>](walkthrough-creating-a-windows-service-application-in-the-component-designer.md)

<span data-ttu-id="c11da-112">Visual Basic および Visual C# でサービスを作成する例を提供します。</span><span class="sxs-lookup"><span data-stu-id="c11da-112">Provides an example of creating a service in Visual Basic and Visual C#.</span></span>

[<span data-ttu-id="c11da-113">サービス アプリケーションのプログラミング アーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="c11da-113">Service Application Programming Architecture</span></span>](service-application-programming-architecture.md)

<span data-ttu-id="c11da-114">サービスのプログラミングで使用される言語要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="c11da-114">Explains the language elements used in service programming.</span></span>

[<span data-ttu-id="c11da-115">方法: Windows サービスを作成する</span><span class="sxs-lookup"><span data-stu-id="c11da-115">How to: Create Windows Services</span></span>](how-to-create-windows-services.md)

<span data-ttu-id="c11da-116">Windows サービス プロジェクトのテンプレートを使用して Windows サービスを作成、構成するプロセスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="c11da-116">Describes the process of creating and configuring Windows services using the Windows service project template.</span></span>

## <a name="related-sections"></a><span data-ttu-id="c11da-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="c11da-117">Related sections</span></span>

<span data-ttu-id="c11da-118"><xref:System.ServiceProcess.ServiceBase>: サービスの作成に使用される、<xref:System.ServiceProcess.ServiceBase> クラスの主要な機能を説明します。</span><span class="sxs-lookup"><span data-stu-id="c11da-118"><xref:System.ServiceProcess.ServiceBase> - Describes the major features of the <xref:System.ServiceProcess.ServiceBase> class, which is used to create services.</span></span>

<span data-ttu-id="c11da-119"><xref:System.ServiceProcess.ServiceProcessInstaller>: <xref:System.ServiceProcess.ServiceInstaller> クラスと共に使用して、サービスをインストール/アンインストールする <xref:System.ServiceProcess.ServiceProcessInstaller> クラスの機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="c11da-119"><xref:System.ServiceProcess.ServiceProcessInstaller> - Describes the features of the <xref:System.ServiceProcess.ServiceProcessInstaller> class, which is used along with the <xref:System.ServiceProcess.ServiceInstaller> class to install and uninstall your services.</span></span>

<span data-ttu-id="c11da-120"><xref:System.ServiceProcess.ServiceInstaller>: <xref:System.ServiceProcess.ServiceProcessInstaller> クラスと共に使用して、サービスをインストール/アンインストールする <xref:System.ServiceProcess.ServiceInstaller> クラスの機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="c11da-120"><xref:System.ServiceProcess.ServiceInstaller> - Describes the features of the <xref:System.ServiceProcess.ServiceInstaller> class, which is used along with the <xref:System.ServiceProcess.ServiceProcessInstaller> class to install and uninstall your service.</span></span>

<span data-ttu-id="c11da-121">[テンプレートからプロジェクトを作成する](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/0fyc0azh(v=vs.120)): この章で使用されるプロジェクトの種類と、それを選択する際に役立つガイドラインを説明します。</span><span class="sxs-lookup"><span data-stu-id="c11da-121">[Create Projects from Templates](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/0fyc0azh(v=vs.120)) -  Describes the projects types used in this chapter and how to choose between them.</span></span>
