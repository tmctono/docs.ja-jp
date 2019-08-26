---
title: 相互運用性の概要 - C# プログラミング ガイド
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- COM interop
- C# language, interoperability
- C++ Interop
- interoperability, about interoperability
- platform invoke
ms.assetid: c025b2e0-2357-4c27-8461-118f0090aeff
ms.openlocfilehash: 1342711ca17b0d2bf5122f4c749514e3b96c9ad7
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69921812"
---
# <a name="interoperability-overview-c-programming-guide"></a><span data-ttu-id="15ade-102">相互運用性の概要 (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="15ade-102">Interoperability Overview (C# Programming Guide)</span></span>
<span data-ttu-id="15ade-103">C# マネージド コードとアンマネージド コード間で相互運用を可能にする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="15ade-103">The topic describes methods to enable interoperability between C# managed code and unmanaged code.</span></span>  
  
## <a name="platform-invoke"></a><span data-ttu-id="15ade-104">プラットフォーム呼び出し</span><span class="sxs-lookup"><span data-stu-id="15ade-104">Platform Invoke</span></span>  
 <span data-ttu-id="15ade-105">"*プラットフォーム呼び出し*" とは、Microsoft Windows API にあるような、ダイナミックリンク ライブラリ (DLL) で実装されているアンマネージド関数をマネージド コードで呼び出すことを可能にするサービスです。</span><span class="sxs-lookup"><span data-stu-id="15ade-105">*Platform invoke* is a service that enables managed code to call unmanaged functions that are implemented in dynamic link libraries (DLLs), such as those in the Microsoft Windows API.</span></span> <span data-ttu-id="15ade-106">これはエクスポートされた関数を見つけて呼び出し、必要に応じて相互運用の境界を越えて、その引数 (整数、文字列、配列、構造体、その他) をマーシャリングします。</span><span class="sxs-lookup"><span data-stu-id="15ade-106">It locates and invokes an exported function and marshals its arguments (integers, strings, arrays, structures, and so on) across the interoperation boundary as needed.</span></span>  
  
 <span data-ttu-id="15ade-107">詳細については、「[アンマネージ DLL 関数の処理](../../../framework/interop/consuming-unmanaged-dll-functions.md)」と「[方法: プラットフォーム呼び出しを使用して Wave ファイルを再生する](./how-to-use-platform-invoke-to-play-a-wave-file.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="15ade-107">For more information, see [Consuming Unmanaged DLL Functions](../../../framework/interop/consuming-unmanaged-dll-functions.md) and [How to: Use Platform Invoke to Play a Wave File](./how-to-use-platform-invoke-to-play-a-wave-file.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="15ade-108">[共通言語ランタイム](../../../standard/clr.md) (CLR) が、システム リソースへのアクセスを管理します。</span><span class="sxs-lookup"><span data-stu-id="15ade-108">The [Common Language Runtime](../../../standard/clr.md) (CLR) manages access to system resources.</span></span> <span data-ttu-id="15ade-109">CLR の外部のアンマネージ コードを呼び出すと、このセキュリティ メカニズムがバイパスされるため、セキュリティ リスクが生じます。</span><span class="sxs-lookup"><span data-stu-id="15ade-109">Calling unmanaged code that is outside the CLR bypasses this security mechanism, and therefore presents a security risk.</span></span> <span data-ttu-id="15ade-110">たとえば、アンマネージ コードがアンマネージ コード内のリソースを直接呼び出した場合、CLR のセキュリティ機構がバイパスされます。</span><span class="sxs-lookup"><span data-stu-id="15ade-110">For example, unmanaged code might call resources in unmanaged code directly, bypassing CLR security mechanisms.</span></span> <span data-ttu-id="15ade-111">詳細については、「[.NET でのセキュリティ](../../../standard/security/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="15ade-111">For more information, see [Security in .NET](../../../standard/security/index.md).</span></span>  
  
## <a name="c-interop"></a><span data-ttu-id="15ade-112">C++ Interop</span><span class="sxs-lookup"><span data-stu-id="15ade-112">C++ Interop</span></span>  
 <span data-ttu-id="15ade-113">It Just Works (IJW) とも呼ばれる C++ interop を使用してネイティブ C++ クラスをラップすると、このクラスを C# またはその他の .NET Framework 言語で作成されたコードで使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="15ade-113">You can use C++ interop, also known as It Just Works (IJW), to wrap a native C++ class so that it can be consumed by code that is authored in C# or another .NET Framework language.</span></span> <span data-ttu-id="15ade-114">これを行うには、C++ コードを記述して、ネイティブ DLL または COM コンポーネントをラップします。</span><span class="sxs-lookup"><span data-stu-id="15ade-114">To do this, you write C++ code to wrap a native DLL or COM component.</span></span> <span data-ttu-id="15ade-115">他の .NET Framework 言語とは異なり、Visual C++ には相互運用性サポートが備えられています。これにより、マネージド コードとアンマネージド コードは同じアプリケーション内、また同じファイルでも共存できるようになります。</span><span class="sxs-lookup"><span data-stu-id="15ade-115">Unlike other .NET Framework languages, Visual C++ has interoperability support that enables managed and unmanaged code to be located in the same application and even in the same file.</span></span> <span data-ttu-id="15ade-116">C++ コードは、マネージド アセンブリを生成する **/clr** コンパイラ スイッチを使用して構築できます。</span><span class="sxs-lookup"><span data-stu-id="15ade-116">You then build the C++ code by using the **/clr** compiler switch to produce a managed assembly.</span></span> <span data-ttu-id="15ade-117">最後に、C# プロジェクトのアセンブリへの参照を追加し、他のマネージド クラスを使用するときと同じように、ラップされたオブジェクトを使用します。</span><span class="sxs-lookup"><span data-stu-id="15ade-117">Finally, you add a reference to the assembly in your C# project and use the wrapped objects just as you would use other managed classes.</span></span>  
  
## <a name="exposing-com-components-to-c"></a><span data-ttu-id="15ade-118">C\# への COM コンポーネントの公開</span><span class="sxs-lookup"><span data-stu-id="15ade-118">Exposing COM Components to C\#</span></span>
 <span data-ttu-id="15ade-119">C# プロジェクトから COM コンポーネントを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="15ade-119">You can consume a COM component from a C# project.</span></span> <span data-ttu-id="15ade-120">一般的な手順は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="15ade-120">The general steps are as follows:</span></span>  
  
1. <span data-ttu-id="15ade-121">使用する COM コンポーネントを探して登録します。</span><span class="sxs-lookup"><span data-stu-id="15ade-121">Locate a COM component to use and register it.</span></span> <span data-ttu-id="15ade-122">regsvr32.exe を使用して、COM DLL の登録または登録解除を行います。</span><span class="sxs-lookup"><span data-stu-id="15ade-122">Use regsvr32.exe to register or un–register a COM DLL.</span></span>  
  
2. <span data-ttu-id="15ade-123">プロジェクトに、COM コンポーネントまたはタイプ ライブラリへの参照を追加します。</span><span class="sxs-lookup"><span data-stu-id="15ade-123">Add to the project a reference to the COM component or type library.</span></span>  
  
     <span data-ttu-id="15ade-124">参照を追加する際、Visual Studio は [Tlbimp.exe (タイプ ライブラリ インポーター)](../../../framework/tools/tlbimp-exe-type-library-importer.md) を使用します。これにより、タイプ ライブラリを入力として取得し、.NET Framework 相互運用アセンブリを出力します。</span><span class="sxs-lookup"><span data-stu-id="15ade-124">When you add the reference, Visual Studio uses the [Tlbimp.exe (Type Library Importer)](../../../framework/tools/tlbimp-exe-type-library-importer.md), which takes a type library as input, to output a .NET Framework interop assembly.</span></span> <span data-ttu-id="15ade-125">このアセンブリは、ランタイム呼び出し可能ラッパー (RCW) とも呼ばれ、タイプ ライブラリ内の COM クラスとインターフェイスをラップする、マネージド クラスとインターフェイスを含みます。</span><span class="sxs-lookup"><span data-stu-id="15ade-125">The assembly, also named a runtime callable wrapper (RCW), contains managed classes and interfaces that wrap the COM classes and interfaces that are in the type library.</span></span> <span data-ttu-id="15ade-126">Visual Studio は、生成されたアセンブリへの参照をプロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="15ade-126">Visual Studio adds to the project a reference to the generated assembly.</span></span>  
  
3. <span data-ttu-id="15ade-127">RCW で定義されているクラスのインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="15ade-127">Create an instance of a class that is defined in the RCW.</span></span> <span data-ttu-id="15ade-128">これにより、COM オブジェクトのインスタンスが作成されます。</span><span class="sxs-lookup"><span data-stu-id="15ade-128">This, in turn, creates an instance of the COM object.</span></span>  
  
4. <span data-ttu-id="15ade-129">他のマネージド オブジェクトを使用するときと同様に、オブジェクトを使用します。</span><span class="sxs-lookup"><span data-stu-id="15ade-129">Use the object just as you use other managed objects.</span></span> <span data-ttu-id="15ade-130">オブジェクトがガベージ コレクションによって解放されるとき、COM オブジェクトのインスタンスもメモリから解放されます。</span><span class="sxs-lookup"><span data-stu-id="15ade-130">When the object is reclaimed by garbage collection, the instance of the COM object is also released from memory.</span></span>  
  
 <span data-ttu-id="15ade-131">詳細については、「[.NET Framework への COM コンポーネントの公開](../../../framework/interop/exposing-com-components.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="15ade-131">For more information, see [Exposing COM Components to the .NET Framework](../../../framework/interop/exposing-com-components.md).</span></span>  
  
## <a name="exposing-c-to-com"></a><span data-ttu-id="15ade-132">COM への C# の公開</span><span class="sxs-lookup"><span data-stu-id="15ade-132">Exposing C# to COM</span></span>  
 <span data-ttu-id="15ade-133">COM クライアントは、適切に公開されている C# 型を使用できます。</span><span class="sxs-lookup"><span data-stu-id="15ade-133">COM clients can consume C# types that have been correctly exposed.</span></span> <span data-ttu-id="15ade-134">C# 型を公開する基本的な手順は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="15ade-134">The basic steps to expose C# types are as follows:</span></span>  
  
1. <span data-ttu-id="15ade-135">C# プロジェクトに相互運用属性を追加します。</span><span class="sxs-lookup"><span data-stu-id="15ade-135">Add interop attributes in the C# project.</span></span>  
  
     <span data-ttu-id="15ade-136">アセンブリ COM は、Visual C# プロジェクト プロパティを変更することで参照できるようになります。</span><span class="sxs-lookup"><span data-stu-id="15ade-136">You can make an assembly COM visible by modifying Visual C# project properties.</span></span> <span data-ttu-id="15ade-137">詳細については、「[[アセンブリ情報] ダイアログ ボックス](/visualstudio/ide/reference/assembly-information-dialog-box)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="15ade-137">For more information, see [Assembly Information Dialog Box](/visualstudio/ide/reference/assembly-information-dialog-box).</span></span>  
  
2. <span data-ttu-id="15ade-138">COM タイプ ライブラリを生成し、COM の使用状況に登録します。</span><span class="sxs-lookup"><span data-stu-id="15ade-138">Generate a COM type library and register it for COM usage.</span></span>  
  
     <span data-ttu-id="15ade-139">Visual C# プロジェクト プロパティを変更して、C# アセンブリが COM 相互運用に自動的に登録されるようにできます。</span><span class="sxs-lookup"><span data-stu-id="15ade-139">You can modify Visual C# project properties to automatically register the C# assembly for COM interop.</span></span> <span data-ttu-id="15ade-140">Visual Studio は `/tlb` コマンド ライン スイッチを使用して [Regasm.exe (アセンブリ登録ツール)](../../../framework/tools/regasm-exe-assembly-registration-tool.md) を使用します。これにより、マネージド アセンブリが入力として取得され、タイプ ライブラリを生成できます。</span><span class="sxs-lookup"><span data-stu-id="15ade-140">Visual Studio uses the [Regasm.exe (Assembly Registration Tool)](../../../framework/tools/regasm-exe-assembly-registration-tool.md), using the `/tlb` command-line switch, which takes a managed assembly as input, to generate a type library.</span></span> <span data-ttu-id="15ade-141">タイプ ライブラリは、アセンブリ内の `public` 型を記述し、レジストリ エントリを追加することで、COM クライアントがマネージド クラスを作成できるようにします。</span><span class="sxs-lookup"><span data-stu-id="15ade-141">This type library describes the `public` types in the assembly and adds registry entries so that COM clients can create managed classes.</span></span>  
  
 <span data-ttu-id="15ade-142">詳細については、「[COM への .NET Framework コンポーネントの公開](../../../framework/interop/exposing-dotnet-components-to-com.md)」と「[COM クラスの例](./example-com-class.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="15ade-142">For more information, see [Exposing .NET Framework Components to COM](../../../framework/interop/exposing-dotnet-components-to-com.md) and [Example COM Class](./example-com-class.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15ade-143">関連項目</span><span class="sxs-lookup"><span data-stu-id="15ade-143">See also</span></span>

- [<span data-ttu-id="15ade-144">相互運用パフォーマンスの向上</span><span class="sxs-lookup"><span data-stu-id="15ade-144">Improving Interop Performance</span></span>](https://docs.microsoft.com/previous-versions/msp-n-p/ff647812%28v=pandp.10%29)
- [<span data-ttu-id="15ade-145">COM と .NET の相互運用性の概要</span><span class="sxs-lookup"><span data-stu-id="15ade-145">Introduction to Interoperability between COM and .NET</span></span>](/office/client-developer/outlook/pia/introduction-to-interoperability-between-com-and-net)
- [<span data-ttu-id="15ade-146">COM 相互運用の概要 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="15ade-146">Introduction to COM Interop in Visual Basic</span></span>](../../../visual-basic/programming-guide/com-interop/introduction-to-com-interop.md)
- [<span data-ttu-id="15ade-147">マネージド コードとアンマネージド コード間でのマーシャリング</span><span class="sxs-lookup"><span data-stu-id="15ade-147">Marshaling between Managed and Unmanaged Code</span></span>](../../../framework/interop/interop-marshaling.md)
- [<span data-ttu-id="15ade-148">アンマネージ コードとの相互運用</span><span class="sxs-lookup"><span data-stu-id="15ade-148">Interoperating with Unmanaged Code</span></span>](../../../framework/interop/index.md)
- [<span data-ttu-id="15ade-149">C# プログラミングガイド</span><span class="sxs-lookup"><span data-stu-id="15ade-149">C# Programming Guide</span></span>](../index.md)
