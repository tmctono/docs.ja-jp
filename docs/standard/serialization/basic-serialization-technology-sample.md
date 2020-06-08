---
title: 基本的なシリアル化の技術サンプル
description: このサンプルでは、メモリ内のオブジェクト グラフをシリアル化してストリームに変換する、CLR の機能の例を示します。 このサンプルは、SoapFormatter または BinaryFormatter を使用できます。
ms.date: 03/30/2017
ms.assetid: 9d824e16-08d1-4a36-bc7f-2388c1f75f34
ms.openlocfilehash: 3f2273e6afb3a72f9734444ffe92d30871fb762b
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "84276570"
---
# <a name="basic-serialization-technology-sample"></a><span data-ttu-id="79a60-104">基本的なシリアル化の技術サンプル</span><span class="sxs-lookup"><span data-stu-id="79a60-104">Basic Serialization Technology Sample</span></span>

[<span data-ttu-id="79a60-105">サンプルのダウンロード</span><span class="sxs-lookup"><span data-stu-id="79a60-105">Download sample</span></span>](https://download.microsoft.com/download/4/7/B/47B2164C-E780-4B10-8DE4-2CB5B886E0A6/Technologies/Serialization/Runtime%20Serialization/Basic.zip.exe)

<span data-ttu-id="79a60-106">このサンプルでは、メモリ内のオブジェクト グラフをシリアル化してストリームに変換する、共通言語ランタイムの機能の例を示します。</span><span class="sxs-lookup"><span data-stu-id="79a60-106">This sample demonstrates the common language runtime's ability to serialize an object graph in memory to a stream.</span></span> <span data-ttu-id="79a60-107">このサンプルでは、<xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter> または <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> のいずれかを使用して、シリアル化を行います。</span><span class="sxs-lookup"><span data-stu-id="79a60-107">This sample can use either the <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter> or the <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> for serialization.</span></span> <span data-ttu-id="79a60-108">データを格納したリンク リストは、ファイル ストリームとの間でシリアル化または逆シリアル化されます。</span><span class="sxs-lookup"><span data-stu-id="79a60-108">A linked list, filled with data, is serialized or deserialized to or from a file stream.</span></span> <span data-ttu-id="79a60-109">いずれの場合でも、リストが表示されるので、結果を参照できます。</span><span class="sxs-lookup"><span data-stu-id="79a60-109">In either case the list is displayed so that you can see the results.</span></span> <span data-ttu-id="79a60-110">このリンク リストは `LinkedList` の一種で、このサンプルで定義してある型です。</span><span class="sxs-lookup"><span data-stu-id="79a60-110">The linked list is of type `LinkedList`, a type defined by this sample.</span></span>

<span data-ttu-id="79a60-111">シリアル化の詳細については、ソース コード ファイルおよび build.proj ファイル内のコメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="79a60-111">Review comments in the source code and build.proj files for more information on serialization.</span></span>

### <a name="to-build-the-sample-using-the-command-prompt"></a><span data-ttu-id="79a60-112">コマンド プロンプトを使用してサンプルをビルドするには</span><span class="sxs-lookup"><span data-stu-id="79a60-112">To build the sample using the Command Prompt</span></span>

1. <span data-ttu-id="79a60-113">コマンド プロンプトを使用して、Technologies\Serialization\Runtime Serialization\Basic ディレクトリにある、言語固有のサブディレクトリのいずれかに移動します。</span><span class="sxs-lookup"><span data-stu-id="79a60-113">Navigate to one of the language-specific subdirectories under the Technologies\Serialization\Runtime Serialization\Basic directory, using the command prompt.</span></span>

2. <span data-ttu-id="79a60-114">選択したプログラミング言語に応じて、コマンド ラインで、「**msbuild SerializationCS.sln**」、「**msbuild SerializationJSL.sln**」、または「**msbuild SerializationVB.sln**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="79a60-114">Type **msbuild SerializationCS.sln**, **msbuild SerializationJSL.sln** or **msbuild SerializationVB.sln**, depending on your choice of programming language, at the command line.</span></span>

### <a name="to-build-the-sample-using-visual-studio"></a><span data-ttu-id="79a60-115">Visual Studio を使用してサンプルをビルドするには</span><span class="sxs-lookup"><span data-stu-id="79a60-115">To build the sample using Visual Studio</span></span>

1. <span data-ttu-id="79a60-116">エクスプローラーを開き、サンプルが格納されている、言語固有のサブディレクトリのいずれかに移動します。</span><span class="sxs-lookup"><span data-stu-id="79a60-116">Open File Explorer and navigate to one of the language-specific subdirectories for the sample.</span></span>

2. <span data-ttu-id="79a60-117">使用しているプログラミング言語に応じて、SerializationCS.sln ファイル、SerializationJSL.sln ファイル、または SerializationVB.sln ファイルのアイコンをダブルクリックして、このファイルを Visual Studio で開きます。</span><span class="sxs-lookup"><span data-stu-id="79a60-117">Double-click the icon for the SerializationCS.sln, SerializationJSL.sln or SerializationVB.sln file, depending on your choice of programming language, to open the file in Visual Studio.</span></span>

3. <span data-ttu-id="79a60-118">**[ビルド]** メニューで、 **[ソリューションのビルド]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="79a60-118">In the **Build** menu, select **Build Solution**.</span></span>

 <span data-ttu-id="79a60-119">サンプル アプリケーションは、既定の \bin サブディレクトリまたは \bin\Debug サブディレクトリにビルドされます。</span><span class="sxs-lookup"><span data-stu-id="79a60-119">The sample application will be built in the default \bin or \bin\Debug subdirectory.</span></span>

### <a name="to-run-the-sample"></a><span data-ttu-id="79a60-120">サンプルを実行するには</span><span class="sxs-lookup"><span data-stu-id="79a60-120">To run the sample</span></span>

1. <span data-ttu-id="79a60-121">ビルドした実行可能ファイルが格納されているディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="79a60-121">Navigate to the directory containing the built executable.</span></span>

2. <span data-ttu-id="79a60-122">コマンド ラインで、「**Serialization.exe**」と入力し、任意のパラメーター値を指定します。</span><span class="sxs-lookup"><span data-stu-id="79a60-122">Type **Serialization.exe**, along with the parameter values you desire, at the command line.</span></span>

  > [!NOTE]
  > <span data-ttu-id="79a60-123">このサンプルでは、コンソール アプリケーションをビルドします。</span><span class="sxs-lookup"><span data-stu-id="79a60-123">This sample builds a console application.</span></span> <span data-ttu-id="79a60-124">出力を表示するには、コマンド プロンプトでこれを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="79a60-124">You must launch it using the command prompt in order to view its output.</span></span>

## <a name="remarks"></a><span data-ttu-id="79a60-125">Remarks</span><span class="sxs-lookup"><span data-stu-id="79a60-125">Remarks</span></span>

<span data-ttu-id="79a60-126">このサンプル アプリケーションは、実行するテストを示すコマンド ライン パラメーターを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="79a60-126">The sample application accepts command line parameters indicating which test you would like to execute.</span></span> <span data-ttu-id="79a60-127">SOAP フォーマッタを使用して、ノード数 10 個のリストを **Test.xml** というファイルにシリアル化するには、**sx Test.xml 10** というパラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="79a60-127">To serialize a 10-node list to a file named **Test.xml** using the SOAP formatter, use the parameters **sx Test.xml 10**.</span></span>

<span data-ttu-id="79a60-128">たとえば、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="79a60-128">For Example:</span></span>

```console
Serialize.exe -sx Test.xml 10
```

<span data-ttu-id="79a60-129">前述の例の **Test.xml** ファイルを逆シリアル化するには、**dx Test.xml** というパラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="79a60-129">To deserialize the **Test.xml** file from the previous example, use the parameters **dx Test.xml**.</span></span>

<span data-ttu-id="79a60-130">たとえば、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="79a60-130">For Example:</span></span>

```console
Serialize.exe -dx Test.xml
```

<span data-ttu-id="79a60-131">上の 2 つの例で、コマンド ライン スイッチに指定した "x" は、XML SOAP シリアル化を行うことを示しています。</span><span class="sxs-lookup"><span data-stu-id="79a60-131">In the two examples above, the "x" in the command line switch indicates that you want XML SOAP serialization.</span></span> <span data-ttu-id="79a60-132">バイナリ シリアル化を使用するには、代わりに "b" を使用します。</span><span class="sxs-lookup"><span data-stu-id="79a60-132">You can use "b" in its place to use binary serialization.</span></span> <span data-ttu-id="79a60-133">ノード数が非常に多いデータをシリアル化する場合は、コンソール出力をファイルにリダイレクトすると便利です。</span><span class="sxs-lookup"><span data-stu-id="79a60-133">If you wish to try serialization with a very large number of nodes, you might want to redirect the console output to a file.</span></span>

<span data-ttu-id="79a60-134">たとえば、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="79a60-134">For Example:</span></span>

```console
Serialize.exe -sb Test.bin 10000 >somefile.txt
```

<span data-ttu-id="79a60-135">このサンプルで使用するクラスと技術についての簡単な説明を、以下に箇条書きします。</span><span class="sxs-lookup"><span data-stu-id="79a60-135">The following bullets briefly describe the classes and technologies used by this sample.</span></span>

- <span data-ttu-id="79a60-136">ランタイム シリアル化</span><span class="sxs-lookup"><span data-stu-id="79a60-136">Runtime Serialization</span></span>

  - <span data-ttu-id="79a60-137"><xref:System.Runtime.Serialization.IFormatter> <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> または <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter> オブジェクトを参照するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="79a60-137"><xref:System.Runtime.Serialization.IFormatter> Used to refer to either a <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> or a <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter> object.</span></span>

  - <span data-ttu-id="79a60-138"><xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> リンク リストをバイナリ形式でストリームにシリアル化するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="79a60-138"><xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> Used to serialize a linked list to a stream in a binary format.</span></span> <span data-ttu-id="79a60-139">バイナリ フォーマッタでは、<xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> 型でのみ理解できる形式を使用します。</span><span class="sxs-lookup"><span data-stu-id="79a60-139">The binary formatter uses a format that only the <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> type understands.</span></span> <span data-ttu-id="79a60-140">ただし、データは簡潔です。</span><span class="sxs-lookup"><span data-stu-id="79a60-140">However, the data is concise.</span></span>

  - <span data-ttu-id="79a60-141"><xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter> リンク リストを SOAP 形式のストリームにシリアル化するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="79a60-141"><xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter> Used to serialize a linked list to a stream in the SOAP format.</span></span> <span data-ttu-id="79a60-142">SOAP は標準の形式です。</span><span class="sxs-lookup"><span data-stu-id="79a60-142">SOAP is a standard format.</span></span>

- <span data-ttu-id="79a60-143">ストリーム入出力</span><span class="sxs-lookup"><span data-stu-id="79a60-143">Stream I/O</span></span>

  - <span data-ttu-id="79a60-144"><xref:System.IO.Stream> は、シリアル化および逆シリアル化に使用します。</span><span class="sxs-lookup"><span data-stu-id="79a60-144"><xref:System.IO.Stream> Used to serialize and deserialize.</span></span> <span data-ttu-id="79a60-145">このサンプルで使用する特有のストリーム型として、<xref:System.IO.FileStream> 型があります。</span><span class="sxs-lookup"><span data-stu-id="79a60-145">The specific stream type used in this sample is the <xref:System.IO.FileStream> type.</span></span> <span data-ttu-id="79a60-146">ただし、シリアル化は、<xref:System.IO.Stream> から派生する任意の型で行うことができます。</span><span class="sxs-lookup"><span data-stu-id="79a60-146">However, serialization can be used with any type derived from <xref:System.IO.Stream>.</span></span>

  - <span data-ttu-id="79a60-147"><xref:System.IO.File> は、ディスク上のファイルを読み込み、作成するための <xref:System.IO.FileStream> オブジェクトを作成するために使用します。</span><span class="sxs-lookup"><span data-stu-id="79a60-147"><xref:System.IO.File> Used to create <xref:System.IO.FileStream> objects for reading and creating files on disk.</span></span>

  - <span data-ttu-id="79a60-148"><xref:System.IO.FileStream> は、リンク リストのシリアル化および逆シリアル化に使用します。</span><span class="sxs-lookup"><span data-stu-id="79a60-148"><xref:System.IO.FileStream> Used to serialize and deserialize linked lists.</span></span>

## <a name="see-also"></a><span data-ttu-id="79a60-149">関連項目</span><span class="sxs-lookup"><span data-stu-id="79a60-149">See also</span></span>

- <xref:System.IO>
- <xref:System.IO.File>
- <xref:System.IO.FileStream>
- <xref:System.IO.Stream>
- <xref:System.Random>
- <xref:System.Runtime.Serialization>
- <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>
- <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter>
- <xref:System.Runtime.Serialization.IFormatter>
- <xref:System.SerializableAttribute>
- <xref:System.Xml.Serialization>
- [<span data-ttu-id="79a60-150">基本的なシリアル化</span><span class="sxs-lookup"><span data-stu-id="79a60-150">Basic Serialization</span></span>](basic-serialization.md)
- [<span data-ttu-id="79a60-151">バイナリ シリアル化</span><span class="sxs-lookup"><span data-stu-id="79a60-151">Binary Serialization</span></span>](binary-serialization.md)
- [<span data-ttu-id="79a60-152">属性を使用した XML シリアル化の制御</span><span class="sxs-lookup"><span data-stu-id="79a60-152">Controlling XML Serialization Using Attributes</span></span>](controlling-xml-serialization-using-attributes.md)
- [<span data-ttu-id="79a60-153">XML シリアル化の概要</span><span class="sxs-lookup"><span data-stu-id="79a60-153">Introducing XML Serialization</span></span>](introducing-xml-serialization.md)
- [<span data-ttu-id="79a60-154">シリアル化</span><span class="sxs-lookup"><span data-stu-id="79a60-154">Serialization</span></span>](index.md)
- [<span data-ttu-id="79a60-155">XML シリアル化および SOAP シリアル化</span><span class="sxs-lookup"><span data-stu-id="79a60-155">XML and SOAP Serialization</span></span>](xml-and-soap-serialization.md)
