---
title: パス/ファイル アクセス エラー
ms.date: 07/20/2015
f1_keywords:
- vbrID75
ms.assetid: 6ce3a161-7316-46bd-a785-0d50e5414020
ms.openlocfilehash: 4f18c9216aa24840bc205534a97124d12698cb98
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59342155"
---
# <a name="pathfile-access-error"></a><span data-ttu-id="f5a7c-102">パス/ファイル アクセス エラー</span><span class="sxs-lookup"><span data-stu-id="f5a7c-102">Path/File access error</span></span>
<span data-ttu-id="f5a7c-103">ファイル アクセスまたはディスク アクセス操作中に、オペレーティング システムは、パスとファイル名の間の接続を作成できませんでした。</span><span class="sxs-lookup"><span data-stu-id="f5a7c-103">During a file-access or disk-access operation, the operating system could not make a connection between the path and the file name.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="f5a7c-104">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="f5a7c-104">To correct this error</span></span>  
  
1. <span data-ttu-id="f5a7c-105">ファイルの仕様が正しく書式設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="f5a7c-105">Make sure the file specification is correctly formatted.</span></span> <span data-ttu-id="f5a7c-106">ファイル名は、完全修飾 (絶対) または相対パスに含めることができますのパス。</span><span class="sxs-lookup"><span data-stu-id="f5a7c-106">A file name can contain a fully qualified (absolute) or relative path.</span></span> <span data-ttu-id="f5a7c-107">(パスは、別のドライブ上にある) 場合、ドライブ名で完全修飾パスを開始し、ルートから、ファイルへの明示的なパスを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="f5a7c-107">A fully qualified path starts with the drive name (if the path is on another drive) and lists the explicit path from the root to the file.</span></span> <span data-ttu-id="f5a7c-108">完全に修飾されていない任意のパスでは、現在のドライブとディレクトリに対して相対的です。</span><span class="sxs-lookup"><span data-stu-id="f5a7c-108">Any path that is not fully qualified is relative to the current drive and directory.</span></span>  
  
2. <span data-ttu-id="f5a7c-109">既存の読み取り専用ファイルを置き換えるファイルの保存試みなかったことを確認します。</span><span class="sxs-lookup"><span data-stu-id="f5a7c-109">Make sure that you did not attempt to save a file that would replace an existing read-only file.</span></span> <span data-ttu-id="f5a7c-110">大文字と小文字の場合は、ターゲット ファイルの読み取り専用属性を変更または別のファイル名、ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="f5a7c-110">If this is the case, change the read-only attribute of the target file, or save the file with a different file name.</span></span>  
  
3. <span data-ttu-id="f5a7c-111">順次読み取り専用のファイルを開くをしないようにするには必ず`Output`または`Append`モード。</span><span class="sxs-lookup"><span data-stu-id="f5a7c-111">Make sure you did not attempt to open a read-only file in sequential `Output` or `Append` mode.</span></span> <span data-ttu-id="f5a7c-112">この場合は、ファイルを開き`Input`モードまたはファイルの読み取り専用属性を変更します。</span><span class="sxs-lookup"><span data-stu-id="f5a7c-112">If this is the case, open the file in `Input` mode or change the read-only attribute of the file.</span></span>  
  
4. <span data-ttu-id="f5a7c-113">データベースまたはドキュメント内での Visual Basic プロジェクトを変更しようとしてしなかったことを確認します。</span><span class="sxs-lookup"><span data-stu-id="f5a7c-113">Make sure you did not attempt to change a Visual Basic project within a database or document.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5a7c-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="f5a7c-114">See also</span></span>

- [<span data-ttu-id="f5a7c-115">エラーの種類</span><span class="sxs-lookup"><span data-stu-id="f5a7c-115">Error Types</span></span>](../../../visual-basic/programming-guide/language-features/error-types.md)
