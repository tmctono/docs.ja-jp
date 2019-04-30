---
title: XML Schema Definition Tool (Xsd.exe)
ms.date: 03/30/2017
ms.assetid: a6e6e65c-347f-4494-9457-653bf29baac2
ms.openlocfilehash: fa90110a803a97cd7a610fd33f94557c44660e2b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62028227"
---
# <a name="xml-schema-definition-tool-xsdexe"></a><span data-ttu-id="28faa-102">XML Schema Definition Tool (Xsd.exe)</span><span class="sxs-lookup"><span data-stu-id="28faa-102">XML Schema Definition Tool (Xsd.exe)</span></span>

<span data-ttu-id="28faa-103">XML スキーマ定義ツール (Xsd.exe) は、XDR、XML、および XSD ファイル、またはランタイム アセンブリ内のクラスから XML スキーマ クラスまたは共通言語ランタイム クラスを生成します。</span><span class="sxs-lookup"><span data-stu-id="28faa-103">The XML Schema Definition (Xsd.exe) tool generates XML schema or common language runtime classes from XDR, XML, and XSD files, or from classes in a runtime assembly.</span></span>

## <a name="syntax"></a><span data-ttu-id="28faa-104">構文</span><span class="sxs-lookup"><span data-stu-id="28faa-104">Syntax</span></span>

```
xsd file.xdr [/outputdir:directory][/parameters:file.xml]
xsd file.xml [/outputdir:directory] [/parameters:file.xml]
xsd file.xsd {/classes | /dataset} [/element:element]
             [/enableLinqDataSet] [/language:language]
                          [/namespace:namespace] [/outputdir:directory] [URI:uri]
                          [/parameters:file.xml]
xsd {file.dll | file.exe} [/outputdir:directory] [/type:typename [...]][/parameters:file.xml]
```

## <a name="argument"></a><span data-ttu-id="28faa-105">引数</span><span class="sxs-lookup"><span data-stu-id="28faa-105">Argument</span></span>

|<span data-ttu-id="28faa-106">引数</span><span class="sxs-lookup"><span data-stu-id="28faa-106">Argument</span></span>|<span data-ttu-id="28faa-107">説明</span><span class="sxs-lookup"><span data-stu-id="28faa-107">Description</span></span>|
|--------------|-----------------|
|<span data-ttu-id="28faa-108">*file.extension*</span><span class="sxs-lookup"><span data-stu-id="28faa-108">*file.extension*</span></span>|<span data-ttu-id="28faa-109">変換元の入力ファイルを指定します。</span><span class="sxs-lookup"><span data-stu-id="28faa-109">Specifies the input file to convert.</span></span> <span data-ttu-id="28faa-110">次の 1 つとして、拡張子を指定する必要があります: .xdr、.xml、.xsd、.dll または .exe です。</span><span class="sxs-lookup"><span data-stu-id="28faa-110">You must specify the extension as one of the following: .xdr, .xml, .xsd, .dll, or .exe.</span></span><br /><br /> <span data-ttu-id="28faa-111">XDR スキーマ ファイル (拡張子 .xdr) を指定すると、Xsd.exe は XDR スキーマを XSD スキーマに変換します。</span><span class="sxs-lookup"><span data-stu-id="28faa-111">If you specify an XDR schema file (.xdr extension), Xsd.exe converts the XDR schema to an XSD schema.</span></span> <span data-ttu-id="28faa-112">出力ファイルの名前は XDR スキーマと同じですが、拡張子は .xsd となります。</span><span class="sxs-lookup"><span data-stu-id="28faa-112">The output file has the same name as the XDR schema, but with the .xsd extension.</span></span><br /><br /> <span data-ttu-id="28faa-113">XML ファイル (拡張子 .xml) を指定すると、Xsd.exe はそのファイル内のデータからスキーマを推測して XSD スキーマを生成します。</span><span class="sxs-lookup"><span data-stu-id="28faa-113">If you specify an XML file (.xml extension), Xsd.exe infers a schema from the data in the file and produces an XSD schema.</span></span> <span data-ttu-id="28faa-114">出力ファイルの名前は XML ファイルと同じですが、拡張子は .xsd となります。</span><span class="sxs-lookup"><span data-stu-id="28faa-114">The output file has the same name as the XML file, but with the .xsd extension.</span></span><br /><br /> <span data-ttu-id="28faa-115">XML スキーマ ファイル (拡張子 .xsd) を指定すると、XML スキーマと対応するランタイム オブジェクト用のソース コードが生成されます。</span><span class="sxs-lookup"><span data-stu-id="28faa-115">If you specify an XML schema file (.xsd extension), Xsd.exe generates source code for runtime objects that correspond to the XML schema.</span></span><br /><br /> <span data-ttu-id="28faa-116">ランタイム アセンブリ ファイル (拡張子 .exe または .dll) を指定すると、そのアセンブリに含まれる 1 つ以上の型用のスキーマが生成されます。</span><span class="sxs-lookup"><span data-stu-id="28faa-116">If you specify a runtime assembly file (.exe or .dll extension), Xsd.exe generates schemas for one or more types in that assembly.</span></span> <span data-ttu-id="28faa-117">`/type` オプションを使用して、スキーマを生成する対象の型を指定できます。</span><span class="sxs-lookup"><span data-stu-id="28faa-117">You can use the `/type` option to specify the types for which to generate schemas.</span></span> <span data-ttu-id="28faa-118">出力スキーマには、schema0.xsd、schema1.xsd などの名前が付けられます。</span><span class="sxs-lookup"><span data-stu-id="28faa-118">The output schemas are named schema0.xsd, schema1.xsd, and so on.</span></span> <span data-ttu-id="28faa-119">Xsd.exe が複数のスキーマを生成するのは、指定した型によって、カスタム属性 `XMLRoot` を使用する名前空間が特定される場合のみです。</span><span class="sxs-lookup"><span data-stu-id="28faa-119">Xsd.exe produces multiple schemas only if the given types specify a namespace using the `XMLRoot` custom attribute.</span></span>|

## <a name="general-options"></a><span data-ttu-id="28faa-120">一般オプション</span><span class="sxs-lookup"><span data-stu-id="28faa-120">General Options</span></span>

|<span data-ttu-id="28faa-121">オプション</span><span class="sxs-lookup"><span data-stu-id="28faa-121">Option</span></span>|<span data-ttu-id="28faa-122">説明</span><span class="sxs-lookup"><span data-stu-id="28faa-122">Description</span></span>|
|------------|-----------------|
|<span data-ttu-id="28faa-123">**/h\[elp\]**</span><span class="sxs-lookup"><span data-stu-id="28faa-123">**/h\[elp\]**</span></span>|<span data-ttu-id="28faa-124">このツールのコマンド構文とオプションを表示します。</span><span class="sxs-lookup"><span data-stu-id="28faa-124">Displays command syntax and options for the tool.</span></span>|
|<span data-ttu-id="28faa-125">**/o\[utputdir\]:**_directory_</span><span class="sxs-lookup"><span data-stu-id="28faa-125">**/o\[utputdir\]:**_directory_</span></span>|<span data-ttu-id="28faa-126">出力ファイル用のディレクトリを指定します。</span><span class="sxs-lookup"><span data-stu-id="28faa-126">Specifies the directory for output files.</span></span> <span data-ttu-id="28faa-127">この引数は 1 回だけ指定できます。</span><span class="sxs-lookup"><span data-stu-id="28faa-127">This argument can appear only once.</span></span> <span data-ttu-id="28faa-128">既定値は、現在のディレクトリです。</span><span class="sxs-lookup"><span data-stu-id="28faa-128">The default is the current directory.</span></span>|
|<span data-ttu-id="28faa-129">**/?**</span><span class="sxs-lookup"><span data-stu-id="28faa-129">**/?**</span></span>|<span data-ttu-id="28faa-130">このツールのコマンド構文とオプションを表示します。</span><span class="sxs-lookup"><span data-stu-id="28faa-130">Displays command syntax and options for the tool.</span></span>|
|<span data-ttu-id="28faa-131">**/p\[arameters\]:**_file.xml_</span><span class="sxs-lookup"><span data-stu-id="28faa-131">**/p\[arameters\]:**_file.xml_</span></span>|<span data-ttu-id="28faa-132">指定された .xml ファイルから各種のオペレーション モードのためのオプションを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="28faa-132">Read options for various operation modes from the specified .xml file.</span></span> <span data-ttu-id="28faa-133">短縮形は `/p:` です。</span><span class="sxs-lookup"><span data-stu-id="28faa-133">The short form is `/p:`.</span></span> <span data-ttu-id="28faa-134">詳細については、次を参照してください。、[解説](#remarks)セクション。</span><span class="sxs-lookup"><span data-stu-id="28faa-134">For more information, see the [Remarks](#remarks) section.</span></span>|

## <a name="xsd-file-options"></a><span data-ttu-id="28faa-135">XSD ファイルのオプション</span><span class="sxs-lookup"><span data-stu-id="28faa-135">XSD File Options</span></span>
 <span data-ttu-id="28faa-136">.xsd ファイルについては、次のオプションのうち 1 つだけを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="28faa-136">You must specify only one of the following options for .xsd files.</span></span>

|<span data-ttu-id="28faa-137">オプション</span><span class="sxs-lookup"><span data-stu-id="28faa-137">Option</span></span>|<span data-ttu-id="28faa-138">説明</span><span class="sxs-lookup"><span data-stu-id="28faa-138">Description</span></span>|
|------------|-----------------|
|<span data-ttu-id="28faa-139">**/c\[lasses\]**</span><span class="sxs-lookup"><span data-stu-id="28faa-139">**/c\[lasses\]**</span></span>|<span data-ttu-id="28faa-140">指定したスキーマと対応するクラスを生成します。</span><span class="sxs-lookup"><span data-stu-id="28faa-140">Generates classes that correspond to the specified schema.</span></span> <span data-ttu-id="28faa-141">オブジェクトに XML データを読み込むには、<xref:System.Xml.Serialization.XmlSerializer.Deserialize%2A?displayProperty=nameWithType> メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="28faa-141">To read XML data into the object, use the <xref:System.Xml.Serialization.XmlSerializer.Deserialize%2A?displayProperty=nameWithType> method.</span></span>|
|<span data-ttu-id="28faa-142">**/d\[ataset\]**</span><span class="sxs-lookup"><span data-stu-id="28faa-142">**/d\[ataset\]**</span></span>|<span data-ttu-id="28faa-143">指定したスキーマに対応する <xref:System.Data.DataSet> から派生したクラスを生成します。</span><span class="sxs-lookup"><span data-stu-id="28faa-143">Generates a class derived from <xref:System.Data.DataSet> that corresponds to the specified schema.</span></span> <span data-ttu-id="28faa-144">派生したクラスに XML データを読み込むには、<xref:System.Data.DataSet.ReadXml%2A?displayProperty=nameWithType> メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="28faa-144">To read XML data into the derived class, use the <xref:System.Data.DataSet.ReadXml%2A?displayProperty=nameWithType> method.</span></span>|

 <span data-ttu-id="28faa-145">.xsd ファイルについては、次のオプションのうち任意のオプションを指定できます。</span><span class="sxs-lookup"><span data-stu-id="28faa-145">You can also specify any of the following options for .xsd files.</span></span>

|<span data-ttu-id="28faa-146">オプション</span><span class="sxs-lookup"><span data-stu-id="28faa-146">Option</span></span>|<span data-ttu-id="28faa-147">説明</span><span class="sxs-lookup"><span data-stu-id="28faa-147">Description</span></span>|
|------------|-----------------|
|<span data-ttu-id="28faa-148">**/e\[lement\]:**_要素_</span><span class="sxs-lookup"><span data-stu-id="28faa-148">**/e\[lement\]:**_element_</span></span>|<span data-ttu-id="28faa-149">コードを生成する対象とする、スキーマ内の要素を指定します。</span><span class="sxs-lookup"><span data-stu-id="28faa-149">Specifies the element in the schema to generate code for.</span></span> <span data-ttu-id="28faa-150">既定では、すべての要素が指定されます。</span><span class="sxs-lookup"><span data-stu-id="28faa-150">By default all elements are typed.</span></span> <span data-ttu-id="28faa-151">この引数は、複数回指定できます。</span><span class="sxs-lookup"><span data-stu-id="28faa-151">You can specify this argument more than once.</span></span>|
|<span data-ttu-id="28faa-152">**/enableDataBinding**</span><span class="sxs-lookup"><span data-stu-id="28faa-152">**/enableDataBinding**</span></span>|<span data-ttu-id="28faa-153">データ バインディングを有効にするために、生成されたすべての型に <xref:System.ComponentModel.INotifyPropertyChanged> インターフェイスを実装します。</span><span class="sxs-lookup"><span data-stu-id="28faa-153">Implements the <xref:System.ComponentModel.INotifyPropertyChanged> interface on all generated types to enable data binding.</span></span> <span data-ttu-id="28faa-154">短縮形は `/edb` です。</span><span class="sxs-lookup"><span data-stu-id="28faa-154">The short form is `/edb`.</span></span>|
|<span data-ttu-id="28faa-155">**/enableLinqDataSet**</span><span class="sxs-lookup"><span data-stu-id="28faa-155">**/enableLinqDataSet**</span></span>|<span data-ttu-id="28faa-156">(短縮形 : `/eld`)。LINQ to DataSet を使用して、生成された DataSet を照会できるように指定します。</span><span class="sxs-lookup"><span data-stu-id="28faa-156">(Short form: `/eld`.) Specifies that the generated DataSet can be queried against using LINQ to DataSet.</span></span> <span data-ttu-id="28faa-157">このオプションは /dataset オプションも指定した場合に使用されます。</span><span class="sxs-lookup"><span data-stu-id="28faa-157">This option is used when the /dataset option is also specified.</span></span> <span data-ttu-id="28faa-158">詳細については、「[LINQ to DataSet Overview](../../../docs/framework/data/adonet/linq-to-dataset-overview.md)」(LINQ to DataSet Overview) と「[Querying Typed DataSets](../../../docs/framework/data/adonet/querying-typed-datasets.md)」(型指定された DataSet のクエリ) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="28faa-158">For more information, see [LINQ to DataSet Overview](../../../docs/framework/data/adonet/linq-to-dataset-overview.md) and [Querying Typed DataSets](../../../docs/framework/data/adonet/querying-typed-datasets.md).</span></span> <span data-ttu-id="28faa-159">LINQ の使用に関する概要については、次を参照してください。[統合言語クエリ (LINQ) - C# ](../../csharp/programming-guide/concepts/linq/index.md)または[LINQ (Language-Integrated Query) - Visual Basic](../../visual-basic/programming-guide/concepts/linq/index.md)します。</span><span class="sxs-lookup"><span data-stu-id="28faa-159">For general information about using LINQ, see [Language-Integrated Query (LINQ) - C#](../../csharp/programming-guide/concepts/linq/index.md) or [Language-Integrated Query (LINQ) - Visual Basic](../../visual-basic/programming-guide/concepts/linq/index.md).</span></span>|
|<span data-ttu-id="28faa-160">**/f\[ields\]**</span><span class="sxs-lookup"><span data-stu-id="28faa-160">**/f\[ields\]**</span></span>|<span data-ttu-id="28faa-161">プロパティの代わりにフィールドを生成します。</span><span class="sxs-lookup"><span data-stu-id="28faa-161">Generates fields instead of properties.</span></span> <span data-ttu-id="28faa-162">既定では、プロパティが生成されます。</span><span class="sxs-lookup"><span data-stu-id="28faa-162">By default, properties are generated.</span></span>|
|<span data-ttu-id="28faa-163">**/l\[anguage\]:**_言語_</span><span class="sxs-lookup"><span data-stu-id="28faa-163">**/l\[anguage\]:**_language_</span></span>|<span data-ttu-id="28faa-164">使用するプログラミング言語を指定します。</span><span class="sxs-lookup"><span data-stu-id="28faa-164">Specifies the programming language to use.</span></span> <span data-ttu-id="28faa-165">`CS` (C#、既定値)、`VB` (Visual Basic)、`JS` (JScript)、または `VJS` (Visual J#) から選択します。</span><span class="sxs-lookup"><span data-stu-id="28faa-165">Choose from `CS` (C#, which is the default), `VB` (Visual Basic), `JS` (JScript), or `VJS` (Visual J#).</span></span> <span data-ttu-id="28faa-166"><xref:System.CodeDom.Compiler.CodeDomProvider?displayProperty=nameWithType> を実装するクラスの完全修飾名を指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="28faa-166">You can also specify a fully qualified name for a class implementing <xref:System.CodeDom.Compiler.CodeDomProvider?displayProperty=nameWithType></span></span>|
|<span data-ttu-id="28faa-167">**/n\[amespace\]:**_namespace_</span><span class="sxs-lookup"><span data-stu-id="28faa-167">**/n\[amespace\]:**_namespace_</span></span>|<span data-ttu-id="28faa-168">生成する型のランタイム名前空間を指定します。</span><span class="sxs-lookup"><span data-stu-id="28faa-168">Specifies the runtime namespace for the generated types.</span></span> <span data-ttu-id="28faa-169">既定の名前空間は `Schemas` です。</span><span class="sxs-lookup"><span data-stu-id="28faa-169">The default namespace is `Schemas`.</span></span>|
|<span data-ttu-id="28faa-170">**/nologo**</span><span class="sxs-lookup"><span data-stu-id="28faa-170">**/nologo**</span></span>|<span data-ttu-id="28faa-171">バナーを表示しません。</span><span class="sxs-lookup"><span data-stu-id="28faa-171">Suppresses the banner.</span></span>|
|<span data-ttu-id="28faa-172">**/order**</span><span class="sxs-lookup"><span data-stu-id="28faa-172">**/order**</span></span>|<span data-ttu-id="28faa-173">すべてのパーティクル メンバーに明示的な順序 ID を生成します。</span><span class="sxs-lookup"><span data-stu-id="28faa-173">Generates explicit order identifiers on all particle members.</span></span>|
|<span data-ttu-id="28faa-174">**/o\[ut\]:**_directoryName_</span><span class="sxs-lookup"><span data-stu-id="28faa-174">**/o\[ut\]:**_directoryName_</span></span>|<span data-ttu-id="28faa-175">ファイルを格納する出力ディレクトリを指定します。</span><span class="sxs-lookup"><span data-stu-id="28faa-175">Specifies the output directory to place the files in.</span></span> <span data-ttu-id="28faa-176">既定値は、現在のディレクトリです。</span><span class="sxs-lookup"><span data-stu-id="28faa-176">The default is the current directory.</span></span>|
|<span data-ttu-id="28faa-177">**/u\[ri\]:**_uri_</span><span class="sxs-lookup"><span data-stu-id="28faa-177">**/u\[ri\]:**_uri_</span></span>|<span data-ttu-id="28faa-178">コードを生成する対象とする、スキーマ内の要素の URI を指定します。</span><span class="sxs-lookup"><span data-stu-id="28faa-178">Specifies the URI for the elements in the schema to generate code for.</span></span> <span data-ttu-id="28faa-179">指定した場合、この URI は `/element` オプションで指定したすべての要素に適用されます。</span><span class="sxs-lookup"><span data-stu-id="28faa-179">This URI, if present, applies to all elements specified with the `/element` option.</span></span>|

## <a name="dll-and-exe-file-options"></a><span data-ttu-id="28faa-180">DLL ファイルと EXE ファイルのオプション</span><span class="sxs-lookup"><span data-stu-id="28faa-180">DLL and EXE File Options</span></span>

|<span data-ttu-id="28faa-181">オプション</span><span class="sxs-lookup"><span data-stu-id="28faa-181">Option</span></span>|<span data-ttu-id="28faa-182">説明</span><span class="sxs-lookup"><span data-stu-id="28faa-182">Description</span></span>|
|------------|-----------------|
|<span data-ttu-id="28faa-183">**/t\[ype\]:**_typename_</span><span class="sxs-lookup"><span data-stu-id="28faa-183">**/t\[ype\]:**_typename_</span></span>|<span data-ttu-id="28faa-184">スキーマの作成対象とする型の名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="28faa-184">Specifies the name of the type to create a schema for.</span></span> <span data-ttu-id="28faa-185">複数の型の引数を指定できます。</span><span class="sxs-lookup"><span data-stu-id="28faa-185">You can specify multiple type arguments.</span></span> <span data-ttu-id="28faa-186">*typename* によって名前空間が特定されない場合、指定された型を持つアセンブリに含まれるすべての型が対象となります。</span><span class="sxs-lookup"><span data-stu-id="28faa-186">If *typename* does not specify a namespace, Xsd.exe matches all types in the assembly with the specified type.</span></span> <span data-ttu-id="28faa-187">*typename* によって名前空間が特定される場合は、その型だけが対象になります。</span><span class="sxs-lookup"><span data-stu-id="28faa-187">If *typename* specifies a namespace, only that type is matched.</span></span> <span data-ttu-id="28faa-188">*typename* の末尾がアスタリスク (\*) の場合は、\* の前にある文字列で始まる型のすべてが対象となります。</span><span class="sxs-lookup"><span data-stu-id="28faa-188">If *typename* ends with an asterisk character (\*), the tool matches all types that start with the string preceding the \*.</span></span> <span data-ttu-id="28faa-189">`/type` オプションを省略すると、アセンブリに含まれるすべての型についてスキーマが生成されます。</span><span class="sxs-lookup"><span data-stu-id="28faa-189">If you omit the `/type` option, Xsd.exe generates schemas for all types in the assembly.</span></span>|

## <a name="remarks"></a><span data-ttu-id="28faa-190">Remarks</span><span class="sxs-lookup"><span data-stu-id="28faa-190">Remarks</span></span>

<span data-ttu-id="28faa-191">Xsd.exe が実行する操作を次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="28faa-191">The following table shows the operations that Xsd.exe performs.</span></span>

| | |
|------------|-----------------|
|<span data-ttu-id="28faa-192">XDR から XSD へ</span><span class="sxs-lookup"><span data-stu-id="28faa-192">XDR to XSD</span></span>|<span data-ttu-id="28faa-193">XML-Data-Reduced スキーマ ファイルから XML スキーマを生成します。</span><span class="sxs-lookup"><span data-stu-id="28faa-193">Generates an XML schema from an XML-Data-Reduced schema file.</span></span> <span data-ttu-id="28faa-194">XDR は初期の XML ベースのスキーマ形式です。</span><span class="sxs-lookup"><span data-stu-id="28faa-194">XDR is an early XML-based schema format.</span></span>|
|<span data-ttu-id="28faa-195">XML から XSD へ</span><span class="sxs-lookup"><span data-stu-id="28faa-195">XML to XSD</span></span>|<span data-ttu-id="28faa-196">XML ファイルから XML スキーマを生成します。</span><span class="sxs-lookup"><span data-stu-id="28faa-196">Generates an XML schema from an XML file.</span></span>|
|<span data-ttu-id="28faa-197">XSD から DataSet へ</span><span class="sxs-lookup"><span data-stu-id="28faa-197">XSD to DataSet</span></span>|<span data-ttu-id="28faa-198">XSD スキーマ ファイルから共通言語ランタイムの <xref:System.Data.DataSet> クラスを生成します。</span><span class="sxs-lookup"><span data-stu-id="28faa-198">Generates common language runtime <xref:System.Data.DataSet> classes from an XSD schema file.</span></span> <span data-ttu-id="28faa-199">生成されるクラスには、標準の XML データ用のリッチ オブジェクト モデルが用意されています。</span><span class="sxs-lookup"><span data-stu-id="28faa-199">The generated classes provide a rich object model for regular XML data.</span></span>|
|<span data-ttu-id="28faa-200">XSD からクラスへ</span><span class="sxs-lookup"><span data-stu-id="28faa-200">XSD to Classes</span></span>|<span data-ttu-id="28faa-201">XSD スキーマ ファイルからランタイム クラスを生成します。</span><span class="sxs-lookup"><span data-stu-id="28faa-201">Generates runtime classes from an XSD schema file.</span></span> <span data-ttu-id="28faa-202">生成されたクラスを <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType> と組み合わせて使用すると、このスキーマに従う XML コードの読み書きを実行できます。</span><span class="sxs-lookup"><span data-stu-id="28faa-202">The generated classes can be used in conjunction with <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType> to read and write XML code that follows the schema.</span></span>|
|<span data-ttu-id="28faa-203">クラスから XSD へ</span><span class="sxs-lookup"><span data-stu-id="28faa-203">Classes to XSD</span></span>| <span data-ttu-id="28faa-204">ランタイム アセンブリ ファイルに含まれる 1 つ以上の型から XML スキーマを生成します。</span><span class="sxs-lookup"><span data-stu-id="28faa-204">Generates an XML schema from a type or types in a runtime assembly file.</span></span> <span data-ttu-id="28faa-205">生成されたスキーマで使用される XML 形式の定義、<xref:System.Xml.Serialization.XmlSerializer>します。</span><span class="sxs-lookup"><span data-stu-id="28faa-205">The generated schema defines the XML format used by the <xref:System.Xml.Serialization.XmlSerializer>.</span></span>|

 <span data-ttu-id="28faa-206">Xsd.exe によって操作できるのは、W3C (World Wide Web Consortium) が提唱する XSD (XML スキーマ定義) に準拠した XML スキーマだけです。</span><span class="sxs-lookup"><span data-stu-id="28faa-206">Xsd.exe only allows you to manipulate XML schemas that follow the XML Schema Definition (XSD) language proposed by the World Wide Web Consortium (W3C).</span></span> <span data-ttu-id="28faa-207">XML スキーマ定義の提案や XML 標準の詳細については、次を参照してください。<https://w3.org>します。</span><span class="sxs-lookup"><span data-stu-id="28faa-207">For more information on the XML Schema Definition proposal or the XML standard, see <https://w3.org>.</span></span>

## <a name="setting-options-with-an-xml-file"></a><span data-ttu-id="28faa-208">XML ファイルによるオプションの設定</span><span class="sxs-lookup"><span data-stu-id="28faa-208">Setting Options with an XML File</span></span>

<span data-ttu-id="28faa-209">`/parameters` スイッチを使用すると、各種のオプションを設定する単一の XML ファイルを指定できます。</span><span class="sxs-lookup"><span data-stu-id="28faa-209">By using the `/parameters` switch, you can specify a single XML file that sets various options.</span></span> <span data-ttu-id="28faa-210">設定できるオプションは、XSD.exe ツールの使用方法によって異なります。</span><span class="sxs-lookup"><span data-stu-id="28faa-210">The options you can set depend on how you are using the XSD.exe tool.</span></span> <span data-ttu-id="28faa-211">選択肢には、スキーマの生成、コード ファイルの生成、または `DataSet` 機能を含むコード ファイルの生成があります。</span><span class="sxs-lookup"><span data-stu-id="28faa-211">Choices include generating schemas, generating code files, or generating code files that include `DataSet` features.</span></span> <span data-ttu-id="28faa-212">たとえば、コード ファイルではなくスキーマを生成する場合、実行可能ファイル (.exe) またはタイプ ライブラリ (.dll) ファイルの名前に `<assembly>` 要素を設定できます。</span><span class="sxs-lookup"><span data-stu-id="28faa-212">For example, you can set the `<assembly>` element to the name of an executable (.exe) or type library (.dll) file when generating a schema, but not when generating a code file.</span></span> <span data-ttu-id="28faa-213">次の XML に、指定された実行可能ファイルで `<generateSchemas>` 要素を使用する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="28faa-213">The following XML shows how to use the `<generateSchemas>` element with a specified executable:</span></span>

```xml
<!-- This is in a file named GenerateSchemas.xml. -->
<xsd xmlns='http://microsoft.com/dotnet/tools/xsd/'>
<generateSchemas>
   <assembly>ConsoleApplication1.exe</assembly>
</generateSchemas>
</xsd>
```

<span data-ttu-id="28faa-214">この XML が GenerateSchemas.xml というファイルに含まれる場合、コマンド プロンプトで、`/parameters` スイッチを使用して次のように入力し、Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="28faa-214">If the preceding XML is contained in a file named GenerateSchemas.xml, then use the `/parameters` switch by typing the following at a command prompt and pressing ENTER:</span></span>

```console
 xsd /p:GenerateSchemas.xml
```

<span data-ttu-id="28faa-215">アセンブリにある単一の型のスキーマを生成する場合は、次のような XML を使用します。</span><span class="sxs-lookup"><span data-stu-id="28faa-215">On the other hand, if you are generating a schema for a single type found in the assembly, you can use the following XML:</span></span>

```xml
<!-- This is in a file named GenerateSchemaFromType.xml. -->
<xsd xmlns='http://microsoft.com/dotnet/tools/xsd/'>
<generateSchemas>
   <type>IDItems</type>
</generateSchemas>
</xsd>
```

<span data-ttu-id="28faa-216">しかし、上のコードを使用するには、コマンド プロンプトでアセンブリの名前も指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="28faa-216">But to use preceding code, you must also supply the name of the assembly at the command prompt.</span></span> <span data-ttu-id="28faa-217">コマンド プロンプトで次のように入力します (XML ファイルの名前を GenerateSchemaFromType.xml と仮定します)。</span><span class="sxs-lookup"><span data-stu-id="28faa-217">Type the following at a command prompt (presuming the XML file is named GenerateSchemaFromType.xml):</span></span>

```console
xsd /p:GenerateSchemaFromType.xml ConsoleApplication1.exe
```

<span data-ttu-id="28faa-218">`<generateSchemas>` 要素に対しては、次のオプションのうち 1 つだけを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="28faa-218">You must specify only one of the following options for the `<generateSchemas>` element.</span></span>

|<span data-ttu-id="28faa-219">要素</span><span class="sxs-lookup"><span data-stu-id="28faa-219">Element</span></span>|<span data-ttu-id="28faa-220">説明</span><span class="sxs-lookup"><span data-stu-id="28faa-220">Description</span></span>|
|-------------|-----------------|
|<span data-ttu-id="28faa-221">\<assembly></span><span class="sxs-lookup"><span data-stu-id="28faa-221">\<assembly></span></span>|<span data-ttu-id="28faa-222">スキーマを生成するアセンブリを指定します。</span><span class="sxs-lookup"><span data-stu-id="28faa-222">Specifies an assembly to generate the schema from.</span></span>|
|<span data-ttu-id="28faa-223">\<type></span><span class="sxs-lookup"><span data-stu-id="28faa-223">\<type></span></span>|<span data-ttu-id="28faa-224">スキーマを生成するアセンブリに含まれる型を指定します。</span><span class="sxs-lookup"><span data-stu-id="28faa-224">Specifies a type found in an assembly to generate a schema for.</span></span>|
|<span data-ttu-id="28faa-225">\<xml></span><span class="sxs-lookup"><span data-stu-id="28faa-225">\<xml></span></span>|<span data-ttu-id="28faa-226">スキーマを生成する XML ファイルを指定します。</span><span class="sxs-lookup"><span data-stu-id="28faa-226">Specifies an XML file to generate a schema for.</span></span>|
|<span data-ttu-id="28faa-227">\<xdr></span><span class="sxs-lookup"><span data-stu-id="28faa-227">\<xdr></span></span>|<span data-ttu-id="28faa-228">スキーマを生成する XDR ファイルを指定します。</span><span class="sxs-lookup"><span data-stu-id="28faa-228">Specifies an XDR file to generate a schema for.</span></span>|

<span data-ttu-id="28faa-229">コード ファイルを生成するには、`<generateClasses>` 要素を使用します。</span><span class="sxs-lookup"><span data-stu-id="28faa-229">To generate a code file, use the `<generateClasses>` element.</span></span> <span data-ttu-id="28faa-230">コード ファイルを生成する例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="28faa-230">The following example generates a code file.</span></span> <span data-ttu-id="28faa-231">この例では、生成されるファイルのプログラミング言語と名前空間を設定するための 2 つの属性も示されています。</span><span class="sxs-lookup"><span data-stu-id="28faa-231">Note that two attributes are also shown that allow you to set the programming language and namespace of the generated file.</span></span>

```xml
<xsd xmlns='http://microsoft.com/dotnet/tools/xsd/'>
<generateClasses language='VB' namespace='Microsoft.Serialization.Examples'/>
</xsd>
<!-- You must supply an .xsd file when typing in the command line.-->
<!-- For example: xsd /p:genClasses mySchema.xsd -->
```

 <span data-ttu-id="28faa-232">`<generateClasses>` 要素に設定できるオプションは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="28faa-232">Options you can set for the `<generateClasses>` element include the following.</span></span>

|<span data-ttu-id="28faa-233">要素</span><span class="sxs-lookup"><span data-stu-id="28faa-233">Element</span></span>|<span data-ttu-id="28faa-234">説明</span><span class="sxs-lookup"><span data-stu-id="28faa-234">Description</span></span>|
|-------------|-----------------|
|<span data-ttu-id="28faa-235">\<element></span><span class="sxs-lookup"><span data-stu-id="28faa-235">\<element></span></span>|<span data-ttu-id="28faa-236">コードを生成する対象となる .xsd ファイルの要素を指定します。</span><span class="sxs-lookup"><span data-stu-id="28faa-236">Specifies an element in the .xsd file to generate code for.</span></span>|
|<span data-ttu-id="28faa-237">\<schemaImporterExtensions></span><span class="sxs-lookup"><span data-stu-id="28faa-237">\<schemaImporterExtensions></span></span>|<span data-ttu-id="28faa-238"><xref:System.Xml.Serialization.Advanced.SchemaImporterExtension> クラスから派生する型を指定します。</span><span class="sxs-lookup"><span data-stu-id="28faa-238">Specifies a type derived from the <xref:System.Xml.Serialization.Advanced.SchemaImporterExtension> class.</span></span>|
|<span data-ttu-id="28faa-239">\<schema></span><span class="sxs-lookup"><span data-stu-id="28faa-239">\<schema></span></span>|<span data-ttu-id="28faa-240">コードを生成する XML スキーマ ファイルを指定します。</span><span class="sxs-lookup"><span data-stu-id="28faa-240">Specifies a XML Schema file to generate code for.</span></span> <span data-ttu-id="28faa-241">複数の \<schema> 要素を使用して、複数の XML スキーマ ファイルを指定できます。</span><span class="sxs-lookup"><span data-stu-id="28faa-241">Multiple XML Schema files can be specified using multiple \<schema> elements.</span></span>|

<span data-ttu-id="28faa-242">次の表に、`<generateClasses>` 要素と共に使用するその他の属性を示します。</span><span class="sxs-lookup"><span data-stu-id="28faa-242">The following table shows the attributes that can also be used with the `<generateClasses>` element.</span></span>

|<span data-ttu-id="28faa-243">属性</span><span class="sxs-lookup"><span data-stu-id="28faa-243">Attribute</span></span>|<span data-ttu-id="28faa-244">説明</span><span class="sxs-lookup"><span data-stu-id="28faa-244">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="28faa-245">language</span><span class="sxs-lookup"><span data-stu-id="28faa-245">language</span></span>|<span data-ttu-id="28faa-246">使用するプログラミング言語を指定します。</span><span class="sxs-lookup"><span data-stu-id="28faa-246">Specifies the programming language to use.</span></span> <span data-ttu-id="28faa-247">`CS` (C#、既定値)、`VB` (Visual Basic)、`JS` (JScript)、または `VJS` (Visual J#) から選択します。</span><span class="sxs-lookup"><span data-stu-id="28faa-247">Choose from `CS` (C#, the default), `VB` (Visual Basic), `JS` (JScript), or `VJS` (Visual J#).</span></span> <span data-ttu-id="28faa-248"><xref:System.CodeDom.Compiler.CodeDomProvider> を実装するクラスの完全修飾名を指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="28faa-248">You can also specify a fully qualified name for a class that implements <xref:System.CodeDom.Compiler.CodeDomProvider>.</span></span>|
|<span data-ttu-id="28faa-249">namespace</span><span class="sxs-lookup"><span data-stu-id="28faa-249">namespace</span></span>|<span data-ttu-id="28faa-250">生成するコードの名前空間を指定します。</span><span class="sxs-lookup"><span data-stu-id="28faa-250">Specifies the namespace for the generated code.</span></span> <span data-ttu-id="28faa-251">名前空間は、スペースやバックスラッシュ文字を使用しないなどの CLR 標準に準拠する必要があります。</span><span class="sxs-lookup"><span data-stu-id="28faa-251">The namespace must conform to CLR standards (for example, no spaces or backslash characters).</span></span>|
|<span data-ttu-id="28faa-252">options</span><span class="sxs-lookup"><span data-stu-id="28faa-252">options</span></span>|<span data-ttu-id="28faa-253">`none`、`properties` (パブリック フィールドの代わりにプロパティを生成)、`order`、または `enableDataBinding` (前の「XSD ファイルのオプション」セクションの `/order` と `/enableDataBinding` スイッチを参照) のいずれかの値です。</span><span class="sxs-lookup"><span data-stu-id="28faa-253">One of the following values: `none`, `properties` (generates properties instead of public fields), `order`, or `enableDataBinding` (see the `/order` and `/enableDataBinding` switches in the preceding XSD File Options section.</span></span>|

 <span data-ttu-id="28faa-254">`DataSet` 要素を使用すると、`<generateDataSet>` コードを生成する方法を制御できます。</span><span class="sxs-lookup"><span data-stu-id="28faa-254">You can also control how `DataSet` code is generated by using the `<generateDataSet>` element.</span></span> <span data-ttu-id="28faa-255">次の XML では、生成されたコードが使用するように指定`DataSet`構造 (など、<xref:System.Data.DataTable>クラス) を指定した要素の Visual Basic コードを作成します。</span><span class="sxs-lookup"><span data-stu-id="28faa-255">The following XML specifies that the generated code uses `DataSet` structures (such as the <xref:System.Data.DataTable> class) to create Visual Basic code for a specified element.</span></span> <span data-ttu-id="28faa-256">生成された DataSet 構造体では LINQ クエリがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="28faa-256">The generated DataSet structures will support LINQ queries.</span></span>

 ```xml
 <xsd xmlns='http://microsoft.com/dotnet/tools/xsd/'>
     <generateDataSet language='VB' namespace='Microsoft.Serialization.Examples' enableLinqDataSet='true'>
     </generateDataSet>
 </xsd>
```

<span data-ttu-id="28faa-257">`<generateDataSet>` 要素に設定できるオプションは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="28faa-257">Options you can set for the `<generateDataSet>` element include the following.</span></span>

|<span data-ttu-id="28faa-258">要素</span><span class="sxs-lookup"><span data-stu-id="28faa-258">Element</span></span>|<span data-ttu-id="28faa-259">説明</span><span class="sxs-lookup"><span data-stu-id="28faa-259">Description</span></span>|
|-------------|-----------------|
|<span data-ttu-id="28faa-260">\<schema></span><span class="sxs-lookup"><span data-stu-id="28faa-260">\<schema></span></span>|<span data-ttu-id="28faa-261">コードを生成する XML スキーマ ファイルを指定します。</span><span class="sxs-lookup"><span data-stu-id="28faa-261">Specifies an XML Schema file to generate code for.</span></span> <span data-ttu-id="28faa-262">複数の \<schema> 要素を使用して、複数の XML スキーマ ファイルを指定できます。</span><span class="sxs-lookup"><span data-stu-id="28faa-262">Multiple XML Schema files can be specified using multiple \<schema> elements.</span></span>|

 <span data-ttu-id="28faa-263">`<generateDataSet>` 要素と共に使用できる属性を次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="28faa-263">The following table shows the attributes that can be used with the `<generateDataSet>` element.</span></span>

|<span data-ttu-id="28faa-264">属性</span><span class="sxs-lookup"><span data-stu-id="28faa-264">Attribute</span></span>|<span data-ttu-id="28faa-265">説明</span><span class="sxs-lookup"><span data-stu-id="28faa-265">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="28faa-266">enableLinqDataSet</span><span class="sxs-lookup"><span data-stu-id="28faa-266">enableLinqDataSet</span></span>|<span data-ttu-id="28faa-267">LINQ to DataSet を使用して、生成された DataSet を照会できるように指定します。</span><span class="sxs-lookup"><span data-stu-id="28faa-267">Specifies that the generated DataSet can be queried against using LINQ to DataSet.</span></span> <span data-ttu-id="28faa-268">既定値は false です。</span><span class="sxs-lookup"><span data-stu-id="28faa-268">The default value is false.</span></span>|
|<span data-ttu-id="28faa-269">language</span><span class="sxs-lookup"><span data-stu-id="28faa-269">language</span></span>|<span data-ttu-id="28faa-270">使用するプログラミング言語を指定します。</span><span class="sxs-lookup"><span data-stu-id="28faa-270">Specifies the programming language to use.</span></span> <span data-ttu-id="28faa-271">`CS` (C#、既定値)、`VB` (Visual Basic)、`JS` (JScript)、または `VJS` (Visual J#) から選択します。</span><span class="sxs-lookup"><span data-stu-id="28faa-271">Choose from `CS` (C#, the default), `VB` (Visual Basic), `JS` (JScript), or `VJS` (Visual J#).</span></span> <span data-ttu-id="28faa-272"><xref:System.CodeDom.Compiler.CodeDomProvider> を実装するクラスの完全修飾名を指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="28faa-272">You can also specify a fully qualified name for a class that implements <xref:System.CodeDom.Compiler.CodeDomProvider>.</span></span>|
|<span data-ttu-id="28faa-273">namespace</span><span class="sxs-lookup"><span data-stu-id="28faa-273">namespace</span></span>|<span data-ttu-id="28faa-274">生成するコードの名前空間を指定します。</span><span class="sxs-lookup"><span data-stu-id="28faa-274">Specifies the namespace for the generated code.</span></span> <span data-ttu-id="28faa-275">名前空間は、スペースやバックスラッシュ文字を使用しないなどの CLR 標準に準拠する必要があります。</span><span class="sxs-lookup"><span data-stu-id="28faa-275">The namespace must conform to CLR standards (for example, no spaces or backslash characters).</span></span>|

 <span data-ttu-id="28faa-276">トップ レベルの `<xsd>` 要素に設定できる属性があります。</span><span class="sxs-lookup"><span data-stu-id="28faa-276">There are attributes that you can set on the top level `<xsd>` element.</span></span> <span data-ttu-id="28faa-277">これらのオプションは、`<generateSchemas>`、`<generateClasses>`、または `<generateDataSet>` の各子要素と共に使用できます。</span><span class="sxs-lookup"><span data-stu-id="28faa-277">These options can be used with any of the child elements (`<generateSchemas>`, `<generateClasses>` or `<generateDataSet>`).</span></span> <span data-ttu-id="28faa-278">次の XML コードは、"MyOutputDirectory" という出力ディレクトリの "IDItems" という要素のコードを生成します。</span><span class="sxs-lookup"><span data-stu-id="28faa-278">The following XML code generates code for an element named "IDItems" in the output directory named "MyOutputDirectory".</span></span>

```xml
<xsd xmlns='http://microsoft.com/dotnet/tools/xsd/' output='MyOutputDirectory'>
<generateClasses>
    <element>IDItems</element>
</generateClasses>
</xsd>
```

<span data-ttu-id="28faa-279">次の表に、`<xsd>` 要素と共に使用するその他の属性を示します。</span><span class="sxs-lookup"><span data-stu-id="28faa-279">The following table shows the attributes that can also be used with the `<xsd>` element.</span></span>

|<span data-ttu-id="28faa-280">属性</span><span class="sxs-lookup"><span data-stu-id="28faa-280">Attribute</span></span>|<span data-ttu-id="28faa-281">説明</span><span class="sxs-lookup"><span data-stu-id="28faa-281">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="28faa-282">出力</span><span class="sxs-lookup"><span data-stu-id="28faa-282">output</span></span>|<span data-ttu-id="28faa-283">生成されたスキーマまたはコード ファイルが格納されるディレクトリの名前です。</span><span class="sxs-lookup"><span data-stu-id="28faa-283">The name of a directory where the generated schema or code file will be placed.</span></span>|
|<span data-ttu-id="28faa-284">nologo</span><span class="sxs-lookup"><span data-stu-id="28faa-284">nologo</span></span>|<span data-ttu-id="28faa-285">バナーを表示しません。</span><span class="sxs-lookup"><span data-stu-id="28faa-285">Suppresses the banner.</span></span> <span data-ttu-id="28faa-286">`true` または `false` に設定します。</span><span class="sxs-lookup"><span data-stu-id="28faa-286">Set to `true` or `false`.</span></span>|
|<span data-ttu-id="28faa-287">help</span><span class="sxs-lookup"><span data-stu-id="28faa-287">help</span></span>|<span data-ttu-id="28faa-288">このツールのコマンド構文とオプションを表示します。</span><span class="sxs-lookup"><span data-stu-id="28faa-288">Displays command syntax and options for the tool.</span></span> <span data-ttu-id="28faa-289">`true` または `false` に設定します。</span><span class="sxs-lookup"><span data-stu-id="28faa-289">Set to `true` or `false`.</span></span>|

## <a name="examples"></a><span data-ttu-id="28faa-290">使用例</span><span class="sxs-lookup"><span data-stu-id="28faa-290">Examples</span></span>
 <span data-ttu-id="28faa-291">`myFile.xdr` から XML スキーマを生成し、現在のディレクトリに保存するコマンドを次に示します。</span><span class="sxs-lookup"><span data-stu-id="28faa-291">The following command generates an XML schema from `myFile.xdr` and saves it to the current directory.</span></span>

```console
xsd myFile.xdr
```

<span data-ttu-id="28faa-292">`myFile.xml` から XML スキーマを生成し、指定したディレクトリに保存するコマンドを次に示します。</span><span class="sxs-lookup"><span data-stu-id="28faa-292">The following command generates an XML schema from `myFile.xml` and saves it to the specified directory.</span></span>

```console
xsd myFile.xml /outputdir:myOutputDir
```

<span data-ttu-id="28faa-293">指定したスキーマと対応するデータセットを C# 言語で生成し、現在のディレクトリ内に `XSDSchemaFile.cs` として保存するコマンドを次に示します。</span><span class="sxs-lookup"><span data-stu-id="28faa-293">The following command generates a data set that corresponds to the specified schema in the C# language and saves it as `XSDSchemaFile.cs` in the current directory.</span></span>

```console
xsd /dataset /language:CS XSDSchemaFile.xsd
```

<span data-ttu-id="28faa-294">`myAssembly.dll` アセンブリ内のすべての型について XML スキーマを生成し、それらを `schema0.xsd` として現在のディレクトリ内に保存するコマンドを次に示します。</span><span class="sxs-lookup"><span data-stu-id="28faa-294">The following command generates XML schemas for all types in the assembly `myAssembly.dll` and saves them as `schema0.xsd` in the current directory.</span></span>

```console
xsd myAssembly.dll
```

## <a name="see-also"></a><span data-ttu-id="28faa-295">関連項目</span><span class="sxs-lookup"><span data-stu-id="28faa-295">See also</span></span>

- <xref:System.Data.DataSet>
- <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType>
- [<span data-ttu-id="28faa-296">ツール</span><span class="sxs-lookup"><span data-stu-id="28faa-296">Tools</span></span>](../../../docs/framework/tools/index.md)
- [<span data-ttu-id="28faa-297">Visual Studio 用開発者コマンド プロンプト</span><span class="sxs-lookup"><span data-stu-id="28faa-297">Command Prompts</span></span>](../../../docs/framework/tools/developer-command-prompt-for-vs.md)
- [<span data-ttu-id="28faa-298">LINQ to DataSet の概要</span><span class="sxs-lookup"><span data-stu-id="28faa-298">LINQ to DataSet Overview</span></span>](../../../docs/framework/data/adonet/linq-to-dataset-overview.md)
- [<span data-ttu-id="28faa-299">型指定された DataSet のクエリ</span><span class="sxs-lookup"><span data-stu-id="28faa-299">Querying Typed DataSets</span></span>](../../../docs/framework/data/adonet/querying-typed-datasets.md)
- [<span data-ttu-id="28faa-300">LINQ (Language-integrated Query) (C#)</span><span class="sxs-lookup"><span data-stu-id="28faa-300">LINQ (Language-Integrated Query) (C#)</span></span>](../../csharp/programming-guide/concepts/linq/index.md)
- [<span data-ttu-id="28faa-301">LINQ (Language-integrated Query) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="28faa-301">LINQ (Language-Integrated Query) (Visual Basic)</span></span>](../../visual-basic/programming-guide/concepts/linq/index.md)
