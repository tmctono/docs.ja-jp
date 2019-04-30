---
title: ICorDebugExceptionObjectValue インターフェイス
ms.date: 03/30/2017
api_name:
- ICorDebugExceptionObjectValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugExceptionObjectValue
helpviewer_keywords:
- ICorDebugExceptionObjectValue interface [.NET Framework debugging]
ms.assetid: 43416dd5-8892-4106-9f59-f9143b19ddb4
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b5328442ceaee05b3f81466b785f04a361d456a8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61995918"
---
# <a name="icordebugexceptionobjectvalue-interface"></a><span data-ttu-id="43d0c-102">ICorDebugExceptionObjectValue インターフェイス</span><span class="sxs-lookup"><span data-stu-id="43d0c-102">ICorDebugExceptionObjectValue Interface</span></span>
<span data-ttu-id="43d0c-103">マネージ例外オブジェクトからスタック トレース情報を提供する"ICorDebugObjectValue"インターフェイスを拡張します。</span><span class="sxs-lookup"><span data-stu-id="43d0c-103">Extends the "ICorDebugObjectValue" interface to provide stack trace information from a managed exception object.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="43d0c-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="43d0c-104">Methods</span></span>  
  
|<span data-ttu-id="43d0c-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="43d0c-105">Method</span></span>|<span data-ttu-id="43d0c-106">説明</span><span class="sxs-lookup"><span data-stu-id="43d0c-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="43d0c-107">EnumerateExceptionCallStack メソッド</span><span class="sxs-lookup"><span data-stu-id="43d0c-107">EnumerateExceptionCallStack Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectvalue-enumerateexceptioncallstack-method.md)|<span data-ttu-id="43d0c-108">呼び出し履歴を例外オブジェクトに埋め込まれている列挙子を取得します。</span><span class="sxs-lookup"><span data-stu-id="43d0c-108">Gets an enumerator to the call stack embedded in an exception object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="43d0c-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="43d0c-109">Remarks</span></span>  
 <span data-ttu-id="43d0c-110">呼び出し`QueryInterface`から派生したマネージ オブジェクトが成功した<xref:System.Exception?displayProperty=nameWithType>します。</span><span class="sxs-lookup"><span data-stu-id="43d0c-110">The call to `QueryInterface` will succeed for managed objects that derive from <xref:System.Exception?displayProperty=nameWithType>.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="43d0c-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="43d0c-111">Requirements</span></span>  
 <span data-ttu-id="43d0c-112">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="43d0c-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="43d0c-113">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="43d0c-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="43d0c-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="43d0c-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="43d0c-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="43d0c-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43d0c-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="43d0c-116">See also</span></span>

- [<span data-ttu-id="43d0c-117">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="43d0c-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="43d0c-118">デバッグ</span><span class="sxs-lookup"><span data-stu-id="43d0c-118">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
