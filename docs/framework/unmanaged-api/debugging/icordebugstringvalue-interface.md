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
ms.openlocfilehash: cff85a77b113440c2274910cae8ef93419d1bc1b
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/28/2019
ms.locfileid: "56965359"
---
# <a name="icordebugstringvalue-interface"></a><span data-ttu-id="1ef1d-102">ICorDebugStringValue インターフェイス</span><span class="sxs-lookup"><span data-stu-id="1ef1d-102">ICorDebugStringValue Interface</span></span>
<span data-ttu-id="1ef1d-103">文字列値に適用される ICorDebugHeapValue のサブクラスです。</span><span class="sxs-lookup"><span data-stu-id="1ef1d-103">A subclass of ICorDebugHeapValue that applies to string values.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="1ef1d-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="1ef1d-104">Methods</span></span>  
  
|<span data-ttu-id="1ef1d-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="1ef1d-105">Method</span></span>|<span data-ttu-id="1ef1d-106">説明</span><span class="sxs-lookup"><span data-stu-id="1ef1d-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="1ef1d-107">GetLength メソッド</span><span class="sxs-lookup"><span data-stu-id="1ef1d-107">GetLength Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstringvalue-getlength-method.md)|<span data-ttu-id="1ef1d-108">これによって参照される文字列内の文字数を取得`ICorDebugStringValue`します。</span><span class="sxs-lookup"><span data-stu-id="1ef1d-108">Gets the number of characters in the string referenced by this `ICorDebugStringValue`.</span></span>|  
|[<span data-ttu-id="1ef1d-109">GetString メソッド</span><span class="sxs-lookup"><span data-stu-id="1ef1d-109">GetString Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstringvalue-getstring-method.md)|<span data-ttu-id="1ef1d-110">これによって参照される文字列を取得します。`ICorDebugStringValue`します。</span><span class="sxs-lookup"><span data-stu-id="1ef1d-110">Gets the string referenced by this `ICorDebugStringValue`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1ef1d-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="1ef1d-111">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1ef1d-112">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="1ef1d-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1ef1d-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="1ef1d-113">Requirements</span></span>  
 <span data-ttu-id="1ef1d-114">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="1ef1d-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1ef1d-115">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1ef1d-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1ef1d-116">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1ef1d-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1ef1d-117">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1ef1d-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ef1d-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="1ef1d-118">See also</span></span>
- [<span data-ttu-id="1ef1d-119">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="1ef1d-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
