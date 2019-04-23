---
title: ICorDebugCode4 インターフェイス
ms.date: 03/30/2017
api_name:
- ICorDebugCode4
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode4
helpviewer_keywords:
- ICorDebugCode4 interface [.NET Framework debugging]
ms.assetid: a3fdf523-274a-449c-920b-9fcb0aed1d97
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d23f588b46eb452b7670085249938f7d10cea1ba
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59108176"
---
# <a name="icordebugcode4-interface"></a><span data-ttu-id="a32ec-102">ICorDebugCode4 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a32ec-102">ICorDebugCode4 Interface</span></span>
<span data-ttu-id="a32ec-103">ローカル変数と関数の引数を列挙するためにデバッガーをできるようにするメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="a32ec-103">Provides a method that enables a debugger to enumerate the local variables and arguments in a function.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a32ec-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="a32ec-104">Methods</span></span>  
  
|<span data-ttu-id="a32ec-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="a32ec-105">Method</span></span>|<span data-ttu-id="a32ec-106">説明</span><span class="sxs-lookup"><span data-stu-id="a32ec-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a32ec-107">EnumerateVariableHomes メソッド</span><span class="sxs-lookup"><span data-stu-id="a32ec-107">EnumerateVariableHomes Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode4-enumeratevariablehomes-method.md)|<span data-ttu-id="a32ec-108">ローカル変数と引数を関数内の列挙子を取得します。</span><span class="sxs-lookup"><span data-stu-id="a32ec-108">Gets an enumerator to the local variables and arguments in a function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a32ec-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="a32ec-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a32ec-110">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="a32ec-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a32ec-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="a32ec-111">Requirements</span></span>  
 <span data-ttu-id="a32ec-112">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a32ec-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a32ec-113">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a32ec-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a32ec-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a32ec-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a32ec-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a32ec-115">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a32ec-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="a32ec-116">See also</span></span>

- [<span data-ttu-id="a32ec-117">ICorDebugCode3 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a32ec-117">ICorDebugCode3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-interface.md)
- [<span data-ttu-id="a32ec-118">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a32ec-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
