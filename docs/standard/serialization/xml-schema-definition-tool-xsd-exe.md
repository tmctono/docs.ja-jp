---
title: XML Schema Definition Tool (Xsd.exe)
ms.date: 03/30/2017
ms.assetid: a6e6e65c-347f-4494-9457-653bf29baac2
ms.openlocfilehash: 6ec99e77db4215184547ea2bbbe0d1ff8ad3c286
ms.sourcegitcommit: c91110ef6ee3fedb591f3d628dc17739c4a7071e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/15/2020
ms.locfileid: "81389771"
---
# <a name="xml-schema-definition-tool-xsdexe"></a><span data-ttu-id="d6987-102">XML Schema Definition Tool (Xsd.exe)</span><span class="sxs-lookup"><span data-stu-id="d6987-102">XML Schema Definition Tool (Xsd.exe)</span></span>

<span data-ttu-id="d6987-103">XML スキーマ定義ツール (Xsd.exe) は、XDR、XML、および XSD ファイル、またはランタイム アセンブリ内のクラスから XML スキーマ クラスまたは共通言語ランタイム クラスを生成します。</span><span class="sxs-lookup"><span data-stu-id="d6987-103">The XML Schema Definition (Xsd.exe) tool generates XML schema or common language runtime classes from XDR, XML, and XSD files, or from classes in a runtime assembly.</span></span>

<span data-ttu-id="d6987-104">XML スキーマ定義ツール (Xsd.exe) は、通常、次のパスにあります。</span><span class="sxs-lookup"><span data-stu-id="d6987-104">The XML Schema Definition tool (Xsd.exe) usually can be found in the following path:\</span></span>
<span data-ttu-id="d6987-105">_C:\\プログラム\\ファイル (x86)\\マイクロソフト\\SDK\\ウィンドウ\\{バージョン} ビン NETFX {バージョン} ツール\\_</span><span class="sxs-lookup"><span data-stu-id="d6987-105">_C:\\Program Files (x86)\\Microsoft SDKs\\Windows\\{version}\\bin\\NETFX {version} Tools\\_</span></span>

## <a name="syntax"></a><span data-ttu-id="d6987-106">構文</span><span class="sxs-lookup"><span data-stu-id="d6987-106">Syntax</span></span>

<span data-ttu-id="d6987-107">コマンド ラインからツールを実行します。</span><span class="sxs-lookup"><span data-stu-id="d6987-107">Run the tool from the command line.</span></span>

```console
xsd file.xdr [-outputdir:directory][/parameters:file.xml]
xsd file.xml [-outputdir:directory] [/parameters:file.xml]
xsd file.xsd {/classes | /dataset} [/element:element]
             [/enableLinqDataSet] [/language:language]
                          [/namespace:namespace] [-outputdir:directory] [URI:uri]
                          [/parameters:file.xml]
xsd {file.dll | file.exe} [-outputdir:directory] [/type:typename [...]][/parameters:file.xml]
```
  
> [!TIP]
> <span data-ttu-id="d6987-108">NET Framework ツールが正しく機能するには、 、`Path``Include`および 環境変数`Lib`を正しく設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d6987-108">For .NET Framework tools to function properly, you must set your `Path`, `Include`, and `Lib` environment variables correctly.</span></span> <span data-ttu-id="d6987-109">これらの環境変数を設定するには、\<SDK>\v2.0\Bin ディレクトリにある SDKVars.bat を実行します。</span><span class="sxs-lookup"><span data-stu-id="d6987-109">Set these environment variables by running SDKVars.bat, which is located in the \<SDK>\v2.0\Bin directory.</span></span> <span data-ttu-id="d6987-110">SDKVars.bat は、コマンド シェルごとに実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d6987-110">SDKVars.bat must be executed in every command shell.</span></span>

## <a name="argument"></a><span data-ttu-id="d6987-111">引数</span><span class="sxs-lookup"><span data-stu-id="d6987-111">Argument</span></span>

|<span data-ttu-id="d6987-112">引数</span><span class="sxs-lookup"><span data-stu-id="d6987-112">Argument</span></span>|<span data-ttu-id="d6987-113">説明</span><span class="sxs-lookup"><span data-stu-id="d6987-113">Description</span></span>|
|--------------|-----------------|
|<span data-ttu-id="d6987-114">*ファイル拡張子*</span><span class="sxs-lookup"><span data-stu-id="d6987-114">*file.extension*</span></span>|<span data-ttu-id="d6987-115">変換元の入力ファイルを指定します。</span><span class="sxs-lookup"><span data-stu-id="d6987-115">Specifies the input file to convert.</span></span> <span data-ttu-id="d6987-116">拡張子は、.xdr、.xml、.xsd、.dll、または .exe のいずれかとして指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d6987-116">You must specify the extension as one of the following: .xdr, .xml, .xsd, .dll, or .exe.</span></span><br /><br /> <span data-ttu-id="d6987-117">XDR スキーマ ファイル (拡張子 .xdr) を指定すると、Xsd.exe は XDR スキーマを XSD スキーマに変換します。</span><span class="sxs-lookup"><span data-stu-id="d6987-117">If you specify an XDR schema file (.xdr extension), Xsd.exe converts the XDR schema to an XSD schema.</span></span> <span data-ttu-id="d6987-118">出力ファイルの名前は XDR スキーマと同じですが、拡張子は .xsd となります。</span><span class="sxs-lookup"><span data-stu-id="d6987-118">The output file has the same name as the XDR schema, but with the .xsd extension.</span></span><br /><br /> <span data-ttu-id="d6987-119">XML ファイル (拡張子 .xml) を指定すると、Xsd.exe はそのファイル内のデータからスキーマを推測して XSD スキーマを生成します。</span><span class="sxs-lookup"><span data-stu-id="d6987-119">If you specify an XML file (.xml extension), Xsd.exe infers a schema from the data in the file and produces an XSD schema.</span></span> <span data-ttu-id="d6987-120">出力ファイルの名前は XML ファイルと同じですが、拡張子は .xsd となります。</span><span class="sxs-lookup"><span data-stu-id="d6987-120">The output file has the same name as the XML file, but with the .xsd extension.</span></span><br /><br /> <span data-ttu-id="d6987-121">XML スキーマ ファイル (拡張子 .xsd) を指定すると、XML スキーマと対応するランタイム オブジェクト用のソース コードが生成されます。</span><span class="sxs-lookup"><span data-stu-id="d6987-121">If you specify an XML schema file (.xsd extension), Xsd.exe generates source code for runtime objects that correspond to the XML schema.</span></span><br /><br /> <span data-ttu-id="d6987-122">ランタイム アセンブリ ファイル (拡張子 .exe または .dll) を指定すると、そのアセンブリに含まれる 1 つ以上の型用のスキーマが生成されます。</span><span class="sxs-lookup"><span data-stu-id="d6987-122">If you specify a runtime assembly file (.exe or .dll extension), Xsd.exe generates schemas for one or more types in that assembly.</span></span> <span data-ttu-id="d6987-123">`/type` オプションを使用して、スキーマを生成する対象の型を指定できます。</span><span class="sxs-lookup"><span data-stu-id="d6987-123">You can use the `/type` option to specify the types for which to generate schemas.</span></span> <span data-ttu-id="d6987-124">出力スキーマには、schema0.xsd、schema1.xsd などの名前が付けられます。</span><span class="sxs-lookup"><span data-stu-id="d6987-124">The output schemas are named schema0.xsd, schema1.xsd, and so on.</span></span> <span data-ttu-id="d6987-125">Xsd.exe が複数のスキーマを生成するのは、指定した型によって、カスタム属性 `XMLRoot` を使用する名前空間が特定される場合のみです。</span><span class="sxs-lookup"><span data-stu-id="d6987-125">Xsd.exe produces multiple schemas only if the given types specify a namespace using the `XMLRoot` custom attribute.</span></span>|

## <a name="general-options"></a><span data-ttu-id="d6987-126">[全般] のオプション</span><span class="sxs-lookup"><span data-stu-id="d6987-126">General Options</span></span>

|<span data-ttu-id="d6987-127">オプション</span><span class="sxs-lookup"><span data-stu-id="d6987-127">Option</span></span>|<span data-ttu-id="d6987-128">説明</span><span class="sxs-lookup"><span data-stu-id="d6987-128">Description</span></span>|
|------------|-----------------|
|<span data-ttu-id="d6987-129">**/h\[エルプ\]**</span><span class="sxs-lookup"><span data-stu-id="d6987-129">**/h\[elp\]**</span></span>|<span data-ttu-id="d6987-130">このツールのコマンド構文とオプションを表示します。</span><span class="sxs-lookup"><span data-stu-id="d6987-130">Displays command syntax and options for the tool.</span></span>|
|<span data-ttu-id="d6987-131">**/o\[ウット\]プディル :**_ディレクトリ_</span><span class="sxs-lookup"><span data-stu-id="d6987-131">**/o\[utputdir\]:**_directory_</span></span>|<span data-ttu-id="d6987-132">出力ファイル用のディレクトリを指定します。</span><span class="sxs-lookup"><span data-stu-id="d6987-132">Specifies the directory for output files.</span></span> <span data-ttu-id="d6987-133">この引数は 1 回だけ指定できます。</span><span class="sxs-lookup"><span data-stu-id="d6987-133">This argument can appear only once.</span></span> <span data-ttu-id="d6987-134">既定値は現在のディレクトリです。</span><span class="sxs-lookup"><span data-stu-id="d6987-134">The default is the current directory.</span></span>|
|<span data-ttu-id="d6987-135">**/?**</span><span class="sxs-lookup"><span data-stu-id="d6987-135">**/?**</span></span>|<span data-ttu-id="d6987-136">このツールのコマンド構文とオプションを表示します。</span><span class="sxs-lookup"><span data-stu-id="d6987-136">Displays command syntax and options for the tool.</span></span>|
|<span data-ttu-id="d6987-137">**/p\[アラ\]メーター :**_ファイル.xml_</span><span class="sxs-lookup"><span data-stu-id="d6987-137">**/p\[arameters\]:**_file.xml_</span></span>|<span data-ttu-id="d6987-138">指定された .xml ファイルから各種のオペレーション モードのためのオプションを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="d6987-138">Read options for various operation modes from the specified .xml file.</span></span> <span data-ttu-id="d6987-139">短縮形は `/p:` です。</span><span class="sxs-lookup"><span data-stu-id="d6987-139">The short form is `/p:`.</span></span> <span data-ttu-id="d6987-140">詳細については、「[解説」](#remarks)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d6987-140">For more information, see the [Remarks](#remarks) section.</span></span>|

## <a name="xsd-file-options"></a><span data-ttu-id="d6987-141">XSD ファイルのオプション</span><span class="sxs-lookup"><span data-stu-id="d6987-141">XSD File Options</span></span>
 <span data-ttu-id="d6987-142">.xsd ファイルについては、次のオプションのうち 1 つだけを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d6987-142">You must specify only one of the following options for .xsd files.</span></span>

|<span data-ttu-id="d6987-143">オプション</span><span class="sxs-lookup"><span data-stu-id="d6987-143">Option</span></span>|<span data-ttu-id="d6987-144">説明</span><span class="sxs-lookup"><span data-stu-id="d6987-144">Description</span></span>|
|------------|-----------------|
|<span data-ttu-id="d6987-145">**/c\[ラッセ\]**</span><span class="sxs-lookup"><span data-stu-id="d6987-145">**/c\[lasses\]**</span></span>|<span data-ttu-id="d6987-146">指定したスキーマと対応するクラスを生成します。</span><span class="sxs-lookup"><span data-stu-id="d6987-146">Generates classes that correspond to the specified schema.</span></span> <span data-ttu-id="d6987-147">オブジェクトに XML データを読み込むには、<xref:System.Xml.Serialization.XmlSerializer.Deserialize%2A?displayProperty=nameWithType> メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="d6987-147">To read XML data into the object, use the <xref:System.Xml.Serialization.XmlSerializer.Deserialize%2A?displayProperty=nameWithType> method.</span></span>|
|<span data-ttu-id="d6987-148">**/d\[アタセット\]**</span><span class="sxs-lookup"><span data-stu-id="d6987-148">**/d\[ataset\]**</span></span>|<span data-ttu-id="d6987-149">指定したスキーマに対応する <xref:System.Data.DataSet> から派生したクラスを生成します。</span><span class="sxs-lookup"><span data-stu-id="d6987-149">Generates a class derived from <xref:System.Data.DataSet> that corresponds to the specified schema.</span></span> <span data-ttu-id="d6987-150">派生したクラスに XML データを読み込むには、<xref:System.Data.DataSet.ReadXml%2A?displayProperty=nameWithType> メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="d6987-150">To read XML data into the derived class, use the <xref:System.Data.DataSet.ReadXml%2A?displayProperty=nameWithType> method.</span></span>|

 <span data-ttu-id="d6987-151">.xsd ファイルについては、次のオプションのうち任意のオプションを指定できます。</span><span class="sxs-lookup"><span data-stu-id="d6987-151">You can also specify any of the following options for .xsd files.</span></span>

|<span data-ttu-id="d6987-152">オプション</span><span class="sxs-lookup"><span data-stu-id="d6987-152">Option</span></span>|<span data-ttu-id="d6987-153">説明</span><span class="sxs-lookup"><span data-stu-id="d6987-153">Description</span></span>|
|------------|-----------------|
|<span data-ttu-id="d6987-154">**/e\[レ\]メント :**_要素_</span><span class="sxs-lookup"><span data-stu-id="d6987-154">**/e\[lement\]:**_element_</span></span>|<span data-ttu-id="d6987-155">コードを生成する対象とする、スキーマ内の要素を指定します。</span><span class="sxs-lookup"><span data-stu-id="d6987-155">Specifies the element in the schema to generate code for.</span></span> <span data-ttu-id="d6987-156">既定では、すべての要素が指定されます。</span><span class="sxs-lookup"><span data-stu-id="d6987-156">By default all elements are typed.</span></span> <span data-ttu-id="d6987-157">この引数は、複数回指定できます。</span><span class="sxs-lookup"><span data-stu-id="d6987-157">You can specify this argument more than once.</span></span>|
|<span data-ttu-id="d6987-158">**/enableDataBinding**</span><span class="sxs-lookup"><span data-stu-id="d6987-158">**/enableDataBinding**</span></span>|<span data-ttu-id="d6987-159">データ バインディングを有効にするために、生成されたすべての型に <xref:System.ComponentModel.INotifyPropertyChanged> インターフェイスを実装します。</span><span class="sxs-lookup"><span data-stu-id="d6987-159">Implements the <xref:System.ComponentModel.INotifyPropertyChanged> interface on all generated types to enable data binding.</span></span> <span data-ttu-id="d6987-160">短縮形は `/edb` です。</span><span class="sxs-lookup"><span data-stu-id="d6987-160">The short form is `/edb`.</span></span>|
|<span data-ttu-id="d6987-161">**/有効なデータセット**</span><span class="sxs-lookup"><span data-stu-id="d6987-161">**/enableLinqDataSet**</span></span>|<span data-ttu-id="d6987-162">(短い形式`/eld`: .)生成されたデータセットを LINQ to DataSet の使用に対してクエリできることを指定します。</span><span class="sxs-lookup"><span data-stu-id="d6987-162">(Short form: `/eld`.) Specifies that the generated DataSet can be queried against using LINQ to DataSet.</span></span> <span data-ttu-id="d6987-163">このオプションは /dataset オプションも指定した場合に使用されます。</span><span class="sxs-lookup"><span data-stu-id="d6987-163">This option is used when the /dataset option is also specified.</span></span> <span data-ttu-id="d6987-164">詳細については、「[LINQ to DataSet Overview](../../../docs/framework/data/adonet/linq-to-dataset-overview.md)」(LINQ to DataSet Overview) と「[Querying Typed DataSets](../../../docs/framework/data/adonet/querying-typed-datasets.md)」(型指定された DataSet のクエリ) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d6987-164">For more information, see [LINQ to DataSet Overview](../../../docs/framework/data/adonet/linq-to-dataset-overview.md) and [Querying Typed DataSets](../../../docs/framework/data/adonet/querying-typed-datasets.md).</span></span> <span data-ttu-id="d6987-165">LINQ の使用に関する一般的な情報については、「[言語統合クエリ (LINQ) - C#](../../csharp/programming-guide/concepts/linq/index.md)または[言語統合クエリ (LINQ) - Visual Basic](../../visual-basic/programming-guide/concepts/linq/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d6987-165">For general information about using LINQ, see [Language-Integrated Query (LINQ) - C#](../../csharp/programming-guide/concepts/linq/index.md) or [Language-Integrated Query (LINQ) - Visual Basic](../../visual-basic/programming-guide/concepts/linq/index.md).</span></span>|
|<span data-ttu-id="d6987-166">**/f\[イエルド\]**</span><span class="sxs-lookup"><span data-stu-id="d6987-166">**/f\[ields\]**</span></span>|<span data-ttu-id="d6987-167">プロパティの代わりにフィールドを生成します。</span><span class="sxs-lookup"><span data-stu-id="d6987-167">Generates fields instead of properties.</span></span> <span data-ttu-id="d6987-168">既定では、プロパティが生成されます。</span><span class="sxs-lookup"><span data-stu-id="d6987-168">By default, properties are generated.</span></span>|
|<span data-ttu-id="d6987-169">**/l\[アンゲージ\]:**_言語_</span><span class="sxs-lookup"><span data-stu-id="d6987-169">**/l\[anguage\]:**_language_</span></span>|<span data-ttu-id="d6987-170">使用するプログラミング言語を指定します。</span><span class="sxs-lookup"><span data-stu-id="d6987-170">Specifies the programming language to use.</span></span> <span data-ttu-id="d6987-171">`CS` (C#、既定値)、`VB` (Visual Basic)、`JS` (JScript)、または `VJS` (Visual J#) から選択します。</span><span class="sxs-lookup"><span data-stu-id="d6987-171">Choose from `CS` (C#, which is the default), `VB` (Visual Basic), `JS` (JScript), or `VJS` (Visual J#).</span></span> <span data-ttu-id="d6987-172"><xref:System.CodeDom.Compiler.CodeDomProvider?displayProperty=nameWithType> を実装するクラスの完全修飾名を指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="d6987-172">You can also specify a fully qualified name for a class implementing <xref:System.CodeDom.Compiler.CodeDomProvider?displayProperty=nameWithType></span></span>|
|<span data-ttu-id="d6987-173">**/n\[\]amespace :**_名前空間_</span><span class="sxs-lookup"><span data-stu-id="d6987-173">**/n\[amespace\]:**_namespace_</span></span>|<span data-ttu-id="d6987-174">生成する型のランタイム名前空間を指定します。</span><span class="sxs-lookup"><span data-stu-id="d6987-174">Specifies the runtime namespace for the generated types.</span></span> <span data-ttu-id="d6987-175">既定の名前空間は `Schemas` です。</span><span class="sxs-lookup"><span data-stu-id="d6987-175">The default namespace is `Schemas`.</span></span>|
|<span data-ttu-id="d6987-176">**/nologo**</span><span class="sxs-lookup"><span data-stu-id="d6987-176">**/nologo**</span></span>|<span data-ttu-id="d6987-177">バナーを表示しません。</span><span class="sxs-lookup"><span data-stu-id="d6987-177">Suppresses the banner.</span></span>|
|<span data-ttu-id="d6987-178">**/order**</span><span class="sxs-lookup"><span data-stu-id="d6987-178">**/order**</span></span>|<span data-ttu-id="d6987-179">すべてのパーティクル メンバーに明示的な順序 ID を生成します。</span><span class="sxs-lookup"><span data-stu-id="d6987-179">Generates explicit order identifiers on all particle members.</span></span>|
|<span data-ttu-id="d6987-180">**/o\[\]ut :**_ディレクトリ名_</span><span class="sxs-lookup"><span data-stu-id="d6987-180">**/o\[ut\]:**_directoryName_</span></span>|<span data-ttu-id="d6987-181">ファイルを格納する出力ディレクトリを指定します。</span><span class="sxs-lookup"><span data-stu-id="d6987-181">Specifies the output directory to place the files in.</span></span> <span data-ttu-id="d6987-182">既定値は現在のディレクトリです。</span><span class="sxs-lookup"><span data-stu-id="d6987-182">The default is the current directory.</span></span>|
|<span data-ttu-id="d6987-183">**/u\[\]ri :**_uri_</span><span class="sxs-lookup"><span data-stu-id="d6987-183">**/u\[ri\]:**_uri_</span></span>|<span data-ttu-id="d6987-184">コードを生成する対象とする、スキーマ内の要素の URI を指定します。</span><span class="sxs-lookup"><span data-stu-id="d6987-184">Specifies the URI for the elements in the schema to generate code for.</span></span> <span data-ttu-id="d6987-185">指定した場合、この URI は `/element` オプションで指定したすべての要素に適用されます。</span><span class="sxs-lookup"><span data-stu-id="d6987-185">This URI, if present, applies to all elements specified with the `/element` option.</span></span>|

## <a name="dll-and-exe-file-options"></a><span data-ttu-id="d6987-186">DLL ファイルと EXE ファイルのオプション</span><span class="sxs-lookup"><span data-stu-id="d6987-186">DLL and EXE File Options</span></span>

|<span data-ttu-id="d6987-187">オプション</span><span class="sxs-lookup"><span data-stu-id="d6987-187">Option</span></span>|<span data-ttu-id="d6987-188">説明</span><span class="sxs-lookup"><span data-stu-id="d6987-188">Description</span></span>|
|------------|-----------------|
|<span data-ttu-id="d6987-189">**/t\[ype\]:**_型名_</span><span class="sxs-lookup"><span data-stu-id="d6987-189">**/t\[ype\]:**_typename_</span></span>|<span data-ttu-id="d6987-190">スキーマの作成対象とする型の名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="d6987-190">Specifies the name of the type to create a schema for.</span></span> <span data-ttu-id="d6987-191">複数の型の引数を指定できます。</span><span class="sxs-lookup"><span data-stu-id="d6987-191">You can specify multiple type arguments.</span></span> <span data-ttu-id="d6987-192">*typename* によって名前空間が特定されない場合、指定された型を持つアセンブリに含まれるすべての型が対象となります。</span><span class="sxs-lookup"><span data-stu-id="d6987-192">If *typename* does not specify a namespace, Xsd.exe matches all types in the assembly with the specified type.</span></span> <span data-ttu-id="d6987-193">*typename* によって名前空間が特定される場合は、その型だけが対象になります。</span><span class="sxs-lookup"><span data-stu-id="d6987-193">If *typename* specifies a namespace, only that type is matched.</span></span> <span data-ttu-id="d6987-194">*typename* の末尾がアスタリスク (\*) の場合は、\* の前にある文字列で始まる型のすべてが対象となります。</span><span class="sxs-lookup"><span data-stu-id="d6987-194">If *typename* ends with an asterisk character (\*), the tool matches all types that start with the string preceding the \*.</span></span> <span data-ttu-id="d6987-195">`/type` オプションを省略すると、アセンブリに含まれるすべての型についてスキーマが生成されます。</span><span class="sxs-lookup"><span data-stu-id="d6987-195">If you omit the `/type` option, Xsd.exe generates schemas for all types in the assembly.</span></span>|

## <a name="remarks"></a><span data-ttu-id="d6987-196">解説</span><span class="sxs-lookup"><span data-stu-id="d6987-196">Remarks</span></span>

<span data-ttu-id="d6987-197">Xsd.exe が実行する操作を次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="d6987-197">The following table shows the operations that Xsd.exe performs.</span></span>

| | |
|------------|-----------------|
|<span data-ttu-id="d6987-198">XDR から XSD へ</span><span class="sxs-lookup"><span data-stu-id="d6987-198">XDR to XSD</span></span>|<span data-ttu-id="d6987-199">XML-Data-Reduced スキーマ ファイルから XML スキーマを生成します。</span><span class="sxs-lookup"><span data-stu-id="d6987-199">Generates an XML schema from an XML-Data-Reduced schema file.</span></span> <span data-ttu-id="d6987-200">XDR は初期の XML ベースのスキーマ形式です。</span><span class="sxs-lookup"><span data-stu-id="d6987-200">XDR is an early XML-based schema format.</span></span>|
|<span data-ttu-id="d6987-201">XML から XSD へ</span><span class="sxs-lookup"><span data-stu-id="d6987-201">XML to XSD</span></span>|<span data-ttu-id="d6987-202">XML ファイルから XML スキーマを生成します。</span><span class="sxs-lookup"><span data-stu-id="d6987-202">Generates an XML schema from an XML file.</span></span>|
|<span data-ttu-id="d6987-203">XSD から DataSet へ</span><span class="sxs-lookup"><span data-stu-id="d6987-203">XSD to DataSet</span></span>|<span data-ttu-id="d6987-204">XSD スキーマ ファイルから共通言語ランタイムの <xref:System.Data.DataSet> クラスを生成します。</span><span class="sxs-lookup"><span data-stu-id="d6987-204">Generates common language runtime <xref:System.Data.DataSet> classes from an XSD schema file.</span></span> <span data-ttu-id="d6987-205">生成されるクラスには、標準の XML データ用のリッチ オブジェクト モデルが用意されています。</span><span class="sxs-lookup"><span data-stu-id="d6987-205">The generated classes provide a rich object model for regular XML data.</span></span>|
|<span data-ttu-id="d6987-206">XSD からクラスへ</span><span class="sxs-lookup"><span data-stu-id="d6987-206">XSD to Classes</span></span>|<span data-ttu-id="d6987-207">XSD スキーマ ファイルからランタイム クラスを生成します。</span><span class="sxs-lookup"><span data-stu-id="d6987-207">Generates runtime classes from an XSD schema file.</span></span> <span data-ttu-id="d6987-208">生成されたクラスを <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType> と組み合わせて使用すると、このスキーマに従う XML コードの読み書きを実行できます。</span><span class="sxs-lookup"><span data-stu-id="d6987-208">The generated classes can be used in conjunction with <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType> to read and write XML code that follows the schema.</span></span>|
|<span data-ttu-id="d6987-209">クラスから XSD へ</span><span class="sxs-lookup"><span data-stu-id="d6987-209">Classes to XSD</span></span>| <span data-ttu-id="d6987-210">ランタイム アセンブリ ファイルに含まれる 1 つ以上の型から XML スキーマを生成します。</span><span class="sxs-lookup"><span data-stu-id="d6987-210">Generates an XML schema from a type or types in a runtime assembly file.</span></span> <span data-ttu-id="d6987-211">生成されたスキーマは、 で使用される<xref:System.Xml.Serialization.XmlSerializer>XML 形式を定義します。</span><span class="sxs-lookup"><span data-stu-id="d6987-211">The generated schema defines the XML format used by the <xref:System.Xml.Serialization.XmlSerializer>.</span></span>|

 <span data-ttu-id="d6987-212">Xsd.exe によって操作できるのは、W3C (World Wide Web Consortium) が提唱する XSD (XML スキーマ定義) に準拠した XML スキーマだけです。</span><span class="sxs-lookup"><span data-stu-id="d6987-212">Xsd.exe only allows you to manipulate XML schemas that follow the XML Schema Definition (XSD) language proposed by the World Wide Web Consortium (W3C).</span></span> <span data-ttu-id="d6987-213">XML スキーマ定義の提案または XML 標準の詳細については、<https://w3.org>を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d6987-213">For more information on the XML Schema Definition proposal or the XML standard, see <https://w3.org>.</span></span>

## <a name="setting-options-with-an-xml-file"></a><span data-ttu-id="d6987-214">XML ファイルによるオプションの設定</span><span class="sxs-lookup"><span data-stu-id="d6987-214">Setting Options with an XML File</span></span>

<span data-ttu-id="d6987-215">`/parameters` スイッチを使用すると、各種のオプションを設定する単一の XML ファイルを指定できます。</span><span class="sxs-lookup"><span data-stu-id="d6987-215">By using the `/parameters` switch, you can specify a single XML file that sets various options.</span></span> <span data-ttu-id="d6987-216">設定できるオプションは、XSD.exe ツールの使用方法によって異なります。</span><span class="sxs-lookup"><span data-stu-id="d6987-216">The options you can set depend on how you are using the XSD.exe tool.</span></span> <span data-ttu-id="d6987-217">選択肢には、スキーマの生成、コード ファイルの生成、または `DataSet` 機能を含むコード ファイルの生成があります。</span><span class="sxs-lookup"><span data-stu-id="d6987-217">Choices include generating schemas, generating code files, or generating code files that include `DataSet` features.</span></span> <span data-ttu-id="d6987-218">たとえば、コード ファイルではなくスキーマを生成する場合、実行可能ファイル (.exe) またはタイプ ライブラリ (.dll) ファイルの名前に `<assembly>` 要素を設定できます。</span><span class="sxs-lookup"><span data-stu-id="d6987-218">For example, you can set the `<assembly>` element to the name of an executable (.exe) or type library (.dll) file when generating a schema, but not when generating a code file.</span></span> <span data-ttu-id="d6987-219">次の XML に、指定された実行可能ファイルで `<generateSchemas>` 要素を使用する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="d6987-219">The following XML shows how to use the `<generateSchemas>` element with a specified executable:</span></span>

```xml
<!-- This is in a file named GenerateSchemas.xml. -->
<xsd xmlns='http://microsoft.com/dotnet/tools/xsd/'>
<generateSchemas>
   <assembly>ConsoleApplication1.exe</assembly>
</generateSchemas>
</xsd>
```

<span data-ttu-id="d6987-220">上記の XML が GenerateSchemas.xml という名前のファイルに含まれている`/parameters`場合は、コマンド プロンプトで次のように入力し **、Enter**キーを押してスイッチを使用します。</span><span class="sxs-lookup"><span data-stu-id="d6987-220">If the preceding XML is contained in a file named GenerateSchemas.xml, then use the `/parameters` switch by typing the following at a command prompt and pressing **Enter**:</span></span>

```console
 xsd /p:GenerateSchemas.xml
```

<span data-ttu-id="d6987-221">アセンブリにある単一の型のスキーマを生成する場合は、次のような XML を使用します。</span><span class="sxs-lookup"><span data-stu-id="d6987-221">On the other hand, if you are generating a schema for a single type found in the assembly, you can use the following XML:</span></span>

```xml
<!-- This is in a file named GenerateSchemaFromType.xml. -->
<xsd xmlns='http://microsoft.com/dotnet/tools/xsd/'>
<generateSchemas>
   <type>IDItems</type>
</generateSchemas>
</xsd>
```

<span data-ttu-id="d6987-222">しかし、上のコードを使用するには、コマンド プロンプトでアセンブリの名前も指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d6987-222">But to use preceding code, you must also supply the name of the assembly at the command prompt.</span></span> <span data-ttu-id="d6987-223">コマンド プロンプトで次のように入力します (XML ファイルの名前は GenerateSchemaFromType.xml とします)。</span><span class="sxs-lookup"><span data-stu-id="d6987-223">Enter the following at a command prompt (presuming the XML file is named GenerateSchemaFromType.xml):</span></span>

```console
xsd /p:GenerateSchemaFromType.xml ConsoleApplication1.exe
```

<span data-ttu-id="d6987-224">`<generateSchemas>` 要素に対しては、次のオプションのうち 1 つだけを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d6987-224">You must specify only one of the following options for the `<generateSchemas>` element.</span></span>

|<span data-ttu-id="d6987-225">要素</span><span class="sxs-lookup"><span data-stu-id="d6987-225">Element</span></span>|<span data-ttu-id="d6987-226">説明</span><span class="sxs-lookup"><span data-stu-id="d6987-226">Description</span></span>|
|-------------|-----------------|
|<span data-ttu-id="d6987-227">\<assembly></span><span class="sxs-lookup"><span data-stu-id="d6987-227">\<assembly></span></span>|<span data-ttu-id="d6987-228">スキーマを生成するアセンブリを指定します。</span><span class="sxs-lookup"><span data-stu-id="d6987-228">Specifies an assembly to generate the schema from.</span></span>|
|<span data-ttu-id="d6987-229">\<type></span><span class="sxs-lookup"><span data-stu-id="d6987-229">\<type></span></span>|<span data-ttu-id="d6987-230">スキーマを生成するアセンブリに含まれる型を指定します。</span><span class="sxs-lookup"><span data-stu-id="d6987-230">Specifies a type found in an assembly to generate a schema for.</span></span>|
|<span data-ttu-id="d6987-231">\<xml></span><span class="sxs-lookup"><span data-stu-id="d6987-231">\<xml></span></span>|<span data-ttu-id="d6987-232">スキーマを生成する XML ファイルを指定します。</span><span class="sxs-lookup"><span data-stu-id="d6987-232">Specifies an XML file to generate a schema for.</span></span>|
|<span data-ttu-id="d6987-233">\<xdr></span><span class="sxs-lookup"><span data-stu-id="d6987-233">\<xdr></span></span>|<span data-ttu-id="d6987-234">スキーマを生成する XDR ファイルを指定します。</span><span class="sxs-lookup"><span data-stu-id="d6987-234">Specifies an XDR file to generate a schema for.</span></span>|

<span data-ttu-id="d6987-235">コード ファイルを生成するには、`<generateClasses>` 要素を使用します。</span><span class="sxs-lookup"><span data-stu-id="d6987-235">To generate a code file, use the `<generateClasses>` element.</span></span> <span data-ttu-id="d6987-236">コード ファイルを生成する例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="d6987-236">The following example generates a code file.</span></span> <span data-ttu-id="d6987-237">この例では、生成されるファイルのプログラミング言語と名前空間を設定するための 2 つの属性も示されています。</span><span class="sxs-lookup"><span data-stu-id="d6987-237">Note that two attributes are also shown that allow you to set the programming language and namespace of the generated file.</span></span>

```xml
<xsd xmlns='http://microsoft.com/dotnet/tools/xsd/'>
<generateClasses language='VB' namespace='Microsoft.Serialization.Examples'/>
</xsd>
<!-- You must supply an .xsd file when typing in the command line.-->
<!-- For example: xsd /p:genClasses mySchema.xsd -->
```

 <span data-ttu-id="d6987-238">`<generateClasses>` 要素に設定できるオプションは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="d6987-238">Options you can set for the `<generateClasses>` element include the following.</span></span>

|<span data-ttu-id="d6987-239">要素</span><span class="sxs-lookup"><span data-stu-id="d6987-239">Element</span></span>|<span data-ttu-id="d6987-240">説明</span><span class="sxs-lookup"><span data-stu-id="d6987-240">Description</span></span>|
|-------------|-----------------|
|<span data-ttu-id="d6987-241">\<element></span><span class="sxs-lookup"><span data-stu-id="d6987-241">\<element></span></span>|<span data-ttu-id="d6987-242">コードを生成する対象となる .xsd ファイルの要素を指定します。</span><span class="sxs-lookup"><span data-stu-id="d6987-242">Specifies an element in the .xsd file to generate code for.</span></span>|
|<span data-ttu-id="d6987-243">\<schemaImporterExtensions></span><span class="sxs-lookup"><span data-stu-id="d6987-243">\<schemaImporterExtensions></span></span>|<span data-ttu-id="d6987-244"><xref:System.Xml.Serialization.Advanced.SchemaImporterExtension> クラスから派生する型を指定します。</span><span class="sxs-lookup"><span data-stu-id="d6987-244">Specifies a type derived from the <xref:System.Xml.Serialization.Advanced.SchemaImporterExtension> class.</span></span>|
|<span data-ttu-id="d6987-245">\<schema></span><span class="sxs-lookup"><span data-stu-id="d6987-245">\<schema></span></span>|<span data-ttu-id="d6987-246">コードを生成する XML スキーマ ファイルを指定します。</span><span class="sxs-lookup"><span data-stu-id="d6987-246">Specifies a XML Schema file to generate code for.</span></span> <span data-ttu-id="d6987-247">複数の \<schema> 要素を使用して、複数の XML スキーマ ファイルを指定できます。</span><span class="sxs-lookup"><span data-stu-id="d6987-247">Multiple XML Schema files can be specified using multiple \<schema> elements.</span></span>|

<span data-ttu-id="d6987-248">次の表に、`<generateClasses>` 要素と共に使用するその他の属性を示します。</span><span class="sxs-lookup"><span data-stu-id="d6987-248">The following table shows the attributes that can also be used with the `<generateClasses>` element.</span></span>

|<span data-ttu-id="d6987-249">属性</span><span class="sxs-lookup"><span data-stu-id="d6987-249">Attribute</span></span>|<span data-ttu-id="d6987-250">説明</span><span class="sxs-lookup"><span data-stu-id="d6987-250">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="d6987-251">language</span><span class="sxs-lookup"><span data-stu-id="d6987-251">language</span></span>|<span data-ttu-id="d6987-252">使用するプログラミング言語を指定します。</span><span class="sxs-lookup"><span data-stu-id="d6987-252">Specifies the programming language to use.</span></span> <span data-ttu-id="d6987-253">`CS` (C#、既定値)、`VB` (Visual Basic)、`JS` (JScript)、または `VJS` (Visual J#) から選択します。</span><span class="sxs-lookup"><span data-stu-id="d6987-253">Choose from `CS` (C#, the default), `VB` (Visual Basic), `JS` (JScript), or `VJS` (Visual J#).</span></span> <span data-ttu-id="d6987-254"><xref:System.CodeDom.Compiler.CodeDomProvider> を実装するクラスの完全修飾名を指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="d6987-254">You can also specify a fully qualified name for a class that implements <xref:System.CodeDom.Compiler.CodeDomProvider>.</span></span>|
|<span data-ttu-id="d6987-255">namespace</span><span class="sxs-lookup"><span data-stu-id="d6987-255">namespace</span></span>|<span data-ttu-id="d6987-256">生成するコードの名前空間を指定します。</span><span class="sxs-lookup"><span data-stu-id="d6987-256">Specifies the namespace for the generated code.</span></span> <span data-ttu-id="d6987-257">名前空間は、スペースやバックスラッシュ文字を使用しないなどの CLR 標準に準拠する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d6987-257">The namespace must conform to CLR standards (for example, no spaces or backslash characters).</span></span>|
|<span data-ttu-id="d6987-258">options</span><span class="sxs-lookup"><span data-stu-id="d6987-258">options</span></span>|<span data-ttu-id="d6987-259">`none`、`properties` (パブリック フィールドの代わりにプロパティを生成)、`order`、または `enableDataBinding` (前の「XSD ファイルのオプション」セクションの `/order` と `/enableDataBinding` スイッチを参照) のいずれかの値です。</span><span class="sxs-lookup"><span data-stu-id="d6987-259">One of the following values: `none`, `properties` (generates properties instead of public fields), `order`, or `enableDataBinding` (see the `/order` and `/enableDataBinding` switches in the preceding XSD File Options section.</span></span>|

 <span data-ttu-id="d6987-260">`DataSet` 要素を使用すると、`<generateDataSet>` コードを生成する方法を制御できます。</span><span class="sxs-lookup"><span data-stu-id="d6987-260">You can also control how `DataSet` code is generated by using the `<generateDataSet>` element.</span></span> <span data-ttu-id="d6987-261">次の XML は、生成された`DataSet`コードが、指定した要素<xref:System.Data.DataTable>の Visual Basic コードを作成するために、クラスなどの構造体を使用することを指定します。</span><span class="sxs-lookup"><span data-stu-id="d6987-261">The following XML specifies that the generated code uses `DataSet` structures (such as the <xref:System.Data.DataTable> class) to create Visual Basic code for a specified element.</span></span> <span data-ttu-id="d6987-262">生成された DataSet 構造体では LINQ クエリがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="d6987-262">The generated DataSet structures will support LINQ queries.</span></span>

 ```xml
 <xsd xmlns='http://microsoft.com/dotnet/tools/xsd/'>
     <generateDataSet language='VB' namespace='Microsoft.Serialization.Examples' enableLinqDataSet='true'>
     </generateDataSet>
 </xsd>
```

<span data-ttu-id="d6987-263">`<generateDataSet>` 要素に設定できるオプションは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="d6987-263">Options you can set for the `<generateDataSet>` element include the following.</span></span>

|<span data-ttu-id="d6987-264">要素</span><span class="sxs-lookup"><span data-stu-id="d6987-264">Element</span></span>|<span data-ttu-id="d6987-265">説明</span><span class="sxs-lookup"><span data-stu-id="d6987-265">Description</span></span>|
|-------------|-----------------|
|<span data-ttu-id="d6987-266">\<schema></span><span class="sxs-lookup"><span data-stu-id="d6987-266">\<schema></span></span>|<span data-ttu-id="d6987-267">コードを生成する XML スキーマ ファイルを指定します。</span><span class="sxs-lookup"><span data-stu-id="d6987-267">Specifies an XML Schema file to generate code for.</span></span> <span data-ttu-id="d6987-268">複数の \<schema> 要素を使用して、複数の XML スキーマ ファイルを指定できます。</span><span class="sxs-lookup"><span data-stu-id="d6987-268">Multiple XML Schema files can be specified using multiple \<schema> elements.</span></span>|

 <span data-ttu-id="d6987-269">`<generateDataSet>` 要素と共に使用できる属性を次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="d6987-269">The following table shows the attributes that can be used with the `<generateDataSet>` element.</span></span>

|<span data-ttu-id="d6987-270">属性</span><span class="sxs-lookup"><span data-stu-id="d6987-270">Attribute</span></span>|<span data-ttu-id="d6987-271">説明</span><span class="sxs-lookup"><span data-stu-id="d6987-271">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="d6987-272">enableLinqDataSet</span><span class="sxs-lookup"><span data-stu-id="d6987-272">enableLinqDataSet</span></span>|<span data-ttu-id="d6987-273">LINQ to DataSet を使用して、生成された DataSet を照会できるように指定します。</span><span class="sxs-lookup"><span data-stu-id="d6987-273">Specifies that the generated DataSet can be queried against using LINQ to DataSet.</span></span> <span data-ttu-id="d6987-274">既定値は false です。</span><span class="sxs-lookup"><span data-stu-id="d6987-274">The default value is false.</span></span>|
|<span data-ttu-id="d6987-275">language</span><span class="sxs-lookup"><span data-stu-id="d6987-275">language</span></span>|<span data-ttu-id="d6987-276">使用するプログラミング言語を指定します。</span><span class="sxs-lookup"><span data-stu-id="d6987-276">Specifies the programming language to use.</span></span> <span data-ttu-id="d6987-277">`CS` (C#、既定値)、`VB` (Visual Basic)、`JS` (JScript)、または `VJS` (Visual J#) から選択します。</span><span class="sxs-lookup"><span data-stu-id="d6987-277">Choose from `CS` (C#, the default), `VB` (Visual Basic), `JS` (JScript), or `VJS` (Visual J#).</span></span> <span data-ttu-id="d6987-278"><xref:System.CodeDom.Compiler.CodeDomProvider> を実装するクラスの完全修飾名を指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="d6987-278">You can also specify a fully qualified name for a class that implements <xref:System.CodeDom.Compiler.CodeDomProvider>.</span></span>|
|<span data-ttu-id="d6987-279">namespace</span><span class="sxs-lookup"><span data-stu-id="d6987-279">namespace</span></span>|<span data-ttu-id="d6987-280">生成するコードの名前空間を指定します。</span><span class="sxs-lookup"><span data-stu-id="d6987-280">Specifies the namespace for the generated code.</span></span> <span data-ttu-id="d6987-281">名前空間は、スペースやバックスラッシュ文字を使用しないなどの CLR 標準に準拠する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d6987-281">The namespace must conform to CLR standards (for example, no spaces or backslash characters).</span></span>|

 <span data-ttu-id="d6987-282">トップ レベルの `<xsd>` 要素に設定できる属性があります。</span><span class="sxs-lookup"><span data-stu-id="d6987-282">There are attributes that you can set on the top level `<xsd>` element.</span></span> <span data-ttu-id="d6987-283">これらのオプションは、`<generateSchemas>`、`<generateClasses>`、または `<generateDataSet>` の各子要素と共に使用できます。</span><span class="sxs-lookup"><span data-stu-id="d6987-283">These options can be used with any of the child elements (`<generateSchemas>`, `<generateClasses>` or `<generateDataSet>`).</span></span> <span data-ttu-id="d6987-284">次の XML コードは、"MyOutputDirectory" という出力ディレクトリの "IDItems" という要素のコードを生成します。</span><span class="sxs-lookup"><span data-stu-id="d6987-284">The following XML code generates code for an element named "IDItems" in the output directory named "MyOutputDirectory".</span></span>

```xml
<xsd xmlns='http://microsoft.com/dotnet/tools/xsd/' output='MyOutputDirectory'>
<generateClasses>
    <element>IDItems</element>
</generateClasses>
</xsd>
```

<span data-ttu-id="d6987-285">次の表に、`<xsd>` 要素と共に使用するその他の属性を示します。</span><span class="sxs-lookup"><span data-stu-id="d6987-285">The following table shows the attributes that can also be used with the `<xsd>` element.</span></span>

|<span data-ttu-id="d6987-286">属性</span><span class="sxs-lookup"><span data-stu-id="d6987-286">Attribute</span></span>|<span data-ttu-id="d6987-287">説明</span><span class="sxs-lookup"><span data-stu-id="d6987-287">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="d6987-288">output</span><span class="sxs-lookup"><span data-stu-id="d6987-288">output</span></span>|<span data-ttu-id="d6987-289">生成されたスキーマまたはコード ファイルが格納されるディレクトリの名前です。</span><span class="sxs-lookup"><span data-stu-id="d6987-289">The name of a directory where the generated schema or code file will be placed.</span></span>|
|<span data-ttu-id="d6987-290">nologo</span><span class="sxs-lookup"><span data-stu-id="d6987-290">nologo</span></span>|<span data-ttu-id="d6987-291">バナーを表示しません。</span><span class="sxs-lookup"><span data-stu-id="d6987-291">Suppresses the banner.</span></span> <span data-ttu-id="d6987-292">`true` または `false` に設定します。</span><span class="sxs-lookup"><span data-stu-id="d6987-292">Set to `true` or `false`.</span></span>|
|<span data-ttu-id="d6987-293">help</span><span class="sxs-lookup"><span data-stu-id="d6987-293">help</span></span>|<span data-ttu-id="d6987-294">このツールのコマンド構文とオプションを表示します。</span><span class="sxs-lookup"><span data-stu-id="d6987-294">Displays command syntax and options for the tool.</span></span> <span data-ttu-id="d6987-295">`true` または `false` に設定します。</span><span class="sxs-lookup"><span data-stu-id="d6987-295">Set to `true` or `false`.</span></span>|

## <a name="examples"></a><span data-ttu-id="d6987-296">例</span><span class="sxs-lookup"><span data-stu-id="d6987-296">Examples</span></span>
 <span data-ttu-id="d6987-297">`myFile.xdr` から XML スキーマを生成し、現在のディレクトリに保存するコマンドを次に示します。</span><span class="sxs-lookup"><span data-stu-id="d6987-297">The following command generates an XML schema from `myFile.xdr` and saves it to the current directory.</span></span>

```console
xsd myFile.xdr
```

<span data-ttu-id="d6987-298">`myFile.xml` から XML スキーマを生成し、指定したディレクトリに保存するコマンドを次に示します。</span><span class="sxs-lookup"><span data-stu-id="d6987-298">The following command generates an XML schema from `myFile.xml` and saves it to the specified directory.</span></span>

```console
xsd myFile.xml /outputdir:myOutputDir
```

<span data-ttu-id="d6987-299">指定したスキーマと対応するデータセットを C# 言語で生成し、現在のディレクトリ内に `XSDSchemaFile.cs` として保存するコマンドを次に示します。</span><span class="sxs-lookup"><span data-stu-id="d6987-299">The following command generates a data set that corresponds to the specified schema in the C# language and saves it as `XSDSchemaFile.cs` in the current directory.</span></span>

```console
xsd /dataset /language:CS XSDSchemaFile.xsd
```

<span data-ttu-id="d6987-300">`myAssembly.dll` アセンブリ内のすべての型について XML スキーマを生成し、それらを `schema0.xsd` として現在のディレクトリ内に保存するコマンドを次に示します。</span><span class="sxs-lookup"><span data-stu-id="d6987-300">The following command generates XML schemas for all types in the assembly `myAssembly.dll` and saves them as `schema0.xsd` in the current directory.</span></span>

```console
xsd myAssembly.dll
```

## <a name="see-also"></a><span data-ttu-id="d6987-301">関連項目</span><span class="sxs-lookup"><span data-stu-id="d6987-301">See also</span></span>

- <xref:System.Data.DataSet>
- <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType>
- [<span data-ttu-id="d6987-302">ツール</span><span class="sxs-lookup"><span data-stu-id="d6987-302">Tools</span></span>](../../../docs/framework/tools/index.md)
- [<span data-ttu-id="d6987-303">Visual Studio 用開発者コマンド プロンプト</span><span class="sxs-lookup"><span data-stu-id="d6987-303">Command Prompts</span></span>](../../../docs/framework/tools/developer-command-prompt-for-vs.md)
- [<span data-ttu-id="d6987-304">LINQ to DataSet の概要</span><span class="sxs-lookup"><span data-stu-id="d6987-304">LINQ to DataSet Overview</span></span>](../../../docs/framework/data/adonet/linq-to-dataset-overview.md)
- [<span data-ttu-id="d6987-305">型指定された DataSet のクエリ</span><span class="sxs-lookup"><span data-stu-id="d6987-305">Querying Typed DataSets</span></span>](../../../docs/framework/data/adonet/querying-typed-datasets.md)
- [<span data-ttu-id="d6987-306">LINQ (言語統合クエリ) (C#)</span><span class="sxs-lookup"><span data-stu-id="d6987-306">LINQ (Language-Integrated Query) (C#)</span></span>](../../csharp/programming-guide/concepts/linq/index.md)
- [<span data-ttu-id="d6987-307">LINQ (言語統合クエリ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d6987-307">LINQ (Language-Integrated Query) (Visual Basic)</span></span>](../../visual-basic/programming-guide/concepts/linq/index.md)
