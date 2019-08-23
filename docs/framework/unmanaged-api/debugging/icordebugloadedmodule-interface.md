---
title: ICorDebugLoadedModule インターフェイス
ms.date: 03/30/2017
ms.assetid: 34be6369-2e75-4a95-a538-3b29ac97cf6d
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a9da6aba61382381fc25fe70615976cd0e744ee1
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69910002"
---
# <a name="icordebugloadedmodule-interface"></a><span data-ttu-id="dc76c-102">ICorDebugLoadedModule インターフェイス</span><span class="sxs-lookup"><span data-stu-id="dc76c-102">ICorDebugLoadedModule Interface</span></span>
<span data-ttu-id="dc76c-103">読み込まれたモジュールについての情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="dc76c-103">Provides information about a loaded module.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="dc76c-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="dc76c-104">Methods</span></span>  
  
|<span data-ttu-id="dc76c-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="dc76c-105">Method</span></span>|<span data-ttu-id="dc76c-106">説明</span><span class="sxs-lookup"><span data-stu-id="dc76c-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="dc76c-107">GetBaseAddress メソッド</span><span class="sxs-lookup"><span data-stu-id="dc76c-107">GetBaseAddress Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugloadedmodule-getbaseaddress-method.md)|<span data-ttu-id="dc76c-108">読み込まれたモジュールのベース アドレスを取得します。</span><span class="sxs-lookup"><span data-stu-id="dc76c-108">Gets the base address of the loaded module.</span></span>|  
|[<span data-ttu-id="dc76c-109">GetName メソッド</span><span class="sxs-lookup"><span data-stu-id="dc76c-109">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugloadedmodule-getname-method.md)|<span data-ttu-id="dc76c-110">読み込まれたモジュールの名前を取得します。</span><span class="sxs-lookup"><span data-stu-id="dc76c-110">Gets the name of the loaded module.</span></span>|  
|[<span data-ttu-id="dc76c-111">GetSize メソッド</span><span class="sxs-lookup"><span data-stu-id="dc76c-111">GetSize Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugloadedmodule-getsize-method.md)|<span data-ttu-id="dc76c-112">読み込まれたモジュールのサイズ (バイト単位) を取得します。</span><span class="sxs-lookup"><span data-stu-id="dc76c-112">Gets the size in bytes of the loaded module.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dc76c-113">Remarks</span><span class="sxs-lookup"><span data-stu-id="dc76c-113">Remarks</span></span>  
 <span data-ttu-id="dc76c-114">`ICorDebugLoadedModule` インターフェイスはデバッガーによって実装され、CLR デバッグ インターフェイスが、デバッガーから読み込まれたモジュールに関する情報を取得するために使用します。</span><span class="sxs-lookup"><span data-stu-id="dc76c-114">The `ICorDebugLoadedModule` interface is implemented by a debugger and is used by the CLR debugging interfaces to get information about the loaded module from the debugger.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="dc76c-115">このインターフェイスは .NET ネイティブでのみ使用可能です。</span><span class="sxs-lookup"><span data-stu-id="dc76c-115">This interface is available with .NET Native only.</span></span> <span data-ttu-id="dc76c-116">.NET ネイティブの外部で ICorDebug シナリオについてこのインターフェイスを実装する場合は、共通言語ランタイムはこのインターフェイスを無視します。</span><span class="sxs-lookup"><span data-stu-id="dc76c-116">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dc76c-117">必要条件</span><span class="sxs-lookup"><span data-stu-id="dc76c-117">Requirements</span></span>  
 <span data-ttu-id="dc76c-118">**・** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="dc76c-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dc76c-119">**ヘッダー:** CorDebug .idl、CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="dc76c-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="dc76c-120">**ライブラリ**CorGuids .lib</span><span class="sxs-lookup"><span data-stu-id="dc76c-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dc76c-121">**.NET Framework のバージョン:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dc76c-121">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc76c-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="dc76c-122">See also</span></span>

- [<span data-ttu-id="dc76c-123">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="dc76c-123">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="dc76c-124">デバッグ</span><span class="sxs-lookup"><span data-stu-id="dc76c-124">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
