---
title: アセンブリを使用したプログラム
ms.date: 08/20/2019
helpviewer_keywords:
- assemblies [.NET Framework], programming
- programming assemblies
ms.assetid: 25918b15-701d-42c7-95fc-c290d08648d6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 03babe701b46eab54a76094c4728af80e6d9911e
ms.sourcegitcommit: 7b1ce327e8c84f115f007be4728d29a89efe11ef
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/13/2019
ms.locfileid: "70972619"
---
# <a name="program-with-assemblies"></a><span data-ttu-id="da12b-102">アセンブリを使用したプログラム</span><span class="sxs-lookup"><span data-stu-id="da12b-102">Program with assemblies</span></span>
<span data-ttu-id="da12b-103">アセンブリは .NET Framework の構成要素であり、配置、バージョン管理、再利用、アクティブ化のスコープの指定、およびセキュリティ アクセス許可の基本単位となります。</span><span class="sxs-lookup"><span data-stu-id="da12b-103">Assemblies are the building blocks of the .NET Framework; they form the fundamental unit of deployment, version control, reuse, activation scoping, and security permissions.</span></span> <span data-ttu-id="da12b-104">共通言語ランタイムは、型の実装に関して必要な情報をアセンブリから取得します。</span><span class="sxs-lookup"><span data-stu-id="da12b-104">An assembly provides the common language runtime with the information it needs to be aware of type implementations.</span></span> <span data-ttu-id="da12b-105">アセンブリは、相互に連携して 1 つの論理的な機能単位を形成するように構築された型やリソースの集合です。</span><span class="sxs-lookup"><span data-stu-id="da12b-105">It is a collection of types and resources that are built to work together and form a logical unit of functionality.</span></span> <span data-ttu-id="da12b-106">共通言語ランタイムにとって、型はアセンブリのコンテキストの外部には存在しません。</span><span class="sxs-lookup"><span data-stu-id="da12b-106">To the runtime, a type does not exist outside the context of an assembly.</span></span>  
  
 <span data-ttu-id="da12b-107">このセクションでは、モジュールを作成する方法、モジュールからアセンブリを作成する方法、キー ペアを作成して厳密な名前でアセンブリに署名する方法、およびグローバル アセンブリ キャッシュにアセンブリをインストールする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="da12b-107">This section describes how to create modules, create assemblies from modules, create a key pair and sign an assembly with a strong name, and install an assembly into the global assembly cache.</span></span> <span data-ttu-id="da12b-108">さらに、[MSIL 逆アセンブラー (Ildasm.exe)](../../framework/tools/ildasm-exe-il-disassembler.md) を使ってアセンブリ マニフェストの情報を表示する方法も説明します。</span><span class="sxs-lookup"><span data-stu-id="da12b-108">In addition, this section describes how to use the [MSIL Disassembler (Ildasm.exe)](../../framework/tools/ildasm-exe-il-disassembler.md) to view assembly manifest information.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="da12b-109">.NET Framework Version 2.0 以降では、現在読み込まれているランタイムよりもバージョン番号が新しい .NET Framework のバージョンでコンパイルされたアセンブリは、ランタイムに読み込まれないようになりました。</span><span class="sxs-lookup"><span data-stu-id="da12b-109">Starting with the .NET Framework version 2.0, the runtime will not load an assembly that was compiled with a version of the .NET Framework that has a higher version number than the currently loaded runtime.</span></span> <span data-ttu-id="da12b-110">これはメジャー コンポーネントとマイナー コンポーネントの組み合わせたバージョン番号に適用されます。</span><span class="sxs-lookup"><span data-stu-id="da12b-110">This applies to the combination of the major and minor components of the version number.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="da12b-111">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="da12b-111">In this section</span></span>  
 [<span data-ttu-id="da12b-112">アセンブリを作成する</span><span class="sxs-lookup"><span data-stu-id="da12b-112">Create assemblies</span></span>](create.md)  
 <span data-ttu-id="da12b-113">単一ファイル アセンブリおよびマルチファイル アセンブリの概要を示します。</span><span class="sxs-lookup"><span data-stu-id="da12b-113">Provides an overview of single-file and multifile assemblies.</span></span>  
  
 [<span data-ttu-id="da12b-114">アセンブリ名</span><span class="sxs-lookup"><span data-stu-id="da12b-114">Assembly names</span></span>](names.md)  
 <span data-ttu-id="da12b-115">アセンブリの名前付けの概要を説明します。</span><span class="sxs-lookup"><span data-stu-id="da12b-115">Provides an overview of assembly naming.</span></span>  
  
 [<span data-ttu-id="da12b-116">方法: アセンブリの完全修飾名を特定する</span><span class="sxs-lookup"><span data-stu-id="da12b-116">How to: Determine an assembly's fully qualified name</span></span>](find-fully-qualified-name.md)  
 <span data-ttu-id="da12b-117">アセンブリの完全修飾名を特定する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="da12b-117">Describes how to determine the fully qualified name of an assembly.</span></span>  
  
 [<span data-ttu-id="da12b-118">イントラネット アプリケーションの完全信頼での実行</span><span class="sxs-lookup"><span data-stu-id="da12b-118">Run intranet applications in full trust</span></span>](../../framework/app-domains/running-intranet-applications-in-full-trust.md)  
 <span data-ttu-id="da12b-119">イントラネット共有上の完全に信頼されたアセンブリに対して従来のセキュリティ ポリシーを指定する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="da12b-119">Describes how to specify legacy security policy for full-trust assemblies on an intranet share.</span></span>  
  
 [<span data-ttu-id="da12b-120">アセンブリの場所</span><span class="sxs-lookup"><span data-stu-id="da12b-120">Assembly location</span></span>](location.md)  
 <span data-ttu-id="da12b-121">アセンブリを配置する場所の概要について説明します。</span><span class="sxs-lookup"><span data-stu-id="da12b-121">Provides an overview of where to locate assemblies.</span></span>  
  
 [<span data-ttu-id="da12b-122">方法: シングルファイル アセンブリをビルドする</span><span class="sxs-lookup"><span data-stu-id="da12b-122">How to: Build a single-file assembly</span></span>](../../framework/app-domains/build-single-file-assembly.md)  
 <span data-ttu-id="da12b-123">シングルファイル アセンブリを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="da12b-123">Describes how to create a single-file assembly.</span></span>  
  
 [<span data-ttu-id="da12b-124">マルチファイル アセンブリ</span><span class="sxs-lookup"><span data-stu-id="da12b-124">Multifile assemblies</span></span>](../../framework/app-domains/multifile-assemblies.md)  
 <span data-ttu-id="da12b-125">マルチファイル アセンブリを作成する理由について説明します。</span><span class="sxs-lookup"><span data-stu-id="da12b-125">Describes reasons for creating multifile assemblies.</span></span>  
  
 [<span data-ttu-id="da12b-126">方法: マルチファイル アセンブリをビルドする</span><span class="sxs-lookup"><span data-stu-id="da12b-126">How to: Build a multifile assembly</span></span>](../../framework/app-domains/build-multifile-assembly.md)  
 <span data-ttu-id="da12b-127">マルチファイル アセンブリを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="da12b-127">Describes how to create a multifile assembly.</span></span>  
  
 [<span data-ttu-id="da12b-128">アセンブリ属性の設定</span><span class="sxs-lookup"><span data-stu-id="da12b-128">Set assembly attributes</span></span>](set-attributes.md)  
 <span data-ttu-id="da12b-129">アセンブリの属性とその設定方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="da12b-129">Describes assembly attributes and how to set them.</span></span>  
  
 [<span data-ttu-id="da12b-130">厳密な名前付きアセンブリの作成と使用</span><span class="sxs-lookup"><span data-stu-id="da12b-130">Create and use strong-named assemblies</span></span>](create-use-strong-named.md)  
 <span data-ttu-id="da12b-131">厳密な名前でアセンブリに署名する方法と理由について説明します。方法に関するトピックが含まれています。</span><span class="sxs-lookup"><span data-stu-id="da12b-131">Describes how and why you sign an assembly with a strong name, and includes how-to topics.</span></span>  
  
 [<span data-ttu-id="da12b-132">アセンブリへの遅延署名</span><span class="sxs-lookup"><span data-stu-id="da12b-132">Delay-sign an assembly</span></span>](delay-sign.md)  
 <span data-ttu-id="da12b-133">アセンブリに遅延署名する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="da12b-133">Describes how to delay-sign an assembly.</span></span>  
  
 [<span data-ttu-id="da12b-134">アセンブリとグローバル アセンブリ キャッシュの使用</span><span class="sxs-lookup"><span data-stu-id="da12b-134">Work with assemblies and the global assembly cache</span></span>](../../framework/app-domains/working-with-assemblies-and-the-gac.md)  
 <span data-ttu-id="da12b-135">アセンブリをグローバル アセンブリ キャッシュに追加する方法と理由について説明します。方法に関するトピックが含まれています。</span><span class="sxs-lookup"><span data-stu-id="da12b-135">Describes how and why you add assemblies to the global assembly cache, and includes how-to topics.</span></span>  
  
 [<span data-ttu-id="da12b-136">方法: アセンブリの内容を表示する</span><span class="sxs-lookup"><span data-stu-id="da12b-136">How to: View assembly contents</span></span>](view-contents.md)  
 <span data-ttu-id="da12b-137">MSIL 逆アセンブラー (Ildasm.exe) を使ってアセンブリの内容を表示する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="da12b-137">Describes how to use the MSIL Disassembler (Ildasm.exe) to view assembly contents.</span></span>  
  
 [<span data-ttu-id="da12b-138">共通言語ランタイムでの型の転送</span><span class="sxs-lookup"><span data-stu-id="da12b-138">Type forwarding in the common language runtime</span></span>](type-forwarding.md)  
 <span data-ttu-id="da12b-139">型の転送を使うことで、既存のアプリケーションを壊さずに異なるアセンブリに型を移動する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="da12b-139">Describes how to use type forwarding to move a type into a different assembly without breaking existing applications.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="da12b-140">関連項目</span><span class="sxs-lookup"><span data-stu-id="da12b-140">Reference</span></span>  
 <xref:System.Reflection.Assembly>  
 <span data-ttu-id="da12b-141">アセンブリを表す .NET Framework クラス。</span><span class="sxs-lookup"><span data-stu-id="da12b-141">The .NET Framework class that represents an assembly.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="da12b-142">関連項目</span><span class="sxs-lookup"><span data-stu-id="da12b-142">Related sections</span></span>  
 [<span data-ttu-id="da12b-143">方法: アセンブリから型およびメンバーの情報を取得する</span><span class="sxs-lookup"><span data-stu-id="da12b-143">How to: Obtain type and member information from an assembly</span></span>](../../framework/reflection-and-codedom/get-type-member-information.md)  
 <span data-ttu-id="da12b-144">プログラムでアセンブリから型およびその他の情報を取得する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="da12b-144">Describes how to programmatically obtain type and other information from an assembly.</span></span>  
  
 [<span data-ttu-id="da12b-145">.NET のアセンブリ</span><span class="sxs-lookup"><span data-stu-id="da12b-145">Assemblies in .NET</span></span>](index.md)  
 <span data-ttu-id="da12b-146">共通言語ランタイムのアセンブリの概念的な概要について説明します。</span><span class="sxs-lookup"><span data-stu-id="da12b-146">Provides a conceptual overview of common language runtime assemblies.</span></span>  
  
 [<span data-ttu-id="da12b-147">アセンブリのバージョン管理</span><span class="sxs-lookup"><span data-stu-id="da12b-147">Assembly versioning</span></span>](versioning.md)  
 <span data-ttu-id="da12b-148">アセンブリのバインディング、および <xref:System.Reflection.AssemblyVersionAttribute> 属性と <xref:System.Reflection.AssemblyInformationalVersionAttribute> 属性の概要について説明します。</span><span class="sxs-lookup"><span data-stu-id="da12b-148">Provides an overview of assembly binding and of the <xref:System.Reflection.AssemblyVersionAttribute> and <xref:System.Reflection.AssemblyInformationalVersionAttribute> attributes.</span></span>  
  
 [<span data-ttu-id="da12b-149">ランタイムがアセンブリを検索する方法</span><span class="sxs-lookup"><span data-stu-id="da12b-149">How the runtime locates assemblies</span></span>](../../framework/deployment/how-the-runtime-locates-assemblies.md)  
 <span data-ttu-id="da12b-150">ランタイムがバインド要求を満たすために使うアセンブリを決定する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="da12b-150">Describes how the runtime determines which assembly to use to fulfill a binding request.</span></span>  
  
 <span data-ttu-id="da12b-151">[リフレクション](../../framework/reflection-and-codedom/reflection.md) </span><span class="sxs-lookup"><span data-stu-id="da12b-151">[Reflection](../../framework/reflection-and-codedom/reflection.md) </span></span>  
 <span data-ttu-id="da12b-152">**Reflection** クラスを使用して、アセンブリに関する情報を取得する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="da12b-152">Describes how to use the **Reflection** class to obtain information about an assembly.</span></span>
