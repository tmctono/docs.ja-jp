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
ms.openlocfilehash: 5537a48fd085ce98de855fa1ec0913e2637e58e0
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2020
ms.locfileid: "83376194"
---
# <a name="icordebugstringvalue-interface"></a><span data-ttu-id="046e5-102">ICorDebugStringValue インターフェイス</span><span class="sxs-lookup"><span data-stu-id="046e5-102">ICorDebugStringValue Interface</span></span>
<span data-ttu-id="046e5-103">文字列値に適用される、値のサブクラスです。</span><span class="sxs-lookup"><span data-stu-id="046e5-103">A subclass of ICorDebugHeapValue that applies to string values.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="046e5-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="046e5-104">Methods</span></span>  
  
|<span data-ttu-id="046e5-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="046e5-105">Method</span></span>|<span data-ttu-id="046e5-106">説明</span><span class="sxs-lookup"><span data-stu-id="046e5-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="046e5-107">GetLength メソッド</span><span class="sxs-lookup"><span data-stu-id="046e5-107">GetLength Method</span></span>](icordebugstringvalue-getlength-method.md)|<span data-ttu-id="046e5-108">このによって参照される文字列の文字数を取得し `ICorDebugStringValue` ます。</span><span class="sxs-lookup"><span data-stu-id="046e5-108">Gets the number of characters in the string referenced by this `ICorDebugStringValue`.</span></span>|  
|[<span data-ttu-id="046e5-109">GetString メソッド</span><span class="sxs-lookup"><span data-stu-id="046e5-109">GetString Method</span></span>](icordebugstringvalue-getstring-method.md)|<span data-ttu-id="046e5-110">このによって参照される文字列を取得し `ICorDebugStringValue` ます。</span><span class="sxs-lookup"><span data-stu-id="046e5-110">Gets the string referenced by this `ICorDebugStringValue`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="046e5-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="046e5-111">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="046e5-112">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="046e5-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="046e5-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="046e5-113">Requirements</span></span>  
 <span data-ttu-id="046e5-114">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="046e5-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="046e5-115">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="046e5-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="046e5-116">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="046e5-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="046e5-117">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="046e5-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="046e5-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="046e5-118">See also</span></span>

- [<span data-ttu-id="046e5-119">デバッグのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="046e5-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
