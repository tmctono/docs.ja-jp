---
title: C# の予約済み属性:呼び出し元情報の追跡
ms.date: 04/09/2020
description: これらの属性を使用すると、メンバーを呼び出すコードに関する情報を生成するようにコンパイラに指示できます。 CallerFilePath、CallerLineNumber、および CallerMemberName を使用して、詳細なトレース情報を提供します。
ms.openlocfilehash: ee061d4cae35bdcc0b89007e360e94fee8c5f87c
ms.sourcegitcommit: c91110ef6ee3fedb591f3d628dc17739c4a7071e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/15/2020
ms.locfileid: "81389824"
---
# <a name="reserved-attributes-determine-caller-information"></a><span data-ttu-id="63db3-104">予約済みの属性:呼び出し元情報を判断する</span><span class="sxs-lookup"><span data-stu-id="63db3-104">Reserved attributes: Determine caller information</span></span>

<span data-ttu-id="63db3-105">info 属性を使用して、メソッドの呼び出し元に関する情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="63db3-105">Using info attributes, you obtain information about the caller to a method.</span></span> <span data-ttu-id="63db3-106">ソース コードのファイル パス、ソース コードの行番号、呼び出し元のメンバー名を取得します。</span><span class="sxs-lookup"><span data-stu-id="63db3-106">You obtain the file path of the source code, the line number in the source code, and the member name of the caller.</span></span> <span data-ttu-id="63db3-107">メンバー呼び出し元情報を取得するには、省略可能なパラメーターに適用される属性を使用します。</span><span class="sxs-lookup"><span data-stu-id="63db3-107">To obtain member caller information, you use attributes that are applied to optional parameters.</span></span> <span data-ttu-id="63db3-108">省略可能な各パラメーターでは既定値が指定されます。</span><span class="sxs-lookup"><span data-stu-id="63db3-108">Each optional parameter specifies a default value.</span></span> <span data-ttu-id="63db3-109">次の表は、<xref:System.Runtime.CompilerServices?displayProperty=nameWithType> 名前空間で定義されている呼び出し元情報の属性の一覧です。</span><span class="sxs-lookup"><span data-stu-id="63db3-109">The following table lists the Caller Info attributes that are defined in the <xref:System.Runtime.CompilerServices?displayProperty=nameWithType> namespace:</span></span>

|<span data-ttu-id="63db3-110">属性</span><span class="sxs-lookup"><span data-stu-id="63db3-110">Attribute</span></span>|<span data-ttu-id="63db3-111">説明</span><span class="sxs-lookup"><span data-stu-id="63db3-111">Description</span></span>|<span data-ttu-id="63db3-112">種類</span><span class="sxs-lookup"><span data-stu-id="63db3-112">Type</span></span>|
|---|---|---|
|<xref:System.Runtime.CompilerServices.CallerFilePathAttribute>|<span data-ttu-id="63db3-113">呼び出し元を含むソース ファイルのフル パスです。</span><span class="sxs-lookup"><span data-stu-id="63db3-113">Full path of the source file that contains the caller.</span></span> <span data-ttu-id="63db3-114">完全なパスは、コンパイル時のパスです。</span><span class="sxs-lookup"><span data-stu-id="63db3-114">The full path is the path at compile time.</span></span>|`String`|
|<xref:System.Runtime.CompilerServices.CallerLineNumberAttribute>|<span data-ttu-id="63db3-115">メソッドの呼び出し元であるソース ファイルの行番号。</span><span class="sxs-lookup"><span data-stu-id="63db3-115">Line number in the source file from which the method is called.</span></span>|`Integer`|
|<xref:System.Runtime.CompilerServices.CallerMemberNameAttribute>|<span data-ttu-id="63db3-116">呼び出し元のメソッド名またはプロパティ名。</span><span class="sxs-lookup"><span data-stu-id="63db3-116">Method name or property name of the caller.</span></span>|`String`|

<span data-ttu-id="63db3-117">この情報は、トレースの作成、デバッグ、および診断ツールの作成に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="63db3-117">This information helps you write tracing, debugging, and create diagnostic tools.</span></span> <span data-ttu-id="63db3-118">呼び出し元情報の属性を使用する方法の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="63db3-118">The following example shows how to use caller info attributes.</span></span> <span data-ttu-id="63db3-119">`TraceMessage` メソッドを呼び出すたびに、呼び出し元情報は、省略可能なパラメーターの引数として設定されます。</span><span class="sxs-lookup"><span data-stu-id="63db3-119">On each call to the `TraceMessage` method, the caller information is substituted as arguments to the optional parameters.</span></span>

```csharp
public void DoProcessing()
{
    TraceMessage("Something happened.");
}

public void TraceMessage(string message,
        [CallerMemberName] string memberName = "",
        [CallerFilePath] string sourceFilePath = "",
        [CallerLineNumber] int sourceLineNumber = 0)
{
    Trace.WriteLine("message: " + message);
    Trace.WriteLine("member name: " + memberName);
    Trace.WriteLine("source file path: " + sourceFilePath);
    Trace.WriteLine("source line number: " + sourceLineNumber);
}

// Sample Output:
//  message: Something happened.
//  member name: DoProcessing
//  source file path: c:\Visual Studio Projects\CallerInfoCS\CallerInfoCS\Form1.cs
//  source line number: 31
```

<span data-ttu-id="63db3-120">省略可能な各パラメーターには、明示的な既定値を指定します。</span><span class="sxs-lookup"><span data-stu-id="63db3-120">You specify an explicit default value for each optional parameter.</span></span> <span data-ttu-id="63db3-121">省略可能と指定されていないパラメーターには、呼び出し元情報の属性を適用できません。</span><span class="sxs-lookup"><span data-stu-id="63db3-121">You can't apply caller info attributes to parameters that aren't specified as optional.</span></span> <span data-ttu-id="63db3-122">呼び出し元情報の属性によってパラメーターが省略可能になるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="63db3-122">The caller info attributes don't make a parameter optional.</span></span> <span data-ttu-id="63db3-123">この属性は、引数を省略したときに渡される既定値に影響します。</span><span class="sxs-lookup"><span data-stu-id="63db3-123">Instead, they affect the default value that's passed in when the argument is omitted.</span></span> <span data-ttu-id="63db3-124">呼び出し元情報の値は、コンパイル時に中間言語 (IL) 内にリテラルとして出力されます。</span><span class="sxs-lookup"><span data-stu-id="63db3-124">Caller info values are emitted as literals into the Intermediate Language (IL) at compile time.</span></span> <span data-ttu-id="63db3-125">例外の <xref:System.Exception.StackTrace%2A> プロパティの結果とは異なり、難読化による影響は受けません。</span><span class="sxs-lookup"><span data-stu-id="63db3-125">Unlike the results of the <xref:System.Exception.StackTrace%2A> property for exceptions, the results aren't affected by obfuscation.</span></span> <span data-ttu-id="63db3-126">省略可能な引数を明示的に指定して、呼び出し元情報を制御したり、非表示にしたりできます。</span><span class="sxs-lookup"><span data-stu-id="63db3-126">You can explicitly supply the optional arguments to control the caller information or to hide caller information.</span></span>

### <a name="member-names"></a><span data-ttu-id="63db3-127">メンバー名</span><span class="sxs-lookup"><span data-stu-id="63db3-127">Member names</span></span>

<span data-ttu-id="63db3-128">`CallerMemberName` 属性を使用して、呼び出されたメソッドにメンバー名を `String` 引数として指定することを回避できます。</span><span class="sxs-lookup"><span data-stu-id="63db3-128">You can use the `CallerMemberName` attribute to avoid specifying the member name as a `String` argument to the called method.</span></span> <span data-ttu-id="63db3-129">この方法を使用すると、**リファクタリングの名前の変更**で `String` 値が変更されないという問題が発生しなくなります。</span><span class="sxs-lookup"><span data-stu-id="63db3-129">By using this technique, you avoid the problem that **Rename Refactoring** doesn't change the `String` values.</span></span> <span data-ttu-id="63db3-130">この利点は、次のタスクで役立ちます。</span><span class="sxs-lookup"><span data-stu-id="63db3-130">This benefit is especially useful for the following tasks:</span></span>

- <span data-ttu-id="63db3-131">トレース ルーチンと診断ルーチンの使用。</span><span class="sxs-lookup"><span data-stu-id="63db3-131">Using tracing and diagnostic routines.</span></span>
- <span data-ttu-id="63db3-132">データ バインディング時の <xref:System.ComponentModel.INotifyPropertyChanged> インターフェイスの実装。</span><span class="sxs-lookup"><span data-stu-id="63db3-132">Implementing the <xref:System.ComponentModel.INotifyPropertyChanged> interface when binding data.</span></span> <span data-ttu-id="63db3-133">このインターフェイスを使用すると、オブジェクトのプロパティが、プロパティが変更されたことをデータ バインド コントロールに通知できます。これによって、このコントロールは、更新された情報を表示できます。</span><span class="sxs-lookup"><span data-stu-id="63db3-133">This interface allows the property of an object to notify a bound control that the property has changed, so that the control can display the updated information.</span></span> <span data-ttu-id="63db3-134">`CallerMemberName` 属性がない場合は、リテラルとしてプロパティ名を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="63db3-134">Without the `CallerMemberName` attribute, you must specify the property name as a literal.</span></span>

<span data-ttu-id="63db3-135">次のグラフは、`CallerMemberName` 属性の使用時に返されるメンバー名を示します。</span><span class="sxs-lookup"><span data-stu-id="63db3-135">The following chart shows the member names that are returned when you use the `CallerMemberName` attribute.</span></span>

|<span data-ttu-id="63db3-136">呼び出しの発生元</span><span class="sxs-lookup"><span data-stu-id="63db3-136">Calls occur within</span></span>|<span data-ttu-id="63db3-137">メンバー名の結果</span><span class="sxs-lookup"><span data-stu-id="63db3-137">Member name result</span></span>|
|-|-|
|<span data-ttu-id="63db3-138">メソッド、プロパティ、またはイベント</span><span class="sxs-lookup"><span data-stu-id="63db3-138">Method, property, or event</span></span>|<span data-ttu-id="63db3-139">呼び出しが発生したメソッド、プロパティ、またはイベントの名前。</span><span class="sxs-lookup"><span data-stu-id="63db3-139">The name of the method, property, or event from which the call originated.</span></span>|
|<span data-ttu-id="63db3-140">コンストラクター</span><span class="sxs-lookup"><span data-stu-id="63db3-140">Constructor</span></span>|<span data-ttu-id="63db3-141">文字列「.ctor」</span><span class="sxs-lookup"><span data-stu-id="63db3-141">The string ".ctor"</span></span>|
|<span data-ttu-id="63db3-142">静的コンストラクター</span><span class="sxs-lookup"><span data-stu-id="63db3-142">Static constructor</span></span>|<span data-ttu-id="63db3-143">文字列「.cctor」</span><span class="sxs-lookup"><span data-stu-id="63db3-143">The string ".cctor"</span></span>|
|<span data-ttu-id="63db3-144">デストラクターです。</span><span class="sxs-lookup"><span data-stu-id="63db3-144">Destructor</span></span>|<span data-ttu-id="63db3-145">文字列「Finalize」</span><span class="sxs-lookup"><span data-stu-id="63db3-145">The string "Finalize"</span></span>|
|<span data-ttu-id="63db3-146">ユーザー定義の演算子または変換</span><span class="sxs-lookup"><span data-stu-id="63db3-146">User-defined operators or conversions</span></span>|<span data-ttu-id="63db3-147">生成されたメンバー名 (「op_Addition」など)。</span><span class="sxs-lookup"><span data-stu-id="63db3-147">The generated name for the member, for example, "op_Addition".</span></span>|
|<span data-ttu-id="63db3-148">Attribute コンストラクター</span><span class="sxs-lookup"><span data-stu-id="63db3-148">Attribute constructor</span></span>|<span data-ttu-id="63db3-149">属性が適用されるメソッドまたはプロパティの名前。</span><span class="sxs-lookup"><span data-stu-id="63db3-149">The name of the method or property to which the attribute is applied.</span></span> <span data-ttu-id="63db3-150">属性がメンバー内の要素 (パラメーター、戻り値、ジェネリック型パラメーターなど) である場合、この結果は、その要素に関連付けられているメンバーの名前になります。</span><span class="sxs-lookup"><span data-stu-id="63db3-150">If the attribute is any element within a member (such as a parameter, a return value, or a generic type parameter), this result is the name of the member that's associated with that element.</span></span>|
|<span data-ttu-id="63db3-151">含んでいないメンバー (型に適用されているアセンブリ レベルや属性など)</span><span class="sxs-lookup"><span data-stu-id="63db3-151">No containing member (for example, assembly-level or attributes that are applied to types)</span></span>|<span data-ttu-id="63db3-152">省略可能なパラメーターの既定値。</span><span class="sxs-lookup"><span data-stu-id="63db3-152">The default value of the optional parameter.</span></span>|

## <a name="see-also"></a><span data-ttu-id="63db3-153">関連項目</span><span class="sxs-lookup"><span data-stu-id="63db3-153">See also</span></span>

- [<span data-ttu-id="63db3-154">名前付き引数と省略可能な引数</span><span class="sxs-lookup"><span data-stu-id="63db3-154">Named and Optional Arguments</span></span>](../../programming-guide/classes-and-structs/named-and-optional-arguments.md)
- <xref:System.Reflection>
- <xref:System.Attribute>
- [<span data-ttu-id="63db3-155">属性</span><span class="sxs-lookup"><span data-stu-id="63db3-155">Attributes</span></span>](../../../standard/attributes/index.md)
