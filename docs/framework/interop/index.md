---
title: アンマネージ コードとの相互運用
ms.date: 01/17/2018
helpviewer_keywords:
- unmanaged code, interoperation
- managed code, interoperation with unmanaged code
- .NET Framework, interoperation with unmanaged code
- unmanaged code
- interoperation with unmanaged code
- interoperation with unmanaged code, about interoperation
- components [.NET Framework], interoperation with unmanaged code
ms.assetid: ccb68ce7-b0e9-4ffb-839d-03b1cd2c1258
ms.openlocfilehash: 12183f390a5178f038c6dd2122a72a33e31ae0ee
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2019
ms.locfileid: "73457968"
---
# <a name="interoperating-with-unmanaged-code"></a><span data-ttu-id="260d9-102">アンマネージ コードとの相互運用</span><span class="sxs-lookup"><span data-stu-id="260d9-102">Interoperating with unmanaged code</span></span>

<span data-ttu-id="260d9-103">.NET Framework は、COM コンポーネント、COM+ サービス、外部のタイプ ライブラリ、各種のオペレーティング システム サービスとの相互運用を促進します。</span><span class="sxs-lookup"><span data-stu-id="260d9-103">The .NET Framework promotes interaction with COM components, COM+ services, external type libraries, and many operating system services.</span></span> <span data-ttu-id="260d9-104">データ型、メソッド署名、およびエラー処理機構は、マネージド オブジェクト モデルとアンマネージド オブジェクト モデルでは異なります。</span><span class="sxs-lookup"><span data-stu-id="260d9-104">Data types, method signatures, and error-handling mechanisms vary between managed and unmanaged object models.</span></span> <span data-ttu-id="260d9-105">.NET Framework コンポーネントとアンマネージ コードの間の相互運用を簡素化し、移行パスを簡単にするために、共通言語ランタイムがクライアントとサーバーの両方からこれらのオブジェクト モデルの違いを隠します。</span><span class="sxs-lookup"><span data-stu-id="260d9-105">To simplify interoperation between .NET Framework components and unmanaged code and to ease the migration path, the common language runtime conceals from both clients and servers the differences in these object models.</span></span>

<span data-ttu-id="260d9-106">ランタイムの制御下で実行されるコードは、マネージド コードと呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="260d9-106">Code that executes under the control of the runtime is called managed code.</span></span> <span data-ttu-id="260d9-107">逆に、ランタイムの外部で実行されるコードはアンマネージ コードと呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="260d9-107">Conversely, code that runs outside the runtime is called unmanaged code.</span></span> <span data-ttu-id="260d9-108">アンマネージ コードの例としては、COM コンポーネント、ActiveX インターフェイス、Windows API 関数があります。</span><span class="sxs-lookup"><span data-stu-id="260d9-108">COM components, ActiveX interfaces, and Windows API functions are examples of unmanaged code.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="260d9-109">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="260d9-109">In this section</span></span>

[<span data-ttu-id="260d9-110">.NET Framework への COM コンポーネントの公開</span><span class="sxs-lookup"><span data-stu-id="260d9-110">Exposing COM Components to the .NET Framework</span></span>](exposing-com-components.md)  
<span data-ttu-id="260d9-111">.NET Framework アプリケーションから COM コンポーネントを使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="260d9-111">Describes how to use COM components from .NET Framework applications.</span></span>

[<span data-ttu-id="260d9-112">COM への .NET Framework コンポーネントの公開</span><span class="sxs-lookup"><span data-stu-id="260d9-112">Exposing .NET Framework Components to COM</span></span>](exposing-dotnet-components-to-com.md)  
<span data-ttu-id="260d9-113">COM アプリケーションから .NET Framework コンポーネントを使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="260d9-113">Describes how to use .NET Framework components from COM applications.</span></span>

[<span data-ttu-id="260d9-114">アンマネージ DLL 関数の処理</span><span class="sxs-lookup"><span data-stu-id="260d9-114">Consuming Unmanaged DLL Functions</span></span>](consuming-unmanaged-dll-functions.md)  
<span data-ttu-id="260d9-115">プラットフォーム呼び出しを使用して、アンマネージ DLL 関数を呼び出す方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="260d9-115">Describes how to call unmanaged DLL functions using platform invoke.</span></span>

[<span data-ttu-id="260d9-116">相互運用マーシャリング</span><span class="sxs-lookup"><span data-stu-id="260d9-116">Interop Marshaling</span></span>](interop-marshaling.md)  
<span data-ttu-id="260d9-117">COM 相互運用機能とプラットフォーム呼び出しのマーシャリングについて説明します。</span><span class="sxs-lookup"><span data-stu-id="260d9-117">Describes marshaling for COM interop and platform invoke.</span></span>

[<span data-ttu-id="260d9-118">方法: HRESULT に例外を割り当てる</span><span class="sxs-lookup"><span data-stu-id="260d9-118">How to: Map HRESULTs and Exceptions</span></span>](how-to-map-hresults-and-exceptions.md)  
<span data-ttu-id="260d9-119">例外と HRESULT の間のマッピングについて説明します。</span><span class="sxs-lookup"><span data-stu-id="260d9-119">Describes the mapping between exceptions and HRESULTs.</span></span>

[<span data-ttu-id="260d9-120">型の等価性と埋め込まれた相互運用機能型</span><span class="sxs-lookup"><span data-stu-id="260d9-120">Type Equivalence and Embedded Interop Types</span></span>](type-equivalence-and-embedded-interop-types.md)  
<span data-ttu-id="260d9-121">COM 型の型情報をアセンブリに埋め込む方法と、共通言語ランタイムが埋め込みの COM 型の等価性を決定する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="260d9-121">Describes how type information for COM types is embedded in assemblies, and how the common language runtime determines the equivalence of embedded COM types.</span></span>

[<span data-ttu-id="260d9-122">方法: Tlbimp.exe を使用してプライマリ相互運用機能アセンブリを生成する</span><span class="sxs-lookup"><span data-stu-id="260d9-122">How to: Generate Primary Interop Assemblies Using Tlbimp.exe</span></span>](how-to-generate-primary-interop-assemblies-using-tlbimp-exe.md)  
<span data-ttu-id="260d9-123">*Tlbimp.exe* (タイプ ライブラリ インポーター) を使用して、プライマリ相互運用機能アセンブリを生成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="260d9-123">Describes how to produce primary interop assemblies using *Tlbimp.exe* (Type Library Importer).</span></span>

[<span data-ttu-id="260d9-124">方法: プライマリ相互運用機能アセンブリを登録する</span><span class="sxs-lookup"><span data-stu-id="260d9-124">How to: Register Primary Interop Assemblies</span></span>](how-to-register-primary-interop-assemblies.md)  
<span data-ttu-id="260d9-125">プロジェクトで参照する前に、プライマリ相互運用機能アセンブリを登録する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="260d9-125">Describes how to register the primary interop assemblies before you can reference them in your projects.</span></span>

[<span data-ttu-id="260d9-126">登録を必要としない COM 相互運用機能</span><span class="sxs-lookup"><span data-stu-id="260d9-126">Registration-Free COM Interop</span></span>](registration-free-com-interop.md)  
<span data-ttu-id="260d9-127">COM 相互運用機能によって Windows レジストリを使用せずにコンポーネントをアクティブ化する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="260d9-127">Describes how COM interop can activate components without using the Windows registry.</span></span>

[<span data-ttu-id="260d9-128">方法: 登録を必要としないアクティベーション用の .NET Framework ベースの COM コンポーネントを構成する</span><span class="sxs-lookup"><span data-stu-id="260d9-128">How to: Configure .NET Framework-Based COM Components for Registration-Free Activation</span></span>](configure-net-framework-based-com-components-for-reg.md)  
<span data-ttu-id="260d9-129">アプリケーション マニフェストを作成する方法と、コンポーネント マニフェストを作成して埋め込む方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="260d9-129">Describes how to create an application manifest and how to create and embed a component manifest.</span></span>

## <a name="related-sections"></a><span data-ttu-id="260d9-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="260d9-130">Related sections</span></span>

[<span data-ttu-id="260d9-131">COM ラッパー</span><span class="sxs-lookup"><span data-stu-id="260d9-131">COM Wrappers</span></span>](../../standard/native-interop/com-wrappers.md)  
<span data-ttu-id="260d9-132">COM 相互運用機能が提供するラッパーをについて説明します。</span><span class="sxs-lookup"><span data-stu-id="260d9-132">Describes the wrappers provided by COM interop.</span></span>
