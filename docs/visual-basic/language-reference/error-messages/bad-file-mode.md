---
title: ファイル モードが正しくありません。
ms.date: 07/20/2015
f1_keywords:
- vbrID54
ms.assetid: 74891e96-884b-4c8d-872d-cd11ae272372
ms.openlocfilehash: 9a59faf1b6f845858e36efcabdf0758e41ad75dc
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64619744"
---
# <a name="bad-file-mode"></a><span data-ttu-id="0b781-102">ファイル モードが正しくありません。</span><span class="sxs-lookup"><span data-stu-id="0b781-102">Bad file mode</span></span>
<span data-ttu-id="0b781-103">ファイルの内容を操作するために使用されるステートメントは、ファイルが開かれたモードに適している必要があります。</span><span class="sxs-lookup"><span data-stu-id="0b781-103">Statements used in manipulating file contents must be appropriate to the mode in which the file was opened.</span></span> <span data-ttu-id="0b781-104">以下の原因が考えられます。</span><span class="sxs-lookup"><span data-stu-id="0b781-104">Possible causes include:</span></span>  
  
- <span data-ttu-id="0b781-105">`FilePutObject` または `FileGetObject` ステートメントがシーケンシャル ファイルを指定しています。</span><span class="sxs-lookup"><span data-stu-id="0b781-105">A `FilePutObject` or `FileGetObject` statement specifies a sequential file.</span></span>  
  
- <span data-ttu-id="0b781-106">`Print` ステートメントが、`Output` または `Append` 以外のアクセス モード用に開かれたファイルを指定しています。</span><span class="sxs-lookup"><span data-stu-id="0b781-106">A `Print` statement specifies a file opened for an access mode other than `Output` or `Append`.</span></span>  
  
- <span data-ttu-id="0b781-107">`Input` ステートメントが、`Input` 以外のアクセス モードで開かれたファイルを指定しています</span><span class="sxs-lookup"><span data-stu-id="0b781-107">An `Input` statement specifies a file opened for an access mode other than `Input`</span></span>  
  
- <span data-ttu-id="0b781-108">読み取り専用ファイルに書き込もうとしました。</span><span class="sxs-lookup"><span data-stu-id="0b781-108">An attempt to write to a read-only file.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="0b781-109">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="0b781-109">To correct this error</span></span>  
  
- <span data-ttu-id="0b781-110">`FilePutObject` および `FileGetObject` が、`Random` または `Binary` アクセス用に開かれたファイルのみを参照していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="0b781-110">Make sure `FilePutObject` and `FileGetObject` are only referring to files open for `Random` or `Binary` access.</span></span>  
  
- <span data-ttu-id="0b781-111">`Print` が `Output` または `Append` アクセス モードのいずれかで開かれているファイルを指定していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="0b781-111">Make sure `Print` specifies a file opened for either `Output` or `Append` access mode.</span></span> <span data-ttu-id="0b781-112">そうでない場合は、別のステートメントを使用してファイルにデータを格納するか、適切なモードでファイルを再度開きます。</span><span class="sxs-lookup"><span data-stu-id="0b781-112">If not, use a different statement to place data in the file, or reopen the file in an appropriate mode.</span></span>  
  
- <span data-ttu-id="0b781-113">`Input` が `Input` で開かれているファイルを指定していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="0b781-113">Make sure `Input` specifies a file opened for `Input`.</span></span> <span data-ttu-id="0b781-114">そうでない場合は、別のステートメントを使用してファイルにデータを格納するか、適切なモードでファイルを再度開きます。</span><span class="sxs-lookup"><span data-stu-id="0b781-114">If not, use a different statement to place data in the file or reopen the file in an appropriate mode.</span></span>  
  
- <span data-ttu-id="0b781-115">読み取り専用ファイルに書き込む場合は、ファイルの読み取り/書き込みの状態を変更するか、ファイルへの書き込みを試みないようにします。</span><span class="sxs-lookup"><span data-stu-id="0b781-115">If you are writing to a read-only file, change the read/write status of the file or do not try to write to it.</span></span>  
  
- <span data-ttu-id="0b781-116">`My.Computer.FileSystem` オブジェクトで利用できる機能を使用します。</span><span class="sxs-lookup"><span data-stu-id="0b781-116">Use the functionality available in the `My.Computer.FileSystem` object.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b781-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="0b781-117">See also</span></span>

- <xref:Microsoft.VisualBasic.FileSystem>
- [<span data-ttu-id="0b781-118">トラブルシューティング : テキスト ファイルの読み取りと書き込み</span><span class="sxs-lookup"><span data-stu-id="0b781-118">Troubleshooting: Reading from and Writing to Text Files</span></span>](../../../visual-basic/developing-apps/programming/drives-directories-files/troubleshooting-reading-from-and-writing-to-text-files.md)
