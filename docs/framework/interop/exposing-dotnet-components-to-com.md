---
title: COM への .NET コンポーネントの公開
description: COM に .NET コンポーネントを公開します。 相互運用のための .NET 型の要件を満たします。 相互運用属性を適用します。 COM 用のアセンブリをパッケージ化します。 COM からマネージド型を使用します。
ms.date: 03/30/2017
helpviewer_keywords:
- exposing .NET Framework components to COM
- interoperation with unmanaged code, exposing .NET Framework components
- COM interop, exposing COM components
ms.assetid: e42a65f7-1e61-411f-b09a-aca1bbce24c6
ms.openlocfilehash: 918c90f6741047f7d3cdf89a9b182700ecb2ed93
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617459"
---
# <a name="exposing-net-components-to-com"></a><span data-ttu-id="434a7-107">COM への .NET コンポーネントの公開</span><span class="sxs-lookup"><span data-stu-id="434a7-107">Exposing .NET components to COM</span></span>

<span data-ttu-id="434a7-108">.NET 型の記述とその型をアンマネージ コードから使用することは、開発者にとっては個別のアクティビティです。</span><span class="sxs-lookup"><span data-stu-id="434a7-108">Writing a .NET type and consuming that type from unmanaged code are distinct activities for developers.</span></span> <span data-ttu-id="434a7-109">このセクションでは、COM クライアントと相互運用するマネージド コードの記述のためのいくつかのヒントについて説明します。</span><span class="sxs-lookup"><span data-stu-id="434a7-109">This section describes several tips for writing managed code that interoperates with COM clients:</span></span>

- <span data-ttu-id="434a7-110">[相互運用のための .NET 型の要件を満たす](../../standard/native-interop/qualify-net-types-for-interoperation.md)。</span><span class="sxs-lookup"><span data-stu-id="434a7-110">[Qualifying .NET types for interoperation](../../standard/native-interop/qualify-net-types-for-interoperation.md).</span></span>

     <span data-ttu-id="434a7-111">COM に対して公開するすべてのマネージド型、マネージド メソッド、マネージド プロパティ、マネージド フィールド、およびマネージド イベントは、パブリックとしてください。</span><span class="sxs-lookup"><span data-stu-id="434a7-111">All managed types, methods, properties, fields, and events that you want to expose to COM must be public.</span></span> <span data-ttu-id="434a7-112">型には、パラメーターなしのパブリック コンストラクターが含まれている必要があります。これは COM を通じて呼び出すことができる唯一のコンストラクターです。</span><span class="sxs-lookup"><span data-stu-id="434a7-112">Types must have a public parameterless constructor, which is the only constructor that can be invoked through COM.</span></span>

- <span data-ttu-id="434a7-113">[相互運用属性を適用する](../../standard/native-interop/apply-interop-attributes.md)。</span><span class="sxs-lookup"><span data-stu-id="434a7-113">[Applying interop attributes](../../standard/native-interop/apply-interop-attributes.md).</span></span>

     <span data-ttu-id="434a7-114">マネージド コード内のカスタム属性は、コンポーネントの相互運用性を強化できます。</span><span class="sxs-lookup"><span data-stu-id="434a7-114">Custom attributes within managed code can enhance the interoperability of a component.</span></span>

- <span data-ttu-id="434a7-115">[COM 用にアセンブリをパッケージ化する](packaging-an-assembly-for-com.md)。</span><span class="sxs-lookup"><span data-stu-id="434a7-115">[Packaging an assembly for COM](packaging-an-assembly-for-com.md).</span></span>

     <span data-ttu-id="434a7-116">COM 開発者から、アセンブリの参照と展開に必要な手順をまとめるように求められる場合があります。</span><span class="sxs-lookup"><span data-stu-id="434a7-116">COM developers might require that you summarize the steps involved in referencing and deploying your assemblies.</span></span>

 <span data-ttu-id="434a7-117">さらに、このセクションでは、COM クライアントからマネージド型の使用に関連するタスクを明らかにします。</span><span class="sxs-lookup"><span data-stu-id="434a7-117">Additionally, this section identifies the tasks related to consuming a managed type from a COM client.</span></span>

## <a name="to-consume-a-managed-type-from-com"></a><span data-ttu-id="434a7-118">COM からマネージド型を使用するには</span><span class="sxs-lookup"><span data-stu-id="434a7-118">To consume a managed type from COM</span></span>

1. <span data-ttu-id="434a7-119">[COM にアセンブリを登録する](registering-assemblies-with-com.md)。</span><span class="sxs-lookup"><span data-stu-id="434a7-119">[Register assemblies with COM](registering-assemblies-with-com.md).</span></span>

     <span data-ttu-id="434a7-120">アセンブリ (およびタイプ ライブラリ) 内の型は、デザイン時に登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="434a7-120">Types in an assembly (and type libraries) must be registered at design time.</span></span> <span data-ttu-id="434a7-121">インストーラーでアセンブリが登録されない場合は、Regasm.exe を使用するように COM 開発者に指示します。</span><span class="sxs-lookup"><span data-stu-id="434a7-121">If an installer does not register the assembly, instruct COM developers to use Regasm.exe.</span></span>

2. <span data-ttu-id="434a7-122">[COM から .NET 型を参照する](how-to-reference-net-types-from-com.md)。</span><span class="sxs-lookup"><span data-stu-id="434a7-122">[Reference .NET types from COM](how-to-reference-net-types-from-com.md).</span></span>

     <span data-ttu-id="434a7-123">COM 開発者は、現在使用しているのと同じツールと手法を使用して、アセンブリ内の型を参照できます。</span><span class="sxs-lookup"><span data-stu-id="434a7-123">COM developers can reference types in an assembly using the same tools and techniques they use today.</span></span>

3. <span data-ttu-id="434a7-124">[.NET オブジェクトを呼び出す](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/8hw8h46b(v=vs.100))。</span><span class="sxs-lookup"><span data-stu-id="434a7-124">[Call a .NET object](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/8hw8h46b(v=vs.100)).</span></span>

     <span data-ttu-id="434a7-125">COM 開発者は、アンマネージ型でメソッドを呼び出すのと同じ方法で、.NET オブジェクトでメソッドを呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="434a7-125">COM developers can call methods on the .NET object the same way they call methods on any unmanaged type.</span></span> <span data-ttu-id="434a7-126">たとえば、COM **CoCreateInstance** API は、.NET オブジェクトをアクティブにします。</span><span class="sxs-lookup"><span data-stu-id="434a7-126">For example, the COM **CoCreateInstance** API activates .NET objects.</span></span>

4. <span data-ttu-id="434a7-127">[COM アクセスに対してアプリケーションを展開する](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/c2850st8(v=vs.100))。</span><span class="sxs-lookup"><span data-stu-id="434a7-127">[Deploy an application for COM access](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/c2850st8(v=vs.100)).</span></span>

     <span data-ttu-id="434a7-128">厳格な名前付きのアセンブリは、グローバル アセンブリ キャッシュにインストールすることができ、発行元からの署名が必要です。</span><span class="sxs-lookup"><span data-stu-id="434a7-128">A strong-named assembly can be installed in the global assembly cache and requires a signature from its publisher.</span></span> <span data-ttu-id="434a7-129">厳密な名前のないアセンブリは、クライアントのアプリケーション ディレクトリにインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="434a7-129">Assemblies that are not strong named must be installed in the application directory of the client.</span></span>

## <a name="see-also"></a><span data-ttu-id="434a7-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="434a7-130">See also</span></span>

- [<span data-ttu-id="434a7-131">アンマネージ コードとの相互運用</span><span class="sxs-lookup"><span data-stu-id="434a7-131">Interoperating with Unmanaged Code</span></span>](index.md)
- [<span data-ttu-id="434a7-132">COM 相互運用機能のサンプル:COM クライアントおよび .NET サーバー</span><span class="sxs-lookup"><span data-stu-id="434a7-132">COM Interop Sample: COM Client and .NET Server</span></span>](com-interop-sample-com-client-and-net-server.md)
