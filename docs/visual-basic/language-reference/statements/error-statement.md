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
ms.openlocfilehash: f3f9f5ecb96686fe525e98cf64672d81a3145796
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2020
ms.locfileid: "90873276"
---
# <a name="error-statement"></a><span data-ttu-id="1352a-102">Error ステートメント</span><span class="sxs-lookup"><span data-stu-id="1352a-102">Error Statement</span></span>

<span data-ttu-id="1352a-103">エラーの発生をシミュレートします。</span><span class="sxs-lookup"><span data-stu-id="1352a-103">Simulates the occurrence of an error.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1352a-104">構文</span><span class="sxs-lookup"><span data-stu-id="1352a-104">Syntax</span></span>  
  
```vb  
Error errornumber  
```  
  
## <a name="parts"></a><span data-ttu-id="1352a-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="1352a-105">Parts</span></span>  

 `errornumber`  
 <span data-ttu-id="1352a-106">必須です。</span><span class="sxs-lookup"><span data-stu-id="1352a-106">Required.</span></span> <span data-ttu-id="1352a-107">任意の有効なエラー番号を指定できます。</span><span class="sxs-lookup"><span data-stu-id="1352a-107">Can be any valid error number.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1352a-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="1352a-108">Remarks</span></span>  

 <span data-ttu-id="1352a-109">`Error` ステートメントは下位互換性のためにサポートされています。</span><span class="sxs-lookup"><span data-stu-id="1352a-109">The `Error` statement is supported for backward compatibility.</span></span> <span data-ttu-id="1352a-110">新しいコードでは、特にオブジェクトを作成する場合に、`Err` オブジェクトの `Raise` メソッドを使用して、実行時エラーを生成します。</span><span class="sxs-lookup"><span data-stu-id="1352a-110">In new code, especially when creating objects, use the `Err` object's `Raise` method to generate run-time errors.</span></span>  
  
 <span data-ttu-id="1352a-111">`errornumber` を定義している場合、`Err` オブジェクトのプロパティに次の既定値が代入されると、`Error` ステートメントによって、エラー ハンドラーが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="1352a-111">If `errornumber` is defined, the `Error` statement calls the error handler after the properties of the `Err` object are assigned the following default values:</span></span>  
  
|<span data-ttu-id="1352a-112">プロパティ</span><span class="sxs-lookup"><span data-stu-id="1352a-112">Property</span></span>|<span data-ttu-id="1352a-113">[値]</span><span class="sxs-lookup"><span data-stu-id="1352a-113">Value</span></span>|  
|--------------|-----------|  
|`Number`|<span data-ttu-id="1352a-114">`Error` ステートメントの引数として指定された値。</span><span class="sxs-lookup"><span data-stu-id="1352a-114">Value specified as argument to `Error` statement.</span></span> <span data-ttu-id="1352a-115">任意の有効なエラー番号を指定できます。</span><span class="sxs-lookup"><span data-stu-id="1352a-115">Can be any valid error number.</span></span>|  
|`Source`|<span data-ttu-id="1352a-116">現在の Visual Basic プロジェクトの名前。</span><span class="sxs-lookup"><span data-stu-id="1352a-116">Name of the current Visual Basic project.</span></span>|  
|`Description`|<span data-ttu-id="1352a-117">指定した `Number` の `Error` 関数の戻り値に対応する文字列式 (この文字列が存在する場合)。</span><span class="sxs-lookup"><span data-stu-id="1352a-117">String expression corresponding to the return value of the `Error` function for the specified `Number`, if this string exists.</span></span> <span data-ttu-id="1352a-118">文字列が存在しない場合は、`Description` に長さゼロの文字列 ("") が格納されます。</span><span class="sxs-lookup"><span data-stu-id="1352a-118">If the string does not exist, `Description` contains a zero-length string ("").</span></span>|  
|`HelpFile`|<span data-ttu-id="1352a-119">該当する Visual Basic ヘルプ ファイルの完全修飾ドライブ、パス、およびファイル名。</span><span class="sxs-lookup"><span data-stu-id="1352a-119">The fully qualified drive, path, and file name of the appropriate Visual Basic Help file.</span></span>|  
|`HelpContext`|<span data-ttu-id="1352a-120">`Number` プロパティに対応するエラーについての該当する Visual Basic ヘルプ ファイル コンテキスト ID。</span><span class="sxs-lookup"><span data-stu-id="1352a-120">The appropriate Visual Basic Help file context ID for the error corresponding to the `Number` property.</span></span>|  
|`LastDLLError`|<span data-ttu-id="1352a-121">ゼロ。</span><span class="sxs-lookup"><span data-stu-id="1352a-121">Zero.</span></span>|  
  
 <span data-ttu-id="1352a-122">エラー ハンドラーが存在しない場合、または有効なものがない場合は、`Err` オブジェクトのプロパティからエラーメッセージが作成され、表示されます。</span><span class="sxs-lookup"><span data-stu-id="1352a-122">If no error handler exists, or if none is enabled, an error message is created and displayed from the `Err` object properties.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1352a-123">一部の Visual Basic ホストアプリケーションでは、オブジェクトを作成できない場合があります。</span><span class="sxs-lookup"><span data-stu-id="1352a-123">Some Visual Basic host applications cannot create objects.</span></span> <span data-ttu-id="1352a-124">ホスト アプリケーションでクラスとオブジェクトを作成できるかどうかを判断するには、そのドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="1352a-124">See your host application's documentation to determine whether it can create classes and objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1352a-125">例</span><span class="sxs-lookup"><span data-stu-id="1352a-125">Example</span></span>  

 <span data-ttu-id="1352a-126">この例では、`Error` ステートメントを使用して、エラー番号 11 を生成しています。</span><span class="sxs-lookup"><span data-stu-id="1352a-126">This example uses the `Error` statement to generate error number 11.</span></span>  
  
```vb  
On Error Resume Next   ' Defer error handling.  
Error 11   ' Simulate the "Division by zero" error.  
```  
  
## <a name="requirements"></a><span data-ttu-id="1352a-127">必要条件</span><span class="sxs-lookup"><span data-stu-id="1352a-127">Requirements</span></span>  

 <span data-ttu-id="1352a-128">**名前空間:** [Microsoft.VisualBasic](../runtime-library-members.md)</span><span class="sxs-lookup"><span data-stu-id="1352a-128">**Namespace:** [Microsoft.VisualBasic](../runtime-library-members.md)</span></span>  
  
 <span data-ttu-id="1352a-129">**アセンブリ:** Visual Basic ランタイム ライブラリ (Microsoft.VisualBasic.dll)</span><span class="sxs-lookup"><span data-stu-id="1352a-129">**Assembly:** Visual Basic Runtime Library (in Microsoft.VisualBasic.dll)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1352a-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="1352a-130">See also</span></span>

- <xref:Microsoft.VisualBasic.ErrObject.Clear%2A>
- <xref:Microsoft.VisualBasic.Information.Err%2A>
- <xref:Microsoft.VisualBasic.ErrObject.Raise%2A>
- [<span data-ttu-id="1352a-131">On Error ステートメント</span><span class="sxs-lookup"><span data-stu-id="1352a-131">On Error Statement</span></span>](on-error-statement.md)
- [<span data-ttu-id="1352a-132">Resume ステートメント</span><span class="sxs-lookup"><span data-stu-id="1352a-132">Resume Statement</span></span>](resume-statement.md)
- [<span data-ttu-id="1352a-133">エラー メッセージ</span><span class="sxs-lookup"><span data-stu-id="1352a-133">Error Messages</span></span>](../error-messages/index.md)
