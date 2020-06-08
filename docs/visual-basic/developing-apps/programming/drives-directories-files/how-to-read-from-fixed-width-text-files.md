---
title: '方法: 固定幅のテキスト ファイルを読み取る'
ms.date: 07/20/2015
helpviewer_keywords:
- fixed-width text file
- reading text files [Visual Basic], fixed-width
- files [Visual Basic], parsing
- text files [Visual Basic], tasks
- text files [Visual Basic], reading
ms.assetid: 99be5692-967a-4e85-993e-cd18139a5a69
ms.openlocfilehash: 77b2e0a4ebe36b68501f821ef5731935ee3b16a7
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2020
ms.locfileid: "84411630"
---
# <a name="how-to-read-from-fixed-width-text-files-in-visual-basic"></a><span data-ttu-id="ccae2-102">方法: Visual Basic で固定幅のテキスト ファイルを読み取る</span><span class="sxs-lookup"><span data-stu-id="ccae2-102">How to: read from fixed-width text files in Visual Basic</span></span>

<span data-ttu-id="ccae2-103">`TextFieldParser` オブジェクトには、構造化されたテキスト ファイル (ログなど) を簡単にかつ効率的に解析する方法が備わっています。</span><span class="sxs-lookup"><span data-stu-id="ccae2-103">The `TextFieldParser` object provides a way to easily and efficiently parse structured text files, such as logs.</span></span>  
  
 <span data-ttu-id="ccae2-104">解析対象のファイルが区切り形式であるか固定幅フィールドであるかは、`TextFieldType` プロパティで定義します。</span><span class="sxs-lookup"><span data-stu-id="ccae2-104">The `TextFieldType` property defines whether the parsed file is a delimited file or one that has fixed-width fields of text.</span></span> <span data-ttu-id="ccae2-105">固定幅のテキスト ファイルでは、最終フィールドを可変幅とすることができます。</span><span class="sxs-lookup"><span data-stu-id="ccae2-105">In a fixed-width text file, the field at the end can have a variable width.</span></span> <span data-ttu-id="ccae2-106">最後のフィールドを可変幅として指定するには、その幅に 0 以下の値を指定します。</span><span class="sxs-lookup"><span data-stu-id="ccae2-106">To specify that the field at the end has a variable width, define it to have a width less than or equal to zero.</span></span>  
  
### <a name="to-parse-a-fixed-width-text-file"></a><span data-ttu-id="ccae2-107">固定幅のテキスト ファイルを解析するには</span><span class="sxs-lookup"><span data-stu-id="ccae2-107">To parse a fixed-width text file</span></span>  
  
1. <span data-ttu-id="ccae2-108">新しい `TextFieldParser` を作成します。</span><span class="sxs-lookup"><span data-stu-id="ccae2-108">Create a new `TextFieldParser`.</span></span> <span data-ttu-id="ccae2-109">次のコードは、`Reader` という名前の `TextFieldParser` を作成し、`test.log` ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="ccae2-109">The following code creates the `TextFieldParser` named `Reader` and opens the file `test.log`.</span></span>  
  
     [!code-vb[VbFileIORead#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIORead/VB/Class1.vb#9)]  
  
2. <span data-ttu-id="ccae2-110">`TextFieldType` プロパティを `FixedWidth` として定義し、幅と形式を定義します。</span><span class="sxs-lookup"><span data-stu-id="ccae2-110">Define the `TextFieldType` property as `FixedWidth`, defining the width and format.</span></span> <span data-ttu-id="ccae2-111">次のコードでは、テキストの列を定義しています。先頭列の幅が 5 文字、2 列目が 10 文字、3 列目が 11 文字、そして 4 列目が可変幅です。</span><span class="sxs-lookup"><span data-stu-id="ccae2-111">The following code defines the columns of text; the first is 5 characters wide, the second 10, the third 11, and the fourth is of variable width.</span></span>  
  
     [!code-vb[VbFileIORead#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIORead/VB/Class1.vb#10)]  
  
3. <span data-ttu-id="ccae2-112">ファイル内のフィールドをループします。</span><span class="sxs-lookup"><span data-stu-id="ccae2-112">Loop through the fields in the file.</span></span> <span data-ttu-id="ccae2-113">破損している行が見つかった場合は、エラーを報告して解析を続行します。</span><span class="sxs-lookup"><span data-stu-id="ccae2-113">If any lines are corrupted, report an error and continue parsing.</span></span>  
  
     [!code-vb[VbFileIORead#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIORead/VB/Class1.vb#11)]  
  
4. <span data-ttu-id="ccae2-114">`While` ブロックと `Using` ブロックをそれぞれ `End While` と `End Using` で閉じます。</span><span class="sxs-lookup"><span data-stu-id="ccae2-114">Close the `While` and `Using` blocks with `End While` and `End Using`.</span></span>  
  
     [!code-vb[VbFileIORead#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIORead/VB/Class1.vb#12)]  
  
## <a name="example"></a><span data-ttu-id="ccae2-115">例</span><span class="sxs-lookup"><span data-stu-id="ccae2-115">Example</span></span>  

 <span data-ttu-id="ccae2-116">次のコードは、`test.log` ファイルから読み取りを行う例です。</span><span class="sxs-lookup"><span data-stu-id="ccae2-116">This example reads from the file `test.log`.</span></span>  
  
 [!code-vb[VbFileIORead#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIORead/VB/Class1.vb#13)]  
  
## <a name="robust-programming"></a><span data-ttu-id="ccae2-117">信頼性の高いプログラミング</span><span class="sxs-lookup"><span data-stu-id="ccae2-117">Robust programming</span></span>  

 <span data-ttu-id="ccae2-118">次の条件を満たす場合は、例外が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ccae2-118">The following conditions may cause an exception:</span></span>  
  
- <span data-ttu-id="ccae2-119">指定された形式で行を解析できない (<xref:Microsoft.VisualBasic.FileIO.MalformedLineException>)。</span><span class="sxs-lookup"><span data-stu-id="ccae2-119">A row cannot be parsed using the specified format (<xref:Microsoft.VisualBasic.FileIO.MalformedLineException>).</span></span> <span data-ttu-id="ccae2-120">例外の原因となった行が例外メッセージで報告され、その行に含まれているテキストには <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.ErrorLine%2A> プロパティが代入されます。</span><span class="sxs-lookup"><span data-stu-id="ccae2-120">The exception message specifies the line causing the exception, while the <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.ErrorLine%2A> property is assigned to the text contained in the line.</span></span>  
  
- <span data-ttu-id="ccae2-121">指定されたファイルが存在しない (<xref:System.IO.FileNotFoundException>)。</span><span class="sxs-lookup"><span data-stu-id="ccae2-121">The specified file does not exist (<xref:System.IO.FileNotFoundException>).</span></span>  
  
- <span data-ttu-id="ccae2-122">部分信頼の状況下で、ファイルにアクセスするために必要なアクセス許可がユーザーにない。</span><span class="sxs-lookup"><span data-stu-id="ccae2-122">A partial-trust situation in which the user does not have sufficient permissions to access the file.</span></span> <span data-ttu-id="ccae2-123">(<xref:System.Security.SecurityException>).</span><span class="sxs-lookup"><span data-stu-id="ccae2-123">(<xref:System.Security.SecurityException>).</span></span>  
  
- <span data-ttu-id="ccae2-124">パスが長すぎる (<xref:System.IO.PathTooLongException>)。</span><span class="sxs-lookup"><span data-stu-id="ccae2-124">The path is too long (<xref:System.IO.PathTooLongException>).</span></span>  
  
- <span data-ttu-id="ccae2-125">ファイルにアクセスする十分なアクセス許可がユーザーにない (<xref:System.UnauthorizedAccessException>)。</span><span class="sxs-lookup"><span data-stu-id="ccae2-125">The user does not have sufficient permissions to access the file (<xref:System.UnauthorizedAccessException>).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ccae2-126">参照</span><span class="sxs-lookup"><span data-stu-id="ccae2-126">See also</span></span>

- <xref:Microsoft.VisualBasic.FileIO.TextFieldParser?displayProperty=nameWithType>
- [<span data-ttu-id="ccae2-127">方法: コンマ区切りのテキスト ファイルを読み取る</span><span class="sxs-lookup"><span data-stu-id="ccae2-127">How to: Read From Comma-Delimited Text Files</span></span>](how-to-read-from-comma-delimited-text-files.md)
- [<span data-ttu-id="ccae2-128">方法: 複数の書式を持つテキスト ファイルを読み取る</span><span class="sxs-lookup"><span data-stu-id="ccae2-128">How to: Read From Text Files with Multiple Formats</span></span>](how-to-read-from-text-files-with-multiple-formats.md)
- [<span data-ttu-id="ccae2-129">TextFieldParser オブジェクトによるテキスト ファイルの解析</span><span class="sxs-lookup"><span data-stu-id="ccae2-129">Parsing Text Files with the TextFieldParser Object</span></span>](parsing-text-files-with-the-textfieldparser-object.md)
- [<span data-ttu-id="ccae2-130">チュートリアル: Visual Basic によるファイルとディレクトリの操作</span><span class="sxs-lookup"><span data-stu-id="ccae2-130">Walkthrough: Manipulating Files and Directories in Visual Basic</span></span>](walkthrough-manipulating-files-and-directories.md)
- [<span data-ttu-id="ccae2-131">トラブルシューティング : テキスト ファイルの読み取りと書き込み</span><span class="sxs-lookup"><span data-stu-id="ccae2-131">Troubleshooting: Reading from and Writing to Text Files</span></span>](troubleshooting-reading-from-and-writing-to-text-files.md)
