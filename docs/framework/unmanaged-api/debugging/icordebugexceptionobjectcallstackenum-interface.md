---
title: ICorDebugExceptionObjectCallStackEnum インターフェイス
ms.date: 03/30/2017
api_name:
- ICorDebugExceptionObjectCallStackEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugExceptionObjectCallStackEnum
helpviewer_keywords:
- ICorDebugExceptionObjectCallStackEnum interface [.NET Framework debugging]
ms.assetid: 39dffa18-c71b-48c4-b11d-e814631ab1e9
topic_type:
- apiref
ms.openlocfilehash: e6dd951b0f432d455d95bb60f4c42df64d5bee24
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2020
ms.locfileid: "82975993"
---
# <a name="icordebugexceptionobjectcallstackenum-interface"></a><span data-ttu-id="8a9c1-102">ICorDebugExceptionObjectCallStackEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8a9c1-102">ICorDebugExceptionObjectCallStackEnum Interface</span></span>
<span data-ttu-id="8a9c1-103">例外オブジェクトに埋め込まれているコール スタックの情報の列挙子を提供します。</span><span class="sxs-lookup"><span data-stu-id="8a9c1-103">Provides an enumerator for call stack information that is embedded in an exception object.</span></span> <span data-ttu-id="8a9c1-104">このインターフェイスは、ICorDebugEnum インターフェイスのサブクラスです。</span><span class="sxs-lookup"><span data-stu-id="8a9c1-104">This interface is a subclass of the ICorDebugEnum interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="8a9c1-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="8a9c1-105">Methods</span></span>  
  
|<span data-ttu-id="8a9c1-106">メソッド</span><span class="sxs-lookup"><span data-stu-id="8a9c1-106">Method</span></span>|<span data-ttu-id="8a9c1-107">説明</span><span class="sxs-lookup"><span data-stu-id="8a9c1-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="8a9c1-108">いい Exceptionobjectcallstackenum:: Next</span><span class="sxs-lookup"><span data-stu-id="8a9c1-108">ICorDebugExceptionObjectCallStackEnum::Next</span></span>](icordebugexceptionobjectcallstackenum-next-method.md)|<span data-ttu-id="8a9c1-109">例外オブジェクトの呼び出し履歴に関する情報を格納している、指定した数の[CorDebugExceptionObjectStackFrame](cordebugexceptionobjectstackframe-structure.md)オブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="8a9c1-109">Gets a specified number of [CorDebugExceptionObjectStackFrame](cordebugexceptionobjectstackframe-structure.md) objects that contain information about an exception object's call stack.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8a9c1-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="8a9c1-110">Remarks</span></span>  
 <span data-ttu-id="8a9c1-111">インターフェイス`ICorDebugExceptionObjectCallStackEnum`は、ICorDebugEnum インターフェイスを実装します。</span><span class="sxs-lookup"><span data-stu-id="8a9c1-111">The `ICorDebugExceptionObjectCallStackEnum` interface implements the ICorDebugEnum interface.</span></span>  
  
 <span data-ttu-id="8a9c1-112">CorDebugExceptionObjectStackFrame `ICorDebugExceptionObjectCallStackEnum`オブジェクトを使用し[CorDebugExceptionObjectStackFrame](cordebugexceptionobjectstackframe-structure.md)てインスタンスに値を設定するには、 [EnumerateExceptionCallStack](icordebugexceptionobjectvalue-enumerateexceptioncallstack-method.md)メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="8a9c1-112">An `ICorDebugExceptionObjectCallStackEnum` instance is populated with [CorDebugExceptionObjectStackFrame](cordebugexceptionobjectstackframe-structure.md) objects by calling the [ICorDebugExceptionObjectValue::EnumerateExceptionCallStack](icordebugexceptionobjectvalue-enumerateexceptioncallstack-method.md) method.</span></span> <span data-ttu-id="8a9c1-113">コレクション内のコールスタック項目を列挙するには、[次](icordebugexceptionobjectcallstackenum-next-method.md)のように指定します。</span><span class="sxs-lookup"><span data-stu-id="8a9c1-113">The call stack items in the collection can be enumerated by calling the [ICorDebugExceptionObjectCallStackEnum::Next](icordebugexceptionobjectcallstackenum-next-method.md) method</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8a9c1-114">必要条件</span><span class="sxs-lookup"><span data-stu-id="8a9c1-114">Requirements</span></span>  
 <span data-ttu-id="8a9c1-115">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8a9c1-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8a9c1-116">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8a9c1-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8a9c1-117">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8a9c1-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8a9c1-118">**.NET Framework のバージョン:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8a9c1-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a9c1-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="8a9c1-119">See also</span></span>

- [<span data-ttu-id="8a9c1-120">デバッグのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="8a9c1-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="8a9c1-121">デバッグ</span><span class="sxs-lookup"><span data-stu-id="8a9c1-121">Debugging</span></span>](index.md)
