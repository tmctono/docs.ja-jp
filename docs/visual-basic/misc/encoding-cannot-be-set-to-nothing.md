---
title: エンコードは Nothing に設定できません
ms.date: 07/20/2015
ms.assetid: 59f7c731-8291-4a85-bf51-c225e48cdc84
ms.openlocfilehash: 30b0b4a29fbdf931aa62263b75d1fa946e87b145
ms.sourcegitcommit: 5c1abeec15fbddcc7dbaa729fabc1f1f29f12045
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/15/2019
ms.locfileid: "58028441"
---
# <a name="encoding-cannot-be-set-to-nothing"></a><span data-ttu-id="bcc2f-102">エンコードは Nothing に設定できません</span><span class="sxs-lookup"><span data-stu-id="bcc2f-102">Encoding cannot be set to Nothing</span></span>
<span data-ttu-id="bcc2f-103">パラメーター `encoding` が `Nothing` に設定されていますが、正しい値が必要なため、ファイルへの読み取りまたは書き込みに失敗しました。</span><span class="sxs-lookup"><span data-stu-id="bcc2f-103">An attempt to read from or write to a file has failed because the parameter `encoding` has been set to `Nothing` but requires a valid value.</span></span>  
  
 <span data-ttu-id="bcc2f-104"><xref:System.Text.Encoding> は、ファイルへの書き込み時に使用するエンコードを判別するのに使用されます。</span><span class="sxs-lookup"><span data-stu-id="bcc2f-104"><xref:System.Text.Encoding> is used to determine what encoding to use when writing to a file.</span></span> <span data-ttu-id="bcc2f-105">既定は UTF-8 です。</span><span class="sxs-lookup"><span data-stu-id="bcc2f-105">The default is UTF-8.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="bcc2f-106">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="bcc2f-106">To correct this error</span></span>  
  
-   <span data-ttu-id="bcc2f-107">正しい値を `encoding` パラメーターに指定します。</span><span class="sxs-lookup"><span data-stu-id="bcc2f-107">Supply a valid value for the `encoding` parameter.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bcc2f-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="bcc2f-108">See also</span></span>

- [<span data-ttu-id="bcc2f-109">ファイル エンコーディング</span><span class="sxs-lookup"><span data-stu-id="bcc2f-109">File Encodings</span></span>](../../visual-basic/developing-apps/programming/drives-directories-files/file-encodings.md)
- [<span data-ttu-id="bcc2f-110">ファイルの読み取り</span><span class="sxs-lookup"><span data-stu-id="bcc2f-110">Reading from Files</span></span>](../../visual-basic/developing-apps/programming/drives-directories-files/reading-from-files.md)
- [<span data-ttu-id="bcc2f-111">ファイルへの書き込み</span><span class="sxs-lookup"><span data-stu-id="bcc2f-111">Writing to Files</span></span>](../../visual-basic/developing-apps/programming/drives-directories-files/writing-to-files.md)
- [<span data-ttu-id="bcc2f-112">My.Computer.FileSystem.ReadAllText</span><span class="sxs-lookup"><span data-stu-id="bcc2f-112">My.Computer.FileSystem.ReadAllText</span></span>](xref:Microsoft.VisualBasic.FileIO.FileSystem.ReadAllText%2A)
- [<span data-ttu-id="bcc2f-113">My.Computer.FileSystem.WriteAllText</span><span class="sxs-lookup"><span data-stu-id="bcc2f-113">My.Computer.FileSystem.WriteAllText</span></span>](xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllText%2A)
