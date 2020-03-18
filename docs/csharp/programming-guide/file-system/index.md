---
title: ファイル システムとレジストリ - C# プログラミング ガイド
ms.date: 07/20/2015
helpviewer_keywords:
- file system [C#]
- registry [C#]
- files [C#]
ms.assetid: 0f2511cf-2b02-4b41-b001-b1754677c38f
ms.openlocfilehash: f160df456f1a3437e11de2d3660d158ae4d4bb67
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/15/2020
ms.locfileid: "75900563"
---
# <a name="file-system-and-the-registry-c-programming-guide"></a><span data-ttu-id="d6222-102">ファイル システムとレジストリ (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="d6222-102">File system and the registry (C# Programming Guide)</span></span>

<span data-ttu-id="d6222-103">次の記事では、C# と .NET を使用して、ファイル、フォルダー、レジストリに対するさまざまな基本操作を実行する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="d6222-103">The following articles show how to use C# and .NET to perform various basic operations on files, folders, and the registry.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="d6222-104">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="d6222-104">In this section</span></span>

|<span data-ttu-id="d6222-105">**Title**</span><span class="sxs-lookup"><span data-stu-id="d6222-105">**Title**</span></span>|<span data-ttu-id="d6222-106">**説明**</span><span class="sxs-lookup"><span data-stu-id="d6222-106">**Description**</span></span>|
|---------------|---------------------|
|[<span data-ttu-id="d6222-107">ディレクトリ ツリーを反復処理する方法</span><span class="sxs-lookup"><span data-stu-id="d6222-107">How to iterate through a directory tree</span></span>](how-to-iterate-through-a-directory-tree.md)|<span data-ttu-id="d6222-108">ディレクトリ ツリーを手動で反復処理する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="d6222-108">Shows how to manually iterate through a directory tree.</span></span>|
|[<span data-ttu-id="d6222-109">ファイル、フォルダー、およびドライブに関する情報を取得する方法</span><span class="sxs-lookup"><span data-stu-id="d6222-109">How to get information about files, folders, and drives</span></span>](how-to-get-information-about-files-folders-and-drives.md)|<span data-ttu-id="d6222-110">作成時刻やサイズなど、ファイル、フォルダー、ドライブに関する情報を取得する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="d6222-110">Shows how to retrieve information such as creation times and size, about files, folders and drives.</span></span>|
|[<span data-ttu-id="d6222-111">ファイルまたはフォルダーを作成する方法</span><span class="sxs-lookup"><span data-stu-id="d6222-111">How to create a file or folder</span></span>](how-to-create-a-file-or-folder.md)|<span data-ttu-id="d6222-112">新しいファイルまたはフォルダーを作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="d6222-112">Shows how to create a new file or folder.</span></span>|
|[<span data-ttu-id="d6222-113">ファイルおよびフォルダーのコピー、削除、および移動を行う方法 (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="d6222-113">How to copy, delete, and move files and folders (C# Programming Guide)</span></span>](how-to-copy-delete-and-move-files-and-folders.md)|<span data-ttu-id="d6222-114">ファイルやフォルダーをコピー、削除、および移動する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="d6222-114">Shows how to copy, delete and move files and folders.</span></span>|
|<span data-ttu-id="d6222-115">[ファイル操作の [進行状況] ダイアログ ボックスを表示する方法](how-to-provide-a-progress-dialog-box-for-file-operations.md)</span><span class="sxs-lookup"><span data-stu-id="d6222-115">[How to provide a progress dialog box for file operations](how-to-provide-a-progress-dialog-box-for-file-operations.md)</span></span>|<span data-ttu-id="d6222-116">特定のファイル操作について、Windows の標準的な進行状況ダイアログを表示する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="d6222-116">Shows how to display a standard Windows progress dialog for certain file operations.</span></span>|
|[<span data-ttu-id="d6222-117">テキスト ファイルに書き込む方法</span><span class="sxs-lookup"><span data-stu-id="d6222-117">How to write to a text file</span></span>](how-to-write-to-a-text-file.md)|<span data-ttu-id="d6222-118">テキスト ファイルに書き込み方法を示します。</span><span class="sxs-lookup"><span data-stu-id="d6222-118">Shows how to write to a text file.</span></span>|
|[<span data-ttu-id="d6222-119">テキスト ファイルから読み取る方法</span><span class="sxs-lookup"><span data-stu-id="d6222-119">How to read from a text file</span></span>](how-to-read-from-a-text-file.md)|<span data-ttu-id="d6222-120">テキスト ファイルから読み取る方法を示します。</span><span class="sxs-lookup"><span data-stu-id="d6222-120">Shows how to read from a text file.</span></span>|
|[<span data-ttu-id="d6222-121">テキスト ファイルを一度に 1 行読み取る方法</span><span class="sxs-lookup"><span data-stu-id="d6222-121">How to read a text file one line at a time</span></span>](how-to-read-a-text-file-one-line-at-a-time.md)|<span data-ttu-id="d6222-122">ファイルから一度に 1 行ずつテキストを取得する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="d6222-122">Shows how to retrieve text from a file one line at a time.</span></span>|
|[<span data-ttu-id="d6222-123">レジストリにキーを作成する方法</span><span class="sxs-lookup"><span data-stu-id="d6222-123">How to create a key in the registry</span></span>](how-to-create-a-key-in-the-registry.md)|<span data-ttu-id="d6222-124">キーをシステム レジストリに書き込む方法を示します。</span><span class="sxs-lookup"><span data-stu-id="d6222-124">Shows how to write a key to the system registry.</span></span>|

## <a name="related-sections"></a><span data-ttu-id="d6222-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="d6222-125">Related sections</span></span>

- [<span data-ttu-id="d6222-126">ファイルおよびストリーム入出力</span><span class="sxs-lookup"><span data-stu-id="d6222-126">File and Stream I/O</span></span>](../../../standard/io/index.md)
- [<span data-ttu-id="d6222-127">ファイルおよびフォルダーのコピー、削除、および移動を行う方法 (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="d6222-127">How to copy, delete, and move files and folders (C# Programming Guide)</span></span>](how-to-copy-delete-and-move-files-and-folders.md)
- [<span data-ttu-id="d6222-128">C# プログラミングガイド</span><span class="sxs-lookup"><span data-stu-id="d6222-128">C# Programming Guide</span></span>](../index.md)
- <xref:System.IO?displayProperty=nameWithType>
