---
title: '方法: Visual Basic でコンマ区切りのテキスト ファイルを読み取る'
ms.date: 07/20/2015
helpviewer_keywords:
- files [Visual Basic], parsing
- text files [Visual Basic], tasks
- reading text files [Visual Basic], comma-delimited
- text files [Visual Basic], reading
ms.assetid: a8413fe4-0dba-49c8-8692-44fb67a9ec4f
ms.openlocfilehash: 8b9faaad2abaa0d551304ff03f8212bd535eda58
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64623236"
---
# <a name="how-to-read-from-comma-delimited-text-files-in-visual-basic"></a><span data-ttu-id="0bec4-102">方法: Visual Basic でコンマ区切りのテキスト ファイルを読み取る</span><span class="sxs-lookup"><span data-stu-id="0bec4-102">How to: read from comma-delimited text files in Visual Basic</span></span>
<span data-ttu-id="0bec4-103">`TextFieldParser` オブジェクトには、構造化されたテキスト ファイル (ログなど) を簡単にかつ効率的に解析する方法が備わっています。</span><span class="sxs-lookup"><span data-stu-id="0bec4-103">The `TextFieldParser` object provides a way to easily and efficiently parse structured text files, such as logs.</span></span> <span data-ttu-id="0bec4-104">区切り形式のファイルか、固定幅フィールドのテキストを使用したファイルかは、`TextFieldType` プロパティで定義します。</span><span class="sxs-lookup"><span data-stu-id="0bec4-104">The `TextFieldType` property defines whether it is a delimited file or one with fixed-width fields of text.</span></span>  
  
### <a name="to-parse-a-comma-delimited-text-file"></a><span data-ttu-id="0bec4-105">コンマ区切りテキスト ファイルを解析するには</span><span class="sxs-lookup"><span data-stu-id="0bec4-105">To parse a comma delimited text file</span></span>  
  
1. <span data-ttu-id="0bec4-106">新規の `TextFieldParser` を作成します。</span><span class="sxs-lookup"><span data-stu-id="0bec4-106">Create a new `TextFieldParser`.</span></span> <span data-ttu-id="0bec4-107">次のコードは、`MyReader` という名前の `TextFieldParser` を作成し、`test.txt` ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="0bec4-107">The following code creates the `TextFieldParser` named `MyReader` and opens the file `test.txt`.</span></span>  
  
     [!code-vb[VbFileIORead#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIORead/VB/Class1.vb#15)]  
  
2. <span data-ttu-id="0bec4-108">`TextField` 型と区切り記号を定義します。</span><span class="sxs-lookup"><span data-stu-id="0bec4-108">Define the `TextField` type and delimiter.</span></span> <span data-ttu-id="0bec4-109">次のコードは、`TextFieldType` プロパティを `Delimited`、区切り記号を "," として定義します。</span><span class="sxs-lookup"><span data-stu-id="0bec4-109">The following code defines the `TextFieldType` property as `Delimited` and the delimiter as ",".</span></span>  
  
     [!code-vb[VbFileIORead#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIORead/VB/Class1.vb#16)]  
  
3. <span data-ttu-id="0bec4-110">ファイル内のフィールドをループします。</span><span class="sxs-lookup"><span data-stu-id="0bec4-110">Loop through the fields in the file.</span></span> <span data-ttu-id="0bec4-111">破損している行が見つかった場合は、エラーを報告して解析を続行します。</span><span class="sxs-lookup"><span data-stu-id="0bec4-111">If any lines are corrupt, report an error and continue parsing.</span></span> <span data-ttu-id="0bec4-112">次のコードは、ファイル内をループし、各フィールド順次表示して、不正にフォーマットされているフィールドをレポートします。</span><span class="sxs-lookup"><span data-stu-id="0bec4-112">The following code loops through the file, displaying each field in turn and reporting any fields that are formatted incorrectly.</span></span>  
  
     [!code-vb[VbFileIORead#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIORead/VB/Class1.vb#17)]  
  
4. <span data-ttu-id="0bec4-113">`While` ブロックと `Using` ブロックをそれぞれ `End While` と `End Using` で閉じます。</span><span class="sxs-lookup"><span data-stu-id="0bec4-113">Close the `While` and `Using` blocks with `End While` and `End Using`.</span></span>  
  
     [!code-vb[VbFileIORead#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIORead/VB/Class1.vb#18)]  
  
## <a name="example"></a><span data-ttu-id="0bec4-114">例</span><span class="sxs-lookup"><span data-stu-id="0bec4-114">Example</span></span>  
 <span data-ttu-id="0bec4-115">次のコードは、`test.txt` ファイルから読み取りを行う例です。</span><span class="sxs-lookup"><span data-stu-id="0bec4-115">This example reads from the file `test.txt`.</span></span>  
  
 [!code-vb[VbFileIORead#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIORead/VB/Class1.vb#19)]  
  
## <a name="robust-programming"></a><span data-ttu-id="0bec4-116">信頼性の高いプログラミング</span><span class="sxs-lookup"><span data-stu-id="0bec4-116">Robust programming</span></span>  
 <span data-ttu-id="0bec4-117">次の条件を満たす場合は、例外が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="0bec4-117">The following conditions may cause an exception:</span></span>  
  
- <span data-ttu-id="0bec4-118">指定された形式で行を解析できない (<xref:Microsoft.VisualBasic.FileIO.MalformedLineException>)。</span><span class="sxs-lookup"><span data-stu-id="0bec4-118">A row cannot be parsed using the specified format (<xref:Microsoft.VisualBasic.FileIO.MalformedLineException>).</span></span> <span data-ttu-id="0bec4-119">例外の原因となった行が例外メッセージで報告され、その行に含まれているテキストには <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.ErrorLine%2A> プロパティが代入されます。</span><span class="sxs-lookup"><span data-stu-id="0bec4-119">The exception message specifies the line causing the exception, while the <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.ErrorLine%2A> property is assigned the text contained in the line.</span></span>  
  
- <span data-ttu-id="0bec4-120">指定されたファイルが存在しない (<xref:System.IO.FileNotFoundException>)。</span><span class="sxs-lookup"><span data-stu-id="0bec4-120">The specified file does not exist (<xref:System.IO.FileNotFoundException>).</span></span>  
  
- <span data-ttu-id="0bec4-121">部分信頼の状況下で、ファイルにアクセスするために必要なアクセス許可がユーザーにない。</span><span class="sxs-lookup"><span data-stu-id="0bec4-121">A partial-trust situation in which the user does not have sufficient permissions to access the file.</span></span> <span data-ttu-id="0bec4-122">(<xref:System.Security.SecurityException>).</span><span class="sxs-lookup"><span data-stu-id="0bec4-122">(<xref:System.Security.SecurityException>).</span></span>  
  
- <span data-ttu-id="0bec4-123">パスが長すぎる (<xref:System.IO.PathTooLongException>)。</span><span class="sxs-lookup"><span data-stu-id="0bec4-123">The path is too long (<xref:System.IO.PathTooLongException>).</span></span>  
  
- <span data-ttu-id="0bec4-124">ファイルにアクセスする十分なアクセス許可がユーザーにない (<xref:System.UnauthorizedAccessException>)。</span><span class="sxs-lookup"><span data-stu-id="0bec4-124">The user does not have sufficient permissions to access the file (<xref:System.UnauthorizedAccessException>).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0bec4-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="0bec4-125">See also</span></span>

- <xref:Microsoft.VisualBasic.FileIO.TextFieldParser?displayProperty=nameWithType>
- [<span data-ttu-id="0bec4-126">方法: 固定幅のテキスト ファイルを読み取る</span><span class="sxs-lookup"><span data-stu-id="0bec4-126">How to: Read From Fixed-width Text Files</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-fixed-width-text-files.md)
- [<span data-ttu-id="0bec4-127">方法: 複数の書式を持つテキスト ファイルを読み取る</span><span class="sxs-lookup"><span data-stu-id="0bec4-127">How to: Read From Text Files with Multiple Formats</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-text-files-with-multiple-formats.md)
- [<span data-ttu-id="0bec4-128">TextFieldParser オブジェクトによるテキスト ファイルの解析</span><span class="sxs-lookup"><span data-stu-id="0bec4-128">Parsing Text Files with the TextFieldParser Object</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/parsing-text-files-with-the-textfieldparser-object.md)
- [<span data-ttu-id="0bec4-129">チュートリアル: Visual Basic によるファイルとディレクトリの操作</span><span class="sxs-lookup"><span data-stu-id="0bec4-129">Walkthrough: Manipulating Files and Directories in Visual Basic</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/walkthrough-manipulating-files-and-directories.md)
- [<span data-ttu-id="0bec4-130">トラブルシューティング : テキスト ファイルの読み取りと書き込み</span><span class="sxs-lookup"><span data-stu-id="0bec4-130">Troubleshooting: Reading from and Writing to Text Files</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/troubleshooting-reading-from-and-writing-to-text-files.md)
