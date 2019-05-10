---
title: クリップボードの形式が有効ではありません。
ms.date: 07/20/2015
f1_keywords:
- vbrID460
ms.assetid: 71a4a045-65bb-417d-b3bd-99a9fa3c53f6
ms.openlocfilehash: 15bc530d1030a8c4d720321ea249fdd7fb6cd8b6
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64623094"
---
# <a name="clipboard-format-is-not-valid"></a><span data-ttu-id="bf9b1-102">クリップボードの形式が有効ではありません。</span><span class="sxs-lookup"><span data-stu-id="bf9b1-102">Clipboard format is not valid</span></span>
<span data-ttu-id="bf9b1-103">指定されたクリップボードの形式は、実行中のメソッドと互換性がありません。</span><span class="sxs-lookup"><span data-stu-id="bf9b1-103">The specified Clipboard format is incompatible with the method being executed.</span></span> <span data-ttu-id="bf9b1-104">このエラーの考えられる原因には。</span><span class="sxs-lookup"><span data-stu-id="bf9b1-104">Among the possible causes for this error are:</span></span>  
  
- <span data-ttu-id="bf9b1-105">クリップボードを使用して`GetText`または`SetText`メソッド以外のクリップボード形式を`vbCFText`または`vbCFLink`します。</span><span class="sxs-lookup"><span data-stu-id="bf9b1-105">Using the Clipboard's `GetText` or `SetText` method with a Clipboard format other than `vbCFText` or `vbCFLink`.</span></span>  
  
- <span data-ttu-id="bf9b1-106">クリップボードを使用して`GetData`または`SetData`メソッド以外のクリップボード形式を`vbCFBitmap`、 `vbCFDIB`、または`vbCFMetafile`します。</span><span class="sxs-lookup"><span data-stu-id="bf9b1-106">Using the Clipboard's `GetData` or `SetData` method with a Clipboard format other than `vbCFBitmap`, `vbCFDIB`, or `vbCFMetafile`.</span></span>  
  
- <span data-ttu-id="bf9b1-107">使用して、`GetData`または`SetData`のメソッド、`DataObject`登録されている形式 (& HC000 - & HFFFF)、Microsoft Windows によって予約された範囲内のクリップボード形式のときにそのクリップボードの形式で Microsoft Windows 登録されていません.</span><span class="sxs-lookup"><span data-stu-id="bf9b1-107">Using the `GetData` or `SetData` methods of a `DataObject` with a Clipboard format in the range reserved by Microsoft Windows for registered formats (&HC000-&HFFFF), when that Clipboard format has not been registered with Microsoft Windows.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="bf9b1-108">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="bf9b1-108">To correct this error</span></span>  
  
- <span data-ttu-id="bf9b1-109">無効な形式を削除し、有効なものを指定します。</span><span class="sxs-lookup"><span data-stu-id="bf9b1-109">Remove the invalid format and specify a valid one.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf9b1-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="bf9b1-110">See also</span></span>

- [<span data-ttu-id="bf9b1-111">クリップボード: その他の形式の追加</span><span class="sxs-lookup"><span data-stu-id="bf9b1-111">Clipboard: Adding Other Formats</span></span>](/cpp/mfc/clipboard-adding-other-formats)
