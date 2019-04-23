---
title: '方法: XmlSerializer を使用する WCF クライアント アプリケーションの起動時間を短縮する'
ms.date: 03/30/2017
ms.assetid: 21093451-0bc3-4b1a-9a9d-05f7f71fa7d0
ms.openlocfilehash: b6f010cb5edc3111f05c78f5d27cf178bd501ef9
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59326425"
---
# <a name="how-to-improve-the-startup-time-of-wcf-client-applications-using-the-xmlserializer"></a><span data-ttu-id="ec61f-102">方法: XmlSerializer を使用する WCF クライアント アプリケーションの起動時間を短縮する</span><span class="sxs-lookup"><span data-stu-id="ec61f-102">How to: Improve the Startup Time of WCF Client Applications using the XmlSerializer</span></span>
<span data-ttu-id="ec61f-103"><xref:System.Xml.Serialization.XmlSerializer> を使用してシリアル化できるデータ型を使用するサービスおよびクライアント アプリケーションは、実行時にこのようなデータ型のシリアル化コードを生成およびコンパイルします。このため、起動時のパフォーマンスが低下することがあります。</span><span class="sxs-lookup"><span data-stu-id="ec61f-103">Services and client applications that use data types that are serializable using the <xref:System.Xml.Serialization.XmlSerializer> generate and compile serialization code for those data types at runtime, which can result in slow start-up performance.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ec61f-104">事前生成済みシリアル化コードはクライアント アプリケーションでのみ使用できます。サービスでは使用できません。</span><span class="sxs-lookup"><span data-stu-id="ec61f-104">Pre-generated serialization code can only be used in client applications and not in services.</span></span>  
  
 <span data-ttu-id="ec61f-105">[ServiceModel メタデータ ユーティリティ ツール (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)アプリケーションのコンパイル済みアセンブリから必要なシリアル化コードを生成することによって、これらのアプリケーションの起動時のパフォーマンスを向上させることができます。</span><span class="sxs-lookup"><span data-stu-id="ec61f-105">The [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) can improve start-up performance for these applications by generating the necessary serialization code from the compiled assemblies for the application.</span></span> <span data-ttu-id="ec61f-106">Svcutil.exe は、<xref:System.Xml.Serialization.XmlSerializer> を使用してシリアル化できるコンパイル済みアプリケーション アセンブリに格納されたサービス コントラクトで使用されるすべてのデータ型に対して、シリアル化コードを生成します。</span><span class="sxs-lookup"><span data-stu-id="ec61f-106">Svcutil.exe generates serialization code for all data types used in service contracts in the compiled application assembly that can be serialized using the <xref:System.Xml.Serialization.XmlSerializer>.</span></span> <span data-ttu-id="ec61f-107"><xref:System.Xml.Serialization.XmlSerializer> を使用するサービスおよび操作コントラクトは、<xref:System.ServiceModel.XmlSerializerFormatAttribute> でマークされます。</span><span class="sxs-lookup"><span data-stu-id="ec61f-107">Service and operation contracts that use the <xref:System.Xml.Serialization.XmlSerializer> are marked with the <xref:System.ServiceModel.XmlSerializerFormatAttribute>.</span></span>  
  
### <a name="to-generate-xmlserializer-serialization-code"></a><span data-ttu-id="ec61f-108">XmlSerializer シリアル化コードを生成するには</span><span class="sxs-lookup"><span data-stu-id="ec61f-108">To generate XmlSerializer serialization code</span></span>  
  
1. <span data-ttu-id="ec61f-109">サービスまたはクライアント コードを 1 つ以上のアセンブリにコンパイルします。</span><span class="sxs-lookup"><span data-stu-id="ec61f-109">Compile your service or client code into one or more assemblies.</span></span>  
  
2. <span data-ttu-id="ec61f-110">SDK コマンド プロンプトを開きます。</span><span class="sxs-lookup"><span data-stu-id="ec61f-110">Open an SDK command prompt.</span></span>  
  
3. <span data-ttu-id="ec61f-111">コマンド プロンプトで、次の形式を使用して Svcutil.exe ツールを起動します。</span><span class="sxs-lookup"><span data-stu-id="ec61f-111">At the command prompt, launch the Svcutil.exe tool using the following format.</span></span>  
  
    ```  
    svcutil.exe /t:xmlSerializer  <assemblyPath>*  
    ```  
  
     <span data-ttu-id="ec61f-112">`assemblyPath` 引数には、サービス コントラクト型を格納するアセンブリへのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="ec61f-112">The `assemblyPath` argument specifies the path to an assembly that contains service contract types.</span></span> <span data-ttu-id="ec61f-113">Svcutil.exe は、<xref:System.Xml.Serialization.XmlSerializer> を使用してシリアル化できるコンパイル済みアプリケーション アセンブリに格納されたサービス コントラクトで使用されるすべてのデータ型に対して、シリアル化コードを生成します。</span><span class="sxs-lookup"><span data-stu-id="ec61f-113">Svcutil.exe generates serialization code for all data types used in service contracts in the compiled application assembly that can be serialized using the <xref:System.Xml.Serialization.XmlSerializer>.</span></span>  
  
     <span data-ttu-id="ec61f-114">Svcutil.exe は、C# のシリアル化コードのみを生成できます。</span><span class="sxs-lookup"><span data-stu-id="ec61f-114">Svcutil.exe can only generate C# serialization code.</span></span> <span data-ttu-id="ec61f-115">入力アセンブリごとに、1 つのソース コード ファイルが生成されます。</span><span class="sxs-lookup"><span data-stu-id="ec61f-115">One source code file is generated for each input assembly.</span></span> <span data-ttu-id="ec61f-116">使用することはできません、 **/language**スイッチを生成されたコードの言語を変更します。</span><span class="sxs-lookup"><span data-stu-id="ec61f-116">You cannot use the **/language** switch to change the language of the generated code.</span></span>  
  
     <span data-ttu-id="ec61f-117">依存アセンブリへのパスを指定するには、使用、 **/reference**オプション。</span><span class="sxs-lookup"><span data-stu-id="ec61f-117">To specify the path to dependent assemblies, use the **/reference** option.</span></span>  
  
4. <span data-ttu-id="ec61f-118">次のオプションのいずれかを使用して、生成したシリアル化コードをアプリケーションから利用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="ec61f-118">Make the generated serialization code available to your application by using one of the following options:</span></span>  
  
    1.  <span data-ttu-id="ec61f-119">名前の別のアセンブリに生成されたシリアル化コードをコンパイル [*元のアセンブリ*]。XmlSerializers.dll (たとえば、MyApp.XmlSerializers.dll)。</span><span class="sxs-lookup"><span data-stu-id="ec61f-119">Compile the generated serialization code into a separate assembly with the name [*original assembly*].XmlSerializers.dll (for example, MyApp.XmlSerializers.dll).</span></span> <span data-ttu-id="ec61f-120">アプリケーションがアセンブリを読み込むことができ、アセンブリが元のアセンブリと同じキーで署名されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="ec61f-120">Your application must be able to load the assembly, which must be signed with the same key as the original assembly.</span></span> <span data-ttu-id="ec61f-121">元のアセンブリを再コンパイルする場合は、シリアル化アセンブリも再生成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ec61f-121">If you recompile the original assembly, you must regenerate the serialization assembly.</span></span>  
  
    2.  <span data-ttu-id="ec61f-122">生成されたシリアル化コードを別個のアセンブリにコンパイルし、<xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute> を使用するサービス コントラクトで <xref:System.ServiceModel.XmlSerializerFormatAttribute> を使用します。</span><span class="sxs-lookup"><span data-stu-id="ec61f-122">Compile the generated serialization code into a separate assembly and use the <xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute> on the service contract that uses the <xref:System.ServiceModel.XmlSerializerFormatAttribute>.</span></span> <span data-ttu-id="ec61f-123"><xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute.AssemblyName%2A> プロパティまたは <xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute.CodeBase%2A> プロパティが、コンパイル済みのシリアル化アセンブリを指すように設定します。</span><span class="sxs-lookup"><span data-stu-id="ec61f-123">Set the <xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute.AssemblyName%2A> or <xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute.CodeBase%2A> properties to point to the compiled serialization assembly.</span></span>  
  
    3.  <span data-ttu-id="ec61f-124">生成されたシリアル化コードをアプリケーション アセンブリにコンパイルし、<xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute> を使用するサービス コントラクトに <xref:System.ServiceModel.XmlSerializerFormatAttribute> を追加します。</span><span class="sxs-lookup"><span data-stu-id="ec61f-124">Compile the generated serialization code into your application assembly and add the <xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute> to the service contract that uses the <xref:System.ServiceModel.XmlSerializerFormatAttribute>.</span></span> <span data-ttu-id="ec61f-125"><xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute.AssemblyName%2A> プロパティおよび <xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute.CodeBase%2A> プロパティは設定しないでください。</span><span class="sxs-lookup"><span data-stu-id="ec61f-125">Do not set the <xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute.AssemblyName%2A> or <xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute.CodeBase%2A> properties.</span></span> <span data-ttu-id="ec61f-126">既定のシリアル化アセンブリが現在のアセンブリであると見なされます。</span><span class="sxs-lookup"><span data-stu-id="ec61f-126">The default serialization assembly is assumed to be the current assembly.</span></span>  
  
### <a name="to-generate-xmlserializer-serialization-code-in-visual-studio"></a><span data-ttu-id="ec61f-127">Visual Studio で XmlSerializer シリアル化コードを生成するには</span><span class="sxs-lookup"><span data-stu-id="ec61f-127">To generate XmlSerializer serialization code in Visual Studio</span></span>  
  
1. <span data-ttu-id="ec61f-128">Visual Studio で WCF サービスとクライアント プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="ec61f-128">Create the WCF service and client projects in Visual Studio.</span></span> <span data-ttu-id="ec61f-129">次に、クライアント プロジェクトにサービス参照を追加します。</span><span class="sxs-lookup"><span data-stu-id="ec61f-129">Then, add a service reference to the client project.</span></span>  
  
2. <span data-ttu-id="ec61f-130">追加、<xref:System.ServiceModel.XmlSerializerFormatAttribute>でサービス コントラクトに、 *reference.cs*ファイルでクライアント アプリ プロジェクトで**serviceReference** -> **reference.svcmap**.</span><span class="sxs-lookup"><span data-stu-id="ec61f-130">Add an <xref:System.ServiceModel.XmlSerializerFormatAttribute> to the service contract in the *reference.cs* file in the client app project under **serviceReference** -> **reference.svcmap**.</span></span> <span data-ttu-id="ec61f-131">すべてのファイルを表示する必要がありますに注意してください。**ソリューション エクスプ ローラー**にこれらのファイルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ec61f-131">Note that you need to show all files in **Solution Explorer** to see these files.</span></span>  
  
3. <span data-ttu-id="ec61f-132">クライアント アプリをビルドします。</span><span class="sxs-lookup"><span data-stu-id="ec61f-132">Build the client app.</span></span>  
  
4. <span data-ttu-id="ec61f-133">使用して、 [ServiceModel メタデータ ユーティリティ ツール (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)事前生成されたシリアライザーを作成する *.cs*コマンドを使用してファイル。</span><span class="sxs-lookup"><span data-stu-id="ec61f-133">Use the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) to create a pre-generated serializer *.cs* file by using the command:</span></span>  
  
    ```  
    svcutil.exe /t:xmlSerializer  <assemblyPath>*  
    ```  
  
     <span data-ttu-id="ec61f-134">AssemblyPath 引数には、WCF クライアント アセンブリへのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="ec61f-134">The assemblyPath argument specifies the path to the WCF client assembly.</span></span>  
  
     <span data-ttu-id="ec61f-135">例:</span><span class="sxs-lookup"><span data-stu-id="ec61f-135">Such as:</span></span>  
  
    ```  
    svcutil.exe /t:xmlSerializer wcfclient.exe  
    ```  
  
     <span data-ttu-id="ec61f-136">*WCFClient.XmlSerializers.dll.cs*ファイルが生成されます。</span><span class="sxs-lookup"><span data-stu-id="ec61f-136">The *WCFClient.XmlSerializers.dll.cs* file will be generated.</span></span>  
  
5. <span data-ttu-id="ec61f-137">生成済みシリアル化アセンブリをコンパイルします。</span><span class="sxs-lookup"><span data-stu-id="ec61f-137">Compile the pre-generated serialization assembly.</span></span>  
  
     <span data-ttu-id="ec61f-138">前の手順の例に基づいて、コンパイルのコマンドは、次のようになります</span><span class="sxs-lookup"><span data-stu-id="ec61f-138">Based on the example in the previous step, the compile command would be the following:</span></span>  
  
    ```  
    csc /r:wcfclient.exe /out:WCFClient.XmlSerializers.dll /t:library WCFClient.XmlSerializers.dll.cs  
    ```  
  
     <span data-ttu-id="ec61f-139">必ず、生成された*WCFClient.XmlSerializers.dll*はクライアント アプリと同じディレクトリに*WCFClient.exe*ここでします。</span><span class="sxs-lookup"><span data-stu-id="ec61f-139">Make sure the generated *WCFClient.XmlSerializers.dll* is in the same directory as the client app, which is *WCFClient.exe* in this case.</span></span>  
  
6. <span data-ttu-id="ec61f-140">クライアント アプリを通常どおり実行します。</span><span class="sxs-lookup"><span data-stu-id="ec61f-140">Run the client app as usual.</span></span> <span data-ttu-id="ec61f-141">生成済みシリアル化アセンブリが使用されます。</span><span class="sxs-lookup"><span data-stu-id="ec61f-141">The pre-generated serialization assembly will be used.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ec61f-142">例</span><span class="sxs-lookup"><span data-stu-id="ec61f-142">Example</span></span>  
 <span data-ttu-id="ec61f-143">次のコマンドにより、アセンブリに含まれているサービス コントラクトが使用する `XmlSerializer` 型用のシリアル化型を生成します。</span><span class="sxs-lookup"><span data-stu-id="ec61f-143">The following command generates serialization types for `XmlSerializer` types that any service contracts in the assembly use.</span></span>  
  
```  
svcutil /t:xmlserializer myContractLibrary.exe  
```  
  
## <a name="see-also"></a><span data-ttu-id="ec61f-144">関連項目</span><span class="sxs-lookup"><span data-stu-id="ec61f-144">See also</span></span>

- [<span data-ttu-id="ec61f-145">ServiceModel メタデータ ユーティリティ ツール (Svcutil.exe)</span><span class="sxs-lookup"><span data-stu-id="ec61f-145">ServiceModel Metadata Utility Tool (Svcutil.exe)</span></span>](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)
