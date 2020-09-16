---
title: XamlName の文法
ms.date: 03/30/2017
helpviewer_keywords:
- DottedXamlName grammar [XAML Services]
- grammar [XAML Services], DottedXamlName
- grammar [XAML Services], XamlName
- names in XAML [XAML Services]
- XamlName grammar [XAML Services]
ms.assetid: 11e4cada-41d2-494d-9531-0d3df4dfcbe3
ms.openlocfilehash: ceb027938b6d4313babbe02949e0b6dd5ee85589
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/15/2020
ms.locfileid: "90556695"
---
# <a name="xamlname-grammar"></a><span data-ttu-id="9e907-102">XamlName の文法</span><span class="sxs-lookup"><span data-stu-id="9e907-102">XamlName Grammar</span></span>

<span data-ttu-id="9e907-103">XamlName 文法は、XAML 言語仕様 (MS XAML) で定義されている特定の文法です。これは便宜上、ここで再現します。</span><span class="sxs-lookup"><span data-stu-id="9e907-103">XamlName Grammar is a specific grammar that is defined in the XAML language specification [MS-XAML], which is reproduced here for convenience.</span></span>

## <a name="from-the-xaml-specification"></a><span data-ttu-id="9e907-104">XAML 仕様から</span><span class="sxs-lookup"><span data-stu-id="9e907-104">From the XAML Specification</span></span>

<span data-ttu-id="9e907-105">[XamlName 仕様は、型とプロパティに使用される一連の有効なシンボル識別子を識別する文法を定義します。</span><span class="sxs-lookup"><span data-stu-id="9e907-105">The [MS-XAML] specification defines the grammar XamlName to identify the set of legal symbolic identifiers used for types and properties.</span></span>

<span data-ttu-id="9e907-106">XamlName 型の文字列値は、次の文法に準拠している必要があります。</span><span class="sxs-lookup"><span data-stu-id="9e907-106">String values that are of type XamlName must conform to the following grammar:</span></span>

```xaml
XamlName ::= NameStartChar ( NameChar )*
NameStartChar ::= LetterCharacter | '_'
NameChar ::= NameStartChar | DecimalDigit | CombiningCharacter
LetterCharacter ::= UnicodeLu | UnicodeLl | UnicodeLo | UnicodeLt | UnicodeNl
DecimalDigit ::= UnicodeNd
CombiningCharacter ::= UnicodeMn | UnicodeMc
```

<span data-ttu-id="9e907-107">Unicode 文字データベースで定義されている次の一般的なカテゴリ値を前提としています。</span><span class="sxs-lookup"><span data-stu-id="9e907-107">Which assumes the following general category values as defined in the Unicode Character Database</span></span>

| <span data-ttu-id="9e907-108">Unicode カテゴリ</span><span class="sxs-lookup"><span data-stu-id="9e907-108">Unicode category</span></span>   | <span data-ttu-id="9e907-109">説明</span><span class="sxs-lookup"><span data-stu-id="9e907-109">Description</span></span>                   |
|--------------------|-------------------------------|
| <span data-ttu-id="9e907-110">ルー語</span><span class="sxs-lookup"><span data-stu-id="9e907-110">Lu</span></span>                 | <span data-ttu-id="9e907-111">Letter, Uppercase (字、大文字)</span><span class="sxs-lookup"><span data-stu-id="9e907-111">Letter, Uppercase</span></span>             |
| <span data-ttu-id="9e907-112">Ll</span><span class="sxs-lookup"><span data-stu-id="9e907-112">Ll</span></span>                 | <span data-ttu-id="9e907-113">Letter, Lowercase (字、小文字)</span><span class="sxs-lookup"><span data-stu-id="9e907-113">Letter, Lowercase</span></span>             |
| <span data-ttu-id="9e907-114">Lt</span><span class="sxs-lookup"><span data-stu-id="9e907-114">Lt</span></span>                 | <span data-ttu-id="9e907-115">Letter, Titlecase (字、タイトル文字)</span><span class="sxs-lookup"><span data-stu-id="9e907-115">Letter, Titlecase</span></span>             |
| <span data-ttu-id="9e907-116">Lm</span><span class="sxs-lookup"><span data-stu-id="9e907-116">Lm</span></span>                 | <span data-ttu-id="9e907-117">Letter, Modifier (字、修飾)</span><span class="sxs-lookup"><span data-stu-id="9e907-117">Letter, Modifier</span></span>              |
| <span data-ttu-id="9e907-118">Lo</span><span class="sxs-lookup"><span data-stu-id="9e907-118">Lo</span></span>                 | <span data-ttu-id="9e907-119">Letter, Other (字、その他)</span><span class="sxs-lookup"><span data-stu-id="9e907-119">Letter, Other</span></span>                 |
| <span data-ttu-id="9e907-120">Mn</span><span class="sxs-lookup"><span data-stu-id="9e907-120">Mn</span></span>                 | <span data-ttu-id="9e907-121">マーク (スペースなし)</span><span class="sxs-lookup"><span data-stu-id="9e907-121">Mark, Non-Spacing</span></span>             |
| <span data-ttu-id="9e907-122">Mc</span><span class="sxs-lookup"><span data-stu-id="9e907-122">Mc</span></span>                 | <span data-ttu-id="9e907-123">Mark, Spacing Combining (結合文字、幅あり)</span><span class="sxs-lookup"><span data-stu-id="9e907-123">Mark, Spacing Combining</span></span>       |
| <span data-ttu-id="9e907-124">Nd</span><span class="sxs-lookup"><span data-stu-id="9e907-124">Nd</span></span>                 | <span data-ttu-id="9e907-125">Number、Decimal</span><span class="sxs-lookup"><span data-stu-id="9e907-125">Number, Decimal</span></span>               |
| <span data-ttu-id="9e907-126">Nl</span><span class="sxs-lookup"><span data-stu-id="9e907-126">Nl</span></span>                 | <span data-ttu-id="9e907-127">Number, Letter (数、字)</span><span class="sxs-lookup"><span data-stu-id="9e907-127">Number, Letter</span></span>                |

<span data-ttu-id="9e907-128">XAML は、プロパティおよびイベント修飾参照に使用される2番目の文法、DottedXamlName、およびアタッチされたメンバーに対しても定義します。</span><span class="sxs-lookup"><span data-stu-id="9e907-128">XAML defines a second grammar, DottedXamlName, that is used for property and event qualified references, and also for attached members.</span></span> <span data-ttu-id="9e907-129">詳細については、「」 <xref:System.Windows.DependencyProperty> および「 [XAML の概要 (WPF)](../fundamentals/xaml.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9e907-129">For more information, see <xref:System.Windows.DependencyProperty> and [XAML Overview (WPF)](../fundamentals/xaml.md).</span></span>

<span data-ttu-id="9e907-130">DottedXamlName 型の文字列値は、次の文法に準拠している必要があります。</span><span class="sxs-lookup"><span data-stu-id="9e907-130">String values that are of type DottedXamlName must conform to the following grammar:</span></span>

```xaml
DottedXamlName ::= XamlName '.' XamlName
```

## <a name="remarks"></a><span data-ttu-id="9e907-131">Remarks</span><span class="sxs-lookup"><span data-stu-id="9e907-131">Remarks</span></span>

<span data-ttu-id="9e907-132">完全な仕様については、「 [ \[ MS XAML \] ](/previous-versions/msp-n-p/ff650760(v=pandp.10))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9e907-132">For the complete specification, see [\[MS-XAML\]](/previous-versions/msp-n-p/ff650760(v=pandp.10)).</span></span>
