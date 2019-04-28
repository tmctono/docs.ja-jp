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
ms.openlocfilehash: 7c141ca9a8e1c74015883f45cb2eaa9183bb3d89
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61922292"
---
# <a name="icordebugappdomain3-interface"></a><span data-ttu-id="92d8f-102">ICorDebugAppDomain3 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="92d8f-102">ICorDebugAppDomain3 Interface</span></span>
<span data-ttu-id="92d8f-103">マネージ表現に関する情報を取得するメソッドを提供[!INCLUDE[wrt](../../../../includes/wrt-md.md)]アプリケーション ドメインで現在読み込まれている型。</span><span class="sxs-lookup"><span data-stu-id="92d8f-103">Provides methods to retrieve information about the managed representations of [!INCLUDE[wrt](../../../../includes/wrt-md.md)] types currently loaded in an application domain.</span></span> <span data-ttu-id="92d8f-104">このインターフェイスは、ICorDebugAppDomain および ICorDebugAppDomain2 インターフェイスの拡張です。</span><span class="sxs-lookup"><span data-stu-id="92d8f-104">This interface is an extension of the ICorDebugAppDomain and ICorDebugAppDomain2 interfaces.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="92d8f-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="92d8f-105">Methods</span></span>  
  
|<span data-ttu-id="92d8f-106">メソッド</span><span class="sxs-lookup"><span data-stu-id="92d8f-106">Method</span></span>|<span data-ttu-id="92d8f-107">説明</span><span class="sxs-lookup"><span data-stu-id="92d8f-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="92d8f-108">ICorDebugAppDomain3::GetCachedWinRTTypes</span><span class="sxs-lookup"><span data-stu-id="92d8f-108">ICorDebugAppDomain3::GetCachedWinRTTypes</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-getcachedwinrttypes-method.md)|<span data-ttu-id="92d8f-109">キャッシュされたすべての列挙子を取得します。[!INCLUDE[wrt](../../../../includes/wrt-md.md)]型。</span><span class="sxs-lookup"><span data-stu-id="92d8f-109">Gets an enumerator for all cached [!INCLUDE[wrt](../../../../includes/wrt-md.md)] types.</span></span>|  
|[<span data-ttu-id="92d8f-110">ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs</span><span class="sxs-lookup"><span data-stu-id="92d8f-110">ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-getcachedwinrttypesforiids-method.md)|<span data-ttu-id="92d8f-111">キャッシュされた列挙子を取得[!INCLUDE[wrt](../../../../includes/wrt-md.md)]アプリケーション ドメイン内の型、インターフェイスの id に基づいています。</span><span class="sxs-lookup"><span data-stu-id="92d8f-111">Gets an enumerator for cached [!INCLUDE[wrt](../../../../includes/wrt-md.md)] types in an application domain based on their interface identifiers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="92d8f-112">Remarks</span><span class="sxs-lookup"><span data-stu-id="92d8f-112">Remarks</span></span>  
 <span data-ttu-id="92d8f-113">このインターフェイスは、関数の評価の呼び出しと組み合わせて、デバッガーによって使用されるものでは`M:System.Runtime.InteropServices.Marshal.GetInspectableIIDs(System.Object)`します。</span><span class="sxs-lookup"><span data-stu-id="92d8f-113">This interface is meant to be used by a debugger in conjunction with a function evaluation call to `M:System.Runtime.InteropServices.Marshal.GetInspectableIIDs(System.Object)`.</span></span> <span data-ttu-id="92d8f-114">メソッドはによってサポートされるインターフェイスの識別子を取得すると、[!INCLUDE[wrt](../../../../includes/wrt-md.md)]サーバー オブジェクトをデバッガーでこのインターフェイスで定義されているメソッドを使用してそれらのインターフェイスに対応するマネージ型に割り当てる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="92d8f-114">When the method retrieves the interface identifiers supported by a [!INCLUDE[wrt](../../../../includes/wrt-md.md)] server object, the debugger may use the methods defined in this interface to map them to managed types that correspond to those interfaces.</span></span>  
  
 <span data-ttu-id="92d8f-115">このインターフェイスのインスタンスを取得するには実行`QueryInterface`ICorDebugAppDomain または ICorDebugAppDomain2 インターフェイスのインスタンスにします。</span><span class="sxs-lookup"><span data-stu-id="92d8f-115">To retrieve an instance of this interface, run `QueryInterface` on an instance of the ICorDebugAppDomain or ICorDebugAppDomain2 interface.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="92d8f-116">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="92d8f-116">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="92d8f-117">必要条件</span><span class="sxs-lookup"><span data-stu-id="92d8f-117">Requirements</span></span>  
 <span data-ttu-id="92d8f-118">**プラットフォーム:** [!INCLUDE[wrt](../../../../includes/wrt-md.md)]</span><span class="sxs-lookup"><span data-stu-id="92d8f-118">**Platforms:** [!INCLUDE[wrt](../../../../includes/wrt-md.md)]</span></span>  
  
 <span data-ttu-id="92d8f-119">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="92d8f-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="92d8f-120">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="92d8f-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="92d8f-121">**.NET Framework のバージョン:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="92d8f-121">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92d8f-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="92d8f-122">See also</span></span>

- [<span data-ttu-id="92d8f-123">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="92d8f-123">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
