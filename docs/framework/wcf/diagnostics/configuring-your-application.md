---
title: アプリケーションの構成
ms.date: 03/30/2017
ms.assetid: a2f995b0-669d-4721-b00f-4561ec7eb6a4
ms.openlocfilehash: e096f4b64ada8b142e8b82c8877eec7f1b84637c
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69939812"
---
# <a name="configuring-your-application"></a><span data-ttu-id="ed699-102">アプリケーションの構成</span><span class="sxs-lookup"><span data-stu-id="ed699-102">Configuring Your Application</span></span>
<span data-ttu-id="ed699-103">Windows Communication Foundation (WCF) では、.NET 構成システムを使用して、コンピューターとアプリケーションの両方のスコープでサービスを構成できます。</span><span class="sxs-lookup"><span data-stu-id="ed699-103">Windows Communication Foundation (WCF) uses the .NET configuration system and allows you to configure services at both the machine and application scope.</span></span>  
  
 <span data-ttu-id="ed699-104">WCF によって定義された構成`<system.serviceModel>`設定は、セクショングループにあります。</span><span class="sxs-lookup"><span data-stu-id="ed699-104">Configuration settings defined by WCF are located in the `<system.serviceModel>` section group.</span></span> <span data-ttu-id="ed699-105">WCF サービスを構成する方法の詳細については、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ed699-105">For more information about how to configure a WCF service, see the following topics:</span></span>  
  
- [<span data-ttu-id="ed699-106">サービスの構成</span><span class="sxs-lookup"><span data-stu-id="ed699-106">Configuring Services</span></span>](../../../../docs/framework/wcf/configuring-services.md)  
  
- [<span data-ttu-id="ed699-107">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="ed699-107">\<system.serviceModel></span></span>](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)  
  
 <span data-ttu-id="ed699-108">アプリケーション定義の構成設定は、`<appSettings>` セクション グループで定義されています。</span><span class="sxs-lookup"><span data-stu-id="ed699-108">Application-defined configurations settings are defined in the `<appSettings>` section group.</span></span> <span data-ttu-id="ed699-109">.Net 構成ファイルのアプリケーション設定の詳細については、「 [ \<appSettings >](https://go.microsoft.com/fwlink/?LinkId=95159)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ed699-109">For more information about application settings in .NET configuration files, see [\<appSettings>](https://go.microsoft.com/fwlink/?LinkId=95159).</span></span>  
  
## <a name="using-the-configuration-editor"></a><span data-ttu-id="ed699-110">構成エディターの使用</span><span class="sxs-lookup"><span data-stu-id="ed699-110">Using the Configuration Editor</span></span>  
 <span data-ttu-id="ed699-111">WCF[構成エディターツール (svcconfigeditor.exe)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md)を使用すると、管理者および開発者は、グラフィカルユーザーインターフェイスを使用して wcf サービスの構成設定を作成および変更できます。</span><span class="sxs-lookup"><span data-stu-id="ed699-111">The WCF [Configuration Editor Tool (SvcConfigEditor.exe)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md) allows administrators and developers to create and modify configuration settings for WCF services using a graphical user interface.</span></span> <span data-ttu-id="ed699-112">このツールを使用すると、XML 構成ファイルを直接編集することなく、WCF のバインディング、動作、サービス、および診断の設定を管理できます。</span><span class="sxs-lookup"><span data-stu-id="ed699-112">With this tool, you can manage settings for WCF bindings, behaviors, services, and diagnostics without directly editing XML configuration files.</span></span>  
  
## <a name="editing-configuration-files-in-visual-studio"></a><span data-ttu-id="ed699-113">Visual Studio の構成ファイルの編集</span><span class="sxs-lookup"><span data-stu-id="ed699-113">Editing Configuration Files in Visual Studio</span></span>  
 <span data-ttu-id="ed699-114">Visual Studio で WCF サービスプロジェクトの構成ファイルを編集するには、**ソリューションエクスプローラー**で右クリックし、 **[Wcf 構成の編集]** コンテキストメニュー項目を選択します。</span><span class="sxs-lookup"><span data-stu-id="ed699-114">To edit the configuration file of a WCF service project in Visual Studio, right click it in **Solution Explorer** and choose the **Edit WCF Config** context menu item.</span></span> <span data-ttu-id="ed699-115">これにより、[構成エディターツール (svcconfigeditor.exe)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md)が起動します。</span><span class="sxs-lookup"><span data-stu-id="ed699-115">This launches the [Configuration Editor Tool (SvcConfigEditor.exe)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ed699-116">**ソリューションエクスプローラー**で Wcf Web サービスプロジェクトの構成ファイルを右クリックして編集する場合は、 **[Wcf 構成の編集]** コンテキストメニュー項目が表示されないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="ed699-116">If you edit the configuration file of a WCF Web Service project in Visual Studio by right-clicking it in **Solution Explorer**, notice that the **Edit WCF Config** context menu item is missing.</span></span> <span data-ttu-id="ed699-117">この問題を回避するには、 **[ツール]** メニューをクリックし、 **[WCF サービス構成エディター]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="ed699-117">To workaround this issue, click the **Tools** menu, and choose **WCF Service Config Editor**.</span></span> <span data-ttu-id="ed699-118">その後、構成ファイルを右クリックし、 **[WCF 構成の編集]** コンテキストメニュー項目を使用できます。</span><span class="sxs-lookup"><span data-stu-id="ed699-118">After that, you can right-click a configuration file and use the **Edit WCF Config** context menu item.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed699-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="ed699-119">See also</span></span>

- [<span data-ttu-id="ed699-120">構成エディター ツール (SvcConfigEditor.exe)</span><span class="sxs-lookup"><span data-stu-id="ed699-120">Configuration Editor Tool (SvcConfigEditor.exe)</span></span>](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md)
- [<span data-ttu-id="ed699-121">サービスの構成</span><span class="sxs-lookup"><span data-stu-id="ed699-121">Configuring Services</span></span>](../../../../docs/framework/wcf/configuring-services.md)
- [<span data-ttu-id="ed699-122">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="ed699-122">\<system.serviceModel></span></span>](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)
