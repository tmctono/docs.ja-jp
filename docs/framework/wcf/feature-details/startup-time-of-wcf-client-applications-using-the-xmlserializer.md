---
title: '方法 : XmlSerializer を使用する WCF クライアント アプリケーションの起動時間を短縮する'
ms.date: 03/30/2017
ms.assetid: 21093451-0bc3-4b1a-9a9d-05f7f71fa7d0
ms.openlocfilehash: ca15d710a30586135f0d030e155b09b63a22ee45
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/12/2019
ms.locfileid: "73976065"
---
# <a name="how-to-improve-the-startup-time-of-wcf-client-applications-using-the-xmlserializer"></a><span data-ttu-id="86d82-102">方法 : XmlSerializer を使用する WCF クライアント アプリケーションの起動時間を短縮する</span><span class="sxs-lookup"><span data-stu-id="86d82-102">How to: Improve the Startup Time of WCF Client Applications using the XmlSerializer</span></span>
<span data-ttu-id="86d82-103"><xref:System.Xml.Serialization.XmlSerializer> を使用してシリアル化できるデータ型を使用するサービスおよびクライアント アプリケーションは、実行時にこのようなデータ型のシリアル化コードを生成およびコンパイルします。このため、起動時のパフォーマンスが低下することがあります。</span><span class="sxs-lookup"><span data-stu-id="86d82-103">Services and client applications that use data types that are serializable using the <xref:System.Xml.Serialization.XmlSerializer> generate and compile serialization code for those data types at runtime, which can result in slow start-up performance.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="86d82-104">事前生成済みシリアル化コードはクライアント アプリケーションでのみ使用できます。サービスでは使用できません。</span><span class="sxs-lookup"><span data-stu-id="86d82-104">Pre-generated serialization code can only be used in client applications and not in services.</span></span>  
  
 <span data-ttu-id="86d82-105">[ServiceModel メタデータユーティリティツール (svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)を使用すると、アプリケーションのコンパイル済みアセンブリから必要なシリアル化コードを生成することで、これらのアプリケーションの起動時のパフォーマンスを向上させることができます。</span><span class="sxs-lookup"><span data-stu-id="86d82-105">The [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) can improve start-up performance for these applications by generating the necessary serialization code from the compiled assemblies for the application.</span></span> <span data-ttu-id="86d82-106">Svcutil.exe は、<xref:System.Xml.Serialization.XmlSerializer> を使用してシリアル化できるコンパイル済みアプリケーション アセンブリに格納されたサービス コントラクトで使用されるすべてのデータ型に対して、シリアル化コードを生成します。</span><span class="sxs-lookup"><span data-stu-id="86d82-106">Svcutil.exe generates serialization code for all data types used in service contracts in the compiled application assembly that can be serialized using the <xref:System.Xml.Serialization.XmlSerializer>.</span></span> <span data-ttu-id="86d82-107"><xref:System.Xml.Serialization.XmlSerializer> を使用するサービスおよび操作コントラクトは、<xref:System.ServiceModel.XmlSerializerFormatAttribute> でマークされます。</span><span class="sxs-lookup"><span data-stu-id="86d82-107">Service and operation contracts that use the <xref:System.Xml.Serialization.XmlSerializer> are marked with the <xref:System.ServiceModel.XmlSerializerFormatAttribute>.</span></span>  
  
### <a name="to-generate-xmlserializer-serialization-code"></a><span data-ttu-id="86d82-108">XmlSerializer シリアル化コードを生成するには</span><span class="sxs-lookup"><span data-stu-id="86d82-108">To generate XmlSerializer serialization code</span></span>  
  
1. <span data-ttu-id="86d82-109">サービスまたはクライアント コードを 1 つ以上のアセンブリにコンパイルします。</span><span class="sxs-lookup"><span data-stu-id="86d82-109">Compile your service or client code into one or more assemblies.</span></span>  
  
2. <span data-ttu-id="86d82-110">SDK コマンド プロンプトを開きます。</span><span class="sxs-lookup"><span data-stu-id="86d82-110">Open an SDK command prompt.</span></span>  
  
3. <span data-ttu-id="86d82-111">コマンド プロンプトで、次の形式を使用して Svcutil.exe ツールを起動します。</span><span class="sxs-lookup"><span data-stu-id="86d82-111">At the command prompt, launch the Svcutil.exe tool using the following format.</span></span>  
  
    ```console  
    svcutil.exe /t:xmlSerializer  <assemblyPath>*  
    ```  
  
     <span data-ttu-id="86d82-112">`assemblyPath` 引数には、サービス コントラクト型を格納するアセンブリへのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="86d82-112">The `assemblyPath` argument specifies the path to an assembly that contains service contract types.</span></span> <span data-ttu-id="86d82-113">Svcutil.exe は、<xref:System.Xml.Serialization.XmlSerializer> を使用してシリアル化できるコンパイル済みアプリケーション アセンブリに格納されたサービス コントラクトで使用されるすべてのデータ型に対して、シリアル化コードを生成します。</span><span class="sxs-lookup"><span data-stu-id="86d82-113">Svcutil.exe generates serialization code for all data types used in service contracts in the compiled application assembly that can be serialized using the <xref:System.Xml.Serialization.XmlSerializer>.</span></span>  
  
     <span data-ttu-id="86d82-114">Svcutil.exe は、C# のシリアル化コードのみを生成できます。</span><span class="sxs-lookup"><span data-stu-id="86d82-114">Svcutil.exe can only generate C# serialization code.</span></span> <span data-ttu-id="86d82-115">入力アセンブリごとに、1 つのソース コード ファイルが生成されます。</span><span class="sxs-lookup"><span data-stu-id="86d82-115">One source code file is generated for each input assembly.</span></span> <span data-ttu-id="86d82-116">**/言語**スイッチを使用して、生成されたコードの言語を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="86d82-116">You cannot use the **/language** switch to change the language of the generated code.</span></span>  
  
     <span data-ttu-id="86d82-117">依存アセンブリへのパスを指定するには、 **/reference**オプションを使用します。</span><span class="sxs-lookup"><span data-stu-id="86d82-117">To specify the path to dependent assemblies, use the **/reference** option.</span></span>  
  
4. <span data-ttu-id="86d82-118">次のオプションのいずれかを使用して、生成したシリアル化コードをアプリケーションから利用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="86d82-118">Make the generated serialization code available to your application by using one of the following options:</span></span>  
  
    1. <span data-ttu-id="86d82-119">生成されたシリアル化コードを、[*元のアセンブリ*] という名前の別のアセンブリにコンパイルします。XmlSerializers .dll (例、MyApp. XmlSerializers .dll)。</span><span class="sxs-lookup"><span data-stu-id="86d82-119">Compile the generated serialization code into a separate assembly with the name [*original assembly*].XmlSerializers.dll (for example, MyApp.XmlSerializers.dll).</span></span> <span data-ttu-id="86d82-120">アプリケーションがアセンブリを読み込むことができ、アセンブリが元のアセンブリと同じキーで署名されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="86d82-120">Your application must be able to load the assembly, which must be signed with the same key as the original assembly.</span></span> <span data-ttu-id="86d82-121">元のアセンブリを再コンパイルする場合は、シリアル化アセンブリも再生成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="86d82-121">If you recompile the original assembly, you must regenerate the serialization assembly.</span></span>  
  
    2. <span data-ttu-id="86d82-122">生成されたシリアル化コードを別個のアセンブリにコンパイルし、<xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute> を使用するサービス コントラクトで <xref:System.ServiceModel.XmlSerializerFormatAttribute> を使用します。</span><span class="sxs-lookup"><span data-stu-id="86d82-122">Compile the generated serialization code into a separate assembly and use the <xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute> on the service contract that uses the <xref:System.ServiceModel.XmlSerializerFormatAttribute>.</span></span> <span data-ttu-id="86d82-123"><xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute.AssemblyName%2A> プロパティまたは <xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute.CodeBase%2A> プロパティが、コンパイル済みのシリアル化アセンブリを指すように設定します。</span><span class="sxs-lookup"><span data-stu-id="86d82-123">Set the <xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute.AssemblyName%2A> or <xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute.CodeBase%2A> properties to point to the compiled serialization assembly.</span></span>  
  
    3. <span data-ttu-id="86d82-124">生成されたシリアル化コードをアプリケーション アセンブリにコンパイルし、<xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute> を使用するサービス コントラクトに <xref:System.ServiceModel.XmlSerializerFormatAttribute> を追加します。</span><span class="sxs-lookup"><span data-stu-id="86d82-124">Compile the generated serialization code into your application assembly and add the <xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute> to the service contract that uses the <xref:System.ServiceModel.XmlSerializerFormatAttribute>.</span></span> <span data-ttu-id="86d82-125"><xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute.AssemblyName%2A> プロパティおよび <xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute.CodeBase%2A> プロパティは設定しないでください。</span><span class="sxs-lookup"><span data-stu-id="86d82-125">Do not set the <xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute.AssemblyName%2A> or <xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute.CodeBase%2A> properties.</span></span> <span data-ttu-id="86d82-126">既定のシリアル化アセンブリが現在のアセンブリであると見なされます。</span><span class="sxs-lookup"><span data-stu-id="86d82-126">The default serialization assembly is assumed to be the current assembly.</span></span>  
  
### <a name="to-generate-xmlserializer-serialization-code-in-visual-studio"></a><span data-ttu-id="86d82-127">Visual Studio で XmlSerializer シリアル化コードを生成するには</span><span class="sxs-lookup"><span data-stu-id="86d82-127">To generate XmlSerializer serialization code in Visual Studio</span></span>  
  
1. <span data-ttu-id="86d82-128">Visual Studio で WCF サービスとクライアントプロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="86d82-128">Create the WCF service and client projects in Visual Studio.</span></span> <span data-ttu-id="86d82-129">次に、クライアントプロジェクトにサービス参照を追加します。</span><span class="sxs-lookup"><span data-stu-id="86d82-129">Then, add a service reference to the client project.</span></span>  
  
2. <span data-ttu-id="86d82-130">クライアントアプリプロジェクトの*reference.cs*ファイルにあるサービスコントラクトに <xref:System.ServiceModel.XmlSerializerFormatAttribute> を追加します。 **serviceReference**には、の下の -> を**参照し**てください。</span><span class="sxs-lookup"><span data-stu-id="86d82-130">Add an <xref:System.ServiceModel.XmlSerializerFormatAttribute> to the service contract in the *reference.cs* file in the client app project under **serviceReference** -> **reference.svcmap**.</span></span> <span data-ttu-id="86d82-131">これらのファイルを表示するには、**ソリューションエクスプローラー**内のすべてのファイルを表示する必要があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="86d82-131">Note that you need to show all files in **Solution Explorer** to see these files.</span></span>  
  
3. <span data-ttu-id="86d82-132">クライアントアプリをビルドします。</span><span class="sxs-lookup"><span data-stu-id="86d82-132">Build the client app.</span></span>  
  
4. <span data-ttu-id="86d82-133">[ServiceModel メタデータユーティリティツール (svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)を使用して、次のコマンドを使用して、事前に生成さ*れ*たシリアライザーファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="86d82-133">Use the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) to create a pre-generated serializer *.cs* file by using the command:</span></span>  
  
    ```console  
    svcutil.exe /t:xmlSerializer  <assemblyPath>*  
    ```  
  
     <span data-ttu-id="86d82-134">AssemblyPath 引数は、WCF クライアントアセンブリへのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="86d82-134">The assemblyPath argument specifies the path to the WCF client assembly.</span></span>  
  
     <span data-ttu-id="86d82-135">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="86d82-135">Such as:</span></span>  
  
    ```console  
    svcutil.exe /t:xmlSerializer wcfclient.exe  
    ```  
  
     <span data-ttu-id="86d82-136">*WCFClient.XmlSerializers.dll.cs*ファイルが生成されます。</span><span class="sxs-lookup"><span data-stu-id="86d82-136">The *WCFClient.XmlSerializers.dll.cs* file will be generated.</span></span>  
  
5. <span data-ttu-id="86d82-137">事前に生成されたシリアル化アセンブリをコンパイルします。</span><span class="sxs-lookup"><span data-stu-id="86d82-137">Compile the pre-generated serialization assembly.</span></span>  
  
     <span data-ttu-id="86d82-138">前の手順の例に基づいて、compile コマンドは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="86d82-138">Based on the example in the previous step, the compile command would be the following:</span></span>  
  
    ```console  
    csc /r:wcfclient.exe /out:WCFClient.XmlSerializers.dll /t:library WCFClient.XmlSerializers.dll.cs  
    ```  
  
     <span data-ttu-id="86d82-139">生成された*WCFClient*がクライアントアプリと同じディレクトリ (この場合は*WCFClient* ) にあることを確認します。</span><span class="sxs-lookup"><span data-stu-id="86d82-139">Make sure the generated *WCFClient.XmlSerializers.dll* is in the same directory as the client app, which is *WCFClient.exe* in this case.</span></span>  
  
6. <span data-ttu-id="86d82-140">通常どおりにクライアントアプリを実行します。</span><span class="sxs-lookup"><span data-stu-id="86d82-140">Run the client app as usual.</span></span> <span data-ttu-id="86d82-141">事前に生成されたシリアル化アセンブリが使用されます。</span><span class="sxs-lookup"><span data-stu-id="86d82-141">The pre-generated serialization assembly will be used.</span></span>  
  
## <a name="example"></a><span data-ttu-id="86d82-142">例</span><span class="sxs-lookup"><span data-stu-id="86d82-142">Example</span></span>  
 <span data-ttu-id="86d82-143">次のコマンドにより、アセンブリに含まれているサービス コントラクトが使用する `XmlSerializer` 型用のシリアル化型を生成します。</span><span class="sxs-lookup"><span data-stu-id="86d82-143">The following command generates serialization types for `XmlSerializer` types that any service contracts in the assembly use.</span></span>  
  
```console  
svcutil /t:xmlserializer myContractLibrary.exe  
```  
  
## <a name="see-also"></a><span data-ttu-id="86d82-144">関連項目</span><span class="sxs-lookup"><span data-stu-id="86d82-144">See also</span></span>

- [<span data-ttu-id="86d82-145">ServiceModel メタデータ ユーティリティ ツール (Svcutil.exe)</span><span class="sxs-lookup"><span data-stu-id="86d82-145">ServiceModel Metadata Utility Tool (Svcutil.exe)</span></span>](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)
