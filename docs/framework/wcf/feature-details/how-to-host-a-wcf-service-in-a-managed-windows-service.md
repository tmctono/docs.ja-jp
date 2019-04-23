---
title: '方法: マネージド Windows サービスで WCF サービスをホストする'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8e37363b-4dad-4fb6-907f-73c30fac1d9a
ms.openlocfilehash: c63b249cf16100f0b18d622fdecd7cd375df83d8
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59297760"
---
# <a name="how-to-host-a-wcf-service-in-a-managed-windows-service"></a><span data-ttu-id="2a445-102">方法: マネージド Windows サービスで WCF サービスをホストする</span><span class="sxs-lookup"><span data-stu-id="2a445-102">How to: Host a WCF Service in a Managed Windows Service</span></span>

<span data-ttu-id="2a445-103">このトピックでは、Windows サービスによってホストされている Windows Communication Foundation (WCF) サービスを作成するために必要な基本的な手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="2a445-103">This topic outlines the basic steps required to create a Windows Communication Foundation (WCF) service that is hosted by a Windows Service.</span></span> <span data-ttu-id="2a445-104">シナリオは、ホスト オプションがアクティブ化メッセージをセキュリティで保護された環境でインターネット インフォメーション サービス (IIS) の外部でホストされている実行時間の長い WCF サービスでは、マネージ Windows サービスで有効です。</span><span class="sxs-lookup"><span data-stu-id="2a445-104">The scenario is enabled by the managed Windows service hosting option that is a long-running WCF service hosted outside of Internet Information Services (IIS) in a secure environment that is not message activated.</span></span> <span data-ttu-id="2a445-105">サービスの有効期限は代わりにオペレーティング システムによって制御されます。</span><span class="sxs-lookup"><span data-stu-id="2a445-105">The lifetime of the service is controlled instead by the operating system.</span></span> <span data-ttu-id="2a445-106">このホスト オプションは Windows のすべてのバージョンで使用できます。</span><span class="sxs-lookup"><span data-stu-id="2a445-106">This hosting option is available in all versions of Windows.</span></span>

<span data-ttu-id="2a445-107">Windows サービスは、Microsoft 管理コンソール (MMC) の Microsoft.ManagementConsole.SnapIn を使用して管理し、システムのブート時に自動的に起動するように構成できます。</span><span class="sxs-lookup"><span data-stu-id="2a445-107">Windows services can be managed with the Microsoft.ManagementConsole.SnapIn in Microsoft Management Console (MMC) and can be configured to start up automatically when the system boots up.</span></span> <span data-ttu-id="2a445-108">このホスト オプションは、サービスのプロセス有効期間は Windows サービスのサービス コントロール マネージャー (SCM) によって、制御できるようにマネージ Windows サービスとして WCF サービスをホストするアプリケーション ドメイン (AppDomain) の登録で構成されます。</span><span class="sxs-lookup"><span data-stu-id="2a445-108">This hosting option consists of registering the application domain (AppDomain) that hosts a WCF service as a managed Windows service so that the process lifetime of the service is controlled by the Service Control Manager (SCM) for Windows services.</span></span>

<span data-ttu-id="2a445-109">サービス コードには、サービス コントラクトのサービス実装、Windows サービス クラス、およびインストーラー クラスが含まれています。</span><span class="sxs-lookup"><span data-stu-id="2a445-109">The service code includes a service implementation of the service contract, a Windows Service class, and an installer class.</span></span> <span data-ttu-id="2a445-110">サービス実装クラスで、`CalculatorService`は、WCF サービスです。</span><span class="sxs-lookup"><span data-stu-id="2a445-110">The service implementation class, `CalculatorService`, is a WCF service.</span></span> <span data-ttu-id="2a445-111">一方、`CalculatorWindowsService` は Windows サービスです。</span><span class="sxs-lookup"><span data-stu-id="2a445-111">The `CalculatorWindowsService` is a Windows service.</span></span> <span data-ttu-id="2a445-112">Windows サービスとして限定するため、このクラスは `ServiceBase` を継承し、`OnStart` メソッドと `OnStop` メソッドを実装しています。</span><span class="sxs-lookup"><span data-stu-id="2a445-112">To qualify as a Windows service, the class inherits from `ServiceBase` and implements the `OnStart` and `OnStop` methods.</span></span> <span data-ttu-id="2a445-113">`OnStart` では、<xref:System.ServiceModel.ServiceHost> 型の `CalculatorService` が作成され、開かれます。</span><span class="sxs-lookup"><span data-stu-id="2a445-113">In `OnStart`, a <xref:System.ServiceModel.ServiceHost> is created for the `CalculatorService` type and opened.</span></span> <span data-ttu-id="2a445-114">`OnStop` では、このサービスが停止され、破棄されます。</span><span class="sxs-lookup"><span data-stu-id="2a445-114">In `OnStop`, the service is stopped and disposed.</span></span> <span data-ttu-id="2a445-115">ホストはベース アドレスをサービス ホストに提供する必要もあります。サービス ホストは、アプリケーション設定で構成されます。</span><span class="sxs-lookup"><span data-stu-id="2a445-115">The host is also responsible for providing a base address to the service host, which has been configured in application settings.</span></span> <span data-ttu-id="2a445-116">インストーラー クラスは <xref:System.Configuration.Install.Installer> を継承します。このクラスを使用すると、Installutil.exe ツールにより、プログラムを Windows サービスとしてインストールできます。</span><span class="sxs-lookup"><span data-stu-id="2a445-116">The installer class, which inherits from <xref:System.Configuration.Install.Installer>, allows the program to be installed as a Windows service by the Installutil.exe tool.</span></span>

## <a name="construct-the-service-and-provide-the-hosting-code"></a><span data-ttu-id="2a445-117"> サービスを構築してホスティング コードを提供する</span><span class="sxs-lookup"><span data-stu-id="2a445-117">Construct the service and provide the hosting code</span></span>

1. <span data-ttu-id="2a445-118">作成する新しい Visual Studio**コンソール アプリ**という名前のプロジェクト**サービス**します。</span><span class="sxs-lookup"><span data-stu-id="2a445-118">Create a new Visual Studio **Console app** project called **Service**.</span></span>

2. <span data-ttu-id="2a445-119">Program.cs を Service.cs に変更します。</span><span class="sxs-lookup"><span data-stu-id="2a445-119">Rename Program.cs to Service.cs.</span></span>

3. <span data-ttu-id="2a445-120">名前空間を変更`Microsoft.ServiceModel.Samples`します。</span><span class="sxs-lookup"><span data-stu-id="2a445-120">Change the namespace to `Microsoft.ServiceModel.Samples`.</span></span>

4. <span data-ttu-id="2a445-121">次のアセンブリへの参照を追加します。</span><span class="sxs-lookup"><span data-stu-id="2a445-121">Add references to the following assemblies:</span></span>

    - <span data-ttu-id="2a445-122">System.ServiceModel.dll</span><span class="sxs-lookup"><span data-stu-id="2a445-122">System.ServiceModel.dll</span></span>

    - <span data-ttu-id="2a445-123">System.ServiceProcess.dll</span><span class="sxs-lookup"><span data-stu-id="2a445-123">System.ServiceProcess.dll</span></span>

    - <span data-ttu-id="2a445-124">System.Configuration.Install.dll</span><span class="sxs-lookup"><span data-stu-id="2a445-124">System.Configuration.Install.dll</span></span>

5. <span data-ttu-id="2a445-125">次の using ステートメントを Service.cs に追加します。</span><span class="sxs-lookup"><span data-stu-id="2a445-125">Add the following using statements to Service.cs.</span></span>

     [!code-csharp[c_HowTo_HostInNTService#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinntservice/cs/service.cs#0)]
     [!code-vb[c_HowTo_HostInNTService#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostinntservice/vb/service.vb#0)]

6. <span data-ttu-id="2a445-126">次のコードに示すように、`ICalculator` サービス コントラクトを定義します。</span><span class="sxs-lookup"><span data-stu-id="2a445-126">Define the `ICalculator` service contract as shown in the following code.</span></span>

     [!code-csharp[c_HowTo_HostInNTService#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinntservice/cs/service.cs#1)]
     [!code-vb[c_HowTo_HostInNTService#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostinntservice/vb/service.vb#1)]

7. <span data-ttu-id="2a445-127">次のコードに示すように、`CalculatorService` というクラスにサービス コントラクトを実装します。</span><span class="sxs-lookup"><span data-stu-id="2a445-127">Implement the service contract in a class called `CalculatorService` as shown in the following code.</span></span>

     [!code-csharp[c_HowTo_HostInNTService#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinntservice/cs/service.cs#2)]
     [!code-vb[c_HowTo_HostInNTService#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostinntservice/vb/service.vb#2)]

8. <span data-ttu-id="2a445-128">`CalculatorWindowsService` クラスから継承する <xref:System.ServiceProcess.ServiceBase> という新しいクラスを作成します。</span><span class="sxs-lookup"><span data-stu-id="2a445-128">Create a new class called `CalculatorWindowsService` that inherits from the <xref:System.ServiceProcess.ServiceBase> class.</span></span> <span data-ttu-id="2a445-129">`serviceHost` というローカル変数を追加して、<xref:System.ServiceModel.ServiceHost> インスタンスを参照します。</span><span class="sxs-lookup"><span data-stu-id="2a445-129">Add a local variable called `serviceHost` to reference the <xref:System.ServiceModel.ServiceHost> instance.</span></span> <span data-ttu-id="2a445-130">`Main` を呼び出す `ServiceBase.Run(new CalculatorWindowsService)` というメソッドを定義します。</span><span class="sxs-lookup"><span data-stu-id="2a445-130">Define the `Main` method that calls `ServiceBase.Run(new CalculatorWindowsService)`</span></span>

     [!code-csharp[c_HowTo_HostInNTService#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinntservice/cs/service.cs#3)]
     [!code-vb[c_HowTo_HostInNTService#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostinntservice/vb/service.vb#3)]

9. <span data-ttu-id="2a445-131">次のコードに示すように、新しい <xref:System.ServiceProcess.ServiceBase.OnStart%28System.String%5B%5D%29> インスタンスを作成して開くことによって <xref:System.ServiceModel.ServiceHost> メソッドをオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="2a445-131">Override the <xref:System.ServiceProcess.ServiceBase.OnStart%28System.String%5B%5D%29> method by creating and opening a new <xref:System.ServiceModel.ServiceHost> instance as shown in the following code.</span></span>

     [!code-csharp[c_HowTo_HostInNTService#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinntservice/cs/service.cs#4)]
     [!code-vb[c_HowTo_HostInNTService#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostinntservice/vb/service.vb#4)]

10. <span data-ttu-id="2a445-132">次のコードに示すように、<xref:System.ServiceProcess.ServiceBase.OnStop%2A> を閉じて <xref:System.ServiceModel.ServiceHost> メソッドをオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="2a445-132">Override the <xref:System.ServiceProcess.ServiceBase.OnStop%2A> method closing the <xref:System.ServiceModel.ServiceHost> as shown in the following code.</span></span>

     [!code-csharp[c_HowTo_HostInNTService#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinntservice/cs/service.cs#5)]
     [!code-vb[c_HowTo_HostInNTService#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostinntservice/vb/service.vb#5)]

11. <span data-ttu-id="2a445-133">`ProjectInstaller` から継承し、<xref:System.Configuration.Install.Installer> に設定された <xref:System.ComponentModel.RunInstallerAttribute> でマークされた `true` という新しいクラスを作成します。</span><span class="sxs-lookup"><span data-stu-id="2a445-133">Create a new class called `ProjectInstaller` that inherits from <xref:System.Configuration.Install.Installer> and that is marked with the <xref:System.ComponentModel.RunInstallerAttribute> set to `true`.</span></span> <span data-ttu-id="2a445-134">これで、Installutil.exe ツールで Windows サービスをインストールできるようになります。</span><span class="sxs-lookup"><span data-stu-id="2a445-134">This allows the Windows service to be installed by the Installutil.exe tool.</span></span>

     [!code-csharp[c_HowTo_HostInNTService#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinntservice/cs/service.cs#6)]
     [!code-vb[c_HowTo_HostInNTService#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostinntservice/vb/service.vb#6)]

12. <span data-ttu-id="2a445-135">プロジェクトを作成したときに生成された `Service` クラスを削除します。</span><span class="sxs-lookup"><span data-stu-id="2a445-135">Remove the `Service` class that was generated when you created the project.</span></span>

13. <span data-ttu-id="2a445-136">アプリケーション構成ファイルをプロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="2a445-136">Add an application configuration file to the project.</span></span> <span data-ttu-id="2a445-137">ファイルの内容を次の構成 XML に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="2a445-137">Replace the contents of the file with the following configuration XML.</span></span>

    ```xml
    <?xml version="1.0" encoding="utf-8" ?>
    <configuration>
      <system.serviceModel>    <services>
          <!-- This section is optional with the new configuration model
               introduced in .NET Framework 4. -->
          <service name="Microsoft.ServiceModel.Samples.CalculatorService"
                   behaviorConfiguration="CalculatorServiceBehavior">
            <host>
              <baseAddresses>
                <add baseAddress="http://localhost:8000/ServiceModelSamples/service"/>
              </baseAddresses>
            </host>
            <!-- this endpoint is exposed at the base address provided by host: http://localhost:8000/ServiceModelSamples/service  -->
            <endpoint address=""
                      binding="wsHttpBinding"
                      contract="Microsoft.ServiceModel.Samples.ICalculator" />
            <!-- the mex endpoint is exposed at http://localhost:8000/ServiceModelSamples/service/mex -->
            <endpoint address="mex"
                      binding="mexHttpBinding"
                      contract="IMetadataExchange" />
          </service>
        </services>
        <behaviors>
          <serviceBehaviors>
            <behavior name="CalculatorServiceBehavior">
              <serviceMetadata httpGetEnabled="true"/>
              <serviceDebug includeExceptionDetailInFaults="False"/>
            </behavior>
          </serviceBehaviors>
        </behaviors>
      </system.serviceModel>
    </configuration>
    ```

     <span data-ttu-id="2a445-138">App.config ファイルを右クリックして、**ソリューション エクスプ ローラー**選択**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="2a445-138">Right click the App.config file in the **Solution Explorer** and select **Properties**.</span></span> <span data-ttu-id="2a445-139">**出力ディレクトリにコピー**選択**新しい場合はコピー**します。</span><span class="sxs-lookup"><span data-stu-id="2a445-139">Under **Copy to Output Directory** select **Copy if Newer**.</span></span>

     <span data-ttu-id="2a445-140">この例では、構成ファイルにエンドポイントを明示的に指定します。</span><span class="sxs-lookup"><span data-stu-id="2a445-140">This example explicitly specifies endpoints in the configuration file.</span></span> <span data-ttu-id="2a445-141">エンドポイントをサービスに追加しない場合、ランタイムによって既定のエンドポイントが追加されます。</span><span class="sxs-lookup"><span data-stu-id="2a445-141">If you do not add any endpoints to the service, the runtime adds default endpoints for you.</span></span> <span data-ttu-id="2a445-142">この例では、サービスには <xref:System.ServiceModel.Description.ServiceMetadataBehavior> に設定された `true` があるので、サービスで公開メタデータも有効化されています。</span><span class="sxs-lookup"><span data-stu-id="2a445-142">In this example, because the service has a <xref:System.ServiceModel.Description.ServiceMetadataBehavior> set to `true`, your service also has publishing metadata enabled.</span></span> <span data-ttu-id="2a445-143">既定のエンドポイントについては、「[Simplified Configuration](../../../../docs/framework/wcf/simplified-configuration.md)」 (簡易構成) と「[Simplified Configuration for WCF Services](../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md)」 (WCF サービスの簡易構成) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2a445-143">For more information about default endpoints, bindings, and behaviors, see [Simplified Configuration](../../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>

## <a name="install-and-run-the-service"></a><span data-ttu-id="2a445-144">サービスをインストールして実行する</span><span class="sxs-lookup"><span data-stu-id="2a445-144">Install and run the service</span></span>

1. <span data-ttu-id="2a445-145">ソリューションをビルドして `Service.exe` 実行可能ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="2a445-145">Build the solution to create the `Service.exe` executable.</span></span>

2. <span data-ttu-id="2a445-146">For Visual Studio 開発者コマンド プロンプトを開き、プロジェクト ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="2a445-146">Open Developer Command Prompt for Visual Studio and navigate to the project directory.</span></span> <span data-ttu-id="2a445-147">コマンド プロンプトで「`installutil bin\service.exe`」と入力して、Windows サービスをインストールします </span><span class="sxs-lookup"><span data-stu-id="2a445-147">Type `installutil bin\service.exe` at the command prompt to install the Windows service.</span></span>

     <span data-ttu-id="2a445-148">コマンド プロンプトで「`services.msc`」と入力してサービス コントロール マネージャー (SCM) にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="2a445-148">Type `services.msc` at the command prompt to access the Service Control Manager (SCM).</span></span> <span data-ttu-id="2a445-149">Windows サービスは、[Services] に "WCFWindowsServiceSample" として表示されます。</span><span class="sxs-lookup"><span data-stu-id="2a445-149">The Windows service should appear in Services as "WCFWindowsServiceSample".</span></span> <span data-ttu-id="2a445-150">WCF サービスは、Windows サービスが実行されている場合にのみクライアントに応答できます。</span><span class="sxs-lookup"><span data-stu-id="2a445-150">The WCF service can only respond to clients if the Windows service is running.</span></span> <span data-ttu-id="2a445-151">サービスを開始する、SCM"Start"、または選択の種類で右**net start WCFWindowsServiceSample**コマンド プロンプトでします。</span><span class="sxs-lookup"><span data-stu-id="2a445-151">To start the service, right-click it in the SCM and select "Start", or type **net start WCFWindowsServiceSample** at the command prompt.</span></span>

3. <span data-ttu-id="2a445-152">サービスを変更する場合は、まずそのサービスを停止してからアンインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="2a445-152">If you make changes to the service, you must first stop it and uninstall it.</span></span> <span data-ttu-id="2a445-153">サービスを停止し、SCM でそのサービスを右クリックし、"Stop"を選択または**型 net stop WCFWindowsServiceSample**コマンド プロンプトでします。</span><span class="sxs-lookup"><span data-stu-id="2a445-153">To stop the service, right-click the service in the SCM and select "Stop", or **type net stop WCFWindowsServiceSample** at the command prompt.</span></span> <span data-ttu-id="2a445-154">Windows サービスを停止してクライアントを実行すると、クライアントがこのサービスにアクセスしようとしたときに <xref:System.ServiceModel.EndpointNotFoundException> 例外が発生することに注意してください。</span><span class="sxs-lookup"><span data-stu-id="2a445-154">Note that if you stop the Windows service and then run a client, an <xref:System.ServiceModel.EndpointNotFoundException> exception occurs when a client attempts to access the service.</span></span> <span data-ttu-id="2a445-155">Windows サービスの種類をアンインストールする**installutil/u bin\service.exe**コマンド プロンプトでします。</span><span class="sxs-lookup"><span data-stu-id="2a445-155">To uninstall the Windows service type **installutil /u bin\service.exe** at the command prompt.</span></span>

## <a name="example"></a><span data-ttu-id="2a445-156">例</span><span class="sxs-lookup"><span data-stu-id="2a445-156">Example</span></span>

<span data-ttu-id="2a445-157">このトピックで使用されるコードの完全な一覧を次に示します。</span><span class="sxs-lookup"><span data-stu-id="2a445-157">The following is a complete listing of the code used by this topic:</span></span>

[!code-csharp[c_HowTo_HostInNTService#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinntservice/cs/service.cs#8)]
[!code-vb[c_HowTo_HostInNTService#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostinntservice/vb/service.vb#8)]

<span data-ttu-id="2a445-158">"自己ホスト" オプションと同様、Windows サービス ホスト環境では、ホスト コードをアプリケーションの一部として記述する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2a445-158">Like the "Self-Hosting" option, the Windows service hosting environment requires that some hosting code be written as part of the application.</span></span> <span data-ttu-id="2a445-159">サービスはコンソール アプリケーションとして実装され、独自のホスティング コードが指定されます。</span><span class="sxs-lookup"><span data-stu-id="2a445-159">The service is implemented as a console application and contains its own hosting code.</span></span> <span data-ttu-id="2a445-160">インターネット インフォメーション サービス (IIS) でホストされる Windows プロセス アクティブ化サービス (WAS) など、他のホスト環境ではホスティング コードを記述する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="2a445-160">In other hosting environments, such as Windows Process Activation Service (WAS) hosting in Internet Information Services (IIS), it is not necessary for developers to write hosting code.</span></span>

## <a name="see-also"></a><span data-ttu-id="2a445-161">関連項目</span><span class="sxs-lookup"><span data-stu-id="2a445-161">See also</span></span>

- [<span data-ttu-id="2a445-162">簡略化された構成</span><span class="sxs-lookup"><span data-stu-id="2a445-162">Simplified Configuration</span></span>](../../../../docs/framework/wcf/simplified-configuration.md)
- [<span data-ttu-id="2a445-163">マネージド アプリケーションのホスト</span><span class="sxs-lookup"><span data-stu-id="2a445-163">Hosting in a Managed Application</span></span>](../../../../docs/framework/wcf/feature-details/hosting-in-a-managed-application.md)
- [<span data-ttu-id="2a445-164">ホスティング サービス</span><span class="sxs-lookup"><span data-stu-id="2a445-164">Hosting Services</span></span>](../../../../docs/framework/wcf/hosting-services.md)
- [<span data-ttu-id="2a445-165">AppFabric のホスティング機能</span><span class="sxs-lookup"><span data-stu-id="2a445-165">Windows Server App Fabric Hosting Features</span></span>](https://go.microsoft.com/fwlink/?LinkId=201276)