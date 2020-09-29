---
title: レコード長が正しくありません。
ms.date: 07/20/2015
f1_keywords:
- vbrID59
ms.assetid: 0926a3a4-177b-4452-9b33-d8a01e24cc21
ms.openlocfilehash: 6967015572b2567f52697f7ddcb1ff594013a2c4
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2020
ms.locfileid: "90869261"
---
# <a name="bad-record-length"></a><span data-ttu-id="9ecdf-102">レコード長が正しくありません。</span><span class="sxs-lookup"><span data-stu-id="9ecdf-102">Bad record length</span></span>

<span data-ttu-id="9ecdf-103">このエラーでは以下の原因が考えられます。</span><span class="sxs-lookup"><span data-stu-id="9ecdf-103">Among the possible causes of this error are:</span></span>  
  
- <span data-ttu-id="9ecdf-104">`FileGet`、`FileGetObject`、`FilePut`、または `FilePutObject` ステートメントに指定されたレコード変数の長さが、対応する `FileOpen` ステートメントに指定された長さと異なります。</span><span class="sxs-lookup"><span data-stu-id="9ecdf-104">The length of a record variable specified in a `FileGet`, `FileGetObject`, `FilePut` or `FilePutObject` statement differs from the length specified in the corresponding `FileOpen` statement.</span></span>  
  
- <span data-ttu-id="9ecdf-105">`FilePut` または `FilePutObject` ステートメント内の変数は、可変長文字列であるか、またはそれを含んでいます。</span><span class="sxs-lookup"><span data-stu-id="9ecdf-105">The variable in a `FilePut` or `FilePutObject` statement is or includes a variable-length string.</span></span>  
  
- <span data-ttu-id="9ecdf-106">`FilePut` または `FilePutObject` 内の変数は、`Variant` 型であるか、またはそれを含んでいます。</span><span class="sxs-lookup"><span data-stu-id="9ecdf-106">The variable in a `FilePut` or `FilePutObject` is or includes a `Variant` type.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="9ecdf-107">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="9ecdf-107">To correct this error</span></span>  
  
1. <span data-ttu-id="9ecdf-108">レコード変数の型を定義しているユーザー定義型の固定長変数のサイズの合計が、`FileOpen` ステートメントの `Len` 句に記述されている値と同じであることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="9ecdf-108">Make sure the sum of the sizes of fixed-length variables in the user-defined type defining the record variable's type is the same as the value stated in the `FileOpen` statement's `Len` clause.</span></span>  
  
2. <span data-ttu-id="9ecdf-109">`FilePut` または `FilePutObject` ステートメント内の変数が、可変長文字列であるか、またはそれを含んでいる場合、可変長文字列が `FileOpen` ステートメントの `Len` 句に指定されているレコード長よりも少なくとも 2 文字短いことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="9ecdf-109">If the variable in a `FilePut` or `FilePutObject` statement is or includes a variable-length string, make sure the variable-length string is at least 2 characters shorter than the record length specified in the `Len` clause of the `FileOpen` statement.</span></span>  
  
3. <span data-ttu-id="9ecdf-110">`FilePut` または `FilePutObject` 内の変数が `Variant` であるか、またはそれを含んでいる場合、可変長文字列が、`FileOpen` ステートメントの `Len` 句に指定されているレコード長よりも少なくとも 4 バイト短いことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="9ecdf-110">If the variable in a `FilePut` or `FilePutObject` is or includes a `Variant` make sure the variable-length string is at least 4 bytes shorter than the record length specified in the `Len` clause of the `FileOpen` statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ecdf-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="9ecdf-111">See also</span></span>

- <xref:Microsoft.VisualBasic.FileSystem.FileGet%2A>
- <xref:Microsoft.VisualBasic.FileSystem.FileGetObject%2A>
- <xref:Microsoft.VisualBasic.FileSystem.FilePut%2A>
- <xref:Microsoft.VisualBasic.FileSystem.FilePutObject%2A>
