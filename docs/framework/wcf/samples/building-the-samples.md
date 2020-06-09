---
title: Windows Communication Foundation サンプルのビルド
ms.date: 03/30/2017
ms.assetid: 2899e7a5-9cb2-4e8d-b8d2-f31391549198
ms.openlocfilehash: 53599b3b1827651b48df9921bb59a679a36ee39c
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84592620"
---
# <a name="building-the-windows-communication-foundation-samples"></a><span data-ttu-id="0c550-102">Windows Communication Foundation サンプルのビルド</span><span class="sxs-lookup"><span data-stu-id="0c550-102">Building the Windows Communication Foundation Samples</span></span>

<span data-ttu-id="0c550-103">Windows Communication Foundation (WCF) のサンプルは、Visual Studio IDE を使用するか、コマンドラインから**msbuild**コマンドを使用してビルドできます。</span><span class="sxs-lookup"><span data-stu-id="0c550-103">The Windows Communication Foundation (WCF) samples can be built using the Visual Studio IDE or using the **msbuild** command from the command line.</span></span> <span data-ttu-id="0c550-104">ここでは、両方の手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="0c550-104">Both procedures are described in this topic.</span></span>

> [!NOTE]
> <span data-ttu-id="0c550-105">WCF サンプルをビルドまたは実行する前に、 [Windows Communication Foundation のサンプルに対して1回限りのセットアップ手順](one-time-setup-procedure-for-the-wcf-samples.md)を実行していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="0c550-105">Before building or running any of the WCF samples, ensure you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>

## <a name="to-build-the-sample-using-a-command-prompt"></a><span data-ttu-id="0c550-106">コマンド プロンプトを使用してサンプルをビルドするには</span><span class="sxs-lookup"><span data-stu-id="0c550-106">To build the sample using a command prompt</span></span>

1. <span data-ttu-id="0c550-107">Visual Studio の開発者コマンドプロンプトを開き、サンプルをインストールしたディレクトリの場所にある言語固有のサブディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="0c550-107">Open Developer Command Prompt for Visual Studio and navigate to the language-specific subdirectory under the directory location where you installed the sample.</span></span>

2. <span data-ttu-id="0c550-108">`msbuild`コマンドラインで「」と入力します。</span><span class="sxs-lookup"><span data-stu-id="0c550-108">Type `msbuild` at the command line.</span></span> <span data-ttu-id="0c550-109">クライアントプログラムファイルが*client\bin*に構築され、サービスプログラムファイルが*service\bin*に構築されます。</span><span class="sxs-lookup"><span data-stu-id="0c550-109">The client program files are built to *client\bin* and the service program files are built to *service\bin*.</span></span> <span data-ttu-id="0c550-110">サービスがインターネットインフォメーションサービス (IIS) によってホストされている場合、サービスプログラムファイルは*servicemodelsamples*ディレクトリとその*\bin*サブディレクトリにもコピーされます。</span><span class="sxs-lookup"><span data-stu-id="0c550-110">If the service is hosted by Internet Information Services (IIS), the service program files are also copied to the *servicemodelsamples* directory and its *\bin* subdirectory.</span></span>

> [!NOTE]
> <span data-ttu-id="0c550-111">*%Systemdrive%\inetpub\wwwroot*の acl を設定して、実行しているアカウントに変更のアクセス許可を付与する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0c550-111">You must set the ACLs on *%systemdrive%\inetpub\wwwroot* to grant modify permissions to the account under which you are running.</span></span> <span data-ttu-id="0c550-112">このように設定しない場合、ビルド後のイベントが失敗する場合があります。</span><span class="sxs-lookup"><span data-stu-id="0c550-112">Otherwise some post build events fail.</span></span> <span data-ttu-id="0c550-113">代わりに、ACL の設定はそのままにして、SDK コマンド プロンプトを管理者として実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="0c550-113">Alternatively, you can leave the ACLs as they are and run the SDK command prompt as administrator.</span></span>

## <a name="to-build-the-sample-using-visual-studio"></a><span data-ttu-id="0c550-114">Visual Studio を使用してサンプルをビルドするには</span><span class="sxs-lookup"><span data-stu-id="0c550-114">To build the sample using Visual Studio</span></span>

1. <span data-ttu-id="0c550-115">Visual Studio の [**ファイル**] メニューの [ **Open**  >  **プロジェクト/ソリューション**を開く] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0c550-115">From the **File** menu in Visual Studio, select **Open** > **Project/Solution**.</span></span> <span data-ttu-id="0c550-116">サンプルをインストールしたディレクトリの下にある言語固有のサブディレクトリに移動し、.sln ファイルアイコンをダブルクリックして、Visual Studio でソリューションを開きます。</span><span class="sxs-lookup"><span data-stu-id="0c550-116">Navigate to the language-specific subdirectory under the directory in which you installed the sample, and double-click the .sln file icon to open the solution in Visual Studio.</span></span>

1. <span data-ttu-id="0c550-117">[**ビルド**] メニューの [**ソリューションのリビルド**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0c550-117">From the **Build** menu, select **Rebuild Solution**.</span></span>

   <span data-ttu-id="0c550-118">クライアント プログラムが client\bin にビルドされ、サービス プログラムが service\bin にビルドされます。</span><span class="sxs-lookup"><span data-stu-id="0c550-118">The client program files are built to client\bin and the service program files are built to service\bin.</span></span> <span data-ttu-id="0c550-119">サービスが IIS でホストされている場合、サービスプログラムファイルは*servicemodelsamples*ディレクトリとその*\bin*サブディレクトリにもコピーされます。</span><span class="sxs-lookup"><span data-stu-id="0c550-119">If the service is hosted in IIS, the service program files are also copied to the *servicemodelsamples* directory and its *\bin* subdirectory.</span></span>

> [!NOTE]
> <span data-ttu-id="0c550-120">%systemdrive%\inetpub\wwwroot 上の ACL を、実行中のアカウントに変更権限を付与するように設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0c550-120">You must set the ACLs on %systemdrive%\inetpub\wwwroot to grant modify permissions to the account under which you are running.</span></span> <span data-ttu-id="0c550-121">このように設定しない場合、ビルド後のイベントが失敗する場合があります。</span><span class="sxs-lookup"><span data-stu-id="0c550-121">Otherwise some post build events fail.</span></span> <span data-ttu-id="0c550-122">代わりに、ACL の設定はそのままにして、SDK コマンド プロンプトまたは Visual Studio を管理者として実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="0c550-122">Alternatively, you can leave the ACLs as they are and run the SDK command prompt or Visual Studio as administrator.</span></span> <span data-ttu-id="0c550-123">Visual Studio の一部のアクション (デバッガを ASP.Net ワーカー プロセスにアタッチするアクションなど) では、さらに管理特権が必要です。</span><span class="sxs-lookup"><span data-stu-id="0c550-123">Some Visual Studio actions (such as attaching a debugger to the ASP.Net worker process) also require administrative privileges.</span></span>

## <a name="setup-batch-files-and-scripts"></a><span data-ttu-id="0c550-124">セットアップ バッチ ファイルとスクリプト</span><span class="sxs-lookup"><span data-stu-id="0c550-124">Setup Batch Files and Scripts</span></span>
 <span data-ttu-id="0c550-125">Setup.exe および Cleanup のバッチファイルとスクリプトは、Visual Studio 開発者コマンドプロンプトから実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0c550-125">Setup.exe and Cleanup.exe batch files and scripts should be run from Developer Command Prompt for Visual Studio.</span></span> <span data-ttu-id="0c550-126">いくつかのセットアップ ファイルとクリーンアップ ファイルは、管理特権が必要なタスクを実行します。したがって、これらのファイルは管理特権で起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0c550-126">Several set up and clean up files perform tasks that require administrative privileges and should be launched with administrator privileges.</span></span>

## <a name="important-security-information-about-metadata-endpoints"></a><span data-ttu-id="0c550-127">メタデータ エンドポイントに関する重要なセキュリティ情報</span><span class="sxs-lookup"><span data-stu-id="0c550-127">Important Security Information about Metadata Endpoints</span></span>
 <span data-ttu-id="0c550-128">機密性の高いサービスメタデータが誤って公開されるのを防ぐために、Windows Communication Foundation (WCF) サービスの既定の構成では、メタデータの公開が無効になっています。</span><span class="sxs-lookup"><span data-stu-id="0c550-128">To prevent unintentional disclosure of potentially sensitive service metadata, the default configuration for Windows Communication Foundation (WCF) services disables metadata publishing.</span></span> <span data-ttu-id="0c550-129">この動作は、既定の設定ではセキュリティで保護されますが、同時に、サービスの構成の中でメタデータ発行の動作が明示的に有効化されない限り、サービスの呼び出しに必要なクライアント コードをメタデータ インポート ツール (Svcutil.exe など) を使用して生成できないことも意味します。</span><span class="sxs-lookup"><span data-stu-id="0c550-129">This behavior is secure by default, but also means that you cannot use a metadata import tool (such as Svcutil.exe) to generate the client code required to call the service unless the service’s metadata publishing behavior is explicitly enabled in configuration.</span></span> <span data-ttu-id="0c550-130">サンプルでの試みを容易にするため、ほとんどすべてのサンプルでは、セキュリティ保護されていないメタデータ公開エンドポイントを公開しています。</span><span class="sxs-lookup"><span data-stu-id="0c550-130">To make experimenting with the samples easier, almost all samples expose an unsecured metadata publishing endpoint.</span></span> <span data-ttu-id="0c550-131">このようなエンドポイントを利用するコンシューマーは、匿名で、認証を受けていない可能性もあります。したがって、エンドポイントを配置する前には注意を払い、サービスのメタデータをパブリックに開示することが適切であることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0c550-131">Such endpoints are potentially available to anonymous unauthenticated consumers and care must be taken before deploying such endpoints to ensure that publicly disclosing a service’s metadata is appropriate.</span></span> <span data-ttu-id="0c550-132">サービスメタデータの発行の詳細については、[メタデータ公開動作](metadata-publishing-behavior.md)のサンプルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="0c550-132">For more information about publishing service metadata, see the [Metadata Publishing Behavior](metadata-publishing-behavior.md) sample.</span></span> <span data-ttu-id="0c550-133">メタデータエンドポイントをセキュリティで保護するサンプルについては、[カスタムセキュアメタデータエンドポイント](custom-secure-metadata-endpoint.md)のサンプルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="0c550-133">See the [Custom Secure Metadata Endpoint](custom-secure-metadata-endpoint.md) sample for a sample securing a metadata endpoint.</span></span>

## <a name="exception-handling"></a><span data-ttu-id="0c550-134">例外処理</span><span class="sxs-lookup"><span data-stu-id="0c550-134">Exception Handling</span></span>
 <span data-ttu-id="0c550-135">通常、コードではサンプルの主題を重視するので、これらのサンプルに例外処理は含まれていません。</span><span class="sxs-lookup"><span data-stu-id="0c550-135">Generally speaking these samples do not include exception handling to keep the code focused on the subject of the sample.</span></span> <span data-ttu-id="0c550-136">例外処理の詳細については、「[予期される例外](expected-exceptions.md)のサンプル」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0c550-136">For more information about exception handling, see the [Expected Exceptions](expected-exceptions.md) sample.</span></span>

## <a name="regenerating-clients-and-configuration-with-svcutil"></a><span data-ttu-id="0c550-137">Svcutil を使用したクライアントと構成の再生成</span><span class="sxs-lookup"><span data-stu-id="0c550-137">Regenerating Clients and Configuration with Svcutil</span></span>
 <span data-ttu-id="0c550-138">[ServiceModel メタデータユーティリティツール (svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md)を使用して、ほとんどのサンプルのクライアントコードと構成を再生成することができます。</span><span class="sxs-lookup"><span data-stu-id="0c550-138">You can use the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) to regenerate client code and configuration for most of the samples.</span></span> <span data-ttu-id="0c550-139">一部のサンプルでは、構成を手動で編集する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0c550-139">Some samples require manually edited configuration.</span></span> <span data-ttu-id="0c550-140">たとえば、Svcutil.exe を使用して、クライアント証明書の資格情報を使用するサンプルの構成を再生成する場合は、以前に構成された資格情報を手動で指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0c550-140">For example, if you use Svcutil.exe to regenerate the configuration for a sample that uses client certificate credentials, you must manually specify the credentials previously configured.</span></span> <span data-ttu-id="0c550-141">一部のサンプルでは、生成コードに影響を与える、Svcutil.exe の特定のオプションを使用します。これらのオプションは、そうした特定のサンプルのトピックで指定されます。</span><span class="sxs-lookup"><span data-stu-id="0c550-141">Some samples use specific Svcutil.exe options to affect the generated code, these options are specified in the specific sample topics.</span></span>

### <a name="to-regenerate-the-client-and-configuration-files"></a><span data-ttu-id="0c550-142">クライアントと構成ファイルを再生成するには</span><span class="sxs-lookup"><span data-stu-id="0c550-142">To regenerate the client and configuration files</span></span>

1. <span data-ttu-id="0c550-143">SDK コマンド プロンプトを開き、サンプルのインストール ディレクトリに存在する言語固有のサブディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="0c550-143">Open an SDK command prompt and navigate to the language-specific subdirectory under the directory location where you installed the sample.</span></span>

2. <span data-ttu-id="0c550-144">サービスが Web ホスト型の場合は、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="0c550-144">If the service is a Web-hosted type, use the following command.</span></span>

    ```console
    svcutil.exe /n:"http://Microsoft.ServiceModel.Samples,Microsoft.ServiceModel.Samples" http://localhost/servicemodelsamples/service.svc/mex /out:generatedClient.cs
    ```

     <span data-ttu-id="0c550-145">サービスが自己ホスト型の場合は、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="0c550-145">If the service is a self-hosted type the following command.</span></span>

    ```console
    svcutil.exe /n:"http://Microsoft.ServiceModel.Samples,Microsoft.ServiceModel.Samples" http://localhost:8000/servicemodelsamples/service.svc/mex /out:generatedClient.cs
    ```

     <span data-ttu-id="0c550-146">`http://localhost:8000/ServiceModelSamples/service.svc/mex`自己ホスト型サービスの mex エンドポイントのアドレスで置き換えます。</span><span class="sxs-lookup"><span data-stu-id="0c550-146">Replace `http://localhost:8000/ServiceModelSamples/service.svc/mex` with the address of the self-hosted service's mex endpoint.</span></span>

     <span data-ttu-id="0c550-147">Visual Basic の型でクライアントを生成するには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="0c550-147">To generate the client in a Visual Basic type, use the following command.</span></span>

    ```console
    svcutil.exe /n:"http://Microsoft.ServiceModel.Samples,Microsoft.ServiceModel.Samples" http://localhost/servicemodelsamples/service.svc/mex /l:vb /out:generatedClient.vb
    ```

     <span data-ttu-id="0c550-148">サービスが自己ホスト型の場合は、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="0c550-148">If the service is a self-hosted type, use the following command.</span></span>

    ```console
    svcutil.exe /n:"http://Microsoft.ServiceModel.Samples,Microsoft.ServiceModel.Samples" http://localhost:8000/servicemodelsamples/service.svc/mex /l:vb /out:generatedClient.vb
    ```

    > [!NOTE]
    > <span data-ttu-id="0c550-149">クライアント構成の生成をスキップするには、 **/noConfig**オプションを追加します。</span><span class="sxs-lookup"><span data-stu-id="0c550-149">To skip the generation of client configuration add the **/noConfig** option.</span></span>

## <a name="see-also"></a><span data-ttu-id="0c550-150">関連項目</span><span class="sxs-lookup"><span data-stu-id="0c550-150">See also</span></span>

- [<span data-ttu-id="0c550-151">Windows Communication Foundation サンプルの実行</span><span class="sxs-lookup"><span data-stu-id="0c550-151">Running the Windows Communication Foundation Samples</span></span>](running-the-samples.md)
- [<span data-ttu-id="0c550-152">ServiceModel メタデータ ユーティリティ ツール (Svcutil.exe)</span><span class="sxs-lookup"><span data-stu-id="0c550-152">ServiceModel Metadata Utility Tool (Svcutil.exe)</span></span>](../servicemodel-metadata-utility-tool-svcutil-exe.md)
