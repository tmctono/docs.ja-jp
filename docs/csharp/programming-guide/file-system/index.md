---
title: ファイル システムとレジストリ - C# プログラミング ガイド
description: C# と .NET を使用して、ファイル、フォルダー、レジストリに対して基本操作を実行する方法を説明する記事を示します。
ms.date: 07/20/2015
helpviewer_keywords:
- file system [C#]
- registry [C#]
- files [C#]
ms.assetid: 0f2511cf-2b02-4b41-b001-b1754677c38f
ms.openlocfilehash: 9e25058f5fb8ae49196c070dd426123e61a55e46
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/28/2020
ms.locfileid: "87301633"
---
# <a name="file-system-and-the-registry-c-programming-guide"></a><span data-ttu-id="29e5f-103">ファイル システムとレジストリ (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="29e5f-103">File system and the registry (C# Programming Guide)</span></span>

<span data-ttu-id="29e5f-104">次の記事では、C# と .NET を使用して、ファイル、フォルダー、レジストリに対するさまざまな基本操作を実行する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="29e5f-104">The following articles show how to use C# and .NET to perform various basic operations on files, folders, and the registry.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="29e5f-105">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="29e5f-105">In this section</span></span>

|<span data-ttu-id="29e5f-106">**タイトル**</span><span class="sxs-lookup"><span data-stu-id="29e5f-106">**Title**</span></span>|<span data-ttu-id="29e5f-107">**説明**</span><span class="sxs-lookup"><span data-stu-id="29e5f-107">**Description**</span></span>|
|---------------|---------------------|
|[<span data-ttu-id="29e5f-108">ディレクトリ ツリーを反復処理する方法</span><span class="sxs-lookup"><span data-stu-id="29e5f-108">How to iterate through a directory tree</span></span>](how-to-iterate-through-a-directory-tree.md)|<span data-ttu-id="29e5f-109">ディレクトリ ツリーを手動で反復処理する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="29e5f-109">Shows how to manually iterate through a directory tree.</span></span>|
|[<span data-ttu-id="29e5f-110">ファイル、フォルダー、およびドライブに関する情報を取得する方法</span><span class="sxs-lookup"><span data-stu-id="29e5f-110">How to get information about files, folders, and drives</span></span>](how-to-get-information-about-files-folders-and-drives.md)|<span data-ttu-id="29e5f-111">作成時刻やサイズなど、ファイル、フォルダー、ドライブに関する情報を取得する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="29e5f-111">Shows how to retrieve information such as creation times and size, about files, folders and drives.</span></span>|
|[<span data-ttu-id="29e5f-112">ファイルまたはフォルダーを作成する方法</span><span class="sxs-lookup"><span data-stu-id="29e5f-112">How to create a file or folder</span></span>](how-to-create-a-file-or-folder.md)|<span data-ttu-id="29e5f-113">新しいファイルまたはフォルダーを作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="29e5f-113">Shows how to create a new file or folder.</span></span>|
|[<span data-ttu-id="29e5f-114">ファイルおよびフォルダーのコピー、削除、および移動を行う方法 (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="29e5f-114">How to copy, delete, and move files and folders (C# Programming Guide)</span></span>](how-to-copy-delete-and-move-files-and-folders.md)|<span data-ttu-id="29e5f-115">ファイルやフォルダーをコピー、削除、および移動する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="29e5f-115">Shows how to copy, delete and move files and folders.</span></span>|
|<span data-ttu-id="29e5f-116">[ファイル操作の [進行状況] ダイアログ ボックスを表示する方法](how-to-provide-a-progress-dialog-box-for-file-operations.md)</span><span class="sxs-lookup"><span data-stu-id="29e5f-116">[How to provide a progress dialog box for file operations](how-to-provide-a-progress-dialog-box-for-file-operations.md)</span></span>|<span data-ttu-id="29e5f-117">特定のファイル操作について、Windows の標準的な進行状況ダイアログを表示する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="29e5f-117">Shows how to display a standard Windows progress dialog for certain file operations.</span></span>|
|[<span data-ttu-id="29e5f-118">テキスト ファイルに書き込む方法</span><span class="sxs-lookup"><span data-stu-id="29e5f-118">How to write to a text file</span></span>](how-to-write-to-a-text-file.md)|<span data-ttu-id="29e5f-119">テキスト ファイルに書き込み方法を示します。</span><span class="sxs-lookup"><span data-stu-id="29e5f-119">Shows how to write to a text file.</span></span>|
|[<span data-ttu-id="29e5f-120">テキスト ファイルから読み取る方法</span><span class="sxs-lookup"><span data-stu-id="29e5f-120">How to read from a text file</span></span>](how-to-read-from-a-text-file.md)|<span data-ttu-id="29e5f-121">テキスト ファイルから読み取る方法を示します。</span><span class="sxs-lookup"><span data-stu-id="29e5f-121">Shows how to read from a text file.</span></span>|
|[<span data-ttu-id="29e5f-122">テキスト ファイルを一度に 1 行読み取る方法</span><span class="sxs-lookup"><span data-stu-id="29e5f-122">How to read a text file one line at a time</span></span>](how-to-read-a-text-file-one-line-at-a-time.md)|<span data-ttu-id="29e5f-123">ファイルから一度に 1 行ずつテキストを取得する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="29e5f-123">Shows how to retrieve text from a file one line at a time.</span></span>|
|[<span data-ttu-id="29e5f-124">レジストリにキーを作成する方法</span><span class="sxs-lookup"><span data-stu-id="29e5f-124">How to create a key in the registry</span></span>](how-to-create-a-key-in-the-registry.md)|<span data-ttu-id="29e5f-125">キーをシステム レジストリに書き込む方法を示します。</span><span class="sxs-lookup"><span data-stu-id="29e5f-125">Shows how to write a key to the system registry.</span></span>|

## <a name="related-sections"></a><span data-ttu-id="29e5f-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="29e5f-126">Related sections</span></span>

- [<span data-ttu-id="29e5f-127">ファイルおよびストリーム入出力</span><span class="sxs-lookup"><span data-stu-id="29e5f-127">File and Stream I/O</span></span>](../../../standard/io/index.md)
- [<span data-ttu-id="29e5f-128">ファイルおよびフォルダーのコピー、削除、および移動を行う方法 (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="29e5f-128">How to copy, delete, and move files and folders (C# Programming Guide)</span></span>](how-to-copy-delete-and-move-files-and-folders.md)
- [<span data-ttu-id="29e5f-129">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="29e5f-129">C# Programming Guide</span></span>](../index.md)
- <xref:System.IO?displayProperty=nameWithType>
