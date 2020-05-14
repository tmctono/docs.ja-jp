---
title: パス/ファイル アクセス エラー
ms.date: 07/20/2015
f1_keywords:
- vbrID75
ms.assetid: 6ce3a161-7316-46bd-a785-0d50e5414020
ms.openlocfilehash: 4f18c9216aa24840bc205534a97124d12698cb98
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61799181"
---
# <a name="pathfile-access-error"></a><span data-ttu-id="5c045-102">パス/ファイル アクセス エラー</span><span class="sxs-lookup"><span data-stu-id="5c045-102">Path/File access error</span></span>
<span data-ttu-id="5c045-103">ファイル アクセス操作またはディスク アクセス操作中に、オペレーティング システムがパスとファイル名の間の接続を作成できませんでした。</span><span class="sxs-lookup"><span data-stu-id="5c045-103">During a file-access or disk-access operation, the operating system could not make a connection between the path and the file name.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="5c045-104">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="5c045-104">To correct this error</span></span>  
  
1. <span data-ttu-id="5c045-105">ファイルの指定が正しく書式設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="5c045-105">Make sure the file specification is correctly formatted.</span></span> <span data-ttu-id="5c045-106">ファイル名には、完全修飾パス (絶対パスまたは相対パス) を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="5c045-106">A file name can contain a fully qualified (absolute) or relative path.</span></span> <span data-ttu-id="5c045-107">完全修飾パスは、ドライブ名 (パスが別のドライブにある場合) で始まり、ルートからファイルへの明示的なパスを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="5c045-107">A fully qualified path starts with the drive name (if the path is on another drive) and lists the explicit path from the root to the file.</span></span> <span data-ttu-id="5c045-108">完全修飾されていないパスは、現在のドライブとディレクトリに対する相対パスです。</span><span class="sxs-lookup"><span data-stu-id="5c045-108">Any path that is not fully qualified is relative to the current drive and directory.</span></span>  
  
2. <span data-ttu-id="5c045-109">既存の読み取り専用ファイルを置き換えるファイルを保存しようとしていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="5c045-109">Make sure that you did not attempt to save a file that would replace an existing read-only file.</span></span> <span data-ttu-id="5c045-110">この場合は、ターゲット ファイルの読み取り専用属性を変更するか、別のファイル名でファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="5c045-110">If this is the case, change the read-only attribute of the target file, or save the file with a different file name.</span></span>  
  
3. <span data-ttu-id="5c045-111">シーケンシャル `Output` モードまたは `Append` モードで読み取り専用ファイルを開こうとしていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="5c045-111">Make sure you did not attempt to open a read-only file in sequential `Output` or `Append` mode.</span></span> <span data-ttu-id="5c045-112">この場合は、ファイルを `Input` モードで開くか、ファイルの読み取り専用属性を変更します。</span><span class="sxs-lookup"><span data-stu-id="5c045-112">If this is the case, open the file in `Input` mode or change the read-only attribute of the file.</span></span>  
  
4. <span data-ttu-id="5c045-113">データベースまたはドキュメント内の Visual Basic プロジェクトを変更しようとしていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="5c045-113">Make sure you did not attempt to change a Visual Basic project within a database or document.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c045-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="5c045-114">See also</span></span>

- [<span data-ttu-id="5c045-115">エラーの種類</span><span class="sxs-lookup"><span data-stu-id="5c045-115">Error Types</span></span>](../../../visual-basic/programming-guide/language-features/error-types.md)
