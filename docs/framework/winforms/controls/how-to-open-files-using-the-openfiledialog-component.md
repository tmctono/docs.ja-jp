---
title: '方法: ファイルを開くダイアログ コンポーネントを使用してファイルを開く'
ms.date: 02/11/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- OpenFileDialog component [Windows Forms], opening files
- OpenFile method [Windows Forms], OpenFileDialog component
- files [Windows Forms], opening with OpenFileDialog component
ms.assetid: 9d88367a-cc21-4ffd-be74-89fd63767d35
ms.openlocfilehash: ca69de19ab1b9ae387002898145fe99e35a7b6b9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182128"
---
# <a name="how-to-open-files-with-the-openfiledialog"></a><span data-ttu-id="bf7bf-102">方法 : ファイルを開くダイアログ ボックスでファイルを開く</span><span class="sxs-lookup"><span data-stu-id="bf7bf-102">How to: Open files with the OpenFileDialog</span></span>

<span data-ttu-id="bf7bf-103">この<xref:System.Windows.Forms.OpenFileDialog?displayProperty=nameWithType>コンポーネントは、ファイルの参照と選択を行うための Windows ダイアログ ボックスを開きます。</span><span class="sxs-lookup"><span data-stu-id="bf7bf-103">The <xref:System.Windows.Forms.OpenFileDialog?displayProperty=nameWithType> component opens the Windows dialog box for browsing and selecting files.</span></span> <span data-ttu-id="bf7bf-104">選択したファイルを開いて読み取るために、メソッド<xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A?displayProperty=nameWithType>を使用するか、クラスのインスタンスを<xref:System.IO.StreamReader?displayProperty=nameWithType>作成します。</span><span class="sxs-lookup"><span data-stu-id="bf7bf-104">To open and read the selected files, you can use the <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A?displayProperty=nameWithType> method, or create an instance of the <xref:System.IO.StreamReader?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="bf7bf-105">次の例は、両方の方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="bf7bf-105">The following examples show both approaches.</span></span>

<span data-ttu-id="bf7bf-106">.NET Framework では、プロパティを取得<xref:System.Windows.Forms.FileDialog.FileName%2A>または設定するには、クラスによって付与される<xref:System.Security.Permissions.FileIOPermission?displayProperty=nameWithType>特権レベルが必要です。</span><span class="sxs-lookup"><span data-stu-id="bf7bf-106">In .NET Framework, to get or set the <xref:System.Windows.Forms.FileDialog.FileName%2A> property requires a privilege level granted by the <xref:System.Security.Permissions.FileIOPermission?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="bf7bf-107">この例では、<xref:System.Security.Permissions.FileIOPermission>アクセス許可チェックを実行し、部分信頼コンテキストで実行すると、特権が不十分なために例外をスローできます。</span><span class="sxs-lookup"><span data-stu-id="bf7bf-107">The examples run a <xref:System.Security.Permissions.FileIOPermission> permission check, and can throw an exception due to insufficient privileges if run in a partial-trust context.</span></span> <span data-ttu-id="bf7bf-108">詳細については、「コード[アクセス セキュリティの基本](../../misc/code-access-security-basics.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bf7bf-108">For more information, see [Code access security basics](../../misc/code-access-security-basics.md).</span></span>

<span data-ttu-id="bf7bf-109">これらの例は、C# または Visual Basic のコマンド ラインから .NET Framework アプリとしてビルドして実行できます。</span><span class="sxs-lookup"><span data-stu-id="bf7bf-109">You can build and run these examples as .NET Framework apps from the C# or Visual Basic command line.</span></span> <span data-ttu-id="bf7bf-110">詳細については、「 [csc.exe を使用したコマンド ラインビルド](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)」または「[コマンド ラインからのビルド](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bf7bf-110">For more information, see [Command-line building with csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md) or [Build from the command line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md).</span></span>

<span data-ttu-id="bf7bf-111">NET Core 3.0 以降では、.NET Core Windows フォーム*\<フォルダー名>.csproj*プロジェクト ファイルを持つフォルダーから Windows .NET Core アプリとしてサンプルをビルドして実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="bf7bf-111">Starting with .NET Core 3.0, you can also build and run the examples as Windows .NET Core apps from a folder that has a .NET Core Windows Forms *\<folder name>.csproj* project file.</span></span>

## <a name="example-read-a-file-as-a-stream-with-streamreader"></a><span data-ttu-id="bf7bf-112">例: ストリームリーダーを使用してファイルをストリームとして読み取る</span><span class="sxs-lookup"><span data-stu-id="bf7bf-112">Example: Read a file as a stream with StreamReader</span></span>  
  
<span data-ttu-id="bf7bf-113">次の例では、Windows<xref:System.Windows.Forms.Button>フォーム コントロール<xref:System.Windows.Forms.Control.Click>のイベント ハンドラーを<xref:System.Windows.Forms.OpenFileDialog>使用して<xref:System.Windows.Forms.CommonDialog.ShowDialog%2A>、メソッドを使用して を開きます。</span><span class="sxs-lookup"><span data-stu-id="bf7bf-113">The following example uses the Windows Forms <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Click> event handler to open the <xref:System.Windows.Forms.OpenFileDialog> with the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method.</span></span> <span data-ttu-id="bf7bf-114">ユーザーがファイルを選択して **[OK] を**選択すると、クラス<xref:System.IO.StreamReader>のインスタンスがファイルを読み取り、フォームのテキスト ボックスに内容を表示します。</span><span class="sxs-lookup"><span data-stu-id="bf7bf-114">After the user chooses a file and selects **OK**, an instance of the <xref:System.IO.StreamReader> class reads the file and displays its contents in the form's text box.</span></span> <span data-ttu-id="bf7bf-115">ファイル ストリームからの読み取りの詳細<xref:System.IO.FileStream.BeginRead%2A?displayProperty=nameWithType>については<xref:System.IO.FileStream.Read%2A?displayProperty=nameWithType>、 および を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bf7bf-115">For more information about reading from file streams, see <xref:System.IO.FileStream.BeginRead%2A?displayProperty=nameWithType> and <xref:System.IO.FileStream.Read%2A?displayProperty=nameWithType>.</span></span>  

 [!code-csharp[OpenFileDialog#1](~/samples/snippets/winforms/open-files/example1/cs/Form1.cs)]
 [!code-vb[OpenFileDialog#1](~/samples/snippets/winforms/open-files/example1/vb/Form1.vb)]  

## <a name="example-open-a-file-from-a-filtered-selection-with-openfile"></a><span data-ttu-id="bf7bf-116">例: OpenFile を使用して、フィルター選択されたファイルを開く</span><span class="sxs-lookup"><span data-stu-id="bf7bf-116">Example: Open a file from a filtered selection with OpenFile</span></span>

<span data-ttu-id="bf7bf-117">次の例では、<xref:System.Windows.Forms.Button>コントロールの<xref:System.Windows.Forms.Control.Click>イベント ハンドラーを使用して<xref:System.Windows.Forms.OpenFileDialog>、テキスト ファイルのみを表示するフィルターを使用して を開きます。</span><span class="sxs-lookup"><span data-stu-id="bf7bf-117">The following example uses the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Click> event handler to open the <xref:System.Windows.Forms.OpenFileDialog> with a filter that shows only text files.</span></span> <span data-ttu-id="bf7bf-118">ユーザーがテキスト ファイルを選択し、[ **OK**]<xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A>を選択すると、このメソッドを使用してメモ帳でファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="bf7bf-118">After the user chooses a text file and selects **OK**, the <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A> method is used to open the file in Notepad.</span></span>

 [!code-csharp[OpenFileDialog#2](~/samples/snippets/winforms/open-files/example2/cs/Form1.cs)]
 [!code-vb[OpenFileDialog#2](~/samples/snippets/winforms/open-files/example2/vb/Form1.vb)]  

## <a name="see-also"></a><span data-ttu-id="bf7bf-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="bf7bf-119">See also</span></span>

- <xref:System.Windows.Forms.OpenFileDialog>
- [<span data-ttu-id="bf7bf-120">コンポーネントを開きます。</span><span class="sxs-lookup"><span data-stu-id="bf7bf-120">OpenFileDialog component</span></span>](openfiledialog-component-windows-forms.md)
