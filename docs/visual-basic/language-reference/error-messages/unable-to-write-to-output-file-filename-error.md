---
title: "出力ファイル '<filename>' に書き込めません : <error>"
ms.date: 07/20/2015
f1_keywords:
- vbc31019
- bc31019
helpviewer_keywords:
- BC31019
ms.assetid: 0845b245-11bb-46fd-95ca-f6cef3c318ef
ms.openlocfilehash: e0a00c4f57e45d65ff46fb9487a603a67d5a9e5c
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64620596"
---
# <a name="unable-to-write-to-output-file-filename-error"></a><span data-ttu-id="ea00a-102">出力ファイルに書き込めません '\<filename >':\<エラー >。</span><span class="sxs-lookup"><span data-stu-id="ea00a-102">Unable to write to output file '\<filename>': \<error></span></span>
<span data-ttu-id="ea00a-103">ファイルの作成で問題が発生しました。</span><span class="sxs-lookup"><span data-stu-id="ea00a-103">There was a problem creating the file.</span></span>  
  
 <span data-ttu-id="ea00a-104">出力ファイルを書き込み用に開くことができません。</span><span class="sxs-lookup"><span data-stu-id="ea00a-104">An output file cannot be opened for writing.</span></span> <span data-ttu-id="ea00a-105">ファイル (または、そのファイルが格納されているフォルダー) は、別のプロセスによって排他的に開かれているか、読み取り専用属性が設定されている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ea00a-105">The file (or the folder containing the file) may be opened for exclusive use by another process, or it may have its read-only attribute set.</span></span>  
  
 <span data-ttu-id="ea00a-106">ファイルが排他的に開かれている一般的な原因として、次の状況が考えられます。</span><span class="sxs-lookup"><span data-stu-id="ea00a-106">Common situations where a file is opened exclusively are:</span></span>  
  
- <span data-ttu-id="ea00a-107">このアプリケーションが既に実行されていて、ファイルを使用している。</span><span class="sxs-lookup"><span data-stu-id="ea00a-107">The application is already running and using its files.</span></span> <span data-ttu-id="ea00a-108">この問題を解決するためには、アプリケーションを終了します。</span><span class="sxs-lookup"><span data-stu-id="ea00a-108">To solve this problem, make sure that the application is not running.</span></span>  
  
- <span data-ttu-id="ea00a-109">別のアプリケーションがファイルを開いている。</span><span class="sxs-lookup"><span data-stu-id="ea00a-109">Another application has opened the file.</span></span> <span data-ttu-id="ea00a-110">この問題を解決するためには、ファイルにアクセスしている他のアプリケーションがないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="ea00a-110">To solve this problem, make sure that no other application is accessing the files.</span></span> <span data-ttu-id="ea00a-111">ファイルにアクセスしているアプリケーションがわからない場合があります。この場合、アプリケーションを終了する最も簡単な方法として、コンピューターの再起動が考えられます。</span><span class="sxs-lookup"><span data-stu-id="ea00a-111">It is not always obvious which application is accessing your files; in that case, restarting the computer might be the easiest way to terminate the application.</span></span>  
  
 <span data-ttu-id="ea00a-112">プロジェクトの出力ファイルのいずれか 1 つだけが読み取り専用になっている場合でも、この例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="ea00a-112">If even one of the project output files is marked as read-only, this exception will be thrown.</span></span>  
  
 <span data-ttu-id="ea00a-113">**エラー ID:** BC31019</span><span class="sxs-lookup"><span data-stu-id="ea00a-113">**Error ID:** BC31019</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="ea00a-114">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="ea00a-114">To correct this error</span></span>  
  
1. <span data-ttu-id="ea00a-115">プログラムをもう一度コンパイルし、エラーがまだ発生するかどうか確認します。</span><span class="sxs-lookup"><span data-stu-id="ea00a-115">Compile the program again to see if the error recurs.</span></span>  
  
2. <span data-ttu-id="ea00a-116">エラーが引き続き発生する場合は、作業内容を保存し、Visual Studio を再起動します。</span><span class="sxs-lookup"><span data-stu-id="ea00a-116">If the error continues, save your work and restart Visual Studio.</span></span>  
  
3. <span data-ttu-id="ea00a-117">エラーが引き続き発生する場合は、コンピューターを再起動します。</span><span class="sxs-lookup"><span data-stu-id="ea00a-117">If the error continues, restart the computer.</span></span>  
  
4. <span data-ttu-id="ea00a-118">エラーが再発する場合は、Visual Basic を再インストールします。</span><span class="sxs-lookup"><span data-stu-id="ea00a-118">If the error recurs, reinstall Visual Basic.</span></span>  
  
5. <span data-ttu-id="ea00a-119">再インストールした後にエラーが続く場合は、マイクロソフト プロダクト サポート サービスに通知してください。</span><span class="sxs-lookup"><span data-stu-id="ea00a-119">If the error persists after reinstallation, notify Microsoft Product Support Services.</span></span>  
  
### <a name="to-check-file-attributes-in-file-explorer"></a><span data-ttu-id="ea00a-120">エクスプローラーでファイル属性を確認するには</span><span class="sxs-lookup"><span data-stu-id="ea00a-120">To check file attributes in File Explorer</span></span>  
  
1. <span data-ttu-id="ea00a-121">対象のフォルダーを開きます。</span><span class="sxs-lookup"><span data-stu-id="ea00a-121">Open the folder you are interested in.</span></span>  
  
2. <span data-ttu-id="ea00a-122">をクリックして、**ビュー**アイコンを選択し、**詳細**します。</span><span class="sxs-lookup"><span data-stu-id="ea00a-122">Click the **Views** icon and choose **Details**.</span></span>  
  
3. <span data-ttu-id="ea00a-123">列ヘッダーを右クリックして選択**属性**ドロップダウン リストから。</span><span class="sxs-lookup"><span data-stu-id="ea00a-123">Right-click the column header, and choose **Attributes** from the drop-down list.</span></span>  
  
### <a name="to-change-the-attributes-of-a-file-or-folder"></a><span data-ttu-id="ea00a-124">ファイルやフォルダーの属性を変更するには</span><span class="sxs-lookup"><span data-stu-id="ea00a-124">To change the attributes of a file or folder</span></span>  
  
1. <span data-ttu-id="ea00a-125">**ファイル エクスプ ローラー**をファイルまたはフォルダーを右クリックして**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="ea00a-125">In **File Explorer**, right-click the file or folder and choose **Properties**.</span></span>  
  
2. <span data-ttu-id="ea00a-126">**属性**のセクション、**全般**タブで、、**読み取り専用**ボックス。</span><span class="sxs-lookup"><span data-stu-id="ea00a-126">In the **Attributes** section of the **General** tab, clear the **Read-only** box.</span></span>  
  
3. <span data-ttu-id="ea00a-127">**[OK]** を押します。</span><span class="sxs-lookup"><span data-stu-id="ea00a-127">Press **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea00a-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="ea00a-128">See also</span></span>

- [<span data-ttu-id="ea00a-129">ご意見</span><span class="sxs-lookup"><span data-stu-id="ea00a-129">Talk to Us</span></span>](/visualstudio/ide/talk-to-us)
