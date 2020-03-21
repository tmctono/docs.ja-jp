---
title: デバッグのインターフェイス
ms.date: 02/07/2019
helpviewer_keywords:
- unmanaged interfaces [.NET Framework], debugging
- debugging interfaces [.NET Framework]
- interfaces [.NET Framework debugging]
ms.assetid: b6297c26-7624-4431-8af4-14112d07bcd5
ms.openlocfilehash: c4b9cdc2bc90096ab7c3b041bd8aa2742b48c35c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179161"
---
# <a name="debugging-interfaces"></a><span data-ttu-id="355f3-102">デバッグのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="355f3-102">Debugging Interfaces</span></span>
<span data-ttu-id="355f3-103">ここでは、共通言語ランタイム (CLR: Common Language Runtime) で実行するプログラムのデバッグを処理するアンマネージ インターフェイスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="355f3-103">This section describes the unmanaged interfaces that handle the debugging of a program that is executing in the common language runtime (CLR).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="355f3-104">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="355f3-104">In This Section</span></span>  
 <span data-ttu-id="355f3-105">[インターフェイス](iclrdataenummemoryregions-interface.md)</span><span class="sxs-lookup"><span data-stu-id="355f3-105">[ICLRDataEnumMemoryRegions Interface](iclrdataenummemoryregions-interface.md)</span></span>\
 <span data-ttu-id="355f3-106">呼び出し元が指定したメモリ範囲を列挙するメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="355f3-106">Provides a method to enumerate regions of memory that are specified by callers.</span></span>  
  
 <span data-ttu-id="355f3-107">[コールバック インターフェイス](iclrdataenummemoryregionscallback-interface.md)</span><span class="sxs-lookup"><span data-stu-id="355f3-107">[ICLRDataEnumMemoryRegionsCallback Interface](iclrdataenummemoryregionscallback-interface.md)</span></span>\
 <span data-ttu-id="355f3-108">メモリの指定された領域を列挙した結果の `EnumMemoryRegions` をデバッガーにレポートするコールバック メソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="355f3-108">Provides a callback method for `EnumMemoryRegions` to report to the debugger, the result of an attempt to enumerate a specified region of memory.</span></span>  
  
 <span data-ttu-id="355f3-109">[インターフェイス](iclrdatatarget-interface.md)</span><span class="sxs-lookup"><span data-stu-id="355f3-109">[ICLRDataTarget Interface](iclrdatatarget-interface.md)</span></span>\
 <span data-ttu-id="355f3-110">対象の CLR プロセスと対話するためのメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="355f3-110">Provides methods for interaction with a target CLR process.</span></span>  
  
 <span data-ttu-id="355f3-111">[インターフェイス](iclrdatatarget2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="355f3-111">[ICLRDataTarget2 Interface](iclrdatatarget2-interface.md)</span></span>\
 <span data-ttu-id="355f3-112">データ アクセス サービス層で使用して対象プロセスの仮想メモリ領域を操作する、`ICLRDataTarget` のサブクラスです。</span><span class="sxs-lookup"><span data-stu-id="355f3-112">A subclass of `ICLRDataTarget` that is used by the data access services layer to manipulate virtual memory regions in the target process.</span></span>  
  
 <span data-ttu-id="355f3-113">[インターフェイス](iclrdatatarget3-interface.md)</span><span class="sxs-lookup"><span data-stu-id="355f3-113">[ICLRDataTarget3 Interface](iclrdatatarget3-interface.md)</span></span>\
 <span data-ttu-id="355f3-114">例外情報へのアクセスを提供する[ICLRDataTarget2](iclrdatatarget2-interface.md)のサブクラス。</span><span class="sxs-lookup"><span data-stu-id="355f3-114">A subclass of [ICLRDataTarget2](iclrdatatarget2-interface.md) that provides access to exception information.</span></span>  
  
 <span data-ttu-id="355f3-115">[インターフェイスのデバッグ](iclrdebugging-interface.md)</span><span class="sxs-lookup"><span data-stu-id="355f3-115">[ICLRDebugging Interface](iclrdebugging-interface.md)</span></span>\
 <span data-ttu-id="355f3-116">デバッグ用にモジュールの読み込みとアンロードを処理するメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="355f3-116">Provides methods that handle loading and unloading modules for debugging.</span></span>  
  
 <span data-ttu-id="355f3-117">[インターフェイス](iclrdebugginglibraryprovider-interface.md)</span><span class="sxs-lookup"><span data-stu-id="355f3-117">[ICLRDebuggingLibraryProvider Interface](iclrdebugginglibraryprovider-interface.md)</span></span>\
 <span data-ttu-id="355f3-118">メソッドを含む[、 ProvideLibrary メソッド](iclrdebugginglibraryprovider-providelibrary-method.md)は、共通言語ランタイムのバージョン固有のデバッグ ライブラリを配置し、要求に応じて読み込むライブラリ プロバイダーのコールバック インターフェイスを取得します。</span><span class="sxs-lookup"><span data-stu-id="355f3-118">Includes the [ProvideLibrary Method](iclrdebugginglibraryprovider-providelibrary-method.md) method, which gets a library provider callback interface that allows common language runtime version-specific debugging libraries to be located and loaded on demand.</span></span>  
  
 <span data-ttu-id="355f3-119">[ICLR メタデータ ロケーター インターフェイス](iclrmetadatalocator-interface.md)</span><span class="sxs-lookup"><span data-stu-id="355f3-119">[ICLRMetadataLocator Interface](iclrmetadatalocator-interface.md)</span></span>\
 <span data-ttu-id="355f3-120">データ アクセス サービス層で使用して、対象プロセス内のアセンブリのメタデータを見つけるためのインターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="355f3-120">Interface used by the data access services layer to locate metadata of assemblies in a target process.</span></span>  
  
 <span data-ttu-id="355f3-121">[インターフェイス](icordebug-interface.md)</span><span class="sxs-lookup"><span data-stu-id="355f3-121">[ICorDebug Interface](icordebug-interface.md)</span></span>\
 <span data-ttu-id="355f3-122">開発者が CLR 環境でアプリケーションをデバッグできるようにするメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="355f3-122">Provides methods that allow developers to debug applications in the CLR environment.</span></span>  
  
 <span data-ttu-id="355f3-123">[インターフェイス](icordebugappdomain-interface.md)</span><span class="sxs-lookup"><span data-stu-id="355f3-123">[ICorDebugAppDomain Interface](icordebugappdomain-interface.md)</span></span>\
 <span data-ttu-id="355f3-124">アプリケーション ドメインをデバッグするためのメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="355f3-124">Provides methods for debugging application domains.</span></span>  
  
 <span data-ttu-id="355f3-125">[インターフェイス](icordebugappdomain2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="355f3-125">[ICorDebugAppDomain2 Interface](icordebugappdomain2-interface.md)</span></span>\
 <span data-ttu-id="355f3-126">配列、ポインター、関数ポインター、および ByRef 型を使用するメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="355f3-126">Provides methods to work with arrays, pointers, function pointers, and ByRef types.</span></span> <span data-ttu-id="355f3-127">これは、`ICorDebugAppDomain` インターフェイスの機能を拡張するインターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="355f3-127">This interface is an extension of the `ICorDebugAppDomain` interface.</span></span>  
  
 <span data-ttu-id="355f3-128">[インターフェイス](icordebugappdomain3-interface.md)</span><span class="sxs-lookup"><span data-stu-id="355f3-128">[ICorDebugAppDomain3 Interface](icordebugappdomain3-interface.md)</span></span>\
 <span data-ttu-id="355f3-129">アプリケーション ドメイン内の Windows ランタイム型を操作するメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="355f3-129">Provides methods to work with the Windows Runtime types in an application domain.</span></span> <span data-ttu-id="355f3-130">このインターフェイスは、`ICorDebugAppDomain` インターフェイスと `ICorDebugAppDomain2` インターフェイスを拡張します。</span><span class="sxs-lookup"><span data-stu-id="355f3-130">This interface is an extension of the `ICorDebugAppDomain` and `ICorDebugAppDomain2` interfaces.</span></span>  
  
 <span data-ttu-id="355f3-131">[インターフェイス](icordebugappdomain4-interface.md)</span><span class="sxs-lookup"><span data-stu-id="355f3-131">[ICorDebugAppDomain4 Interface](icordebugappdomain4-interface.md)</span></span>\
 <span data-ttu-id="355f3-132">COM 呼び出し可能ラッパーからマネージ オブジェクトを取得する[ICorDebugAppDomain](icordebugappdomain-interface.md)インターフェイスを論理的に拡張します。</span><span class="sxs-lookup"><span data-stu-id="355f3-132">Logically extends the [ICorDebugAppDomain](icordebugappdomain-interface.md) interface to get a managed object from a COM callable wrapper.</span></span>  
  
 <span data-ttu-id="355f3-133">[インターフェイス](icordebugappdomainenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="355f3-133">[ICorDebugAppDomainEnum Interface](icordebugappdomainenum-interface.md)</span></span>\
 <span data-ttu-id="355f3-134">列挙体の次の位置から、指定した数の `ICorDebugAppDomain` の値を返すメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="355f3-134">Provides a method that returns a specified number of `ICorDebugAppDomain` values starting at the next location in the enumeration.</span></span>  
  
 <span data-ttu-id="355f3-135">[インターフェイス](icordebugarrayvalue-interface.md)</span><span class="sxs-lookup"><span data-stu-id="355f3-135">[ICorDebugArrayValue Interface](icordebugarrayvalue-interface.md)</span></span>\
 <span data-ttu-id="355f3-136">1 次元または多次元の配列を表す `ICorDebugHeapValue` のサブクラスです。</span><span class="sxs-lookup"><span data-stu-id="355f3-136">A subclass of `ICorDebugHeapValue` that represents a single-dimensional or multi-dimensional array.</span></span>  
  
 <span data-ttu-id="355f3-137">[インターフェイスを指定します。](icordebugassembly-interface.md)</span><span class="sxs-lookup"><span data-stu-id="355f3-137">[ICorDebugAssembly Interface](icordebugassembly-interface.md)</span></span>\
 <span data-ttu-id="355f3-138">アセンブリを表します。</span><span class="sxs-lookup"><span data-stu-id="355f3-138">Represents an assembly.</span></span>  
  
 <span data-ttu-id="355f3-139">[インターフェイス](icordebugassembly2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="355f3-139">[ICorDebugAssembly2 Interface](icordebugassembly2-interface.md)</span></span>\
 <span data-ttu-id="355f3-140">アセンブリを表します。</span><span class="sxs-lookup"><span data-stu-id="355f3-140">Represents an assembly.</span></span> <span data-ttu-id="355f3-141">これは、`ICorDebugAssembly` インターフェイスの機能を拡張するインターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="355f3-141">This interface is an extension of the `ICorDebugAssembly` interface.</span></span>  
  
 <span data-ttu-id="355f3-142">[インターフェイス](icordebugassembly3-interface.md)</span><span class="sxs-lookup"><span data-stu-id="355f3-142">[ICorDebugAssembly3 Interface](icordebugassembly3-interface.md)</span></span>\
 <span data-ttu-id="355f3-143">コンテナー アセンブリとその含まれているアセンブリをサポートするために[、ICorDebugAssembly](icordebugassembly-interface.md)インターフェイスを論理的に拡張します。</span><span class="sxs-lookup"><span data-stu-id="355f3-143">Logically extends the [ICorDebugAssembly](icordebugassembly-interface.md) interface to provide support for container assemblies and their contained assemblies.</span></span> <span data-ttu-id="355f3-144">**.NET ネイティブのみで使用できます。**</span><span class="sxs-lookup"><span data-stu-id="355f3-144">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="355f3-145">[インターフェイスを作成します。](icordebugassemblyenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="355f3-145">[ICorDebugAssemblyEnum Interface](icordebugassemblyenum-interface.md)</span></span>\
 <span data-ttu-id="355f3-146">`ICorDebugEnum` メソッドを実装し、`ICorDebugAssembly` 配列を列挙します。</span><span class="sxs-lookup"><span data-stu-id="355f3-146">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugAssembly` arrays.</span></span>  
  
 <span data-ttu-id="355f3-147">[インターフェイスをブロックします。](icordebugblockingobjectenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="355f3-147">[ICorDebugBlockingObjectEnum Interface](icordebugblockingobjectenum-interface.md)</span></span>\
 <span data-ttu-id="355f3-148">[構造体の](cordebugblockingobject-structure.md)一覧の列挙子を提供します。</span><span class="sxs-lookup"><span data-stu-id="355f3-148">Provides an enumerator for a list of [CorDebugBlockingObject](cordebugblockingobject-structure.md) structures.</span></span>  
  
 <span data-ttu-id="355f3-149">[インターフェイスを返します。](icordebugboxvalue-interface.md)</span><span class="sxs-lookup"><span data-stu-id="355f3-149">[ICorDebugBoxValue Interface](icordebugboxvalue-interface.md)</span></span>\
 <span data-ttu-id="355f3-150">ボックス化された値クラスのオブジェクトを表す `ICorDebugHeapValue` のサブクラス。</span><span class="sxs-lookup"><span data-stu-id="355f3-150">A subclass of `ICorDebugHeapValue` that represents a boxed value class object.</span></span>  
  
 <span data-ttu-id="355f3-151">[インターフェイスのデバッグのデバッグ](icordebugbreakpoint-interface.md)</span><span class="sxs-lookup"><span data-stu-id="355f3-151">[ICorDebugBreakpoint Interface](icordebugbreakpoint-interface.md)</span></span>\
 <span data-ttu-id="355f3-152">関数のブレークポイント、または値のウォッチ ポイントを表します。</span><span class="sxs-lookup"><span data-stu-id="355f3-152">Represents a breakpoint in a function or a watch point on a value.</span></span>  
  
 <span data-ttu-id="355f3-153">[インターフェイスをデバッグします。](icordebugbreakpointenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="355f3-153">[ICorDebugBreakpointEnum Interface](icordebugbreakpointenum-interface.md)</span></span>\
 <span data-ttu-id="355f3-154">`ICorDebugEnum` メソッドを実装し、`ICorDebugBreakpoint` 配列を列挙します。</span><span class="sxs-lookup"><span data-stu-id="355f3-154">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugBreakpoint` arrays.</span></span>  
  
 <span data-ttu-id="355f3-155">[インターフェイス](icordebugchain-interface.md)</span><span class="sxs-lookup"><span data-stu-id="355f3-155">[ICorDebugChain Interface](icordebugchain-interface.md)</span></span>\
 <span data-ttu-id="355f3-156">物理呼び出し履歴または論理呼び出し履歴のセグメントを表します。</span><span class="sxs-lookup"><span data-stu-id="355f3-156">Represents a segment of a physical or logical call stack.</span></span>  
  
 <span data-ttu-id="355f3-157">[インターフェイスをデバッグします。](icordebugchainenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="355f3-157">[ICorDebugChainEnum Interface](icordebugchainenum-interface.md)</span></span>\
 <span data-ttu-id="355f3-158">`ICorDebugEnum` メソッドを実装し、`ICorDebugChain` 配列を列挙します。</span><span class="sxs-lookup"><span data-stu-id="355f3-158">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugChain` arrays.</span></span>  
  
 <span data-ttu-id="355f3-159">[インターフェイス](icordebugclass-interface.md)</span><span class="sxs-lookup"><span data-stu-id="355f3-159">[ICorDebugClass Interface](icordebugclass-interface.md)</span></span>\
 <span data-ttu-id="355f3-160">基本型または複合型 (つまり、ユーザー定義) のいずれかの型を表します。</span><span class="sxs-lookup"><span data-stu-id="355f3-160">Represents a type, which can be either basic or complex (that is, user-defined).</span></span> <span data-ttu-id="355f3-161">型がジェネリックの場合、`ICorDebugClass` はインスタンス化されないジェネリック型を表します。</span><span class="sxs-lookup"><span data-stu-id="355f3-161">If the type is generic, `ICorDebugClass` represents the uninstantiated generic type.</span></span>  
  
 <span data-ttu-id="355f3-162">[インターフェイス](icordebugclass2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="355f3-162">[ICorDebugClass2 Interface](icordebugclass2-interface.md)</span></span>\
 <span data-ttu-id="355f3-163">ジェネリック、または <xref:System.Type> 型のメソッド パラメーターを持つクラスを表します。</span><span class="sxs-lookup"><span data-stu-id="355f3-163">Represents a generic class or a class with a method parameter of type <xref:System.Type>.</span></span> <span data-ttu-id="355f3-164">このインターフェイスは、`ICorDebugClass` の機能を拡張します。</span><span class="sxs-lookup"><span data-stu-id="355f3-164">This interface extends `ICorDebugClass`.</span></span>  
  
 <span data-ttu-id="355f3-165">[インターフェイスを指定します。](icordebugcode-interface1.md)</span><span class="sxs-lookup"><span data-stu-id="355f3-165">[ICorDebugCode Interface](icordebugcode-interface1.md)</span></span>\
 <span data-ttu-id="355f3-166">Microsoft Intermediate Language (MSIL) コードまたはネイティブ コードのセグメントを表します。</span><span class="sxs-lookup"><span data-stu-id="355f3-166">Represents a segment of either Microsoft intermediate language (MSIL) code or native code.</span></span>  
  
 <span data-ttu-id="355f3-167">[インターフェイス](icordebugcode2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="355f3-167">[ICorDebugCode2 Interface](icordebugcode2-interface.md)</span></span>\
 <span data-ttu-id="355f3-168">`ICorDebugCode` の機能を拡張するメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="355f3-168">Provides methods that extend the capabilities of `ICorDebugCode`.</span></span>  
  
 <span data-ttu-id="355f3-169">[インターフェイス](icordebugcode3-interface.md)</span><span class="sxs-lookup"><span data-stu-id="355f3-169">[ICorDebugCode3 Interface](icordebugcode3-interface.md)</span></span>\
 <span data-ttu-id="355f3-170">マネージ戻り値に関する情報を提供するために[ICorDebugCode](icordebugcode-interface1.md)と[ICorDebugCode2](icordebugcode2-interface.md)を拡張するメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="355f3-170">Provides a method that extends [ICorDebugCode](icordebugcode-interface1.md) and [ICorDebugCode2](icordebugcode2-interface.md) to provide information about a managed return value.</span></span>  
  
 <span data-ttu-id="355f3-171">[インターフェイス](icordebugcode4-interface.md)</span><span class="sxs-lookup"><span data-stu-id="355f3-171">[ICorDebugCode4 Interface](icordebugcode4-interface.md)</span></span>\
 <span data-ttu-id="355f3-172">デバッガーが関数のローカル変数と引数を列挙できるようにするメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="355f3-172">Provides a method that enables a debugger to enumerate the local variables and arguments in a function.</span></span>  
  
 <span data-ttu-id="355f3-173">[インターフェイスをデバッグします。](icordebugcodeenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="355f3-173">[ICorDebugCodeEnum Interface](icordebugcodeenum-interface.md)</span></span>\
 <span data-ttu-id="355f3-174">`ICorDebugEnum` メソッドを実装し、`ICorDebugCode` 配列を列挙します。</span><span class="sxs-lookup"><span data-stu-id="355f3-174">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugCode` arrays.</span></span>  
  
 <span data-ttu-id="355f3-175">[インターフェイスを指定します。](icordebugcomobjectvalue-interface.md)</span><span class="sxs-lookup"><span data-stu-id="355f3-175">[ICorDebugComObjectValue Interface](icordebugcomobjectvalue-interface.md)</span></span>\
 <span data-ttu-id="355f3-176">キャッシュされたインターフェイス オブジェクトを取得するメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="355f3-176">Provides methods to retrieve cached interface objects.</span></span>  
  
 <span data-ttu-id="355f3-177">[インターフェイス](icordebugcontext-interface.md)</span><span class="sxs-lookup"><span data-stu-id="355f3-177">[ICorDebugContext Interface](icordebugcontext-interface.md)</span></span>\
 <span data-ttu-id="355f3-178">コンテキストのオブジェクトを表します。</span><span class="sxs-lookup"><span data-stu-id="355f3-178">Represents a context object.</span></span> <span data-ttu-id="355f3-179">このインターフェイスはまだ実装されていません。</span><span class="sxs-lookup"><span data-stu-id="355f3-179">This interface has not been implemented yet.</span></span>  
  
 <span data-ttu-id="355f3-180">[インターフェイスを使用します。](icordebugcontroller-interface.md)</span><span class="sxs-lookup"><span data-stu-id="355f3-180">[ICorDebugController Interface](icordebugcontroller-interface.md)</span></span>\
 <span data-ttu-id="355f3-181">コードの実行コンテキストを制御できる <xref:System.Diagnostics.Process> または <xref:System.AppDomain> のスコープを表します。</span><span class="sxs-lookup"><span data-stu-id="355f3-181">Represents a scope, either a <xref:System.Diagnostics.Process> or an <xref:System.AppDomain>, in which code execution context can be controlled.</span></span>  
  
 <span data-ttu-id="355f3-182">[インターフェイスを指定します。](icordebugdatatarget-interface.md)</span><span class="sxs-lookup"><span data-stu-id="355f3-182">[ICorDebugDataTarget Interface](icordebugdatatarget-interface.md)</span></span>\
 <span data-ttu-id="355f3-183">特定のターゲット プロセスにアクセスするためのコールバック インターフェイスが用意されています。</span><span class="sxs-lookup"><span data-stu-id="355f3-183">Provides a callback interface that provides access to a particular target process.</span></span>  
  
 <span data-ttu-id="355f3-184">[インターフェイス](icordebugdatatarget2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="355f3-184">[ICorDebugDataTarget2 Interface](icordebugdatatarget2-interface.md)</span></span>\
 <span data-ttu-id="355f3-185">[インターフェイス](icordebugdatatarget-interface.md)を論理的に拡張します。</span><span class="sxs-lookup"><span data-stu-id="355f3-185">Logically extends the [ICorDebugDataTarget](icordebugdatatarget-interface.md) interface.</span></span> <span data-ttu-id="355f3-186">**.NET ネイティブのみで使用できます。**</span><span class="sxs-lookup"><span data-stu-id="355f3-186">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="355f3-187">[インターフェイス](icordebugdatatarget3-interface.md)</span><span class="sxs-lookup"><span data-stu-id="355f3-187">[ICorDebugDataTarget3 Interface](icordebugdatatarget3-interface.md)</span></span>\
 <span data-ttu-id="355f3-188">読み込まれたモジュールに関する情報を提供する[ICorDebugDataTarget](icordebugdatatarget-interface.md)インターフェイスを論理的に拡張します。</span><span class="sxs-lookup"><span data-stu-id="355f3-188">Logically extends the [ICorDebugDataTarget](icordebugdatatarget-interface.md) interface to provide information about loaded modules.</span></span> <span data-ttu-id="355f3-189">**.NET ネイティブのみで使用できます。**</span><span class="sxs-lookup"><span data-stu-id="355f3-189">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="355f3-190">[インターフェイスをデバッグします。](icordebugdebugevent-interface.md)</span><span class="sxs-lookup"><span data-stu-id="355f3-190">[ICorDebugDebugEvent Interface](icordebugdebugevent-interface.md)</span></span>\
 <span data-ttu-id="355f3-191">すべての `ICorDebug` デバッグ イベントを派生させる基本インターフェイスを定義します。</span><span class="sxs-lookup"><span data-stu-id="355f3-191">Defines the base interface from which all `ICorDebug` debug events derive.</span></span> <span data-ttu-id="355f3-192">**.NET ネイティブのみで使用できます。**</span><span class="sxs-lookup"><span data-stu-id="355f3-192">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="355f3-193">[インターフェイスをデバッグします。](icordebugeditandcontinueerrorinfo-interface.md)</span><span class="sxs-lookup"><span data-stu-id="355f3-193">[ICorDebugEditAndContinueErrorInfo Interface](icordebugeditandcontinueerrorinfo-interface.md)</span></span>\
 <span data-ttu-id="355f3-194">互換性のために残されています。</span><span class="sxs-lookup"><span data-stu-id="355f3-194">Obsolete.</span></span> <span data-ttu-id="355f3-195">このインターフェイスは使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="355f3-195">Do not use this interface.</span></span>  
  
 <span data-ttu-id="355f3-196">[インターフェイスを継続します。](icordebugeditandcontinuesnapshot-interface.md)</span><span class="sxs-lookup"><span data-stu-id="355f3-196">[ICorDebugEditAndContinueSnapshot Interface](icordebugeditandcontinuesnapshot-interface.md)</span></span>\
 <span data-ttu-id="355f3-197">互換性のために残されています。</span><span class="sxs-lookup"><span data-stu-id="355f3-197">Obsolete.</span></span> <span data-ttu-id="355f3-198">このインターフェイスは使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="355f3-198">Do not use this interface.</span></span>  
  
 <span data-ttu-id="355f3-199">[インターフェイス](icordebugenum-interface1.md)</span><span class="sxs-lookup"><span data-stu-id="355f3-199">[ICorDebugEnum Interface](icordebugenum-interface1.md)</span></span>\
 <span data-ttu-id="355f3-200">デバッグ中の列挙子の抽象基底インターフェイスとして機能します。</span><span class="sxs-lookup"><span data-stu-id="355f3-200">Serves as the abstract base interface for debugging enumerators.</span></span>  
  
 <span data-ttu-id="355f3-201">[インターフェイスをデバッグします。](icordebugerrorinfoenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="355f3-201">[ICorDebugErrorInfoEnum Interface](icordebugerrorinfoenum-interface.md)</span></span>\
 <span data-ttu-id="355f3-202">互換性のために残されています。</span><span class="sxs-lookup"><span data-stu-id="355f3-202">Obsolete.</span></span> <span data-ttu-id="355f3-203">このインターフェイスは使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="355f3-203">Do not use this interface.</span></span>  
  
 <span data-ttu-id="355f3-204">[インターフェイス](icordebugeval-interface.md)</span><span class="sxs-lookup"><span data-stu-id="355f3-204">[ICorDebugEval Interface](icordebugeval-interface.md)</span></span>\
 <span data-ttu-id="355f3-205">デバッガーが、デバッグ中のコードのコンテキスト内でコードを実行できるメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="355f3-205">Provides methods to enable the debugger to execute code within the context of the code being debugged.</span></span>  
  
 <span data-ttu-id="355f3-206">[インターフェイス](icordebugeval2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="355f3-206">[ICorDebugEval2 Interface](icordebugeval2-interface.md)</span></span>\
 <span data-ttu-id="355f3-207">ジェネリック型をサポートできるように `ICorDebugEval` を拡張します。</span><span class="sxs-lookup"><span data-stu-id="355f3-207">Extends `ICorDebugEval` to provide support for generic types.</span></span>  
  
 <span data-ttu-id="355f3-208">[インターフェイスを呼び出します。](icordebugexceptiondebugevent-interface.md)</span><span class="sxs-lookup"><span data-stu-id="355f3-208">[ICorDebugExceptionDebugEvent Interface](icordebugexceptiondebugevent-interface.md)</span></span>\
 <span data-ttu-id="355f3-209">例外イベントをサポートするために[インターフェイス](icordebugdebugevent-interface.md)を拡張します。</span><span class="sxs-lookup"><span data-stu-id="355f3-209">Extends the [ICorDebugDebugEvent](icordebugdebugevent-interface.md) interface to support exception events.</span></span> <span data-ttu-id="355f3-210">**.NET ネイティブのみで使用できます。**</span><span class="sxs-lookup"><span data-stu-id="355f3-210">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="355f3-211">[インターフェイスを呼び出します。](icordebugexceptionobjectcallstackenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="355f3-211">[ICorDebugExceptionObjectCallStackEnum Interface](icordebugexceptionobjectcallstackenum-interface.md)</span></span>\
 <span data-ttu-id="355f3-212">例外オブジェクトに埋め込まれているコール スタックの情報の列挙子を提供します。</span><span class="sxs-lookup"><span data-stu-id="355f3-212">Provides an enumerator for call stack information that is embedded in an exception object.</span></span>  
  
 <span data-ttu-id="355f3-213">[インターフェイスを呼び出します。](icordebugexceptionobjectvalue-interface.md)</span><span class="sxs-lookup"><span data-stu-id="355f3-213">[ICorDebugExceptionObjectValue Interface](icordebugexceptionobjectvalue-interface.md)</span></span>\
 <span data-ttu-id="355f3-214">[マネージ例外](icordebugobjectvalue-interface.md)オブジェクトからスタック トレース情報を提供するインターフェイスを拡張します。</span><span class="sxs-lookup"><span data-stu-id="355f3-214">Extends the [ICorDebugObjectValue](icordebugobjectvalue-interface.md) interface to provide stack trace information from a managed exception object.</span></span>  
  
 <span data-ttu-id="355f3-215">[インターフェイスを指定します。](icordebugframe-interface.md)</span><span class="sxs-lookup"><span data-stu-id="355f3-215">[ICorDebugFrame Interface](icordebugframe-interface.md)</span></span>\
 <span data-ttu-id="355f3-216">現在のスタックのフレームを表します。</span><span class="sxs-lookup"><span data-stu-id="355f3-216">Represents a frame on the current stack.</span></span>  
  
 <span data-ttu-id="355f3-217">[インターフェイスをデバッグします。](icordebugframeenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="355f3-217">[ICorDebugFrameEnum Interface](icordebugframeenum-interface.md)</span></span>\
 <span data-ttu-id="355f3-218">`ICorDebugEnum` メソッドを実装し、`ICorDebugFrame` 配列を列挙します。</span><span class="sxs-lookup"><span data-stu-id="355f3-218">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugFrame` arrays.</span></span>  
  
 <span data-ttu-id="355f3-219">[インターフェイス](icordebugfunction-interface1.md)</span><span class="sxs-lookup"><span data-stu-id="355f3-219">[ICorDebugFunction Interface](icordebugfunction-interface1.md)</span></span>\
 <span data-ttu-id="355f3-220">マネージド関数またはマネージド メソッドを表します。</span><span class="sxs-lookup"><span data-stu-id="355f3-220">Represents a managed function or method.</span></span>  
  
 <span data-ttu-id="355f3-221">[インターフェイス](icordebugfunction2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="355f3-221">[ICorDebugFunction2 Interface](icordebugfunction2-interface.md)</span></span>\
 <span data-ttu-id="355f3-222">`ICorDebugFunction` を論理的に拡張して、"マイ コードのみ" ステップ実行によるデバッグをサポートします。</span><span class="sxs-lookup"><span data-stu-id="355f3-222">Logically extends `ICorDebugFunction` to provide support for Just My Code step-through debugging.</span></span>  
  
 <span data-ttu-id="355f3-223">[インターフェイス](icordebugfunction3-interface.md)</span><span class="sxs-lookup"><span data-stu-id="355f3-223">[ICorDebugFunction3 Interface](icordebugfunction3-interface.md)</span></span>\
 <span data-ttu-id="355f3-224">論理的に、ReJIT 要求からコードへのアクセスを提供する[ICorDebugFunction](icordebugfunction-interface1.md)インターフェイスを拡張します。</span><span class="sxs-lookup"><span data-stu-id="355f3-224">Logically extends the [ICorDebugFunction](icordebugfunction-interface1.md) interface to provide access to code from a ReJIT request.</span></span>  
  
 <span data-ttu-id="355f3-225">[インターフェイスを関数のブレークポイントのインターフェイスを使用します。](icordebugfunctionbreakpoint-interface.md)</span><span class="sxs-lookup"><span data-stu-id="355f3-225">[ICorDebugFunctionBreakpoint Interface](icordebugfunctionbreakpoint-interface.md)</span></span>\
 <span data-ttu-id="355f3-226">関数内のブレークポイントをサポートするように `ICorDebugBreakpoint` を拡張します。</span><span class="sxs-lookup"><span data-stu-id="355f3-226">Extends `ICorDebugBreakpoint` to support breakpoints within functions.</span></span>  
  
 <span data-ttu-id="355f3-227">[インターフェイスを指定します。](icordebuggcreferenceenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="355f3-227">[ICorDebugGCReferenceEnum Interface](icordebuggcreferenceenum-interface.md)</span></span>\
 <span data-ttu-id="355f3-228">ガベージ コレクトされるオブジェクトの列挙子を提供します。</span><span class="sxs-lookup"><span data-stu-id="355f3-228">Provides an enumerator for objects that will be garbage-collected.</span></span>  
  
 <span data-ttu-id="355f3-229">[インターフェイスを使用します。](icordebuggenericvalue-interface.md)</span><span class="sxs-lookup"><span data-stu-id="355f3-229">[ICorDebugGenericValue Interface](icordebuggenericvalue-interface.md)</span></span>\
 <span data-ttu-id="355f3-230">すべての値に適用する `ICorDebugValue` のサブクラスです。</span><span class="sxs-lookup"><span data-stu-id="355f3-230">A subclass of `ICorDebugValue` that applies to all values.</span></span> <span data-ttu-id="355f3-231">このインターフェイスは、値に対して Get メソッドと Set メソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="355f3-231">This interface provides Get and Set methods for the value.</span></span>  
  
 <span data-ttu-id="355f3-232">[インターフェイスを使用します。](icordebugguidtotypeenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="355f3-232">[ICorDebugGuidToTypeEnum Interface](icordebugguidtotypeenum-interface.md)</span></span>\
 <span data-ttu-id="355f3-233">GUID およびその対応する `ICorDebugType` オブジェクトをマップするオブジェクトの列挙子を提供します。</span><span class="sxs-lookup"><span data-stu-id="355f3-233">Provides an enumerator for an object that maps GUIDs and their corresponding `ICorDebugType` objects.</span></span>  
  
 <span data-ttu-id="355f3-234">[インターフェイスを処理します。](icordebughandlevalue-interface.md)</span><span class="sxs-lookup"><span data-stu-id="355f3-234">[ICorDebugHandleValue Interface](icordebughandlevalue-interface.md)</span></span>\
 <span data-ttu-id="355f3-235">デバッガーが作成したガベージ コレクションのハンドルへの参照値を表す `ICorDebugReferenceValue` のサブクラスです。</span><span class="sxs-lookup"><span data-stu-id="355f3-235">A subclass of `ICorDebugReferenceValue` that represents a reference value to which the debugger has created a handle for garbage collection.</span></span>  
  
 <span data-ttu-id="355f3-236">[インターフェイス](icordebugheapenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="355f3-236">[ICorDebugHeapEnum Interface](icordebugheapenum-interface.md)</span></span>\
 <span data-ttu-id="355f3-237">マネージド ヒープのオブジェクトの列挙子を提供します。</span><span class="sxs-lookup"><span data-stu-id="355f3-237">Provides an enumerator for objects on the managed heap.</span></span>  
  
 <span data-ttu-id="355f3-238">[インターフェイスを指定します。](icordebugheapsegmentenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="355f3-238">[ICorDebugHeapSegmentEnum Interface](icordebugheapsegmentenum-interface.md)</span></span>\
 <span data-ttu-id="355f3-239">マネージド ヒープのメモリ領域の列挙子を提供します。</span><span class="sxs-lookup"><span data-stu-id="355f3-239">Provides an enumerator for the memory regions of the managed heap.</span></span>  
  
 <span data-ttu-id="355f3-240">[インターフェイスを指定します。](icordebugheapvalue-interface.md)</span><span class="sxs-lookup"><span data-stu-id="355f3-240">[ICorDebugHeapValue Interface](icordebugheapvalue-interface.md)</span></span>\
 <span data-ttu-id="355f3-241">CLR ガベージ コレクターによって収集されたオブジェクトを表す `ICorDebugValue` のサブクラスです。</span><span class="sxs-lookup"><span data-stu-id="355f3-241">A subclass of `ICorDebugValue` that represents an object that has been collected by the CLR garbage collector.</span></span>  
  
 <span data-ttu-id="355f3-242">[インターフェイス](icordebugheapvalue2-interface1.md)</span><span class="sxs-lookup"><span data-stu-id="355f3-242">[ICorDebugHeapValue2 Interface](icordebugheapvalue2-interface1.md)</span></span>\
 <span data-ttu-id="355f3-243">ランタイム ハンドルのサポートを提供する `ICorDebugHeapValue` の拡張機能です。</span><span class="sxs-lookup"><span data-stu-id="355f3-243">An extension of `ICorDebugHeapValue` that provides support for runtime handles.</span></span>  
  
 <span data-ttu-id="355f3-244">[インターフェイス](icordebugheapvalue3-interface.md)</span><span class="sxs-lookup"><span data-stu-id="355f3-244">[ICorDebugHeapValue3 Interface](icordebugheapvalue3-interface.md)</span></span>\
 <span data-ttu-id="355f3-245">オブジェクトのモニター ロック プロパティを公開します。</span><span class="sxs-lookup"><span data-stu-id="355f3-245">Exposes the monitor lock properties of objects.</span></span>  
  
 <span data-ttu-id="355f3-246">[インターフェイス](icordebugilcode-interface.md)</span><span class="sxs-lookup"><span data-stu-id="355f3-246">[ICorDebugILCode Interface](icordebugilcode-interface.md)</span></span>\
 <span data-ttu-id="355f3-247">中間言語 (IL) コードのセグメントを表します。</span><span class="sxs-lookup"><span data-stu-id="355f3-247">Represents a segment of intermediate language (IL) code.</span></span>  
  
 <span data-ttu-id="355f3-248">[インターフェイス](icordebugilcode2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="355f3-248">[ICorDebugILCode2 Interface](icordebugilcode2-interface.md)</span></span>\
 <span data-ttu-id="355f3-249">関数のローカル変数シグネチャのトークンを返すメソッドを提供するために[ICorDebugILCode](icordebugilcode-interface.md)インターフェイスを論理的に拡張し、プロファイラーのインストルメント化された中間言語 (IL) オフセットを元のメソッドの IL オフセットにマップします。</span><span class="sxs-lookup"><span data-stu-id="355f3-249">Logically extends the [ICorDebugILCode](icordebugilcode-interface.md) interface to provide methods that return the token for a function's local variable signature, and that map a profiler's instrumented intermediate language (IL) offsets to original method IL offsets.</span></span>  
  
 <span data-ttu-id="355f3-250">[インターフェイス](icordebugilframe-interface.md)</span><span class="sxs-lookup"><span data-stu-id="355f3-250">[ICorDebugILFrame Interface](icordebugilframe-interface.md)</span></span>\
 <span data-ttu-id="355f3-251">MSIL コードのスタック フレームを表します。</span><span class="sxs-lookup"><span data-stu-id="355f3-251">Represents a stack frame of MSIL code.</span></span>  
  
 <span data-ttu-id="355f3-252">[インターフェイス](icordebugilframe2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="355f3-252">[ICorDebugILFrame2 Interface](icordebugilframe2-interface.md)</span></span>\
 <span data-ttu-id="355f3-253">`ICorDebugILFrame` の論理拡張機能です。</span><span class="sxs-lookup"><span data-stu-id="355f3-253">A logical extension of `ICorDebugILFrame`.</span></span>  
  
 <span data-ttu-id="355f3-254">[インターフェイス](icordebugilframe3-interface.md)</span><span class="sxs-lookup"><span data-stu-id="355f3-254">[ICorDebugILFrame3 Interface](icordebugilframe3-interface.md)</span></span>\
 <span data-ttu-id="355f3-255">関数の戻り値をカプセル化するメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="355f3-255">Provides a method that encapsulates the return value of a function.</span></span>  
  
 <span data-ttu-id="355f3-256">[インターフェイス](icordebugilframe4-interface.md)</span><span class="sxs-lookup"><span data-stu-id="355f3-256">[ICorDebugILFrame4 Interface](icordebugilframe4-interface.md)</span></span>\
 <span data-ttu-id="355f3-257">ローカル変数にアクセスできるようにするメソッドおよび中間言語 (IL) コードのスタック フレームのコードを提供します。</span><span class="sxs-lookup"><span data-stu-id="355f3-257">Provides methods that allow you to access the local variables and code in a stack frame of intermediate language (IL) code.</span></span> <span data-ttu-id="355f3-258">パラメーターは、プロファイラーの ReJIT インストルメンテーションに追加される変数およびコードへデバッガーがアクセスできるかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="355f3-258">A parameter specifies whether the debugger has access to variables and code added in profiler ReJIT instrumentation.</span></span>  
  
 <span data-ttu-id="355f3-259">[フィールド インターフェイス](icordebuginstancefieldsymbol-interface.md)</span><span class="sxs-lookup"><span data-stu-id="355f3-259">[ICorDebugInstanceFieldSymbol Interface](icordebuginstancefieldsymbol-interface.md)</span></span>\
 <span data-ttu-id="355f3-260">インスタンス フィールドのデバッグ シンボル情報を表します。</span><span class="sxs-lookup"><span data-stu-id="355f3-260">Represents the debug symbol information for an instance field.</span></span> <span data-ttu-id="355f3-261">**.NET ネイティブのみで使用できます。**</span><span class="sxs-lookup"><span data-stu-id="355f3-261">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="355f3-262">[インターフェイス](icordebuginternalframe-interface.md)</span><span class="sxs-lookup"><span data-stu-id="355f3-262">[ICorDebugInternalFrame Interface](icordebuginternalframe-interface.md)</span></span>\
 <span data-ttu-id="355f3-263">デバッガーのフレーム種類を識別します。</span><span class="sxs-lookup"><span data-stu-id="355f3-263">Identifies frame types for the debugger.</span></span>  
  
 <span data-ttu-id="355f3-264">[インターフェイス](icordebuginternalframe2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="355f3-264">[ICorDebugInternalFrame2 Interface](icordebuginternalframe2-interface.md)</span></span>\
 <span data-ttu-id="355f3-265">[ICorDebugFrame](icordebugframe-interface.md)オブジェクトに関連するスタック アドレスと位置を含む、内部フレームに関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="355f3-265">Provides information about internal frames, including stack address and position in relation to [ICorDebugFrame](icordebugframe-interface.md) objects.</span></span>  
  
 <span data-ttu-id="355f3-266">[インターフェイスを使用します。](icordebugloadedmodule-interface.md)</span><span class="sxs-lookup"><span data-stu-id="355f3-266">[ICorDebugLoadedModule Interface](icordebugloadedmodule-interface.md)</span></span>\
 <span data-ttu-id="355f3-267">読み込まれたモジュールについての情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="355f3-267">Provides information about a loaded module.</span></span> <span data-ttu-id="355f3-268">**.NET ネイティブのみで使用できます。**</span><span class="sxs-lookup"><span data-stu-id="355f3-268">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="355f3-269">[インターフェイスをデバッグします。](icordebugmanagedcallback-interface.md)</span><span class="sxs-lookup"><span data-stu-id="355f3-269">[ICorDebugManagedCallback Interface](icordebugmanagedcallback-interface.md)</span></span>\
 <span data-ttu-id="355f3-270">デバッガーのコールバックを処理するメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="355f3-270">Provides methods to process debugger callbacks.</span></span>  
  
 <span data-ttu-id="355f3-271">[インターフェイスをマネージ デバッグします。](icordebugmanagedcallback2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="355f3-271">[ICorDebugManagedCallback2 Interface](icordebugmanagedcallback2-interface.md)</span></span>\
 <span data-ttu-id="355f3-272">デバッガーの例外処理およびマネージド デバッグ アシスタント (MDA: Managed Debugging Assistants) をサポートするメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="355f3-272">Provides methods to support debugger exception handling and managed debugging assistants (MDAs).</span></span> <span data-ttu-id="355f3-273">`ICorDebugManagedCallback2` は、`ICorDebugManagedCallback` の論理拡張機能です。</span><span class="sxs-lookup"><span data-stu-id="355f3-273">`ICorDebugManagedCallback2` is a logical extension of `ICorDebugManagedCallback`.</span></span>  
  
 <span data-ttu-id="355f3-274">[インターフェイスをデバッグします。](icordebugmanagedcallback3-interface.md)</span><span class="sxs-lookup"><span data-stu-id="355f3-274">[ICorDebugManagedCallback3 Interface](icordebugmanagedcallback3-interface.md)</span></span>\
 <span data-ttu-id="355f3-275">有効なカスタムのデバッガー通知が発生したことを示すコールバック メソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="355f3-275">Provides a callback method that indicates that an enabled custom debugger notification has been raised.</span></span>  
  
 <span data-ttu-id="355f3-276">[インターフェイス](icordebugmda-interface.md)</span><span class="sxs-lookup"><span data-stu-id="355f3-276">[ICorDebugMDA Interface](icordebugmda-interface.md)</span></span>\
 <span data-ttu-id="355f3-277">マネージド デバッグ アシスタント (MDA) メッセージを表します。</span><span class="sxs-lookup"><span data-stu-id="355f3-277">Represents a managed debugging assistant (MDA) message.</span></span>  
  
 <span data-ttu-id="355f3-278">[インターフェイスをデバッグします。](icordebugmemorybuffer-interface.md)</span><span class="sxs-lookup"><span data-stu-id="355f3-278">[ICorDebugMemoryBuffer Interface](icordebugmemorybuffer-interface.md)</span></span>\
 <span data-ttu-id="355f3-279">メモリ内のバッファーを表します。</span><span class="sxs-lookup"><span data-stu-id="355f3-279">Represents an in-memory buffer.</span></span> <span data-ttu-id="355f3-280">**.NET ネイティブのみで使用できます。**</span><span class="sxs-lookup"><span data-stu-id="355f3-280">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="355f3-281">[レコード インターフェイスをマージしました。](icordebugmergedassemblyrecord-interface.md)</span><span class="sxs-lookup"><span data-stu-id="355f3-281">[ICorDebugMergedAssemblyRecord Interface](icordebugmergedassemblyrecord-interface.md)</span></span>\
 <span data-ttu-id="355f3-282">マージされたアセンブリに関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="355f3-282">Provides information about a merged assembly.</span></span> <span data-ttu-id="355f3-283">**.NET ネイティブのみで使用できます。**</span><span class="sxs-lookup"><span data-stu-id="355f3-283">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="355f3-284">[インターフェイスをデバッグします。](icordebugmetadatalocator-interface.md)</span><span class="sxs-lookup"><span data-stu-id="355f3-284">[ICorDebugMetaDataLocator Interface](icordebugmetadatalocator-interface.md)</span></span>\
 <span data-ttu-id="355f3-285">デバッガーにメタデータ情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="355f3-285">Provides metadata information to the debugger.</span></span>  
  
 <span data-ttu-id="355f3-286">[インターフェイス](icordebugmodule-interface.md)</span><span class="sxs-lookup"><span data-stu-id="355f3-286">[ICorDebugModule Interface](icordebugmodule-interface.md)</span></span>\
 <span data-ttu-id="355f3-287">実行可能ファイルまたはダイナミック リンク ライブラリ (DLL: Dynamic-Link Library) のいずれかの CLR モジュールを表します。</span><span class="sxs-lookup"><span data-stu-id="355f3-287">Represents a CLR module, which is either an executable or a dynamic-link library (DLL).</span></span>  
  
 <span data-ttu-id="355f3-288">[インターフェイス](icordebugmodule2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="355f3-288">[ICorDebugModule2 Interface](icordebugmodule2-interface.md)</span></span>\
 <span data-ttu-id="355f3-289">`ICorDebugModule` の論理的な拡張機能として動作します。</span><span class="sxs-lookup"><span data-stu-id="355f3-289">Serves as a logical extension to `ICorDebugModule`.</span></span>  
  
 <span data-ttu-id="355f3-290">[インターフェイス](icordebugmodule3-interface.md)</span><span class="sxs-lookup"><span data-stu-id="355f3-290">[ICorDebugModule3 Interface](icordebugmodule3-interface.md)</span></span>\
 <span data-ttu-id="355f3-291">動的モジュールのシンボル リーダーを作成します。</span><span class="sxs-lookup"><span data-stu-id="355f3-291">Creates a symbol reader for a dynamic module.</span></span>  
  
 <span data-ttu-id="355f3-292">[インターフェイスをデバッグモジュールのブレークポイント](icordebugmodulebreakpoint-interface.md)</span><span class="sxs-lookup"><span data-stu-id="355f3-292">[ICorDebugModuleBreakpoint Interface](icordebugmodulebreakpoint-interface.md)</span></span>\
 <span data-ttu-id="355f3-293">特定のモジュールにアクセスできるように `ICorDebugBreakpoint` を拡張します。</span><span class="sxs-lookup"><span data-stu-id="355f3-293">Extends `ICorDebugBreakpoint` to provide access to specific modules.</span></span>  
  
 <span data-ttu-id="355f3-294">[インターフェイスをデバッグします。](icordebugmoduledebugevent-interface.md)</span><span class="sxs-lookup"><span data-stu-id="355f3-294">[ICorDebugModuleDebugEvent Interface](icordebugmoduledebugevent-interface.md)</span></span>\
 <span data-ttu-id="355f3-295">モジュール レベルの[イベント](icordebugdebugevent-interface.md)をサポートするようにインターフェイスを拡張します。</span><span class="sxs-lookup"><span data-stu-id="355f3-295">Extends the [ICorDebugDebugEvent](icordebugdebugevent-interface.md) interface to support module-level events.</span></span> <span data-ttu-id="355f3-296">**.NET ネイティブのみで使用できます。**</span><span class="sxs-lookup"><span data-stu-id="355f3-296">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="355f3-297">[インターフェイスを使用します。](icordebugmoduleenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="355f3-297">[ICorDebugModuleEnum Interface](icordebugmoduleenum-interface.md)</span></span>\
 <span data-ttu-id="355f3-298">`ICorDebugEnum` メソッドを実装し、`ICorDebugModule` 配列を列挙します。</span><span class="sxs-lookup"><span data-stu-id="355f3-298">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugModule` arrays.</span></span>  
  
 <span data-ttu-id="355f3-299">[インターフェイスを変更します。](icordebugmutabledatatarget-interface.md)</span><span class="sxs-lookup"><span data-stu-id="355f3-299">[ICorDebugMutableDataTarget Interface](icordebugmutabledatatarget-interface.md)</span></span>\
 <span data-ttu-id="355f3-300">変更可能なデータ[ターゲット](icordebugdatatarget-interface.md)をサポートするインターフェイスを拡張します。</span><span class="sxs-lookup"><span data-stu-id="355f3-300">Extends the [ICorDebugDataTarget](icordebugdatatarget-interface.md) interface to support mutable data targets.</span></span>  
  
 <span data-ttu-id="355f3-301">[インターフェイス](icordebugnativeframe-interface.md)</span><span class="sxs-lookup"><span data-stu-id="355f3-301">[ICorDebugNativeFrame Interface](icordebugnativeframe-interface.md)</span></span>\
 <span data-ttu-id="355f3-302">ネイティブ フレームで使用される `ICorDebugFrame` の特化された実装。</span><span class="sxs-lookup"><span data-stu-id="355f3-302">A specialized implementation of `ICorDebugFrame` used for native frames.</span></span>  
  
 <span data-ttu-id="355f3-303">[インターフェイス](icordebugnativeframe2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="355f3-303">[ICorDebugNativeFrame2 Interface](icordebugnativeframe2-interface.md)</span></span>\
 <span data-ttu-id="355f3-304">子と親のフレームの関係をテストするメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="355f3-304">Provides methods that test for child and parent frame relationships.</span></span>  
  
 <span data-ttu-id="355f3-305">[インターフェイス](icordebugobjectenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="355f3-305">[ICorDebugObjectEnum Interface](icordebugobjectenum-interface.md)</span></span>\
 <span data-ttu-id="355f3-306">`ICorDebugEnum` メソッドを実装し、オブジェクトの配列を相対仮想アドレス (RVA: Relative Virtual Address) で列挙します。</span><span class="sxs-lookup"><span data-stu-id="355f3-306">Implements `ICorDebugEnum` methods, and enumerates arrays of objects by their relative virtual addresses (RVAs).</span></span>  
  
 <span data-ttu-id="355f3-307">[インターフェイスを指定します。](icordebugobjectvalue-interface.md)</span><span class="sxs-lookup"><span data-stu-id="355f3-307">[ICorDebugObjectValue Interface](icordebugobjectvalue-interface.md)</span></span>\
 <span data-ttu-id="355f3-308">オブジェクトが含まれた値を表す `ICorDebugValue` のサブクラスです。</span><span class="sxs-lookup"><span data-stu-id="355f3-308">A subclass of `ICorDebugValue` that represents a value that contains an object.</span></span>  
  
 <span data-ttu-id="355f3-309">[インターフェイス](icordebugobjectvalue2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="355f3-309">[ICorDebugObjectValue2 Interface](icordebugobjectvalue2-interface.md)</span></span>\
 <span data-ttu-id="355f3-310">継承およびオーバーライドをサポートするように `ICorDebugObjectValue` を拡張します。</span><span class="sxs-lookup"><span data-stu-id="355f3-310">Extends `ICorDebugObjectValue` to support inheritance and overrides.</span></span>  
  
 <span data-ttu-id="355f3-311">[インターフェイス](icordebugprocess-interface.md)</span><span class="sxs-lookup"><span data-stu-id="355f3-311">[ICorDebugProcess Interface](icordebugprocess-interface.md)</span></span>\
 <span data-ttu-id="355f3-312">マネージド コードを実行しているプロセスを表します。</span><span class="sxs-lookup"><span data-stu-id="355f3-312">Represents a process that is executing managed code.</span></span>  
  
 <span data-ttu-id="355f3-313">[インターフェイス](icordebugprocess2-interface1.md)</span><span class="sxs-lookup"><span data-stu-id="355f3-313">[ICorDebugProcess2 Interface](icordebugprocess2-interface1.md)</span></span>\
 <span data-ttu-id="355f3-314">`ICorDebugProcess` の論理拡張機能です。</span><span class="sxs-lookup"><span data-stu-id="355f3-314">A logical extension of `ICorDebugProcess`.</span></span>  
  
 <span data-ttu-id="355f3-315">[インターフェイス](icordebugprocess3-interface.md)</span><span class="sxs-lookup"><span data-stu-id="355f3-315">[ICorDebugProcess3 Interface](icordebugprocess3-interface.md)</span></span>\
 <span data-ttu-id="355f3-316">カスタムのデバッガー通知を制御します。</span><span class="sxs-lookup"><span data-stu-id="355f3-316">Controls custom debugger notifications.</span></span>

 <span data-ttu-id="355f3-317">[インターフェイス](icordebugprocess4-interface.md)</span><span class="sxs-lookup"><span data-stu-id="355f3-317">[ICorDebugProcess4 Interface](icordebugprocess4-interface.md)</span></span>\
 <span data-ttu-id="355f3-318">プロセスの実行制御のサポートを提供します。</span><span class="sxs-lookup"><span data-stu-id="355f3-318">Provides support for out of process execution control.</span></span>
  
 <span data-ttu-id="355f3-319">[インターフェイス](icordebugprocess5-interface.md)</span><span class="sxs-lookup"><span data-stu-id="355f3-319">[ICorDebugProcess5 Interface](icordebugprocess5-interface.md)</span></span>\
 <span data-ttu-id="355f3-320">マネージ ヒープへのアクセスをサポートし、マネージ オブジェクトのガベージ コレクションに関する情報を提供し、デバッガーがアプリケーションのローカル ネイティブ イメージ キャッシュからイメージを読み込むかどうかを判断するために[、ICorDebugProcess](icordebugprocess-interface.md)インターフェイスを拡張します。</span><span class="sxs-lookup"><span data-stu-id="355f3-320">Extends the [ICorDebugProcess](icordebugprocess-interface.md) interface to support access to the managed heap, to provide information about garbage collection of managed objects, and to determine whether a debugger loads images from the application's local native image cache.</span></span>  
  
 <span data-ttu-id="355f3-321">[インターフェイス](icordebugprocess6-interface.md)</span><span class="sxs-lookup"><span data-stu-id="355f3-321">[ICorDebugProcess6 Interface](icordebugprocess6-interface.md)</span></span>\
 <span data-ttu-id="355f3-322">[ICorDebugProcess](icordebugprocess-interface.md)インターフェイスを論理的に拡張して、ネイティブ例外デバッグ イベントでエンコードされたマネージ デバッグ イベントのデコードや仮想モジュール分割などの機能を有効にします。</span><span class="sxs-lookup"><span data-stu-id="355f3-322">Logically extends the [ICorDebugProcess](icordebugprocess-interface.md) interface to enable features such as decoding managed debug events that are encoded in native exception debug events and virtual module splitting.</span></span> <span data-ttu-id="355f3-323">**.NET ネイティブのみで使用できます。**</span><span class="sxs-lookup"><span data-stu-id="355f3-323">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="355f3-324">[インターフェイス](icordebugprocess7-interface.md)</span><span class="sxs-lookup"><span data-stu-id="355f3-324">[ICorDebugProcess7 Interface](icordebugprocess7-interface.md)</span></span>\
 <span data-ttu-id="355f3-325">ターゲット プロセスでメモリ内のメタデータ更新を処理するようにデバッガーを構成するメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="355f3-325">Provides a method that configures the debugger to handle in-memory metadata updates in the target process.</span></span>  
  
 <span data-ttu-id="355f3-326">[インターフェイス](icordebugprocess8-interface.md)</span><span class="sxs-lookup"><span data-stu-id="355f3-326">[ICorDebugProcess8 Interface](icordebugprocess8-interface.md)</span></span>\
 <span data-ttu-id="355f3-327">特定の種類の[ICorDebugManagedCallback2](icordebugmanagedcallback2-interface.md)例外コールバックを有効または無効にするインターフェイスを論理的に拡張します。 [ICorDebugProcess](icordebugprocess-interface.md)</span><span class="sxs-lookup"><span data-stu-id="355f3-327">Logically extends the [ICorDebugProcess](icordebugprocess-interface.md) interface to enable or disable certain types of [ICorDebugManagedCallback2](icordebugmanagedcallback2-interface.md) exception callbacks.</span></span>  
  
 <span data-ttu-id="355f3-328">[インターフェイスを処理します。](icordebugprocessenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="355f3-328">[ICorDebugProcessEnum Interface](icordebugprocessenum-interface.md)</span></span>\
 <span data-ttu-id="355f3-329">`ICorDebugEnum` メソッドを実装し、`ICorDebugProcess` 配列を列挙します。</span><span class="sxs-lookup"><span data-stu-id="355f3-329">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugProcess` arrays.</span></span>  
  
 <span data-ttu-id="355f3-330">[インターフェイスを指定します。](icordebugreferencevalue-interface.md)</span><span class="sxs-lookup"><span data-stu-id="355f3-330">[ICorDebugReferenceValue Interface](icordebugreferencevalue-interface.md)</span></span>\
 <span data-ttu-id="355f3-331">参照型をサポートする `ICorDebugValue` のサブクラス。</span><span class="sxs-lookup"><span data-stu-id="355f3-331">A subclass of `ICorDebugValue` that supports reference types.</span></span>  
  
 <span data-ttu-id="355f3-332">[インターフェイスを設定します。](icordebugregisterset-interface.md)</span><span class="sxs-lookup"><span data-stu-id="355f3-332">[ICorDebugRegisterSet Interface](icordebugregisterset-interface.md)</span></span>\
 <span data-ttu-id="355f3-333">現在コードを実行しているマシン上で使用できるレジスタ セットを表します。</span><span class="sxs-lookup"><span data-stu-id="355f3-333">Represents the set of registers available on the machine that is currently executing code.</span></span>  
  
 <span data-ttu-id="355f3-334">[インターフェイス](icordebugregisterset2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="355f3-334">[ICorDebugRegisterSet2 Interface](icordebugregisterset2-interface.md)</span></span>\
 <span data-ttu-id="355f3-335">64 を超えるレジスタを持つハードウェア プラットフォーム用に `ICorDebugRegisterSet` の機能を拡張します。</span><span class="sxs-lookup"><span data-stu-id="355f3-335">Extends the capabilities of `ICorDebugRegisterSet` for hardware platforms that have more than 64 registers.</span></span>  
  
 <span data-ttu-id="355f3-336">[リモート インターフェイス](icordebugremote-interface.md)</span><span class="sxs-lookup"><span data-stu-id="355f3-336">[ICorDebugRemote Interface](icordebugremote-interface.md)</span></span>\
 <span data-ttu-id="355f3-337">リモート ターゲット プロセスに対してマネージド デバッガーを起動または接続する機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="355f3-337">Provides the ability to launch or attach a managed debugger to a remote target process.</span></span>  
  
 <span data-ttu-id="355f3-338">[インターフェイスをデバッグします。](icordebugremotetarget-interface.md)</span><span class="sxs-lookup"><span data-stu-id="355f3-338">[ICorDebugRemoteTarget Interface](icordebugremotetarget-interface.md)</span></span>\
 <span data-ttu-id="355f3-339">開発者が CLR 環境で Silverlight ベース アプリケーションをデバッグできるようにするメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="355f3-339">Provides methods that enable you to debug Silverlight-based applications in the CLR environment.</span></span>  
  
 <span data-ttu-id="355f3-340">[アンワインドブルフレームインターフェイス](icordebugruntimeunwindableframe-interface.md)</span><span class="sxs-lookup"><span data-stu-id="355f3-340">[ICorDebugRuntimeUnwindableFrame Interface](icordebugruntimeunwindableframe-interface.md)</span></span>\
 <span data-ttu-id="355f3-341">共通言語ランタイム (CLR: Common Language Runtime) でフレームをアンワインドする必要のあるアンマネージ メソッドに対してサポートを提供します。</span><span class="sxs-lookup"><span data-stu-id="355f3-341">Provides support for unmanaged methods that require the common language runtime (CLR) to unwind a frame.</span></span>  
  
 <span data-ttu-id="355f3-342">[インターフェイス](icordebugstackwalk-interface.md)</span><span class="sxs-lookup"><span data-stu-id="355f3-342">[ICorDebugStackWalk Interface](icordebugstackwalk-interface.md)</span></span>\
 <span data-ttu-id="355f3-343">スレッドのスタック上のマネージド メソッド (フレーム) を取得するメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="355f3-343">Provides methods for getting the managed methods, or frames, on a thread’s stack.</span></span>  
  
 <span data-ttu-id="355f3-344">[インターフェイスを呼び出します。](icordebugstaticfieldsymbol-interface.md)</span><span class="sxs-lookup"><span data-stu-id="355f3-344">[ICorDebugStaticFieldSymbol Interface](icordebugstaticfieldsymbol-interface.md)</span></span>\
 <span data-ttu-id="355f3-345">静的フィールドのデバッグ シンボル情報を表します。</span><span class="sxs-lookup"><span data-stu-id="355f3-345">Represents the debug symbol information for a static field.</span></span> <span data-ttu-id="355f3-346">**.NET ネイティブのみで使用できます。**</span><span class="sxs-lookup"><span data-stu-id="355f3-346">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="355f3-347">[インターフェイスをデバッグします。](icordebugstepper-interface.md)</span><span class="sxs-lookup"><span data-stu-id="355f3-347">[ICorDebugStepper Interface](icordebugstepper-interface.md)</span></span>\
 <span data-ttu-id="355f3-348">デバッガーが実行するコード実行内のステップを表します。コマンドの発行から完了までの間は識別子として機能します。これを使用するとステップをキャンセルできます。</span><span class="sxs-lookup"><span data-stu-id="355f3-348">Represents a step in code execution that is performed by a debugger, serves as an identifier between the issuance and completion of a command, and provides a way to cancel a step.</span></span>  
  
 <span data-ttu-id="355f3-349">[インターフェイス](icordebugstepper2-interface1.md)</span><span class="sxs-lookup"><span data-stu-id="355f3-349">[ICorDebugStepper2 Interface](icordebugstepper2-interface1.md)</span></span>\
 <span data-ttu-id="355f3-350">マイ コードのみ (JMC: Just My Code) デバッグのサポートを提供します。</span><span class="sxs-lookup"><span data-stu-id="355f3-350">Provides support for Just My Code (JMC) debugging.</span></span>  
  
 <span data-ttu-id="355f3-351">[インターフェイスをデバッグします。](icordebugstepperenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="355f3-351">[ICorDebugStepperEnum Interface](icordebugstepperenum-interface.md)</span></span>\
 <span data-ttu-id="355f3-352">`ICorDebugEnum` メソッドを実装し、`ICorDebugStepper` 配列を列挙します。</span><span class="sxs-lookup"><span data-stu-id="355f3-352">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugStepper` arrays.</span></span>  
  
 <span data-ttu-id="355f3-353">[インターフェイスを返します。](icordebugstringvalue-interface.md)</span><span class="sxs-lookup"><span data-stu-id="355f3-353">[ICorDebugStringValue Interface](icordebugstringvalue-interface.md)</span></span>\
 <span data-ttu-id="355f3-354">文字列値に適用する `ICorDebugHeapValue` のサブクラスです。</span><span class="sxs-lookup"><span data-stu-id="355f3-354">A subclass of `ICorDebugHeapValue` that applies to string values.</span></span>  
  
 <span data-ttu-id="355f3-355">[インターフェイスを指定します。](icordebugsymbolprovider-interface.md)</span><span class="sxs-lookup"><span data-stu-id="355f3-355">[ICorDebugSymbolProvider Interface](icordebugsymbolprovider-interface.md)</span></span>\
 <span data-ttu-id="355f3-356">デバッグ シンボル情報を取得するために使用できるメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="355f3-356">Provides methods that can be used to retrieve debug symbol information.</span></span> <span data-ttu-id="355f3-357">**.NET ネイティブのみで使用できます。**</span><span class="sxs-lookup"><span data-stu-id="355f3-357">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="355f3-358">[インターフェイス](icordebugsymbolprovider2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="355f3-358">[ICorDebugSymbolProvider2 Interface](icordebugsymbolprovider2-interface.md)</span></span>\
 <span data-ttu-id="355f3-359">[ICorDebugSymbolProvider](icordebugsymbolprovider-interface.md)インターフェイスを論理的に拡張して、追加のデバッグ シンボル情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="355f3-359">Logically extends the [ICorDebugSymbolProvider](icordebugsymbolprovider-interface.md) interface to retrieve additional debug symbol information.</span></span> <span data-ttu-id="355f3-360">**.NET ネイティブのみで使用できます。**</span><span class="sxs-lookup"><span data-stu-id="355f3-360">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="355f3-361">[インターフェイス](icordebugthread-interface.md)</span><span class="sxs-lookup"><span data-stu-id="355f3-361">[ICorDebugThread Interface](icordebugthread-interface.md)</span></span>\
 <span data-ttu-id="355f3-362">プロセス内のスレッドを表します。</span><span class="sxs-lookup"><span data-stu-id="355f3-362">Represents a thread in a process.</span></span> <span data-ttu-id="355f3-363">`ICorDebugThread` インスタンスの有効期間は、それが表しているスレッドの有効期間と同じです。</span><span class="sxs-lookup"><span data-stu-id="355f3-363">The lifetime of an `ICorDebugThread` instance is the same as the lifetime of the thread it represents.</span></span>  
  
 <span data-ttu-id="355f3-364">[インターフェイス](icordebugthread2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="355f3-364">[ICorDebugThread2 Interface](icordebugthread2-interface.md)</span></span>\
 <span data-ttu-id="355f3-365">`ICorDebugThread` の論理的な拡張機能として動作します。</span><span class="sxs-lookup"><span data-stu-id="355f3-365">Serves as a logical extension to `ICorDebugThread`.</span></span>  
  
 <span data-ttu-id="355f3-366">[インターフェイス](icordebugthread3-interface.md)</span><span class="sxs-lookup"><span data-stu-id="355f3-366">[ICorDebugThread3 Interface](icordebugthread3-interface.md)</span></span>\
 <span data-ttu-id="355f3-367">[エントリ](icordebugstackwalk-interface.md)ポイントを提供します。</span><span class="sxs-lookup"><span data-stu-id="355f3-367">Provides the entry point to the [ICorDebugStackWalk](icordebugstackwalk-interface.md) and corresponding interfaces.</span></span>  
  
 <span data-ttu-id="355f3-368">[インターフェイス](icordebugthread4-interface.md)</span><span class="sxs-lookup"><span data-stu-id="355f3-368">[ICorDebugThread4 Interface](icordebugthread4-interface.md)</span></span>\
 <span data-ttu-id="355f3-369">スレッドのブロック情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="355f3-369">Provides thread blocking information.</span></span>  
  
 <span data-ttu-id="355f3-370">[インターフェイス](icordebugthreadenum-interface1.md)</span><span class="sxs-lookup"><span data-stu-id="355f3-370">[ICorDebugThreadEnum Interface](icordebugthreadenum-interface1.md)</span></span>\
 <span data-ttu-id="355f3-371">`ICorDebugEnum` メソッドを実装し、`ICorDebugThread` 配列を列挙します。</span><span class="sxs-lookup"><span data-stu-id="355f3-371">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugThread` arrays.</span></span>  
  
 <span data-ttu-id="355f3-372">[インターフェイス](icordebugtype-interface.md)</span><span class="sxs-lookup"><span data-stu-id="355f3-372">[ICorDebugType Interface](icordebugtype-interface.md)</span></span>\
 <span data-ttu-id="355f3-373">基本型または複合型 (つまり、ユーザー定義) のいずれかの型を表します。</span><span class="sxs-lookup"><span data-stu-id="355f3-373">Represents a type, which can be either basic or complex (that is, user-defined).</span></span> <span data-ttu-id="355f3-374">型がジェネリックの場合、`ICorDebugType` はインスタンス化されたジェネリック型を表します。</span><span class="sxs-lookup"><span data-stu-id="355f3-374">If the type is generic, `ICorDebugType` represents the instantiated generic type.</span></span>  
  
 <span data-ttu-id="355f3-375">[インターフェイス](icordebugtype2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="355f3-375">[ICorDebugType2 Interface](icordebugtype2-interface.md)</span></span>\
 <span data-ttu-id="355f3-376">基本型または複合 (ユーザー定義) 型の型識別子を取得する[ICorDebugType](icordebugtype-interface.md)インターフェイスを拡張します。</span><span class="sxs-lookup"><span data-stu-id="355f3-376">Extends the [ICorDebugType](icordebugtype-interface.md) interface to retrieve the type identifier  of a base type or complex (user-defined) type.</span></span>  
  
 <span data-ttu-id="355f3-377">[インターフェイス](icordebugtypeenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="355f3-377">[ICorDebugTypeEnum Interface](icordebugtypeenum-interface.md)</span></span>\
 <span data-ttu-id="355f3-378">`ICorDebugEnum` メソッドを実装し、`ICorDebugType` 配列を列挙します。</span><span class="sxs-lookup"><span data-stu-id="355f3-378">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugType` arrays.</span></span>  
  
 <span data-ttu-id="355f3-379">[インターフェイスをデバッグします。](icordebugunmanagedcallback-interface.md)</span><span class="sxs-lookup"><span data-stu-id="355f3-379">[ICorDebugUnmanagedCallback Interface](icordebugunmanagedcallback-interface.md)</span></span>\
 <span data-ttu-id="355f3-380">CLR に直接関連していないネイティブ イベントについて通知します。</span><span class="sxs-lookup"><span data-stu-id="355f3-380">Provides notification of native events that are not directly related to the CLR.</span></span>  
  
 <span data-ttu-id="355f3-381">[を指定します。](icordebugvalue-interface.md)</span><span class="sxs-lookup"><span data-stu-id="355f3-381">[ICorDebugValue](icordebugvalue-interface.md)</span></span>\
 <span data-ttu-id="355f3-382">デバッグ中のプロセス内の読み取り値または書き込み値を表します。</span><span class="sxs-lookup"><span data-stu-id="355f3-382">Represents a read or write value in the process being debugged.</span></span>  
  
 <span data-ttu-id="355f3-383">[2](icordebugvalue2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="355f3-383">[ICorDebugValue2](icordebugvalue2-interface.md)</span></span>\
 <span data-ttu-id="355f3-384">`ICorDebugValue` をサポートできるように `ICorDebugType` を拡張します。</span><span class="sxs-lookup"><span data-stu-id="355f3-384">Extends `ICorDebugValue` to provide support for `ICorDebugType`.</span></span>  
  
 <span data-ttu-id="355f3-385">[インターフェイス](icordebugvalue3-interface.md)</span><span class="sxs-lookup"><span data-stu-id="355f3-385">[ICorDebugValue3 Interface](icordebugvalue3-interface.md)</span></span>\
 <span data-ttu-id="355f3-386">2 GB を超える配列をサポートするために、"ICorDebugValue" インターフェイスと "ICorDebugValue2" インターフェイスを拡張します。</span><span class="sxs-lookup"><span data-stu-id="355f3-386">Extends the "ICorDebugValue" and "ICorDebugValue2" interfaces to provide support for arrays that are larger than 2 GB.</span></span>  
  
 <span data-ttu-id="355f3-387">[値ブレークポイントを指定します。](icordebugvaluebreakpoint-interface.md)</span><span class="sxs-lookup"><span data-stu-id="355f3-387">[ICorDebugValueBreakpoint](icordebugvaluebreakpoint-interface.md)</span></span>\
 <span data-ttu-id="355f3-388">特定の値にアクセスできるように `ICorDebugBreakpoint` を拡張します。</span><span class="sxs-lookup"><span data-stu-id="355f3-388">Extends `ICorDebugBreakpoint` to provide access to specific values.</span></span>  
  
 <span data-ttu-id="355f3-389">[を返します。](icordebugvalueenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="355f3-389">[ICorDebugValueEnum](icordebugvalueenum-interface.md)</span></span>\
 <span data-ttu-id="355f3-390">`ICorDebugEnum` メソッドを実装し、`ICorDebugValue` 配列を列挙します。</span><span class="sxs-lookup"><span data-stu-id="355f3-390">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugValue` arrays.</span></span>  
  
 <span data-ttu-id="355f3-391">[インターフェイスを変更します。](icordebugvariablehome-interface.md)</span><span class="sxs-lookup"><span data-stu-id="355f3-391">[ICorDebugVariableHome Interface](icordebugvariablehome-interface.md)</span></span>\
 <span data-ttu-id="355f3-392">関数のローカル変数または引数を表します。</span><span class="sxs-lookup"><span data-stu-id="355f3-392">Represents a local variable or argument of a function.</span></span>  
  
 <span data-ttu-id="355f3-393">[インターフェイスを変数として使用します。](icordebugvariablehomeenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="355f3-393">[ICorDebugVariableHomeEnum Interface](icordebugvariablehomeenum-interface.md)</span></span>\
 <span data-ttu-id="355f3-394">関数のローカル変数と引数に列挙子を提供します。</span><span class="sxs-lookup"><span data-stu-id="355f3-394">Provides an enumerator to the local variables and arguments in a function.</span></span>  
  
 <span data-ttu-id="355f3-395">[インターフェイスを使用します。](icordebugvariablesymbol-interface.md)</span><span class="sxs-lookup"><span data-stu-id="355f3-395">[ICorDebugVariableSymbol Interface](icordebugvariablesymbol-interface.md)</span></span>\
 <span data-ttu-id="355f3-396">変数のデバッグ シンボル情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="355f3-396">Retrieves the debug symbol information for a variable.</span></span> <span data-ttu-id="355f3-397">**.NET ネイティブのみで使用できます。**</span><span class="sxs-lookup"><span data-stu-id="355f3-397">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="355f3-398">[インターフェイス](icordebugvirtualunwinder-interface.md)</span><span class="sxs-lookup"><span data-stu-id="355f3-398">[ICorDebugVirtualUnwinder Interface](icordebugvirtualunwinder-interface.md)</span></span>\
 <span data-ttu-id="355f3-399">スタック アンワインドを支援するメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="355f3-399">Provides methods to help in stack unwinding.</span></span> <span data-ttu-id="355f3-400">**.NET ネイティブのみで使用できます。**</span><span class="sxs-lookup"><span data-stu-id="355f3-400">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="355f3-401">[ICorパブリッシュインターフェイス](icorpublish-interface.md)</span><span class="sxs-lookup"><span data-stu-id="355f3-401">[ICorPublish Interface](icorpublish-interface.md)</span></span>\
 <span data-ttu-id="355f3-402">発行プロセスの汎用インターフェイスとして機能します。</span><span class="sxs-lookup"><span data-stu-id="355f3-402">Serves as the general interface for the publishing processes.</span></span>  
  
 <span data-ttu-id="355f3-403">[インターフェイス](icorpublishappdomain-interface.md)</span><span class="sxs-lookup"><span data-stu-id="355f3-403">[ICorPublishAppDomain Interface](icorpublishappdomain-interface.md)</span></span>\
 <span data-ttu-id="355f3-404">アプリケーション ドメインの情報を表し、提供します。</span><span class="sxs-lookup"><span data-stu-id="355f3-404">Represents and provides information about an application domain.</span></span>  
  
 <span data-ttu-id="355f3-405">[インターフェイスを発行します。](icorpublishappdomainenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="355f3-405">[ICorPublishAppDomainEnum Interface](icorpublishappdomainenum-interface.md)</span></span>\
 <span data-ttu-id="355f3-406">現在プロセス内に存在する `ICorPublishAppDomain` オブジェクトのコレクションを走査するメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="355f3-406">Provides methods that traverse a collection of `ICorPublishAppDomain` objects that currently exist within a process.</span></span>  
  
 <span data-ttu-id="355f3-407">[インターフェイス](icorpublishenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="355f3-407">[ICorPublishEnum Interface](icorpublishenum-interface.md)</span></span>\
 <span data-ttu-id="355f3-408">発行する列挙子の抽象ベースとして機能します。</span><span class="sxs-lookup"><span data-stu-id="355f3-408">Serves as the abstract base for publishing enumerators.</span></span>  
  
 <span data-ttu-id="355f3-409">[インターフェイスを発行します。](icorpublishprocess-interface.md)</span><span class="sxs-lookup"><span data-stu-id="355f3-409">[ICorPublishProcess Interface](icorpublishprocess-interface.md)</span></span>\
 <span data-ttu-id="355f3-410">プロセスの情報にアクセスするメソッドを適用します。</span><span class="sxs-lookup"><span data-stu-id="355f3-410">Provides methods that access information about a process.</span></span>  
  
 <span data-ttu-id="355f3-411">[インターフェイスを発行します。](icorpublishprocessenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="355f3-411">[ICorPublishProcessEnum Interface](icorpublishprocessenum-interface.md)</span></span>\
 <span data-ttu-id="355f3-412">`ICorPublishProcess` オブジェクトのコレクションを走査するメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="355f3-412">Provides methods that traverse a collection of `ICorPublishProcess` objects.</span></span>  

 <span data-ttu-id="355f3-413">[インターフェイス](isosdacinterface-interface.md)</span><span class="sxs-lookup"><span data-stu-id="355f3-413">[ISOSDacInterface Interface](isosdacinterface-interface.md)</span></span>\
 <span data-ttu-id="355f3-414">から`SOS`データにアクセスするためのヘルパー メソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="355f3-414">Provides helper methods to access data from `SOS`.</span></span>

 <span data-ttu-id="355f3-415">[インターフェイスを定義します。](ixclrdatamethoddefinition-interface.md)</span><span class="sxs-lookup"><span data-stu-id="355f3-415">[IXCLRDataMethodDefinition Interface](ixclrdatamethoddefinition-interface.md)</span></span>\
 <span data-ttu-id="355f3-416">メソッド定義に関する情報を照会するためのメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="355f3-416">Provides methods for querying information about a method definition.</span></span>

 <span data-ttu-id="355f3-417">[インターフェイス](ixclrdatamethodinstance-interface.md)</span><span class="sxs-lookup"><span data-stu-id="355f3-417">[IXCLRDataMethodInstance Interface](ixclrdatamethodinstance-interface.md)</span></span>\
 <span data-ttu-id="355f3-418">メソッド インスタンスに関する情報を照会するためのメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="355f3-418">Provides methods for querying information about a method instance.</span></span>

 <span data-ttu-id="355f3-419">[インターフェイス](ixclrdatamodule-interface.md)</span><span class="sxs-lookup"><span data-stu-id="355f3-419">[IXCLRDataModule Interface](ixclrdatamodule-interface.md)</span></span>\
 <span data-ttu-id="355f3-420">読み込まれたモジュールに関する情報を照会するためのメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="355f3-420">Provides methods for querying information about a loaded module.</span></span>

 <span data-ttu-id="355f3-421">[インターフェイス](ixclrdataprocess-interface.md)</span><span class="sxs-lookup"><span data-stu-id="355f3-421">[IXCLRDataProcess Interface](ixclrdataprocess-interface.md)</span></span>\
 <span data-ttu-id="355f3-422">プロセスに関する情報を照会するためのメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="355f3-422">Provides methods for querying information about a process.</span></span>
  
## <a name="related-sections"></a><span data-ttu-id="355f3-423">関連項目</span><span class="sxs-lookup"><span data-stu-id="355f3-423">Related Sections</span></span>  
 <span data-ttu-id="355f3-424">[コクラスのデバッグ](debugging-coclasses.md)</span><span class="sxs-lookup"><span data-stu-id="355f3-424">[Debugging Coclasses](debugging-coclasses.md)</span></span>\
 <span data-ttu-id="355f3-425">[グローバル静的関数のデバッグ](debugging-global-static-functions.md)</span><span class="sxs-lookup"><span data-stu-id="355f3-425">[Debugging Global Static Functions](debugging-global-static-functions.md)</span></span>\
 <span data-ttu-id="355f3-426">[列挙体のデバッグ](debugging-enumerations.md)</span><span class="sxs-lookup"><span data-stu-id="355f3-426">[Debugging Enumerations](debugging-enumerations.md)</span></span>\
 <span data-ttu-id="355f3-427">[構造体のデバッグ](debugging-structures.md)</span><span class="sxs-lookup"><span data-stu-id="355f3-427">[Debugging Structures](debugging-structures.md)</span></span>\
