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
ms.openlocfilehash: c7b2adfe7f6b6ff5e89598cb318a90c51595ff6f
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72583380"
---
# <a name="error-statement"></a><span data-ttu-id="a39e7-102">Error ステートメント</span><span class="sxs-lookup"><span data-stu-id="a39e7-102">Error Statement</span></span>
<span data-ttu-id="a39e7-103">エラーの発生をシミュレートします。</span><span class="sxs-lookup"><span data-stu-id="a39e7-103">Simulates the occurrence of an error.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a39e7-104">構文</span><span class="sxs-lookup"><span data-stu-id="a39e7-104">Syntax</span></span>  
  
```vb  
Error errornumber  
```  
  
## <a name="parts"></a><span data-ttu-id="a39e7-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="a39e7-105">Parts</span></span>  
 `errornumber`  
 <span data-ttu-id="a39e7-106">必須です。</span><span class="sxs-lookup"><span data-stu-id="a39e7-106">Required.</span></span> <span data-ttu-id="a39e7-107">任意の有効なエラー番号を指定できます。</span><span class="sxs-lookup"><span data-stu-id="a39e7-107">Can be any valid error number.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a39e7-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="a39e7-108">Remarks</span></span>  
 <span data-ttu-id="a39e7-109">@No__t_0 ステートメントは、旧バージョンとの互換性のためにサポートされています。</span><span class="sxs-lookup"><span data-stu-id="a39e7-109">The `Error` statement is supported for backward compatibility.</span></span> <span data-ttu-id="a39e7-110">新しいコードでは、特にオブジェクトを作成する場合は、`Err` オブジェクトの `Raise` メソッドを使用して、実行時エラーを生成します。</span><span class="sxs-lookup"><span data-stu-id="a39e7-110">In new code, especially when creating objects, use the `Err` object's `Raise` method to generate run-time errors.</span></span>  
  
 <span data-ttu-id="a39e7-111">@No__t_0 が定義されている場合、`Err` オブジェクトのプロパティに次の既定値が割り当てられると、`Error` ステートメントによってエラーハンドラーが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="a39e7-111">If `errornumber` is defined, the `Error` statement calls the error handler after the properties of the `Err` object are assigned the following default values:</span></span>  
  
|<span data-ttu-id="a39e7-112">property</span><span class="sxs-lookup"><span data-stu-id="a39e7-112">Property</span></span>|<span data-ttu-id="a39e7-113">[値]</span><span class="sxs-lookup"><span data-stu-id="a39e7-113">Value</span></span>|  
|--------------|-----------|  
|`Number`|<span data-ttu-id="a39e7-114">@No__t_0 ステートメントの引数として指定された値。</span><span class="sxs-lookup"><span data-stu-id="a39e7-114">Value specified as argument to `Error` statement.</span></span> <span data-ttu-id="a39e7-115">任意の有効なエラー番号を指定できます。</span><span class="sxs-lookup"><span data-stu-id="a39e7-115">Can be any valid error number.</span></span>|  
|`Source`|<span data-ttu-id="a39e7-116">現在の Visual Basic プロジェクトの名前。</span><span class="sxs-lookup"><span data-stu-id="a39e7-116">Name of the current Visual Basic project.</span></span>|  
|`Description`|<span data-ttu-id="a39e7-117">この文字列が存在する場合は、指定された `Number` の `Error` 関数の戻り値に対応する文字列式。</span><span class="sxs-lookup"><span data-stu-id="a39e7-117">String expression corresponding to the return value of the `Error` function for the specified `Number`, if this string exists.</span></span> <span data-ttu-id="a39e7-118">文字列が存在しない場合、`Description` には長さ0の文字列 ("") が含まれます。</span><span class="sxs-lookup"><span data-stu-id="a39e7-118">If the string does not exist, `Description` contains a zero-length string ("").</span></span>|  
|`HelpFile`|<span data-ttu-id="a39e7-119">適切な Visual Basic ヘルプファイルの完全修飾ドライブ、パス、およびファイル名。</span><span class="sxs-lookup"><span data-stu-id="a39e7-119">The fully qualified drive, path, and file name of the appropriate Visual Basic Help file.</span></span>|  
|`HelpContext`|<span data-ttu-id="a39e7-120">@No__t_0 プロパティに対応するエラーの Visual Basic ヘルプファイルコンテキスト ID。</span><span class="sxs-lookup"><span data-stu-id="a39e7-120">The appropriate Visual Basic Help file context ID for the error corresponding to the `Number` property.</span></span>|  
|`LastDLLError`|<span data-ttu-id="a39e7-121">回.</span><span class="sxs-lookup"><span data-stu-id="a39e7-121">Zero.</span></span>|  
  
 <span data-ttu-id="a39e7-122">エラーハンドラーが存在しない場合、または何も有効になっていない場合は、エラーメッセージが作成され、`Err` オブジェクトのプロパティから表示されます。</span><span class="sxs-lookup"><span data-stu-id="a39e7-122">If no error handler exists, or if none is enabled, an error message is created and displayed from the `Err` object properties.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a39e7-123">Visual Basic ホストアプリケーションによっては、オブジェクトを作成できない場合があります。</span><span class="sxs-lookup"><span data-stu-id="a39e7-123">Some Visual Basic host applications cannot create objects.</span></span> <span data-ttu-id="a39e7-124">クラスとオブジェクトを作成できるかどうかを判断するには、ホストアプリケーションのドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a39e7-124">See your host application's documentation to determine whether it can create classes and objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a39e7-125">例</span><span class="sxs-lookup"><span data-stu-id="a39e7-125">Example</span></span>  
 <span data-ttu-id="a39e7-126">この例では、`Error` ステートメントを使用して、エラー番号11を生成します。</span><span class="sxs-lookup"><span data-stu-id="a39e7-126">This example uses the `Error` statement to generate error number 11.</span></span>  
  
```vb  
On Error Resume Next   ' Defer error handling.  
Error 11   ' Simulate the "Division by zero" error.  
```  
  
## <a name="requirements"></a><span data-ttu-id="a39e7-127">［要件］</span><span class="sxs-lookup"><span data-stu-id="a39e7-127">Requirements</span></span>  
 <span data-ttu-id="a39e7-128">**名前空間:** [Microsoft. visual basic](../../../visual-basic/language-reference/runtime-library-members.md)</span><span class="sxs-lookup"><span data-stu-id="a39e7-128">**Namespace:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)</span></span>  
  
 <span data-ttu-id="a39e7-129">**アセンブリ:** Visual Basic ランタイムライブラリ (Microsoft... .dll)</span><span class="sxs-lookup"><span data-stu-id="a39e7-129">**Assembly:** Visual Basic Runtime Library (in Microsoft.VisualBasic.dll)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a39e7-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="a39e7-130">See also</span></span>

- <xref:Microsoft.VisualBasic.ErrObject.Clear%2A>
- <xref:Microsoft.VisualBasic.Information.Err%2A>
- <xref:Microsoft.VisualBasic.ErrObject.Raise%2A>
- [<span data-ttu-id="a39e7-131">On Error ステートメント</span><span class="sxs-lookup"><span data-stu-id="a39e7-131">On Error Statement</span></span>](../../../visual-basic/language-reference/statements/on-error-statement.md)
- [<span data-ttu-id="a39e7-132">Resume ステートメント</span><span class="sxs-lookup"><span data-stu-id="a39e7-132">Resume Statement</span></span>](../../../visual-basic/language-reference/statements/resume-statement.md)
- [<span data-ttu-id="a39e7-133">エラー メッセージ</span><span class="sxs-lookup"><span data-stu-id="a39e7-133">Error Messages</span></span>](../../../visual-basic/language-reference/error-messages/index.md)
