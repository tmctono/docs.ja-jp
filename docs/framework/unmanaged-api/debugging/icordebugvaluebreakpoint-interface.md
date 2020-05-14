---
title: ICorDebugValueBreakpoint インターフェイス
ms.date: 03/30/2017
api_name:
- ICorDebugValueBreakpoint
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValueBreakpoint
helpviewer_keywords:
- ICorDebugValueBreakpoint interface [.NET Framework debugging]
ms.assetid: c02338fe-da6c-467f-9567-70ebb387e901
topic_type:
- apiref
ms.openlocfilehash: 1183f9f6d1ac221b20767f0a1bab15b3e9665a61
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2020
ms.locfileid: "83396608"
---
# <a name="icordebugvaluebreakpoint-interface"></a><span data-ttu-id="38b84-102">ICorDebugValueBreakpoint インターフェイス</span><span class="sxs-lookup"><span data-stu-id="38b84-102">ICorDebugValueBreakpoint Interface</span></span>
<span data-ttu-id="38b84-103">ICorDebugBreakpoint インターフェイスを拡張して、特定の値にアクセスできるようにします。</span><span class="sxs-lookup"><span data-stu-id="38b84-103">Extends the ICorDebugBreakpoint interface to provide access to specific values.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="38b84-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="38b84-104">Methods</span></span>  
  
|<span data-ttu-id="38b84-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="38b84-105">Method</span></span>|<span data-ttu-id="38b84-106">説明</span><span class="sxs-lookup"><span data-stu-id="38b84-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="38b84-107">GetValue メソッド</span><span class="sxs-lookup"><span data-stu-id="38b84-107">GetValue Method</span></span>](icordebugvaluebreakpoint-getvalue-method.md)|<span data-ttu-id="38b84-108">ブレークポイントが設定されたオブジェクトの値を表す、ICorDebugValue オブジェクトへのインターフェイスポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="38b84-108">Gets an interface pointer to an ICorDebugValue object that represents the value of the object upon which the breakpoint is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="38b84-109">解説</span><span class="sxs-lookup"><span data-stu-id="38b84-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="38b84-110">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="38b84-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="38b84-111">要件</span><span class="sxs-lookup"><span data-stu-id="38b84-111">Requirements</span></span>  
 <span data-ttu-id="38b84-112">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="38b84-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="38b84-113">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="38b84-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="38b84-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="38b84-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="38b84-115">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="38b84-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38b84-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="38b84-116">See also</span></span>

- [<span data-ttu-id="38b84-117">デバッグのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="38b84-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
