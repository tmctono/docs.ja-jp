---
title: デバッグ構造体
ms.date: 03/30/2017
helpviewer_keywords:
- unmanaged structures [.NET Framework], debugging
- debugging structures [.NET Framework]
- structures [.NET Framework debugging]
ms.assetid: 173ba2c2-ab34-49ae-b6a8-e5c49882bf05
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f50db519410b9513725c3dc10637421ba8bb37ec
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61698363"
---
# <a name="debugging-structures"></a><span data-ttu-id="451f8-102">デバッグ構造体</span><span class="sxs-lookup"><span data-stu-id="451f8-102">Debugging Structures</span></span>

<span data-ttu-id="451f8-103">このセクションでは、デバッグ API が使用するアンマネージ構造体について説明します。</span><span class="sxs-lookup"><span data-stu-id="451f8-103">This section describes the unmanaged structures that the debugging API uses.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="451f8-104">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="451f8-104">In This Section</span></span>
 <span data-ttu-id="451f8-105">[CLRDATA_ADDRESS_RANGE 構造](../../../../docs/framework/unmanaged-api/debugging/clrdata-address-range-structure.md)アドレスの範囲を定義します。</span><span class="sxs-lookup"><span data-stu-id="451f8-105">[CLRDATA_ADDRESS_RANGE Structure](../../../../docs/framework/unmanaged-api/debugging/clrdata-address-range-structure.md) Defines an address range.</span></span>

 <span data-ttu-id="451f8-106">[CLRDATA_IL_ADDRESS_MAP 構造](../../../../docs/framework/unmanaged-api/debugging/clrdata-il-address-map-structure.md)アドレスへのマッピングから、IL を定義します。</span><span class="sxs-lookup"><span data-stu-id="451f8-106">[CLRDATA_IL_ADDRESS_MAP Structure](../../../../docs/framework/unmanaged-api/debugging/clrdata-il-address-map-structure.md) Defines an IL to address mapping</span></span>

 <span data-ttu-id="451f8-107">[CLR_DEBUGGING_VERSION 構造体](../../../../docs/framework/unmanaged-api/debugging/clr-debugging-version-structure.md)デバッグのための共通言語ランタイム (CLR) の製品バージョンを定義します。</span><span class="sxs-lookup"><span data-stu-id="451f8-107">[CLR_DEBUGGING_VERSION Structure](../../../../docs/framework/unmanaged-api/debugging/clr-debugging-version-structure.md) Defines the product version of the common language runtime (CLR) for debugging purposes.</span></span>

 <span data-ttu-id="451f8-108">[CodeChunkInfo 構造体](../../../../docs/framework/unmanaged-api/debugging/codechunkinfo-structure.md)メモリ内のコードの 1 つのチャンクを表します。</span><span class="sxs-lookup"><span data-stu-id="451f8-108">[CodeChunkInfo Structure](../../../../docs/framework/unmanaged-api/debugging/codechunkinfo-structure.md) Represents a single chunk of code in memory.</span></span>

 <span data-ttu-id="451f8-109">[COR_ACTIVE_FUNCTION](cor-active-function-structure.md)スレッドのフレームで現在アクティブな関数についての情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="451f8-109">[COR_ACTIVE_FUNCTION](cor-active-function-structure.md) Contains information about the functions that are currently active in a thread's frames.</span></span>

 <span data-ttu-id="451f8-110">[COR_ARRAY_LAYOUT 構造体](../../../../docs/framework/unmanaged-api/debugging/cor-array-layout-structure.md)メモリ内配列オブジェクトのレイアウトに関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="451f8-110">[COR_ARRAY_LAYOUT Structure](../../../../docs/framework/unmanaged-api/debugging/cor-array-layout-structure.md) Provides information about the layout of an array object in memory.</span></span>

 <span data-ttu-id="451f8-111">[COR_DEBUG_IL_TO_NATIVE_MAP](cor-debug-il-to-native-map-structure.md) Microsoft intermediate language (MSIL) にマップするために使用されるオフセットがネイティブ コードにコードが含まれます。</span><span class="sxs-lookup"><span data-stu-id="451f8-111">[COR_DEBUG_IL_TO_NATIVE_MAP](cor-debug-il-to-native-map-structure.md) Contains the offsets that are used to map Microsoft intermediate language (MSIL) code to native code.</span></span>

 <span data-ttu-id="451f8-112">[COR_DEBUG_STEP_RANGE](cor-debug-step-range-structure.md)コードの範囲に関するオフセット情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="451f8-112">[COR_DEBUG_STEP_RANGE](cor-debug-step-range-structure.md) Contains the offset information for a range of code.</span></span>

 <span data-ttu-id="451f8-113">[COR_FIELD 構造体](../../../../docs/framework/unmanaged-api/debugging/cor-field-structure.md)オブジェクトのフィールドに関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="451f8-113">[COR_FIELD Structure](../../../../docs/framework/unmanaged-api/debugging/cor-field-structure.md) Provides information about a field in an object.</span></span>

 <span data-ttu-id="451f8-114">[COR_GC_REFERENCE 構造体](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md)ガベージ コレクトされるオブジェクトに関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="451f8-114">[COR_GC_REFERENCE Structure](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) Contains information about an object that is to be garbage-collected.</span></span>

 <span data-ttu-id="451f8-115">[COR_HEAPINFO 構造体](../../../../docs/framework/unmanaged-api/debugging/cor-heapinfo-structure.md)列挙可能かどうかなど、ガベージ コレクション ヒープに関する全般情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="451f8-115">[COR_HEAPINFO Structure](../../../../docs/framework/unmanaged-api/debugging/cor-heapinfo-structure.md) Provides general information about the garbage collection heap, including whether it is enumerable.</span></span>

 <span data-ttu-id="451f8-116">[COR_HEAPOBJECT 構造体](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md)マネージ ヒープのオブジェクトに関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="451f8-116">[COR_HEAPOBJECT Structure](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) Provides information about an object on the managed heap.</span></span>

 <span data-ttu-id="451f8-117">[COR_IL_MAP](cor-il-map-structure.md)関数の相対的なオフセットの変更を指定します。</span><span class="sxs-lookup"><span data-stu-id="451f8-117">[COR_IL_MAP](cor-il-map-structure.md) Specifies changes in the relative offset of a function.</span></span>

 <span data-ttu-id="451f8-118">[COR_SEGMENT 構造体](../../../../docs/framework/unmanaged-api/debugging/cor-segment-structure.md)マネージ ヒープのメモリの領域に関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="451f8-118">[COR_SEGMENT Structure](../../../../docs/framework/unmanaged-api/debugging/cor-segment-structure.md) Contains information about a region of memory in the managed heap.</span></span>

 <span data-ttu-id="451f8-119">[COR_TYPEID 構造体](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md)型識別子が含まれています。</span><span class="sxs-lookup"><span data-stu-id="451f8-119">[COR_TYPEID Structure](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) Contains a type identifier.</span></span>

 <span data-ttu-id="451f8-120">[COR_TYPE_LAYOUT 構造体](../../../../docs/framework/unmanaged-api/debugging/cor-type-layout-structure.md)メモリ内のオブジェクトのレイアウトに関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="451f8-120">[COR_TYPE_LAYOUT Structure](../../../../docs/framework/unmanaged-api/debugging/cor-type-layout-structure.md) Provides information about the layout of an object in memory.</span></span>

 <span data-ttu-id="451f8-121">[COR_VERSION](cor-version-structure.md)共通言語ランタイムの標準的な 4 部構成のバージョン番号を格納します。</span><span class="sxs-lookup"><span data-stu-id="451f8-121">[COR_VERSION](cor-version-structure.md) Stores the standard four-part version number of the common language runtime.</span></span>

 <span data-ttu-id="451f8-122">[CorDebugBlockingObject 構造体](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md)スレッドとスレッドがブロックされている理由の理由をブロックしているオブジェクトを定義します。</span><span class="sxs-lookup"><span data-stu-id="451f8-122">[CorDebugBlockingObject Structure](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) Defines an object that is blocking a thread and the reason why the thread is blocked.</span></span>

 <span data-ttu-id="451f8-123">[CorDebugEHClause 構造体](../../../../docs/framework/unmanaged-api/debugging/cordebugehclause-structure.md)の中間言語 (IL) の特定の例外処理 (EH) 句を表します。</span><span class="sxs-lookup"><span data-stu-id="451f8-123">[CorDebugEHClause Structure](../../../../docs/framework/unmanaged-api/debugging/cordebugehclause-structure.md) Represents an exception handling (EH) clause for a given piece of intermediate language (IL).</span></span>

 <span data-ttu-id="451f8-124">[CorDebugExceptionObjectStackFrame 構造体](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionobjectstackframe-structure.md)表しますスタック フレームの情報を例外オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="451f8-124">[CorDebugExceptionObjectStackFrame Structure](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionobjectstackframe-structure.md) Represents stack frame information from an exception object.</span></span>

 <span data-ttu-id="451f8-125">[CorDebugGuidToTypeMapping 構造体](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md)マップ、[!INCLUDE[wrt](../../../../includes/wrt-md.md)]を対応する GUID [ICorDebugType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-interface.md)オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="451f8-125">[CorDebugGuidToTypeMapping Structure](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) Maps a [!INCLUDE[wrt](../../../../includes/wrt-md.md)] GUID to its corresponding [ICorDebugType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-interface.md) object.</span></span>

 <span data-ttu-id="451f8-126">[DacpGetModuleAddress 構造](../../../../docs/framework/unmanaged-api/debugging/dacpgetmoduleaddress-structure.md)モジュール アドレス要求のコンテナーを定義します。</span><span class="sxs-lookup"><span data-stu-id="451f8-126">[DacpGetModuleAddress Structure](../../../../docs/framework/unmanaged-api/debugging/dacpgetmoduleaddress-structure.md) Defines the container for a module address request.</span></span>

 <span data-ttu-id="451f8-127">[DacpMethodDescData 構造](../../../../docs/framework/unmanaged-api/debugging/dacpmethoddescdata-structure.md)トランスポートのバッファーをメソッドのランタイム情報を定義します。</span><span class="sxs-lookup"><span data-stu-id="451f8-127">[DacpMethodDescData Structure](../../../../docs/framework/unmanaged-api/debugging/dacpmethoddescdata-structure.md) Defines a transport buffer for a method's runtime information.</span></span>

 <span data-ttu-id="451f8-128">[DacpModuleData 構造](../../../../docs/framework/unmanaged-api/debugging/dacpmoduledata-structure.md)トランスポートのバッファーをモジュールのランタイム情報を定義します。</span><span class="sxs-lookup"><span data-stu-id="451f8-128">[DacpModuleData Structure](../../../../docs/framework/unmanaged-api/debugging/dacpmoduledata-structure.md) Defines a transport buffer for a module's runtime information.</span></span>

 <span data-ttu-id="451f8-129">[DacpReJitData 構造](../../../../docs/framework/unmanaged-api/debugging/dacprejitdata-structure.md)プロファイラー インストルメント メソッドに関する基本情報を定義します。</span><span class="sxs-lookup"><span data-stu-id="451f8-129">[DacpReJitData Structure](../../../../docs/framework/unmanaged-api/debugging/dacprejitdata-structure.md) Defines the basic information about a given profiler-instrumented method.</span></span>

 <span data-ttu-id="451f8-130">[StackTrace_SimpleContext 構造体](../../../../docs/framework/unmanaged-api/debugging/stacktrace-simplecontext-structure.md)フルの代わりに使用できる単純なコンテキスト`CONTEXT`構造体。</span><span class="sxs-lookup"><span data-stu-id="451f8-130">[StackTrace_SimpleContext Structure](../../../../docs/framework/unmanaged-api/debugging/stacktrace-simplecontext-structure.md) Provides a simple context that can be used in place of a full `CONTEXT` structure.</span></span>

## <a name="related-sections"></a><span data-ttu-id="451f8-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="451f8-131">Related Sections</span></span>

 [<span data-ttu-id="451f8-132">デバッグ コクラス</span><span class="sxs-lookup"><span data-stu-id="451f8-132">Debugging Coclasses</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-coclasses.md)

 [<span data-ttu-id="451f8-133">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="451f8-133">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)

 [<span data-ttu-id="451f8-134">デバッグ グローバル静的関数</span><span class="sxs-lookup"><span data-stu-id="451f8-134">Debugging Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-global-static-functions.md)

 [<span data-ttu-id="451f8-135">列挙型のデバッグ</span><span class="sxs-lookup"><span data-stu-id="451f8-135">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)

 [<span data-ttu-id="451f8-136">デバッグ</span><span class="sxs-lookup"><span data-stu-id="451f8-136">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
