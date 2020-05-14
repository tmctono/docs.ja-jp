---
title: レコード長が正しくありません。
ms.date: 07/20/2015
f1_keywords:
- vbrID59
ms.assetid: 0926a3a4-177b-4452-9b33-d8a01e24cc21
ms.openlocfilehash: 7ec0a8c27f425ec717bca5d45d5dfd2b601c11d5
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64665736"
---
# <a name="bad-record-length"></a><span data-ttu-id="6dbd8-102">レコード長が正しくありません。</span><span class="sxs-lookup"><span data-stu-id="6dbd8-102">Bad record length</span></span>
<span data-ttu-id="6dbd8-103">このエラーでは以下の原因が考えられます。</span><span class="sxs-lookup"><span data-stu-id="6dbd8-103">Among the possible causes of this error are:</span></span>  
  
- <span data-ttu-id="6dbd8-104">`FileGet`、`FileGetObject`、`FilePut`、または `FilePutObject` ステートメントに指定されたレコード変数の長さが、対応する `FileOpen` ステートメントに指定された長さと異なります。</span><span class="sxs-lookup"><span data-stu-id="6dbd8-104">The length of a record variable specified in a `FileGet`, `FileGetObject`, `FilePut` or `FilePutObject` statement differs from the length specified in the corresponding `FileOpen` statement.</span></span>  
  
- <span data-ttu-id="6dbd8-105">`FilePut` または `FilePutObject` ステートメント内の変数は、可変長文字列であるか、またはそれを含んでいます。</span><span class="sxs-lookup"><span data-stu-id="6dbd8-105">The variable in a `FilePut` or `FilePutObject` statement is or includes a variable-length string.</span></span>  
  
- <span data-ttu-id="6dbd8-106">`FilePut` または `FilePutObject` 内の変数は、`Variant` 型であるか、またはそれを含んでいます。</span><span class="sxs-lookup"><span data-stu-id="6dbd8-106">The variable in a `FilePut` or `FilePutObject` is or includes a `Variant` type.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="6dbd8-107">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="6dbd8-107">To correct this error</span></span>  
  
1. <span data-ttu-id="6dbd8-108">レコード変数の型を定義しているユーザー定義型の固定長変数のサイズの合計が、`FileOpen` ステートメントの `Len` 句に記述されている値と同じであることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="6dbd8-108">Make sure the sum of the sizes of fixed-length variables in the user-defined type defining the record variable's type is the same as the value stated in the `FileOpen` statement's `Len` clause.</span></span>  
  
2. <span data-ttu-id="6dbd8-109">`FilePut` または `FilePutObject` ステートメント内の変数が、可変長文字列であるか、またはそれを含んでいる場合、可変長文字列が `FileOpen` ステートメントの `Len` 句に指定されているレコード長よりも少なくとも 2 文字短いことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="6dbd8-109">If the variable in a `FilePut` or `FilePutObject` statement is or includes a variable-length string, make sure the variable-length string is at least 2 characters shorter than the record length specified in the `Len` clause of the `FileOpen` statement.</span></span>  
  
3. <span data-ttu-id="6dbd8-110">`FilePut` または `FilePutObject` 内の変数が `Variant` であるか、またはそれを含んでいる場合、可変長文字列が、`FileOpen` ステートメントの `Len` 句に指定されているレコード長よりも少なくとも 4 バイト短いことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="6dbd8-110">If the variable in a `FilePut` or `FilePutObject` is or includes a `Variant` make sure the variable-length string is at least 4 bytes shorter than the record length specified in the `Len` clause of the `FileOpen` statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6dbd8-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="6dbd8-111">See also</span></span>

- <xref:Microsoft.VisualBasic.FileSystem.FileGet%2A>
- <xref:Microsoft.VisualBasic.FileSystem.FileGetObject%2A>
- <xref:Microsoft.VisualBasic.FileSystem.FilePut%2A>
- <xref:Microsoft.VisualBasic.FileSystem.FilePutObject%2A>
