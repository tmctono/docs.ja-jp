---
title: '方法: OpenFileDialog コンポーネントでファイルを開く'
ms.date: 02/11/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- OpenFileDialog component [Windows Forms], opening files
- OpenFile method [Windows Forms], OpenFileDialog component
- files [Windows Forms], opening with OpenFileDialog component
ms.assetid: 9d88367a-cc21-4ffd-be74-89fd63767d35
ms.openlocfilehash: 7f4e96f1714a182647665f12e29d38f2b8037478
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61913459"
---
# <a name="how-to-open-files-with-the-openfiledialog"></a><span data-ttu-id="e1907-102">方法: それは、OpenFileDialog を開いているファイル</span><span class="sxs-lookup"><span data-stu-id="e1907-102">How to: Open files with the OpenFileDialog</span></span> 

<span data-ttu-id="e1907-103"><xref:System.Windows.Forms.OpenFileDialog?displayProperty=nameWithType>コンポーネントは、参照やファイルを選択する [Windows] ダイアログ ボックスを開きます。</span><span class="sxs-lookup"><span data-stu-id="e1907-103">The <xref:System.Windows.Forms.OpenFileDialog?displayProperty=nameWithType> component opens the Windows dialog box for browsing and selecting files.</span></span> <span data-ttu-id="e1907-104">開き、選択したファイルを読み取り、使用することができます、<xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A?displayProperty=nameWithType>メソッド、またはのインスタンスを作成、<xref:System.IO.StreamReader?displayProperty=nameWithType>クラス。</span><span class="sxs-lookup"><span data-stu-id="e1907-104">To open and read the selected files, you can use the <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A?displayProperty=nameWithType> method, or create an instance of the <xref:System.IO.StreamReader?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="e1907-105">次の例では、両方の方法を示します。</span><span class="sxs-lookup"><span data-stu-id="e1907-105">The following examples show both approaches.</span></span> 

<span data-ttu-id="e1907-106">.NET framework で取得または設定する、<xref:System.Windows.Forms.FileDialog.FileName%2A>プロパティには特権レベルが付与して、<xref:System.Security.Permissions.FileIOPermission?displayProperty=nameWithType>クラス。</span><span class="sxs-lookup"><span data-stu-id="e1907-106">In .NET Framework, to get or set the <xref:System.Windows.Forms.FileDialog.FileName%2A> property requires a privilege level granted by the <xref:System.Security.Permissions.FileIOPermission?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="e1907-107">例では、実行、<xref:System.Security.Permissions.FileIOPermission>アクセス許可を確認して、部分的に信頼されたコンテキストで実行する場合は、特権がないため例外をスローできます。</span><span class="sxs-lookup"><span data-stu-id="e1907-107">The examples run a <xref:System.Security.Permissions.FileIOPermission> permission check, and can throw an exception due to insufficient privileges if run in a partial-trust context.</span></span> <span data-ttu-id="e1907-108">詳細については、次を参照してください。[コード アクセス セキュリティの基礎](../../misc/code-access-security-basics.md)します。</span><span class="sxs-lookup"><span data-stu-id="e1907-108">For more information, see [Code access security basics](../../misc/code-access-security-basics.md).</span></span>

<span data-ttu-id="e1907-109">ビルドしてから、.NET Framework アプリとしてこれらの例を実行することができます、C#または Visual Basic のコマンド ライン。</span><span class="sxs-lookup"><span data-stu-id="e1907-109">You can build and run these examples as .NET Framework apps from the C# or Visual Basic command line.</span></span> <span data-ttu-id="e1907-110">詳細については、次を参照してください。 [csc.exe を](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)または[コマンドラインからビルド](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md)します。</span><span class="sxs-lookup"><span data-stu-id="e1907-110">For more information, see [Command-line building with csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md) or [Build from the command line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md).</span></span> 

<span data-ttu-id="e1907-111">.NET Core 3.0 以降では、ことができますもビルドおよび実行する例では、.NET Core アプリを Windows として .NET Core の Windows フォームのあるフォルダーから *\<フォルダー名>.csproj* プロジェクト ファイル。</span><span class="sxs-lookup"><span data-stu-id="e1907-111">Starting with .NET Core 3.0, you can also build and run the examples as Windows .NET Core apps from a folder that has a .NET Core Windows Forms *\<folder name>.csproj* project file.</span></span> 

## <a name="example-read-a-file-as-a-stream-with-streamreader"></a><span data-ttu-id="e1907-112">例:StreamReader とストリームとしてファイルを読み取り</span><span class="sxs-lookup"><span data-stu-id="e1907-112">Example: Read a file as a stream with StreamReader</span></span>  
  
<span data-ttu-id="e1907-113">次のコードの例では、Windows フォーム<xref:System.Windows.Forms.Button>コントロールの<xref:System.Windows.Forms.Control.Click>を開くイベント ハンドラー、<xref:System.Windows.Forms.OpenFileDialog>で、<xref:System.Windows.Forms.CommonDialog.ShowDialog%2A>メソッド。</span><span class="sxs-lookup"><span data-stu-id="e1907-113">The following example uses the Windows Forms <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Click> event handler to open the <xref:System.Windows.Forms.OpenFileDialog> with the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method.</span></span> <span data-ttu-id="e1907-114">ユーザーがファイルを選択し、選択した後**OK**のインスタンス、<xref:System.IO.StreamReader>クラス ファイルを読み取り、フォームのテキスト ボックスにその内容を表示します。</span><span class="sxs-lookup"><span data-stu-id="e1907-114">After the user chooses a file and selects **OK**, an instance of the <xref:System.IO.StreamReader> class reads the file and displays its contents in the form's text box.</span></span> <span data-ttu-id="e1907-115">ファイル ストリームからの読み取りの詳細については、次を参照してください。<xref:System.IO.FileStream.BeginRead%2A?displayProperty=nameWithType>と<xref:System.IO.FileStream.Read%2A?displayProperty=nameWithType>します。</span><span class="sxs-lookup"><span data-stu-id="e1907-115">For more information about reading from file streams, see <xref:System.IO.FileStream.BeginRead%2A?displayProperty=nameWithType> and <xref:System.IO.FileStream.Read%2A?displayProperty=nameWithType>.</span></span>  

 [!code-csharp[OpenFileDialog#1](~/samples/snippets/winforms/open-files/example1/cs/Form1.cs)]
 [!code-vb[OpenFileDialog#1](~/samples/snippets/winforms/open-files/example1/vb/Form1.vb)]  

## <a name="example-open-a-file-from-a-filtered-selection-with-openfile"></a><span data-ttu-id="e1907-116">例:選択されている OpenFile フィルター選択された項目からファイルを開く</span><span class="sxs-lookup"><span data-stu-id="e1907-116">Example: Open a file from a filtered selection with OpenFile</span></span> 

<span data-ttu-id="e1907-117">次の例では、<xref:System.Windows.Forms.Button>コントロールの<xref:System.Windows.Forms.Control.Click>を開くイベント ハンドラー、<xref:System.Windows.Forms.OpenFileDialog>はテキスト ファイルのみを表示するフィルター。</span><span class="sxs-lookup"><span data-stu-id="e1907-117">The following example uses the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Click> event handler to open the <xref:System.Windows.Forms.OpenFileDialog> with a filter that shows only text files.</span></span> <span data-ttu-id="e1907-118">ユーザーがテキスト ファイルを選択し、選択した後**OK**、<xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A>メソッドを使用して、メモ帳でファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="e1907-118">After the user chooses a text file and selects **OK**, the <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A> method is used to open the file in Notepad.</span></span>

 [!code-csharp[OpenFileDialog#2](~/samples/snippets/winforms/open-files/example2/cs/Form1.cs)]
 [!code-vb[OpenFileDialog#2](~/samples/snippets/winforms/open-files/example2/vb/Form1.vb)]  

## <a name="see-also"></a><span data-ttu-id="e1907-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="e1907-119">See also</span></span>

- <xref:System.Windows.Forms.OpenFileDialog>
- [<span data-ttu-id="e1907-120">OpenFileDialog コンポーネント</span><span class="sxs-lookup"><span data-stu-id="e1907-120">OpenFileDialog component</span></span>](openfiledialog-component-windows-forms.md)
