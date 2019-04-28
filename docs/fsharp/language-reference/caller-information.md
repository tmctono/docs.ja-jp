---
title: 呼び出し元情報
description: 呼び出し元情報の引数属性を使用して、メソッドから呼び出し元情報を取得する方法について説明します。
ms.date: 04/25/2017
ms.openlocfilehash: 13092df453b684d3ed4a93c842ea49c066157cb6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61703167"
---
# <a name="caller-information"></a><span data-ttu-id="522f8-103">呼び出し元情報</span><span class="sxs-lookup"><span data-stu-id="522f8-103">Caller information</span></span>

<span data-ttu-id="522f8-104">呼び出し元情報の属性を使用すると、メソッドへの呼び出し元に関する情報を取得できます。</span><span class="sxs-lookup"><span data-stu-id="522f8-104">By using Caller Info attributes, you can obtain information about the caller to a method.</span></span> <span data-ttu-id="522f8-105">ソース コードのファイル パス、ソース コードの行番号、および呼び出し元のメンバー名を取得できます。</span><span class="sxs-lookup"><span data-stu-id="522f8-105">You can obtain file path of the source code, the line number in the source code, and the member name of the caller.</span></span> <span data-ttu-id="522f8-106">この情報は、トレース、デバッグ、および診断ツールの作成に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="522f8-106">This information is helpful for tracing, debugging, and creating diagnostic tools.</span></span>

<span data-ttu-id="522f8-107">この情報を取得するには、省略可能なパラメーターに適用される属性を使用します。各パラメーターには既定値があります。</span><span class="sxs-lookup"><span data-stu-id="522f8-107">To obtain this information, you use attributes that are applied to optional parameters, each of which has a default value.</span></span> <span data-ttu-id="522f8-108">次の表に、呼び出し元情報属性で定義されている、 [System.Runtime.CompilerServices](/dotnet/api/system.runtime.compilerservices)名前空間。</span><span class="sxs-lookup"><span data-stu-id="522f8-108">The following table lists the Caller Info attributes that are defined in the [System.Runtime.CompilerServices](/dotnet/api/system.runtime.compilerservices) namespace:</span></span>

|<span data-ttu-id="522f8-109">属性</span><span class="sxs-lookup"><span data-stu-id="522f8-109">Attribute</span></span>|<span data-ttu-id="522f8-110">説明</span><span class="sxs-lookup"><span data-stu-id="522f8-110">Description</span></span>|<span data-ttu-id="522f8-111">型</span><span class="sxs-lookup"><span data-stu-id="522f8-111">Type</span></span>|
|---------|-----------|----|
|[<span data-ttu-id="522f8-112">CallerFilePath</span><span class="sxs-lookup"><span data-stu-id="522f8-112">CallerFilePath</span></span>](/dotnet/api/system.runtime.compilerservices.callerfilepathattribute)|<span data-ttu-id="522f8-113">呼び出し元を含むソース ファイルのフル パスです。</span><span class="sxs-lookup"><span data-stu-id="522f8-113">Full path of the source file that contains the caller.</span></span> <span data-ttu-id="522f8-114">これは、コンパイル時のファイル パスです。</span><span class="sxs-lookup"><span data-stu-id="522f8-114">This is the file path at compile time.</span></span>|`String`
|[<span data-ttu-id="522f8-115">CallerLineNumber</span><span class="sxs-lookup"><span data-stu-id="522f8-115">CallerLineNumber</span></span>](/dotnet/api/system.runtime.compilerservices.callerlinenumberattribute)|<span data-ttu-id="522f8-116">メソッドが呼び出されたソース ファイルの行番号。</span><span class="sxs-lookup"><span data-stu-id="522f8-116">Line number in the source file at which the method is called.</span></span>|`Integer`|
|[<span data-ttu-id="522f8-117">CallerMemberName</span><span class="sxs-lookup"><span data-stu-id="522f8-117">CallerMemberName</span></span>](/dotnet/api/system.runtime.compilerservices.callermembernameattribute)|<span data-ttu-id="522f8-118">呼び出し元のメソッド名またはプロパティ名。</span><span class="sxs-lookup"><span data-stu-id="522f8-118">Method or property name of the caller.</span></span> <span data-ttu-id="522f8-119">このトピックの後半では、メンバー名を参照してください。</span><span class="sxs-lookup"><span data-stu-id="522f8-119">See the Member Names section later in this topic.</span></span>|`String`|

## <a name="example"></a><span data-ttu-id="522f8-120">例</span><span class="sxs-lookup"><span data-stu-id="522f8-120">Example</span></span>

<span data-ttu-id="522f8-121">次の例では、これらの属性を呼び出し元のトレースを使用する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="522f8-121">The following example shows how you might use these attributes to trace a caller.</span></span>

```fsharp
open System.Diagnostics
open System.Runtime.CompilerServices
open System.Runtime.InteropServices

type Tracer() =
    member __.DoTrace(message: string,
                      [<CallerMemberName; Optional; DefaultParameterValue("")>] memberName: string,
                      [<CallerFilePath; Optional; DefaultParameterValue("")>] path: string,
                      [<CallerLineNumber; Optional; DefaultParameterValue(0)>] line: int) =
        Trace.WriteLine(sprintf "Message: %s" message)
        Trace.WriteLine(sprintf "Member name: %s" memberName)
        Trace.WriteLine(sprintf "Source file path: %s" path)
        Trace.WriteLine(sprintf "Source line number: %d" line)
```

## <a name="remarks"></a><span data-ttu-id="522f8-122">Remarks</span><span class="sxs-lookup"><span data-stu-id="522f8-122">Remarks</span></span>

<span data-ttu-id="522f8-123">呼び出し元情報属性は、省略可能なパラメーターにのみ適用できます。</span><span class="sxs-lookup"><span data-stu-id="522f8-123">Caller Info attributes can only be applied to optional parameters.</span></span> <span data-ttu-id="522f8-124">呼び出し元情報属性には、呼び出し元情報属性で修飾された省略可能な各パラメーターの適切な値を記述するコンパイラが発生します。</span><span class="sxs-lookup"><span data-stu-id="522f8-124">The Caller Info attributes cause the compiler to write the proper value for each optional parameter decorated with a Caller Info attribute.</span></span>

<span data-ttu-id="522f8-125">呼び出し元情報の値は、コンパイル時に中間言語 (IL) 内にリテラルとして出力されます。</span><span class="sxs-lookup"><span data-stu-id="522f8-125">Caller Info values are emitted as literals into the Intermediate Language (IL) at compile time.</span></span> <span data-ttu-id="522f8-126">結果とは異なり、 [StackTrace](/dotnet/api/system.diagnostics.stacktrace)結果の例外のプロパティに難読化による影響はありません。</span><span class="sxs-lookup"><span data-stu-id="522f8-126">Unlike the results of the [StackTrace](/dotnet/api/system.diagnostics.stacktrace) property for exceptions, the results aren't affected by obfuscation.</span></span>

<span data-ttu-id="522f8-127">省略可能な引数を明示的に指定して、呼び出し元情報を制御したり、非表示にしたりできます。</span><span class="sxs-lookup"><span data-stu-id="522f8-127">You can explicitly supply the optional arguments to control the caller information or to hide caller information.</span></span>

## <a name="member-names"></a><span data-ttu-id="522f8-128">メンバー名</span><span class="sxs-lookup"><span data-stu-id="522f8-128">Member names</span></span>

<span data-ttu-id="522f8-129">使用することができます、 [ `CallerMemberName` ](/dotnet/api/system.runtime.compilerservices.callermembernameattribute)属性とメンバーの名前を指定することを回避するために、`String`呼び出されたメソッドの引数。</span><span class="sxs-lookup"><span data-stu-id="522f8-129">You can use the [`CallerMemberName`](/dotnet/api/system.runtime.compilerservices.callermembernameattribute) attribute to avoid specifying the member name as a `String` argument to the called method.</span></span> <span data-ttu-id="522f8-130">この手法を使用すると、名前の変更リファクタリング変更されない問題を避けるため、`String`値。</span><span class="sxs-lookup"><span data-stu-id="522f8-130">By using this technique, you avoid the problem that Rename Refactoring doesn't change the `String` values.</span></span> <span data-ttu-id="522f8-131">この利点は、次のタスクで役立ちます。</span><span class="sxs-lookup"><span data-stu-id="522f8-131">This benefit is especially useful for the following tasks:</span></span>

* <span data-ttu-id="522f8-132">トレース ルーチンと診断ルーチンの使用。</span><span class="sxs-lookup"><span data-stu-id="522f8-132">Using tracing and diagnostic routines.</span></span>
* <span data-ttu-id="522f8-133">実装する、 [INotifyPropertyChanged](/dotnet/api/system.componentmodel.inotifypropertychanged)インターフェイスのデータをバインドするときにします。</span><span class="sxs-lookup"><span data-stu-id="522f8-133">Implementing the [INotifyPropertyChanged](/dotnet/api/system.componentmodel.inotifypropertychanged) interface when binding data.</span></span> <span data-ttu-id="522f8-134">このインターフェイスを使用すると、オブジェクトのプロパティが、プロパティが変更されたことをデータ バインド コントロールに通知できます。これによって、このコントロールは、更新された情報を表示できます。</span><span class="sxs-lookup"><span data-stu-id="522f8-134">This interface allows the property of an object to notify a bound control that the property has changed, so that the control can display the updated information.</span></span> <span data-ttu-id="522f8-135">なし、 [ `CallerMemberName` ](/dotnet/api/system.runtime.compilerservices.callermembernameattribute)属性、リテラルとしてプロパティ名を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="522f8-135">Without the [`CallerMemberName`](/dotnet/api/system.runtime.compilerservices.callermembernameattribute) attribute, you must specify the property name as a literal.</span></span>

<span data-ttu-id="522f8-136">次の図は、CallerMemberName 属性を使用するときに返される名、メンバーを示します。</span><span class="sxs-lookup"><span data-stu-id="522f8-136">The following chart shows the member names that are returned when you use the CallerMemberName attribute.</span></span>

|<span data-ttu-id="522f8-137">呼び出しは、次のものの中で発生します。</span><span class="sxs-lookup"><span data-stu-id="522f8-137">Calls occurs within</span></span>|<span data-ttu-id="522f8-138">メンバー名の結果</span><span class="sxs-lookup"><span data-stu-id="522f8-138">Member name result</span></span>|
|-------------------|------------------|
|<span data-ttu-id="522f8-139">メソッド、プロパティ、またはイベント</span><span class="sxs-lookup"><span data-stu-id="522f8-139">Method, property, or event</span></span>|<span data-ttu-id="522f8-140">呼び出しが発生したメソッド、プロパティ、またはイベントの名前。</span><span class="sxs-lookup"><span data-stu-id="522f8-140">The name of the method, property, or event from which the call originated.</span></span>|
|<span data-ttu-id="522f8-141">コンストラクター</span><span class="sxs-lookup"><span data-stu-id="522f8-141">Constructor</span></span>|<span data-ttu-id="522f8-142">文字列「.ctor」</span><span class="sxs-lookup"><span data-stu-id="522f8-142">The string ".ctor"</span></span>|
|<span data-ttu-id="522f8-143">静的コンストラクター</span><span class="sxs-lookup"><span data-stu-id="522f8-143">Static constructor</span></span>|<span data-ttu-id="522f8-144">文字列「.cctor」</span><span class="sxs-lookup"><span data-stu-id="522f8-144">The string ".cctor"</span></span>|
|<span data-ttu-id="522f8-145">デストラクターです。</span><span class="sxs-lookup"><span data-stu-id="522f8-145">Destructor</span></span>|<span data-ttu-id="522f8-146">文字列「Finalize」</span><span class="sxs-lookup"><span data-stu-id="522f8-146">The string "Finalize"</span></span>|
|<span data-ttu-id="522f8-147">ユーザー定義の演算子または変換</span><span class="sxs-lookup"><span data-stu-id="522f8-147">User-defined operators or conversions</span></span>|<span data-ttu-id="522f8-148">生成されたメンバー名 (「op_Addition」など)。</span><span class="sxs-lookup"><span data-stu-id="522f8-148">The generated name for the member, for example, "op_Addition".</span></span>|
|<span data-ttu-id="522f8-149">Attribute コンストラクター</span><span class="sxs-lookup"><span data-stu-id="522f8-149">Attribute constructor</span></span>|<span data-ttu-id="522f8-150">属性が適用されるメンバーの名前。</span><span class="sxs-lookup"><span data-stu-id="522f8-150">The name of the member to which the attribute is applied.</span></span> <span data-ttu-id="522f8-151">属性がメンバー内の要素 (パラメーター、戻り値、ジェネリック型パラメーターなど) である場合、この結果は、その要素に関連付けられているメンバーの名前になります。</span><span class="sxs-lookup"><span data-stu-id="522f8-151">If the attribute is any element within a member (such as a parameter, a return value, or a generic type parameter), this result is the name of the member that's associated with that element.</span></span>|
|<span data-ttu-id="522f8-152">含んでいないメンバー (型に適用されているアセンブリ レベルや属性など)</span><span class="sxs-lookup"><span data-stu-id="522f8-152">No containing member (for example, assembly-level or attributes that are applied to types)</span></span>|<span data-ttu-id="522f8-153">省略可能なパラメーターの既定値。</span><span class="sxs-lookup"><span data-stu-id="522f8-153">The default value of the optional parameter.</span></span>|

## <a name="see-also"></a><span data-ttu-id="522f8-154">関連項目</span><span class="sxs-lookup"><span data-stu-id="522f8-154">See also</span></span>

- [<span data-ttu-id="522f8-155">属性</span><span class="sxs-lookup"><span data-stu-id="522f8-155">Attributes</span></span>](attributes.md)
- [<span data-ttu-id="522f8-156">名前付き引数</span><span class="sxs-lookup"><span data-stu-id="522f8-156">Named arguments</span></span>](parameters-and-arguments.md#named-arguments)
- [<span data-ttu-id="522f8-157">省略可能なパラメーター</span><span class="sxs-lookup"><span data-stu-id="522f8-157">Optional parameters</span></span>](parameters-and-arguments.md#optional-parameters)
