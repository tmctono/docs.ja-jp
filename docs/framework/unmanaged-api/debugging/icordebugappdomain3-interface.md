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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 256fd900fa73948b4ca42ac6b6f21f145effc461
ms.sourcegitcommit: 5bc85ad81d96b8dc2a90ce53bada475ee5662c44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/12/2019
ms.locfileid: "67025885"
---
# <a name="icordebugappdomain3-interface"></a><span data-ttu-id="55360-102">ICorDebugAppDomain3 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="55360-102">ICorDebugAppDomain3 Interface</span></span>
<span data-ttu-id="55360-103">アプリケーション ドメインで現在読み込まれている Windows ランタイム型のマネージ表現についての情報を取得するメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="55360-103">Provides methods to retrieve information about the managed representations of Windows Runtime types currently loaded in an application domain.</span></span> <span data-ttu-id="55360-104">このインターフェイスは、ICorDebugAppDomain および ICorDebugAppDomain2 インターフェイスの拡張です。</span><span class="sxs-lookup"><span data-stu-id="55360-104">This interface is an extension of the ICorDebugAppDomain and ICorDebugAppDomain2 interfaces.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="55360-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="55360-105">Methods</span></span>  
  
|<span data-ttu-id="55360-106">メソッド</span><span class="sxs-lookup"><span data-stu-id="55360-106">Method</span></span>|<span data-ttu-id="55360-107">説明</span><span class="sxs-lookup"><span data-stu-id="55360-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="55360-108">ICorDebugAppDomain3::GetCachedWinRTTypes</span><span class="sxs-lookup"><span data-stu-id="55360-108">ICorDebugAppDomain3::GetCachedWinRTTypes</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-getcachedwinrttypes-method.md)|<span data-ttu-id="55360-109">キャッシュされたすべての Windows ランタイム型の列挙子を取得します。</span><span class="sxs-lookup"><span data-stu-id="55360-109">Gets an enumerator for all cached Windows Runtime types.</span></span>|  
|[<span data-ttu-id="55360-110">ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs</span><span class="sxs-lookup"><span data-stu-id="55360-110">ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-getcachedwinrttypesforiids-method.md)|<span data-ttu-id="55360-111">インターフェイスの識別子に基づいて、アプリケーション ドメインで、キャッシュ済みの Windows ランタイム型の列挙子を取得します。</span><span class="sxs-lookup"><span data-stu-id="55360-111">Gets an enumerator for cached Windows Runtime types in an application domain based on their interface identifiers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="55360-112">Remarks</span><span class="sxs-lookup"><span data-stu-id="55360-112">Remarks</span></span>  
 <span data-ttu-id="55360-113">このインターフェイスは、関数の評価の呼び出しと組み合わせて、デバッガーによって使用されるものでは`M:System.Runtime.InteropServices.Marshal.GetInspectableIIDs(System.Object)`します。</span><span class="sxs-lookup"><span data-stu-id="55360-113">This interface is meant to be used by a debugger in conjunction with a function evaluation call to `M:System.Runtime.InteropServices.Marshal.GetInspectableIIDs(System.Object)`.</span></span> <span data-ttu-id="55360-114">メソッドは、Windows ランタイムのサーバー オブジェクトでサポートされているインターフェイスの識別子を取得するとき、デバッガーは、それらのインターフェイスに対応するマネージ型にマップをこのインターフェイスで定義されているメソッドを使用できます。</span><span class="sxs-lookup"><span data-stu-id="55360-114">When the method retrieves the interface identifiers supported by a Windows Runtime server object, the debugger may use the methods defined in this interface to map them to managed types that correspond to those interfaces.</span></span>  
  
 <span data-ttu-id="55360-115">このインターフェイスのインスタンスを取得するには実行`QueryInterface`ICorDebugAppDomain または ICorDebugAppDomain2 インターフェイスのインスタンスにします。</span><span class="sxs-lookup"><span data-stu-id="55360-115">To retrieve an instance of this interface, run `QueryInterface` on an instance of the ICorDebugAppDomain or ICorDebugAppDomain2 interface.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="55360-116">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="55360-116">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="55360-117">必要条件</span><span class="sxs-lookup"><span data-stu-id="55360-117">Requirements</span></span>  
 <span data-ttu-id="55360-118">**プラットフォーム:** Windows ランタイム</span><span class="sxs-lookup"><span data-stu-id="55360-118">**Platforms:** Windows Runtime</span></span>  
  
 <span data-ttu-id="55360-119">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="55360-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="55360-120">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="55360-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="55360-121">**.NET Framework のバージョン:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="55360-121">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55360-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="55360-122">See also</span></span>

- [<span data-ttu-id="55360-123">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="55360-123">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
