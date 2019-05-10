---
title: アプリケーションの構成
ms.date: 03/30/2017
ms.assetid: a2f995b0-669d-4721-b00f-4561ec7eb6a4
ms.openlocfilehash: 9a1365bb567c552fb087e67a10e48fe0bc2da873
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64652035"
---
# <a name="configuring-your-application"></a><span data-ttu-id="1f6ce-102">アプリケーションの構成</span><span class="sxs-lookup"><span data-stu-id="1f6ce-102">Configuring Your Application</span></span>
<span data-ttu-id="1f6ce-103">Windows Communication Foundation (WCF) は、.NET 構成システムを使用し、コンピューターとアプリケーションの両方のスコープでサービスを構成することができます。</span><span class="sxs-lookup"><span data-stu-id="1f6ce-103">Windows Communication Foundation (WCF) uses the .NET configuration system and allows you to configure services at both the machine and application scope.</span></span>  
  
 <span data-ttu-id="1f6ce-104">WCF によって定義された構成設定にある、`<system.serviceModel>`セクション グループ。</span><span class="sxs-lookup"><span data-stu-id="1f6ce-104">Configuration settings defined by WCF are located in the `<system.serviceModel>` section group.</span></span> <span data-ttu-id="1f6ce-105">WCF サービスを構成する方法の詳細については、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="1f6ce-105">For more information about how to configure a WCF service, see the following topics:</span></span>  
  
- [<span data-ttu-id="1f6ce-106">サービスの構成</span><span class="sxs-lookup"><span data-stu-id="1f6ce-106">Configuring Services</span></span>](../../../../docs/framework/wcf/configuring-services.md)  
  
- [<span data-ttu-id="1f6ce-107">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="1f6ce-107">\<system.serviceModel></span></span>](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)  
  
 <span data-ttu-id="1f6ce-108">アプリケーション定義の構成設定は、`<appSettings>` セクション グループで定義されています。</span><span class="sxs-lookup"><span data-stu-id="1f6ce-108">Application-defined configurations settings are defined in the `<appSettings>` section group.</span></span> <span data-ttu-id="1f6ce-109">.NET 構成ファイル内のアプリケーション設定の詳細については、次を参照してください。 [ \<appSettings >](https://go.microsoft.com/fwlink/?LinkId=95159)します。</span><span class="sxs-lookup"><span data-stu-id="1f6ce-109">For more information about application settings in .NET configuration files, see [\<appSettings>](https://go.microsoft.com/fwlink/?LinkId=95159).</span></span>  
  
## <a name="using-the-configuration-editor"></a><span data-ttu-id="1f6ce-110">構成エディターの使用</span><span class="sxs-lookup"><span data-stu-id="1f6ce-110">Using the Configuration Editor</span></span>  
 <span data-ttu-id="1f6ce-111">WCF[構成エディター ツール (SvcConfigEditor.exe)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md)管理者および開発者を作成およびグラフィカル ユーザー インターフェイスを使用して WCF サービスの構成設定を変更します。</span><span class="sxs-lookup"><span data-stu-id="1f6ce-111">The WCF [Configuration Editor Tool (SvcConfigEditor.exe)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md) allows administrators and developers to create and modify configuration settings for WCF services using a graphical user interface.</span></span> <span data-ttu-id="1f6ce-112">このツールでは、XML 構成ファイルを直接編集することがなく WCF バインディング、動作、サービス、および診断の設定を管理できます。</span><span class="sxs-lookup"><span data-stu-id="1f6ce-112">With this tool, you can manage settings for WCF bindings, behaviors, services, and diagnostics without directly editing XML configuration files.</span></span>  
  
## <a name="editing-configuration-files-in-visual-studio"></a><span data-ttu-id="1f6ce-113">Visual Studio の構成ファイルの編集</span><span class="sxs-lookup"><span data-stu-id="1f6ce-113">Editing Configuration Files in Visual Studio</span></span>  
 <span data-ttu-id="1f6ce-114">Visual Studio での WCF サービス プロジェクトの構成ファイルを編集するには、右クリックで**ソリューション エクスプ ローラー**を選択し、 **Edit WCF Config**コンテキスト メニュー項目。</span><span class="sxs-lookup"><span data-stu-id="1f6ce-114">To edit the configuration file of a WCF service project in Visual Studio, right click it in **Solution Explorer** and choose the **Edit WCF Config** context menu item.</span></span> <span data-ttu-id="1f6ce-115">これにより、起動、[構成エディター ツール (SvcConfigEditor.exe)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md)します。</span><span class="sxs-lookup"><span data-stu-id="1f6ce-115">This launches the [Configuration Editor Tool (SvcConfigEditor.exe)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1f6ce-116">右クリックして Visual Studio での WCF Web サービス プロジェクトの構成ファイルを編集する場合**ソリューション エクスプ ローラー**、注意、 **Edit WCF Config**コンテキスト メニュー項目がありません。</span><span class="sxs-lookup"><span data-stu-id="1f6ce-116">If you edit the configuration file of a WCF Web Service project in Visual Studio by right-clicking it in **Solution Explorer**, notice that the **Edit WCF Config** context menu item is missing.</span></span> <span data-ttu-id="1f6ce-117">この問題を回避するには、をクリックして、**ツール**] メニューの [選択**WCF Service Config Editor**します。</span><span class="sxs-lookup"><span data-stu-id="1f6ce-117">To workaround this issue, click the **Tools** menu, and choose **WCF Service Config Editor**.</span></span> <span data-ttu-id="1f6ce-118">その後、構成ファイルを右クリックし、使用して、、 **Edit WCF Config**コンテキスト メニュー項目。</span><span class="sxs-lookup"><span data-stu-id="1f6ce-118">After that, you can right-click a configuration file and use the **Edit WCF Config** context menu item.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f6ce-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="1f6ce-119">See also</span></span>

- [<span data-ttu-id="1f6ce-120">構成エディター ツール (SvcConfigEditor.exe)</span><span class="sxs-lookup"><span data-stu-id="1f6ce-120">Configuration Editor Tool (SvcConfigEditor.exe)</span></span>](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md)
- [<span data-ttu-id="1f6ce-121">サービスの構成</span><span class="sxs-lookup"><span data-stu-id="1f6ce-121">Configuring Services</span></span>](../../../../docs/framework/wcf/configuring-services.md)
- [<span data-ttu-id="1f6ce-122">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="1f6ce-122">\<system.serviceModel></span></span>](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)
