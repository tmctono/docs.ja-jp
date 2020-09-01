---
description: -nullable (C# コンパイラ オプション)
title: -nullable (C# コンパイラ オプション)
author: IEvangelist
ms.author: dapine
ms.date: 06/04/2020
f1_keywords:
- /nullable
helpviewer_keywords:
- nullable compiler option [C#]
- /nullable compiler option [C#]
- -nullable compiler option [C#]
ms.openlocfilehash: f9c6c204d2563865f741c6ddb4644eb56f956c12
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/30/2020
ms.locfileid: "89125047"
---
# <a name="-nullable-c-compiler-options"></a><span data-ttu-id="c79d2-103">-nullable (C# コンパイラ オプション)</span><span class="sxs-lookup"><span data-stu-id="c79d2-103">-nullable (C# Compiler Options)</span></span>

<span data-ttu-id="c79d2-104">**-nullable** オプションを使用すると、必要な Null 許容コンテキストを指定できます。</span><span class="sxs-lookup"><span data-stu-id="c79d2-104">The **-nullable** option lets you specify the desired nullable context.</span></span>

## <a name="syntax"></a><span data-ttu-id="c79d2-105">構文</span><span class="sxs-lookup"><span data-stu-id="c79d2-105">Syntax</span></span>

```console
-nullable[+ | -]
-nullable:{enable | disable | warnings | annotations}
```

## <a name="arguments"></a><span data-ttu-id="c79d2-106">引数</span><span class="sxs-lookup"><span data-stu-id="c79d2-106">Arguments</span></span>

<span data-ttu-id="c79d2-107">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="c79d2-107">`+` &#124; `-`</span></span>  
<span data-ttu-id="c79d2-108">`+`、または単に **-nullable** を指定すると、コンパイラによって Null 許容のコンテキストが有効になります。</span><span class="sxs-lookup"><span data-stu-id="c79d2-108">Specifying `+`, or just **-nullable**, causes the compiler to enable nullable context.</span></span> <span data-ttu-id="c79d2-109">**nullable** を指定しない場合に有効な `-` を指定すると、Null 許容コンテキストは無効になります。</span><span class="sxs-lookup"><span data-stu-id="c79d2-109">Specifying `-`, which is in effect if you do not specify **-nullable**, disables nullable context.</span></span>

<span data-ttu-id="c79d2-110">`enable` &#124; `disable` &#124; `warnings` &#124; `annotations`</span><span class="sxs-lookup"><span data-stu-id="c79d2-110">`enable` &#124; `disable` &#124; `warnings` &#124; `annotations`</span></span>  
<span data-ttu-id="c79d2-111">Null 許容コンテキスト オプションを指定します。</span><span class="sxs-lookup"><span data-stu-id="c79d2-111">Specifies the nullable context option.</span></span> <span data-ttu-id="c79d2-112">有効または無効にする `+` または `-` に似ていますが、Null 許容のコンテキストをより細かく指定できます。</span><span class="sxs-lookup"><span data-stu-id="c79d2-112">Similar to `+` or `-`, to enable and disable, but allows for more granularity of nullable context specificity.</span></span> <span data-ttu-id="c79d2-113">`enable` 引数は、 **-nullable** の指定と同じですが、Null 許容のコンテキストを有効にします。</span><span class="sxs-lookup"><span data-stu-id="c79d2-113">The `enable` argument, which is in effect the same as if you specify **-nullable**, enables the nullable context.</span></span> <span data-ttu-id="c79d2-114">`disable` を指定すると、Null 許容コンテキストは無効になります。</span><span class="sxs-lookup"><span data-stu-id="c79d2-114">Specifying `disable` will disable nullable context.</span></span> <span data-ttu-id="c79d2-115">**nullable: warning** のように `warnings` 引数を指定すると、Null 許容の警告コンテキストが有効になります。</span><span class="sxs-lookup"><span data-stu-id="c79d2-115">When providing the `warnings` argument, **-nullable:warnings**, the nullable warning context is enabled.</span></span> <span data-ttu-id="c79d2-116">**-nullable:annotations** のように `annotations` 引数を指定すると、Null 許容の注釈コンテキストが有効になります。</span><span class="sxs-lookup"><span data-stu-id="c79d2-116">When specifying the `annotations` argument, **-nullable:annotations**, the nullable annotation context is enabled.</span></span>

## <a name="remarks"></a><span data-ttu-id="c79d2-117">Remarks</span><span class="sxs-lookup"><span data-stu-id="c79d2-117">Remarks</span></span>

<span data-ttu-id="c79d2-118">フロー分析は、実行可能コード内の変数に null 値が許容されるかどうかを推測するために使用します。</span><span class="sxs-lookup"><span data-stu-id="c79d2-118">Flow analysis is used to infer the nullability of variables within executable code.</span></span> <span data-ttu-id="c79d2-119">null 値が変数で許容されるかの推定は、変数の宣言されている null 許容とは無関係です。</span><span class="sxs-lookup"><span data-stu-id="c79d2-119">The inferred nullability of a variable is independent of the variable's declared nullability.</span></span> <span data-ttu-id="c79d2-120">メソッド呼び出しは、条件付きで省略される場合でも分析されます。</span><span class="sxs-lookup"><span data-stu-id="c79d2-120">Method calls are analyzed even when they are conditionally omitted.</span></span> <span data-ttu-id="c79d2-121">たとえば、リリース モードの <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> です。</span><span class="sxs-lookup"><span data-stu-id="c79d2-121">For instance, <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> in release mode.</span></span>

<span data-ttu-id="c79d2-122">次の属性の注釈が付いたメソッド呼び出しも、フロー分析に影響します。</span><span class="sxs-lookup"><span data-stu-id="c79d2-122">Invocation of methods annotated with the following attributes will also affect flow analysis:</span></span>

- <span data-ttu-id="c79d2-123">単純な実行前条件: <xref:System.Diagnostics.CodeAnalysis.AllowNullAttribute> と <xref:System.Diagnostics.CodeAnalysis.DisallowNullAttribute></span><span class="sxs-lookup"><span data-stu-id="c79d2-123">Simple pre-conditions: <xref:System.Diagnostics.CodeAnalysis.AllowNullAttribute> and <xref:System.Diagnostics.CodeAnalysis.DisallowNullAttribute></span></span>
- <span data-ttu-id="c79d2-124">単純な実行後条件: <xref:System.Diagnostics.CodeAnalysis.MaybeNullAttribute> と <xref:System.Diagnostics.CodeAnalysis.NotNullAttribute></span><span class="sxs-lookup"><span data-stu-id="c79d2-124">Simple post-conditions: <xref:System.Diagnostics.CodeAnalysis.MaybeNullAttribute> and <xref:System.Diagnostics.CodeAnalysis.NotNullAttribute></span></span>
- <span data-ttu-id="c79d2-125">条件付きの実行後条件: <xref:System.Diagnostics.CodeAnalysis.MaybeNullWhenAttribute> および <xref:System.Diagnostics.CodeAnalysis.NotNullWhenAttribute></span><span class="sxs-lookup"><span data-stu-id="c79d2-125">Conditional post-conditions: <xref:System.Diagnostics.CodeAnalysis.MaybeNullWhenAttribute> and <xref:System.Diagnostics.CodeAnalysis.NotNullWhenAttribute></span></span>
- <span data-ttu-id="c79d2-126"><xref:System.Diagnostics.CodeAnalysis.DoesNotReturnIfAttribute> (<xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> の `DoesNotReturnIf(false)` など) と <xref:System.Diagnostics.CodeAnalysis.DoesNotReturnAttribute></span><span class="sxs-lookup"><span data-stu-id="c79d2-126"><xref:System.Diagnostics.CodeAnalysis.DoesNotReturnIfAttribute> (for example, `DoesNotReturnIf(false)` for <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>) and <xref:System.Diagnostics.CodeAnalysis.DoesNotReturnAttribute></span></span>
- <xref:System.Diagnostics.CodeAnalysis.NotNullIfNotNullAttribute>
- <span data-ttu-id="c79d2-127">メンバーの実行後条件: <xref:System.Diagnostics.CodeAnalysis.MemberNotNullAttribute.%23ctor(System.String)> と <xref:System.Diagnostics.CodeAnalysis.MemberNotNullAttribute.%23ctor(System.String[])></span><span class="sxs-lookup"><span data-stu-id="c79d2-127">Member post-conditions: <xref:System.Diagnostics.CodeAnalysis.MemberNotNullAttribute.%23ctor(System.String)> and <xref:System.Diagnostics.CodeAnalysis.MemberNotNullAttribute.%23ctor(System.String[])></span></span>

### <a name="to-set-this-compiler-option-in-a-project"></a><span data-ttu-id="c79d2-128">プロジェクトでこのコンパイラ オプションを設定するには</span><span class="sxs-lookup"><span data-stu-id="c79d2-128">To set this compiler option in a project</span></span>

<span data-ttu-id="c79d2-129">*.csproj* ファイルを編集して、`Project/PropertyGroup` 階層に `<Nullable>` タグを追加します。</span><span class="sxs-lookup"><span data-stu-id="c79d2-129">Edit the *.csproj* file to add the `<Nullable>` tag within a `Project/PropertyGroup` hierarchy:</span></span>

```xml
<Project Sdk="...">

  <PropertyGroup>
    <Nullable>enable</Nullable>
  </PropertyGroup>

</Project>
```

## <a name="see-also"></a><span data-ttu-id="c79d2-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="c79d2-130">See also</span></span>

- [<span data-ttu-id="c79d2-131">C# コンパイラ オプション</span><span class="sxs-lookup"><span data-stu-id="c79d2-131">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="c79d2-132">Null 許容参照型</span><span class="sxs-lookup"><span data-stu-id="c79d2-132">Nullable reference types</span></span>](../../nullable-references.md)
