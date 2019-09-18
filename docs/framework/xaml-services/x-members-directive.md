---
title: x:Members ディレクティブ
ms.date: 03/30/2017
ms.assetid: 155b393d-3b49-4c5a-8c9e-b3d9893af4e4
ms.openlocfilehash: ca42079c1c40a8fb3b1ddfc8f4a6f742768fa9e1
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2019
ms.locfileid: "71053762"
---
# <a name="xmembers-directive"></a><span data-ttu-id="1f079-102">x:Members ディレクティブ</span><span class="sxs-lookup"><span data-stu-id="1f079-102">x:Members Directive</span></span>
<span data-ttu-id="1f079-103">マークアップで定義されているメンバーのセットを保持します。これは、親要素の x:Class に適用されます。</span><span class="sxs-lookup"><span data-stu-id="1f079-103">Holds a set of members that are defined in markup, which apply to the x:Class of the parent element.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="1f079-104">XAML 属性の使用方法</span><span class="sxs-lookup"><span data-stu-id="1f079-104">XAML Attribute Usage</span></span>  
  
```xaml  
<object x:Class="className">  
  <x:Members>  
    oneOrMoreMembers  
  </x:Members  
</object>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="1f079-105">XAML 値</span><span class="sxs-lookup"><span data-stu-id="1f079-105">XAML Values</span></span>  
  
|||  
|-|-|  
|`className`|<span data-ttu-id="1f079-106">XAML 運用環境のバッキング クラスまたは部分クラスの名前。</span><span class="sxs-lookup"><span data-stu-id="1f079-106">Name of the backing class or partial class for the XAML production.</span></span> <span data-ttu-id="1f079-107">「解説」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1f079-107">See Remarks.</span></span>|  
|`oneOrMoreMembers`|<span data-ttu-id="1f079-108">メンバー定義を表す1つ以上のオブジェクト要素。</span><span class="sxs-lookup"><span data-stu-id="1f079-108">One or more object elements that represent member definitions.</span></span> <span data-ttu-id="1f079-109">通常、これらは`x:Property`オブジェクト要素です。</span><span class="sxs-lookup"><span data-stu-id="1f079-109">Typically, these are `x:Property` object elements.</span></span> <span data-ttu-id="1f079-110">「解説」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1f079-110">See Remarks.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1f079-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="1f079-111">Remarks</span></span>  
 <span data-ttu-id="1f079-112">.NET Framework XAML サービスの実装では、のバッキングクラスまたは基になるメンバー `x:Members`の実装はありません。</span><span class="sxs-lookup"><span data-stu-id="1f079-112">In the .NET Framework XAML Services implementation, there is no backing class or underlying member implementation for `x:Members`.</span></span> <span data-ttu-id="1f079-113">`x:Members`は、任意の型のメンバーとして存在できる特殊な XAML メンバーです。</span><span class="sxs-lookup"><span data-stu-id="1f079-113">`x:Members` is a special XAML member that can exist as a member on any type.</span></span> <span data-ttu-id="1f079-114">Xaml ノードストリーム`x:Members`では、は、xaml 言語の xaml `Members`名前空間からという名前のメンバーとして表されます。</span><span class="sxs-lookup"><span data-stu-id="1f079-114">In a XAML node stream, `x:Members` is represented as a member named `Members`, from the XAML language XAML namespace.</span></span> <span data-ttu-id="1f079-115">メンバー `Members`には、オブジェクトの読み取り専用の`Member`ジェネリックリストが含まれています。</span><span class="sxs-lookup"><span data-stu-id="1f079-115">The member `Members` contains a read-only generic list of `Member` objects.</span></span> <span data-ttu-id="1f079-116">一般的なマークアップでは、個々の`x:Property`メンバーはプロパティ要素として指定されます。</span><span class="sxs-lookup"><span data-stu-id="1f079-116">In typical markup the individual members are specified as `x:Property` property elements.</span></span> <span data-ttu-id="1f079-117">`x:Property`は、型のプロパティ専用のより正確な型であり、 `x:Member`に割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="1f079-117">`x:Property` is a more precise type specifically for properties of types and is assignable to `x:Member`.</span></span> <span data-ttu-id="1f079-118">詳細については、「 [X:Property ディレクティブ](x-property-directive.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1f079-118">For more information, see [x:Property Directive](x-property-directive.md).</span></span>  
  
 <span data-ttu-id="1f079-119">マークアップでメンバーの定義を指定する手段として `x:Members` の実用的な使用法をサポートするため、メンバーを変更可能なクラスに関連付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="1f079-119">To support a practical usage of `x:Members` as a means to specify member definitions in markup, the members must be associated with a class that can be modified.</span></span> <span data-ttu-id="1f079-120">目的とするモデルは、`x:Members` が `x:Class` を指定する型のメンバーとして存在することです。</span><span class="sxs-lookup"><span data-stu-id="1f079-120">The intended model is that `x:Members` exists as a member of a type that specifies an `x:Class`.</span></span> <span data-ttu-id="1f079-121">ただし、型とメンバーを関連付けたり、動的メンバーの定義を作成したりするメカニズムは、.NET Framework XAML サービス レベルではサポートされません。</span><span class="sxs-lookup"><span data-stu-id="1f079-121">However, the mechanism for associating types and members or for producing dynamic member definitions is not supported at the .NET Framework XAML Services level.</span></span> <span data-ttu-id="1f079-122">これは、XAML のメンバーの定義をサポートするアプリケーション モデルがある個々のフレームワークに残されています。</span><span class="sxs-lookup"><span data-stu-id="1f079-122">This is left to individual frameworks that have application models that support member definitions from XAML.</span></span> <span data-ttu-id="1f079-123">一般に、XAML をマークアップ コンパイルするとともに、XAML と分離コードの統合または純粋な XAML からのアセンブリの生成を行う MSBUILD のビルド操作が、この機能をサポートするために必要です。</span><span class="sxs-lookup"><span data-stu-id="1f079-123">Typically, MSBUILD build actions that markup-compile the XAML and either integrate it with code-behind or produce pure from-XAML assemblies are needed to support that feature.</span></span>  
  
## <a name="xmembers-for-windows-workflow-foundation"></a><span data-ttu-id="1f079-124">Windows Workflow Foundation 用の x:Members</span><span class="sxs-lookup"><span data-stu-id="1f079-124">x:Members for Windows Workflow Foundation</span></span>  
 <span data-ttu-id="1f079-125">Windows Workflow Foundation の場合`x:Members`は、xaml で完全に構成されるカスタムアクティビティのメンバー、または分離コードを持つアクティビティデザイナーの xaml で定義された動的メンバーが含まれます。</span><span class="sxs-lookup"><span data-stu-id="1f079-125">For Windows Workflow Foundation, `x:Members` contains the members of a custom activity composed entirely in XAML, or XAML –defined dynamic members for an activity designer with code-behind.</span></span> <span data-ttu-id="1f079-126">`x:Class` は、XAML の運用環境のルート要素にも指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1f079-126">`x:Class` must also be specified on the root element of the XAML production.</span></span> <span data-ttu-id="1f079-127">これは、.NET Framework XAML サービス レベルの要件ではありませんが、全般にカスタム アクティビティと Windows Workflow Foundation の XAML をサポートする MSBUILD のビルド アクションによって XAML の運用環境が読み込まれるときの要件になります。</span><span class="sxs-lookup"><span data-stu-id="1f079-127">This is not a requirement at the .NET Framework XAML Services level, but becomes a requirement when the XAML production is loaded by the MSBUILD build actions that support custom activities and Windows Workflow Foundation XAML in general.</span></span> <span data-ttu-id="1f079-128">`x:Members`は、を`x:Class`宣言するオブジェクト要素のマークアップ内の最初の子要素である必要があります。</span><span class="sxs-lookup"><span data-stu-id="1f079-128">`x:Members` must be the first child element in markup of the object element that declares the `x:Class`.</span></span>
