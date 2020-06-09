---
title: -nullable (C# コンパイラ オプション)
ms.date: 06/04/2020
f1_keywords:
- /nullable
helpviewer_keywords:
- nullable compiler option [C#]
- /nullable compiler option [C#]
- -nullable compiler option [C#]
ms.openlocfilehash: a68255dba18a022784cd4aaf0027c371893c577b
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/05/2020
ms.locfileid: "84449799"
---
# <a name="-nullable-c-compiler-options"></a><span data-ttu-id="9e8eb-102">-nullable (C# コンパイラ オプション)</span><span class="sxs-lookup"><span data-stu-id="9e8eb-102">-nullable (C# Compiler Options)</span></span>

<span data-ttu-id="9e8eb-103">**-nullable** オプションを使用すると、必要な Null 許容コンテキストを指定できます。</span><span class="sxs-lookup"><span data-stu-id="9e8eb-103">The **-nullable** option lets you specify the desired nullable context.</span></span>

## <a name="syntax"></a><span data-ttu-id="9e8eb-104">構文</span><span class="sxs-lookup"><span data-stu-id="9e8eb-104">Syntax</span></span>

```console
-nullable[+ | -]
-nullable:{enable | disable | warnings | annotations}
```

## <a name="arguments"></a><span data-ttu-id="9e8eb-105">引数</span><span class="sxs-lookup"><span data-stu-id="9e8eb-105">Arguments</span></span>

<span data-ttu-id="9e8eb-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="9e8eb-106">`+` &#124; `-`</span></span>  
<span data-ttu-id="9e8eb-107">`+`、または単に **-nullable** を指定すると、コンパイラによって Null 許容のコンテキストが有効になります。</span><span class="sxs-lookup"><span data-stu-id="9e8eb-107">Specifying `+`, or just **-nullable**, causes the compiler to enable nullable context.</span></span> <span data-ttu-id="9e8eb-108">**nullable** を指定しない場合に有効な `-` を指定すると、Null 許容コンテキストは無効になります。</span><span class="sxs-lookup"><span data-stu-id="9e8eb-108">Specifying `-`, which is in effect if you do not specify **-nullable**, disables nullable context.</span></span>

<span data-ttu-id="9e8eb-109">`enable` &#124; `disable` &#124; `warnings` &#124; `annotations`</span><span class="sxs-lookup"><span data-stu-id="9e8eb-109">`enable` &#124; `disable` &#124; `warnings` &#124; `annotations`</span></span>  
<span data-ttu-id="9e8eb-110">Null 許容コンテキスト オプションを指定します。</span><span class="sxs-lookup"><span data-stu-id="9e8eb-110">Specifies the nullable context option.</span></span> <span data-ttu-id="9e8eb-111">有効または無効にする `+` または `-` に似ていますが、Null 許容のコンテキストをより細かく指定できます。</span><span class="sxs-lookup"><span data-stu-id="9e8eb-111">Similar to `+` or `-`, to enable and disable, but allows for more granularity of nullable context specificity.</span></span> <span data-ttu-id="9e8eb-112">`enable` 引数は、 **-nullable** の指定と同じですが、Null 許容のコンテキストを有効にします。</span><span class="sxs-lookup"><span data-stu-id="9e8eb-112">The `enable` argument, which is in effect the same as if you specify **-nullable**, enables the nullable context.</span></span> <span data-ttu-id="9e8eb-113">`disable` を指定すると、Null 許容コンテキストは無効になります。</span><span class="sxs-lookup"><span data-stu-id="9e8eb-113">Specifying `disable` will disable nullable context.</span></span> <span data-ttu-id="9e8eb-114">**nullable: warning** のように `warnings` 引数を指定すると、Null 許容の警告コンテキストが有効になります。</span><span class="sxs-lookup"><span data-stu-id="9e8eb-114">When providing the `warnings` argument, **-nullable:warnings**, the nullable warning context is enabled.</span></span> <span data-ttu-id="9e8eb-115">**-nullable:annotations** のように `annotations` 引数を指定すると、Null 許容の注釈コンテキストが有効になります。</span><span class="sxs-lookup"><span data-stu-id="9e8eb-115">When specifying the `annotations` argument, **-nullable:annotations**, the nullable annotation context is enabled.</span></span>

## <a name="remarks"></a><span data-ttu-id="9e8eb-116">Remarks</span><span class="sxs-lookup"><span data-stu-id="9e8eb-116">Remarks</span></span>

<span data-ttu-id="9e8eb-117">フロー分析は、実行可能コード内の変数に null 値が許容されるかどうかを推測するために使用します。</span><span class="sxs-lookup"><span data-stu-id="9e8eb-117">Flow analysis is used to infer the nullability of variables within executable code.</span></span> <span data-ttu-id="9e8eb-118">null 値が変数で許容されるかの推定は、変数の宣言されている null 許容とは無関係です。</span><span class="sxs-lookup"><span data-stu-id="9e8eb-118">The inferred nullability of a variable is independent of the variable's declared nullability.</span></span> <span data-ttu-id="9e8eb-119">メソッド呼び出しは、条件付きで省略される場合でも分析されます。</span><span class="sxs-lookup"><span data-stu-id="9e8eb-119">Method calls are analyzed even when they are conditionally omitted.</span></span> <span data-ttu-id="9e8eb-120">たとえば、リリース モードの <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> です。</span><span class="sxs-lookup"><span data-stu-id="9e8eb-120">For instance, <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> in release mode.</span></span>

<span data-ttu-id="9e8eb-121">次の属性の注釈が付いたメソッド呼び出しも、フロー分析に影響します。</span><span class="sxs-lookup"><span data-stu-id="9e8eb-121">Invocation of methods annotated with the following attributes will also affect flow analysis:</span></span>

- <span data-ttu-id="9e8eb-122">単純な実行前条件: <xref:System.Diagnostics.CodeAnalysis.AllowNullAttribute> と <xref:System.Diagnostics.CodeAnalysis.DisallowNullAttribute></span><span class="sxs-lookup"><span data-stu-id="9e8eb-122">Simple pre-conditions: <xref:System.Diagnostics.CodeAnalysis.AllowNullAttribute> and <xref:System.Diagnostics.CodeAnalysis.DisallowNullAttribute></span></span>
- <span data-ttu-id="9e8eb-123">単純な実行後条件: <xref:System.Diagnostics.CodeAnalysis.MaybeNullAttribute> と <xref:System.Diagnostics.CodeAnalysis.NotNullAttribute></span><span class="sxs-lookup"><span data-stu-id="9e8eb-123">Simple post-conditions: <xref:System.Diagnostics.CodeAnalysis.MaybeNullAttribute> and <xref:System.Diagnostics.CodeAnalysis.NotNullAttribute></span></span>
- <span data-ttu-id="9e8eb-124">条件付きの実行後条件: <xref:System.Diagnostics.CodeAnalysis.MaybeNullWhenAttribute> および <xref:System.Diagnostics.CodeAnalysis.NotNullWhenAttribute></span><span class="sxs-lookup"><span data-stu-id="9e8eb-124">Conditional post-conditions: <xref:System.Diagnostics.CodeAnalysis.MaybeNullWhenAttribute> and <xref:System.Diagnostics.CodeAnalysis.NotNullWhenAttribute></span></span>
- <span data-ttu-id="9e8eb-125"><xref:System.Diagnostics.CodeAnalysis.DoesNotReturnIfAttribute> (例: <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> 用の `DoesNotReturnIf(false)`) と <xref:System.Diagnostics.CodeAnalysis.DoesNotReturnAttribute></span><span class="sxs-lookup"><span data-stu-id="9e8eb-125"><xref:System.Diagnostics.CodeAnalysis.DoesNotReturnIfAttribute> (e.g. `DoesNotReturnIf(false)` for <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>) and <xref:System.Diagnostics.CodeAnalysis.DoesNotReturnAttribute></span></span>
- <xref:System.Diagnostics.CodeAnalysis.NotNullIfNotNullAttribute>
- <span data-ttu-id="9e8eb-126">メンバーの実行後条件: <xref:System.Diagnostics.CodeAnalysis.MemberNotNullAttribute.%23ctor(System.String)> と <xref:System.Diagnostics.CodeAnalysis.MemberNotNullAttribute.%23ctor(System.String[])></span><span class="sxs-lookup"><span data-stu-id="9e8eb-126">Member post-conditions: <xref:System.Diagnostics.CodeAnalysis.MemberNotNullAttribute.%23ctor(System.String)> and <xref:System.Diagnostics.CodeAnalysis.MemberNotNullAttribute.%23ctor(System.String[])></span></span>

### <a name="to-set-this-compiler-option-in-a-project"></a><span data-ttu-id="9e8eb-127">プロジェクトでこのコンパイラ オプションを設定するには</span><span class="sxs-lookup"><span data-stu-id="9e8eb-127">To set this compiler option in a project</span></span>

<span data-ttu-id="9e8eb-128">*.csproj* を編集して、`Project/PropertyGroup` 階層に `<Nullable>` タグを追加します。</span><span class="sxs-lookup"><span data-stu-id="9e8eb-128">Edit the *.csproj* to add the `<Nullable>` tag within a `Project/PropertyGroup` hierarchy:</span></span>

```xml
<Project Sdk="...">

  <PropertyGroup>
    <Nullable>enable</Nullable>
  </PropertyGroup>

</Project>
```

## <a name="see-also"></a><span data-ttu-id="9e8eb-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="9e8eb-129">See also</span></span>

- [<span data-ttu-id="9e8eb-130">C# コンパイラ オプション</span><span class="sxs-lookup"><span data-stu-id="9e8eb-130">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="9e8eb-131">Null 許容参照型</span><span class="sxs-lookup"><span data-stu-id="9e8eb-131">Nullable reference types</span></span>](../../nullable-references.md)
