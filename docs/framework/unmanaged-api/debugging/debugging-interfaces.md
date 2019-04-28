---
title: デバッグのインターフェイス
ms.date: 02/07/2019
helpviewer_keywords:
- unmanaged interfaces [.NET Framework], debugging
- debugging interfaces [.NET Framework]
- interfaces [.NET Framework debugging]
ms.assetid: b6297c26-7624-4431-8af4-14112d07bcd5
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d939063aaefb00d4db3de604df0dbd1b2175bf95
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61698422"
---
# <a name="debugging-interfaces"></a><span data-ttu-id="eae7e-102">デバッグのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="eae7e-102">Debugging Interfaces</span></span>
<span data-ttu-id="eae7e-103">ここでは、共通言語ランタイム (CLR: Common Language Runtime) で実行するプログラムのデバッグを処理するアンマネージ インターフェイスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="eae7e-103">This section describes the unmanaged interfaces that handle the debugging of a program that is executing in the common language runtime (CLR).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="eae7e-104">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="eae7e-104">In This Section</span></span>  
 <span data-ttu-id="eae7e-105">[ICLRDataEnumMemoryRegions インターフェイス](iclrdataenummemoryregions-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="eae7e-105">[ICLRDataEnumMemoryRegions Interface](iclrdataenummemoryregions-interface.md)\\</span></span>
 <span data-ttu-id="eae7e-106">呼び出し元が指定したメモリ範囲を列挙するメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="eae7e-106">Provides a method to enumerate regions of memory that are specified by callers.</span></span>  
  
 <span data-ttu-id="eae7e-107">[ICLRDataEnumMemoryRegionsCallback インターフェイス](iclrdataenummemoryregionscallback-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="eae7e-107">[ICLRDataEnumMemoryRegionsCallback Interface](iclrdataenummemoryregionscallback-interface.md)\\</span></span>
 <span data-ttu-id="eae7e-108">メモリの指定された領域を列挙した結果の `EnumMemoryRegions` をデバッガーにレポートするコールバック メソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="eae7e-108">Provides a callback method for `EnumMemoryRegions` to report to the debugger, the result of an attempt to enumerate a specified region of memory.</span></span>  
  
 <span data-ttu-id="eae7e-109">[ICLRDataTarget インターフェイス](iclrdatatarget-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="eae7e-109">[ICLRDataTarget Interface](iclrdatatarget-interface.md)\\</span></span>
 <span data-ttu-id="eae7e-110">対象の CLR プロセスと対話するためのメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="eae7e-110">Provides methods for interaction with a target CLR process.</span></span>  
  
 <span data-ttu-id="eae7e-111">[ICLRDataTarget2 インターフェイス](iclrdatatarget2-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="eae7e-111">[ICLRDataTarget2 Interface](iclrdatatarget2-interface.md)\\</span></span>
 <span data-ttu-id="eae7e-112">データ アクセス サービス層で使用して対象プロセスの仮想メモリ領域を操作する、`ICLRDataTarget` のサブクラスです。</span><span class="sxs-lookup"><span data-stu-id="eae7e-112">A subclass of `ICLRDataTarget` that is used by the data access services layer to manipulate virtual memory regions in the target process.</span></span>  
  
 <span data-ttu-id="eae7e-113">[ICLRDataTarget3 インターフェイス](iclrdatatarget3-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="eae7e-113">[ICLRDataTarget3 Interface](iclrdatatarget3-interface.md)\\</span></span>
 <span data-ttu-id="eae7e-114">サブクラス[ICLRDataTarget2](iclrdatatarget2-interface.md)例外情報へのアクセスを提供します。</span><span class="sxs-lookup"><span data-stu-id="eae7e-114">A subclass of [ICLRDataTarget2](iclrdatatarget2-interface.md) that provides access to exception information.</span></span>  
  
 <span data-ttu-id="eae7e-115">[ICLRDebugging インターフェイス](iclrdebugging-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="eae7e-115">[ICLRDebugging Interface](iclrdebugging-interface.md)\\</span></span>
 <span data-ttu-id="eae7e-116">デバッグ用にモジュールの読み込みとアンロードを処理するメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="eae7e-116">Provides methods that handle loading and unloading modules for debugging.</span></span>  
  
 <span data-ttu-id="eae7e-117">[ICLRDebuggingLibraryProvider インターフェイス](iclrdebugginglibraryprovider-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="eae7e-117">[ICLRDebuggingLibraryProvider Interface](iclrdebugginglibraryprovider-interface.md)\\</span></span>
 <span data-ttu-id="eae7e-118">含まれています、 [ProvideLibrary メソッド](iclrdebugginglibraryprovider-providelibrary-method.md)メソッドで、ライブラリ プロバイダーの共通言語ランタイム バージョン固有デバッグ ライブラリを検索しに読み込む要求を許可するコールバック インターフェイスを取得します。</span><span class="sxs-lookup"><span data-stu-id="eae7e-118">Includes the [ProvideLibrary Method](iclrdebugginglibraryprovider-providelibrary-method.md) method, which gets a library provider callback interface that allows common language runtime version-specific debugging libraries to be located and loaded on demand.</span></span>  
  
 <span data-ttu-id="eae7e-119">[ICLRMetadataLocator インターフェイス](iclrmetadatalocator-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="eae7e-119">[ICLRMetadataLocator Interface](iclrmetadatalocator-interface.md)\\</span></span>
 <span data-ttu-id="eae7e-120">データ アクセス サービス層で使用して、対象プロセス内のアセンブリのメタデータを見つけるためのインターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="eae7e-120">Interface used by the data access services layer to locate metadata of assemblies in a target process.</span></span>  
  
 <span data-ttu-id="eae7e-121">[ICorDebug インターフェイス](icordebug-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="eae7e-121">[ICorDebug Interface](icordebug-interface.md)\\</span></span>
 <span data-ttu-id="eae7e-122">開発者が CLR 環境でアプリケーションをデバッグできるようにするメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="eae7e-122">Provides methods that allow developers to debug applications in the CLR environment.</span></span>  
  
 <span data-ttu-id="eae7e-123">[ICorDebugAppDomain インターフェイス](icordebugappdomain-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="eae7e-123">[ICorDebugAppDomain Interface](icordebugappdomain-interface.md)\\</span></span>
 <span data-ttu-id="eae7e-124">アプリケーション ドメインをデバッグするためのメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="eae7e-124">Provides methods for debugging application domains.</span></span>  
  
 <span data-ttu-id="eae7e-125">[ICorDebugAppDomain2 インターフェイス](icordebugappdomain2-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="eae7e-125">[ICorDebugAppDomain2 Interface](icordebugappdomain2-interface.md)\\</span></span>
 <span data-ttu-id="eae7e-126">配列、ポインター、関数ポインター、および ByRef 型を使用するメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="eae7e-126">Provides methods to work with arrays, pointers, function pointers, and ByRef types.</span></span> <span data-ttu-id="eae7e-127">これは、`ICorDebugAppDomain` インターフェイスの機能を拡張するインターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="eae7e-127">This interface is an extension of the `ICorDebugAppDomain` interface.</span></span>  
  
 <span data-ttu-id="eae7e-128">[ICorDebugAppDomain3 インターフェイス](icordebugappdomain3-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="eae7e-128">[ICorDebugAppDomain3 Interface](icordebugappdomain3-interface.md)\\</span></span>
 <span data-ttu-id="eae7e-129">アプリケーション ドメインで [!INCLUDE[wrt](../../../../includes/wrt-md.md)] 型を操作するメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="eae7e-129">Provides methods to work with the [!INCLUDE[wrt](../../../../includes/wrt-md.md)] types in an application domain.</span></span> <span data-ttu-id="eae7e-130">このインターフェイスは、`ICorDebugAppDomain` インターフェイスと `ICorDebugAppDomain2` インターフェイスを拡張します。</span><span class="sxs-lookup"><span data-stu-id="eae7e-130">This interface is an extension of the `ICorDebugAppDomain` and `ICorDebugAppDomain2` interfaces.</span></span>  
  
 <span data-ttu-id="eae7e-131">[ICorDebugAppDomain4 インターフェイス](icordebugappdomain4-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="eae7e-131">[ICorDebugAppDomain4 Interface](icordebugappdomain4-interface.md)\\</span></span>
 <span data-ttu-id="eae7e-132">論理的に拡張し、 [ICorDebugAppDomain](icordebugappdomain-interface.md)インターフェイスが COM 呼び出し可能ラッパーからマネージ オブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="eae7e-132">Logically extends the [ICorDebugAppDomain](icordebugappdomain-interface.md) interface to get a managed object from a COM callable wrapper.</span></span>  
  
 <span data-ttu-id="eae7e-133">[ICorDebugAppDomainEnum インターフェイス](icordebugappdomainenum-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="eae7e-133">[ICorDebugAppDomainEnum Interface](icordebugappdomainenum-interface.md)\\</span></span>
 <span data-ttu-id="eae7e-134">列挙体の次の位置から、指定した数の `ICorDebugAppDomain` の値を返すメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="eae7e-134">Provides a method that returns a specified number of `ICorDebugAppDomain` values starting at the next location in the enumeration.</span></span>  
  
 <span data-ttu-id="eae7e-135">[ICorDebugArrayValue インターフェイス](icordebugarrayvalue-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="eae7e-135">[ICorDebugArrayValue Interface](icordebugarrayvalue-interface.md)\\</span></span>
 <span data-ttu-id="eae7e-136">1 次元または多次元の配列を表す `ICorDebugHeapValue` のサブクラスです。</span><span class="sxs-lookup"><span data-stu-id="eae7e-136">A subclass of `ICorDebugHeapValue` that represents a single-dimensional or multi-dimensional array.</span></span>  
  
 <span data-ttu-id="eae7e-137">[ICorDebugAssembly インターフェイス](icordebugassembly-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="eae7e-137">[ICorDebugAssembly Interface](icordebugassembly-interface.md)\\</span></span>
 <span data-ttu-id="eae7e-138">アセンブリを表します。</span><span class="sxs-lookup"><span data-stu-id="eae7e-138">Represents an assembly.</span></span>  
  
 <span data-ttu-id="eae7e-139">[ICorDebugAssembly2 インターフェイス](icordebugassembly2-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="eae7e-139">[ICorDebugAssembly2 Interface](icordebugassembly2-interface.md)\\</span></span>
 <span data-ttu-id="eae7e-140">アセンブリを表します。</span><span class="sxs-lookup"><span data-stu-id="eae7e-140">Represents an assembly.</span></span> <span data-ttu-id="eae7e-141">これは、`ICorDebugAssembly` インターフェイスの機能を拡張するインターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="eae7e-141">This interface is an extension of the `ICorDebugAssembly` interface.</span></span>  
  
 <span data-ttu-id="eae7e-142">[ICorDebugAssembly3 インターフェイス](icordebugassembly3-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="eae7e-142">[ICorDebugAssembly3 Interface](icordebugassembly3-interface.md)\\</span></span>
 <span data-ttu-id="eae7e-143">論理的に拡張し、 [ICorDebugAssembly](icordebugassembly-interface.md)コンテナー アセンブリとその格納されているアセンブリのサポートを提供するインターフェイス。</span><span class="sxs-lookup"><span data-stu-id="eae7e-143">Logically extends the [ICorDebugAssembly](icordebugassembly-interface.md) interface to provide support for container assemblies and their contained assemblies.</span></span> <span data-ttu-id="eae7e-144">**.NET ネイティブのみで使用できます。**</span><span class="sxs-lookup"><span data-stu-id="eae7e-144">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="eae7e-145">[ICorDebugAssemblyEnum インターフェイス](icordebugassemblyenum-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="eae7e-145">[ICorDebugAssemblyEnum Interface](icordebugassemblyenum-interface.md)\\</span></span>
 <span data-ttu-id="eae7e-146">`ICorDebugEnum` メソッドを実装し、`ICorDebugAssembly` 配列を列挙します。</span><span class="sxs-lookup"><span data-stu-id="eae7e-146">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugAssembly` arrays.</span></span>  
  
 <span data-ttu-id="eae7e-147">[ICorDebugBlockingObjectEnum インターフェイス](icordebugblockingobjectenum-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="eae7e-147">[ICorDebugBlockingObjectEnum Interface](icordebugblockingobjectenum-interface.md)\\</span></span>
 <span data-ttu-id="eae7e-148">一覧については、列挙子を提供します。 [CorDebugBlockingObject](cordebugblockingobject-structure.md)構造体。</span><span class="sxs-lookup"><span data-stu-id="eae7e-148">Provides an enumerator for a list of [CorDebugBlockingObject](cordebugblockingobject-structure.md) structures.</span></span>  
  
 <span data-ttu-id="eae7e-149">[ICorDebugBoxValue インターフェイス](icordebugboxvalue-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="eae7e-149">[ICorDebugBoxValue Interface](icordebugboxvalue-interface.md)\\</span></span>
 <span data-ttu-id="eae7e-150">ボックス化された値クラスのオブジェクトを表す `ICorDebugHeapValue` のサブクラス。</span><span class="sxs-lookup"><span data-stu-id="eae7e-150">A subclass of `ICorDebugHeapValue` that represents a boxed value class object.</span></span>  
  
 <span data-ttu-id="eae7e-151">[ICorDebugBreakpoint インターフェイス](icordebugbreakpoint-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="eae7e-151">[ICorDebugBreakpoint Interface](icordebugbreakpoint-interface.md)\\</span></span>
 <span data-ttu-id="eae7e-152">関数のブレークポイント、または値のウォッチ ポイントを表します。</span><span class="sxs-lookup"><span data-stu-id="eae7e-152">Represents a breakpoint in a function or a watch point on a value.</span></span>  
  
 <span data-ttu-id="eae7e-153">[ICorDebugBreakpointEnum インターフェイス](icordebugbreakpointenum-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="eae7e-153">[ICorDebugBreakpointEnum Interface](icordebugbreakpointenum-interface.md)\\</span></span>
 <span data-ttu-id="eae7e-154">`ICorDebugEnum` メソッドを実装し、`ICorDebugBreakpoint` 配列を列挙します。</span><span class="sxs-lookup"><span data-stu-id="eae7e-154">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugBreakpoint` arrays.</span></span>  
  
 <span data-ttu-id="eae7e-155">[ICorDebugChain インターフェイス](icordebugchain-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="eae7e-155">[ICorDebugChain Interface](icordebugchain-interface.md)\\</span></span>
 <span data-ttu-id="eae7e-156">物理呼び出し履歴または論理呼び出し履歴のセグメントを表します。</span><span class="sxs-lookup"><span data-stu-id="eae7e-156">Represents a segment of a physical or logical call stack.</span></span>  
  
 <span data-ttu-id="eae7e-157">[ICorDebugChainEnum インターフェイス](icordebugchainenum-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="eae7e-157">[ICorDebugChainEnum Interface](icordebugchainenum-interface.md)\\</span></span>
 <span data-ttu-id="eae7e-158">`ICorDebugEnum` メソッドを実装し、`ICorDebugChain` 配列を列挙します。</span><span class="sxs-lookup"><span data-stu-id="eae7e-158">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugChain` arrays.</span></span>  
  
 <span data-ttu-id="eae7e-159">[ICorDebugClass インターフェイス](icordebugclass-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="eae7e-159">[ICorDebugClass Interface](icordebugclass-interface.md)\\</span></span>
 <span data-ttu-id="eae7e-160">基本型または複合型 (つまり、ユーザー定義) のいずれかの型を表します。</span><span class="sxs-lookup"><span data-stu-id="eae7e-160">Represents a type, which can be either basic or complex (that is, user-defined).</span></span> <span data-ttu-id="eae7e-161">型がジェネリックの場合、`ICorDebugClass` はインスタンス化されないジェネリック型を表します。</span><span class="sxs-lookup"><span data-stu-id="eae7e-161">If the type is generic, `ICorDebugClass` represents the uninstantiated generic type.</span></span>  
  
 <span data-ttu-id="eae7e-162">[ICorDebugClass2 インターフェイス](icordebugclass2-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="eae7e-162">[ICorDebugClass2 Interface](icordebugclass2-interface.md)\\</span></span>
 <span data-ttu-id="eae7e-163">ジェネリック、または <xref:System.Type> 型のメソッド パラメーターを持つクラスを表します。</span><span class="sxs-lookup"><span data-stu-id="eae7e-163">Represents a generic class or a class with a method parameter of type <xref:System.Type>.</span></span> <span data-ttu-id="eae7e-164">このインターフェイスは、`ICorDebugClass` の機能を拡張します。</span><span class="sxs-lookup"><span data-stu-id="eae7e-164">This interface extends `ICorDebugClass`.</span></span>  
  
 <span data-ttu-id="eae7e-165">[ICorDebugCode インターフェイス](icordebugcode-interface1.md)\\</span><span class="sxs-lookup"><span data-stu-id="eae7e-165">[ICorDebugCode Interface](icordebugcode-interface1.md)\\</span></span>
 <span data-ttu-id="eae7e-166">Microsoft Intermediate Language (MSIL) コードまたはネイティブ コードのセグメントを表します。</span><span class="sxs-lookup"><span data-stu-id="eae7e-166">Represents a segment of either Microsoft intermediate language (MSIL) code or native code.</span></span>  
  
 <span data-ttu-id="eae7e-167">[ICorDebugCode2 インターフェイス](icordebugcode2-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="eae7e-167">[ICorDebugCode2 Interface](icordebugcode2-interface.md)\\</span></span>
 <span data-ttu-id="eae7e-168">`ICorDebugCode` の機能を拡張するメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="eae7e-168">Provides methods that extend the capabilities of `ICorDebugCode`.</span></span>  
  
 <span data-ttu-id="eae7e-169">[ICorDebugCode3 インターフェイス](icordebugcode3-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="eae7e-169">[ICorDebugCode3 Interface](icordebugcode3-interface.md)\\</span></span>
 <span data-ttu-id="eae7e-170">拡張メソッドを提供[ICorDebugCode](icordebugcode-interface1.md)と[ICorDebugCode2](icordebugcode2-interface.md)マネージ戻り値に関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="eae7e-170">Provides a method that extends [ICorDebugCode](icordebugcode-interface1.md) and [ICorDebugCode2](icordebugcode2-interface.md) to provide information about a managed return value.</span></span>  
  
 <span data-ttu-id="eae7e-171">[ICorDebugCode4 インターフェイス](icordebugcode4-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="eae7e-171">[ICorDebugCode4 Interface](icordebugcode4-interface.md)\\</span></span>
 <span data-ttu-id="eae7e-172">ローカル変数と関数の引数を列挙するためにデバッガーをできるようにするメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="eae7e-172">Provides a method that enables a debugger to enumerate the local variables and arguments in a function.</span></span>  
  
 <span data-ttu-id="eae7e-173">[ICorDebugCodeEnum インターフェイス](icordebugcodeenum-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="eae7e-173">[ICorDebugCodeEnum Interface](icordebugcodeenum-interface.md)\\</span></span>
 <span data-ttu-id="eae7e-174">`ICorDebugEnum` メソッドを実装し、`ICorDebugCode` 配列を列挙します。</span><span class="sxs-lookup"><span data-stu-id="eae7e-174">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugCode` arrays.</span></span>  
  
 <span data-ttu-id="eae7e-175">[ICorDebugComObjectValue のインターフェイス](icordebugcomobjectvalue-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="eae7e-175">[ICorDebugComObjectValue Interface](icordebugcomobjectvalue-interface.md)\\</span></span>
 <span data-ttu-id="eae7e-176">キャッシュされたインターフェイス オブジェクトを取得するメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="eae7e-176">Provides methods to retrieve cached interface objects.</span></span>  
  
 <span data-ttu-id="eae7e-177">[ICorDebugContext インターフェイス](icordebugcontext-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="eae7e-177">[ICorDebugContext Interface](icordebugcontext-interface.md)\\</span></span>
 <span data-ttu-id="eae7e-178">コンテキストのオブジェクトを表します。</span><span class="sxs-lookup"><span data-stu-id="eae7e-178">Represents a context object.</span></span> <span data-ttu-id="eae7e-179">このインターフェイスはまだ実装されていません。</span><span class="sxs-lookup"><span data-stu-id="eae7e-179">This interface has not been implemented yet.</span></span>  
  
 <span data-ttu-id="eae7e-180">[ICorDebugController インターフェイス](icordebugcontroller-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="eae7e-180">[ICorDebugController Interface](icordebugcontroller-interface.md)\\</span></span>
 <span data-ttu-id="eae7e-181">コードの実行コンテキストを制御できる <xref:System.Diagnostics.Process> または <xref:System.AppDomain> のスコープを表します。</span><span class="sxs-lookup"><span data-stu-id="eae7e-181">Represents a scope, either a <xref:System.Diagnostics.Process> or an <xref:System.AppDomain>, in which code execution context can be controlled.</span></span>  
  
 <span data-ttu-id="eae7e-182">[ICorDebugDataTarget インターフェイス](icordebugdatatarget-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="eae7e-182">[ICorDebugDataTarget Interface](icordebugdatatarget-interface.md)\\</span></span>
 <span data-ttu-id="eae7e-183">特定のターゲット プロセスにアクセスするためのコールバック インターフェイスが用意されています。</span><span class="sxs-lookup"><span data-stu-id="eae7e-183">Provides a callback interface that provides access to a particular target process.</span></span>  
  
 <span data-ttu-id="eae7e-184">[ICorDebugDataTarget2 インターフェイス](icordebugdatatarget2-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="eae7e-184">[ICorDebugDataTarget2 Interface](icordebugdatatarget2-interface.md)\\</span></span>
 <span data-ttu-id="eae7e-185">論理的に拡張し、 [ICorDebugDataTarget](icordebugdatatarget-interface.md)インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="eae7e-185">Logically extends the [ICorDebugDataTarget](icordebugdatatarget-interface.md) interface.</span></span> <span data-ttu-id="eae7e-186">**.NET ネイティブのみで使用できます。**</span><span class="sxs-lookup"><span data-stu-id="eae7e-186">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="eae7e-187">[ICorDebugDataTarget3 インターフェイス](icordebugdatatarget3-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="eae7e-187">[ICorDebugDataTarget3 Interface](icordebugdatatarget3-interface.md)\\</span></span>
 <span data-ttu-id="eae7e-188">論理的に拡張し、 [ICorDebugDataTarget](icordebugdatatarget-interface.md)インターフェイスが読み込まれたモジュールに関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="eae7e-188">Logically extends the [ICorDebugDataTarget](icordebugdatatarget-interface.md) interface to provide information about loaded modules.</span></span> <span data-ttu-id="eae7e-189">**.NET ネイティブのみで使用できます。**</span><span class="sxs-lookup"><span data-stu-id="eae7e-189">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="eae7e-190">[ICorDebugDebugEvent インターフェイス](icordebugdebugevent-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="eae7e-190">[ICorDebugDebugEvent Interface](icordebugdebugevent-interface.md)\\</span></span>
 <span data-ttu-id="eae7e-191">すべての `ICorDebug` デバッグ イベントを派生させる基本インターフェイスを定義します。</span><span class="sxs-lookup"><span data-stu-id="eae7e-191">Defines the base interface from which all `ICorDebug` debug events derive.</span></span> <span data-ttu-id="eae7e-192">**.NET ネイティブのみで使用できます。**</span><span class="sxs-lookup"><span data-stu-id="eae7e-192">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="eae7e-193">[ICorDebugEditAndContinueErrorInfo インターフェイス](icordebugeditandcontinueerrorinfo-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="eae7e-193">[ICorDebugEditAndContinueErrorInfo Interface](icordebugeditandcontinueerrorinfo-interface.md)\\</span></span>
 <span data-ttu-id="eae7e-194">互換性のために残されています。</span><span class="sxs-lookup"><span data-stu-id="eae7e-194">Obsolete.</span></span> <span data-ttu-id="eae7e-195">このインターフェイスは使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="eae7e-195">Do not use this interface.</span></span>  
  
 <span data-ttu-id="eae7e-196">[ICorDebugEditAndContinueSnapshot インターフェイス](icordebugeditandcontinuesnapshot-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="eae7e-196">[ICorDebugEditAndContinueSnapshot Interface](icordebugeditandcontinuesnapshot-interface.md)\\</span></span>
 <span data-ttu-id="eae7e-197">互換性のために残されています。</span><span class="sxs-lookup"><span data-stu-id="eae7e-197">Obsolete.</span></span> <span data-ttu-id="eae7e-198">このインターフェイスは使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="eae7e-198">Do not use this interface.</span></span>  
  
 <span data-ttu-id="eae7e-199">[ICorDebugEnum インターフェイス](icordebugenum-interface1.md)\\</span><span class="sxs-lookup"><span data-stu-id="eae7e-199">[ICorDebugEnum Interface](icordebugenum-interface1.md)\\</span></span>
 <span data-ttu-id="eae7e-200">デバッグ中の列挙子の抽象基底インターフェイスとして機能します。</span><span class="sxs-lookup"><span data-stu-id="eae7e-200">Serves as the abstract base interface for debugging enumerators.</span></span>  
  
 <span data-ttu-id="eae7e-201">[ICorDebugErrorInfoEnum インターフェイス](icordebugerrorinfoenum-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="eae7e-201">[ICorDebugErrorInfoEnum Interface](icordebugerrorinfoenum-interface.md)\\</span></span>
 <span data-ttu-id="eae7e-202">互換性のために残されています。</span><span class="sxs-lookup"><span data-stu-id="eae7e-202">Obsolete.</span></span> <span data-ttu-id="eae7e-203">このインターフェイスは使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="eae7e-203">Do not use this interface.</span></span>  
  
 <span data-ttu-id="eae7e-204">[ICorDebugEval インターフェイス](icordebugeval-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="eae7e-204">[ICorDebugEval Interface](icordebugeval-interface.md)\\</span></span>
 <span data-ttu-id="eae7e-205">デバッガーが、デバッグ中のコードのコンテキスト内でコードを実行できるメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="eae7e-205">Provides methods to enable the debugger to execute code within the context of the code being debugged.</span></span>  
  
 <span data-ttu-id="eae7e-206">[ICorDebugEval2 インターフェイス](icordebugeval2-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="eae7e-206">[ICorDebugEval2 Interface](icordebugeval2-interface.md)\\</span></span>
 <span data-ttu-id="eae7e-207">ジェネリック型をサポートできるように `ICorDebugEval` を拡張します。</span><span class="sxs-lookup"><span data-stu-id="eae7e-207">Extends `ICorDebugEval` to provide support for generic types.</span></span>  
  
 <span data-ttu-id="eae7e-208">[ICorDebugExceptionDebugEvent インターフェイス](icordebugexceptiondebugevent-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="eae7e-208">[ICorDebugExceptionDebugEvent Interface](icordebugexceptiondebugevent-interface.md)\\</span></span>
 <span data-ttu-id="eae7e-209">拡張、 [ICorDebugDebugEvent](icordebugdebugevent-interface.md)例外イベントをサポートするインターフェイス。</span><span class="sxs-lookup"><span data-stu-id="eae7e-209">Extends the [ICorDebugDebugEvent](icordebugdebugevent-interface.md) interface to support exception events.</span></span> <span data-ttu-id="eae7e-210">**.NET ネイティブのみで使用できます。**</span><span class="sxs-lookup"><span data-stu-id="eae7e-210">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="eae7e-211">[ICorDebugExceptionObjectCallStackEnum インターフェイス](icordebugexceptionobjectcallstackenum-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="eae7e-211">[ICorDebugExceptionObjectCallStackEnum Interface](icordebugexceptionobjectcallstackenum-interface.md)\\</span></span>
 <span data-ttu-id="eae7e-212">例外オブジェクトに埋め込まれているコール スタックの情報の列挙子を提供します。</span><span class="sxs-lookup"><span data-stu-id="eae7e-212">Provides an enumerator for call stack information that is embedded in an exception object.</span></span>  
  
 <span data-ttu-id="eae7e-213">[ICorDebugExceptionObjectValue インターフェイス](icordebugexceptionobjectvalue-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="eae7e-213">[ICorDebugExceptionObjectValue Interface](icordebugexceptionobjectvalue-interface.md)\\</span></span>
 <span data-ttu-id="eae7e-214">拡張、 [ICorDebugObjectValue](icordebugobjectvalue-interface.md)マネージ例外オブジェクトからスタック トレース情報を提供するインターフェイス。</span><span class="sxs-lookup"><span data-stu-id="eae7e-214">Extends the [ICorDebugObjectValue](icordebugobjectvalue-interface.md) interface to provide stack trace information from a managed exception object.</span></span>  
  
 <span data-ttu-id="eae7e-215">[ICorDebugFrame インターフェイス](icordebugframe-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="eae7e-215">[ICorDebugFrame Interface](icordebugframe-interface.md)\\</span></span>
 <span data-ttu-id="eae7e-216">現在のスタックのフレームを表します。</span><span class="sxs-lookup"><span data-stu-id="eae7e-216">Represents a frame on the current stack.</span></span>  
  
 <span data-ttu-id="eae7e-217">[ICorDebugFrameEnum インターフェイス](icordebugframeenum-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="eae7e-217">[ICorDebugFrameEnum Interface](icordebugframeenum-interface.md)\\</span></span>
 <span data-ttu-id="eae7e-218">`ICorDebugEnum` メソッドを実装し、`ICorDebugFrame` 配列を列挙します。</span><span class="sxs-lookup"><span data-stu-id="eae7e-218">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugFrame` arrays.</span></span>  
  
 <span data-ttu-id="eae7e-219">[ICorDebugFunction インターフェイス](icordebugfunction-interface1.md)\\</span><span class="sxs-lookup"><span data-stu-id="eae7e-219">[ICorDebugFunction Interface](icordebugfunction-interface1.md)\\</span></span>
 <span data-ttu-id="eae7e-220">マネージド関数またはマネージド メソッドを表します。</span><span class="sxs-lookup"><span data-stu-id="eae7e-220">Represents a managed function or method.</span></span>  
  
 <span data-ttu-id="eae7e-221">[ICorDebugFunction2 インターフェイス](icordebugfunction2-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="eae7e-221">[ICorDebugFunction2 Interface](icordebugfunction2-interface.md)\\</span></span>
 <span data-ttu-id="eae7e-222">`ICorDebugFunction` を論理的に拡張して、"マイ コードのみ" ステップ実行によるデバッグをサポートします。</span><span class="sxs-lookup"><span data-stu-id="eae7e-222">Logically extends `ICorDebugFunction` to provide support for Just My Code step-through debugging.</span></span>  
  
 <span data-ttu-id="eae7e-223">[ICorDebugFunction3 インターフェイス](icordebugfunction3-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="eae7e-223">[ICorDebugFunction3 Interface](icordebugfunction3-interface.md)\\</span></span>
 <span data-ttu-id="eae7e-224">論理的に拡張し、 [ICorDebugFunction](icordebugfunction-interface1.md) ReJIT 要求からコードへのアクセスを提供するインターフェイス。</span><span class="sxs-lookup"><span data-stu-id="eae7e-224">Logically extends the [ICorDebugFunction](icordebugfunction-interface1.md) interface to provide access to code from a ReJIT request.</span></span>  
  
 <span data-ttu-id="eae7e-225">[ICorDebugFunctionBreakpoint インターフェイス](icordebugfunctionbreakpoint-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="eae7e-225">[ICorDebugFunctionBreakpoint Interface](icordebugfunctionbreakpoint-interface.md)\\</span></span>
 <span data-ttu-id="eae7e-226">関数内のブレークポイントをサポートするように `ICorDebugBreakpoint` を拡張します。</span><span class="sxs-lookup"><span data-stu-id="eae7e-226">Extends `ICorDebugBreakpoint` to support breakpoints within functions.</span></span>  
  
 <span data-ttu-id="eae7e-227">[ICorDebugGCReferenceEnum インターフェイス](icordebuggcreferenceenum-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="eae7e-227">[ICorDebugGCReferenceEnum Interface](icordebuggcreferenceenum-interface.md)\\</span></span>
 <span data-ttu-id="eae7e-228">ガベージ コレクトされるオブジェクトの列挙子を提供します。</span><span class="sxs-lookup"><span data-stu-id="eae7e-228">Provides an enumerator for objects that will be garbage-collected.</span></span>  
  
 <span data-ttu-id="eae7e-229">[ICorDebugGenericValue インターフェイス](icordebuggenericvalue-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="eae7e-229">[ICorDebugGenericValue Interface](icordebuggenericvalue-interface.md)\\</span></span>
 <span data-ttu-id="eae7e-230">すべての値に適用する `ICorDebugValue` のサブクラスです。</span><span class="sxs-lookup"><span data-stu-id="eae7e-230">A subclass of `ICorDebugValue` that applies to all values.</span></span> <span data-ttu-id="eae7e-231">このインターフェイスは、値に対して Get メソッドと Set メソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="eae7e-231">This interface provides Get and Set methods for the value.</span></span>  
  
 <span data-ttu-id="eae7e-232">[ICorDebugGuidToTypeEnum インターフェイス](icordebugguidtotypeenum-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="eae7e-232">[ICorDebugGuidToTypeEnum Interface](icordebugguidtotypeenum-interface.md)\\</span></span>
 <span data-ttu-id="eae7e-233">GUID およびその対応する `ICorDebugType` オブジェクトをマップするオブジェクトの列挙子を提供します。</span><span class="sxs-lookup"><span data-stu-id="eae7e-233">Provides an enumerator for an object that maps GUIDs and their corresponding `ICorDebugType` objects.</span></span>  
  
 <span data-ttu-id="eae7e-234">[ICorDebugHandleValue インターフェイス](icordebughandlevalue-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="eae7e-234">[ICorDebugHandleValue Interface](icordebughandlevalue-interface.md)\\</span></span>
 <span data-ttu-id="eae7e-235">デバッガーが作成したガベージ コレクションのハンドルへの参照値を表す `ICorDebugReferenceValue` のサブクラスです。</span><span class="sxs-lookup"><span data-stu-id="eae7e-235">A subclass of `ICorDebugReferenceValue` that represents a reference value to which the debugger has created a handle for garbage collection.</span></span>  
  
 <span data-ttu-id="eae7e-236">[ICorDebugHeapEnum インターフェイス](icordebugheapenum-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="eae7e-236">[ICorDebugHeapEnum Interface](icordebugheapenum-interface.md)\\</span></span>
 <span data-ttu-id="eae7e-237">マネージド ヒープのオブジェクトの列挙子を提供します。</span><span class="sxs-lookup"><span data-stu-id="eae7e-237">Provides an enumerator for objects on the managed heap.</span></span>  
  
 <span data-ttu-id="eae7e-238">[ICorDebugHeapSegmentEnum インターフェイス](icordebugheapsegmentenum-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="eae7e-238">[ICorDebugHeapSegmentEnum Interface](icordebugheapsegmentenum-interface.md)\\</span></span>
 <span data-ttu-id="eae7e-239">マネージド ヒープのメモリ領域の列挙子を提供します。</span><span class="sxs-lookup"><span data-stu-id="eae7e-239">Provides an enumerator for the memory regions of the managed heap.</span></span>  
  
 <span data-ttu-id="eae7e-240">[ICorDebugHeapValue インターフェイス](icordebugheapvalue-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="eae7e-240">[ICorDebugHeapValue Interface](icordebugheapvalue-interface.md)\\</span></span>
 <span data-ttu-id="eae7e-241">CLR ガベージ コレクターによって収集されたオブジェクトを表す `ICorDebugValue` のサブクラスです。</span><span class="sxs-lookup"><span data-stu-id="eae7e-241">A subclass of `ICorDebugValue` that represents an object that has been collected by the CLR garbage collector.</span></span>  
  
 <span data-ttu-id="eae7e-242">[ICorDebugHeapValue2 インターフェイス](icordebugheapvalue2-interface1.md)\\</span><span class="sxs-lookup"><span data-stu-id="eae7e-242">[ICorDebugHeapValue2 Interface](icordebugheapvalue2-interface1.md)\\</span></span>
 <span data-ttu-id="eae7e-243">ランタイム ハンドルのサポートを提供する `ICorDebugHeapValue` の拡張機能です。</span><span class="sxs-lookup"><span data-stu-id="eae7e-243">An extension of `ICorDebugHeapValue` that provides support for runtime handles.</span></span>  
  
 <span data-ttu-id="eae7e-244">[ICorDebugHeapValue3 インターフェイス](icordebugheapvalue3-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="eae7e-244">[ICorDebugHeapValue3 Interface](icordebugheapvalue3-interface.md)\\</span></span>
 <span data-ttu-id="eae7e-245">オブジェクトのモニター ロック プロパティを公開します。</span><span class="sxs-lookup"><span data-stu-id="eae7e-245">Exposes the monitor lock properties of objects.</span></span>  
  
 <span data-ttu-id="eae7e-246">[ICorDebugILCode インターフェイス](icordebugilcode-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="eae7e-246">[ICorDebugILCode Interface](icordebugilcode-interface.md)\\</span></span>
 <span data-ttu-id="eae7e-247">中間言語 (IL) コードのセグメントを表します。</span><span class="sxs-lookup"><span data-stu-id="eae7e-247">Represents a segment of intermediate language (IL) code.</span></span>  
  
 <span data-ttu-id="eae7e-248">[ICorDebugILCode2 インターフェイス](icordebugilcode2-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="eae7e-248">[ICorDebugILCode2 Interface](icordebugilcode2-interface.md)\\</span></span>
 <span data-ttu-id="eae7e-249">論理的に拡張し、 [ICorDebugILCode](icordebugilcode-interface.md)に元のメソッド IL オフセットを関数のローカル変数シグネチャのトークンを返すし、プロファイラーのインストルメント化された中間言語 (IL) をマップする方法を提供するインターフェイスオフセットします。</span><span class="sxs-lookup"><span data-stu-id="eae7e-249">Logically extends the [ICorDebugILCode](icordebugilcode-interface.md) interface to provide methods that return the token for a function's local variable signature, and that map a profiler's instrumented intermediate language (IL) offsets to original method IL offsets.</span></span>  
  
 <span data-ttu-id="eae7e-250">[ICorDebugILFrame インターフェイス](icordebugilframe-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="eae7e-250">[ICorDebugILFrame Interface](icordebugilframe-interface.md)\\</span></span>
 <span data-ttu-id="eae7e-251">MSIL コードのスタック フレームを表します。</span><span class="sxs-lookup"><span data-stu-id="eae7e-251">Represents a stack frame of MSIL code.</span></span>  
  
 <span data-ttu-id="eae7e-252">[ICorDebugILFrame2 インターフェイス](icordebugilframe2-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="eae7e-252">[ICorDebugILFrame2 Interface](icordebugilframe2-interface.md)\\</span></span>
 <span data-ttu-id="eae7e-253">`ICorDebugILFrame` の論理拡張機能です。</span><span class="sxs-lookup"><span data-stu-id="eae7e-253">A logical extension of `ICorDebugILFrame`.</span></span>  
  
 <span data-ttu-id="eae7e-254">[ICorDebugILFrame3 インターフェイス](icordebugilframe3-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="eae7e-254">[ICorDebugILFrame3 Interface](icordebugilframe3-interface.md)\\</span></span>
 <span data-ttu-id="eae7e-255">関数の戻り値をカプセル化するメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="eae7e-255">Provides a method that encapsulates the return value of a function.</span></span>  
  
 <span data-ttu-id="eae7e-256">[ICorDebugILFrame4 インターフェイス](icordebugilframe4-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="eae7e-256">[ICorDebugILFrame4 Interface](icordebugilframe4-interface.md)\\</span></span>
 <span data-ttu-id="eae7e-257">ローカル変数にアクセスできるようにするメソッドおよび中間言語 (IL) コードのスタック フレームのコードを提供します。</span><span class="sxs-lookup"><span data-stu-id="eae7e-257">Provides methods that allow you to access the local variables and code in a stack frame of intermediate language (IL) code.</span></span> <span data-ttu-id="eae7e-258">パラメーターは、プロファイラーの ReJIT インストルメンテーションに追加される変数およびコードへデバッガーがアクセスできるかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="eae7e-258">A parameter specifies whether the debugger has access to variables and code added in profiler ReJIT instrumentation.</span></span>  
  
 <span data-ttu-id="eae7e-259">[ICorDebugInstanceFieldSymbol インターフェイス](icordebuginstancefieldsymbol-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="eae7e-259">[ICorDebugInstanceFieldSymbol Interface](icordebuginstancefieldsymbol-interface.md)\\</span></span>
 <span data-ttu-id="eae7e-260">インスタンス フィールドのデバッグ シンボル情報を表します。</span><span class="sxs-lookup"><span data-stu-id="eae7e-260">Represents the debug symbol information for an instance field.</span></span> <span data-ttu-id="eae7e-261">**.NET ネイティブのみで使用できます。**</span><span class="sxs-lookup"><span data-stu-id="eae7e-261">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="eae7e-262">[ICorDebugInternalFrame インターフェイス](icordebuginternalframe-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="eae7e-262">[ICorDebugInternalFrame Interface](icordebuginternalframe-interface.md)\\</span></span>
 <span data-ttu-id="eae7e-263">デバッガーのフレーム種類を識別します。</span><span class="sxs-lookup"><span data-stu-id="eae7e-263">Identifies frame types for the debugger.</span></span>  
  
 <span data-ttu-id="eae7e-264">[ICorDebugInternalFrame2 インターフェイス](icordebuginternalframe2-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="eae7e-264">[ICorDebugInternalFrame2 Interface](icordebuginternalframe2-interface.md)\\</span></span>
 <span data-ttu-id="eae7e-265">スタックのアドレスや位置などの内部フレームに関する情報を提供します[ICorDebugFrame](icordebugframe-interface.md)オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="eae7e-265">Provides information about internal frames, including stack address and position in relation to [ICorDebugFrame](icordebugframe-interface.md) objects.</span></span>  
  
 <span data-ttu-id="eae7e-266">[ICorDebugLoadedModule インターフェイス](icordebugloadedmodule-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="eae7e-266">[ICorDebugLoadedModule Interface](icordebugloadedmodule-interface.md)\\</span></span>
 <span data-ttu-id="eae7e-267">読み込まれたモジュールについての情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="eae7e-267">Provides information about a loaded module.</span></span> <span data-ttu-id="eae7e-268">**.NET ネイティブのみで使用できます。**</span><span class="sxs-lookup"><span data-stu-id="eae7e-268">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="eae7e-269">[ICorDebugManagedCallback インターフェイス](icordebugmanagedcallback-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="eae7e-269">[ICorDebugManagedCallback Interface](icordebugmanagedcallback-interface.md)\\</span></span>
 <span data-ttu-id="eae7e-270">デバッガーのコールバックを処理するメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="eae7e-270">Provides methods to process debugger callbacks.</span></span>  
  
 <span data-ttu-id="eae7e-271">[ICorDebugManagedCallback2 インターフェイス](icordebugmanagedcallback2-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="eae7e-271">[ICorDebugManagedCallback2 Interface](icordebugmanagedcallback2-interface.md)\\</span></span>
 <span data-ttu-id="eae7e-272">デバッガーの例外処理およびマネージド デバッグ アシスタント (MDA: Managed Debugging Assistants) をサポートするメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="eae7e-272">Provides methods to support debugger exception handling and managed debugging assistants (MDAs).</span></span> <span data-ttu-id="eae7e-273">`ICorDebugManagedCallback2` は、`ICorDebugManagedCallback` の論理拡張機能です。</span><span class="sxs-lookup"><span data-stu-id="eae7e-273">`ICorDebugManagedCallback2` is a logical extension of `ICorDebugManagedCallback`.</span></span>  
  
 <span data-ttu-id="eae7e-274">[ICorDebugManagedCallback3 インターフェイス](icordebugmanagedcallback3-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="eae7e-274">[ICorDebugManagedCallback3 Interface](icordebugmanagedcallback3-interface.md)\\</span></span>
 <span data-ttu-id="eae7e-275">有効なカスタムのデバッガー通知が発生したことを示すコールバック メソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="eae7e-275">Provides a callback method that indicates that an enabled custom debugger notification has been raised.</span></span>  
  
 <span data-ttu-id="eae7e-276">[ICorDebugMDA インターフェイス](icordebugmda-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="eae7e-276">[ICorDebugMDA Interface](icordebugmda-interface.md)\\</span></span>
 <span data-ttu-id="eae7e-277">マネージド デバッグ アシスタント (MDA) メッセージを表します。</span><span class="sxs-lookup"><span data-stu-id="eae7e-277">Represents a managed debugging assistant (MDA) message.</span></span>  
  
 <span data-ttu-id="eae7e-278">[ICorDebugMemoryBuffer インターフェイス](icordebugmemorybuffer-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="eae7e-278">[ICorDebugMemoryBuffer Interface](icordebugmemorybuffer-interface.md)\\</span></span>
 <span data-ttu-id="eae7e-279">メモリ内のバッファーを表します。</span><span class="sxs-lookup"><span data-stu-id="eae7e-279">Represents an in-memory buffer.</span></span> <span data-ttu-id="eae7e-280">**.NET ネイティブのみで使用できます。**</span><span class="sxs-lookup"><span data-stu-id="eae7e-280">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="eae7e-281">[ICorDebugMergedAssemblyRecord インターフェイス](icordebugmergedassemblyrecord-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="eae7e-281">[ICorDebugMergedAssemblyRecord Interface](icordebugmergedassemblyrecord-interface.md)\\</span></span>
 <span data-ttu-id="eae7e-282">マージされたアセンブリに関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="eae7e-282">Provides information about a merged assembly.</span></span> <span data-ttu-id="eae7e-283">**.NET ネイティブのみで使用できます。**</span><span class="sxs-lookup"><span data-stu-id="eae7e-283">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="eae7e-284">[ICorDebugMetaDataLocator インターフェイス](icordebugmetadatalocator-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="eae7e-284">[ICorDebugMetaDataLocator Interface](icordebugmetadatalocator-interface.md)\\</span></span>
 <span data-ttu-id="eae7e-285">デバッガーにメタデータ情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="eae7e-285">Provides metadata information to the debugger.</span></span>  
  
 <span data-ttu-id="eae7e-286">[ICorDebugModule インターフェイス](icordebugmodule-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="eae7e-286">[ICorDebugModule Interface](icordebugmodule-interface.md)\\</span></span>
 <span data-ttu-id="eae7e-287">実行可能ファイルまたはダイナミック リンク ライブラリ (DLL: Dynamic-Link Library) のいずれかの CLR モジュールを表します。</span><span class="sxs-lookup"><span data-stu-id="eae7e-287">Represents a CLR module, which is either an executable or a dynamic-link library (DLL).</span></span>  
  
 <span data-ttu-id="eae7e-288">[ICorDebugModule2 インターフェイス](icordebugmodule2-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="eae7e-288">[ICorDebugModule2 Interface](icordebugmodule2-interface.md)\\</span></span>
 <span data-ttu-id="eae7e-289">`ICorDebugModule` の論理的な拡張機能として動作します。</span><span class="sxs-lookup"><span data-stu-id="eae7e-289">Serves as a logical extension to `ICorDebugModule`.</span></span>  
  
 <span data-ttu-id="eae7e-290">[ICorDebugModule3 インターフェイス](icordebugmodule3-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="eae7e-290">[ICorDebugModule3 Interface](icordebugmodule3-interface.md)\\</span></span>
 <span data-ttu-id="eae7e-291">動的モジュールのシンボル リーダーを作成します。</span><span class="sxs-lookup"><span data-stu-id="eae7e-291">Creates a symbol reader for a dynamic module.</span></span>  
  
 <span data-ttu-id="eae7e-292">[ICorDebugModuleBreakpoint インターフェイス](icordebugmodulebreakpoint-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="eae7e-292">[ICorDebugModuleBreakpoint Interface](icordebugmodulebreakpoint-interface.md)\\</span></span>
 <span data-ttu-id="eae7e-293">特定のモジュールにアクセスできるように `ICorDebugBreakpoint` を拡張します。</span><span class="sxs-lookup"><span data-stu-id="eae7e-293">Extends `ICorDebugBreakpoint` to provide access to specific modules.</span></span>  
  
 <span data-ttu-id="eae7e-294">[ICorDebugModuleDebugEvent インターフェイス](icordebugmoduledebugevent-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="eae7e-294">[ICorDebugModuleDebugEvent Interface](icordebugmoduledebugevent-interface.md)\\</span></span>
 <span data-ttu-id="eae7e-295">拡張、 [ICorDebugDebugEvent](icordebugdebugevent-interface.md)モジュール レベルのイベントをサポートするインターフェイス。</span><span class="sxs-lookup"><span data-stu-id="eae7e-295">Extends the [ICorDebugDebugEvent](icordebugdebugevent-interface.md) interface to support module-level events.</span></span> <span data-ttu-id="eae7e-296">**.NET ネイティブのみで使用できます。**</span><span class="sxs-lookup"><span data-stu-id="eae7e-296">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="eae7e-297">[ICorDebugModuleEnum インターフェイス](icordebugmoduleenum-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="eae7e-297">[ICorDebugModuleEnum Interface](icordebugmoduleenum-interface.md)\\</span></span>
 <span data-ttu-id="eae7e-298">`ICorDebugEnum` メソッドを実装し、`ICorDebugModule` 配列を列挙します。</span><span class="sxs-lookup"><span data-stu-id="eae7e-298">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugModule` arrays.</span></span>  
  
 <span data-ttu-id="eae7e-299">[ICorDebugMutableDataTarget インターフェイス](icordebugmutabledatatarget-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="eae7e-299">[ICorDebugMutableDataTarget Interface](icordebugmutabledatatarget-interface.md)\\</span></span>
 <span data-ttu-id="eae7e-300">拡張、 [ICorDebugDataTarget](icordebugdatatarget-interface.md)変更可能なデータのターゲットをサポートするインターフェイス。</span><span class="sxs-lookup"><span data-stu-id="eae7e-300">Extends the [ICorDebugDataTarget](icordebugdatatarget-interface.md) interface to support mutable data targets.</span></span>  
  
 <span data-ttu-id="eae7e-301">[ICorDebugNativeFrame インターフェイス](icordebugnativeframe-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="eae7e-301">[ICorDebugNativeFrame Interface](icordebugnativeframe-interface.md)\\</span></span>
 <span data-ttu-id="eae7e-302">ネイティブ フレームで使用される `ICorDebugFrame` の特化された実装。</span><span class="sxs-lookup"><span data-stu-id="eae7e-302">A specialized implementation of `ICorDebugFrame` used for native frames.</span></span>  
  
 <span data-ttu-id="eae7e-303">[ICorDebugNativeFrame2 インターフェイス](icordebugnativeframe2-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="eae7e-303">[ICorDebugNativeFrame2 Interface](icordebugnativeframe2-interface.md)\\</span></span>
 <span data-ttu-id="eae7e-304">子と親のフレームの関係をテストするメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="eae7e-304">Provides methods that test for child and parent frame relationships.</span></span>  
  
 <span data-ttu-id="eae7e-305">[ICorDebugObjectEnum インターフェイス](icordebugobjectenum-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="eae7e-305">[ICorDebugObjectEnum Interface](icordebugobjectenum-interface.md)\\</span></span>
 <span data-ttu-id="eae7e-306">`ICorDebugEnum` メソッドを実装し、オブジェクトの配列を相対仮想アドレス (RVA: Relative Virtual Address) で列挙します。</span><span class="sxs-lookup"><span data-stu-id="eae7e-306">Implements `ICorDebugEnum` methods, and enumerates arrays of objects by their relative virtual addresses (RVAs).</span></span>  
  
 <span data-ttu-id="eae7e-307">[ICorDebugObjectValue インターフェイス](icordebugobjectvalue-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="eae7e-307">[ICorDebugObjectValue Interface](icordebugobjectvalue-interface.md)\\</span></span>
 <span data-ttu-id="eae7e-308">オブジェクトが含まれた値を表す `ICorDebugValue` のサブクラスです。</span><span class="sxs-lookup"><span data-stu-id="eae7e-308">A subclass of `ICorDebugValue` that represents a value that contains an object.</span></span>  
  
 <span data-ttu-id="eae7e-309">[ICorDebugObjectValue2 インターフェイス](icordebugobjectvalue2-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="eae7e-309">[ICorDebugObjectValue2 Interface](icordebugobjectvalue2-interface.md)\\</span></span>
 <span data-ttu-id="eae7e-310">継承およびオーバーライドをサポートするように `ICorDebugObjectValue` を拡張します。</span><span class="sxs-lookup"><span data-stu-id="eae7e-310">Extends `ICorDebugObjectValue` to support inheritance and overrides.</span></span>  
  
 <span data-ttu-id="eae7e-311">[ICorDebugProcess インターフェイス](icordebugprocess-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="eae7e-311">[ICorDebugProcess Interface](icordebugprocess-interface.md)\\</span></span>
 <span data-ttu-id="eae7e-312">マネージド コードを実行しているプロセスを表します。</span><span class="sxs-lookup"><span data-stu-id="eae7e-312">Represents a process that is executing managed code.</span></span>  
  
 <span data-ttu-id="eae7e-313">[ICorDebugProcess2 インターフェイス](icordebugprocess2-interface1.md)\\</span><span class="sxs-lookup"><span data-stu-id="eae7e-313">[ICorDebugProcess2 Interface](icordebugprocess2-interface1.md)\\</span></span>
 <span data-ttu-id="eae7e-314">`ICorDebugProcess` の論理拡張機能です。</span><span class="sxs-lookup"><span data-stu-id="eae7e-314">A logical extension of `ICorDebugProcess`.</span></span>  
  
 <span data-ttu-id="eae7e-315">[ICorDebugProcess3 インターフェイス](icordebugprocess3-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="eae7e-315">[ICorDebugProcess3 Interface](icordebugprocess3-interface.md)\\</span></span>
 <span data-ttu-id="eae7e-316">カスタムのデバッガー通知を制御します。</span><span class="sxs-lookup"><span data-stu-id="eae7e-316">Controls custom debugger notifications.</span></span>

 <span data-ttu-id="eae7e-317">[ICorDebugProcess4 インターフェイス](icordebugprocess4-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="eae7e-317">[ICorDebugProcess4 Interface](icordebugprocess4-interface.md)\\</span></span>
 <span data-ttu-id="eae7e-318">プロセス実行の制御外のサポートを提供します。</span><span class="sxs-lookup"><span data-stu-id="eae7e-318">Provides support for out of process execution control.</span></span>
  
 <span data-ttu-id="eae7e-319">[ICorDebugProcess5 インターフェイス](icordebugprocess5-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="eae7e-319">[ICorDebugProcess5 Interface](icordebugprocess5-interface.md)\\</span></span>
 <span data-ttu-id="eae7e-320">拡張、 [ICorDebugProcess](icordebugprocess-interface.md)マネージ オブジェクトのガベージ コレクションに関する情報を提供し、デバッガーがアプリケーションからイメージを読み込むかどうかを判断する、マネージ ヒープへのアクセスをサポートするインターフェイスのローカルネイティブ イメージ キャッシュします。</span><span class="sxs-lookup"><span data-stu-id="eae7e-320">Extends the [ICorDebugProcess](icordebugprocess-interface.md) interface to support access to the managed heap, to provide information about garbage collection of managed objects, and to determine whether a debugger loads images from the application's local native image cache.</span></span>  
  
 <span data-ttu-id="eae7e-321">[ICorDebugProcess6 インターフェイス](icordebugprocess6-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="eae7e-321">[ICorDebugProcess6 Interface](icordebugprocess6-interface.md)\\</span></span>
 <span data-ttu-id="eae7e-322">論理的に拡張し、 [ICorDebugProcess](icordebugprocess-interface.md)ネイティブ例外デバッグ イベントや仮想モジュール分割でエンコードされたマネージ デバッグ イベントをデコードなどの機能を有効にするインターフェイス。</span><span class="sxs-lookup"><span data-stu-id="eae7e-322">Logically extends the [ICorDebugProcess](icordebugprocess-interface.md) interface to enable features such as decoding managed debug events that are encoded in native exception debug events and virtual module splitting.</span></span> <span data-ttu-id="eae7e-323">**.NET ネイティブのみで使用できます。**</span><span class="sxs-lookup"><span data-stu-id="eae7e-323">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="eae7e-324">[ICorDebugProcess7 インターフェイス](icordebugprocess7-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="eae7e-324">[ICorDebugProcess7 Interface](icordebugprocess7-interface.md)\\</span></span>
 <span data-ttu-id="eae7e-325">ターゲット プロセスでメモリ内のメタデータ更新を処理するようにデバッガーを構成するメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="eae7e-325">Provides a method that configures the debugger to handle in-memory metadata updates in the target process.</span></span>  
  
 <span data-ttu-id="eae7e-326">[ICorDebugProcess8 インターフェイス](icordebugprocess8-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="eae7e-326">[ICorDebugProcess8 Interface](icordebugprocess8-interface.md)\\</span></span>
 <span data-ttu-id="eae7e-327">論理的に拡張し、 [ICorDebugProcess](icordebugprocess-interface.md)を有効にするまたはの特定の種類を無効にするインターフェイス[ICorDebugManagedCallback2](icordebugmanagedcallback2-interface.md)例外コールバック。</span><span class="sxs-lookup"><span data-stu-id="eae7e-327">Logically extends the [ICorDebugProcess](icordebugprocess-interface.md) interface to enable or disable certain types of [ICorDebugManagedCallback2](icordebugmanagedcallback2-interface.md) exception callbacks.</span></span>  
  
 <span data-ttu-id="eae7e-328">[ICorDebugProcessEnum インターフェイス](icordebugprocessenum-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="eae7e-328">[ICorDebugProcessEnum Interface](icordebugprocessenum-interface.md)\\</span></span>
 <span data-ttu-id="eae7e-329">`ICorDebugEnum` メソッドを実装し、`ICorDebugProcess` 配列を列挙します。</span><span class="sxs-lookup"><span data-stu-id="eae7e-329">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugProcess` arrays.</span></span>  
  
 <span data-ttu-id="eae7e-330">[ICorDebugReferenceValue インターフェイス](icordebugreferencevalue-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="eae7e-330">[ICorDebugReferenceValue Interface](icordebugreferencevalue-interface.md)\\</span></span>
 <span data-ttu-id="eae7e-331">参照型をサポートする `ICorDebugValue` のサブクラス。</span><span class="sxs-lookup"><span data-stu-id="eae7e-331">A subclass of `ICorDebugValue` that supports reference types.</span></span>  
  
 <span data-ttu-id="eae7e-332">[ICorDebugRegisterSet インターフェイス](icordebugregisterset-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="eae7e-332">[ICorDebugRegisterSet Interface](icordebugregisterset-interface.md)\\</span></span>
 <span data-ttu-id="eae7e-333">現在コードを実行しているマシン上で使用できるレジスタ セットを表します。</span><span class="sxs-lookup"><span data-stu-id="eae7e-333">Represents the set of registers available on the machine that is currently executing code.</span></span>  
  
 <span data-ttu-id="eae7e-334">[ICorDebugRegisterSet2 インターフェイス](icordebugregisterset2-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="eae7e-334">[ICorDebugRegisterSet2 Interface](icordebugregisterset2-interface.md)\\</span></span>
 <span data-ttu-id="eae7e-335">64 を超えるレジスタを持つハードウェア プラットフォーム用に `ICorDebugRegisterSet` の機能を拡張します。</span><span class="sxs-lookup"><span data-stu-id="eae7e-335">Extends the capabilities of `ICorDebugRegisterSet` for hardware platforms that have more than 64 registers.</span></span>  
  
 <span data-ttu-id="eae7e-336">[ICorDebugRemote インターフェイス](icordebugremote-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="eae7e-336">[ICorDebugRemote Interface](icordebugremote-interface.md)\\</span></span>
 <span data-ttu-id="eae7e-337">リモート ターゲット プロセスに対してマネージド デバッガーを起動または接続する機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="eae7e-337">Provides the ability to launch or attach a managed debugger to a remote target process.</span></span>  
  
 <span data-ttu-id="eae7e-338">[ICorDebugRemoteTarget インターフェイス](icordebugremotetarget-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="eae7e-338">[ICorDebugRemoteTarget Interface](icordebugremotetarget-interface.md)\\</span></span>
 <span data-ttu-id="eae7e-339">開発者が CLR 環境で Silverlight ベース アプリケーションをデバッグできるようにするメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="eae7e-339">Provides methods that enable you to debug Silverlight-based applications in the CLR environment.</span></span>  
  
 <span data-ttu-id="eae7e-340">[ICorDebugRuntimeUnwindableFrame インターフェイス](icordebugruntimeunwindableframe-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="eae7e-340">[ICorDebugRuntimeUnwindableFrame Interface](icordebugruntimeunwindableframe-interface.md)\\</span></span>
 <span data-ttu-id="eae7e-341">共通言語ランタイム (CLR: Common Language Runtime) でフレームをアンワインドする必要のあるアンマネージ メソッドに対してサポートを提供します。</span><span class="sxs-lookup"><span data-stu-id="eae7e-341">Provides support for unmanaged methods that require the common language runtime (CLR) to unwind a frame.</span></span>  
  
 <span data-ttu-id="eae7e-342">[ICorDebugStackWalk インターフェイス](icordebugstackwalk-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="eae7e-342">[ICorDebugStackWalk Interface](icordebugstackwalk-interface.md)\\</span></span>
 <span data-ttu-id="eae7e-343">スレッドのスタック上のマネージド メソッド (フレーム) を取得するメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="eae7e-343">Provides methods for getting the managed methods, or frames, on a thread’s stack.</span></span>  
  
 <span data-ttu-id="eae7e-344">[ICorDebugStaticFieldSymbol インターフェイス](icordebugstaticfieldsymbol-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="eae7e-344">[ICorDebugStaticFieldSymbol Interface](icordebugstaticfieldsymbol-interface.md)\\</span></span>
 <span data-ttu-id="eae7e-345">静的フィールドのデバッグ シンボル情報を表します。</span><span class="sxs-lookup"><span data-stu-id="eae7e-345">Represents the debug symbol information for a static field.</span></span> <span data-ttu-id="eae7e-346">**.NET ネイティブのみで使用できます。**</span><span class="sxs-lookup"><span data-stu-id="eae7e-346">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="eae7e-347">[ICorDebugStepper インターフェイス](icordebugstepper-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="eae7e-347">[ICorDebugStepper Interface](icordebugstepper-interface.md)\\</span></span>
 <span data-ttu-id="eae7e-348">デバッガーが実行するコード実行内のステップを表します。コマンドの発行から完了までの間は識別子として機能します。これを使用するとステップをキャンセルできます。</span><span class="sxs-lookup"><span data-stu-id="eae7e-348">Represents a step in code execution that is performed by a debugger, serves as an identifier between the issuance and completion of a command, and provides a way to cancel a step.</span></span>  
  
 <span data-ttu-id="eae7e-349">[ICorDebugStepper2 インターフェイス](icordebugstepper2-interface1.md)\\</span><span class="sxs-lookup"><span data-stu-id="eae7e-349">[ICorDebugStepper2 Interface](icordebugstepper2-interface1.md)\\</span></span>
 <span data-ttu-id="eae7e-350">マイ コードのみ (JMC: Just My Code) デバッグのサポートを提供します。</span><span class="sxs-lookup"><span data-stu-id="eae7e-350">Provides support for Just My Code (JMC) debugging.</span></span>  
  
 <span data-ttu-id="eae7e-351">[ICorDebugStepperEnum インターフェイス](icordebugstepperenum-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="eae7e-351">[ICorDebugStepperEnum Interface](icordebugstepperenum-interface.md)\\</span></span>
 <span data-ttu-id="eae7e-352">`ICorDebugEnum` メソッドを実装し、`ICorDebugStepper` 配列を列挙します。</span><span class="sxs-lookup"><span data-stu-id="eae7e-352">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugStepper` arrays.</span></span>  
  
 <span data-ttu-id="eae7e-353">[ICorDebugStringValue インターフェイス](icordebugstringvalue-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="eae7e-353">[ICorDebugStringValue Interface](icordebugstringvalue-interface.md)\\</span></span>
 <span data-ttu-id="eae7e-354">文字列値に適用する `ICorDebugHeapValue` のサブクラスです。</span><span class="sxs-lookup"><span data-stu-id="eae7e-354">A subclass of `ICorDebugHeapValue` that applies to string values.</span></span>  
  
 <span data-ttu-id="eae7e-355">[ICorDebugSymbolProvider インターフェイス](icordebugsymbolprovider-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="eae7e-355">[ICorDebugSymbolProvider Interface](icordebugsymbolprovider-interface.md)\\</span></span>
 <span data-ttu-id="eae7e-356">デバッグ シンボル情報を取得するために使用できるメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="eae7e-356">Provides methods that can be used to retrieve debug symbol information.</span></span> <span data-ttu-id="eae7e-357">**.NET ネイティブのみで使用できます。**</span><span class="sxs-lookup"><span data-stu-id="eae7e-357">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="eae7e-358">[ICorDebugSymbolProvider2 インターフェイス](icordebugsymbolprovider2-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="eae7e-358">[ICorDebugSymbolProvider2 Interface](icordebugsymbolprovider2-interface.md)\\</span></span>
 <span data-ttu-id="eae7e-359">論理的に拡張し、 [ICorDebugSymbolProvider](icordebugsymbolprovider-interface.md)追加のデバッグ シンボル情報を取得するインターフェイス。</span><span class="sxs-lookup"><span data-stu-id="eae7e-359">Logically extends the [ICorDebugSymbolProvider](icordebugsymbolprovider-interface.md) interface to retrieve additional debug symbol information.</span></span> <span data-ttu-id="eae7e-360">**.NET ネイティブのみで使用できます。**</span><span class="sxs-lookup"><span data-stu-id="eae7e-360">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="eae7e-361">[ICorDebugThread インターフェイス](icordebugthread-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="eae7e-361">[ICorDebugThread Interface](icordebugthread-interface.md)\\</span></span>
 <span data-ttu-id="eae7e-362">プロセス内のスレッドを表します。</span><span class="sxs-lookup"><span data-stu-id="eae7e-362">Represents a thread in a process.</span></span> <span data-ttu-id="eae7e-363">`ICorDebugThread` インスタンスの有効期間は、それが表しているスレッドの有効期間と同じです。</span><span class="sxs-lookup"><span data-stu-id="eae7e-363">The lifetime of an `ICorDebugThread` instance is the same as the lifetime of the thread it represents.</span></span>  
  
 <span data-ttu-id="eae7e-364">[ICorDebugThread2 インターフェイス](icordebugthread2-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="eae7e-364">[ICorDebugThread2 Interface](icordebugthread2-interface.md)\\</span></span>
 <span data-ttu-id="eae7e-365">`ICorDebugThread` の論理的な拡張機能として動作します。</span><span class="sxs-lookup"><span data-stu-id="eae7e-365">Serves as a logical extension to `ICorDebugThread`.</span></span>  
  
 <span data-ttu-id="eae7e-366">[ICorDebugThread3 インターフェイス](icordebugthread3-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="eae7e-366">[ICorDebugThread3 Interface](icordebugthread3-interface.md)\\</span></span>
 <span data-ttu-id="eae7e-367">エントリ ポイントを提供します、 [ICorDebugStackWalk](icordebugstackwalk-interface.md)と対応するインターフェイス。</span><span class="sxs-lookup"><span data-stu-id="eae7e-367">Provides the entry point to the [ICorDebugStackWalk](icordebugstackwalk-interface.md) and corresponding interfaces.</span></span>  
  
 <span data-ttu-id="eae7e-368">[ICorDebugThread4 インターフェイス](icordebugthread4-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="eae7e-368">[ICorDebugThread4 Interface](icordebugthread4-interface.md)\\</span></span>
 <span data-ttu-id="eae7e-369">スレッドのブロック情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="eae7e-369">Provides thread blocking information.</span></span>  
  
 <span data-ttu-id="eae7e-370">[ICorDebugThreadEnum インターフェイス](icordebugthreadenum-interface1.md)\\</span><span class="sxs-lookup"><span data-stu-id="eae7e-370">[ICorDebugThreadEnum Interface](icordebugthreadenum-interface1.md)\\</span></span>
 <span data-ttu-id="eae7e-371">`ICorDebugEnum` メソッドを実装し、`ICorDebugThread` 配列を列挙します。</span><span class="sxs-lookup"><span data-stu-id="eae7e-371">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugThread` arrays.</span></span>  
  
 <span data-ttu-id="eae7e-372">[ICorDebugType インターフェイス](icordebugtype-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="eae7e-372">[ICorDebugType Interface](icordebugtype-interface.md)\\</span></span>
 <span data-ttu-id="eae7e-373">基本型または複合型 (つまり、ユーザー定義) のいずれかの型を表します。</span><span class="sxs-lookup"><span data-stu-id="eae7e-373">Represents a type, which can be either basic or complex (that is, user-defined).</span></span> <span data-ttu-id="eae7e-374">型がジェネリックの場合、`ICorDebugType` はインスタンス化されたジェネリック型を表します。</span><span class="sxs-lookup"><span data-stu-id="eae7e-374">If the type is generic, `ICorDebugType` represents the instantiated generic type.</span></span>  
  
 <span data-ttu-id="eae7e-375">[ICorDebugType2 インターフェイス](icordebugtype2-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="eae7e-375">[ICorDebugType2 Interface](icordebugtype2-interface.md)\\</span></span>
 <span data-ttu-id="eae7e-376">拡張、 [ICorDebugType](icordebugtype-interface.md)基本型または複合 (ユーザー定義) の型の型の識別子を取得するインターフェイス。</span><span class="sxs-lookup"><span data-stu-id="eae7e-376">Extends the [ICorDebugType](icordebugtype-interface.md) interface to retrieve the type identifier  of a base type or complex (user-defined) type.</span></span>  
  
 <span data-ttu-id="eae7e-377">[ICorDebugTypeEnum インターフェイス](icordebugtypeenum-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="eae7e-377">[ICorDebugTypeEnum Interface](icordebugtypeenum-interface.md)\\</span></span>
 <span data-ttu-id="eae7e-378">`ICorDebugEnum` メソッドを実装し、`ICorDebugType` 配列を列挙します。</span><span class="sxs-lookup"><span data-stu-id="eae7e-378">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugType` arrays.</span></span>  
  
 <span data-ttu-id="eae7e-379">[ICorDebugUnmanagedCallback インターフェイス](icordebugunmanagedcallback-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="eae7e-379">[ICorDebugUnmanagedCallback Interface](icordebugunmanagedcallback-interface.md)\\</span></span>
 <span data-ttu-id="eae7e-380">CLR に直接関連していないネイティブ イベントについて通知します。</span><span class="sxs-lookup"><span data-stu-id="eae7e-380">Provides notification of native events that are not directly related to the CLR.</span></span>  
  
 <span data-ttu-id="eae7e-381">[ICorDebugValue](icordebugvalue-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="eae7e-381">[ICorDebugValue](icordebugvalue-interface.md)\\</span></span>
 <span data-ttu-id="eae7e-382">デバッグ中のプロセス内の読み取り値または書き込み値を表します。</span><span class="sxs-lookup"><span data-stu-id="eae7e-382">Represents a read or write value in the process being debugged.</span></span>  
  
 <span data-ttu-id="eae7e-383">[ICorDebugValue2](icordebugvalue2-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="eae7e-383">[ICorDebugValue2](icordebugvalue2-interface.md)\\</span></span>
 <span data-ttu-id="eae7e-384">`ICorDebugValue` をサポートできるように `ICorDebugType` を拡張します。</span><span class="sxs-lookup"><span data-stu-id="eae7e-384">Extends `ICorDebugValue` to provide support for `ICorDebugType`.</span></span>  
  
 <span data-ttu-id="eae7e-385">[ICorDebugValue3 インターフェイス](icordebugvalue3-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="eae7e-385">[ICorDebugValue3 Interface](icordebugvalue3-interface.md)\\</span></span>
 <span data-ttu-id="eae7e-386">2 GB を超える配列のサポートを提供する"ICorDebugValue"と"ICorDebugValue2"インターフェイスを拡張します。</span><span class="sxs-lookup"><span data-stu-id="eae7e-386">Extends the "ICorDebugValue" and "ICorDebugValue2" interfaces to provide support for arrays that are larger than 2 GB.</span></span>  
  
 <span data-ttu-id="eae7e-387">[ICorDebugValueBreakpoint](icordebugvaluebreakpoint-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="eae7e-387">[ICorDebugValueBreakpoint](icordebugvaluebreakpoint-interface.md)\\</span></span>
 <span data-ttu-id="eae7e-388">特定の値にアクセスできるように `ICorDebugBreakpoint` を拡張します。</span><span class="sxs-lookup"><span data-stu-id="eae7e-388">Extends `ICorDebugBreakpoint` to provide access to specific values.</span></span>  
  
 <span data-ttu-id="eae7e-389">[ICorDebugValueEnum](icordebugvalueenum-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="eae7e-389">[ICorDebugValueEnum](icordebugvalueenum-interface.md)\\</span></span>
 <span data-ttu-id="eae7e-390">`ICorDebugEnum` メソッドを実装し、`ICorDebugValue` 配列を列挙します。</span><span class="sxs-lookup"><span data-stu-id="eae7e-390">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugValue` arrays.</span></span>  
  
 <span data-ttu-id="eae7e-391">[ICorDebugVariableHome インターフェイス](icordebugvariablehome-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="eae7e-391">[ICorDebugVariableHome Interface](icordebugvariablehome-interface.md)\\</span></span>
 <span data-ttu-id="eae7e-392">ローカル変数または関数の引数を表します。</span><span class="sxs-lookup"><span data-stu-id="eae7e-392">Represents a local variable or argument of a function.</span></span>  
  
 <span data-ttu-id="eae7e-393">[ICorDebugVariableHomeEnum インターフェイス](icordebugvariablehomeenum-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="eae7e-393">[ICorDebugVariableHomeEnum Interface](icordebugvariablehomeenum-interface.md)\\</span></span>
 <span data-ttu-id="eae7e-394">ローカル変数と関数の引数、列挙子を提供します。</span><span class="sxs-lookup"><span data-stu-id="eae7e-394">Provides an enumerator to the local variables and arguments in a function.</span></span>  
  
 <span data-ttu-id="eae7e-395">[ICorDebugVariableSymbol インターフェイス](icordebugvariablesymbol-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="eae7e-395">[ICorDebugVariableSymbol Interface](icordebugvariablesymbol-interface.md)\\</span></span>
 <span data-ttu-id="eae7e-396">変数のデバッグ シンボル情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="eae7e-396">Retrieves the debug symbol information for a variable.</span></span> <span data-ttu-id="eae7e-397">**.NET ネイティブのみで使用できます。**</span><span class="sxs-lookup"><span data-stu-id="eae7e-397">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="eae7e-398">[ICorDebugVirtualUnwinder インターフェイス](icordebugvirtualunwinder-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="eae7e-398">[ICorDebugVirtualUnwinder Interface](icordebugvirtualunwinder-interface.md)\\</span></span>
 <span data-ttu-id="eae7e-399">スタック アンワインドを支援するメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="eae7e-399">Provides methods to help in stack unwinding.</span></span> <span data-ttu-id="eae7e-400">**.NET ネイティブのみで使用できます。**</span><span class="sxs-lookup"><span data-stu-id="eae7e-400">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="eae7e-401">[ICorPublish インターフェイス](icorpublish-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="eae7e-401">[ICorPublish Interface](icorpublish-interface.md)\\</span></span>
 <span data-ttu-id="eae7e-402">発行プロセスの汎用インターフェイスとして機能します。</span><span class="sxs-lookup"><span data-stu-id="eae7e-402">Serves as the general interface for the publishing processes.</span></span>  
  
 <span data-ttu-id="eae7e-403">[ICorPublishAppDomain インターフェイス](icorpublishappdomain-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="eae7e-403">[ICorPublishAppDomain Interface](icorpublishappdomain-interface.md)\\</span></span>
 <span data-ttu-id="eae7e-404">アプリケーション ドメインの情報を表し、提供します。</span><span class="sxs-lookup"><span data-stu-id="eae7e-404">Represents and provides information about an application domain.</span></span>  
  
 <span data-ttu-id="eae7e-405">[ICorPublishAppDomainEnum インターフェイス](icorpublishappdomainenum-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="eae7e-405">[ICorPublishAppDomainEnum Interface](icorpublishappdomainenum-interface.md)\\</span></span>
 <span data-ttu-id="eae7e-406">現在プロセス内に存在する `ICorPublishAppDomain` オブジェクトのコレクションを走査するメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="eae7e-406">Provides methods that traverse a collection of `ICorPublishAppDomain` objects that currently exist within a process.</span></span>  
  
 <span data-ttu-id="eae7e-407">[ICorPublishEnum インターフェイス](icorpublishenum-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="eae7e-407">[ICorPublishEnum Interface](icorpublishenum-interface.md)\\</span></span>
 <span data-ttu-id="eae7e-408">発行する列挙子の抽象ベースとして機能します。</span><span class="sxs-lookup"><span data-stu-id="eae7e-408">Serves as the abstract base for publishing enumerators.</span></span>  
  
 <span data-ttu-id="eae7e-409">[ICorPublishProcess インターフェイス](icorpublishprocess-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="eae7e-409">[ICorPublishProcess Interface](icorpublishprocess-interface.md)\\</span></span>
 <span data-ttu-id="eae7e-410">プロセスの情報にアクセスするメソッドを適用します。</span><span class="sxs-lookup"><span data-stu-id="eae7e-410">Provides methods that access information about a process.</span></span>  
  
 <span data-ttu-id="eae7e-411">[ICorPublishProcessEnum インターフェイス](icorpublishprocessenum-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="eae7e-411">[ICorPublishProcessEnum Interface](icorpublishprocessenum-interface.md)\\</span></span>
 <span data-ttu-id="eae7e-412">`ICorPublishProcess` オブジェクトのコレクションを走査するメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="eae7e-412">Provides methods that traverse a collection of `ICorPublishProcess` objects.</span></span>  

 <span data-ttu-id="eae7e-413">[ISOSDacInterface インターフェイス](isosdacinterface-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="eae7e-413">[ISOSDacInterface Interface](isosdacinterface-interface.md)\\</span></span>
 <span data-ttu-id="eae7e-414">データにアクセスするヘルパー メソッドを提供します。`SOS`します。</span><span class="sxs-lookup"><span data-stu-id="eae7e-414">Provides helper methods to access data from `SOS`.</span></span>

 <span data-ttu-id="eae7e-415">[IXCLRDataMethodDefinition インターフェイス](ixclrdatamethoddefinition-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="eae7e-415">[IXCLRDataMethodDefinition Interface](ixclrdatamethoddefinition-interface.md)\\</span></span>
 <span data-ttu-id="eae7e-416">メソッドの定義に関する情報を照会するためのメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="eae7e-416">Provides methods for querying information about a method definition.</span></span>
 
 <span data-ttu-id="eae7e-417">[IXCLRDataMethodInstance インターフェイス](ixclrdatamethodinstance-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="eae7e-417">[IXCLRDataMethodInstance Interface](ixclrdatamethodinstance-interface.md)\\</span></span>
 <span data-ttu-id="eae7e-418">メソッド インスタンスの情報を照会するためのメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="eae7e-418">Provides methods for querying information about a method instance.</span></span>
 
 <span data-ttu-id="eae7e-419">[IXCLRDataModule インターフェイス](ixclrdatamodule-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="eae7e-419">[IXCLRDataModule Interface](ixclrdatamodule-interface.md)\\</span></span>
 <span data-ttu-id="eae7e-420">読み込まれたモジュールに関する情報を照会するためのメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="eae7e-420">Provides methods for querying information about a loaded module.</span></span>
 
 <span data-ttu-id="eae7e-421">[IXCLRDataProcess インターフェイス](ixclrdataprocess-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="eae7e-421">[IXCLRDataProcess Interface](ixclrdataprocess-interface.md)\\</span></span>
 <span data-ttu-id="eae7e-422">プロセスの情報を照会するためのメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="eae7e-422">Provides methods for querying information about a process.</span></span>
  
## <a name="related-sections"></a><span data-ttu-id="eae7e-423">関連項目</span><span class="sxs-lookup"><span data-stu-id="eae7e-423">Related Sections</span></span>  
 <span data-ttu-id="eae7e-424">[デバッグ コクラス](debugging-coclasses.md)\\</span><span class="sxs-lookup"><span data-stu-id="eae7e-424">[Debugging Coclasses](debugging-coclasses.md)\\</span></span>
 <span data-ttu-id="eae7e-425">[デバッグ グローバル静的関数](debugging-global-static-functions.md)\\</span><span class="sxs-lookup"><span data-stu-id="eae7e-425">[Debugging Global Static Functions](debugging-global-static-functions.md)\\</span></span>
 <span data-ttu-id="eae7e-426">[列挙体のデバッグ](debugging-enumerations.md)\\</span><span class="sxs-lookup"><span data-stu-id="eae7e-426">[Debugging Enumerations](debugging-enumerations.md)\\</span></span>
 <span data-ttu-id="eae7e-427">[デバッグ構造体](debugging-structures.md)\\</span><span class="sxs-lookup"><span data-stu-id="eae7e-427">[Debugging Structures](debugging-structures.md)\\</span></span>
