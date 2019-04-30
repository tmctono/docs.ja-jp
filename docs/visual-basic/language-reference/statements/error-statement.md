---
title: Error ステートメント (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.error
helpviewer_keywords:
- Error statement [Visual Basic], syntax
- Error statement [Visual Basic]
- Error keyword [Visual Basic]
- run-time errors [Visual Basic], codes
- errors [Visual Basic], simulating
ms.assetid: 85cd5c59-5224-4f02-aaf5-fcfefab17a29
ms.openlocfilehash: 8ac7cee2f9959bc75df165d00d3a0a67e1dd9af0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61982398"
---
# <a name="error-statement"></a><span data-ttu-id="edca9-102">Error ステートメント</span><span class="sxs-lookup"><span data-stu-id="edca9-102">Error Statement</span></span>
<span data-ttu-id="edca9-103">エラーの発生をシミュレートします。</span><span class="sxs-lookup"><span data-stu-id="edca9-103">Simulates the occurrence of an error.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="edca9-104">構文</span><span class="sxs-lookup"><span data-stu-id="edca9-104">Syntax</span></span>  
  
```  
Error errornumber  
```  
  
## <a name="parts"></a><span data-ttu-id="edca9-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="edca9-105">Parts</span></span>  
 `errornumber`  
 <span data-ttu-id="edca9-106">必須。</span><span class="sxs-lookup"><span data-stu-id="edca9-106">Required.</span></span> <span data-ttu-id="edca9-107">有効なエラー番号を指定できます。</span><span class="sxs-lookup"><span data-stu-id="edca9-107">Can be any valid error number.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="edca9-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="edca9-108">Remarks</span></span>  
 <span data-ttu-id="edca9-109">`Error`ステートメントは、旧バージョンとの互換性をサポートします。</span><span class="sxs-lookup"><span data-stu-id="edca9-109">The `Error` statement is supported for backward compatibility.</span></span> <span data-ttu-id="edca9-110">オブジェクトを作成するときに特に新しいコードを使用して、`Err`オブジェクトの`Raise`実行時エラーを生成します。</span><span class="sxs-lookup"><span data-stu-id="edca9-110">In new code, especially when creating objects, use the `Err` object's `Raise` method to generate run-time errors.</span></span>  
  
 <span data-ttu-id="edca9-111">場合`errornumber`が定義されている、`Error`ステートメントのプロパティの後のエラー ハンドラーの呼び出し、`Err`オブジェクトには、次の既定値が割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="edca9-111">If `errornumber` is defined, the `Error` statement calls the error handler after the properties of the `Err` object are assigned the following default values:</span></span>  
  
|<span data-ttu-id="edca9-112">プロパティ</span><span class="sxs-lookup"><span data-stu-id="edca9-112">Property</span></span>|<span data-ttu-id="edca9-113">[値]</span><span class="sxs-lookup"><span data-stu-id="edca9-113">Value</span></span>|  
|--------------|-----------|  
|`Number`|<span data-ttu-id="edca9-114">引数として指定された値`Error`ステートメント。</span><span class="sxs-lookup"><span data-stu-id="edca9-114">Value specified as argument to `Error` statement.</span></span> <span data-ttu-id="edca9-115">有効なエラー番号を指定できます。</span><span class="sxs-lookup"><span data-stu-id="edca9-115">Can be any valid error number.</span></span>|  
|`Source`|<span data-ttu-id="edca9-116">現在の Visual Basic プロジェクトの名前です。</span><span class="sxs-lookup"><span data-stu-id="edca9-116">Name of the current Visual Basic project.</span></span>|  
|`Description`|<span data-ttu-id="edca9-117">文字列式の戻り値に対応する、 `Error` 、指定された関数`Number`、この文字列が存在する場合。</span><span class="sxs-lookup"><span data-stu-id="edca9-117">String expression corresponding to the return value of the `Error` function for the specified `Number`, if this string exists.</span></span> <span data-ttu-id="edca9-118">文字列が存在しない場合`Description`長さ 0 の文字列が含まれています ("")。</span><span class="sxs-lookup"><span data-stu-id="edca9-118">If the string does not exist, `Description` contains a zero-length string ("").</span></span>|  
|`HelpFile`|<span data-ttu-id="edca9-119">完全修飾のドライブ、パス、および適切な Visual Basic ヘルプ ファイルの名前。</span><span class="sxs-lookup"><span data-stu-id="edca9-119">The fully qualified drive, path, and file name of the appropriate Visual Basic Help file.</span></span>|  
|`HelpContext`|<span data-ttu-id="edca9-120">対応するエラーのコンテキスト ID を適切な Visual Basic ヘルプ ファイル、`Number`プロパティ。</span><span class="sxs-lookup"><span data-stu-id="edca9-120">The appropriate Visual Basic Help file context ID for the error corresponding to the `Number` property.</span></span>|  
|`LastDLLError`|<span data-ttu-id="edca9-121">0 を返します。</span><span class="sxs-lookup"><span data-stu-id="edca9-121">Zero.</span></span>|  
  
 <span data-ttu-id="edca9-122">エラー ハンドラーが存在しないか、有効でない場合、エラー メッセージが作成されから表示される場合、`Err`オブジェクトのプロパティ。</span><span class="sxs-lookup"><span data-stu-id="edca9-122">If no error handler exists, or if none is enabled, an error message is created and displayed from the `Err` object properties.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="edca9-123">Visual Basic のホスト アプリケーションによっては、オブジェクトを作成できません。</span><span class="sxs-lookup"><span data-stu-id="edca9-123">Some Visual Basic host applications cannot create objects.</span></span> <span data-ttu-id="edca9-124">クラスとオブジェクトのどちらを作成できるかどうかを判断する、ホスト アプリケーションのマニュアルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="edca9-124">See your host application's documentation to determine whether it can create classes and objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="edca9-125">例</span><span class="sxs-lookup"><span data-stu-id="edca9-125">Example</span></span>  
 <span data-ttu-id="edca9-126">この例では、 `Error` 11 のエラー番号を生成するステートメント。</span><span class="sxs-lookup"><span data-stu-id="edca9-126">This example uses the `Error` statement to generate error number 11.</span></span>  
  
```  
On Error Resume Next   ' Defer error handling.  
Error 11   ' Simulate the "Division by zero" error.  
```  
  
## <a name="requirements"></a><span data-ttu-id="edca9-127">必要条件</span><span class="sxs-lookup"><span data-stu-id="edca9-127">Requirements</span></span>  
 <span data-ttu-id="edca9-128">**名前空間:**[Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)</span><span class="sxs-lookup"><span data-stu-id="edca9-128">**Namespace:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)</span></span>  
  
 <span data-ttu-id="edca9-129">**アセンブリ:** Visual Basic ランタイム ライブラリ (Microsoft.VisualBasic.dll)</span><span class="sxs-lookup"><span data-stu-id="edca9-129">**Assembly:** Visual Basic Runtime Library (in Microsoft.VisualBasic.dll)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="edca9-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="edca9-130">See also</span></span>

- <xref:Microsoft.VisualBasic.ErrObject.Clear%2A>
- <xref:Microsoft.VisualBasic.Information.Err%2A>
- <xref:Microsoft.VisualBasic.ErrObject.Raise%2A>
- [<span data-ttu-id="edca9-131">On Error ステートメント</span><span class="sxs-lookup"><span data-stu-id="edca9-131">On Error Statement</span></span>](../../../visual-basic/language-reference/statements/on-error-statement.md)
- [<span data-ttu-id="edca9-132">Resume ステートメント</span><span class="sxs-lookup"><span data-stu-id="edca9-132">Resume Statement</span></span>](../../../visual-basic/language-reference/statements/resume-statement.md)
- [<span data-ttu-id="edca9-133">エラー メッセージ</span><span class="sxs-lookup"><span data-stu-id="edca9-133">Error Messages</span></span>](../../../visual-basic/language-reference/error-messages/index.md)
