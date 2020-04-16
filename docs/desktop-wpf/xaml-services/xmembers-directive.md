---
title: x:Members ディレクティブ
ms.date: 03/30/2017
ms.assetid: 155b393d-3b49-4c5a-8c9e-b3d9893af4e4
ms.openlocfilehash: c751a4f1cdea8dce7ef5165f5225ab3a825c7344
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/27/2020
ms.locfileid: "81432726"
---
# <a name="xmembers-directive"></a><span data-ttu-id="157e3-102">x:Members ディレクティブ</span><span class="sxs-lookup"><span data-stu-id="157e3-102">x:Members Directive</span></span>
<span data-ttu-id="157e3-103">親要素の x:Class に適用される、マークアップで定義されたメンバーのセットを保持します。</span><span class="sxs-lookup"><span data-stu-id="157e3-103">Holds a set of members that are defined in markup, which apply to the x:Class of the parent element.</span></span>

## <a name="xaml-attribute-usage"></a><span data-ttu-id="157e3-104">XAML 属性の使用方法</span><span class="sxs-lookup"><span data-stu-id="157e3-104">XAML Attribute Usage</span></span>

```xaml
<object x:Class="className">
<x:Members>
  oneOrMoreMembers
</x:Members
</object>
```

## <a name="xaml-values"></a><span data-ttu-id="157e3-105">XAML 値</span><span class="sxs-lookup"><span data-stu-id="157e3-105">XAML Values</span></span>

|||
|-|-|
|`className`|<span data-ttu-id="157e3-106">XAML 運用環境のバッキング クラスまたは部分クラスの名前。</span><span class="sxs-lookup"><span data-stu-id="157e3-106">Name of the backing class or partial class for the XAML production.</span></span> <span data-ttu-id="157e3-107">「解説」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="157e3-107">See Remarks.</span></span>|
|`oneOrMoreMembers`|<span data-ttu-id="157e3-108">メンバ定義を表す 1 つ以上のオブジェクト要素。</span><span class="sxs-lookup"><span data-stu-id="157e3-108">One or more object elements that represent member definitions.</span></span> <span data-ttu-id="157e3-109">通常、これらはオブジェクト`x:Property`要素です。</span><span class="sxs-lookup"><span data-stu-id="157e3-109">Typically, these are `x:Property` object elements.</span></span> <span data-ttu-id="157e3-110">「解説」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="157e3-110">See Remarks.</span></span>|

## <a name="remarks"></a><span data-ttu-id="157e3-111">解説</span><span class="sxs-lookup"><span data-stu-id="157e3-111">Remarks</span></span>

<span data-ttu-id="157e3-112">NET XAML サービスの実装では、バッキング クラスや基になるメンバー`x:Members`の実装はありません。</span><span class="sxs-lookup"><span data-stu-id="157e3-112">In .NET XAML Services implementation, there is no backing class or underlying member implementation for `x:Members`.</span></span> <span data-ttu-id="157e3-113">`x:Members`は、任意の型のメンバーとして存在できる特殊な XAML メンバーです。</span><span class="sxs-lookup"><span data-stu-id="157e3-113">`x:Members` is a special XAML member that can exist as a member on any type.</span></span> <span data-ttu-id="157e3-114">XAML ノード ストリームでは`x:Members`、XAML 言語 XAML`Members`名前空間からという名前のメンバーとして表されます。</span><span class="sxs-lookup"><span data-stu-id="157e3-114">In a XAML node stream, `x:Members` is represented as a member named `Members`, from the XAML language XAML namespace.</span></span> <span data-ttu-id="157e3-115">メンバー`Members`には、オブジェクトの読み取り専用`Member`の汎用リストが含まれています。</span><span class="sxs-lookup"><span data-stu-id="157e3-115">The member `Members` contains a read-only generic list of `Member` objects.</span></span> <span data-ttu-id="157e3-116">一般的なマークアップでは、個々のメンバ`x:Property`はプロパティ要素として指定されます。</span><span class="sxs-lookup"><span data-stu-id="157e3-116">In typical markup the individual members are specified as `x:Property` property elements.</span></span> <span data-ttu-id="157e3-117">`x:Property`は、型のプロパティに特化したより正確な型であり、`x:Member`に割り当て可能です。</span><span class="sxs-lookup"><span data-stu-id="157e3-117">`x:Property` is a more precise type specifically for properties of types and is assignable to `x:Member`.</span></span> <span data-ttu-id="157e3-118">詳細については、「 [x: プロパティ ディレクティブ](xproperty-directive.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="157e3-118">For more information, see [x:Property Directive](xproperty-directive.md).</span></span>

<span data-ttu-id="157e3-119">マークアップでメンバーの定義を指定する手段として `x:Members` の実用的な使用法をサポートするため、メンバーを変更可能なクラスに関連付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="157e3-119">To support a practical usage of `x:Members` as a means to specify member definitions in markup, the members must be associated with a class that can be modified.</span></span> <span data-ttu-id="157e3-120">目的とするモデルは、`x:Members` が `x:Class` を指定する型のメンバーとして存在することです。</span><span class="sxs-lookup"><span data-stu-id="157e3-120">The intended model is that `x:Members` exists as a member of a type that specifies an `x:Class`.</span></span> <span data-ttu-id="157e3-121">ただし、型とメンバーを関連付けたり、動的メンバー定義を生成するためのメカニズムは、.NET XAML サービス レベルではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="157e3-121">However, the mechanism for associating types and members or for producing dynamic member definitions is not supported at .NET XAML Services level.</span></span> <span data-ttu-id="157e3-122">これは、XAML のメンバーの定義をサポートするアプリケーション モデルがある個々のフレームワークに残されています。</span><span class="sxs-lookup"><span data-stu-id="157e3-122">This is left to individual frameworks that have application models that support member definitions from XAML.</span></span> <span data-ttu-id="157e3-123">一般に、XAML をマークアップ コンパイルするとともに、XAML と分離コードの統合または純粋な XAML からのアセンブリの生成を行う MSBUILD のビルド操作が、この機能をサポートするために必要です。</span><span class="sxs-lookup"><span data-stu-id="157e3-123">Typically, MSBUILD build actions that markup-compile the XAML and either integrate it with code-behind or produce pure from-XAML assemblies are needed to support that feature.</span></span>

## <a name="xmembers-for-windows-workflow-foundation"></a><span data-ttu-id="157e3-124">x:Windows ワークフローファウンデーションのメンバー</span><span class="sxs-lookup"><span data-stu-id="157e3-124">x:Members for Windows Workflow Foundation</span></span>

<span data-ttu-id="157e3-125">Windows ワークフロー ファン`x:Members`デーションの場合、XAML で完全に構成されたカスタム アクティビティのメンバー、または分離コードを持つアクティビティ デザイナーの XAML 定義動的メンバーが含まれます。</span><span class="sxs-lookup"><span data-stu-id="157e3-125">For Windows Workflow Foundation, `x:Members` contains the members of a custom activity composed entirely in XAML, or XAML –defined dynamic members for an activity designer with code-behind.</span></span> <span data-ttu-id="157e3-126">`x:Class` は、XAML の運用環境のルート要素にも指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="157e3-126">`x:Class` must also be specified on the root element of the XAML production.</span></span> <span data-ttu-id="157e3-127">これは .NET XAML サービス レベルでは必須ではありませんが、カスタム アクティビティと Windows ワークフローファウンデーション XAML 全般をサポートする MSBUILD ビルド アクションによって XAML の運用環境が読み込まれる場合に必要になります。</span><span class="sxs-lookup"><span data-stu-id="157e3-127">This is not a requirement at .NET XAML Services level, but becomes a requirement when the XAML production is loaded by the MSBUILD build actions that support custom activities and Windows Workflow Foundation XAML in general.</span></span> <span data-ttu-id="157e3-128">`x:Members`は、`x:Class`を宣言するオブジェクト要素のマークアップ内の最初の子要素である必要があります。</span><span class="sxs-lookup"><span data-stu-id="157e3-128">`x:Members` must be the first child element in markup of the object element that declares the `x:Class`.</span></span>
