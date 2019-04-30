---
title: ICorDebugStringValue インターフェイス
ms.date: 03/30/2017
api_name:
- ICorDebugStringValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStringValue
helpviewer_keywords:
- ICorDebugStringValue interface [.NET Framework debugging]
ms.assetid: bf84d0af-53e1-4c04-bc5b-7e5f81ba2cc2
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6709b14ce8e7bc131f9feb7a277fb41851ee4352
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61994267"
---
# <a name="icordebugstringvalue-interface"></a><span data-ttu-id="cfa5c-102">ICorDebugStringValue インターフェイス</span><span class="sxs-lookup"><span data-stu-id="cfa5c-102">ICorDebugStringValue Interface</span></span>
<span data-ttu-id="cfa5c-103">文字列値に適用される ICorDebugHeapValue のサブクラスです。</span><span class="sxs-lookup"><span data-stu-id="cfa5c-103">A subclass of ICorDebugHeapValue that applies to string values.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="cfa5c-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="cfa5c-104">Methods</span></span>  
  
|<span data-ttu-id="cfa5c-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="cfa5c-105">Method</span></span>|<span data-ttu-id="cfa5c-106">説明</span><span class="sxs-lookup"><span data-stu-id="cfa5c-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="cfa5c-107">GetLength メソッド</span><span class="sxs-lookup"><span data-stu-id="cfa5c-107">GetLength Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstringvalue-getlength-method.md)|<span data-ttu-id="cfa5c-108">これによって参照される文字列内の文字数を取得`ICorDebugStringValue`します。</span><span class="sxs-lookup"><span data-stu-id="cfa5c-108">Gets the number of characters in the string referenced by this `ICorDebugStringValue`.</span></span>|  
|[<span data-ttu-id="cfa5c-109">GetString メソッド</span><span class="sxs-lookup"><span data-stu-id="cfa5c-109">GetString Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstringvalue-getstring-method.md)|<span data-ttu-id="cfa5c-110">これによって参照される文字列を取得します。`ICorDebugStringValue`します。</span><span class="sxs-lookup"><span data-stu-id="cfa5c-110">Gets the string referenced by this `ICorDebugStringValue`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cfa5c-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="cfa5c-111">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cfa5c-112">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="cfa5c-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cfa5c-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="cfa5c-113">Requirements</span></span>  
 <span data-ttu-id="cfa5c-114">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="cfa5c-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cfa5c-115">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cfa5c-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cfa5c-116">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cfa5c-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cfa5c-117">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cfa5c-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cfa5c-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="cfa5c-118">See also</span></span>

- [<span data-ttu-id="cfa5c-119">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="cfa5c-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
