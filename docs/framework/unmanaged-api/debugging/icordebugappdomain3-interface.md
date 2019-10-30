---
title: ICorDebugAppDomain3 インターフェイス
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain3
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain3
helpviewer_keywords:
- ICorDebugAppDomain3 interface [.NET Framework debugging]
ms.assetid: 875ef5be-c1e7-4d95-97e9-d3a667aeaba0
topic_type:
- apiref
ms.openlocfilehash: 0b238a953fa5cd57c8b7af9a0643bfc36ee1032e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73088859"
---
# <a name="icordebugappdomain3-interface"></a><span data-ttu-id="5e92f-102">ICorDebugAppDomain3 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="5e92f-102">ICorDebugAppDomain3 Interface</span></span>
<span data-ttu-id="5e92f-103">アプリケーションドメインに現在読み込まれている Windows ランタイム型のマネージ表現に関する情報を取得するメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="5e92f-103">Provides methods to retrieve information about the managed representations of Windows Runtime types currently loaded in an application domain.</span></span> <span data-ttu-id="5e92f-104">このインターフェイスは、"ICorDebugAppDomain2" というインターフェイスを拡張したものです。</span><span class="sxs-lookup"><span data-stu-id="5e92f-104">This interface is an extension of the ICorDebugAppDomain and ICorDebugAppDomain2 interfaces.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="5e92f-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="5e92f-105">Methods</span></span>  
  
|<span data-ttu-id="5e92f-106">メソッド</span><span class="sxs-lookup"><span data-stu-id="5e92f-106">Method</span></span>|<span data-ttu-id="5e92f-107">説明</span><span class="sxs-lookup"><span data-stu-id="5e92f-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5e92f-108">ICorDebugAppDomain3:: GetCachedWinRTTypes</span><span class="sxs-lookup"><span data-stu-id="5e92f-108">ICorDebugAppDomain3::GetCachedWinRTTypes</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-getcachedwinrttypes-method.md)|<span data-ttu-id="5e92f-109">キャッシュされているすべての Windows ランタイム型の列挙子を取得します。</span><span class="sxs-lookup"><span data-stu-id="5e92f-109">Gets an enumerator for all cached Windows Runtime types.</span></span>|  
|[<span data-ttu-id="5e92f-110">ICorDebugAppDomain3:: GetCachedWinRTTypesForIIDs</span><span class="sxs-lookup"><span data-stu-id="5e92f-110">ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-getcachedwinrttypesforiids-method.md)|<span data-ttu-id="5e92f-111">インターフェイス識別子に基づいて、アプリケーションドメイン内のキャッシュされた Windows ランタイム型の列挙子を取得します。</span><span class="sxs-lookup"><span data-stu-id="5e92f-111">Gets an enumerator for cached Windows Runtime types in an application domain based on their interface identifiers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5e92f-112">Remarks</span><span class="sxs-lookup"><span data-stu-id="5e92f-112">Remarks</span></span>  
 <span data-ttu-id="5e92f-113">このインターフェイスは、デバッガーが `M:System.Runtime.InteropServices.Marshal.GetInspectableIIDs(System.Object)`に対する関数評価呼び出しと共に使用することを意図しています。</span><span class="sxs-lookup"><span data-stu-id="5e92f-113">This interface is meant to be used by a debugger in conjunction with a function evaluation call to `M:System.Runtime.InteropServices.Marshal.GetInspectableIIDs(System.Object)`.</span></span> <span data-ttu-id="5e92f-114">メソッドが Windows ランタイムサーバーオブジェクトでサポートされているインターフェイス識別子を取得すると、デバッガーはこのインターフェイスで定義されているメソッドを使用して、これらのインターフェイスに対応するマネージ型にマップすることができます。</span><span class="sxs-lookup"><span data-stu-id="5e92f-114">When the method retrieves the interface identifiers supported by a Windows Runtime server object, the debugger may use the methods defined in this interface to map them to managed types that correspond to those interfaces.</span></span>  
  
 <span data-ttu-id="5e92f-115">このインターフェイスのインスタンスを取得するには、のインスタンスに対して `QueryInterface` を実行します。</span><span class="sxs-lookup"><span data-stu-id="5e92f-115">To retrieve an instance of this interface, run `QueryInterface` on an instance of the ICorDebugAppDomain or ICorDebugAppDomain2 interface.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5e92f-116">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="5e92f-116">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5e92f-117">［要件］</span><span class="sxs-lookup"><span data-stu-id="5e92f-117">Requirements</span></span>  
 <span data-ttu-id="5e92f-118">**プラットフォーム:** Windows ランタイム</span><span class="sxs-lookup"><span data-stu-id="5e92f-118">**Platforms:** Windows Runtime</span></span>  
  
 <span data-ttu-id="5e92f-119">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5e92f-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5e92f-120">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5e92f-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5e92f-121">**.NET Framework のバージョン:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5e92f-121">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e92f-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="5e92f-122">See also</span></span>

- [<span data-ttu-id="5e92f-123">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="5e92f-123">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
