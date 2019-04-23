---
title: '方法: DBML ファイルおよび外部マッピング ファイルを検証する'
ms.date: 03/30/2017
ms.assetid: d9ea37f5-0a9e-4401-8fc3-1e6fd44c49f9
ms.openlocfilehash: 83a26f22495c849aa00143ca36b63fa147120c28
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59310240"
---
# <a name="how-to-validate-dbml-and-external-mapping-files"></a><span data-ttu-id="181bd-102">方法: DBML ファイルおよび外部マッピング ファイルを検証する</span><span class="sxs-lookup"><span data-stu-id="181bd-102">How to: Validate DBML and External Mapping Files</span></span>
<span data-ttu-id="181bd-103">変更した外部マッピング ファイルや .dbml ファイルは、それぞれのスキーマ定義に対して検証する必要があります。</span><span class="sxs-lookup"><span data-stu-id="181bd-103">External mapping files and .dbml files that you modify must be validated against their respective schema definitions.</span></span> <span data-ttu-id="181bd-104">このトピックでは、検証プロセスを実装する手順を Visual Studio のユーザーを提供します。</span><span class="sxs-lookup"><span data-stu-id="181bd-104">This topic provides Visual Studio users with the steps to implement the validation process.</span></span>  
  
 [!INCLUDE[note_settings_general](../../../../../../includes/note-settings-general-md.md)]  
  
### <a name="to-validate-a-dbml-or-xml-file"></a><span data-ttu-id="181bd-105">.dbml ファイルまたは XML ファイルを検証するには</span><span class="sxs-lookup"><span data-stu-id="181bd-105">To validate a .dbml or XML file</span></span>  
  
1. <span data-ttu-id="181bd-106">Visual Studio で**ファイル**メニューで、**オープン**、 をクリックし、**ファイル**。</span><span class="sxs-lookup"><span data-stu-id="181bd-106">On the Visual Studio **File** menu, point to **Open**, and then click **File**.</span></span>  
  
2. <span data-ttu-id="181bd-107">**ファイルを開く** ダイアログ ボックスで、.dbml ファイルまたは XML マッピング ファイルを検証する をクリックします。</span><span class="sxs-lookup"><span data-stu-id="181bd-107">In the **Open File** dialog box, click the .dbml or XML mapping file that you want to validate.</span></span>  
  
     <span data-ttu-id="181bd-108">ファイルが開きます、 **XML エディター**します。</span><span class="sxs-lookup"><span data-stu-id="181bd-108">The file opens in the **XML Editor**.</span></span>  
  
3. <span data-ttu-id="181bd-109">ウィンドウを右クリックし、クリックして**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="181bd-109">Right-click the window, and then click **Properties**.</span></span>  
  
4. <span data-ttu-id="181bd-110">**プロパティ** ウィンドウの省略記号をクリックして、**スキーマ**プロパティ。</span><span class="sxs-lookup"><span data-stu-id="181bd-110">In the **Properties** window, click the ellipsis for the **Schemas** property.</span></span>  
  
     <span data-ttu-id="181bd-111">**XML スキーマ** ダイアログ ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="181bd-111">The **XML Schemas** dialog box opens.</span></span>  
  
5. <span data-ttu-id="181bd-112">目的に適したスキーマ定義を見つけます。</span><span class="sxs-lookup"><span data-stu-id="181bd-112">Note the appropriate schema definition for your purpose.</span></span>  
  
    -   <span data-ttu-id="181bd-113">DbmlSchema.xsd は、.dbml ファイルを検証するためのスキーマ定義です。</span><span class="sxs-lookup"><span data-stu-id="181bd-113">DbmlSchema.xsd is the schema definition for validating a .dbml file.</span></span> <span data-ttu-id="181bd-114">詳細については、次を参照してください。 [LINQ to SQL でのコード生成](../../../../../../docs/framework/data/adonet/sql/linq/code-generation-in-linq-to-sql.md)します。</span><span class="sxs-lookup"><span data-stu-id="181bd-114">For more information, see [Code Generation in LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/code-generation-in-linq-to-sql.md).</span></span>  
  
    -   <span data-ttu-id="181bd-115">LinqToSqlMapping.xsd は、外部 XML マッピング ファイルを検証するためのスキーマ定義です。</span><span class="sxs-lookup"><span data-stu-id="181bd-115">LinqToSqlMapping.xsd is the schema definition for validating an external XML mapping file.</span></span> <span data-ttu-id="181bd-116">詳細については、次を参照してください。[外部マッピング](../../../../../../docs/framework/data/adonet/sql/linq/external-mapping.md)します。</span><span class="sxs-lookup"><span data-stu-id="181bd-116">For more information, see [External Mapping](../../../../../../docs/framework/data/adonet/sql/linq/external-mapping.md).</span></span>  
  
6. <span data-ttu-id="181bd-117">**使用**クリックして、ドロップ ダウン ボックスを開き、クリックして目的のスキーマ定義の行の列**このスキーマを使用して、** します。</span><span class="sxs-lookup"><span data-stu-id="181bd-117">In the **Use** column of the desired schema definition row, click to open the drop-down box, and then click **Use this schema**.</span></span>  
  
     <span data-ttu-id="181bd-118">これで、スキーマ定義ファイルが DBML ファイルまたは XML マッピング ファイルに関連付けられます。</span><span class="sxs-lookup"><span data-stu-id="181bd-118">The schema definition file is now associated with your DBML or XML mapping file.</span></span>  
  
     <span data-ttu-id="181bd-119">他のスキーマ定義は選択しないようにしてください。</span><span class="sxs-lookup"><span data-stu-id="181bd-119">Make sure no other schema definitions are selected.</span></span>  
  
7. <span data-ttu-id="181bd-120">**ビュー**  メニューのをクリックして**エラー一覧**します。</span><span class="sxs-lookup"><span data-stu-id="181bd-120">On the **View** menu, click **Error List**.</span></span>  
  
     <span data-ttu-id="181bd-121">エラー、警告、またはメッセージが生成されていないか確認します。</span><span class="sxs-lookup"><span data-stu-id="181bd-121">Determine whether errors, warnings, or messages have been generated.</span></span> <span data-ttu-id="181bd-122">生成されていなければ、XML ファイルはスキーマ定義に対して有効です。</span><span class="sxs-lookup"><span data-stu-id="181bd-122">If not, the XML file is valid against the schema definition.</span></span>  
  
## <a name="alternate-method-for-supplying-schema-definition"></a><span data-ttu-id="181bd-123">スキーマ定義を指定する別の方法</span><span class="sxs-lookup"><span data-stu-id="181bd-123">Alternate Method for Supplying Schema Definition</span></span>  
 <span data-ttu-id="181bd-124">何らかの理由により、適切な .xsd ファイルが表示されない場合に、 **XML スキーマ**ダイアログ ボックスで、ヘルプ トピックから .xsd ファイルをダウンロードすることができます。</span><span class="sxs-lookup"><span data-stu-id="181bd-124">If for some reason the appropriate .xsd file does not appear in the **XML Schemas** dialog box, you can download the .xsd file from a Help topic.</span></span> <span data-ttu-id="181bd-125">次の手順では、Visual Studio XML エディターによって必要な Unicode 形式でダウンロードしたファイルを保存できます。</span><span class="sxs-lookup"><span data-stu-id="181bd-125">The following steps help you save the downloaded file in the Unicode format required by the Visual Studio XML Editor.</span></span>  
  
#### <a name="to-copy-a-schema-definition-file-from-a-help-topic"></a><span data-ttu-id="181bd-126">スキーマ定義ファイルをヘルプ トピックからコピーするには</span><span class="sxs-lookup"><span data-stu-id="181bd-126">To copy a schema definition file from a Help topic</span></span>  
  
1. <span data-ttu-id="181bd-127">このトピックで既に説明したように、スキーマ定義が含まれているヘルプ トピックを表示します。</span><span class="sxs-lookup"><span data-stu-id="181bd-127">Locate the Help topic that contains the schema definition as described earlier in this topic.</span></span>  
  
    -   <span data-ttu-id="181bd-128">.Dbml ファイルでは、次を参照してください。 [LINQ to SQL でのコード生成](../../../../../../docs/framework/data/adonet/sql/linq/code-generation-in-linq-to-sql.md)します。</span><span class="sxs-lookup"><span data-stu-id="181bd-128">For .dbml files, see [Code Generation in LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/code-generation-in-linq-to-sql.md).</span></span>  
  
    -   <span data-ttu-id="181bd-129">外部マッピング ファイルでは、次を参照してください。[外部マッピング](../../../../../../docs/framework/data/adonet/sql/linq/external-mapping.md)します。</span><span class="sxs-lookup"><span data-stu-id="181bd-129">For external mapping files, see [External Mapping](../../../../../../docs/framework/data/adonet/sql/linq/external-mapping.md).</span></span>  
  
2. <span data-ttu-id="181bd-130">クリックして**コードのコピー**コード ファイルをクリップボードにコピーします。</span><span class="sxs-lookup"><span data-stu-id="181bd-130">Click **Copy Code** to copy the code file to the Clipboard.</span></span>  
  
3. <span data-ttu-id="181bd-131">メモ帳を起動して、新しいファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="181bd-131">Start Notepad to create a new file.</span></span>  
  
4. <span data-ttu-id="181bd-132">クリップボードからメモ帳のファイルにコードを貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="181bd-132">Paste the code from the clipboard into Notepad file.</span></span>  
  
5. <span data-ttu-id="181bd-133">メモ帳**ファイル** メニューのをクリックして**名前を付けて保存**します。</span><span class="sxs-lookup"><span data-stu-id="181bd-133">On the Notepad **File** menu, click **Save As**.</span></span>  
  
6. <span data-ttu-id="181bd-134">**エンコード**ボックスで、 **Unicode**します。</span><span class="sxs-lookup"><span data-stu-id="181bd-134">In the **Encoding** box, select **Unicode**.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="181bd-135">これを選択することで、テキスト ファイルの先頭に Unicode-16 のバイト順マーカー (`FFFE`) が追加されます。</span><span class="sxs-lookup"><span data-stu-id="181bd-135">This selection guarantees that the Unicode-16 byte-order marker (`FFFE`) is prepended to the text file.</span></span>  
  
7. <span data-ttu-id="181bd-136">**ファイル名**ボックスに、拡張子が .xsd でファイル名を作成します。</span><span class="sxs-lookup"><span data-stu-id="181bd-136">In the **File name** box, create a file name with an .xsd extension.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="181bd-137">関連項目</span><span class="sxs-lookup"><span data-stu-id="181bd-137">See also</span></span>

- [<span data-ttu-id="181bd-138">参照</span><span class="sxs-lookup"><span data-stu-id="181bd-138">Reference</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/reference.md)
