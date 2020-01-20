---
title: ファイルまたはフォルダーを作成する方法 - C# プログラミング ガイド
ms.date: 07/20/2015
helpviewer_keywords:
- folders [C#]
- creating files [C#]
- files [C#]
- creating folders [C#]
ms.assetid: 4582ee2d-d72d-4687-bcb9-08d336c62c25
ms.openlocfilehash: e0d0a7fbbc7e6a5c9a0bd00dec1188c5cfdcf896
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/07/2020
ms.locfileid: "75705250"
---
# <a name="how-to-create-a-file-or-folder-c-programming-guide"></a><span data-ttu-id="d9c76-102">ファイルまたはフォルダーを作成する方法 (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="d9c76-102">How to create a file or folder (C# Programming Guide)</span></span>
<span data-ttu-id="d9c76-103">プログラムによって、コンピューター上でのフォルダーの作成、サブフォルダーの作成、サブフォルダー内でのファイルの作成、およびファイルへのデータの記述を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="d9c76-103">You can programmatically create a folder on your computer, create a subfolder, create a file in the subfolder, and write data to the file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d9c76-104">例</span><span class="sxs-lookup"><span data-stu-id="d9c76-104">Example</span></span>  
 [!code-csharp[csFilesandFolders#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csFilesAndFolders/CS/FileIteration.cs#10)]  
  
 <span data-ttu-id="d9c76-105">フォルダーが既に存在していた場合、<xref:System.IO.Directory.CreateDirectory%2A> は何も実行せず、例外はスローされません。</span><span class="sxs-lookup"><span data-stu-id="d9c76-105">If the folder already exists, <xref:System.IO.Directory.CreateDirectory%2A> does nothing, and no exception is thrown.</span></span> <span data-ttu-id="d9c76-106">ただし <xref:System.IO.File.Create%2A?displayProperty=nameWithType> は、既存のファイルを新しいファイルに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="d9c76-106">However, <xref:System.IO.File.Create%2A?displayProperty=nameWithType> replaces an existing file with a new file.</span></span> <span data-ttu-id="d9c76-107">この例では、`if`-`else` ステートメントを使用して、既存のファイルが置き換えられないようにします。</span><span class="sxs-lookup"><span data-stu-id="d9c76-107">The example uses an `if`-`else` statement to prevent an existing file from being replaced.</span></span>  
  
 <span data-ttu-id="d9c76-108">この例に次の変更を加えることによって、特定の名前のファイルが既に存在するかどうかに基づいて異なる結果を指定できます。</span><span class="sxs-lookup"><span data-stu-id="d9c76-108">By making the following changes in the example, you can specify different outcomes based on whether a file with a certain name already exists.</span></span> <span data-ttu-id="d9c76-109">そのようなファイルが存在しない場合、コードによって作成されます。</span><span class="sxs-lookup"><span data-stu-id="d9c76-109">If such a file doesn't exist, the code creates one.</span></span> <span data-ttu-id="d9c76-110">このようなファイルがある場合、コードはそのファイルにデータを追加します。</span><span class="sxs-lookup"><span data-stu-id="d9c76-110">If such a file exists, the code appends data to that file.</span></span>  
  
- <span data-ttu-id="d9c76-111">ランダムではないファイル名を指定します。</span><span class="sxs-lookup"><span data-stu-id="d9c76-111">Specify a non-random file name.</span></span>  
  
    ```csharp  
    // Comment out the following line.  
    //string fileName = System.IO.Path.GetRandomFileName();  
  
    // Replace that line with the following assignment.  
    string fileName = "MyNewFile.txt";  
    ```  
  
- <span data-ttu-id="d9c76-112">次のコードで、`if`-`else` ステートメントを `using` に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="d9c76-112">Replace the `if`-`else` statement with the `using` statement in the following code.</span></span>  
  
    ```csharp  
    using (System.IO.FileStream fs = new System.IO.FileStream(pathString, FileMode.Append))   
    {  
        for (byte i = 0; i < 100; i++)  
        {  
            fs.WriteByte(i);  
        }  
    }  
    ```  
  
 <span data-ttu-id="d9c76-113">データがファイルに追加されたことを毎回確認するために、この例を数回実行します。</span><span class="sxs-lookup"><span data-stu-id="d9c76-113">Run the example several times to verify that data is added to the file each time.</span></span>  
  
 <span data-ttu-id="d9c76-114">試用できるその他の `FileMode` 値については、<xref:System.IO.FileMode> を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d9c76-114">For more `FileMode` values that you can try, see <xref:System.IO.FileMode>.</span></span>  
  
 <span data-ttu-id="d9c76-115">次の条件を満たす場合は、例外が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d9c76-115">The following conditions may cause an exception:</span></span>  
  
- <span data-ttu-id="d9c76-116">フォルダー名が不適切である場合。</span><span class="sxs-lookup"><span data-stu-id="d9c76-116">The folder name is malformed.</span></span> <span data-ttu-id="d9c76-117">たとえば、不正な文字が含まれている場合や、空白だけの場合などがその例です (<xref:System.ArgumentException> クラス)。</span><span class="sxs-lookup"><span data-stu-id="d9c76-117">For example, it contains illegal characters or is only white space (<xref:System.ArgumentException> class).</span></span> <span data-ttu-id="d9c76-118">有効なパス名を作成するには、<xref:System.IO.Path> クラスを使用します。</span><span class="sxs-lookup"><span data-stu-id="d9c76-118">Use the <xref:System.IO.Path> class to create valid path names.</span></span>  
  
- <span data-ttu-id="d9c76-119">作成するフォルダーの親フォルダーが読み取り専用である場合 (<xref:System.IO.IOException> クラス)。</span><span class="sxs-lookup"><span data-stu-id="d9c76-119">The parent folder of the folder to be created is read-only (<xref:System.IO.IOException> class).</span></span>  
  
- <span data-ttu-id="d9c76-120">フォルダー名が `null` である場合 (<xref:System.ArgumentNullException> クラス)。</span><span class="sxs-lookup"><span data-stu-id="d9c76-120">The folder name is `null` (<xref:System.ArgumentNullException> class).</span></span>  
  
- <span data-ttu-id="d9c76-121">フォルダー名が長すぎる場合 (<xref:System.IO.PathTooLongException> クラス)。</span><span class="sxs-lookup"><span data-stu-id="d9c76-121">The folder name is too long (<xref:System.IO.PathTooLongException> class).</span></span>  
  
- <span data-ttu-id="d9c76-122">フォルダー名がコロン (":") だけである場合 (<xref:System.IO.PathTooLongException> クラス)。</span><span class="sxs-lookup"><span data-stu-id="d9c76-122">The folder name is only a colon, ":" (<xref:System.IO.PathTooLongException> class).</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="d9c76-123">.NET Framework セキュリティ</span><span class="sxs-lookup"><span data-stu-id="d9c76-123">.NET Framework Security</span></span>  
 <span data-ttu-id="d9c76-124">部分的に信頼された状況では、<xref:System.Security.SecurityException> クラスのインスタンスがスローされることがあります。</span><span class="sxs-lookup"><span data-stu-id="d9c76-124">An instance of the <xref:System.Security.SecurityException> class may be thrown in partial-trust situations.</span></span>  
  
 <span data-ttu-id="d9c76-125">フォルダーの作成に必要なアクセス許可が与えられていない場合、この例では <xref:System.UnauthorizedAccessException> クラスのインスタンスがスローされます。</span><span class="sxs-lookup"><span data-stu-id="d9c76-125">If you don’t have permission to create the folder, the example throws an instance of the <xref:System.UnauthorizedAccessException> class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9c76-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="d9c76-126">See also</span></span>

- <xref:System.IO?displayProperty=nameWithType>
- [<span data-ttu-id="d9c76-127">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="d9c76-127">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="d9c76-128">ファイル システムとレジストリ (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="d9c76-128">File System and the Registry (C# Programming Guide)</span></span>](./index.md)
