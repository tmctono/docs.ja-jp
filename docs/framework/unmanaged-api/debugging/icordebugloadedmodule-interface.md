---
title: ICorDebugLoadedModule インターフェイス
ms.date: 03/30/2017
ms.assetid: 34be6369-2e75-4a95-a538-3b29ac97cf6d
ms.openlocfilehash: 9d3bdcec9e90dab337b595294d114de4bd3d531f
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76781998"
---
# <a name="icordebugloadedmodule-interface"></a><span data-ttu-id="caf0e-102">ICorDebugLoadedModule インターフェイス</span><span class="sxs-lookup"><span data-stu-id="caf0e-102">ICorDebugLoadedModule Interface</span></span>
<span data-ttu-id="caf0e-103">読み込まれたモジュールについての情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="caf0e-103">Provides information about a loaded module.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="caf0e-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="caf0e-104">Methods</span></span>  
  
|<span data-ttu-id="caf0e-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="caf0e-105">Method</span></span>|<span data-ttu-id="caf0e-106">説明</span><span class="sxs-lookup"><span data-stu-id="caf0e-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="caf0e-107">GetBaseAddress メソッド</span><span class="sxs-lookup"><span data-stu-id="caf0e-107">GetBaseAddress Method</span></span>](icordebugloadedmodule-getbaseaddress-method.md)|<span data-ttu-id="caf0e-108">読み込まれたモジュールのベース アドレスを取得します。</span><span class="sxs-lookup"><span data-stu-id="caf0e-108">Gets the base address of the loaded module.</span></span>|  
|[<span data-ttu-id="caf0e-109">GetName メソッド</span><span class="sxs-lookup"><span data-stu-id="caf0e-109">GetName Method</span></span>](icordebugloadedmodule-getname-method.md)|<span data-ttu-id="caf0e-110">読み込まれたモジュールの名前を取得します。</span><span class="sxs-lookup"><span data-stu-id="caf0e-110">Gets the name of the loaded module.</span></span>|  
|[<span data-ttu-id="caf0e-111">GetSize メソッド</span><span class="sxs-lookup"><span data-stu-id="caf0e-111">GetSize Method</span></span>](icordebugloadedmodule-getsize-method.md)|<span data-ttu-id="caf0e-112">読み込まれたモジュールのサイズ (バイト単位) を取得します。</span><span class="sxs-lookup"><span data-stu-id="caf0e-112">Gets the size in bytes of the loaded module.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="caf0e-113">コメント</span><span class="sxs-lookup"><span data-stu-id="caf0e-113">Remarks</span></span>  
 <span data-ttu-id="caf0e-114">`ICorDebugLoadedModule` インターフェイスはデバッガーによって実装され、CLR デバッグ インターフェイスが、デバッガーから読み込まれたモジュールに関する情報を取得するために使用します。</span><span class="sxs-lookup"><span data-stu-id="caf0e-114">The `ICorDebugLoadedModule` interface is implemented by a debugger and is used by the CLR debugging interfaces to get information about the loaded module from the debugger.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="caf0e-115">このインターフェイスは .NET ネイティブでのみ使用可能です。</span><span class="sxs-lookup"><span data-stu-id="caf0e-115">This interface is available with .NET Native only.</span></span> <span data-ttu-id="caf0e-116">.NET ネイティブの外部で ICorDebug シナリオについてこのインターフェイスを実装する場合は、共通言語ランタイムはこのインターフェイスを無視します。</span><span class="sxs-lookup"><span data-stu-id="caf0e-116">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="caf0e-117">要件</span><span class="sxs-lookup"><span data-stu-id="caf0e-117">Requirements</span></span>  
 <span data-ttu-id="caf0e-118">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="caf0e-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="caf0e-119">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="caf0e-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="caf0e-120">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="caf0e-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="caf0e-121">**.NET Framework のバージョン:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="caf0e-121">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="caf0e-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="caf0e-122">See also</span></span>

- [<span data-ttu-id="caf0e-123">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="caf0e-123">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="caf0e-124">デバッグ</span><span class="sxs-lookup"><span data-stu-id="caf0e-124">Debugging</span></span>](index.md)
