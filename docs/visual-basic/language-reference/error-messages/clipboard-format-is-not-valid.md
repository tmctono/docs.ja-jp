---
title: クリップボードの形式が有効ではありません。
ms.date: 07/20/2015
f1_keywords:
- vbrID460
ms.assetid: 71a4a045-65bb-417d-b3bd-99a9fa3c53f6
ms.openlocfilehash: 5ec077be30b0afc8917d431dc9bd73c8dd41be89
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61649869"
---
# <a name="clipboard-format-is-not-valid"></a><span data-ttu-id="9d173-102">クリップボードの形式が有効ではありません。</span><span class="sxs-lookup"><span data-stu-id="9d173-102">Clipboard format is not valid</span></span>
<span data-ttu-id="9d173-103">指定されたクリップボードの形式は、実行中のメソッドと互換性がありません。</span><span class="sxs-lookup"><span data-stu-id="9d173-103">The specified Clipboard format is incompatible with the method being executed.</span></span> <span data-ttu-id="9d173-104">このエラーの考えられる原因には。</span><span class="sxs-lookup"><span data-stu-id="9d173-104">Among the possible causes for this error are:</span></span>  
  
- <span data-ttu-id="9d173-105">クリップボードを使用して`GetText`または`SetText`メソッド以外のクリップボード形式を`vbCFText`または`vbCFLink`します。</span><span class="sxs-lookup"><span data-stu-id="9d173-105">Using the Clipboard's `GetText` or `SetText` method with a Clipboard format other than `vbCFText` or `vbCFLink`.</span></span>  
  
- <span data-ttu-id="9d173-106">クリップボードを使用して`GetData`または`SetData`メソッド以外のクリップボード形式を`vbCFBitmap`、 `vbCFDIB`、または`vbCFMetafile`します。</span><span class="sxs-lookup"><span data-stu-id="9d173-106">Using the Clipboard's `GetData` or `SetData` method with a Clipboard format other than `vbCFBitmap`, `vbCFDIB`, or `vbCFMetafile`.</span></span>  
  
- <span data-ttu-id="9d173-107">使用して、`GetData`または`SetData`のメソッド、`DataObject`登録されている形式 (& HC000 - & HFFFF)、Microsoft Windows によって予約された範囲内のクリップボード形式のときにそのクリップボードの形式で Microsoft Windows 登録されていません.</span><span class="sxs-lookup"><span data-stu-id="9d173-107">Using the `GetData` or `SetData` methods of a `DataObject` with a Clipboard format in the range reserved by Microsoft Windows for registered formats (&HC000-&HFFFF), when that Clipboard format has not been registered with Microsoft Windows.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="9d173-108">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="9d173-108">To correct this error</span></span>  
  
- <span data-ttu-id="9d173-109">無効な形式を削除し、有効なものを指定します。</span><span class="sxs-lookup"><span data-stu-id="9d173-109">Remove the invalid format and specify a valid one.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d173-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="9d173-110">See also</span></span>

- [<span data-ttu-id="9d173-111">クリップボード: その他の形式の追加</span><span class="sxs-lookup"><span data-stu-id="9d173-111">Clipboard: Adding Other Formats</span></span>](/cpp/mfc/clipboard-adding-other-formats)
