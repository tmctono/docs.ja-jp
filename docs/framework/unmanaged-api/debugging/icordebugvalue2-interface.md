---
title: ICorDebugValue2 インターフェイス
ms.date: 03/30/2017
api_name:
- ICorDebugValue2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValue2
helpviewer_keywords:
- ICorDebugValue2 interface [.NET Framework debugging]
ms.assetid: 3ff2ad2a-da5a-461b-8627-1a8eba49df9c
topic_type:
- apiref
ms.openlocfilehash: c6f20b0f7927d79ee56b5b6962137d668dc048d1
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791111"
---
# <a name="icordebugvalue2-interface"></a><span data-ttu-id="e0bf7-102">ICorDebugValue2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e0bf7-102">ICorDebugValue2 Interface</span></span>
<span data-ttu-id="e0bf7-103">"ICorDebugValue" インターフェイスを拡張して "テキスト" オブジェクトのサポートを提供します。</span><span class="sxs-lookup"><span data-stu-id="e0bf7-103">Extends the "ICorDebugValue" interface to provide support for "ICorDebugType" objects.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e0bf7-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="e0bf7-104">Methods</span></span>  
  
|<span data-ttu-id="e0bf7-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="e0bf7-105">Method</span></span>|<span data-ttu-id="e0bf7-106">説明</span><span class="sxs-lookup"><span data-stu-id="e0bf7-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e0bf7-107">GetExactType メソッド</span><span class="sxs-lookup"><span data-stu-id="e0bf7-107">GetExactType Method</span></span>](icordebugvalue2-getexacttype-method.md)|<span data-ttu-id="e0bf7-108">この値の <xref:System.Type> を表す `ICorDebugType` オブジェクトへのインターフェイスポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="e0bf7-108">Gets an interface pointer to an `ICorDebugType` object that represents the <xref:System.Type> of this value.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e0bf7-109">コメント</span><span class="sxs-lookup"><span data-stu-id="e0bf7-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e0bf7-110">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="e0bf7-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e0bf7-111">要件</span><span class="sxs-lookup"><span data-stu-id="e0bf7-111">Requirements</span></span>  
 <span data-ttu-id="e0bf7-112">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e0bf7-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e0bf7-113">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e0bf7-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e0bf7-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e0bf7-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e0bf7-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e0bf7-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0bf7-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="e0bf7-116">See also</span></span>

- [<span data-ttu-id="e0bf7-117">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e0bf7-117">Debugging Interfaces</span></span>](debugging-interfaces.md)

- [<span data-ttu-id="e0bf7-118">ICorDebugValue3 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e0bf7-118">ICorDebugValue3 Interface</span></span>](icordebugvalue3-interface.md)
