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
ms.openlocfilehash: fa154d0bb48f4ecd4fc6a50ce22fd13c592b7c40
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76782732"
---
# <a name="icordebugexceptionobjectvalue-interface"></a><span data-ttu-id="38711-102">ICorDebugExceptionObjectValue インターフェイス</span><span class="sxs-lookup"><span data-stu-id="38711-102">ICorDebugExceptionObjectValue Interface</span></span>
<span data-ttu-id="38711-103">"は、マネージ例外オブジェクトからスタックトレース情報を提供するために、" は、"" のような "のインターフェイスを拡張します。</span><span class="sxs-lookup"><span data-stu-id="38711-103">Extends the "ICorDebugObjectValue" interface to provide stack trace information from a managed exception object.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="38711-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="38711-104">Methods</span></span>  
  
|<span data-ttu-id="38711-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="38711-105">Method</span></span>|<span data-ttu-id="38711-106">説明</span><span class="sxs-lookup"><span data-stu-id="38711-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="38711-107">EnumerateExceptionCallStack メソッド</span><span class="sxs-lookup"><span data-stu-id="38711-107">EnumerateExceptionCallStack Method</span></span>](icordebugexceptionobjectvalue-enumerateexceptioncallstack-method.md)|<span data-ttu-id="38711-108">例外オブジェクトに埋め込まれている呼び出し履歴に対する列挙子を取得します。</span><span class="sxs-lookup"><span data-stu-id="38711-108">Gets an enumerator to the call stack embedded in an exception object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="38711-109">コメント</span><span class="sxs-lookup"><span data-stu-id="38711-109">Remarks</span></span>  
 <span data-ttu-id="38711-110">`QueryInterface` の呼び出しは、<xref:System.Exception?displayProperty=nameWithType>から派生したマネージオブジェクトに対して成功します。</span><span class="sxs-lookup"><span data-stu-id="38711-110">The call to `QueryInterface` will succeed for managed objects that derive from <xref:System.Exception?displayProperty=nameWithType>.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="38711-111">要件</span><span class="sxs-lookup"><span data-stu-id="38711-111">Requirements</span></span>  
 <span data-ttu-id="38711-112">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="38711-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="38711-113">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="38711-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="38711-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="38711-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="38711-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="38711-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38711-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="38711-116">See also</span></span>

- [<span data-ttu-id="38711-117">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="38711-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="38711-118">デバッグ</span><span class="sxs-lookup"><span data-stu-id="38711-118">Debugging</span></span>](index.md)
