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
ms.openlocfilehash: 2663e5604cdd55472cc148b2d2b38599df81f11e
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76794438"
---
# <a name="icordebugguidtotypeenum-interface"></a><span data-ttu-id="4920b-102">ICorDebugGuidToTypeEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="4920b-102">ICorDebugGuidToTypeEnum Interface</span></span>
<span data-ttu-id="4920b-103">整数のセットとそれに対応する型の間のマッピングを定義する列挙子を提供します。これは、テキストインスタンスによって表されます。</span><span class="sxs-lookup"><span data-stu-id="4920b-103">Provides an enumerator that defines the mapping between a set of GUIDs and their corresponding types, which are represented by ICorDebugType instances.</span></span> <span data-ttu-id="4920b-104">このインターフェイスは、ICorDebugEnum インターフェイスからメソッドを継承します。</span><span class="sxs-lookup"><span data-stu-id="4920b-104">This interface inherits the methods from the ICorDebugEnum interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="4920b-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="4920b-105">Methods</span></span>  
  
|<span data-ttu-id="4920b-106">メソッド</span><span class="sxs-lookup"><span data-stu-id="4920b-106">Method</span></span>|<span data-ttu-id="4920b-107">説明</span><span class="sxs-lookup"><span data-stu-id="4920b-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="4920b-108">いいね Totypeenum:: Next</span><span class="sxs-lookup"><span data-stu-id="4920b-108">ICorDebugGuidToTypeEnum::Next</span></span>](icordebugguidtotypeenum-next-method.md)|<span data-ttu-id="4920b-109">Guid を型情報にマップする、指定された数の[Cordebugguidtotypemapping](cordebugguidtotypemapping-structure.md)インスタンスを取得します。</span><span class="sxs-lookup"><span data-stu-id="4920b-109">Gets the specified number of [CorDebugGuidToTypeMapping](cordebugguidtotypemapping-structure.md) instances that map GUIDs to type information.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4920b-110">コメント</span><span class="sxs-lookup"><span data-stu-id="4920b-110">Remarks</span></span>  
 <span data-ttu-id="4920b-111">`ICorDebugGuidToTypeEnum` インターフェイスオブジェクトは、 [ICorDebugAppDomain3:: GetCachedWinRTTypes](icordebugappdomain3-getcachedwinrttypes-method.md)メソッドを呼び出すことによって取得できます。</span><span class="sxs-lookup"><span data-stu-id="4920b-111">An `ICorDebugGuidToTypeEnum` interface object can be retrieved by calling the [ICorDebugAppDomain3::GetCachedWinRTTypes](icordebugappdomain3-getcachedwinrttypes-method.md) method.</span></span> <span data-ttu-id="4920b-112">デバッガーは、このインターフェイスの[Next](icordebugguidtotypeenum-next-method.md)メソッドを呼び出して、 [ICorDebugAppDomain3:: GetCachedWinRTTypes](icordebugappdomain3-getcachedwinrttypes-method.md)メソッドの呼び出しに使用されるアプリケーションドメインに読み込まれた Windows ランタイム型のマネージ表現のマッピングを表す[cordebugguidtotypemapping](cordebugguidtotypemapping-structure.md)オブジェクトを取得できます。</span><span class="sxs-lookup"><span data-stu-id="4920b-112">A debugger can call this interface's [Next](icordebugguidtotypeenum-next-method.md) method to retrieve [CorDebugGuidToTypeMapping](cordebugguidtotypemapping-structure.md) objects that represent mappings of managed representations of Windows Runtime types loaded in the application domain used for the call to the [ICorDebugAppDomain3::GetCachedWinRTTypes](icordebugappdomain3-getcachedwinrttypes-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4920b-113">要件</span><span class="sxs-lookup"><span data-stu-id="4920b-113">Requirements</span></span>  
 <span data-ttu-id="4920b-114">**プラットフォーム:** Windows ランタイム</span><span class="sxs-lookup"><span data-stu-id="4920b-114">**Platforms:** Windows Runtime</span></span>  
  
 <span data-ttu-id="4920b-115">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4920b-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4920b-116">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4920b-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4920b-117">**.NET Framework のバージョン:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4920b-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4920b-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="4920b-118">See also</span></span>

- [<span data-ttu-id="4920b-119">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="4920b-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
