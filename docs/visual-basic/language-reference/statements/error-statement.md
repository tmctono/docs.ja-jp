---
title: Error ステートメント
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
ms.openlocfilehash: 668ffbc7b8db73a706c5771bb0734a77f8fc0206
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351245"
---
# <a name="error-statement"></a><span data-ttu-id="b6a7f-102">Error ステートメント</span><span class="sxs-lookup"><span data-stu-id="b6a7f-102">Error Statement</span></span>
<span data-ttu-id="b6a7f-103">エラーの発生をシミュレートします。</span><span class="sxs-lookup"><span data-stu-id="b6a7f-103">Simulates the occurrence of an error.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b6a7f-104">構文</span><span class="sxs-lookup"><span data-stu-id="b6a7f-104">Syntax</span></span>  
  
```vb  
Error errornumber  
```  
  
## <a name="parts"></a><span data-ttu-id="b6a7f-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="b6a7f-105">Parts</span></span>  
 `errornumber`  
 <span data-ttu-id="b6a7f-106">必須。</span><span class="sxs-lookup"><span data-stu-id="b6a7f-106">Required.</span></span> <span data-ttu-id="b6a7f-107">任意の有効なエラー番号を指定できます。</span><span class="sxs-lookup"><span data-stu-id="b6a7f-107">Can be any valid error number.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b6a7f-108">コメント</span><span class="sxs-lookup"><span data-stu-id="b6a7f-108">Remarks</span></span>  
 <span data-ttu-id="b6a7f-109">`Error` ステートメントは、旧バージョンとの互換性のためにサポートされています。</span><span class="sxs-lookup"><span data-stu-id="b6a7f-109">The `Error` statement is supported for backward compatibility.</span></span> <span data-ttu-id="b6a7f-110">新しいコードでは、特にオブジェクトを作成する場合は、`Err` オブジェクトの `Raise` メソッドを使用して、実行時エラーを生成します。</span><span class="sxs-lookup"><span data-stu-id="b6a7f-110">In new code, especially when creating objects, use the `Err` object's `Raise` method to generate run-time errors.</span></span>  
  
 <span data-ttu-id="b6a7f-111">`errornumber` が定義されている場合、`Err` オブジェクトのプロパティに次の既定値が割り当てられると、`Error` ステートメントによってエラーハンドラーが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="b6a7f-111">If `errornumber` is defined, the `Error` statement calls the error handler after the properties of the `Err` object are assigned the following default values:</span></span>  
  
|<span data-ttu-id="b6a7f-112">プロパティ</span><span class="sxs-lookup"><span data-stu-id="b6a7f-112">Property</span></span>|<span data-ttu-id="b6a7f-113">値</span><span class="sxs-lookup"><span data-stu-id="b6a7f-113">Value</span></span>|  
|--------------|-----------|  
|`Number`|<span data-ttu-id="b6a7f-114">`Error` ステートメントの引数として指定された値。</span><span class="sxs-lookup"><span data-stu-id="b6a7f-114">Value specified as argument to `Error` statement.</span></span> <span data-ttu-id="b6a7f-115">任意の有効なエラー番号を指定できます。</span><span class="sxs-lookup"><span data-stu-id="b6a7f-115">Can be any valid error number.</span></span>|  
|`Source`|<span data-ttu-id="b6a7f-116">現在の Visual Basic プロジェクトの名前。</span><span class="sxs-lookup"><span data-stu-id="b6a7f-116">Name of the current Visual Basic project.</span></span>|  
|`Description`|<span data-ttu-id="b6a7f-117">この文字列が存在する場合は、指定された `Number`の `Error` 関数の戻り値に対応する文字列式。</span><span class="sxs-lookup"><span data-stu-id="b6a7f-117">String expression corresponding to the return value of the `Error` function for the specified `Number`, if this string exists.</span></span> <span data-ttu-id="b6a7f-118">文字列が存在しない場合、`Description` には長さ0の文字列 ("") が含まれます。</span><span class="sxs-lookup"><span data-stu-id="b6a7f-118">If the string does not exist, `Description` contains a zero-length string ("").</span></span>|  
|`HelpFile`|<span data-ttu-id="b6a7f-119">適切な Visual Basic ヘルプファイルの完全修飾ドライブ、パス、およびファイル名。</span><span class="sxs-lookup"><span data-stu-id="b6a7f-119">The fully qualified drive, path, and file name of the appropriate Visual Basic Help file.</span></span>|  
|`HelpContext`|<span data-ttu-id="b6a7f-120">`Number` プロパティに対応するエラーの Visual Basic ヘルプファイルコンテキスト ID。</span><span class="sxs-lookup"><span data-stu-id="b6a7f-120">The appropriate Visual Basic Help file context ID for the error corresponding to the `Number` property.</span></span>|  
|`LastDLLError`|<span data-ttu-id="b6a7f-121">ゼロ。</span><span class="sxs-lookup"><span data-stu-id="b6a7f-121">Zero.</span></span>|  
  
 <span data-ttu-id="b6a7f-122">エラーハンドラーが存在しない場合、または何も有効になっていない場合は、エラーメッセージが作成され、`Err` オブジェクトのプロパティから表示されます。</span><span class="sxs-lookup"><span data-stu-id="b6a7f-122">If no error handler exists, or if none is enabled, an error message is created and displayed from the `Err` object properties.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b6a7f-123">Visual Basic ホストアプリケーションによっては、オブジェクトを作成できない場合があります。</span><span class="sxs-lookup"><span data-stu-id="b6a7f-123">Some Visual Basic host applications cannot create objects.</span></span> <span data-ttu-id="b6a7f-124">クラスとオブジェクトを作成できるかどうかを判断するには、ホストアプリケーションのドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b6a7f-124">See your host application's documentation to determine whether it can create classes and objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b6a7f-125">例</span><span class="sxs-lookup"><span data-stu-id="b6a7f-125">Example</span></span>  
 <span data-ttu-id="b6a7f-126">この例では、`Error` ステートメントを使用して、エラー番号11を生成します。</span><span class="sxs-lookup"><span data-stu-id="b6a7f-126">This example uses the `Error` statement to generate error number 11.</span></span>  
  
```vb  
On Error Resume Next   ' Defer error handling.  
Error 11   ' Simulate the "Division by zero" error.  
```  
  
## <a name="requirements"></a><span data-ttu-id="b6a7f-127">要件</span><span class="sxs-lookup"><span data-stu-id="b6a7f-127">Requirements</span></span>  
 <span data-ttu-id="b6a7f-128">**名前空間:** [Microsoft. visual basic](../../../visual-basic/language-reference/runtime-library-members.md)</span><span class="sxs-lookup"><span data-stu-id="b6a7f-128">**Namespace:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)</span></span>  
  
 <span data-ttu-id="b6a7f-129">**アセンブリ:** Visual Basic ランタイムライブラリ (Microsoft... .dll)</span><span class="sxs-lookup"><span data-stu-id="b6a7f-129">**Assembly:** Visual Basic Runtime Library (in Microsoft.VisualBasic.dll)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6a7f-130">参照</span><span class="sxs-lookup"><span data-stu-id="b6a7f-130">See also</span></span>

- <xref:Microsoft.VisualBasic.ErrObject.Clear%2A>
- <xref:Microsoft.VisualBasic.Information.Err%2A>
- <xref:Microsoft.VisualBasic.ErrObject.Raise%2A>
- [<span data-ttu-id="b6a7f-131">On Error ステートメント</span><span class="sxs-lookup"><span data-stu-id="b6a7f-131">On Error Statement</span></span>](../../../visual-basic/language-reference/statements/on-error-statement.md)
- [<span data-ttu-id="b6a7f-132">Resume ステートメント</span><span class="sxs-lookup"><span data-stu-id="b6a7f-132">Resume Statement</span></span>](../../../visual-basic/language-reference/statements/resume-statement.md)
- [<span data-ttu-id="b6a7f-133">エラー メッセージ</span><span class="sxs-lookup"><span data-stu-id="b6a7f-133">Error Messages</span></span>](../../../visual-basic/language-reference/error-messages/index.md)
