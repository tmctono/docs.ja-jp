---
title: ICorDebugGuidToTypeEnum インターフェイス
ms.date: 03/30/2017
api_name:
- ICorDebugGuidToTypeEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugGuidToTypeEnum
helpviewer_keywords:
- ICorDebugGuidToTypeEnum interface [.NET Framework debugging]
ms.assetid: aa32b12b-05fc-4ea8-a904-adae25034269
topic_type:
- apiref
ms.openlocfilehash: da921644c4d967efb0d88060ada0332c5eb63965
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138528"
---
# <a name="icordebugguidtotypeenum-interface"></a><span data-ttu-id="086f8-102">ICorDebugGuidToTypeEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="086f8-102">ICorDebugGuidToTypeEnum Interface</span></span>
<span data-ttu-id="086f8-103">整数のセットとそれに対応する型の間のマッピングを定義する列挙子を提供します。これは、テキストインスタンスによって表されます。</span><span class="sxs-lookup"><span data-stu-id="086f8-103">Provides an enumerator that defines the mapping between a set of GUIDs and their corresponding types, which are represented by ICorDebugType instances.</span></span> <span data-ttu-id="086f8-104">このインターフェイスは、ICorDebugEnum インターフェイスからメソッドを継承します。</span><span class="sxs-lookup"><span data-stu-id="086f8-104">This interface inherits the methods from the ICorDebugEnum interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="086f8-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="086f8-105">Methods</span></span>  
  
|<span data-ttu-id="086f8-106">メソッド</span><span class="sxs-lookup"><span data-stu-id="086f8-106">Method</span></span>|<span data-ttu-id="086f8-107">説明</span><span class="sxs-lookup"><span data-stu-id="086f8-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="086f8-108">いいね Totypeenum:: Next</span><span class="sxs-lookup"><span data-stu-id="086f8-108">ICorDebugGuidToTypeEnum::Next</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugguidtotypeenum-next-method.md)|<span data-ttu-id="086f8-109">Guid を型情報にマップする、指定された数の[Cordebugguidtotypemapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md)インスタンスを取得します。</span><span class="sxs-lookup"><span data-stu-id="086f8-109">Gets the specified number of [CorDebugGuidToTypeMapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) instances that map GUIDs to type information.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="086f8-110">コメント</span><span class="sxs-lookup"><span data-stu-id="086f8-110">Remarks</span></span>  
 <span data-ttu-id="086f8-111">`ICorDebugGuidToTypeEnum` インターフェイスオブジェクトは、 [ICorDebugAppDomain3:: GetCachedWinRTTypes](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-getcachedwinrttypes-method.md)メソッドを呼び出すことによって取得できます。</span><span class="sxs-lookup"><span data-stu-id="086f8-111">An `ICorDebugGuidToTypeEnum` interface object can be retrieved by calling the [ICorDebugAppDomain3::GetCachedWinRTTypes](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-getcachedwinrttypes-method.md) method.</span></span> <span data-ttu-id="086f8-112">デバッガーは、このインターフェイスの[次](../../../../docs/framework/unmanaged-api/debugging/icordebugguidtotypeenum-next-method.md)のメソッドを呼び出して、の 呼び出しに使用されるアプリケーションドメインに読み込まれた Windows ランタイム型のマネージ表現のマッピングを表す [cordebugguidtotypemapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) オブジェクトを取得できます。[ICorDebugAppDomain3:: GetCachedWinRTTypes](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-getcachedwinrttypes-method.md)メソッド。</span><span class="sxs-lookup"><span data-stu-id="086f8-112">A debugger can call this interface's [Next](../../../../docs/framework/unmanaged-api/debugging/icordebugguidtotypeenum-next-method.md) method to retrieve [CorDebugGuidToTypeMapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) objects that represent mappings of managed representations of Windows Runtime types loaded in the application domain used for the call to the [ICorDebugAppDomain3::GetCachedWinRTTypes](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-getcachedwinrttypes-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="086f8-113">要件</span><span class="sxs-lookup"><span data-stu-id="086f8-113">Requirements</span></span>  
 <span data-ttu-id="086f8-114">**・** Windows ランタイム</span><span class="sxs-lookup"><span data-stu-id="086f8-114">**Platforms:** Windows Runtime</span></span>  
  
 <span data-ttu-id="086f8-115">**ヘッダー:** CorDebug .idl、CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="086f8-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="086f8-116">**ライブラリ**CorGuids .lib</span><span class="sxs-lookup"><span data-stu-id="086f8-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="086f8-117">**.NET Framework のバージョン:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="086f8-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="086f8-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="086f8-118">See also</span></span>

- [<span data-ttu-id="086f8-119">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="086f8-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
