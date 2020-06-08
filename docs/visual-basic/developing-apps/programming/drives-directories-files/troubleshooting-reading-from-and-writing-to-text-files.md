---
title: 'トラブルシューティング: テキスト ファイルの読み取りと書き込み'
ms.date: 07/20/2015
helpviewer_keywords:
- troubleshooting file I/O
- writing text to files [Visual Basic], troubleshooting
- troubleshooting Visual Basic, text files
- I/O [Visual Basic], troubleshooting text files
- writing to files [Visual Basic], troubleshooting
- reading text files [Visual Basic], troubleshooting
ms.assetid: a8e9b44d-facb-4718-8c0f-466537171182
ms.openlocfilehash: 8af4160d09f39f2622a007aef793173d614a8b44
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2020
ms.locfileid: "84406626"
---
# <a name="troubleshooting-reading-from-and-writing-to-text-files-visual-basic"></a><span data-ttu-id="b863d-102">トラブルシューティング: テキスト ファイルの読み取りと書き込み (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b863d-102">Troubleshooting: reading from and writing to text files (Visual Basic)</span></span>

<span data-ttu-id="b863d-103">このトピックでは、テキスト ファイルを使用するときに発生する一般的な問題について説明し、それぞれの対処方法を示します。</span><span class="sxs-lookup"><span data-stu-id="b863d-103">This topic discusses common problems encountered when working with text files and suggests an approach to each.</span></span>  
  
## <a name="common-problems"></a><span data-ttu-id="b863d-104">一般的な問題</span><span class="sxs-lookup"><span data-stu-id="b863d-104">Common problems</span></span>  

 <span data-ttu-id="b863d-105">テキスト ファイルを使用するときに特によく発生する問題として、セキュリティ例外、ファイル エンコーディング、無効なパスがあります。</span><span class="sxs-lookup"><span data-stu-id="b863d-105">The most common issues encountered when working with text files include security exceptions, file encodings, or invalid paths.</span></span>  
  
### <a name="security-exceptions"></a><span data-ttu-id="b863d-106">セキュリティ例外</span><span class="sxs-lookup"><span data-stu-id="b863d-106">Security exceptions</span></span>  

 <span data-ttu-id="b863d-107">セキュリティ エラーが発生した場合、<xref:System.Security.SecurityException> がスローされます。</span><span class="sxs-lookup"><span data-stu-id="b863d-107">A <xref:System.Security.SecurityException> is thrown when a security error occurs.</span></span> <span data-ttu-id="b863d-108">この問題は、多くの場合、ユーザーに必要なアクセス許可がないことが原因で発生するため、アクセス許可を追加するか、分離ストレージでファイルを操作することで解決できます。</span><span class="sxs-lookup"><span data-stu-id="b863d-108">This is often a result of the user lacking necessary permissions, which may be solved by adding permissions or working with files in isolated storage.</span></span>  
  
### <a name="file-encodings"></a><span data-ttu-id="b863d-109">ファイル エンコーディング</span><span class="sxs-lookup"><span data-stu-id="b863d-109">File encodings</span></span>  

 <span data-ttu-id="b863d-110">ファイル エンコーディングは、文字エンコーディングとも呼ばれ、テキストを処理するときの文字の表現方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="b863d-110">File encodings, also known as character encodings, specify how to represent characters when text processing.</span></span> <span data-ttu-id="b863d-111">エンコーディングが誤っていると、テキスト ファイルに予期しない文字が含まれることがあります。</span><span class="sxs-lookup"><span data-stu-id="b863d-111">Unexpected characters in a text file may result from incorrect encoding.</span></span> <span data-ttu-id="b863d-112">ほとんどのファイルで、言語で処理できる (または処理できない) 文字という観点から、あるエンコードが他のエンコーディングよりも望ましいということがありますが、一般的には Unicode が好まれます。</span><span class="sxs-lookup"><span data-stu-id="b863d-112">For most files, one encoding may be preferable over another in terms of which language characters it can or cannot handle, although Unicode is usually preferred.</span></span> <span data-ttu-id="b863d-113">詳細については、[ファイル エンコーディング](file-encodings.md) および <xref:System.Text.Encoding> に関する各記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b863d-113">For more information, see [File Encodings](file-encodings.md) and <xref:System.Text.Encoding>.</span></span>  
  
### <a name="incorrect-paths"></a><span data-ttu-id="b863d-114">無効なパス</span><span class="sxs-lookup"><span data-stu-id="b863d-114">Incorrect paths</span></span>  

 <span data-ttu-id="b863d-115">ファイル パス (特に相対パス) を解析するときに、間違ったデータを指定してしまうことがよくあります。</span><span class="sxs-lookup"><span data-stu-id="b863d-115">When parsing file paths, particularly relative paths, it is easy to supply the wrong data.</span></span> <span data-ttu-id="b863d-116">正しいパスを指定しているかどうかを確認することで、問題の多くを解決できます。</span><span class="sxs-lookup"><span data-stu-id="b863d-116">Many problems can be corrected by making sure you are supplying the correct path.</span></span> <span data-ttu-id="b863d-117">詳細については、「[方法: ファイル パスを解析する](how-to-parse-file-paths.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b863d-117">For more information, see [How to: Parse File Paths](how-to-parse-file-paths.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b863d-118">参照</span><span class="sxs-lookup"><span data-stu-id="b863d-118">See also</span></span>

- <xref:Microsoft.VisualBasic.FileIO.FileSystem>
- [<span data-ttu-id="b863d-119">ファイルの読み取り</span><span class="sxs-lookup"><span data-stu-id="b863d-119">Reading from Files</span></span>](reading-from-files.md)
- [<span data-ttu-id="b863d-120">ファイルへの書き込み</span><span class="sxs-lookup"><span data-stu-id="b863d-120">Writing to Files</span></span>](writing-to-files.md)
- [<span data-ttu-id="b863d-121">TextFieldParser オブジェクトによるテキスト ファイルの解析</span><span class="sxs-lookup"><span data-stu-id="b863d-121">Parsing Text Files with the TextFieldParser Object</span></span>](parsing-text-files-with-the-textfieldparser-object.md)
