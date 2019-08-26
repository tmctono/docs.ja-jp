---
title: '方法: ファイル操作の [進行状況] ダイアログ ボックスを表示する - C# プログラミング ガイド'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- progress dialog [C#]
ms.assetid: 01b71fe7-8178-4dc8-aeb1-12053be7b51c
ms.openlocfilehash: 028e779f3cd8a17f162a79791b0c84abae14cf44
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/19/2019
ms.locfileid: "69590051"
---
# <a name="how-to-provide-a-progress-dialog-box-for-file-operations-c-programming-guide"></a><span data-ttu-id="9b71a-102">方法: ファイル操作の [進行状況] ダイアログ ボックスを表示する (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="9b71a-102">How to: Provide a Progress Dialog Box for File Operations (C# Programming Guide)</span></span>
<span data-ttu-id="9b71a-103"><xref:Microsoft.VisualBasic.FileIO.FileSystem.CopyFile%28System.String%2CSystem.String%2CMicrosoft.VisualBasic.FileIO.UIOption%29> 名前空間の <xref:Microsoft.VisualBasic?displayProperty=nameWithType> メソッドを使用すると、Windows でのファイル操作に関する進行状況を示す標準ダイアログ ボックスを提供できます。</span><span class="sxs-lookup"><span data-stu-id="9b71a-103">You can provide a standard dialog box that shows progress on file operations in Windows if you use the <xref:Microsoft.VisualBasic.FileIO.FileSystem.CopyFile%28System.String%2CSystem.String%2CMicrosoft.VisualBasic.FileIO.UIOption%29> method in the <xref:Microsoft.VisualBasic?displayProperty=nameWithType> namespace.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-add-a-reference-in-visual-studio"></a><span data-ttu-id="9b71a-104">Visual Studio で参照を追加するには</span><span class="sxs-lookup"><span data-stu-id="9b71a-104">To add a reference in Visual Studio</span></span>  
  
1. <span data-ttu-id="9b71a-105">メニュー バーで、 **[プロジェクト]** 、 **[参照の追加]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="9b71a-105">On the menu bar, choose **Project**, **Add Reference**.</span></span>  
  
     <span data-ttu-id="9b71a-106">**[参照マネージャー]** ダイアログ ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="9b71a-106">The **Reference Manager** dialog box appears.</span></span>  
  
2. <span data-ttu-id="9b71a-107">**[アセンブリ]** で、 **[フレームワーク]** を選択します (選択されていない場合)。</span><span class="sxs-lookup"><span data-stu-id="9b71a-107">In the **Assemblies** area, choose **Framework** if it isn’t already chosen.</span></span>  
  
3. <span data-ttu-id="9b71a-108">名前の一覧で、 **[Microsoft.VisualBasic]** のチェック ボックスをオンにし、 **[OK]** をクリックしてダイアログ ボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="9b71a-108">In the list of names, select the **Microsoft.VisualBasic** check box, and then choose the **OK** button to close the dialog box.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9b71a-109">例</span><span class="sxs-lookup"><span data-stu-id="9b71a-109">Example</span></span>  
 <span data-ttu-id="9b71a-110">次のコードは、`sourcePath` で指定されたディレクトリを `destinationPath` で指定されたディレクトリにコピーします。</span><span class="sxs-lookup"><span data-stu-id="9b71a-110">The following code copies the directory that `sourcePath` specifies into the directory that `destinationPath` specifies.</span></span> <span data-ttu-id="9b71a-111">また、操作の完了までに必要な残りの予測時間を示す、標準的なダイアログ ボックスを表示します。</span><span class="sxs-lookup"><span data-stu-id="9b71a-111">This code also provides a standard dialog box that shows the estimated amount of time remaining before the operation finishes.</span></span>  
  
 [!code-csharp[csFilesandFolders#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csFilesAndFolders/CS/FileIteration.cs#11)]  
  
## <a name="see-also"></a><span data-ttu-id="9b71a-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="9b71a-112">See also</span></span>

- [<span data-ttu-id="9b71a-113">ファイル システムとレジストリ (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="9b71a-113">File System and the Registry (C# Programming Guide)</span></span>](./index.md)
