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
ms.openlocfilehash: d1d3a5eb6e0b24b40a35c13a99465dd3c7032a91
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138940"
---
# <a name="icordebugstringvalue-interface"></a><span data-ttu-id="73347-102">ICorDebugStringValue インターフェイス</span><span class="sxs-lookup"><span data-stu-id="73347-102">ICorDebugStringValue Interface</span></span>
<span data-ttu-id="73347-103">文字列値に適用される、値のサブクラスです。</span><span class="sxs-lookup"><span data-stu-id="73347-103">A subclass of ICorDebugHeapValue that applies to string values.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="73347-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="73347-104">Methods</span></span>  
  
|<span data-ttu-id="73347-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="73347-105">Method</span></span>|<span data-ttu-id="73347-106">説明</span><span class="sxs-lookup"><span data-stu-id="73347-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="73347-107">GetLength メソッド</span><span class="sxs-lookup"><span data-stu-id="73347-107">GetLength Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstringvalue-getlength-method.md)|<span data-ttu-id="73347-108">この `ICorDebugStringValue`によって参照される文字列の文字数を取得します。</span><span class="sxs-lookup"><span data-stu-id="73347-108">Gets the number of characters in the string referenced by this `ICorDebugStringValue`.</span></span>|  
|[<span data-ttu-id="73347-109">GetString メソッド</span><span class="sxs-lookup"><span data-stu-id="73347-109">GetString Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstringvalue-getstring-method.md)|<span data-ttu-id="73347-110">この `ICorDebugStringValue`によって参照される文字列を取得します。</span><span class="sxs-lookup"><span data-stu-id="73347-110">Gets the string referenced by this `ICorDebugStringValue`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="73347-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="73347-111">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="73347-112">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="73347-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="73347-113">［要件］</span><span class="sxs-lookup"><span data-stu-id="73347-113">Requirements</span></span>  
 <span data-ttu-id="73347-114">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="73347-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="73347-115">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="73347-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="73347-116">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="73347-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="73347-117">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="73347-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73347-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="73347-118">See also</span></span>

- [<span data-ttu-id="73347-119">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="73347-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
