---
title: レコード長が正しくありません。
ms.date: 07/20/2015
f1_keywords:
- vbrID59
ms.assetid: 0926a3a4-177b-4452-9b33-d8a01e24cc21
ms.openlocfilehash: 1bc75303bcc2f46e54c06e89347da28997e59786
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61935253"
---
# <a name="bad-record-length"></a><span data-ttu-id="fc319-102">レコード長が正しくありません。</span><span class="sxs-lookup"><span data-stu-id="fc319-102">Bad record length</span></span>
<span data-ttu-id="fc319-103">このエラーでは以下の原因が考えられます。</span><span class="sxs-lookup"><span data-stu-id="fc319-103">Among the possible causes of this error are:</span></span>  
  
- <span data-ttu-id="fc319-104">指定されたレコードの変数の長さ、 `FileGet`、 `FileGetObject`、`FilePut`または`FilePutObject`ステートメントは、対応する指定された長さによって異なります。`FileOpen`ステートメント。</span><span class="sxs-lookup"><span data-stu-id="fc319-104">The length of a record variable specified in a `FileGet`, `FileGetObject`, `FilePut` or `FilePutObject` statement differs from the length specified in the corresponding `FileOpen` statement.</span></span>  
  
- <span data-ttu-id="fc319-105">内の変数を`FilePut`または`FilePutObject`ステートメントまたは可変長文字列が含まれています。</span><span class="sxs-lookup"><span data-stu-id="fc319-105">The variable in a `FilePut` or `FilePutObject` statement is or includes a variable-length string.</span></span>  
  
- <span data-ttu-id="fc319-106">内の変数を`FilePut`または`FilePutObject`かが含まれています、`Variant`型。</span><span class="sxs-lookup"><span data-stu-id="fc319-106">The variable in a `FilePut` or `FilePutObject` is or includes a `Variant` type.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="fc319-107">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="fc319-107">To correct this error</span></span>  
  
1. <span data-ttu-id="fc319-108">記載されている値と同じレコードの変数の型を定義するユーザー定義型の変数を固定長のサイズの合計がかどうかを確認、`FileOpen`ステートメントの`Len`句。</span><span class="sxs-lookup"><span data-stu-id="fc319-108">Make sure the sum of the sizes of fixed-length variables in the user-defined type defining the record variable's type is the same as the value stated in the `FileOpen` statement's `Len` clause.</span></span>  
  
2. <span data-ttu-id="fc319-109">場合に、変数、`FilePut`または`FilePutObject`ステートメントが可変長文字列が含まれるか、可変長文字列が少なくとも 2 つの文字で指定されたレコードの長さよりも短いかどうかを確認、`Len`の句、 `FileOpen`ステートメント。</span><span class="sxs-lookup"><span data-stu-id="fc319-109">If the variable in a `FilePut` or `FilePutObject` statement is or includes a variable-length string, make sure the variable-length string is at least 2 characters shorter than the record length specified in the `Len` clause of the `FileOpen` statement.</span></span>  
  
3. <span data-ttu-id="fc319-110">場合内の変数を`FilePut`または`FilePutObject`かが含まれています、`Variant`可変長文字列は、少なくとも 4 バイトで指定されたレコードの長さよりも短いかどうかを確認、`Len`の句、`FileOpen`ステートメント。</span><span class="sxs-lookup"><span data-stu-id="fc319-110">If the variable in a `FilePut` or `FilePutObject` is or includes a `Variant` make sure the variable-length string is at least 4 bytes shorter than the record length specified in the `Len` clause of the `FileOpen` statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc319-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="fc319-111">See also</span></span>

- <xref:Microsoft.VisualBasic.FileSystem.FileGet%2A>
- <xref:Microsoft.VisualBasic.FileSystem.FileGetObject%2A>
- <xref:Microsoft.VisualBasic.FileSystem.FilePut%2A>
- <xref:Microsoft.VisualBasic.FileSystem.FilePutObject%2A>
